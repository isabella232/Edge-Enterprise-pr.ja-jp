---
title: Jamf を使用して macOS の Microsoft Edge を構成する
ms.author: brianalt
author: dan-wesley
manager: laurawi
ms.date: 6/29/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Jamf を使用して Mac デバイスの Microsoft Edge ポリシー設定を構成する
ms.openlocfilehash: 8556a5b1d0fc01feb67fc86cb016a9ed47061b55
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641633"
---
# <a name="configure-microsoft-edge-policy-settings-on-macos-with-jamf"></a>Jamf を使用して macOS の Microsoft Edge ポリシー設定を構成する

この記事では、Jamf Pro 10.19 の Microsoft Edge ポリシー マニフェスト ファイルを使用して、macOS のポリシー設定を構成する方法について説明します。

macOS の Microsoft Edge ポリシー設定は、プロパティ リスト (.plist) ファイルを使用して構成することもできます。 詳細については、「[.plist を使用して macOS 用に構成する](configure-microsoft-edge-on-mac.md)」を参照してください


## <a name="prerequisites"></a>前提条件

次のソフトウェアが必要です。

- Microsoft Edge Stable チャネル 81
- ポリシー テンプレート ファイル (バージョン 81.0.416.3)
- Jamf Pro (バージョン 10.19)

## <a name="about-the-jamf-pro-application--custom-settings-menu"></a>Jamf Pro の [Application & Custom Settings] メニューについて

Jamf Pro 10.18 以前では、Office 365 の管理には手動による .plist の作成が必要でした。 この作業は、強力な技術的バックグラウンドが必要になる、時間のかかるワークフローでした。 Jamf Pro 10.18 では、構成プロセスを合理化することで、このような障壁が排除されました。 ただし、この新しいユーザー インターフェイスは、IT 管理者のみが使用できるものであり、Jamf が指定した特定のアプリケーションと優先ドメインに対応していました。

Jamf Pro 10.19 では、ユーザーが「カスタム スキーマ」として JSON マニフェストをアップロードすることで任意の優先ドメインをターゲットに設定できます。このマニフェストから、グラフィカル ユーザー インターフェイスが生成されます。 このカスタム スキーマは、JSON スキーマ仕様に従って作成します。

詳細については、Jamf Pro 管理者ガイドの「[コンピューター構成プロファイル](https://jamf.it/computer-configuration-profiles)」を参照してください。

## <a name="get-the-policy-manifest-for-a-specific-version-of-microsoft-edge"></a>Microsoft Edge の特定のバージョン用のポリシー マニフェストを取得する

ポリシー マニフェストを取得するには:

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)に移動します。
- [チャネル/バージョン] ドロップダウン リストで、**バージョン 81 以降の任意のチャネルを選択します。**_。
- [ビルド] ドロップダウン リストで、_*81 以降の任意のビルドを選択します。**_。
- [ポリシー ファイルの取得] をクリックして、ポリシー テンプレートのバンドルをダウンロードします。

  > [!NOTE]
  > 現在、このポリシー テンプレートのバンドルは、CAB ファイルとして署名されています。 このファイルを macOS で開くには、サード パーティ製ツール (The Unarchiver など) を使用する必要があります。

CAB ファイルを展開してから、ZIP ファイルを展開して、最上位ディレクトリの "mac" に移動します。 このディレクトリに、"policy_manifest.json" という名前のマニフェスト ファイルがあります。

このマニフェスト ファイルは、ビルド 81.0.416.3 以降のポリシー バンドルごとに発行されます。 開発用チャネルのポリシーをテストする場合は、それぞれの開発リリースに関連付けられたマニフェストを取得して、そのマニフェストを Jamf Pro でテストしてください。  

## <a name="use-the-policy-manifest-in-jamf-pro"></a>Jamf Pro でポリシー マニフェストを使用する

次の手順を使用して、Jamf Pro にポリシー マニフェストをアップロードし、macOS 用のポリシー プロファイルを作成します。

1. Jamf にサインインします。
2. [_*Computer**] タブを選択します。
3. **[Content Management]** (コンテンツ管理) にある **[Configuration Profiles]** (構成プロファイル) をクリックします。
4. **[Configuration Profiles]** ページで、**[+ New]** (+ 新規) をクリックします。

   ![Jamf に新しいプロファイルを追加する](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles.png)

5. **[New macOS Configuration Profile]** (新規 macOS 構成プロファイル) > **[Options]** (オプション) で、**[Application & Custom Settings]** (アプリケーションとカスタムの設定) を選択します。
6. **[Application & Custom Settings]** ポップアップ ウィンドウで、**[Configure]** (構成) をクリックします。

   ![アプリケーションとカスタムの設定を構成する](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom.png)

7. **[Application & Custom Settings]** セクションで、次のスクリーンショットに示した値を設定します。

   ![プロファイル ソースとカスタム スキーマ](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-schema.png)

   - **[Creation Method]** (作成方法) には、**[Configure settings]** (設定を構成する) を選択します。
   - **[Source]** (ソース) には、**[Custom Schema]** (カスタム スキーマ) を選択します。
   - **[Preference Domain]** (優先ドメイン) には、対象のドメイン名を指定します。 この例では、そのドメインとして「*com.microsoft.Edge*」を使用します。
   - **[Custom Schema]** (カスタム スキーマ) には、"policy_manifest.json" マニフェスト ファイルの内容を貼り付けます。
   - **[保存]** をクリックします。

8. プロファイルを保存すると、Jamf により、次のスクリーン ショットに示す **[General]** (全般) セクションが表示されます。

   ![[General] セクションの構成](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-general-setting.png)

   - プロファイルの **[Name]** (名前) と **[Description]** (説明) を入力します。
   - **[Category]** (カテゴリ) の既定の設定 **[None]** (なし) は、そのままにします。
   - **[Distribution Method]** (配布方法) のオプションは、**[Install Automatically]** (自動的にインストールする) または **[Make Available in Self Service]** (セルフサービスで利用可能にする) にします。
   - **[Level]** (レベル) のオプションは、**[User Level]** (ユーザー レベル) または **[Computer Level]** (コンピューター レベル) にします。
   - **[保存]** をクリックします。

9. [General] セクションを保存すると、Jamf により、この記事の例に応じて設定された "Microsoft Edge Beta Channel" 構成プロファイルが示されます。 次のスクリーン ショットでは、**[Edit]** (編集) をクリックすることでプロファイルの作業を続行できます。作業が完了している場合は、**[Done]** (完了) をクリックします。

   ![オプションを設定した新しい構成プロファイル](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel.png)

   > [!NOTE]
   > このプロファイルは保存後に、別の Jamf セッションで編集できます。 たとえば、[Distribution Method] を [Make Available in Self Service] に変更できます。

   Microsoft Edge Stable チャネルの追加編集や削除を実行する場合は、次のスクリーン ショットに示す [Configuration Profiles] でプロファイル名を選択します。

   ![[Configuration Profiles] リスト](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel-done.png)

新しい構成プロファイルの作成後には、そのプロファイルの **[Scope]** (スコープ) も構成する必要があります。

### <a name="to-configure-the-scope"></a>スコープを構成するには

1. **[Targets]** (ターゲット) で、次の最小限の設定を指定します。

   - TARGET COMPUTERS (ターゲット コンピューター)。 このオプションは、[Specific Computers] (特定のコンピューター) または [All Computers] (すべてのコンピューター) にします。
   - TARGET USERS (ターゲット ユーザー)。 このオプションは、[Specific Users] (特定のユーザー) または [All Users] (すべてのユーザー) にします。
   - **[保存]** をクリックします。
2. **[Limitations]** (制限) は、既定の設定 [None] のままにします。 [**キャンセル**] をクリックします。
3. **[Exclusions]** (除外) は、既定の設定 [None] のままにします。 [**キャンセル**] をクリックします。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Intune で macOS 用に構成する](configure-microsoft-edge-on-mac.md)
- [Windows 用に構成する](configure-microsoft-edge.md)
- [Intune で Windows 用に構成する](configure-edge-with-intune.md)
