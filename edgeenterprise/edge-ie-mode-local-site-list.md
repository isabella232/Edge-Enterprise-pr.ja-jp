---
title: IE モードのローカル サイト一覧
ms.author: shisub
author: AndreaLBarr
manager: srugh
ms.date: 07/20/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: ローカル サイト一覧および IE モードへの簡単アクセスを有効にする方法について説明します。
ms.openlocfilehash: 0c79622a1f96cad83a2436f5e79e69914f4a2c40
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979757"
---
## <a name="local-site-list-for-ie-mode"></a>IE モードのローカル サイト一覧

>[!Note]
> Internet Explorer 11 デスクトップ アプリケーションは廃止され、2022 年 6 月 15 日にサポートが終了します (スコープ内の一覧については、[FAQ を参照してください](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549))。 現在使用しているものと同じ IE11 アプリとサイトを、Internet Explorer モードの Microsoft Edge で開くことができます。 [詳細については、こちらを参照してください](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

この記事では、Internet Explorer モード (IE モード) への簡単アクセスを構成し、組織内でローカル サイト一覧の使用を許可する方法について説明します。

> [!NOTE]
> この記事は Microsoft Edge バージョン 92 以降に適用されます。

### <a name="prerequisites"></a>前提条件

1. Windows 更新プログラム

- Windows 10 バージョン 1909 - [KB5003698](https://support.microsoft.com/topic/june-15-2021-kb5003698-os-build-18363-1645-preview-1ecf117e-1f89-40f9-a0a5-ed5766737620) 以降  

- Windows 10 バージョン 2004; Windows 10 バージョン 20H2 および Windows 10 バージョン 21H1 – [KB5003690](https://support.microsoft.com/topic/june-21-2021-kb5003690-os-builds-19041-1081-19042-1081-and-19043-1081-preview-11a7581f-2a01-47d5-ba12-431709ee2248) 以降

2. Microsoft Edge バージョン 92 (92.0.925.0 以降)

## <a name="overview"></a>概要

IE モードでは、エンタープライズ モード サイト一覧の構成を使用します。 IE モードを使用するサイト一覧でサイトを特定および構成している間、ユーザーが待機したり、スタンドアロン IE11 アプリケーションにフォール バックしたりする必要はなくなりました。

Microsoft Edge バージョン 92 以降、*構成されていない* IE モード サイトに簡単に繰り返しアクセスできます。 ユーザーは IE モードでサイトを再読み込みできます。 これらのサイトをローカル サイト一覧に追加して、組織のサイト一覧が更新される間、30 日間にわたって IE モードで自動的にレンダリングできます。 環境内で [IE11 が無効になっている](/deployedge/edge-ie-disable-ie11)とき、ユーザーが組織のサイト一覧のみに依存することはなくなりました。

このエクスペリエンスは、組織のグループ ポリシーを使用して構成できます。

注: *構成されていない*サイトとは、IE モードが必要なものの、IE モードで開くようエンタープライズ モード サイト一覧で構成されていないサイトのことです。

## <a name="local-site-list-experience"></a>ローカル サイト一覧のエクスペリエンス

ローカル サイト一覧のエクスペリエンスを有効にするため、ユーザーは URL *edge://settings/defaultBrowser* に移動し、**[Internet Explorer モードでサイトの再読み込みを許可する]** を **[許可]** に設定できます。

:::image type="content" source="media/Edge-hybrid-IE-mode/internet-explorer-compatibilitiy.png" alt-text="Internet Explorer の互換性":::

>[!注:]  

>1. *InternetExplorerIntegrationTestingAllowed* ポリシーを使用して IE モード テストを有効にした場合、この設定は表示されますが、*InternetExplorerIntegrationReloadInIEModeAllowed* ポリシーを明示的に有効にしない限り、灰色表示されます。  
>2. **[Internet Explorer モードでサイトの再読み込みを許可する]** が **[既定]** に設定されていると、ユーザーが Internet Explorer 11 を既に使用している場合、IE モードでサイトを再読み込みできる場合があります。  

この設定を有効にすると、ユーザーは **[設定など] (省略記号アイコン ...) > [Internet Explorer モードで再読み込み]** を選択して IE モードでサイトを再読み込みできます。 ユーザーは、タブを右クリックして **[Internet Explorer モードでタブを再読み込み]** を選択するか、リンクを右クリックして **[新しい Internet Explorer モード タブでリンクを開く]** を選択することもできます。

:::image type="content" source="media/Edge-hybrid-IE-mode/reload-in-internet-exploror-mode-screenshot.png" alt-text="Internet Explorer モードで再読み込み":::

**[Internet Explorer モードで再読み込み]** アイコンは、ツールバーにピン留めできます。 ツールバー ボタンを使用すると、ユーザーは IE モードを簡単に開始および終了できます。これは、*edge://settings/appearance* URL から管理できます。

:::image type="content" source="media/Edge-hybrid-IE-mode/reload-in-internet-exploror-mode-icon-screenshot.png" alt-text="[Internet Explorer モードで再読み込み] アイコン":::

>[!Note]
>ユーザーが組織のエンタープライズ モード サイト一覧に既に含まれているサイトにアクセスしている場合、[Internet Explorer モードで再読み込み] (または終了する) のオプションは表示されますが、灰色表示されます。

オプションを選択すると、サイトは IE モードで再読み込みされます。 IE モード インジケーター アイコンはアドレス バーの左側に表示され、ポップアップには、ユーザーが次回ページを Internet Explorer モードで開くための切り替えオプションが表示されます。 これにより、ユーザーがアクセスしている特定のページがローカル サイト一覧に追加され、次の 30 日間は IE モードで自動的に開きます。

:::image type="content" source="media/Edge-hybrid-IE-mode/site-has-been-reloaded-in-ie-mode-screenshot.png" alt-text="このページは Internet Explorer モードで開かれています":::

サイトが IE モードで再読み込みされた後、"ページ内" ナビゲーション (ページ上のリンク、スクリプト、フォームや別の "ページ内" ナビゲーションからのサーバー側リダイレクトなど) は IE モードのままになります。  

IE モードでは、IE モードであることを示すバナーと、IE モードを終了し、(まだピン留めされていない場合は) IE モード アイコンをツールバーにピン留めするためのオプションが表示されます。

:::image type="content" source="media/Edge-hybrid-IE-mode/ie-mode-banner-screenshot.png" alt-text="IE モード バナー":::

ユーザーは、バナーの [終了] ボタン、ピン留めされた IE モード アイコン、または **[設定など] (省略記号アイコン ...) > [Internet Explorer モードを終了]** を使用して、IE モードを終了することを選択できます。それ以外の場合は、"ページ内" にないナビゲーション (アドレス バー、[戻る] ボタン、お気に入りのリンクの使用など) が発生すると、Microsoft Edge が自動的に IE モードを終了します。

エントリは、既定の期間である 30 日間、ローカル サイト一覧に残ります。 組織の従来のサイトをエンタープライズ モード サイト一覧で構成することをお勧めします。 ローカル サイト一覧を使用すると、組織のサイト一覧の更新中にユーザーが中断することなくワークフローを続行できます。 31 日目に、ユーザーがサイトに移動すると、そのサイトが IE モードで読み込まれなくなることを説明するバナーが表示されます。 ユーザーが希望する場合、サイトをローカル サイト一覧に再度追加できます。

:::image type="content" source="media/Edge-hybrid-IE-mode/page-will-no-longer-load-in-ie-mode-screenshot.png" alt-text="ページは IE モードで読み込まれなくなりました":::

## <a name="policies-to-configure-the-use-of-local-site-lists-for-ie-mode"></a>IE モードでのローカル サイト一覧の使用を構成するためのポリシー

2 つのグループ ポリシーを使用して、Microsoft Edge でのローカル サイト一覧のエクスペリエンスを構成できます。 これらのポリシーは、次のとおりです。

### *<a name="policy-internetexplorerintegrationreloadiniemodeallowed"></a>ポリシー: InternetExplorerIntegrationReloadInIEModeAllowed*

このポリシーは、Microsoft Edge の [Internet Explorer モードでサイトの再読み込みを許可する] の設定に相当します。 この設定にアクセスするには、*edge://settings/defaultbrowser* の URL にアクセスします。

- この設定を有効にした場合、ユーザーは **[設定など] (省略記号アイコン ... > [Internet Explorer モードで再読み込み]** を選択して IE モードでサイトを再読み込みできます。 ユーザーは、タブを右クリックして **[Internet Explorer モードでタブを再読み込み]** を選択するか、リンクを右クリックして **[新しい Internet Explorer モード タブでリンクを開く]** を選択することもできます。
ユーザーは必要に応じて、Microsoft Edge で今後 IE モードを使用するよう設定することができます。 この選択は、既定の期間である 30 日間記憶され、ポリシー *InternetExplorerIntegrationLocalSiteListExpirationDays* を使用して管理できます。

- このポリシーを無効にした場合、ユーザーは構成されていないサイトを IE モードで再読み込みできません。

- このポリシーを構成しない場合は、Internet Explorer 11 の最近の使用状況に応じて、構成されていないサイトを IE モードで再読み込みするオプションがユーザーに表示されます。

このポリシーは [InternetExplorerIntegrationTestingAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) ポリシーの構成方法よりも優先され、後者のポリシーが無効になることに注意してください。

### *<a name="policy-internetexplorerintegrationlocalsitelistexpirationdays"></a>ポリシー: InternetExplorerIntegrationLocalSiteListExpirationDays*

このポリシーを使用して、サイトがユーザーのローカル サイト一覧に残る日数を調整できます。  

- このポリシーを無効にするか、構成しない場合は、既定値である 30 日が使用されます。

- ポリシーを有効にした場合は、サイトをユーザーのローカル サイト一覧に保持する日数として 0 - 90 日の間の値を入力する必要があります。

*InternetExplorerIntegrationReloadInIEModeAllowed* ポリシーを無効にした場合、このポリシーによる影響はありません。

**注:**

ローカル サイト一覧は現在、デバイス間で同期されません。 この改善は現在、バックログに含まれており、利用可能になり次第、お知らせします。

## <a name="see-also"></a>関連項目

Internet Explorer 11 を無効にする - [Internet Explorer 11 を無効にする | Microsoft Docs](/deployedge/edge-ie-disable-ie11)

IE モード ポリシーの構成 - [IE モード ポリシーの構成 | Microsoft Docs](/deployedge/edge-ie-mode-policies)

