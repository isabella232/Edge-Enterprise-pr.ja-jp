---
title: 旧バージョンの Microsoft Edge にアクセスする
ms.author: jtkim
author: dan-wesley
manager: srugh
ms.date: 08/17/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: レガシ バージョンの Microsoft Edge にアクセスする方法について説明します。
ms.openlocfilehash: e4733d020f3a681ded50e5a087fe086d39362201
ms.sourcegitcommit: f7f7eb69d2298b0f9779a9fd28e3c4e297ef2e05
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125519"
---
# Microsoft Edge の新しいバージョンをインストールした後 Microsoft Edge レガシにアクセスする

Microsoft Edge の新しいバージョンをインストールした後 Microsoft Edge レガシにアクセスする方法について説明します。

> [!NOTE]
> この記事は、Microsoft Edge [Stable チャネル](microsoft-edge-channels.md)に適用されます。

ほとんどの組織では Microsoft Edge レガシを新しいバージョンに置き換えることが推奨されますが、ユーザーが両方のバージョンにアクセスする必要がある状況が考えられます。 次に、例を示します。

- Microsoft Edge のいずれかまたは両方のバージョンを使用しているユーザーとやり取りするヘルプデスクとサポートのスタッフ。
- Microsoft Edge のいずれかまたは両方のバージョンを使用している顧客をサポートする開発者。

> [!IMPORTANT]
> 運用環境で Microsoft Edge 従来版を Microsoft Edge の新しいバージョンと同時に実行することは推奨されていません。 この構成は、両方のバージョンのブラウザーのテストが必要な特別なケースでのみ使用してください。
>
> Microsoft Edge 従来版のデスクトップ アプリのサポートは 2021 年 3 月 9 日に終了し、新しい Microsoft Edge に完全に移行します。 つまり、この日以降、Microsoft Edge 従来版にはセキュリティ更新プログラムが送信されなくなります。 この変更は、Microsoft Edge 従来版のデスクトップ アプリで実行されるすべてのエクスペリエンスに適用されます。 [詳しくはこちらをご覧ください](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666)。

## 始める前に
> [!NOTE]
> Windows 10 バージョン 20H2 から、Microsoft Edge 従来版は含まれなくなりました。 Windows 10 のこのバージョンから、並べて表示エクスペリエンスはサポートされていません。

この記事の手順は、最新のセキュリティ更新プログラムで更新されたシステムに適用されます。 Microsoft Edge の新しいバージョンがインストールされると、古いバージョン (Microsoft Edge レガシ) が非表示になります。 既定では、ユーザーが古いバージョンを起動しようとすると常に、新しくインストールされたバージョンの Microsoft Edge にリダイレクトされます。 この記事では、Microsoft Edge をインストールした後も Microsoft Edge レガシを引き続き使用できるようにする方法を説明します。

## クイック スタート: Microsoft Edge Beta チャネルと Microsoft Edge 従来版の同時実行エクスペリエンス

この記事の詳細な手順を実行する前に、ユーザーが Microsoft Edge 従来版と Microsoft Edge [Beta チャネル](microsoft-edge-channels.md)を同時に実行できるようにするために、次の 2 つの手順を実行することを検討してください。

1. Microsoft Edge の Stable チャネルが [Windows Update](https://support.microsoft.com/help/12373/windows-update-faq) で自動的にインストールされないように対策を講じます。

   > [!TIP]
   > [Blocker Toolkit](microsoft-edge-blocker-toolkit.md) を使用すると、Microsoft Edge の自動配布を無効にできます。

2. 新しいバージョンの Microsoft Edge の[Beta チャネル](https://www.microsoft.com/edge/business/download)をインストールします。

   > [!NOTE]
   > レジストリ キー設定の詳細については、「[追加情報](#additional-information)」参照してください。

この同時実行ソリューションは、この記事で説明する詳細な解決方法に比べてシンプルで、管理作業も少なくて済みます。 ただし、このソリューションは、Stable チャネルより Beta チャネルを実行する方が望ましいという意味ではありません。

## Microsoft Edge Stable チャネルと Microsoft Edge 従来版の同時実行エクスペリエンス

次のバージョンの Microsoft Edge の Stable チャネルをシステムレベルでインストールすると、現在のバージョン (Microsoft Edge レガシ) が非表示になります。 Windows で Microsoft Edge の両方のバージョンの同時実行をユーザーに許可する場合は、[**Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する**] グループ ポリシーを [**有効**] に設定すると、このエクスペリエンスを有効にできます。

このグループポリシーについては、[こちら](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs)をご覧ください。

### ブラウザーの同時実行エクスペリエンスをセットアップするには、次の手順を実行します。

1. [Microsoft Edge For Business](https://www.microsoft.com/edge/business/download) からポリシー定義をインストールします。

   - 使用する CHANNEL/BUILD および PLATFORM を選択し、[GET POLICY FILES] (ポリシー ファイルの取得) をクリックします。
   - 圧縮ファイルを展開します。
   - msedge.admx と msedgeupdate.admx を `C:\Windows\PolicyDefinitions` ディレクトリにコピーします。
   - (適切な言語またはロケールのディレクトリから) msedge.adml と msedgeupdate.adml を `C:\Windows\PolicyDefinitions\[APPROPRIATE LANGUAGE/LOCALE]` ディレクトリにコピーします。

2. グループ ポリシー エディター (gpedit.msc) を開きます。
3. **[コンピューターの構成]** の *[管理用テンプレート] > [Microsoft Edge Update] > [アプリケーション]* に移動します。

    > [!NOTE]
    > *Microsoft Edge Update* フォルダーが表示されない場合は、手順 1 が正常に完了していることを確認してください。

4. **[アプリケーション]** で、[Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する] をダブルクリックします。 次の手順に進む前に、「[ベスト プラクティス ガイダンス](#best-practice-guidance)」をご覧ください。

    > [!NOTE]
    > 既定では、このグループ ポリシーは [未構成] に設定されています。これにより、新しいバージョンの Microsoft Edge がインストールされている場合に Microsoft Edge レガシが非表示になります。

5. **[有効]** を選択し、**[OK]** をクリックします。  

このポリシーを設定すると、次のレジストリ キーが "00000001" に設定されます。

- キー:  `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate`
- キーの値:  `Allowsxs`
- 値の種類:  `'REG_DWORD'`

#### ベスト プラクティス ガイダンス

最良のエクスペリエンスを得るには、新しいバージョンの Microsoft Edge をユーザーのデバイスに展開する前に、**[Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する]** を有効にする必要があります。

Microsoft Edge が展開された後でグループ ポリシーが有効になると、次のような影響があり、対処が必要になります。

1. **[Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する]** は、新しいバージョンの Microsoft Edge 用のインストーラーが再度実行されるまで有効になりません。

   > [!NOTE]
   > インストーラーは、直接実行することも、新しいバージョンの Microsoft Edge 更新時に自動で実行することもできます。

2. 新しいバージョンの Microsoft Edge が展開されたときにピン留めが移行されるため、Microsoft Edge レガシはスタート画面またはタスク バーに再度ピン留めする必要があります。
3. Microsoft Edge レガシ用にスタート画面またはタスク バーにピン留めされたサイトは、新しいバージョンの Microsoft Edge に移行されます。

## 追加情報

システムが完全に更新され、次のバージョンの Microsoft Edge の Stable チャネルがインストールされた後、次のレジストリ キーと値が設定されます。

- キー:  `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}`
- キーの値:  `BrowserReplacement`

  > [!IMPORTANT]
  > このキーは、Microsoft Edge Stable チャネルが更新されるたびに上書きされます。 ベスト プラクティスとしては、ユーザーが両方のバージョンの Microsoft Edge にアクセスできるように、このキーを削除しないことをお勧めします。

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge をサポートする Windows 更新プログラム](microsoft-edge-sysupdate-windows-updates.md)
