---
title: Beta チャネルに関する Microsoft Edge のリリース ノート
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 01/15/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Beta チャネルに関する Microsoft Edge のリリース ノート
ms.openlocfilehash: 99ec3764d433906dcf45e851c7bc62d4ec2483fa
ms.sourcegitcommit: 3bafa63c17f01fcec60d6297474a6a391034a8be
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271206"
---
# Microsoft Edge Beta チャネルのリリースノート

これらのリリース ノートでは、Microsoft Edge Beta チャネルに含まれている新機能とセキュリティ以外の更新プログラムに関する情報を提供します。 これらのリリース ノートのアーカイブ バージョンは、[こちら](microsoft-edge-relnote-archive-beta-channel.md)から入手できます。

## バージョン 88.0.705.45: 1 月 15 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン 88.0.705.41: 1 月 11 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン 88.0.705.29: 12 月 21 日

さまざまなバグとパフォーマンスの問題を修正しました。

<!-- begin major 88 -->
## バージョン 88.0.705.18: 12 月 9 日

### 機能の更新プログラム

- **非推奨:**

  - FTP プロトコルのサポートを廃止します。 従来の FTP プロトコルのサポートは Microsoft Edge から削除されました。 FTP リンクに移動しようとすると、ブラウザーは、FTP リンクを処理する外部アプリケーションを開く操作をオペレーティング システムに指示します。 または、IT 管理者は、FTP プロトコルに依存するサイトで IE モードを使用する Microsoft Edge を構成できます。
  - Adobe Flash のサポートは削除されます。 Microsoft Edge Beta バージョン 88 から、Adobe Flash の機能とサポートは削除されます。 詳細: [Adobe Flash Player のサポート終了に関する更新プログラム - Microsoft Edge ブログ (windows.com)](https://blogs.windows.com/msedgedev/2020/09/04/update-adobe-flash-end-support/)

- **認証:**

  - シングル サインオン (SSO) は、macOS およびダウンレベル Windows の Azure Active Directory (Azure AD) アカウントと Microsoft アカウント (MSA) で利用できます。 macOS またはダウンレベルの Microsoft Windows (7, 8.1) で Microsoft Edge にサインインしたユーザーは、Work アカウントと Microsoft アカウント (bing.com、office.com、msn.com、outlook.com など) でシングル サインオンを許可するように構成された Web サイトに自動的にサインインします。<br>注: この機能を利用するには、ユーザーが Microsoft Edge 88 より前のバージョンで Microsoft Edge にサインインした場合、サインアウトしてからサインインしなおす必要がある場合があります。
  - macOS のユーザーを、自分の仕事用アカウントで認証するサイトの仕事用プロファイルに自動的に切り替えます。 Microsoft Edge バージョン 88 から、macOS 上のユーザーの仕事用プロファイルで認証するサイトを切り替える機能が提供されています。<br>注: この機能を利用するには、ユーザーが Microsoft Edge 88 より前のバージョンで Microsoft Edge にサインインした場合、サインアウトしてからサインインしなおす必要がある場合があります。

- セッションを終了するキオスク モード オプション。 [セッションの終了] ボタンは、キオスク モードのパブリック ブラウズ エクスペリエンスで利用できます。 この機能により、Microsoft Edge を閉じたときにブラウザーのデータと設定が削除されます。 キオスク モード機能とロードマップの詳細については 、「[Microsoft Edge キオスク モードを構成する](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode)」を参照してください。

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

### ポリシーの更新

#### 新しいポリシー

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

#### 廃止されたポリシー

次のポリシーは廃止されました。

- [ProactiveAuthEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proactiveauthenabled) - プロアクティブ認証を有効にします。
- [ProxyBypassList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxybypasslist) - プロキシ バイパス ルールを構成します。
- [ProxyMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxymode) - プロキシ サーバー設定を構成します。
- [ProxyPacUrl](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxypacurl) - プロキシの .pac ファイルの URL を設定します。
- [ProxyServer](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxyserver) - プロキシ サーバーのアドレスまたは URL を構成します。
- [WebDriverOverridesIncompatiblePolicies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webdriveroverridesincompatiblepolicies) - WebDriver が互換性のないポリシーを上書きすることを許可します。

#### 不使用のポリシー

次のポリシーは廃止されました。

- [DefaultPluginsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultpluginssetting) - 既定の Adobe Flash 設定。
- [PluginsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsallowedforurls) - 特定のサイトで Adobe Flash プラグインを許可します。
- [PluginsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsblockedforurls) - 特定のサイトで Adobe Flash プラグインをブロックします。
- [RunAllFlashInAllowMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#runallflashinallowmode) - Adobe Flash コンテンツ設定をすべてのコンテンツに拡張します。

<!-- end major 88 -->

## バージョン 87.0.664.55: 12 月 3 日

さまざまなバグとパフォーマンスの問題を修正しました。 このリリースでは、次の新機能がサポートされています。

- **ユーザーのパスワードのオンラインでの漏洩が見つかると、警告が生成されます**。 ユーザーのパスワードは、侵害された資格情報のリポジトリと照合され、一致するものが見つかるとユーザーに警告を通知します。 セキュリティとプライバシーを確保するために、ユーザーのパスワードは漏洩した資格情報のデータベースと照合するときにハッシュ化され、暗号化されます。

## バージョン 87.0.664.52: 11 月 30 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン 87.0.664.40: 11 月 18 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン 87.0.664.36: 11 月 16 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン 87.0.664.30: 11 月 9 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン 87.0.664.24: 11 月 2 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン 87.0.664.18: 10 月 26 日

さまざまなバグとパフォーマンスの問題を修正しました。

<!-- begin major 87 -->
## バージョン 87.0.664.12: 10 月 20 日

### 機能更新プログラム

- **キオスクモードプライバシー機能を有効にします**。 Microsoft Edge バージョン87から、ユーザーデータのプライバシーに関して企業のサポートができるキオスクモードの機能を有効にすることができます。 これらの機能により、終了時にユーザーデータをクリアしたり、ダウンロードしたファイルを削除したり、一定のアイドル時間が経過した後に、構成されていたスタート操作をリセットしたりできます。 [Microsoft Edge キオスクモードを 構成する方法](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode)の詳細については、こちらを参照してください
- **ClickOnce の展開が既定で有効**。 Microsoft Edge 87 では、ClickOnce が既定で有効になっています。これにより、企業がソフトウェアを展開する際の障壁を減らし、Microsoft Edge のレガシブラウザーの動作に合わせることができます。 Microsoft Edge 87 以降、ClickOnceEnabled policyが"未構成"の 状態の場合は、新しい既定の「有効化が ClickOnceの状態」（以前の規定が無効だった状態と異なり）に反映されます。
- **エンタープライズ新しいタブページ (NTP)は、カスタマイズ可能な仕事関連のフィードコンテンツと生産性を結びつけます**。 エンタープライズ NTP は、職場または学校アカウントでサインインしているユーザーに対して提供される Office 365 生産性向上ページだけでなく、カスタマイズされた、仕事関連の企業や業界のコンテンツを1ページにまとめて提供いたします。 ユーザーは、使い慣れた Office 365 のコンテンツと、Bing で提供されている一般法人向けの Microsoft Search を目にすることでしょう。 さらに、ユーザー、会社、またはその業界に関連するコンテンツやモジュールだけでなく、組織が利用可能にしている他のフィードを選択して、カスタマイズ可能な "マイフィード" を簡単に閲覧できます。 [詳しくはこちらをご覧ください](https://docs.microsoft.com/microsoft-365/admin/manage/manage-industry-news?view=o365-worldwide&preserve-view=true)。

- **プライバシーとセキュリティ**

  - ポリシー構成のサイトの TLS トークンバインドをサポートしています。 TLS トークンのバインドは、トークンの盗用攻撃を防ぐために、最初に設定されたデバイス以外のデバイスから cookie が再利用されないようにします。 TLS トークンバインドを使用するには、 [AllowTokenBindingForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowtokenbindingforurls) ポリシーを設定する必要があります。また、リストに記載されているサイトがこの機能をサポートしている必要があります。

- **PDF ファイルで強調表示のキーボードサポート**。 ユーザーは、キーボードのキーを使用して、PDF のテキストを強調表示できます。

- **印刷**

  - 両面印刷時にどのように紙を綴じるか選択します。 ユーザーが両面印刷するときに、用紙の長辺綴じか短辺綴じにするかを選択できます。
  - エンタープライズの印刷ラスター化モードを選択します。 Windows のポストスクリプトプリンター以外に Microsoft Edge をプリントする方法を制御します。 PostScript に対応していないプリンターの印刷ジョブが正しく印刷されるようにラスター化する必要がある場合があります。 印刷オプションには "Full (フル)" と "Fast (高速)"が表示されます。

### ポリシーの更新

#### 新しいポリシー

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

#### 廃止されたポリシー

[NewTabPageSetFeedType](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) - Microsoft Edge の新規タブ ページのエクスペリエンスを設定する

#### 非推奨ポリシー

[EnableDeprecatedWebPlatformFeatures](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledeprecatedwebplatformfeatures) -廃止されたWebプラットフォームの機能を一定期間、再度有効にします。

<!-- end major 87 -->

## バージョン 86.0.622.43: 10 月 16 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン 86.0.622.36: 10 月 7 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン 86.0.622.31: 10 月 1 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン 86.0.622.28: 9 月 28 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン86.0.622.15: 9 月14 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン 86.0.622.11: 9 月 9 日

### 機能更新プログラム

* **Internet Explorer モード:**

   * ユーザーが Microsoft Edge ユーザー インターフェイス (UI) を使用して、Internet Explorer モードでサイトをテストできるようにします。 Microsoft Edge バージョン 86 以降、管理者はユーザーがテスト目的で、またはサイトがサイト一覧の XML に追加されるまでの臨時措置として Internet Explorer モードでタブを読み込むことができるよう、UI オプションを有効にできます。

* **ダウンロード マネージャーを使用して、ダウンロードをディスクから削除できます。** ユーザーは、ブラウザーを離れることなくダウンロードしたファイルをディスクから削除できるようになりました。 ダウンロード削除のこの新しい機能は、ダウンロード シェルフのコンテキスト メニューまたはダウンロード ページに存在します。

* **Microsoft Edge の以前のバージョンにロールバック。** ロールバック機能では、Microsoft Edge の最新バージョンに問題がある場合、管理者は Microsoft Edge を既知の正常なバージョンに戻すことができます。
[詳しくはこちらをご覧ください](edge-learnmore-rollback.md)。

* **エンタープライズ全体で、同期の有効化を既定で強制できます。**  管理者は既定で、[ForceSync](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcesync) ポリシーを使用して、Azure Active Directory (Azure AD) アカウントに対して同期を有効にできます。

* **PDF の更新情報:**

  * PDF ドキュメントの目次。 バージョン 86 以降、Microsoft Edge に PDF ドキュメント内をユーザーが簡単に移動できる目次のサポートが追加されました。
  * スモール フォーム ファクターの画面で、すべての PDF 機能にアクセス。 画面サイズが小さなデバイスでも、Microsoft Edge PDF リーダーのすべての機能にアクセスできます。
  * PDF ファイルで蛍光ペンのペン サポート。 この更新で、ユーザーはデジタル ペンを使用して、実際の蛍光ペンと紙と同様の方法で PDF ファイルでテキストを直接強調表示できます。
  * PDF のスクロールの改善。 長い PDF ドキュメント内を移動するときに、スムーズなスクロールを体験できるようになりました。

* **Windows 7、8、8.1 でのプロファイル の自動切り替え。** 現在 Windows 10 の Microsoft Edge で利用可能なプロフィールの自動切り替えは、ダウンレベルの Windows (Windows 7、8、8.1) に拡張されました。 詳細については、ブログ記事「[プロファイルの自動切り替え](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/)」を参照してください。

* **ユーザーが Microsoft Edge アドオン Web サイトで検索クエリを入力し始めると、自動完了の候補が表示されます。** 自動完了によって、ユーザーは文字列全体を入力せずに検索クエリを素早く完成できます。 ユーザーは正確なスペルを記憶する必要がなく、表示されるオプションから選ぶことができるので、これは便利な機能です。

* **HTML5 アプリケーション キャッシュ API の削除。**  Microsoft Edge バージョン 86 以降、Web ページのオフライン使用を可能にするレガシ アプリケーション キャッシュ API は Microsoft Edge から削除されます。 Web 開発者は、[WebDev ドキュメント](https://web.dev/appcache-removal/)で、アプリケーション キャッシュ API のサービス ワーカーへの置き換えに関する情報を確認する必要があります。  重要: Microsoft Edge バージョン 90 まで、サイトが非推奨のアプリケーション キャッシュ API を引き続き使用できるようにする [AppCache OriginTrial Token](https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673) を要求できます。

* **セキュリティ:**

  * セキュリティで保護された DNS (DNS over HTTPS) のサポート。  Microsoft Edge バージョン 86 以降、セキュリティ保護された DNS を制御する設定が、管理されていないデバイスで利用可能になりました。 ユーザーは管理されたデバイスでこれらの設定にアクセスできませんが、IT 管理者は [dnsoverhttpsmode](https://docs.microsoft.com/deployedge/microsoft-edge-policies#dnsoverhttpsmode) グラウンド ポリシーを使用して、セキュリティ保護された DNS を有効または無効にすることができます。


* **グループ ポリシーを使用して、新しいタブ ページ (NTP) にカスタム イメージを追加できます。** Microsoft Edge バージョン 86 以降、NTP で既定のイメージをユーザーが指定したイメージで置き換えるためのオプションを使用できます。 このイメージのプロパティを管理する機能も、グループ ポリシーによってサポートされています。

* **カスタマイズしたキーボード ショートカットを VS コードと一致させます。** Microsoft Edge の DevTools では、使用しているエディターや IDE に合わせて DevTools のキーボード ショートカットをカスタマイズできるようになりました。 (Microsoft Edge 84 で、VS コードに対して DevTools のキーボードショートカットを一致させる機能を追加しました)。

* **ダウンレベルの Windows と macOS で [MetricsReportingEnabled]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) と [SendSiteInformationToImproveServices]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) ポリシーを置き換えます。** これらのポリシーは Microsoft Edge バージョン 86 では非推奨で、Microsoft Edge バージョン 89 で廃止されます。<br>
これらのポリシーは、Windows 10 では[利用統計情報の許可](https://go.microsoft.com/fwlink/?linkid=2099569)に、その他すべてのプラットフォームでは新しい [DiagnosticData](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata) ポリシーに置き換えられます。 これにより、ユーザーは Windows 7、8、8.1、macOS で、Microsoft に送信される診断データを管理できるようになります。

* **SameSite=既定で緩い Cookie**。 Web セキュリティとプライバシーを向上させるために、Cookie は、既定では、[SameSite=Lax](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite) 処理に設定されます。 つまり、Cookie はファーストパーティのコンテキストでのみ送信され、サードパーティに送信される要求では省略されます。 この変更により、サードパーティのリソースが正しく機能するために Cookie を必要とする Web サイトに互換性の影響が生じる可能性があります。 このような Cookie を許可するために、Web 開発者は、Cookie の設定時に明示的な `SameSite=none` および `Secure` 属性を追加することにより、サードパーティのコンテキストから設定および送信する必要がある Cookie にマークを付けることができます。 特定のサイトをこの変更から除外することを希望する企業は、[LegacySameSiteCookieBehaviorEnabledForDomainList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#legacysamesitecookiebehaviorenabledfordomainlist) ポリシーを使用してこれを行うか、[LegacySameSiteCookieBehaviorEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) ポリシーを使用してすべてのサイトにわたる変更をオプトアウトできます。

### ポリシーの更新

#### 新しいポリシー

19 個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [CollectionsServicesAndExportsBlockList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#collectionsservicesandexportsblocklist) - 指定したサービスの一覧へのアクセスをブロックし、コレクション内のターゲットをエクスポートします。
- [DefaultSensorsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultsensorssetting) - 既定のセンサーの設定。
- [DefaultSerialGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultserialguardsetting) - シリアル API の使用を制御します。
- [DiagnosticData](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata) - ブラウザーの使用状況に関する必須およびオプションの診断データを送信します。
- [EnterpriseModeSiteListManagerAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enterprisemodesitelistmanagerallowed) - Enterprise Mode Site List Manager ツールへのアクセスを許可します。
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
- [URLBlocklist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#urlblocklist) - URL の一覧へのアクセスをブロックします。
- [URLAllowlist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#urlallowlist) - 許可されている URL の一覧を定義します。
- [UserAgentClientHintsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#useragentclienthintsenabled) - ユーザー エージェント クライアント ヒント機能を有効にします。
- [UserDataSnapshotRetentionLimit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#userdatasnapshotretentionlimit) - 緊急ロールバックの場合に使用されるユーザー データのスナップショット数を制限します。

#### 廃止されたポリシー

- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - 使用状況とクラッシュ関連のデータレポートを有効にします。
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Microsoft サービスを改善するためにサイト情報を送信します。

#### 非推奨ポリシー

[TLS13HardeningForLocalAnchorsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#tls13hardeningforlocalanchorsenabled) - ローカル トラスト アンカーの TLS 1.3 セキュリティ機能を有効にします。

#### 変更されたポリシーのキャプション

[NativeWindowOcclusionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled) - ネイティブ ウィンドウ オクルージョンを有効にします。

#### 変更されたポリシーの説明

- [AdsSettingForIntrusiveAdsSites](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#adssettingforintrusiveadssites)
- [AllowTokenBindingForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#allowtokenbindingforurls)
- [AmbientAuthenticationInPrivateModesEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#ambientauthenticationinprivatemodesenabled)
- [ApplicationGuardContainerProxy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#applicationguardcontainerproxy)
- [AutoImportAtFirstRun](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoimportatfirstrun)
- [AutoOpenFileTypes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoopenfiletypes)
- [BrowserSignin](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#browsersignin)
- [ClearBrowsingDataOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#clearbrowsingdataonexit) 
- [ClickOnceEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#clickonceenabled)
- [CommandLineFlagSecurityWarningsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#commandlineflagsecuritywarningsenabled)
- [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin)
- [ConfigureShare](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureshare)
- [CookiesAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#cookiesallowedforurls)
- [CustomHelpLink](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#customhelplink)
- [DefaultCookiesSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultcookiessetting)
- [DefaultGeolocationSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultgeolocationsetting)
- [DefaultImagesSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultimagessetting)
- [Defaul/Securecontentsetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultinsecurecontentsetting)
- [DefaultJavaScriptSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultjavascriptsetting)
- [DefaultNotificationsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultnotificationssetting)
- [DefaultPluginsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultpluginssetting)
- [DefaultPopupsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultpopupssetting)
- [DefaultSearchProviderEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultsearchproviderenabled)
- [DefaultWebBluetoothGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultwebbluetoothguardsetting)
- [DefaultWebUsbGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultwebusbguardsetting)
- [DelayNavigationsForInitialSiteListDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#delaynavigationsforinitialsitelistdownload)
- [DeveloperToolsAvailability](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#developertoolsavailability)
- [EnableSha1ForLocalAnchors](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors)
- [DownloadRestrictions](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#downloadrestrictions)
- [EnableDeprecatedWebPlatformFeatures](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledeprecatedwebplatformfeatures)
- [WinHttpProxyResolverEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#winhttpproxyresolverenabled)
- [ExperimentationAndConfigurationServiceControl](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#experimentationandconfigurationservicecontrol)
- [ExternalProtocolDialogShowAlwaysOpenCheckbox](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#externalprotocoldialogshowalwaysopencheckbox)
- [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)
- [ForceBingSafeSearch](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcebingsafesearch)
- [ForceYouTubeRestrict](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forceyoutuberestrict)
- [HomepageIsNewTabPage](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#homepageisnewtabpage)
- [HomepageLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#homepagelocation)
- [InPrivateModeAvailability](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#inprivatemodeavailability)
- [InternetExplorerIntegrationEnhancedHangDetection](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationenhancedhangdetection)
- [InternetExplorerIntegrationLevel](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlevel)
- [InternetExplorerIntegrationSiteRedirect](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationsiteredirect)
- [LegacySameSiteCookieBehaviorEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled)
- [NativeWindowOcclusionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled)
- [NavigationDelayForInitialSiteListDownloadTimeout](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#navigationdelayforinitialsitelistdownloadtimeout)
- [NetworkPredictionOptions](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#networkpredictionoptions)
- [NewTabPageLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagelocation)
- [NewTabPageSearchBox](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesearchbox)
- [NewTabPageSetFeedType](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype)
- [NonRemovableProfileEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nonremovableprofileenabled)
- [PasswordProtectionWarningTrigger](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordprotectionwarningtrigger)
- [PasswordProtectionLoginURLs](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordprotectionloginurls)
- [PasswordProtectionChangePasswordURL](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordprotectionchangepasswordurl)
- [PluginsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsallowedforurls)
- [PluginsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsblockedforurls)
- [PreventSmartScreenPromptOverride](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#preventsmartscreenpromptoverride)
- [PreventSmartScreenPromptOverrideForFiles](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#preventsmartscreenpromptoverrideforfiles)
- [ProxyMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxymode)
- [RegisteredProtocolHandlers](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#registeredprotocolhandlers)
- [RelaunchNotification](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#relaunchnotification)
- [RestoreOnStartup](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#restoreonstartup)
- [RestoreOnStartupURLs](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#restoreonstartupurls)
- [RestrictSigninToPattern](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#restrictsignintopattern)
- [SSLVersionMin](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sslversionmin)
- [SmartScreenAllowListDomains](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenallowlistdomains)
- [SmartScreenEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenenabled)
- [SmartScreenForTrustedDownloadsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenfortrusteddownloadsenabled)
- [SmartScreenPuaEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled)
- [TrackingPrevention](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#trackingprevention)
- [WebRtcLocalhostIpHandling](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webrtclocalhostiphandling)

<!-- end 86 -->

## バージョン 85.0.564.41: 8 月 25 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン 85.0.564.40: 8 月 21 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン 85.0.564.36: 8 月 17 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン 85.0.564.30: 8 月 10 日

さまざまなバグとパフォーマンスの問題を修正しました。

## バージョン 85.0.564.23: 8 月 3 日

さまざまなバグとパフォーマンスの問題を修正しました。

<!--- Archived to version 85.0.564.18: July 28 ---->

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
