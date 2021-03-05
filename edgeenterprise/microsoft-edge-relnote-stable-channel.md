---
title: Stable チャネルに関する Microsoft Edge リリース ノート
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 03/01/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Stable チャネルに関する Microsoft Edge リリース ノート
ms.openlocfilehash: 3eab05fcb88bcde38de8eb02b50796fcdda12866
ms.sourcegitcommit: f14286edec59ee9183bdf38c15fc890881efd64f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385005"
---
# <a name="release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge Stable チャネルのリリース ノート

これらのリリース ノートでは、Microsoft Edge Stable チャネルに含まれている新機能とセキュリティ以外の更新プログラムに関する情報を提供します。

- すべてのセキュリティの更新プログラムは、[ここ](microsoft-edge-relnotes-security.md)に記載されています。
- Microsoft Edge 安定チャネルのアーカイブされたリリース ノートは、[こちら](microsoft-edge-relnote-archive-stable-channel.md)にあります。

 Microsoft Edge チャネルを理解するには、「[Microsoft Edge チャネルの概要](microsoft-edge-channels.md)」を参照してください。

> [!NOTE]
> 安定チャネルの場合、更新は 1 日以上かけて段階的に公開されます。 詳細については、「[Microsoft Edge 更新プログラムの段階的なロールアウト](microsoft-edge-update-progressive-rollout.md)」を参照してください。


## <a name="version-88070581-february-25"></a>バージョン 88.0.705.81: 2 月 25 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-88070574-february-17"></a>バージョン 88.0.705.74: 2 月 17 日

セキュリティの更新プログラムは、[こちら](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#February-17-2021)に記載されています。

## <a name="version-88070568-february-11"></a>バージョン 88.0.705.68: 2 月 11 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-88070563-february-5"></a>バージョン 88.0.705.63: 2 月 5 日

セキュリティの更新プログラムは、[こちら](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#February-5-2021)に記載されています。 この更新プログラムには、[CVE-2021-21148](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21148) が含まれています。これについては、Chromium チームにより実際に感染報告がある悪用が報告されています。

## <a name="version-88070562-february-4"></a>バージョン 88.0.705.62: 2 月 4 日

セキュリティの更新プログラムは、[こちら](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#February-4-2021)に記載されています。

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-88070556-january-28"></a>バージョン 88.0.705.56: 1 月 28 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-88070553-january-26"></a>バージョン 88.0.705.53: 1 月 26 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-88070550-january-21"></a>バージョン 88.0.705.50: 1 月 21 日

セキュリティの更新プログラムは、[こちら](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#january-21-2021)に記載されています。

<!--- begin major 88  --->
### <a name="feature-updates"></a>機能の更新プログラム

- **非推奨:**

  - FTP プロトコルのサポートを廃止します。 従来の FTP プロトコルのサポートは Microsoft Edge から削除されました。 FTP リンクに移動しようとすると、ブラウザーは、FTP リンクを処理する外部アプリケーションを開く操作をオペレーティング システムに指示します。 または、IT 管理者は、FTP プロトコルに依存するサイトで IE モードを使用する Microsoft Edge を構成できます。
  - Adobe Flash のサポートは削除されます。 Microsoft Edge Beta バージョン 88 から、Adobe Flash の機能とサポートは削除されます。 詳細: [Adobe Flash Player のサポート終了に関する更新プログラム - Microsoft Edge ブログ (windows.com)](https://blogs.windows.com/msedgedev/2020/09/04/update-adobe-flash-end-support/)

- **認証:**

  - シングル サインオン (SSO) は、ダウンレベル Windows の Azure Active Directory (Azure AD) アカウントと Microsoft アカウント (MSA) で利用できます。 ダウンレベルの Microsoft Windows (7、8.1) で Microsoft Edge にサインインしたユーザーは、Work アカウントと Microsoft アカウント (bing.com、office.com、msn.com、outlook.com など) でシングル サインオンを許可するように構成された Web サイトに自動的にサインインします。<br>注: この機能を利用するには、ユーザーが Microsoft Edge 88 より前のバージョンで Microsoft Edge にサインインした場合、サインアウトしてからサインインしなおす必要がある場合があります。
  
  - シングル サインオン (SSO) は、Azure AD 以外の Microsoft Edge プロファイルのシステム上で任意の Windows Azure Active Directory (Azure AD) アカウントを使用することによってサイトで使用できます。 この機能は、職場または学校アカウントでサインインしていない、ゲストやプライベートではないプロファイルに対して有効にできます。また、そのプロファイルのオペレーティング システムでサインインしている任意の職場または学校アカウントを使用できます。 この機能は、**[設定]** > **[プロファイル]** > **[プロファイルの基本設定]** > **[このプロファイルを使用して、職場または学校のサイトにシングル サインオンを許可する]** で構成できます。
  
    > [!NOTE]
    > 「Microsoft Edge プロファイルを使用しているすべての Windows アカウントのシングル サインオン (SSO)」は、1 月 21 日のリリース ノートの更新です。

- **セッションを終了するキオスク モード オプション**。 [セッションの終了] ボタンは、キオスク モードのパブリック ブラウズ エクスペリエンスで利用できます。 この機能により、Microsoft Edge を閉じたときにブラウザーのデータと設定が削除されます。 キオスク モード機能とロードマップの詳細については 、「[Microsoft Edge キオスク モードを構成する](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode)」を参照してください。

- **セキュリティとプライバシー:**

  - ユーザーのパスワードのオンラインでの漏洩が見つかると、警告が生成されます。 ユーザーのパスワードは、侵害された資格情報のリポジトリと照合され、一致するものが見つかるとユーザーに警告を通知します。 セキュリティとプライバシーを確保するために、ユーザーのパスワードは漏洩した資格情報のデータベースと照合するときにハッシュ化され、暗号化されます。
  - 混在コンテンツを自動的にアップグレードします。 HTTPS 経由で配信されるセキュリティで保護されたページには、セキュリティ保護されていない HTTP 経由で提供される参照イメージが含まれる場合があります。 Microsoft Edge 88 のプライバシーとセキュリティを向上させるために、これらの画像は HTTPS 経由で取得されます。 HTTPS 経由で画像を利用できない場合、画像は読み込まれません。
  - サイトの権限をサイト別および最近のアクティビティ別に表示します。 Microsoft Edge 88 から、ユーザーはサイトのアクセス許可を簡単に管理できます。 アクセス許可の種類ではなく、Web サイト別にアクセス許可を表示できます。 さらに、サイトのアクセス許可に対する最近の変更すべてがユーザーに表示される最近のアクティビティ セクションが追加されました。
  - ブラウザーの Cookie の制御が向上しました。 Microsoft Edge 88 から、ユーザーはファースト パーティの Cookie に影響を及ぼさずにサード パーティの Cookie を削除できます。 また、ユーザーは、ファースト パーティまたはサード パーティによって Cookie をフィルター処理し、名前、Cookie の数、および保存および最終変更されたデータの量で並べ替えすることもできます。

- **パスワード:**

  - パスワード ジェネレーター。 Microsoft Edge には、新しいアカウントにサインアップするとき、または既存のパスワードを変更するときに使用できる強力なパスワード ジェネレーターが組み込まれています。 パスワード フィールドでブラウザーが推奨するパスワードのドロップダウンを探すだけで、選択すると自動的にブラウザーに保存され、後で簡単に使用できるようにデバイス間で同期されます。
  - パスワード モニター。 ブラウザーに保存されたパスワードのいずれかが、漏洩された一覧のリストに表示されているパスワードと一致すると、Microsoft Edge から通知され、パスワードを更新するように求められます。 パスワード モニターは、ユーザーに代わって一致をスキャンし、既定でオンになっています。
  - パスワードの編集。 Microsoft Edge の設定で、保存したパスワードを直接編集できます。 Microsoft Edge の外部でパスワードが更新された場合はいつでも、[設定] で保存されたエントリを編集することで、保存された古いパスワードを新しいパスワードに簡単に置き換えることができます。 

- **起動ブーストを使用して Microsoft Edge の起動速度を向上します**。 Microsoft Edge の起動速度を向上させるために、スタートアップ ブーストという名前の機能を開発しました。 起動ブーストにより、Microsoft Edge をバックグラウンドで実行することで、Microsoft Edge の起動速度が向上します。 注: この機能は、実験を有効にしたユーザーのランダムに選択されたグループに限定されます。 これらのユーザーは、機能チームにフィードバックを提供しています。

- **生産性:**

  - 垂直方向のタブを使用して生産性とマルチタスクを改善します。 水平方向のタブの数が増えるにつれて、サイト タイトルが切れ始め、タブが縮小されるごとにタブ コントロールが失われます。 これにより、タブの検索、切り替え、管理に費やす時間が長く、タスクに対する時間が減り、ユーザー ワークフローが中断されます。 垂直方向のタブを使用すると、ユーザーはタブを横に移動できます。縦方向に配置されたアイコンと長いサイト タイトルを使用すると、開くタブをすばやくスキャン、識別、切り替えやすくなります。
  - 生年月日フィールドの日付を自動入力します。 Microsoft Edge では、住所、名前、電話番号などのユーザー データを自動入力することで、フォームに入力し、オンラインでアカウントを作成する際に時間と労力を節約できます。Microsoft Edge では、ユーザーが保存して自動入力できる生年月日フィールドがサポートされます。 ユーザーは、プロファイル設定でいつでもこの情報を表示、編集、削除できます。
  - 履歴で最近閉じた機能が改善されました。 最近閉じた場合、前のセッションではなく、過去の閲覧セッションから最後の 25 のタブとウィンドウが保持されます。 ユーザーは、新しい履歴エクスペリエンスで最近閉じたタブを選択して、開いていたすべてのタブを表示できます。
  - 既定で有効になっている "1 日の一覧" 機能。 Microsoft Edge バージョン 88 から、情報ワーカーは新しいタブ ページ (NTP) でインテリジェントな生産性機能を利用できます。 Microsoft Edge 87 ユーザーも、Microsoft Edge 88 のリリース後 2 週間以内にこれらの機能を利用できます。 M365 Graph を利用して、ユーザーが自分の仕事用または学校アカウントでサインインし、個人設定をした関連するコンテンツを提供します。 ユーザーは、"1 日の一覧" モジュールをすばやくスキャンして、会議や最近の作業を簡単に追跡し、使用するアプリケーションをすばやく起動できます。

- **履歴とオープンタブの同期**。履歴とオープン タブの同期が、ユーザーが利用できるようになりました。 これらの機能を有効にすると、ユーザーは閲覧履歴を作成することにより、前回閲覧を終了した場所を開き、すべての同期デバイスでタブを開くことができるようになります。 同期ポリシーとブラウザー履歴ポリシーを更新しました。Microsoft Edge を使用することで、ユーザーはどのデバイスからでも接続して生産性を高めることができます。 [詳細情報](https://blogs.windows.com/windowsexperience/2021/01/21/this-year-lets-resolve-to-make-the-most-of-our-time-online-and-better-protect-ourselves-from-online-threats/)。

- **PDF:**

  - ブック ビューでの PDF ドキュメントの表示 (2 ページ)。 Microsoft Edge バージョン 88 から、ユーザーは PDF ドキュメントを 1 ページまたは 2 ページのブック ビューで表示できます。 ビューを変更するには、ツール バーの [ **ページ ビュー]** ボタンをクリックします。
  - PDF ファイルのアンカー付きテキスト ノートのサポート。 Microsoft Edge バージョン 87 から、ユーザーは PDF ファイル内の任意のテキストに入力したテキスト ノートを追加できます。

- **フォント:**

  - ブラウザー アイコンは Fluent デザイン システムに更新されます。 ブラウザーで Fluent Design を引き続き使用する作業の一環として、アイコンを新しい Microsoft アイコン システムに合わせて調整する変更を行いました。 これらの変更は、タブ、アドレス バー、さまざまなメニューにあるナビゲーション アイコンや移動方法のアイコンなど、タッチの多いユーザー インターフェイスの多くに影響します。
  - フォントのレンダリングが改善されました。 テキストのレンダリングが改善され、わかりやすくなり、ぼやけも少なくなりました。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

18 個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://www.microsoft.com/edge/business/download)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [BasicAuthOverHttpEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#basicauthoverhttpenabled) - HTTP の基本認証を許可します。
- [BlockExternalExtensions](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#blockexternalextensions) - 外部拡張機能のインストールをブロックします。
- [InternetExplorerIntegrationLocalFileAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalfileallowed) - Internet Explorer モードでローカル ファイルを起動できるようにします。
- [InternetExplorerIntegrationLocalFileExtensionAllowList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalfileextensionallowlist) - Internet Explorer モードのローカル ファイルのファイル拡張子許可リストを開きます。
- [InternetExplorerIntegrationLocalFileShowContextMenu](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalfileshowcontextmenu) - Internet Explorer モードでリンクを開くためのコンテキスト メニューを表示します。
- [IntranetRedirectBehavior](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#intranetredirectbehavior) - イントラネット リダイレクトの動作。
- [PrinterTypeDenyList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#printertypedenylist) - 拒否リストでプリンターの種類を無効にします。
- [ShowMicrosoftRewards](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showmicrosoftrewards) - Microsoft Rewards エクスペリエンスを表示します。
- [SleepingTabsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sleepingtabsenabled) - スリーピング タブを構成します。
- [SleepingTabsTimeout](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sleepingtabstimeout) - スリーピング タブのバックグラウンド タブの非アクティブタイムアウトを設定します。
- [SleepingTabsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sleepingtabsblockedforurls) - 特定のサイトでタブのスリープをブロックします。
- [StartupBoostEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#startupboostenabled) - スタートアップ ブーストを有効にします。
- [TargetBlankImpliesNoOpener](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#targetblankimpliesnoopener) - _blank を対象とするリンクに window.opener を設定しません。
- [UpdatePolicyOverride](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#updatepolicyoverride) - Microsoft Edge で利用できる更新プログラムを Microsoft Edge Update でどのように処理するかを指定します。
- [VerticalTabsAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#verticaltabsallowed) - ブラウザーの横にあるタブの垂直方向のレイアウトの可用性を構成します。
- [WebRtcAllowLegacyTLSProtocols](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webrtcallowlegacytlsprotocols) - WebRTC で従来の TLS/DTLS ダウングレードを許可します。
- [WebWidgetAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webwidgetallowed) - Web ウィジェットを有効にします。
- [WebWidgetIsEnabledOnStartup](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webwidgetisenabledonstartup) - Windows 起動時に Web ウィジェットを許可します。

#### <a name="deprecated-policies"></a>廃止されたポリシー

- [ProactiveAuthEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proactiveauthenabled) - プロアクティブ認証を有効にします。
- [ProxyBypassList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxybypasslist) - プロキシ バイパス ルールを構成します。
- [ProxyMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxymode) - プロキシ サーバー設定を構成します。
- [ProxyPacUrl](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxypacurl) - プロキシの .pac ファイルの URL を設定します。
- [ProxyServer](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxyserver) - プロキシ サーバーのアドレスまたは URL を構成します。
- [WebDriverOverridesIncompatiblePolicies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webdriveroverridesincompatiblepolicies) - WebDriver が互換性のないポリシーを上書きすることを許可します。

### <a name="obsoleted-policies"></a>非推奨ポリシー

- [AllowPopupsDuringPageUnload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#allowpopupsduringpageunload) - ページのアンロード中にポップアップを表示できます。
- [DefaultPluginsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultpluginssetting) - 既定の Adobe Flash 設定です。
- [PluginsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsallowedforurls) - 特定のサイトで Adobe Flash プラグインを許可します。
- [PluginsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsblockedforurls) - 特定のサイトで Adobe Flash プラグインをブロックします。
- [RunAllFlashInAllowMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#runallflashinallowmode) - Adobe Flash コンテンツ設定をすべてのコンテンツに拡張します。
<!--- end major 88  --->
## <a name="version-87066475-january-7"></a>バージョン 87.0.664.75: 1 月 7 日

セキュリティの更新プログラムは、[こちら](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#january-7-2021)に記載されています。

## <a name="version-87066466-december-17"></a>バージョン 87.0.664.66: 12 月 17 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-87066460-december-10"></a>バージョン 87.0.664.60: 12 月 10 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-87066457-december-7"></a>バージョン 87.0.664.57: 12 月 7 日

さまざまなバグとパフォーマンスの問題を修正しました。 セキュリティの更新プログラムは、[ここ](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#december-7-2020)に記載されています。

## <a name="version-87066455-december-3"></a>バージョン 87.0.664.55: 12 月 3 日

さまざまなバグとパフォーマンスの問題を修正しました。 このリリースでは、次の機能が更新されました。

- **ショッピングは既定で有効になっています**。 Microsoft Edge バージョン 87 から、エンタープライズ ユーザーは Microsoft Edge でのショッピングを利用できます。 ショッピング機能を備えた Microsoft Edge は、オンラインでショッピングしながらクーポンやお得な価格を見つけるのに役立ちます。 (クーポンの機能は、Stable バージョン 87.0.664.41 とともにリリースされました。) この更新プログラムで、価格比較エクスペリエンスを利用できるようになりました。 この機能は、[EdgeShoppingAssistantEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgeshoppingassistantenabled) ポリシーを使って構成できます。 Microsoft ショッピングについては、[ブログ](https://blogs.windows.com/windowsexperience/2020/11/19/finish-up-that-holiday-shopping-with-new-features-from-microsoft-edge-and-bing/)および[詳細情報](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#shopping)をご覧ください。

## <a name="version-87066452-november-30"></a>バージョン 87.0.664.52: 11 月 30 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-87066447-november-23"></a>バージョン 87.0.664.47: 11 月 23 日

さまざまなバグとパフォーマンスの問題を修正しました。

<!-- begin major 87 --->
## <a name="version-87066441-november-19"></a>バージョン 87.0.664.41: 11 月 19 日

セキュリティ更新プログラムは、[こちら](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-19-2020)に記載されています。

### <a name="feature-updates"></a>機能の更新プログラム

- **互換性のないサイトを Internet Explorer から Microsoft Edgeにリダイレクトします**。 Microsoft Edge 87 Stable の更新以降、Internet Explorer で互換性のないメッセージを表示する公開 Web サイトは自動的に Microsoft Edge にリダイレクトされます。 詳細とこのエクスペリエンスの構成については、「[互換性のないサイトのリダイレクト](https://docs.microsoft.com/deployedge/edge-learnmore-neededge)」を参照してください。

- **キオスク モードのプライバシー機能を有効にします**。 Microsoft Edge バージョン 87 以降では、ユーザー データのプライバシーに関して企業に役立つキオスク モードの機能が有効になります。 これらの機能により、終了時にユーザーデータをクリアしたり、ダウンロードしたファイルを削除したり、一定のアイドル時間が経過した後に、構成されていたスタート操作をリセットしたりできます。 [Microsoft Edge キオスク モードを構成する方法](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode)の詳細情報

- **既定で有効になっているショッピング機能**。 Microsoft Edge バージョン 87 以降では、エンタープライズ ユーザーは、Edge でのショッピングを利用することもできます。 ショッピング機能を備えた Microsoft Edge は、オンラインでショッピングしながらクーポンやお得な価格を見つけるのに役立ちます。 この更新プログラムではクーポン エクスペリエンスが利用可能であり、価格比較は Microsoft Edge 87 の今後の更新プログラムでリリースされます。 この機能は、[EdgeShoppingAssistantEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#edgeshoppingassistantenabled) ポリシーを使用して構成できます。 Microsoft ショッピングについては、[ブログ](https://blogs.windows.com/windowsexperience/2020/11/19/finish-up-that-holiday-shopping-with-new-features-from-microsoft-edge-and-bing/)および[詳細情報](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#shopping)をご覧ください。

- **ClickOnce の展開が既定で有効になっています**。 Microsoft Edge 87 では、ClickOnce が既定で有効になっています。これにより、企業がソフトウェアを展開する際の障壁を減らし、Microsoft Edge のレガシブラウザーの動作に合わせることができます。 Microsoft Edge 87 以降、ClickOnceEnabled policyが"未構成"の 状態の場合は、新しい既定の「有効化が ClickOnceの状態」（以前の規定が無効だった状態と異なり）に反映されます。

- **エンタープライズ新しいタブページ (NTP)は、カスタマイズ可能な仕事関連のフィードコンテンツと生産性を結びつけます**。 エンタープライズ NTP は、職場または学校アカウントでサインインしているユーザーに対して提供される Office 365 生産性向上ページだけでなく、カスタマイズされた、仕事関連の企業や業界のコンテンツを1ページにまとめて提供いたします。 ユーザーは、使い慣れた Office 365 のコンテンツと、Bing で提供されている一般法人向け Microsoft Search を目にすることでしょう。 さらに、組織で利用可能なコンテンツとモジュールから最も関連性の高いコンテンツを選択することで、「マイ フィード」を簡単にカスタマイズできます。 IT 管​​理者は、Microsoft 365 管理センターにアクセスして、Microsoft Edge の新しいタブ ページで選択した業界を含む、組織のニュース フィード設定を制御できます。 [詳細情報](https://blogs.windows.com/msedgedev/2020/10/29/enterprise-new-tab-page-my-feed/)

- **プライバシーとセキュリティ**

  - ポリシー構成のサイトの TLS トークンバインドをサポートしています。 TLS トークンのバインドは、トークンの盗用攻撃を防ぐために、最初に設定されたデバイス以外のデバイスから cookie が再利用されないようにします。 TLS トークンバインドを使用するには、 [AllowTokenBindingForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowtokenbindingforurls) ポリシーを設定する必要があります。また、リストに記載されているサイトがこの機能をサポートしている必要があります。

- **PDF ファイルで強調表示のキーボードサポート**。 ユーザーは、キーボードのキーを使用して、PDF のテキストを強調表示できます。

- **印刷**

  - 両面印刷時にどのように紙を綴じるか選択します。 ユーザーが両面印刷するときに、用紙の長辺綴じか短辺綴じにするかを選択できます。
  - エンタープライズの印刷ラスター化モードを選択します。 Windows のポストスクリプトプリンター以外に Microsoft Edge をプリントする方法を制御します。 PostScript に対応していないプリンターの印刷ジョブが正しく印刷されるようにラスター化する必要がある場合があります。 印刷オプションには "Full (フル)" と "Fast (高速)"が表示されます。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

10個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://www.microsoft.com/edge/business/download)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [ConfigureFriendlyURLFormat](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configurefriendlyurlformat) -Microsoft Edge からコピーした URLの既定の貼り付け書式を構成し、他の形式をユーザーが利用できるようにするかどうかを決定します。
- [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#edgeshoppingassistantenabled) -Microsoft Edge でのショッピングが有効になります。
- [HideInternetExplorerRedirectUXForIncompatibleSitesEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#hideinternetexplorerredirectuxforincompatiblesitesenabled) -Microsoft Edge のワンタイム リダイレクト ダイアログとバナーを非表示にします。
- [KioskAddressBarEditingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) -キオスクモードのパブリックブラウザーのエクスペリエンスを編集するアドレスバーを構成します。
- [KioskDeleteDownloadsOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) -Microsoft Edge が終了したときに、キオスク セッションの一部としてダウンロードされたファイルを削除します。
- [PasswordRevealEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordrevealenabled) -パスワード表示ボタンを有効にします。
- [RedirectSitesFromInternetExplorerPreventBHOInstall](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerpreventbhoinstall) -Internet Explorer から Microsoft Edge に互換性のないサイトをリダイレクトするためにブラウザー ヘルパー オブジェクト (BHO) をインストールできないようにします。
- [RedirectSitesFromInternetExplorerRedirectMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerredirectmode) -Internet Explorer から Microsoft Edge に互換性のないサイトをリダイレクトします。
- [SpeechRecognitionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#speechrecognitionenabled) -音声認識を構成します。
- [WebCaptureEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcaptureenabled) -Microsoft Edge で Web キャプチャ機能を有効にします。

#### <a name="deprecated-policy"></a>廃止されたポリシー

[NewTabPageSetFeedType](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) - Microsoft Edge の新規タブ ページのエクスペリエンスを設定する

#### <a name="obsoleted-policy"></a>非推奨ポリシー

[EnableDeprecatedWebPlatformFeatures](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledeprecatedwebplatformfeatures) -廃止された Web プラットフォームの機能を一定期間、再度有効にします。

<!-- end major 87 -->

## <a name="version-86062269-november-13"></a>バージョン 86.0.622.69: 11 月 13 日

セキュリティ更新プログラムは、[こちら](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-13-2020)に記載されています。 この更新プログラムには、[CVE-2020-16013](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16013) と [CVE-2020-16017](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16017) が含まれています。これらについては、Chromium チームにより実際に感染報告がある悪用が報告されています。

## <a name="version-86062268-november-11"></a>バージョン 86.0.622.68: 11 月 11 日

セキュリティの更新プログラムは、[ここ](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-11-2020)に記載されています

## <a name="version-86062263-november-4"></a>バージョン 86.0.622.63: 11 月 4 日

セキュリティ更新プログラムは、[こちら](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-4-2020)に記載されています。 この更新プログラムには、[CVE-2020-16009](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16009) が含まれています。これについては、Chromium チームにより実際に感染報告がある悪用が報告されています。

## <a name="version-86062261-november-2"></a>バージョン 86.0.622.61: 11 月 2 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-86062258-october-29"></a>バージョン 86.0.622.58: 10 月 29 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-86062256-october-27"></a>バージョン 86.0.622.56: 10 月 27 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-86062251-october-22"></a>バージョン 86.0.622.51: 10 月 22 日

セキュリティの更新プログラムは、[ここ](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#october-22-2020)に記載されています

## <a name="version-86062248-october-20"></a>バージョン 86.0.622.48: 10 月 20 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-86062243-october-15"></a>バージョン 86.0.622.43 : 10 月 15 日

さまざまなバグとパフォーマンスの問題を修正しました。

<!-- begin major 86 -->
## <a name="version-86062238-october-9"></a>バージョン 86.0.622.38 : 10 月 9 日

セキュリティの更新プログラムは、[ここ](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#october-9-2020)に記載されています

### <a name="feature-updates"></a>機能更新プログラム

* **Microsoft Edge の以前のバージョンにロールバック。** ロールバック機能では、Microsoft Edge の最新バージョンに問題がある場合、管理者は Microsoft Edge を既知の正常なバージョンに戻すことができます。 **注:** Stable バージョン 86.0.622.38 は、ロールバック先となることができる最初のバージョンです。これは、安定バージョン87が、ロールバック元となる準備ができた最初のバージョンという意味でもあります。 [詳しくはこちらをご覧ください](edge-learnmore-rollback.md)。

* **エンタープライズ全体で、同期の有効化を既定で強制できます。**  管理者は既定で、[ForceSync](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcesync) ポリシーを使用して、Azure Active Directory (Azure AD) アカウントに対して同期を有効にできます。

* **Windows 7および8.1 でのプロファイル の自動切り替え。** 現在 Windows 10 の Microsoft Edge で利用可能なプロフィールの自動切り替えは、ダウンレベルの Windows (Windows 7、8.1) に拡張されました。 詳細については、ブログ記事「[プロファイルの自動切り替え](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/)」を参照してください。

* **SameSite=既定で緩い Cookie**。 Web セキュリティとプライバシーを向上させるために、Cookie は、既定では、[SameSite=Lax](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite) 処理に設定されます。 つまり、Cookie はファーストパーティのコンテキストでのみ送信され、サードパーティに送信される要求では省略されます。 この変更により、サードパーティのリソースが正しく機能するために Cookie を必要とする Web サイトに互換性の影響が生じる可能性があります。 このような Cookie を許可するために、Web 開発者は、Cookie の設定時に明示的な `SameSite=none` および `Secure` 属性を追加することにより、サードパーティのコンテキストから設定および送信する必要がある Cookie にマークを付けることができます。 特定のサイトをこの変更から除外することを希望する企業は、[LegacySameSiteCookieBehaviorEnabledForDomainList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#legacysamesitecookiebehaviorenabledfordomainlist) ポリシーを使用してこれを行うか、[LegacySameSiteCookieBehaviorEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) ポリシーを使用してすべてのサイトにわたる変更をオプトアウトできます。

* **HTML5 アプリケーション キャッシュ API の削除。**  Microsoft Edge バージョン 86 以降、Web ページのオフライン使用を可能にするレガシ アプリケーション キャッシュ API は Microsoft Edge から削除されます。 Web 開発者は、[WebDev ドキュメント](https://web.dev/appcache-removal/)で、アプリケーション キャッシュ API のサービス ワーカーへの置き換えに関する情報を確認する必要があります。  重要: Microsoft Edge バージョン 90 まで、サイトが非推奨のアプリケーション キャッシュ API を引き続き使用できるようにする [AppCache OriginTrial Token](https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673) を要求できます。

* **プライバシーとセキュリティ**

  * ダウンレベルの Windows と macOS で [MetricsReportingEnabled]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) と [SendSiteInformationToImproveServices]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) ポリシーを置き換えます。 これらのポリシーは Microsoft Edge バージョン 86 では非推奨で、Microsoft Edge バージョン 89 で廃止されます。<br>
これらのポリシーは、Windows 10 では[利用統計情報の許可](https://go.microsoft.com/fwlink/?linkid=2099569)に、その他すべてのプラットフォームでは新しい [DiagnosticData](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata) ポリシーに置き換えられます。 これにより、ユーザーは Windows 7、8、8.1、macOS で、Microsoft に送信される診断データを管理できるようになります。
  * セキュリティで保護された DNS (DNS-over-HTTPS) のサポート。  Microsoft Edge バージョン 86 以降、セキュリティ保護された DNS を制御する設定が、管理されていないデバイスで利用可能になりました。 ユーザーは管理されたデバイスでこれらの設定にアクセスできませんが、IT 管理者は [dnsoverhttpsmode](https://docs.microsoft.com/deployedge/microsoft-edge-policies#dnsoverhttpsmode) グラウンド ポリシーを使用して、セキュリティ保護された DNS を有効または無効にすることができます。

* **Internet Explorerモード:** ユーザーが Microsoft Edge ユーザー インターフェイス (UI) を使用して、Internet Explorer モードでサイトをテストできるようにします。 Microsoft Edge バージョン 86 以降、管理者はユーザーがテスト目的で、またはサイトがサイト一覧の XML に追加されるまでの臨時措置として Internet Explorer モードでタブを読み込むことができるよう、UI オプションを有効にできます。

* **PDF の更新情報:**

  * PDF ドキュメントの目次。 バージョン 86 以降、Microsoft Edge に PDF ドキュメント内をユーザーが簡単に移動できる目次のサポートが追加されました。
  * スモール フォーム ファクターの画面で、すべての PDF 機能にアクセス。 画面サイズが小さなデバイスでも、Microsoft Edge PDF リーダーのすべての機能にアクセスできます。
  * PDF ファイルで蛍光ペンのペン サポート。 この更新で、ユーザーはデジタル ペンを使用して、実際の蛍光ペンと紙と同様の方法で PDF ファイルでテキストを直接強調表示できます。
  * PDF のスクロールの改善。 長い PDF ドキュメント内を移動するときに、スムーズなスクロールを体験できるようになりました。

* **ユーザーが Microsoft Edge アドオン Web サイトで検索クエリを入力し始めると、自動完了の候補が表示されます。** 自動完了によって、ユーザーは文字列全体を入力せずに検索クエリを素早く完成できます。 ユーザーは正確なスペルを記憶する必要がなく、表示されるオプションから選ぶことができるので、これは便利な機能です。

* **グループ ポリシーを使用して、新しいタブ ページ (NTP) にカスタム イメージを追加できます。** Microsoft Edge バージョン 86 以降、NTP で既定のイメージをユーザーが指定したイメージで置き換えるためのオプションを使用できます。 このイメージのプロパティを管理する機能も、グループ ポリシーによってサポートされています。

* **カスタマイズしたキーボード ショートカットを VS コードと一致させます。** Microsoft Edge の DevTools では、使用しているエディターや IDE に合わせて DevTools のキーボード ショートカットをカスタマイズできるようになりました。 (Microsoft Edge 84 で、VS コードに対して DevTools のキーボードショートカットを一致させる機能を追加しました)。

* **ダウンロード マネージャーを使用して、ダウンロードをディスクから削除できます。** ユーザーは、ブラウザーを離れることなくダウンロードしたファイルをディスクから削除できるようになりました。 ダウンロード削除のこの新しい機能は、ダウンロード シェルフのコンテキスト メニューまたはダウンロード ページに存在します。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

23個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [CollectionsServicesAndExportsBlockList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#collectionsservicesandexportsblocklist) - 指定したサービスの一覧へのアクセスをブロックし、コレクション内のターゲットをエクスポートします。
- [DefaultFileSystemReadGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultfilesystemreadguardsetting) -読み取り用のファイルシステム API の使用を制御します。
- [DefaultFileSystemWriteGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultfilesystemwriteguardsetting)-書き込みにファイルシステム API の使用を制御します。
- [DefaultSensorsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultsensorssetting) - 既定のセンサーの設定。
- [DefaultSerialGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultserialguardsetting) - シリアル API の使用を制御します。
- [DiagnosticData](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata) - ブラウザーの使用状況に関する必須およびオプションの診断データを送信します。
- [EnterpriseModeSiteListManagerAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enterprisemodesitelistmanagerallowed) - Enterprise Mode Site List Manager ツールへのアクセスを許可します。
- [FileSystemReadAskForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#filesystemreadaskforurls) - これらのサイトのファイル システム API を通して読み取りアクセスを許可します。
- [FileSystemReadBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#filesystemreadblockedforurls) -これらのサイトのファイルシステム API を使用した読み取りアクセスをブロックします。
- [FileSystemWriteAskForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#filesystemwriteaskforurls) - これらのサイトのファイルとディレクトリへの書き込みアクセスを許可します。
- [FileSystemWriteBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#filesystemwriteblockedforurls) -これらのサイトのファイルとディレクトリの書き込みアクセスをブロックします。
- [ForceSync](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcesync) - ブラウザーのデータを強制的に同期し、同期の同意プロンプトを表示しません。
- [InsecureFormsWarningsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#insecureformswarningsenabled) - セキュリティで保護されていないフォームに対する警告を有効にします。
- [InternetExplorerIntegrationTestingAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) - Internet Explorer モードテストを許可します。
- [SpotlightExperiencesAndRecommendationsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#spotlightexperiencesandrecommendationsenabled) - カスタマイズされた背景画像およびテキスト、提案、通知、Microsoft サービスのヒントをユーザーが受信できるかどうかを選択します。
- [NewTabPageAllowedBackgroundTypes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpageallowedbackgroundtypes) - 新しいタブ ページ レイアウトに使用できる背景の種類を構成します。
- [SaveCookiesOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#savecookiesonexit) - Microsoft Edge の終了時に Cookie を保存します。
- [SensorsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sensorsallowedforurls) - 特定のサイトのセンサーへのアクセスを許可します。
- [SensorsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sensorsblockedforurls) - 特定のサイトのセンサーへのアクセスをブロックします。
- [SerialAskForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#serialaskforurls) - 特定のサイトのシリアル API を許可します。
- [SerialBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#serialblockedforurls) - 特定のサイトのシリアル API をブロックします。
- [UserAgentClientHintsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#useragentclienthintsenabled) - ユーザー エージェント クライアント ヒント機能を有効にします。
- [UserDataSnapshotRetentionLimit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#userdatasnapshotretentionlimit) - 緊急ロールバックの場合に使用されるユーザー データのスナップショット数を制限します。

#### <a name="deprecated-policies"></a>廃止されたポリシー

- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - 使用状況とクラッシュ関連のデータレポートを有効にします。
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Microsoft サービスを改善するためにサイト情報を送信します。

#### <a name="obsoleted-policy"></a>非推奨ポリシー

[TLS13HardeningForLocalAnchorsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#tls13hardeningforlocalanchorsenabled) - ローカル トラスト アンカーの TLS 1.3 セキュリティ機能を有効にします。

## <a name="version-85056470-october-6"></a>バージョン 85.0.564.70 : 10 月 6 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-85056468-october-1"></a>バージョン 85.0.564.68: 10 月 1 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-85056463-september-23"></a>バージョン 85.0.564.63: 9 月 23 日

セキュリティの更新プログラムは、[ここ](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#september-23-2020)に記載されています

## <a name="version-85056451-september-9"></a>バージョン 85.0.564.51: 9 月 9 日

セキュリティの更新プログラムは、[ここ](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#september-9-2020)に記載されています

## <a name="version-85056444-august-31"></a>バージョン 85.0.564.44: 8 月 31 日

さまざまなバグとパフォーマンスの問題を修正しました。

<!-- 85.0.564.41: August 27 -->
<!-- Archived to version 84.0.522.40: July 16 -->

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
