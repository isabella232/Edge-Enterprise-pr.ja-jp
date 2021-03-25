---
title: 最新の Web サイトに対応するための Internet Explorer から Microsoft Edge へのリダイレクト
ms.author: laannade
author: dan-wesley
manager: ratetali
ms.date: 11/16/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 最新の Web サイトに対応するための Internet Explorer から Microsoft Edge へのリダイレクト
ms.openlocfilehash: ffb295b5c844d15fee2b0fa23e78be9cd34ef03f
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447591"
---
# <a name="redirection-from-internet-explorer-to-microsoft-edge-for-compatibility-with-modern-web-sites"></a>最新の Web サイトに対応するための Internet Explorer から Microsoft Edge へのリダイレクト

> [!NOTE]
> この記事は Microsoft Edge 安定バージョン 87 以降に適用されます。

## <a name="overview"></a>概要

最新の Web サイトの多くが、Internet Explorer と互換性のないデザインを採用しています。 Internet Explorer のユーザーが互換性のないパブリック サイトにアクセスすると、そのサイトがブラウザーと互換性のないものであることを通知するメッセージが表示され、手動で別のブラウザーに切り替える必要があります。

Microsoft Edge 安定バージョン 87 から、手動で別のブラウザーに切り替える必要性について変更がありました。

ユーザーが Internet Explorer と互換性のないサイトにアクセスすると、自動的に Microsoft Edge にリダイレクトされます。 この記事では、リダイレクトのユーザー エクスペリエンスや、自動リダイレクトの構成や無効化に使用するグループ ポリシーについて説明します。

> [!NOTE]
> Microsoft は、Internet Explorer との互換性がないことが知られているすべてのサイトの一覧を保持しています。 詳細については、「[互換性のないサイトの一覧の更新を要求する](/microsoft-edge/web-platform/ie-to-microsoft-edge-redirection#request-an-update-to-the-ie-compatibility-list)」を参照してください。

## <a name="redirection-experience"></a>リダイレクト エクスペリエンス

Microsoft Edge にリダイレクトすると、ユーザーには次のスクリーンショットにあるようなダイアログが 1 回のみ表示されます。 このダイアログでは、リダイレクトされた理由を説明し、Internet Explorer から Microsoft Edge に閲覧データや設定をコピーすることに対する同意を求めています。 次の閲覧データがインポートされます: お気に入り、パスワード、検索エンジン、開いているタブ、履歴、設定、Cookie、ホーム ページ。

![データや環境設定をインポートするためのブラウズ通知とプロンプト。](media/edge-learnmore-neededge/neededge-dialog1.png)

[Always bring over my browsing data and preferences from Internet Explorer] (常に Internet Explorer から閲覧データや環境設定を取り込む) のチェック ボックスをオンにして同意していなくても、 **[閲覧を続ける]**  をクリックしてセッションを継続することができます。

最後に、リダイレクトのたびにアドレス バーの下に次のスクリーンショットに示されているような Web サイトの非互換性バナーが表示されます。

![最新のサイトに関する通知と、Microsoft Edge を既定のブラウザーに設定するか、Microsoft Edge を探すように促すプロンプトが表示されます。](media/edge-learnmore-neededge/neededge-banner.png)

Web サイトの非互換性バナー:

- ユーザーに Microsoft Edge への切り替えを促します
- Microsoft Edge を既定のブラウザーとして設定するよう提案します
- Microsoft Edge を探すためのオプションを提供します

サイトが Internet Explorer から Microsoft Edge へとリダイレクトされた場合、サイトの読み込みを開始した Internet Explorer のタブは、それ以前にコンテンツがない場合には閉じられます。 それ以外の場合は、アクティブなタブ ビューが、サイトが Microsoft Edge へとリダイレクトされた理由を説明する Microsoft の [サポート](https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554?ui=en-US&rs=en-US&ad=US)  ページに移動します。

> [!NOTE]
> リダイレクト後は、ユーザーは Internet Explorer の非互換性リストにないサイトを閲覧するために Internet Explorer の使用に戻ることができます。  

## <a name="policies-to-configure-redirection-to-microsoft-edge"></a>Microsoft Edge へのリダイレクトを構成するポリシー

> [!NOTE]
> これらのポリシーは 2020 年 10 月 26 日までに ADMX ファイルの更新プログラムとして利用可能になり、2020 年 11 月 9 日までに Intune で利用可能になります。

Microsoft Edge への自動リダイレクトを有効にするには、3 つのグループ ポリシーを構成する必要があります。 3 つのポリシーは、次のとおりです。

- RedirectSitesFromInternetExplorerPreventBHOInstall
- RedirectSitesFromInternetExplorerRedirectMode
- HideInternetExplorerRedirectUXForIncompatibleSitesEnabled

### <a name="policy-redirectsitesfrominternetexplorerpreventbhoinstall"></a>ポリシー: RedirectSitesFromInternetExplorerPreventBHOInstall

Internet Explorer から Microsoft Edge へのリダイレクトには、"IEtoEdge BHO" という名前の Internet Explorer ブラウザー ヘルパー オブジェクト (BHO) が必要です。 **RedirectSitesFromInternetExplorerPreventBHOInstall** ポリシーは、この BHO がインストールされるかどうかを制御します。  

- このポリシーを有効にすると、リダイレクトに必要な BHO はインストールされず、Internet Explorer 上の特定の Web サイトではユーザーに対して非互換性メッセージが表示され続けます。 すでに BHO がインストールされている場合は、次回の Microsoft Edge 安定チャネルの更新時にアンインストールされます。
- このポリシーを無効にしているか、構成していない場合、BHO はインストールされます。 これは既定の動作です。

BHO の必要性に加えて、**RedirectSitesFromInternetExplorerRedirectMode** への依存関係があり、「互換性のないサイトのサイトリストに基づいてサイトをリダイレクトする」または「未構成」に設定する必要があります。

### <a name="policy-redirectsitesfrominternetexplorerredirectmode"></a>ポリシー: RedirectSitesFromInternetExplorerRedirectMode

 このポリシーは、Microsoft Edge の**既定のブラウザー**設定 "Internet Explorer に Microsoft Edge でサイトを開かせる" に対応しています。 この設定にアクセスするには、*edge://settings/defaultbrowser* の URL にアクセスします。  

- このポリシーを設定していないか、"Sitelist" に設定している場合、Internet Explorer は互換性のないサイトを Microsoft Edge にリダイレクトします。 これは既定の動作です。
- このポリシーを無効にするには、**[有効]** を選択し、[オプション: 互換性のないサイトを Internet Explorer から Microsoft Edgeに自動的にリダイレクトする] の下のドロップダウンで、**[無効]** を選択します。 この状態では、互換性のないサイトは Microsoft Edge にリダイレクトされません。

> [!NOTE]
> 組織で管理されていない個人のデバイスを使用している場合は、**Internet Explorer の互換性**の下に "サイトの読み込みを Internet Explorer モードで許可する" という別の設定が表示されます。
>
>ドメインに参加しているか、モバイル デバイス管理 (MDM) に登録されているデバイスを使用している場合、このオプションは表示されません。
>
> 代わりに、ユーザーに Internet Explorer モードでサイトを読み込ませる場合は、[Internet Explorer モード テストを許可する](./microsoft-edge-policies.md#allow-internet-explorer-mode-testing)ポリシーを構成します。

### <a name="policy-hideinternetexplorerredirectuxforincompatiblesitesenabled"></a>ポリシー: HideInternetExplorerRedirectUXForIncompatibleSitesEnabled

このポリシーでは、互換性のないサイトを Microsoft Edge にリダイレクトするときのユーザー エクスペリエンスを構成します。  

- このポリシーを有効にすると、ユーザーに対する 1 回限りのリダイレクト ダイアログとリダイレクト バナーが表示されなくなります。 ブラウザーのデータやユーザー設定はインポートされません。
- このポリシーを無効にしているか設定していない場合、最初のリダイレクトでリダイレクト ダイアログが表示され、リダイレクトとともに始まるセッションでは永続的なリダイレクト バナーが表示されます。

  > [!NOTE]
  > ユーザーの閲覧データは、ユーザーに対して新しいリダイレクトが発生するたびにインポートされます。 ただし、これは 1 回限りのリダイレクト ダイアログでユーザーがインポートに同意した場合にのみ発生します。

## <a name="disable-redirection-to-microsoft-edge"></a>Microsoft Edge へのリダイレクトを無効にする

Microsoft Edge 安定バージョン 87 にアップデートする前にリダイレクトを無効にする場合は、次の手順を実行します。

1. **RedirectSitesFromInternetExplorerPreventBHOInstall** ポリシーを**有効**に設定します。

Microsoft Edge 安定バージョン 87 にアップデートした後にリダイレクトを無効にする場合は、次の手順を実行します。

1. **RedirectSitesFromInternetExplorerRedirectMode** ポリシーを **[有効]** に設定し、[オプション: 互換性のないサイトを Internet Explorer から Microsoft Edgeに自動的にリダイレクトする] のドロップダウンで、**[無効]** を選択します。 この設定は、ポリシーが有効になるとすぐにリダイレクトを停止します。
2. **RedirectSitesFromInternetExplorerPreventBHOInstall** ポリシーを**有効**に設定します。 これで次回の Microsoft Edge の更新後に BHO がアンインストールされるようになります。

## <a name="see-also"></a>関連項目

- [互換性のないサイトの一覧の更新を要求する](/microsoft-edge/web-platform/ie-to-microsoft-edge-redirection#request-an-update-to-the-ie-compatibility-list)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge ポリシー](./microsoft-edge-policies.md)