---
title: .plist を使用して macOS 用に Microsoft Edge を構成する
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 02/14/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: .plist を使用して macOS で Microsoft Edge ポリシー設定を構成する
ms.openlocfilehash: 84469a4f84deeee0e47b6d8899426fa36cf345aa
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980352"
---
# .plist を使用して macOS 用に Microsoft Edge ポリシー設定を構成する

この記事では、macOS でプロパティ リスト (.plist) ファイルを使用して Microsoft Edge を構成する方法について説明します。 このファイルを作成して、Microsoft Intune に展開する方法について説明します。

詳しくは、[情報プロパティ リスト ファイルに関するページ](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (Apple の Web サイト) と「[カスタム ペイロードの設定](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1)」をご覧ください。

> [!NOTE]
> この記事は Microsoft Edge version 77 以降に適用されます。

## macOS で Microsoft Edge ポリシーを構成する

まず、plist を作成します。 任意のテキスト エディターを使用して plist ファイルを作成することも、[ターミナルを使用して構成プロファイルを作成する](#create-a-configuration-profile-using-terminal)こともできます。 ただし、XML コードの書式設定が行われるツールを使用する方が、plist ファイルの作成および編集が簡単になります。 *Xcode* は、無料の統合開発環境です。次のいずれかの場所から入手できます。

- [Apple Developer Web サイト](https://developer.apple.com/xcode/)
- [Mac App Store](https://apps.apple.com/app/xcode/id497799835?mt=12)

サポートされているポリシーと、対応する基本設定キー名については、[Microsoft Edge ブラウザー ポリシー リファレンス](microsoft-edge-policies.md)をご覧ください。 [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードできるポリシー テンプレート ファイルの **examples** フォルダーには、plist の例 (*itadminexample.plist*) が含まれています。 このサンプル ファイルには、サポートされているすべてのデータ型が含まれており、これらはカスタマイズしてポリシー設定の定義に使用できます。 

plist のコンテンツを作成できたら、次の手順は、Microsoft Edge の基本設定ドメイン *com.microsoft.Edge* を使用して名前を付けることです。 この名前では、大文字と小文字が区別されます。また、すべての Microsoft Edge チャネルに適用されるため、ターゲットにするチャネルを含めないでください。 plist ファイル名は、「**_com.microsoft.Edge.plist_**」とする必要があります。 

> [!IMPORTANT]
> ビルド 78.0.249.2 以降、macOS 上のすべての Microsoft Edge チャネルは **com.microsoft.Edge** 基本設定ドメインから読み込まれます。 それより前のリリースはすべて、チャネル固有のドメインから読み込まれます (例: Dev チャネルの場合は **com.microsoft.Edge.Dev**)。

最後に、Microsoft Intune など、好みの MDM プロバイダーを使用して、ユーザーの Mac デバイスに plist を展開します。 手順については、「[plist を展開する](#deploy-your-plist)」をご覧ください。

### ターミナルを使用して構成プロファイルを作成する

1. ターミナルで次のコマンドを使用して、好みの設定でデスクトップ上の Microsoft Edge の plist を作成します。

   ```cmd
   /usr/bin/defaults write ~/Desktop/com.microsoft.Edge.plist RestoreOnStartup -int 1
   ```

2. plist をバイナリからプレーンテキスト形式に変換します。

   ```cmd
   /usr/bin/plutil -convert xml1 ~/Desktop/com.microsoft.Edge.plist
   ```
ファイルを変換した後、ポリシー データが正しく、構成プロファイルに必要な設定が含まれていることを確認します。

> [!NOTE]
> plist または xml ファイルは、内容としてキーと値のペアのみが含まれている状態にします。 ファイルを Intune にアップロードする前に、すべての \<plist> と \<dict> の値と xml ヘッダーをファイルから削除します。 ファイルは、キーと値のペアのみが含まれている状態にします。

## plist を展開する

Microsoft Intune の場合は、macOS プラットフォームをターゲットとした新しいデバイス構成プロファイルを作成し、プロファイルの種類として *[Preference file]* (基本設定ファイル) を選択します。 基本設定ドメイン名として **com.microsoft.Edge** を指定し、plist をアップロードします。 詳しくは、「[Microsoft Intune を使用して macOS デバイスにプロパティ リスト ファイルを追加する](https://docs.microsoft.com/intune/configuration/preference-file-settings-macos)」をご覧ください。

Jamf の場合は、[*カスタム設定*] ペイロードとして .plist ファイルをアップロードします。

## よく寄せられる質問

### Microsoft Edge は、マスター基本設定が使用されるように構成できますか?

Microsoft Edge は、マスター基本設定ファイルが使用されるように構成できます。

マスター基本設定ファイルを使用すると、Microsoft Edge を展開する際に、ブラウザー ユーザー プロファイルの既定の設定を構成できます。 マスター基本設定ファイルを使用すると、デバイス管理システムで管理されていないコンピューターに設定を適用することもできます。 これらの設定は、ユーザーがブラウザーを初めて実行するときに、ユーザーのプロファイルに適用されます。 ユーザーがブラウザーを実行した後で発生した、マスター基本設定ファイルへの変更は適用されません。 ユーザーは、ブラウザーでマスター基本設定の設定を変更できます。 ブラウザーを初めて実行した後に設定を必須にしたり、設定を変更したりする場合は、ポリシーを使用する必要があります。

マスター基本設定ファイルを使用すると、ブラウザーのさまざまな設定や基本設定をカスタマイズできます。これには、他の Chromium ベースのブラウザーと共有されるものや、Microsoft Edge に固有のものも含まれます。  ポリシー関連の基本設定は、マスター基本設定ファイルを使用して構成できます。 ポリシーが設定され、対応するマスター基本設定が設定されている場合は、ポリシー設定が優先されます。

> [!IMPORTANT]
> 利用可能なすべての基本設定が Microsoft Edge の用語や命名規則と一致していないこともあります。  これらの基本設定が今後のリリースでも引き続き期待どおりに動作することは保証されません。 今後のバージョンでは、基本設定が変更または無視される可能性もあります。

マスター基本設定ファイルは、JSON マークアップを使用して書式設定されたテキスト ファイルです。 このファイルは、msedge.exe 実行可能ファイルと同じディレクトリに追加する必要があります。 macOS でのシステム全体のエンタープライズ展開では通常、"*~/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*" または "*/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*" になります。

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Jamf を使用して macOS 用に構成する](configure-microsoft-edge-on-mac-jamf.md)
- [Windows 用に構成する](configure-microsoft-edge.md)
- [Intune で Windows 用に構成する](configure-edge-with-intune.md)
