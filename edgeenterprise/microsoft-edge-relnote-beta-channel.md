---
title: Beta チャネルに関する Microsoft Edge のリリース ノート
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 03/03/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Beta チャネルに関する Microsoft Edge のリリース ノート
ms.openlocfilehash: e2a2933e7edf3456bcb33e70d6db7a36ab72aa07
ms.sourcegitcommit: 6603dc23d8e7ff46df76bc6aa48b93a0b435fe7d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385624"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge Beta チャネルのリリースノート

これらのリリース ノートでは、Microsoft Edge Beta チャネルに含まれている新機能とセキュリティ以外の更新プログラムに関する情報を提供します。 これらのリリース ノートのアーカイブ バージョンは、[こちら](microsoft-edge-relnote-archive-beta-channel.md)から入手できます。

## <a name="version-89077445-march-3"></a>バージョン 89.0.774.45: 3 月 3 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-89077439-february-26"></a>バージョン 89.0.774.39: 2 月 26 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-89077434-february-22"></a>バージョン 89.0.774.34: 2 月 22 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-89077427-february-12"></a>バージョン 89.0.774.27: 2 月 12 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-89077423-february-8"></a>バージョン 89.0.774.23: 2 月 8 日

さまざまなバグとパフォーマンスの問題を修正しました。
<!-- begin major 89 -->
## <a name="version-89077418-february-3"></a>バージョン 89.0.774.18: 2 月 3 日

### <a name="feature-updates"></a>機能更新プログラム

- **キオスク モードでは、追加のロックダウン機能が有効になります**。 Microsoft Edge バージョン 89 から、キオスク モード内にロックダウン機能が追加され、お客様は生産性が高く、より安全なエクスペリエンスでジョブを実行できます。 [詳細はこちらをご覧ください](microsoft-edge-configure-kiosk-mode.md#kiosk-mode-supported-features)。

- **Enterprise Mode Site List Manager ツールは、*edge://compat* ページを経由したブラウザーで使用可能です**。 このツールを使用して、Microsoft Edge で Internet Explorer モード向けのサイト一覧 XML を作成、編集、およびエクスポートできます。 必要に応じて、グループ ポリシーを経由してこのツールへのアクセスを有効にできます。 [詳細はこちらをご覧ください](https://docs.microsoft.com/deployedge/edge-ie-mode-site-list-manager)。

- **タブをスリープ状態にし、ブラウザーのパフォーマンスを向上させます**。 タブをスリープすると、アクティブでないタブをスリープ状態にすることでブラウザーのパフォーマンスが向上し、メモリや CPU などのシステム リソースが解放され、アクティブなタブや他のアプリケーションで使用できます。 ユーザーは、サイトがスリープ状態になるのを防ぎ、非アクティブなタブがスリープ状態になる前の時間の長さを構成できます。 ユーザーのフローを維持するために、イントラネット サイトなど、特定のサイトがスリープ状態になるのを防ぐための[ヒューリスティック](https://techcommunity.microsoft.com/t5/articles/sleeping-tabs-faq/m-p/1705434)も用意されています。 この機能は、グループ ポリシーを使用して管理できます。

  > [!NOTE]
  > 「タブをスリープ状態にし、ブラウザーのパフォーマンスを向上させます」は、メジャー バージョン 89.0.774.18 の 2 月 3 日のリリース ノートの更新プログラムです。

- **クラウド内の Microsoft Edge 同期データを手動でリセットします**。 Microsoft Edge の同期データを製品内からリセットする方法を導入しています。 これにより、お使いのデータは、Microsoft サービスからクリアされます。また、以前ならサポートチケットを必要としていたような特定の製品の問題を解決することもできます。

- **PDF ドキュメント内でのテキストの選択エクスペリエンスが向上しました**。 ユーザーは、Microsoft Edge バージョン 89 以降で開いた PDF ドキュメント全体で、よりスムーズでより一貫性の高いテキスト選択エクスペリエンスを実現できるようになります。

- **「開発者モード拡張機能を無効にする」という警告は完全に無視できます**。 Microsoft Edge バージョン 89 以降で、"開発者モード拡張機能を無効にする" という警告をオフにするには、[再び表示しない] オプションを選択します。

- **ツール バーで拡張機能を管理します**。 ツール バーの新しい拡張機能メニューでは、拡張機能を簡単に非表示またはピン留めできます。 拡張機能を管理し、新しい拡張機能を検索するためのクイック リンクでは、新しい拡張機能を簡単に見つけて、既存の拡張機能を管理できます。

- **アドレス バー、履歴検索ページ、および履歴ハブでの自然言語検索のサポート**。 Microsoft Edge バージョン 89 以降で、アドレス バー、履歴ページ、履歴ハブで自然言語検索を使用すると、記事や Web サイトを簡単に検索できます。 ユーザーは、タイトル/URL キーワードの一致に加えて、以前に表示されたページ コンテンツ/説明/タイミング (「先週のレシピ」など) を検索できます。

- **生産性:**

  - オートフィルでサポートされる生年月日フィールド。 現在、Microsoft Edge は、住所、名前、電話番号などのデータを自動入力することで、フォームに入力し、オンラインでアカウントを作成する場合に時間と労力を節約するのに役立ちます。Microsoft Edge バージョン 89 以降で、保存して自動入力できる別のフィールド (生年月日) のサポートが追加されています。 この情報は、プロファイル設定でいつでも表示、編集、削除できます。
  - オートフィル候補を拡張して、クリップボードからコンテンツを含めます。 クリップボードの内容は、オートフィル候補として表示するプロファイル フィールドまたはアドレス フィールド (電話番号、メールアドレス、郵便番号、市区町間、州など) を選択すると解析されます。

- **自動再生ビデオのブロックをサポートします**。 Microsoft Edge バージョン 89 以降で、ユーザーはメディアの自動再生をブロックするオプションを利用できます。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

- [BrowsingDataLifetime](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#browsingdatalifetime) - データの有効期間設定の参照
- [MAMEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#mamenabled) - モバイル アプリ管理の有効化
- [DefinePreferredLanguages](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#definepreferredlanguages) - サイトが言語をサポートしている場合に Web サイトが表示する優先言語の順序付きリストを定義する
- [ShowRecommendationsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showrecommendationsenabled) - Microsoft Edge からの推奨事項とプロモーション通知を許可する
- [PrintingAllowedBackgroundGraphicsModes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#printingallowedbackgroundgraphicsmodes) - バックグラウンド グラフィックス印刷モードを制限する
- [PrintingBackgroundGraphicsDefault](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#printingbackgroundgraphicsdefault)- 既定のバックグラウンド グラフィックス印刷モード
- [SmartActionsBlockList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartactionsblocklist)- サービスの一覧に対するスマート アクションをブロックする

#### <a name="obsoleted-policies"></a>非推奨ポリシー

- [ForceLegacyDefaultReferrerPolicy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcelegacydefaultreferrerpolicy) - no-referrer-when-downgrade の既定の参照元ポリシーを使用します
- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - 使用状況とクラッシュ関連のデータ レポートを有効にします
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices)|Microsoft サービスの品質向上のためにサイト情報を送信します
<!-- end major 89 -->

## <a name="version-88070556-january-29"></a>バージョン 88.0.705.56: 1 月 29 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-88070549-january-20"></a>バージョン 88.0.705.49: 1 月 20 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-88070545-january-15"></a>バージョン 88.0.705.45: 1 月 15 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-88070541-january-11"></a>バージョン 88.0.705.41: 1 月 11 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-88070529-december-21"></a>バージョン 88.0.705.29: 12 月 21 日

さまざまなバグとパフォーマンスの問題を修正しました。

<!-- begin major 88 -->
## <a name="version-88070518-december-9"></a>バージョン 88.0.705.18: 12 月 9 日

### <a name="feature-updates"></a>機能の更新プログラム

- **非推奨:**

  - FTP プロトコルのサポートを廃止します。 従来の FTP プロトコルのサポートは Microsoft Edge から削除されました。 FTP リンクに移動しようとすると、ブラウザーは、FTP リンクを処理する外部アプリケーションを開く操作をオペレーティング システムに指示します。 または、IT 管理者は、FTP プロトコルに依存するサイトで IE モードを使用する Microsoft Edge を構成できます。
  - Adobe Flash のサポートは削除されます。 Microsoft Edge Beta バージョン 88 から、Adobe Flash の機能とサポートは削除されます。 詳細: [Adobe Flash Player のサポート終了に関する更新プログラム - Microsoft Edge ブログ (windows.com)](https://blogs.windows.com/msedgedev/2020/09/04/update-adobe-flash-end-support/)

- **認証:**

  - シングル サインオン (SSO) は、macOS およびダウンレベル Windows の Azure Active Directory (Azure AD) アカウントと Microsoft アカウント (MSA) で利用できます。 macOS またはダウンレベルの Microsoft Windows (7, 8.1) で Microsoft Edge にサインインしたユーザーは、Work アカウントと Microsoft アカウント (bing.com、office.com、msn.com、outlook.com など) でシングル サインオンを許可するように構成された Web サイトに自動的にサインインします。<br>注: この機能を利用するには、ユーザーが Microsoft Edge 88 より前のバージョンで Microsoft Edge にサインインした場合、サインアウトしてからサインインしなおす必要がある場合があります。
  - macOS のユーザーを、自分の仕事用アカウントで認証するサイトの仕事用プロファイルに自動的に切り替えます。 Microsoft Edge バージョン 88 から、macOS 上のユーザーの仕事用プロファイルで認証するサイトを切り替える機能が提供されています。<br>注: この機能を利用するには、ユーザーが Microsoft Edge 88 より前のバージョンで Microsoft Edge にサインインした場合、サインアウトしてからサインインしなおす必要がある場合があります。

- **セッションを終了するキオスク モード オプション**。 [セッションの終了] ボタンは、キオスク モードのパブリック ブラウズ エクスペリエンスで利用できます。 この機能により、Microsoft Edge を閉じたときにブラウザーのデータと設定が削除されます。 キオスク モード機能とロードマップの詳細については 、「[Microsoft Edge キオスク モードを構成する](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode)」を参照してください。

- **セキュリティとプライバシー:**

  - ユーザーのパスワードのオンラインでの漏洩が見つかると、警告が生成されます。 ユーザーのパスワードは、侵害された資格情報のリポジトリと照合され、一致するものが見つかるとユーザーに警告を通知します。 セキュリティとプライバシーを確保するために、ユーザーのパスワードは漏洩した資格情報のデータベースと照合するときにハッシュ化され、暗号化されます。
  - 混在コンテンツを自動的にアップグレードします。 HTTPS 経由で配信されるセキュリティで保護されたページには、セキュリティ保護されていない HTTP 経由で提供される参照イメージが含まれる場合があります。 Microsoft Edge 88 のプライバシーとセキュリティを向上させるために、これらの画像は HTTPS 経由で取得されます。 HTTPS 経由で画像を利用できない場合、画像は読み込まれません。
  - サイトの権限をサイト別および最近のアクティビティ別に表示します。 Microsoft Edge 88 から、ユーザーはサイトのアクセス許可を簡単に管理できます。 アクセス許可の種類ではなく、Web サイト別にアクセス許可を表示できます。 さらに、サイトのアクセス許可に対する最近の変更すべてがユーザーに表示される最近のアクティビティ セクションが追加されました。
  - ブラウザーの Cookie の制御が向上しました。 Microsoft Edge 88 から、ユーザーはファースト パーティの Cookie に影響を及ぼさずにサード パーティの Cookie を削除できます。 また、ユーザーは、ファースト パーティまたはサード パーティによって Cookie をフィルター処理し、名前、Cookie の数、および保存および最終変更されたデータの量で並べ替えすることもできます。

- **パフォーマンス:**

  - タブをスリープ状態にし、ブラウザーのパフォーマンスを向上させます。 タブをスリープすると、アクティブでないタブをスリープ状態にすることでブラウザーのパフォーマンスが向上し、メモリや CPU などのシステム リソースが解放され、アクティブなタブや他のアプリケーションで使用できます。 ユーザーは、サイトがスリープ状態になるのを防ぎ、非アクティブなタブがスリープ状態になる前の時間の長さを構成できます。 ユーザーのフローを維持するために、イントラネット サイトなど、特定のサイトがスリープ状態になるのを防ぐためのヒューリスティックも用意されています。 この機能は、実験を有効にしたユーザーのランダムに選択されたグループに限定されます。 Microsoft Edge バージョン 89 では、スリープ タブ機能を既定で有効にする予定です。 この機能は、グループ ポリシーを使用して管理できます。
  - 起動ブーストを使用して Microsoft Edge の起動速度を向上します。 Microsoft Edge の起動速度を向上させるために、スタートアップ ブーストという名前の機能を開発しました。 起動ブーストにより、Microsoft Edge をバックグラウンドで実行することで、Microsoft Edge の起動速度が向上します。 注: この機能は、実験を有効にしたユーザーのランダムに選択されたグループに限定されます。 これらのユーザーは、機能チームにフィードバックを提供しています。

- **生産性:**

  - 垂直方向のタブを使用して生産性とマルチタスクを改善します。 水平方向のタブの数が増えるにつれて、サイト タイトルが切れ始め、タブが縮小されるごとにタブ コントロールが失われます。 これにより、タブの検索、切り替え、管理に費やす時間が長く、タスクに対する時間が減り、ユーザー ワークフローが中断されます。 垂直方向のタブを使用すると、ユーザーはタブを横に移動できます。縦方向に配置されたアイコンと長いサイト タイトルを使用すると、開くタブをすばやくスキャン、識別、切り替えやすくなります。
  - 生年月日フィールドの日付を自動入力します。 Microsoft Edge では、住所、名前、電話番号などのユーザー データを自動入力することで、フォームに入力し、オンラインでアカウントを作成する際に時間と労力を節約できます。Microsoft Edge では、ユーザーが保存して自動入力できる生年月日フィールドがサポートされます。 ユーザーは、プロファイル設定でいつでもこの情報を表示、編集、削除できます。
  - 履歴で最近閉じた機能が改善されました。 最近閉じた場合、前のセッションではなく、過去の閲覧セッションから最後の 25 のタブとウィンドウが保持されます。 ユーザーは、新しい履歴エクスペリエンスで最近閉じたタブを選択して、開いていたすべてのタブを表示できます。
  - 既定で有効になっている "1 日の一覧" 機能。 Microsoft Edge バージョン 88 から、情報ワーカーは新しいタブ ページ (NTP) でインテリジェントな生産性機能を利用できます。 M365 Graph を利用して、ユーザーが自分の仕事用または学校アカウントでサインインし、個人設定をした関連するコンテンツを提供します。 ユーザーは、"1 日の一覧" モジュールをすばやくスキャンして、会議や最近の作業を簡単に追跡し、使用するアプリケーションをすばやく起動できます。

- **PDF:**

  - ブック ビューでの PDF ドキュメントの表示 (2 ページ)。 Microsoft Edge バージョン 88 から、ユーザーは PDF ドキュメントを 1 ページまたは 2 ページのブック ビューで表示できます。 ビューを変更するには、ツール バーの [ **ページ ビュー]** ボタンをクリックします。
  - PDF ファイルのアンカー付きテキスト ノートのサポート。 Microsoft Edge バージョン 87 から、ユーザーは PDF ファイル内の任意のテキストに入力したテキスト ノートを追加できます。
  - PDF ドキュメントでのテキストの選択エクスペリエンスがスムーズになります。 ユーザーは、Microsoft Edge で開いた PDF ドキュメント全体で、よりスムーズで一貫したテキスト選択エクスペリエンスを実現します。
  - ダウンロード バーに PDF ファイルとして保存された Web ページを表示します。 [ダウンロード] バーの Web ページの印刷先として [PDF 形式で保存] を設定して生成された PDF ファイルを表示できます。

- **フォント:**

  - ブラウザー アイコンは Fluent デザイン システムに更新されます。 ブラウザーで Fluent Design を引き続き使用する作業の一環として、アイコンを新しい Microsoft アイコン システムに合わせて調整する変更を行いました。 これらの変更は、タブ、アドレス バー、さまざまなメニューにあるナビゲーション アイコンや移動方法のアイコンなど、タッチの多いユーザー インターフェイスの多くに影響します。
  - フォントのレンダリングが改善されました。 テキストのレンダリングが改善され、わかりやすくなり、ぼやけも少なくなりました。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

16 個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://www.microsoft.com/edge/business/download)からダウンロードしてください。 次の新しいポリシーが追加されました。

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
- [UpdatePolicyOverride](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#updatepolicyoverride) - Microsoft Edge で利用できる更新プログラムを Microsoft Edge Update でどのように処理するかを指定します
- [VerticalTabsAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#verticaltabsallowed) - ブラウザーの横にあるタブの垂直方向のレイアウトの可用性を構成します。
- [WebRtcAllowLegacyTLSProtocols](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webrtcallowlegacytlsprotocols) - WebRTC で従来の TLS/DTLS ダウングレードを許可します。

#### <a name="deprecated-policies"></a>廃止されたポリシー

次のポリシーは廃止されました。

- [ProactiveAuthEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proactiveauthenabled) - プロアクティブ認証を有効にします。
- [ProxyBypassList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxybypasslist) - プロキシ バイパス ルールを構成します。
- [ProxyMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxymode) - プロキシ サーバー設定を構成します。
- [ProxyPacUrl](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxypacurl) - プロキシの .pac ファイルの URL を設定します。
- [ProxyServer](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxyserver) - プロキシ サーバーのアドレスまたは URL を構成します。
- [WebDriverOverridesIncompatiblePolicies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webdriveroverridesincompatiblepolicies) - WebDriver が互換性のないポリシーを上書きすることを許可します。

#### <a name="obsoleted-policies"></a>不使用のポリシー

次のポリシーは廃止されました。

- [DefaultPluginsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultpluginssetting) - 既定の Adobe Flash 設定。
- [PluginsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsallowedforurls) - 特定のサイトで Adobe Flash プラグインを許可します。
- [PluginsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsblockedforurls) - 特定のサイトで Adobe Flash プラグインをブロックします。
- [RunAllFlashInAllowMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#runallflashinallowmode) - Adobe Flash コンテンツ設定をすべてのコンテンツに拡張します。

<!-- end major 88 -->

## <a name="version-87066455-december-3"></a>バージョン 87.0.664.55: 12 月 3 日

さまざまなバグとパフォーマンスの問題を修正しました。 このリリースでは、次の新機能がサポートされています。

- **ユーザーのパスワードのオンラインでの漏洩が見つかると、警告が生成されます**。 ユーザーのパスワードは、侵害された資格情報のリポジトリと照合され、一致するものが見つかるとユーザーに警告を通知します。 セキュリティとプライバシーを確保するために、ユーザーのパスワードは漏洩した資格情報のデータベースと照合するときにハッシュ化され、暗号化されます。

## <a name="version-87066452-november-30"></a>バージョン 87.0.664.52: 11 月 30 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-87066440-november-18"></a>バージョン 87.0.664.40: 11 月 18 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-87066436-november-16"></a>バージョン 87.0.664.36: 11 月 16 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-87066430-november-9"></a>バージョン 87.0.664.30: 11 月 9 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-87066424-november-2"></a>バージョン 87.0.664.24: 11 月 2 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-87066418-october-26"></a>バージョン 87.0.664.18: 10 月 26 日

さまざまなバグとパフォーマンスの問題を修正しました。

<!-- begin major 87 -->
## <a name="version-87066412-october-20"></a>バージョン 87.0.664.12: 10 月 20 日

### <a name="feature-updates"></a>機能更新プログラム

- **キオスクモードプライバシー機能を有効にします**。 Microsoft Edge バージョン87から、ユーザーデータのプライバシーに関して企業のサポートができるキオスクモードの機能を有効にすることができます。 これらの機能により、終了時にユーザーデータをクリアしたり、ダウンロードしたファイルを削除したり、一定のアイドル時間が経過した後に、構成されていたスタート操作をリセットしたりできます。 [Microsoft Edge キオスクモードを 構成する方法](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode)の詳細については、こちらを参照してください
- **ClickOnce の展開が既定で有効**。 Microsoft Edge 87 では、ClickOnce が既定で有効になっています。これにより、企業がソフトウェアを展開する際の障壁を減らし、Microsoft Edge のレガシブラウザーの動作に合わせることができます。 Microsoft Edge 87 以降、ClickOnceEnabled policyが"未構成"の 状態の場合は、新しい既定の「有効化が ClickOnceの状態」（以前の規定が無効だった状態と異なり）に反映されます。
- **エンタープライズ新しいタブページ (NTP)は、カスタマイズ可能な仕事関連のフィードコンテンツと生産性を結びつけます**。 エンタープライズ NTP は、職場または学校アカウントでサインインしているユーザーに対して提供される Office 365 生産性向上ページだけでなく、カスタマイズされた、仕事関連の企業や業界のコンテンツを1ページにまとめて提供いたします。 ユーザーは、使い慣れた Office 365 のコンテンツと、Bing で提供されている一般法人向けの Microsoft Search を目にすることでしょう。 さらに、ユーザー、会社、またはその業界に関連するコンテンツやモジュールだけでなく、組織が利用可能にしている他のフィードを選択して、カスタマイズ可能な "マイフィード" を簡単に閲覧できます。 [詳しくはこちらをご覧ください](https://docs.microsoft.com/microsoft-365/admin/manage/manage-industry-news?view=o365-worldwide&preserve-view=true)。

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
- [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#edgeshoppingassistantenabled)-Microsoft Edge のショッピングが有効になりました。 
- [HideInternetExplorerRedirectUXForIncompatibleSitesEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#hideinternetexplorerredirectuxforincompatiblesitesenabled) -Microsoft Edge のワンタイムリダイレクトダイアログとバナーを非表示にします。
- [KioskAddressBarEditingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) -キオスクモードのパブリックブラウザーのエクスペリエンスを編集するアドレスバーを構成します。
- [KioskDeleteDownloadsOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) -Microsoft Edge が閉じたときに、キオスク セッションの一部としてダウンロードされたファイルを削除する
- [PasswordRevealEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordrevealenabled) -[パスワードの表示] ボタンを有効にします。
- [RedirectSitesFromInternetExplorerPreventBHOInstall](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerpreventbhoinstall) -Internet Explorer から Microsoft Edge に互換性のないサイトをリダイレクトするために BHO をインストールできないようにします。
- [RedirectSitesFromInternetExplorerRedirectMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerredirectmode) -Internet Explorer から Microsoft Edge に互換性のないサイトをリダイレクトします。
- [SpeechRecognitionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#speechrecognitionenabled) -音声認識を構成します。
- [WebCaptureEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcaptureenabled) -Microsoft Edge で web キャプチャ機能を有効にします。

#### <a name="deprecated-policy"></a>廃止されたポリシー

[NewTabPageSetFeedType](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) - Microsoft Edge の新規タブ ページのエクスペリエンスを設定する

#### <a name="obsoleted-policy"></a>非推奨ポリシー

[EnableDeprecatedWebPlatformFeatures](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledeprecatedwebplatformfeatures) -廃止されたWebプラットフォームの機能を一定期間、再度有効にします。

<!-- end major 87 -->

## <a name="version-86062243-october-16"></a>バージョン 86.0.622.43: 10 月 16 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-86062236-october-7"></a>バージョン 86.0.622.36: 10 月 7 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-86062231-october-1"></a>バージョン 86.0.622.31: 10 月 1 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-86062228-september-28"></a>バージョン 86.0.622.28: 9 月 28 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-86062215-september-14"></a>バージョン86.0.622.15: 9 月14 日

さまざまなバグとパフォーマンスの問題を修正しました。

<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
