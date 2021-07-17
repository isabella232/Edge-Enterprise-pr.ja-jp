---
title: Microsoft Edge Beta チャネルのアーカイブされたリリース ノート
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Beta チャネルのアーカイブされたリリース ノート
ms.openlocfilehash: 065c665892edc264e2ab94375bedf3af9dbc936c
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642423"
---
# <a name="archived-release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge Beta チャネルのアーカイブされたリリース ノート

これらのリリース ノートでは、Microsoft Edge Beta チャネルに含まれている新機能とセキュリティ以外の更新プログラムに関する情報を提供します。 Microsoft Edge チャネルを理解するには、「[Microsoft Edge チャネルの概要](microsoft-edge-channels.md)」を参照してください。 すべてのセキュリティの更新プログラムは、[ここ](microsoft-edge-relnotes-security.md)にリストされています。
## <a name="version-89077418-february-3"></a>バージョン 89.0.774.18: 2 月 3 日

### <a name="feature-updates"></a>機能更新プログラム

- **キオスク モードでは、追加のロックダウン機能が有効になります**。 Microsoft Edge バージョン 89 から、キオスク モード内にロックダウン機能が追加され、お客様は生産性が高く、より安全なエクスペリエンスでジョブを実行できます。 [詳細はこちらをご覧ください](microsoft-edge-configure-kiosk-mode.md#kiosk-mode-supported-features)。

- **Enterprise Mode Site List Manager ツールは、*edge://compat* ページを経由したブラウザーで使用可能です**。 このツールを使用して、Microsoft Edge で Internet Explorer モード向けのサイト一覧 XML を作成、編集、およびエクスポートできます。 必要に応じて、グループ ポリシーを経由してこのツールへのアクセスを有効にできます。 [詳細はこちらをご覧ください](./edge-ie-mode-site-list-manager.md)。

- **タブをスリープ状態にし、ブラウザーのパフォーマンスを向上させます**。 タブをスリープすると、アクティブでないタブをスリープ状態にすることでブラウザーのパフォーマンスが向上し、メモリや CPU などのシステム リソースが解放され、アクティブなタブや他のアプリケーションで使用できます。 ユーザーは、サイトがスリープ状態になるのを防ぎ、非アクティブなタブがスリープ状態になる前の時間の長さを構成できます。 ユーザーのフローを維持するために、イントラネット サイトなど、特定のサイトがスリープ状態になるのを防ぐための[ヒューリスティック](https://techcommunity.microsoft.com/t5/articles/sleeping-tabs-faq/m-p/1705434)も用意されています。 この機能は、グループ ポリシーを使用して管理できます。

  > [!NOTE]
  > 「タブをスリープ状態にし、ブラウザーのパフォーマンスを向上させます」は、メジャー バージョン 89.0.774.18 の 2 月 3 日のリリース ノートの更新プログラムです。

- **クラウド内の Microsoft Edge 同期データを手動でリセットします**。 Microsoft Edge の同期データを製品内からリセットする方法を導入しています。 これにより、お使いのデータは、Microsoft サービスからクリアされます。また、以前ならサポートチケットを必要としていたような特定の製品の問題を解決することもできます。

- **PDF ドキュメント内でのテキストの選択エクスペリエンスが向上しました**。 ユーザーは、Microsoft Edge バージョン 89 以降で開いた PDF ドキュメント全体で、よりスムーズでより一貫性の高いテキスト選択エクスペリエンスを実現できるようになります。

- **オートフィルでサポートされる生年月日フィールド**。 現在、Microsoft Edge は、住所、名前、電話番号などのデータを自動入力することで、フォームに入力し、オンラインでアカウントを作成する場合に時間と労力を節約するのに役立ちます。Microsoft Edge バージョン 89 以降で、保存して自動入力できる別のフィールド (生年月日) のサポートが追加されています。 この情報は、プロファイル設定でいつでも表示、編集、削除できます。

- **アドレス バー、履歴検索ページ、および履歴ハブでの自然言語検索のサポート**。 Microsoft Edge バージョン 89 以降で、アドレス バー、履歴ページ、履歴ハブで自然言語検索を使用すると、記事や Web サイトを簡単に検索できます。 ユーザーは、タイトル/URL キーワードの一致に加えて、以前に表示されたページ コンテンツ/説明/タイミング (「先週のレシピ」など) を検索できます。 この機能は、実験を有効にしたユーザーのランダムに選択されたグループに限定されます。 これらのユーザーは、機能チームにフィードバックを提供しています。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

- [BrowsingDataLifetime](./microsoft-edge-policies.md#browsingdatalifetime) - データの有効期間設定の参照
- [MAMEnabled](./microsoft-edge-policies.md#mamenabled) - モバイル アプリ管理の有効化
- [DefinePreferredLanguages](./microsoft-edge-policies.md#definepreferredlanguages) - サイトが言語をサポートしている場合に Web サイトが表示する優先言語の順序付きリストを定義する
- [ShowRecommendationsEnabled](./microsoft-edge-policies.md#showrecommendationsenabled) - Microsoft Edge からの推奨事項とプロモーション通知を許可する
- [PrintingAllowedBackgroundGraphicsModes](./microsoft-edge-policies.md#printingallowedbackgroundgraphicsmodes) - バックグラウンド グラフィックス印刷モードを制限する
- [PrintingBackgroundGraphicsDefault](./microsoft-edge-policies.md#printingbackgroundgraphicsdefault)- 既定のバックグラウンド グラフィックス印刷モード
- [SmartActionsBlockList](./microsoft-edge-policies.md#smartactionsblocklist)- サービスの一覧に対するスマート アクションをブロックする

#### <a name="obsoleted-policies"></a>非推奨ポリシー

- [ForceLegacyDefaultReferrerPolicy](./microsoft-edge-policies.md#forcelegacydefaultreferrerpolicy) - no-referrer-when-downgrade の既定の参照元ポリシーを使用します
- [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) - 使用状況とクラッシュ関連のデータ レポートを有効にします
- [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices)|Microsoft サービスの品質向上のためにサイト情報を送信します
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

- **セッションを終了するキオスク モード オプション**。 [セッションの終了] ボタンは、キオスク モードのパブリック ブラウズ エクスペリエンスで利用できます。 この機能により、Microsoft Edge を閉じたときにブラウザーのデータと設定が削除されます。 キオスク モード機能とロードマップの詳細については 、「[Microsoft Edge キオスク モードを構成する](./microsoft-edge-configure-kiosk-mode.md)」を参照してください。

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

- [BlockExternalExtensions](./microsoft-edge-policies.md#blockexternalextensions) - 外部拡張機能のインストールをブロックします。
- [InternetExplorerIntegrationLocalFileAllowed](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileallowed) - Internet Explorer モードでローカル ファイルを起動できるようにします。
- [InternetExplorerIntegrationLocalFileExtensionAllowList](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist) - Internet Explorer モードのローカル ファイルのファイル拡張子許可リストを開きます。
- [InternetExplorerIntegrationLocalFileShowContextMenu](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileshowcontextmenu) - Internet Explorer モードでリンクを開くためのコンテキスト メニューを表示します。
- [IntranetRedirectBehavior](./microsoft-edge-policies.md#intranetredirectbehavior) - イントラネット リダイレクトの動作。
- [PrinterTypeDenyList](./microsoft-edge-policies.md#printertypedenylist) - 拒否リストでプリンターの種類を無効にします。
- [ShowMicrosoftRewards](./microsoft-edge-policies.md#showmicrosoftrewards) - Microsoft Rewards エクスペリエンスを表示します。
- [SleepingTabsEnabled](./microsoft-edge-policies.md#sleepingtabsenabled) - スリーピング タブを構成します。
- [SleepingTabsTimeout](./microsoft-edge-policies.md#sleepingtabstimeout) - スリーピング タブのバックグラウンド タブの非アクティブタイムアウトを設定します。
- [SleepingTabsBlockedForUrls](./microsoft-edge-policies.md#sleepingtabsblockedforurls) - 特定のサイトでタブのスリープをブロックします。
- [StartupBoostEnabled](./microsoft-edge-policies.md#startupboostenabled) - スタートアップ ブーストを有効にします。
- [UpdatePolicyOverride](./microsoft-edge-policies.md#updatepolicyoverride) - Microsoft Edge で利用できる更新プログラムを Microsoft Edge Update でどのように処理するかを指定します
- [VerticalTabsAllowed](./microsoft-edge-policies.md#verticaltabsallowed) - ブラウザーの横にあるタブの垂直方向のレイアウトの可用性を構成します。
- [WebRtcAllowLegacyTLSProtocols](./microsoft-edge-policies.md#webrtcallowlegacytlsprotocols) - WebRTC で従来の TLS/DTLS ダウングレードを許可します。

#### <a name="deprecated-policies"></a>廃止されたポリシー

次のポリシーは廃止されました。

- [ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - プロアクティブ認証を有効にします。
- [ProxyBypassList](./microsoft-edge-policies.md#proxybypasslist) - プロキシ バイパス ルールを構成します。
- [ProxyMode](./microsoft-edge-policies.md#proxymode) - プロキシ サーバー設定を構成します。
- [ProxyPacUrl](./microsoft-edge-policies.md#proxypacurl) - プロキシの .pac ファイルの URL を設定します。
- [ProxyServer](./microsoft-edge-policies.md#proxyserver) - プロキシ サーバーのアドレスまたは URL を構成します。
- [WebDriverOverridesIncompatiblePolicies](./microsoft-edge-policies.md#webdriveroverridesincompatiblepolicies) - WebDriver が互換性のないポリシーを上書きすることを許可します。

#### <a name="obsoleted-policies"></a>不使用のポリシー

次のポリシーは廃止されました。

- [DefaultPluginsSetting](./microsoft-edge-policies.md#defaultpluginssetting) - 既定の Adobe Flash 設定。
- [PluginsAllowedForUrls](./microsoft-edge-policies.md#pluginsallowedforurls) - 特定のサイトで Adobe Flash プラグインを許可します。
- [PluginsBlockedForUrls](./microsoft-edge-policies.md#pluginsblockedforurls) - 特定のサイトで Adobe Flash プラグインをブロックします。
- [RunAllFlashInAllowMode](./microsoft-edge-policies.md#runallflashinallowmode) - Adobe Flash コンテンツ設定をすべてのコンテンツに拡張します。

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

- **キオスクモードプライバシー機能を有効にします**。 Microsoft Edge バージョン87から、ユーザーデータのプライバシーに関して企業のサポートができるキオスクモードの機能を有効にすることができます。 これらの機能により、終了時にユーザーデータをクリアしたり、ダウンロードしたファイルを削除したり、一定のアイドル時間が経過した後に、構成されていたスタート操作をリセットしたりできます。 [Microsoft Edge キオスクモードを 構成する方法](./microsoft-edge-configure-kiosk-mode.md)の詳細については、こちらを参照してください
- **ClickOnce の展開が既定で有効**。 Microsoft Edge 87 では、ClickOnce が既定で有効になっています。これにより、企業がソフトウェアを展開する際の障壁を減らし、Microsoft Edge のレガシブラウザーの動作に合わせることができます。 Microsoft Edge 87 以降、ClickOnceEnabled policyが"未構成"の 状態の場合は、新しい既定の「有効化が ClickOnceの状態」（以前の規定が無効だった状態と異なり）に反映されます。
- **エンタープライズ新しいタブページ (NTP)は、カスタマイズ可能な仕事関連のフィードコンテンツと生産性を結びつけます**。 エンタープライズ NTP は、職場または学校アカウントでサインインしているユーザーに対して提供される Office 365 生産性向上ページだけでなく、カスタマイズされた、仕事関連の企業や業界のコンテンツを1ページにまとめて提供いたします。 ユーザーは、使い慣れた Office 365 のコンテンツと、Bing で提供されている一般法人向けの Microsoft Search を目にすることでしょう。 さらに、ユーザー、会社、またはその業界に関連するコンテンツやモジュールだけでなく、組織が利用可能にしている他のフィードを選択して、カスタマイズ可能な "マイフィード" を簡単に閲覧できます。 [詳しくはこちらをご覧ください](/microsoft-365/admin/manage/manage-industry-news?preserve-view=true&view=o365-worldwide)。

- **プライバシーとセキュリティ**

  - ポリシー構成のサイトの TLS トークンバインドをサポートしています。 TLS トークンのバインドは、トークンの盗用攻撃を防ぐために、最初に設定されたデバイス以外のデバイスから cookie が再利用されないようにします。 TLS トークンバインドを使用するには、 [AllowTokenBindingForUrls](./microsoft-edge-policies.md#allowtokenbindingforurls) ポリシーを設定する必要があります。また、リストに記載されているサイトがこの機能をサポートしている必要があります。

- **PDF ファイルで強調表示のキーボードサポート**。 ユーザーは、キーボードのキーを使用して、PDF のテキストを強調表示できます。

- **印刷**

  - 両面印刷時にどのように紙を綴じるか選択します。 ユーザーが両面印刷するときに、用紙の長辺綴じか短辺綴じにするかを選択できます。
  - エンタープライズの印刷ラスター化モードを選択します。 Windows のポストスクリプトプリンター以外に Microsoft Edge をプリントする方法を制御します。 PostScript に対応していないプリンターの印刷ジョブが正しく印刷されるようにラスター化する必要がある場合があります。 印刷オプションには "Full (フル)" と "Fast (高速)"が表示されます。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

10個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://www.microsoft.com/edge/business/download)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [ConfigureFriendlyURLFormat](./microsoft-edge-policies.md#configurefriendlyurlformat) -Microsoft Edge からコピーした URLの既定の貼り付け書式を構成し、他の形式をユーザーが利用できるようにするかどうかを決定します。
- [EdgeShoppingAssistantEnabled](./microsoft-edge-policies.md#edgeshoppingassistantenabled)-Microsoft Edge のショッピングが有効になりました。 
- [HideInternetExplorerRedirectUXForIncompatibleSitesEnabled](./microsoft-edge-policies.md#hideinternetexplorerredirectuxforincompatiblesitesenabled) -Microsoft Edge のワンタイムリダイレクトダイアログとバナーを非表示にします。
- [KioskAddressBarEditingEnabled](./microsoft-edge-policies.md#kioskaddressbareditingenabled) -キオスクモードのパブリックブラウザーのエクスペリエンスを編集するアドレスバーを構成します。
- [KioskDeleteDownloadsOnExit](./microsoft-edge-policies.md#kioskdeletedownloadsonexit) -Microsoft Edge が閉じたときに、キオスク セッションの一部としてダウンロードされたファイルを削除する
- [PasswordRevealEnabled](./microsoft-edge-policies.md#passwordrevealenabled) -[パスワードの表示] ボタンを有効にします。
- [RedirectSitesFromInternetExplorerPreventBHOInstall](./microsoft-edge-policies.md#redirectsitesfrominternetexplorerpreventbhoinstall) -Internet Explorer から Microsoft Edge に互換性のないサイトをリダイレクトするために BHO をインストールできないようにします。
- [RedirectSitesFromInternetExplorerRedirectMode](./microsoft-edge-policies.md#redirectsitesfrominternetexplorerredirectmode) -Internet Explorer から Microsoft Edge に互換性のないサイトをリダイレクトします。
- [SpeechRecognitionEnabled](./microsoft-edge-policies.md#speechrecognitionenabled) -音声認識を構成します。
- [WebCaptureEnabled](./microsoft-edge-policies.md#webcaptureenabled) -Microsoft Edge で web キャプチャ機能を有効にします。

#### <a name="deprecated-policy"></a>廃止されたポリシー

[NewTabPageSetFeedType](./microsoft-edge-policies.md#newtabpagesetfeedtype) - Microsoft Edge の新規タブ ページのエクスペリエンスを設定する

#### <a name="obsoleted-policy"></a>非推奨ポリシー

[EnableDeprecatedWebPlatformFeatures](./microsoft-edge-policies.md#enabledeprecatedwebplatformfeatures) -廃止されたWebプラットフォームの機能を一定期間、再度有効にします。

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
<!-- major 86 -->
## <a name="version-86062211-september-9"></a>バージョン 86.0.622.11: 9 月 9 日

### <a name="feature-updates"></a>機能更新プログラム

* **Internet Explorer モード:**

   * ユーザーが Microsoft Edge ユーザー インターフェイス (UI) を使用して、Internet Explorer モードでサイトをテストできるようにします。 Microsoft Edge バージョン 86 以降、管理者はユーザーがテスト目的で、またはサイトがサイト一覧の XML に追加されるまでの臨時措置として Internet Explorer モードでタブを読み込むことができるよう、UI オプションを有効にできます。

* **ダウンロード マネージャーを使用して、ダウンロードをディスクから削除できます。** ユーザーは、ブラウザーを離れることなくダウンロードしたファイルをディスクから削除できるようになりました。 ダウンロード削除のこの新しい機能は、ダウンロード シェルフのコンテキスト メニューまたはダウンロード ページに存在します。

* **Microsoft Edge の以前のバージョンにロールバック。** ロールバック機能では、Microsoft Edge の最新バージョンに問題がある場合、管理者は Microsoft Edge を既知の正常なバージョンに戻すことができます。
[詳しくはこちらをご覧ください](edge-learnmore-rollback.md)。

* **エンタープライズ全体で、同期の有効化を既定で強制できます。**  管理者は既定で、[ForceSync](./microsoft-edge-policies.md#forcesync) ポリシーを使用して、Azure Active Directory (Azure AD) アカウントに対して同期を有効にできます。

* **PDF の更新情報:**

  * PDF ドキュメントの目次。 バージョン 86 以降、Microsoft Edge に PDF ドキュメント内をユーザーが簡単に移動できる目次のサポートが追加されました。
  * スモール フォーム ファクターの画面で、すべての PDF 機能にアクセス。 画面サイズが小さなデバイスでも、Microsoft Edge PDF リーダーのすべての機能にアクセスできます。
  * PDF ファイルで蛍光ペンのペン サポート。 この更新で、ユーザーはデジタル ペンを使用して、実際の蛍光ペンと紙と同様の方法で PDF ファイルでテキストを直接強調表示できます。
  * PDF のスクロールの改善。 長い PDF ドキュメント内を移動するときに、スムーズなスクロールを体験できるようになりました。

* **Windows 7、8、8.1 でのプロファイル の自動切り替え。** 現在 Windows 10 の Microsoft Edge で利用可能なプロフィールの自動切り替えは、ダウンレベルの Windows (Windows 7、8、8.1) に拡張されました。 詳細については、ブログ記事「[プロファイルの自動切り替え](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/)」を参照してください。

* **ユーザーが Microsoft Edge アドオン Web サイトで検索クエリを入力し始めると、自動完了の候補が表示されます。** 自動完了によって、ユーザーは文字列全体を入力せずに検索クエリを素早く完成できます。 ユーザーは正確なスペルを記憶する必要がなく、表示されるオプションから選ぶことができるので、これは便利な機能です。

* **HTML5 アプリケーション キャッシュ API の削除。**  Microsoft Edge バージョン 86 以降、Web ページのオフライン使用を可能にするレガシ アプリケーション キャッシュ API は Microsoft Edge から削除されます。 Web 開発者は、[WebDev ドキュメント](https://web.dev/appcache-removal/)で、アプリケーション キャッシュ API のサービス ワーカーへの置き換えに関する情報を確認する必要があります。  重要: Microsoft Edge バージョン 90 まで、サイトが非推奨のアプリケーション キャッシュ API を引き続き使用できるようにする [AppCache OriginTrial Token](https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673) を要求できます。

* **セキュリティ:**

  * セキュリティで保護された DNS (DNS over HTTPS) のサポート。  Microsoft Edge バージョン 86 以降、セキュリティ保護された DNS を制御する設定が、管理されていないデバイスで利用可能になりました。 ユーザーは管理されたデバイスでこれらの設定にアクセスできませんが、IT 管理者は [dnsoverhttpsmode](./microsoft-edge-policies.md#dnsoverhttpsmode) グラウンド ポリシーを使用して、セキュリティ保護された DNS を有効または無効にすることができます。


* **グループ ポリシーを使用して、新しいタブ ページ (NTP) にカスタム イメージを追加できます。** Microsoft Edge バージョン 86 以降、NTP で既定のイメージをユーザーが指定したイメージで置き換えるためのオプションを使用できます。 このイメージのプロパティを管理する機能も、グループ ポリシーによってサポートされています。

* **カスタマイズしたキーボード ショートカットを VS コードと一致させます。** Microsoft Edge の DevTools では、使用しているエディターや IDE に合わせて DevTools のキーボード ショートカットをカスタマイズできるようになりました。 (Microsoft Edge 84 で、VS コードに対して DevTools のキーボードショートカットを一致させる機能を追加しました)。

* **ダウンレベルの Windows と macOS で [MetricsReportingEnabled]( /DeployEdge/microsoft-edge-policies#metricsreportingenabled) と [SendSiteInformationToImproveServices]( /DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) ポリシーを置き換えます。** これらのポリシーは Microsoft Edge バージョン 86 では非推奨で、Microsoft Edge バージョン 89 で廃止されます。<br>
これらのポリシーは、Windows 10 では[利用統計情報の許可](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)に、その他すべてのプラットフォームでは新しい [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) ポリシーに置き換えられます。 これにより、ユーザーは Windows 7、8、8.1、macOS で、Microsoft に送信される診断データを管理できるようになります。

* **SameSite=既定で緩い Cookie**。 Web セキュリティとプライバシーを向上させるために、Cookie は、既定では、[SameSite=Lax](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite) 処理に設定されます。 つまり、Cookie はファーストパーティのコンテキストでのみ送信され、サードパーティに送信される要求では省略されます。 この変更により、サードパーティのリソースが正しく機能するために Cookie を必要とする Web サイトに互換性の影響が生じる可能性があります。 このような Cookie を許可するために、Web 開発者は、Cookie の設定時に明示的な `SameSite=none` および `Secure` 属性を追加することにより、サードパーティのコンテキストから設定および送信する必要がある Cookie にマークを付けることができます。 特定のサイトをこの変更から除外することを希望する企業は、[LegacySameSiteCookieBehaviorEnabledForDomainList](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabledfordomainlist) ポリシーを使用してこれを行うか、[LegacySameSiteCookieBehaviorEnabled](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabled) ポリシーを使用してすべてのサイトにわたる変更をオプトアウトできます。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

19 個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [CollectionsServicesAndExportsBlockList](./microsoft-edge-policies.md#collectionsservicesandexportsblocklist) - 指定したサービスの一覧へのアクセスをブロックし、コレクション内のターゲットをエクスポートします。
- [DefaultSensorsSetting](./microsoft-edge-policies.md#defaultsensorssetting) - 既定のセンサーの設定。
- [DefaultSerialGuardSetting](./microsoft-edge-policies.md#defaultserialguardsetting) - シリアル API の使用を制御します。
- [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) - ブラウザーの使用状況に関する必須およびオプションの診断データを送信します。
- [EnterpriseModeSiteListManagerAllowed](./microsoft-edge-policies.md#enterprisemodesitelistmanagerallowed) - Enterprise Mode Site List Manager ツールへのアクセスを許可します。
- [ForceSync](./microsoft-edge-policies.md#forcesync) - ブラウザーのデータを強制的に同期し、同期の同意プロンプトを表示しません。
- [InsecureFormsWarningsEnabled](./microsoft-edge-policies.md#insecureformswarningsenabled) - セキュリティで保護されていないフォームに対する警告を有効にします。
- [InternetExplorerIntegrationTestingAllowed](./microsoft-edge-policies.md#internetexplorerintegrationtestingallowed) - Internet Explorer モードテストを許可します。
- [SpotlightExperiencesAndRecommendationsEnabled](./microsoft-edge-policies.md#spotlightexperiencesandrecommendationsenabled) - カスタマイズされた背景画像およびテキスト、提案、通知、Microsoft サービスのヒントをユーザーが受信できるかどうかを選択します。
- [NewTabPageAllowedBackgroundTypes](./microsoft-edge-policies.md#newtabpageallowedbackgroundtypes) - 新しいタブ ページ レイアウトに使用できる背景の種類を構成します。
- [SaveCookiesOnExit](./microsoft-edge-policies.md#savecookiesonexit) - Microsoft Edge の終了時に Cookie を保存します。
- [SensorsAllowedForUrls](./microsoft-edge-policies.md#sensorsallowedforurls) - 特定のサイトのセンサーへのアクセスを許可します。
- [SensorsBlockedForUrls](./microsoft-edge-policies.md#sensorsblockedforurls) - 特定のサイトのセンサーへのアクセスをブロックします。
- [SerialAskForUrls](./microsoft-edge-policies.md#serialaskforurls) - 特定のサイトのシリアル API を許可します。
- [SerialBlockedForUrls](./microsoft-edge-policies.md#serialblockedforurls) - 特定のサイトのシリアル API をブロックします。
- [URLBlocklist](./microsoft-edge-policies.md#urlblocklist) - URL の一覧へのアクセスをブロックします。
- [URLAllowlist](./microsoft-edge-policies.md#urlallowlist) - 許可されている URL の一覧を定義します。
- [UserAgentClientHintsEnabled](./microsoft-edge-policies.md#useragentclienthintsenabled) - ユーザー エージェント クライアント ヒント機能を有効にします。
- [UserDataSnapshotRetentionLimit](./microsoft-edge-policies.md#userdatasnapshotretentionlimit) - 緊急ロールバックの場合に使用されるユーザー データのスナップショット数を制限します。

#### <a name="deprecated-policies"></a>廃止されたポリシー

- [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) - 使用状況とクラッシュ関連のデータレポートを有効にします。
- [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) - Microsoft サービスを改善するためにサイト情報を送信します。

#### <a name="obsoleted-policy"></a>非推奨ポリシー

[TLS13HardeningForLocalAnchorsEnabled](./microsoft-edge-policies.md#tls13hardeningforlocalanchorsenabled) - ローカル トラスト アンカーの TLS 1.3 セキュリティ機能を有効にします。

#### <a name="policy-caption-changed"></a>変更されたポリシーのキャプション

[NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - ネイティブ ウィンドウ オクルージョンを有効にします。

#### <a name="policy-description-changed"></a>変更されたポリシーの説明

- [AdsSettingForIntrusiveAdsSites](./microsoft-edge-policies.md#adssettingforintrusiveadssites)
- [AllowTokenBindingForUrls](./microsoft-edge-policies.md#allowtokenbindingforurls)
- [AmbientAuthenticationInPrivateModesEnabled](./microsoft-edge-policies.md#ambientauthenticationinprivatemodesenabled)
- [ApplicationGuardContainerProxy](./microsoft-edge-policies.md#applicationguardcontainerproxy)
- [AutoImportAtFirstRun](./microsoft-edge-policies.md#autoimportatfirstrun)
- [AutoOpenFileTypes](./microsoft-edge-policies.md#autoopenfiletypes)
- [BrowserSignin](./microsoft-edge-policies.md#browsersignin)
- [ClearBrowsingDataOnExit](./microsoft-edge-policies.md#clearbrowsingdataonexit) 
- [ClickOnceEnabled](./microsoft-edge-policies.md#clickonceenabled)
- [CommandLineFlagSecurityWarningsEnabled](./microsoft-edge-policies.md#commandlineflagsecuritywarningsenabled)
- [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin)
- [ConfigureShare](./microsoft-edge-policies.md#configureshare)
- [CookiesAllowedForUrls](./microsoft-edge-policies.md#cookiesallowedforurls)
- [CustomHelpLink](./microsoft-edge-policies.md#customhelplink)
- [DefaultCookiesSetting](./microsoft-edge-policies.md#defaultcookiessetting)
- [DefaultGeolocationSetting](./microsoft-edge-policies.md#defaultgeolocationsetting)
- [DefaultImagesSetting](./microsoft-edge-policies.md#defaultimagessetting)
- [Defaul/Securecontentsetting](./microsoft-edge-policies.md#defaultinsecurecontentsetting)
- [DefaultJavaScriptSetting](./microsoft-edge-policies.md#defaultjavascriptsetting)
- [DefaultNotificationsSetting](./microsoft-edge-policies.md#defaultnotificationssetting)
- [DefaultPluginsSetting](./microsoft-edge-policies.md#defaultpluginssetting)
- [DefaultPopupsSetting](./microsoft-edge-policies.md#defaultpopupssetting)
- [DefaultSearchProviderEnabled](./microsoft-edge-policies.md#defaultsearchproviderenabled)
- [DefaultWebBluetoothGuardSetting](./microsoft-edge-policies.md#defaultwebbluetoothguardsetting)
- [DefaultWebUsbGuardSetting](./microsoft-edge-policies.md#defaultwebusbguardsetting)
- [DelayNavigationsForInitialSiteListDownload](./microsoft-edge-policies.md#delaynavigationsforinitialsitelistdownload)
- [DeveloperToolsAvailability](./microsoft-edge-policies.md#developertoolsavailability)
- [EnableSha1ForLocalAnchors](./microsoft-edge-policies.md#enablesha1forlocalanchors)
- [DownloadRestrictions](./microsoft-edge-policies.md#downloadrestrictions)
- [EnableDeprecatedWebPlatformFeatures](./microsoft-edge-policies.md#enabledeprecatedwebplatformfeatures)
- [WinHttpProxyResolverEnabled](./microsoft-edge-policies.md#winhttpproxyresolverenabled)
- [ExperimentationAndConfigurationServiceControl](./microsoft-edge-policies.md#experimentationandconfigurationservicecontrol)
- [ExternalProtocolDialogShowAlwaysOpenCheckbox](./microsoft-edge-policies.md#externalprotocoldialogshowalwaysopencheckbox)
- [ExtensionInstallForcelist](./microsoft-edge-policies.md#extensioninstallforcelist)
- [ForceBingSafeSearch](./microsoft-edge-policies.md#forcebingsafesearch)
- [ForceYouTubeRestrict](./microsoft-edge-policies.md#forceyoutuberestrict)
- [HomepageIsNewTabPage](./microsoft-edge-policies.md#homepageisnewtabpage)
- [HomepageLocation](./microsoft-edge-policies.md#homepagelocation)
- [InPrivateModeAvailability](./microsoft-edge-policies.md#inprivatemodeavailability)
- [InternetExplorerIntegrationEnhancedHangDetection](./microsoft-edge-policies.md#internetexplorerintegrationenhancedhangdetection)
- [InternetExplorerIntegrationLevel](./microsoft-edge-policies.md#internetexplorerintegrationlevel)
- [InternetExplorerIntegrationSiteRedirect](./microsoft-edge-policies.md#internetexplorerintegrationsiteredirect)
- [LegacySameSiteCookieBehaviorEnabled](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabled)
- [NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled)
- [NavigationDelayForInitialSiteListDownloadTimeout](./microsoft-edge-policies.md#navigationdelayforinitialsitelistdownloadtimeout)
- [NetworkPredictionOptions](./microsoft-edge-policies.md#networkpredictionoptions)
- [NewTabPageLocation](./microsoft-edge-policies.md#newtabpagelocation)
- [NewTabPageSearchBox](./microsoft-edge-policies.md#newtabpagesearchbox)
- [NewTabPageSetFeedType](./microsoft-edge-policies.md#newtabpagesetfeedtype)
- [NonRemovableProfileEnabled](./microsoft-edge-policies.md#nonremovableprofileenabled)
- [PasswordProtectionWarningTrigger](./microsoft-edge-policies.md#passwordprotectionwarningtrigger)
- [PasswordProtectionLoginURLs](./microsoft-edge-policies.md#passwordprotectionloginurls)
- [PasswordProtectionChangePasswordURL](./microsoft-edge-policies.md#passwordprotectionchangepasswordurl)
- [PluginsAllowedForUrls](./microsoft-edge-policies.md#pluginsallowedforurls)
- [PluginsBlockedForUrls](./microsoft-edge-policies.md#pluginsblockedforurls)
- [PreventSmartScreenPromptOverride](./microsoft-edge-policies.md#preventsmartscreenpromptoverride)
- [PreventSmartScreenPromptOverrideForFiles](./microsoft-edge-policies.md#preventsmartscreenpromptoverrideforfiles)
- [ProxyMode](./microsoft-edge-policies.md#proxymode)
- [RegisteredProtocolHandlers](./microsoft-edge-policies.md#registeredprotocolhandlers)
- [RelaunchNotification](./microsoft-edge-policies.md#relaunchnotification)
- [RestoreOnStartup](./microsoft-edge-policies.md#restoreonstartup)
- [RestoreOnStartupURLs](./microsoft-edge-policies.md#restoreonstartupurls)
- [RestrictSigninToPattern](./microsoft-edge-policies.md#restrictsignintopattern)
- [SSLVersionMin](./microsoft-edge-policies.md#sslversionmin)
- [SmartScreenAllowListDomains](./microsoft-edge-policies.md#smartscreenallowlistdomains)
- [SmartScreenEnabled](./microsoft-edge-policies.md#smartscreenenabled)
- [SmartScreenForTrustedDownloadsEnabled](./microsoft-edge-policies.md#smartscreenfortrusteddownloadsenabled)
- [SmartScreenPuaEnabled](./microsoft-edge-policies.md#smartscreenpuaenabled)
- [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled)
- [TrackingPrevention](./microsoft-edge-policies.md#trackingprevention)
- [WebRtcLocalhostIpHandling](./microsoft-edge-policies.md#webrtclocalhostiphandling)

<!-- end 86 -->

## <a name="version-85056441-august-25"></a>バージョン 85.0.564.41: 8 月 25 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-85056440-august-21"></a>バージョン 85.0.564.40: 8 月 21 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-85056436-august-17"></a>バージョン 85.0.564.36: 8 月 17 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-85056430-august-10"></a>バージョン 85.0.564.30: 8 月 10 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-85056423-august-3"></a>バージョン 85.0.564.23: 8 月 3 日

さまざまなバグとパフォーマンスの問題を修正しました。
<!-- major 85 -->
## <a name="version-85056418-july-28"></a>バージョン 85.0.564.18: 7 月28 日

### <a name="feature-updates"></a>機能更新プログラム

- **[お気に入り]と[設定]のオンプレミス同期**。 クラウド同期を必要とせずに、自分の環境内の Active Directory プロファイル間でブラウザーのお気に入りと設定を同期できます。

- **確認メッセージを表示せずに、信頼するサイトとアプリの組み合わせを起動するための Microsoft Edge グループポリシーサポート。** 管理者が、確認メッセージを表示せずに、信頼されているサイトとアプリの組み合わせ を追加できるようにしたグループポリシーのサポートが追加されました。 これにより、管理者は、アプリプロトコルを含む URL に移動するときに、エンドユーザーが確認メッセージを表示しないようにするために、信頼されたプロトコル/オリジンの組み合わせ (Microsoft 365 アプリなど) を構成できます。

- **PDFの蛍光ペンツール** このツールをPDF 用のツールバーに追加して、重要なテキストを簡単に強調表示することができます。

- **ストレージアクセス API が使用できます** Storage Access APIは、ブラウザーの現在の構成によってブロックされる可能性があるストレージをユーザーが直接許可できるようにするために、サードパーティのコンテキストでファーストパーティ ストレージにアクセスできるようにします。 詳細については、「[記憶域アクセスAPI](https://www.chromestatus.com/feature/5612590694662144)」を参照してください。

- **[OneNote に送信] は、Microsoft Edge コレクションで使用できます**。 コレクションに収集した情報を OneNote に送信できるようになりました。これで、大きなプロジェクトに情報を提供して、他のユーザーと協力することができます。 さらに重要なのは、Microsoft Edge 85 では、Microsoftアカウント と Azure Active Directory の両方について、*Office for Mac* 製品 (Word、Excel、OneNote) にコンテンツを送信できることです。

- **DevToolsの更新** 次の更新プログラムの詳細については、 [DevTools の新機能 (Microsoft Edge 85)](/microsoft-edge/devtools-guide-chromium/whats-new/2020/06/devtools)を参照してください。

   - Microsoft Edge の DevTools は Surface Duo エミュレーションをサポートしています。 Microsoft Edge の DevTools を使用して Surface Duo をエミュレートすることができます。これにより、ユーザーのweb コンテンツの表示をデュアルスクリーンデバイスでテストできます。 このテストを DevTools で有効にするには、Windows の場合はCtrl+Shift+Mを押しながら、Device Modeに入るか、macOSの場合は、 Command + Shift + M キーを押して、デバイスのドロップダウンリストから Surface Duo を選択します。
   - Microsoft Edge DevTools を使用すると、キーボードショートカットを VS コードと一致させることができます。 Microsoft Edge の DevTools では、使用しているエディターや IDE に合わせて DevTools のキーボードショートカットをカスタマイズできます。 Microsoft Edge 85 で、VS コードに対して DevTools のキーボードショートカットを一致させる機能を追加します。 この変更は、VS コードと DevTools の生産性向上に役立ちます。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

13 個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [AutoLaunchProtocolsFromOrigins](./microsoft-edge-policies.md#autolaunchprotocolsfromorigins) -ユーザーにプロンプ​​トを表示せずに、リストされたオリジンから外部アプリケーションを起動できるプロトコルのリストを定義します。
- [AutoOpenAllowedForURLs](./microsoft-edge-policies.md#autoopenallowedforurls) -AutoOpenFileTypes を適用できるURL。
- [AutoOpenFileTypes](./microsoft-edge-policies.md#autoopenfiletypes) -ダウンロード時に自動的に開く必要があるファイルの種類の一覧。
- [DefaultSearchProviderContextMenuAccessAllowed](./microsoft-edge-policies.md#defaultsearchprovidercontextmenuaccessallowed) -既定の検索プロバイダーコンテキストメニューの検索アクセスを許可します。
- [EnableSha1ForLocalAnchors](./microsoft-edge-policies.md#enablesha1forlocalanchors)-ローカルトラストアンカーによって発行されたときに SHA-1 を使用して署名された証明書を許可します。
- [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](./microsoft-edge-policies.md#exemptdomainfiletypepairsfromfiletypedownloadwarnings)-ドメイン上の指定したファイルの種類についての警告に基づいて、ダウンロードファイルの種類の拡張子を無効にします。
- [IntensiveWakeUpThrottlingEnabled](./microsoft-edge-policies.md#intensivewakeupthrottlingenabled)-IntensiveWakeUpThrottling 機能を制御します。
- [NewTabPagePrerenderEnabled](./microsoft-edge-policies.md#newtabpageprerenderenabled)-新しいタブページのプリロードを有効にして、表示を高速化します。
- [NewTabPageSearchBox](./microsoft-edge-policies.md#newtabpagesearchbox) - 新しいタブ ページ検索ボックスの機能を構成します。
- [PasswordMonitorAllowed](./microsoft-edge-policies.md#passwordmonitorallowed) - パスワードが安全でないことが判明した場合にユーザーに警告することを許可します。
- [RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled)-Microsoft Edgeプロファイルデータ のローミングコピーの使用を有効にします。
- [RoamingProfileLocation](./microsoft-edge-policies.md#roamingprofilelocation)-移動プロファイルディレクトリを設定します。
- [TLSCipherSuiteDenyList](./microsoft-edge-policies.md#tlsciphersuitedenylist)-TLS 暗号スイートを無効に指定します。

#### <a name="obsoleted-policies"></a>不使用のポリシー

- [EnableDomainActionsDownload](./microsoft-edge-policies.md#enabledomainactionsdownload) - Microsoft からのドメイン アクションのダウンロードを有効にします。
- [WebComponentsV0Enabled](./microsoft-edge-policies.md#webcomponentsv0enabled) - Web コンポーネント v0 API ユニット M84 を再有効化する。
- [WebDriverOverridesIncompatiblePolicies](./microsoft-edge-policies.md#webdriveroverridesincompatiblepolicies) - WebDriverに 互換性のないポリシーのオーバーライドを許可します。

<!--- END ---->

## <a name="version-84052235-july-9"></a>Version 84.0.522.35: 7月9日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-84052228-june-26"></a>Version 84.0.522.28: 6月26日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-84052226-june-24"></a>Version 84.0.522.26: 6月24日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-84052220-june-15"></a>Version 84.0.522.20: 6月15日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-84052215-june-8"></a>Version 84.0.522.15: 6月8日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-84052211-june-2"></a>Version 84.0.522.11: 6月2日

### <a name="feature-updates"></a>機能更新プログラム

- このバージョンの Microsoft Edge では、Internet Explorer モードでのサイト一覧のダウンロード時間が改善されました。  キャッシュされたサイト リストがない場合、Internet Explorer モードのサイト一覧のダウンロードのダウンロード遅延が0秒に削減されました （以前の60秒待ちから短縮）。 また、サイト一覧がダウンロードされるまで、Internet Explorer モードのホームページ ナビゲーションを遅延する必要がある場合のために、グループ ポリシーのサポートも追加しました。 詳細については、「[DelayNavigationsForInitialSiteListDownload](./microsoft-edge-policies.md#delaynavigationsforinitialsitelistdownload)」 を参照してください。

- Microsoft Edge では、Windows 10 で "管理者として実行" する場合に、ユーザーがブラウザーにサインインできるようになりました。 これにより、Windows サーバーで Microsoft Edge を実行しているユーザー、またはリモートデスクトップやサンドボックスのシナリオでの使用に役立ちます。

- Microsoft Edge は、全画面表示モードでフル マウス サポートが提供されるようになりました。 これで、全画面表示モードを終了しなくても、マウスを使用してタブ、アドレス バーなどの項目にアクセスできます。

- オンライン購入を改善します。 保存したデビット カードやクレジット カードにカスタム ニックネームを追加します。 これで、オンライン購入時に、クレジット カードを区別して差別化できるようになりました。 デビット カードやクレジット eカードにニックネームを付けることで、オートフィルを使用して支払い方法を選択する際に正しいカードを選ぶことができます。

- TLS/1.0 および TLS/1.1 は既定では無効になっています。 影響を受けるサイトを検出するには、[*edge://flags/#display-レガシ-tls 警告*] フラグを設定すると、Microsoft Edge で、レガシー TLS プロトコルを必要とするページを読み込むときに、ブロック不可の "セキュリティで保護されていない" という通知が表示されます。 [SSLVersionMin](./microsoft-edge-policies.md#sslversionmin) ポリシーにより、TLS/1.0 と TLS/1.1 を再有効化することが可能になります。 このポリシーは、Microsoft Edge バージョン88以上で利用可能になります。 詳細については、「[Microsoft Edge 向けのサイトの互換性に影響する変更点](/microsoft-edge/web-platform/site-impacting-changes)」 を参照してください。

- コレクションの改善

  - ノート機能が追加され、コレクション内のアイテムにメモやコメントを追加することができます。 メモはグループ化されるため、コレクションの中でアイテムを並べ替えても、アイテムにくっついたままです。 この新機能を試すには、アイテムを右クリックし、[メモの追加] を選択します。
  - コレクション内にあるメモの背景色を変更できます。 [色分け] を使用すると、情報を整理して生産性を高めることが可能です。
  - パフォーマンスが大幅に改善されました。これにより、以前のバージョンの Microsoft Edge よりも短時間で Excel にコレクションをエクスポートできるようになりました。

- その他の Microsoft Edge API サポートは、次のとおりです。

  - ストレージ アクセス API です。 この API は、ブラウザーの現在の構成によってブロックされる可能性があるストレージをユーザーが直接使用できるようにする場合に、サードパーティのコンテキストでファーストパーティ ストレージにアクセスできるようにします。

    プライバシーは、ユーザーにとっての重要性がますます高まっているため、より厳格なブラウザの規定値とサードパーティ製ストレージへのアクセスをすべてブロックするようなユーザー オプトイン設定の要求は、ますます一般的になっています。 これらの設定は、プライバシーを改善し、不明な、または信頼されていないパーテによるの不要なアクセスをブロックするのに役立ちますが、ユーザーが表示したいと思うコンテンツ (たとえば、ソーシャル メディアや埋め込まれたメディア コンテンツ) へのアクセスをブロックするなど、不要な副作用をもたらす可能性があります。

  - ネイティブファイルシステム API は、この API を使用してファイルまたはフォルダーを編集するためのアクセス許可をサイトに付与できるものです。

- PDF の改善点は、次のとおりです。

  - PDF 用の音声読み上げを行うことで、ユーザーは、重要なタスクを実行しながら PDF コンテンツを聞くことができます。 また、視聴覚学習者がコンテンツの閲覧に集中するのに役立つため、学習しやすくなります。
  - PDF ファイル編集機能が改善されました。 PDF を編集するたびにコピーを保存するのではなく、編集内容を PDF に保存してファイルに戻すことができるようになりました。

- Microsoft Edge では、イマーシブ リーダーの翻訳が可能になります。 ユーザーがイマーシブ リーダー ビューを開くと、ページを目的の言語に翻訳するためのオプションが表示されます。

- DevTools では、キーボード ショートカットをカスタマイズしてエディターや IDE に合わせることができます。これには、VS コードが含まれています。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

5 個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [AppCacheForceEnabled](./microsoft-edge-policies.md#appcacheforceenabled) - 既定でオフになっている場合でも、App Cache 機能を再度有効にすることを許可します。
- [ApplicationGuardContainerProxy](./microsoft-edge-policies.md#applicationguardcontainerproxy) - Application Guard コンテナー プロキシです。
- [DelayNavigationsForInitialSiteListDownload](./microsoft-edge-policies.md#delaynavigationsforinitialsitelistdownload) - タブ ナビゲーションの前にエンタープライズ モード サイト一覧が使用できるようにします。
- [NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - ネイティブ ウィンドウを非表示にします。
- [NavigationDelayForInitialSiteListDownloadTimeout](./microsoft-edge-policies.md#navigationdelayforinitialsitelistdownloadtimeout) - エンタープライズ モード サイト一覧のタブ ナビゲーションの遅延時間を設定します。

#### <a name="deprecated-policies"></a>廃止されたポリシー

- [AllowSyncXHRInPageDismissal](./microsoft-edge-policies.md#allowsyncxhrinpagedismissal) - ページが同期 XHR 要求をページの解除中に送信できるようにします。
- [BuiltinCertificateVerifierEnabled](./microsoft-edge-policies.md#builtincertificateverifierenabled) - 組み込みの証明書検証機能を使用してサーバー証明書を検証するかどうかを決定します。
- [StricterMixedContentTreatmentEnabled](./microsoft-edge-policies.md#strictermixedcontenttreatmentenabled) - 混合コンテンツに対してより厳密な処理を有効にします。

#### <a name="obsoleted-policy"></a>非推奨ポリシー

[ForceNetworkInProcess](./microsoft-edge-policies.md#forcenetworkinprocess) - ブラウザー プロセスでネットワーク コードを強制的に実行します。

<!-- end 84 -->

## <a name="version-83047844-june-1"></a>Version 83.0.478.44: 6月1日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-83047837-may-20"></a>Version 83.0.478.37: 5月20日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-83047833-may-15"></a>Version 83.0.478.33: 5月15日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-83047828-may-7"></a>バージョン 83.0.478.28: 5 月 7 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-83047825-may-4"></a>バージョン 83.0.478.25: 5 月 4 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-83047818-april-27"></a>バージョン 83.0.478.18: 4 月 27 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-83047813-april-22"></a>バージョン 83.0.478.13: 4 月 22 日

### <a name="feature-updates"></a>機能更新プログラム

- Microsoft Defender SmartScreen の改善: 読み込み時にリダイレクトする悪意のあるサイトからの保護が強化され、悪意のあるサイトを Microsoft Defender SmartScreen の安全ページに完全に置き換えるトップレベルのフレーム ブロックなど、Microsoft Defender SmartScreen サービスにいくつかの改良を加えました。 トップレベルのフレーム ブロックにより、悪意のあるサイトからの音声やその他のメディアの再生が防止され、より簡単かつわかりやすくなります。

- ユーザーのフィードバックに応えて、ユーザーはブラウザーが閉じたときに特定の Cookie を自動的に消去しないように設定できます。 このオプションは、ユーザーのサインアウトは望まないが、ブラウザーを閉じたときに他のすべての Cookie をクリアしたいサイトがある場合に役立ちます。 この機能を使用するには、*edge://settings/clearBrowsingDataOnClose* に移動して、[Cookie およびその他のサイト データ] トグルを有効にします。

- 自動プロファイル切り替えが利用可能になり、プロファイル間でより簡単に作業内容にアクセスできるようになりました。 職場で複数のプロファイルを使用している場合は、個人用プロファイルを使用しているときに、職場または学校のアカウントから認証を必要とするサイトに移動して、プロファイルを確認できます。 変化を検出すると、仕事用プロファイルに切り替えて、認証なしでそのサイトにアクセスするよう求めるプロンプトが表示されます。 切り替えたい仕事用プロファイルを選択すると、仕事用プロファイルで Web サイトが開きます。 このプロファイル切り替え機能により、仕事用データと個人データの分離が可能となり、作業コンテンツに簡単にアクセスできるようになります。 この機能でプロファイルを切り替えるように求められないようにする場合は、[今後表示しない] オプションを選択すると、邪魔になりません。

- コレクション機能の改善:
  - ドラッグ アンド ドロップを使用して、コレクションを開かずにコレクションにアイテムを追加できます。 ドラッグ アンド ドロップ中に、コレクション リストでアイテムを配置する場所を選択することもできます。
  - 一度に 1 つのアイテムを追加する代わりに、コレクションに複数のアイテムを追加できます。 複数のアイテムを追加するには、アイテムを選択して、コレクションにドラッグします。 または、アイテムを選択して右クリックし、アイテムを配置するコレクションを選択することもできます。

- Microsoft Edge ウィンドウのすべてのタブを個別に追加せず、新しいコレクションに追加できます。 すべてのタブを追加するには、任意のタブを右クリックし、[すべてのタブを新しいコレクションに追加] を選択します。

- 拡張機能の同期が利用可能になりました。 すべてのデバイスで拡張機能を同期できるようになりました。 Microsoft Store と Chrome ウェブストアの両方から入手した拡張機能が Microsoft Edge と同期します。 この機能を使用するには: メニュー バーの省略記号 (**…**) をクリックし、[**設定**] を選択します。 [プロファイル] で、[**同期**] をクリックして、同期オプションを表示します。 **Profiles/Sync** で、トグルを使用して拡張機能を有効にします。 [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) グループ ポリシーを使用して、拡張機能の同期を無効にすることができます。

- ブロックされた安全でないダウンロードに関するダウンロード管理ページのメッセージを改善しました。

- イマーシブ リーダーの改善:
  - イマーシブ リーダーの品詞エクスペリエンスで副詞のサポートが追加されました。 イマーシブ リーダーで記事を読みながら、文法ツールを開き、品詞内の副詞をオンにして、ページ上のすべての副詞を強調表示します。
  - Web ページ上の任意のコンテンツを選択し、イマーシブ リーダーで開く機能が追加されました。 この機能により、ユーザーはすべての Web サイトでイマーシブ リーダーとすべての学習ツール (行フォーカスや 音声読み上げなど) を使用できます。

- Link doctor では、ユーザーが URL を誤って入力したときにホスト修正が行われ、検索クエリがユーザーに提供されます。 次に、例を示します。 <br>
ユーザーが "powerbi" を誤って "powerbbi".com と入力したとします。 Link doctor からは、修正案として "powerbi".com が提案され、ユーザーが別の違うサイトを探している場合も想定し "powerbbi" を検索するためのリンクが作成されます。

- ユーザーは、特定のサイトの外部プロトコルを起動するという設定を保存できます。 ユーザーは、[ExternalProtocolDialogShowAlwaysOpenCheckbox](/DeployEdge/microsoft-edge-policies#externalprotocoldialogshowalwaysopencheckbox) ポリシーを構成して、この機能を有効または無効にすることができます。

- ユーザーは、Microsoft Edge の **[設定]** から直接 Microsoft Edge を既定のブラウザーとして設定できます。 この機能により、ユーザーは、オペレーティング システムの設定を検索せずに、ブラウザー自体のコンテキスト内で既定のブラウザーを簡単に変更することができます。 この機能を使用するには、*edge://settings/defaultBrowser* に移動し、**[既定に設定]** をクリックします。

- 新しいリモート デバッグのサポートや UI の改善など、DevTools の機能もいくつか更新されています。 詳細については、「[DevTools の新着情報 (Microsoft Edge 83)](/microsoft-edge/devtools-guide-chromium/whats-new/2020/03/devtools)」 を参照してください。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

15 個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [AllowSurfGame](./microsoft-edge-policies.md#allowsurfgame) - ゲームのサーフィンを許可します。
- [AllowTokenBindingForUrls](./microsoft-edge-policies.md#allowtokenbindingforurls) - Microsoft Edge がトークンのバインドの確立を試行するサイトのリストを構成します。
- [BingAdsSuppression](./microsoft-edge-policies.md#bingadssuppression) - Bing 検索結果ですべての広告をブロックします。
- [BuiltinCertificateVerifierEnabled](./microsoft-edge-policies.md#builtincertificateverifierenabled) - 組み込みの証明書検証機能を使用してサーバー証明書を検証するかどうかを決定します。
- [ClearCachedImagesAndFilesOnExit](./microsoft-edge-policies.md#clearcachedimagesandfilesonexit) - Microsoft Edge を閉じるときに、キャッシュされた画像とファイルをクリアします。
- [ConfigureShare](./microsoft-edge-policies.md#configureshare) - 共有エクスペリエンスを構成します。
- [DeleteDataOnMigration](./microsoft-edge-policies.md#deletedataonmigration) - 移行時に古いブラウザー データを削除します。
- [DnsOverHttpsMode](./microsoft-edge-policies.md#dnsoverhttpsmode) - DNS over HTTPS モードを制御します。
- [DnsOverHttpsTemplates](./microsoft-edge-policies.md#dnsoverhttpstemplates) - 目的の DNS over HTTPS リゾルバーの URI テンプレートを指定します。
- [FamilySafetySettingsEnabled](./microsoft-edge-policies.md#familysafetysettingsenabled) - ユーザーがファミリー セーフティを設定できるようにします。
- [LocalProvidersEnabled](./microsoft-edge-policies.md#localprovidersenabled) - ローカル プロバイダーからのおすすめを許可します。
- [ScrollToTextFragmentEnabled](./microsoft-edge-policies.md#scrolltotextfragmentenabled) - URL フラグメントで指定されたテキストへのスクロールを有効にします。
- [ScreenCaptureAllowed](./microsoft-edge-policies.md#screencaptureallowed) - 画面キャプチャを許可または拒否します。
- [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) - 同期から除外される種類の一覧を構成します。
- [NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - ネイティブ ウィンドウを非表示にします。

#### <a name="deprecated-policy"></a>廃止されたポリシー

このリリースでは、次のポリシーが引き続き機能します。 これは、将来のリリースで「廃止」される予定です。

[EnableDomainActionsDownload](./microsoft-edge-policies.md#enabledomainactionsdownload) Microsoft からのドメイン アクションのダウンロードを有効にする

<!--  end 83 -->

## <a name="version-81041660-april-20"></a>バージョン 81.0.416.60: 4 月 20 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-81041658-april-17"></a>バージョン 81.0.416.58: 4 月 17 日

セキュリティ更新プログラム。

## <a name="version-81041650-april-10"></a>バージョン 81.0.416.50: 4 月 10 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-81041645-april-3"></a>バージョン 81.0.416.45: 4 月 3 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-81041641-march-30"></a>バージョン 81.0.416.41: 3 月 30 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-81041634-march-17"></a>バージョン 81.0.416.34: 3 月 17 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-81041631-march-12"></a>バージョン 81.0.416.31: 3 月 12 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-81041628-march-9"></a>バージョン 81.0.416.28: 3 月 9 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-81041620-february-28"></a>バージョン 81.0.416.20: 2 月 28 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-81041612-february-20"></a>バージョン 81.0.416.12: 2 月 20 日

### <a name="feature-updates"></a>機能更新プログラム

- コレクションが使用できるようになりました。 アドレス バーの横にある [コレクション] アイコンをクリックして開始できます。 これにより、[コレクション] ウィンドウが開き、コレクションを作成、編集、表示できます。 Microsoft は、Web 上で行った操作に基づいて、コレクションを設計しています。 買い物客に、旅行者に、教師に、学生に、コレクションが役立ちます。 [詳しくはこちらをご覧ください](https://blogs.windows.com/msedgedev/2019/12/09/improvements-collections-sync-microsoft-edge/#LuDPRDUDCgdgdOVt.97)。

- 整合性を維持するために、Microsoft Edge ツールバーから [コレクション] ボタンを削除 (ツールバーから非表示にする) できるようにします。

- オンプレミスの Active Directory アカウントの自動サインインは、有効になっている組織に対してのみ有効です。 ユーザーがオンプレミスの AD アカウントで既にサインインしている場合は、そのアカウントからサインアウトすることができます。 Microsoftアカウント または Azure AD アカウントの場合は、オペレーティング システムのプライマリ アカウントで自動的にサインインが行われます。 管理者は、ConfigureOnPremisesAccountAutoSignIn ポリシーを使用して、オンプレミス AD アカウントで自動サインインを有効にすることができます。

- Application Guard。 拡張機能のサポートがコンテナで利用可能になりました。

- ユーザーが Internet Explorer モードで開くように構成されているページに移動したときに Internet Explorer がインストールされていないことをユーザーに通知するメッセージが追加されました。

- Microsoft Edge DevTools の 3D ビュー ツールを更新して、z-index スタッキング コンテキストのデバッグに役立つ新機能を追加しました。 3D ビューには、色とスタックを使用した DOM (ドキュメント オブジェクト モデル) の奥行きが表示され、z-Index インデックス ビューは、ページのさまざまなスタッキング コンテキストを分離することができます。 [詳しくはこちらをご覧ください](https://blogs.windows.com/msedgedev/2020/01/23/debug-z-index-3d-view-edge-devtools/)。

- F12 開発ツールを 10 の新しい言語にローカライズしました。そのため、ブラウザーの他の部分で使用されている言語と一致します。 [詳しくはこちらをご覧ください](https://blogs.windows.com/msedgedev/2020/02/04/localizing-edge-devtools/)。

- ドルビー ビジョン再生のサポートが追加されました。 ドルビー ビジョン Windows 10 ビルド 17134 (April 2018 Update) では、ドルビー ビジョン コンテンツを表示できます。 [Netflix](https://help.netflix.com/en/node/42384) でドルビー ビジョン コンテンツを有効にする方法を参照してください。

- Microsoft Edge は、重複したお気に入りフォルダーを識別して削除し、同じ名前のフォルダーをマージできるようになりました。 ツールにアクセスするには、ブラウザーのツールバーのスターをクリックして、[重複したお気に入りを削除] を選択します。  変更を確認でき、お気に入りの更新はデバイス間で同期されます。

- ユーザーから、両方のウィンドウ フレームが暗いため、暗いテーマの通常のブラウジング ウィンドウと InPrivate ウィンドウを区別するのが難しい場合があるという意見が寄せられました。 右上隅の新しい青く塗りつぶされた InPrivate を示す丸記号により、ユーザーは、InPrivate ブラウズを行っていることを確認できます。

- 正しいブラウザー プロファイルで外部リンクを開きます。 外部アプリ用に開かれているリンクに対する規定プロファイルを選択し、*edge://settings/multiProfileSettings* から開きます。

- 以前に別なアカウントにサインインしたアカウントを使って、ブラウザー プロファイルにサインインするユーザーに通知する警告が追加されました。 これは、意図しないデータの結合を防ぐことができます。

- Microsoft アカウントに支払カード情報を保存している場合は、支払フォームに入力するとき、Microsoft Edge でそれらを使用できます。 Microsoft アカウントにおけるカード情報はデスクトップ デバイス間で同期され、二要素認証 (CVC コードとMicrosoft ID) の後、すべての詳細が Web サイトと共有されます。利便性を高めるために、認証中にカードのコピーをデバイスに安全に保存することを選択できます。

- 行フォーカスは、ユーザーが読み取る際にコンテンツの一部のみに注目できるように設計されています。 これにより、ページの残りの部分を暗くして、ユーザーは一度に 1 行、3 行、5 行に注目できるため、気を散らすことなく読むことができます。 ユーザーはタッチまたは方向キーを使用してスクロールすることができます。フォーカスはそれに応じて移動します。

- Microsoft Edge は、Windows プラットフォーム8.1以降で、Windows Speller と統合されました。 この統合により、より多くの言語辞書アクセスし、Windows カスタム辞書を使用できるため、より優れた言語サポートが提供されます。 OS 言語設定で言語が追加され、Microsoft Edge 設定で言語スペルチェックの切り替えが有効になっている場合、ユーザーがこれ以上の操作を行う必要はありません。

- Microsoft Edge を使用して PDF ドキュメントを開くと、ユーザーはハイライトの作成、色の変更、ハイライトの削除ができるようになります。 これにより、後でドキュメントの重要な部分を参照したり、コラボレーションしたりすることができます。

- Web 用に最適化された長い PDF ドキュメントを読み込む場合、ドキュメントの残りの部分が読み込まれてる間、ユーザーが表示しているページは、より速く、並行して読み込まれます。

- F9 キーを押すだけで、Web サイトのイマーシブ リーダーを簡単に起動できるようになりました。

- キーボード ショートカット (Ctrl + Shift + U) を使用して、音声で読み上げる機能を簡単に起動できるようになりました。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

12 個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [AmbientAuthenticationInPrivateModesEnabled](./microsoft-edge-policies.md#ambientauthenticationinprivatemodesenabled) - InPrivate およびゲスト プロファイルの環境認証を有効にします。 
- [AudioSandboxEnabled](./microsoft-edge-policies.md#audiosandboxenabled) - オーディオ サンドボックスの実行を許可します。
- [ForceLegacyDefaultReferrerPolicy](./microsoft-edge-policies.md#forcelegacydefaultreferrerpolicy) - no-referrer-when-downgrade の既定の参照元ポリシーを使用します。
- [GloballyScopeHTTPAuthCacheEnabled](./microsoft-edge-policies.md#globallyscopehttpauthcacheenabled) - グローバル スコープの HTTP 認証キャッシュを有効にします。
- [ImportExtensions](./microsoft-edge-policies.md#importextensions) - 拡張機能のインポートを許可します。
- [ImportCookies](./microsoft-edge-policies.md#importcookies) - Cookie のインポートを許可します。
- [ImportShortcuts](./microsoft-edge-policies.md#importshortcuts) - ショートカットのインポートを許可します。
- [InternetExplorerIntegrationSiteRedirect](./microsoft-edge-policies.md#internetexplorerintegrationsiteredirect) - Internet Explorer モード ページから起動した場合、未構成サイトへの「ページ内」ナビゲーションの動作を指定します。
- [OmniboxMSBProviderEnabled](./microsoft-edge-policies.md) - Omnibox で Microsoft Search for Business プロバイダーを有効にします。
- [StricterMixedContentTreatmentEnabled](./microsoft-edge-policies.md#strictermixedcontenttreatmentenabled) - 混合コンテンツに対してより厳密な処理を有効にします。
- [TLS13HardeningForLocalAnchorsEnabled](./microsoft-edge-policies.md#tls13hardeningforlocalanchorsenabled) - ローカル トラスト アンカーの TLS 1.3 セキュリティ機能を有効にします。
- [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin) - Azure AD ドメイン アカウントがない場合、Active Directory ドメイン アカウントで自動サインインを構成します。

#### <a name="deprecated-policies"></a>廃止されたポリシー

このリリースでは、次のポリシーが引き続き機能します。 これらは、将来のリリースで「廃止」される予定です。

- [WebComponentsV0Enabled](./microsoft-edge-policies.md#webcomponentsv0enabled) - M84 まで Web コンポーネント v0 API を再度有効にします。
- [WebDriverOverridesIncompatiblePolicies](./microsoft-edge-policies.md#webdriveroverridesincompatiblepolicies) - WebDriverに 互換性のないオーバーライドを許可します。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)