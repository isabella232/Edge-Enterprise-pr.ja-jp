---
title: Microsoft Edge ブラウザー ポリシーに関するドキュメント
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 01/07/2021
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge ブラウザーでサポートされているすべてのポリシーに関する Windows と Mac のドキュメント
ms.openlocfilehash: b422361809b0a2acaa392729025a95aef7ac8f83
ms.sourcegitcommit: 4dc45cde7cfd29cd24a03f6e830502e95c43d82e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2021
ms.locfileid: "11254975"
---
# Microsoft Edge - ポリシー

最新バージョンの Microsoft Edge には、次のポリシーが含まれています。 これらのポリシーを使用して、組織内での Microsoft Edge の動作方法を構成することができます。

Microsoft Edge の更新方法とタイミングを制御するために使用される追加のポリシー セットについては、「[Microsoft Edge update policy reference (Microsoft Edge の更新ポリシー リファレンス)](microsoft-edge-update-policies.md)」を参照してください。

Microsoft Edge に推奨されるセキュリティ構成のベースライン設定については、[Microsoft Security Compliance Toolkit](https://www.microsoft.com/download/details.aspx?id=55319) をダウンロードすることができます。 詳細については、「[Microsoft セキュリティ ベースライン ブログ](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)」を参照してください。

> [!NOTE]
> この記事は Microsoft Edge version 77 以降に適用されます。


## 新しいポリシー

次の表に、この更新プログラムの新しいポリシーを示します。

| 名前 | キャプション |
|-|-|
|[BasicAuthOverHttpEnabled](#basicauthoverhttpenabled)|HTTP の基本認証を許可する|
|[TargetBlankImpliesNoOpener](#targetblankimpliesnoopener)|\_blank をターゲットとするリンクに window.opener を設定しない|
|[WebWidgetAllowed](#webwidgetallowed)|Web ウィジェットを許可する|
|[WebWidgetIsEnabledOnStartup](#webwidgetisenabledonstartup)|Windows 起動時に Web ウィジェットを有効にする|


## 使用可能なポリシー

次の表は、このリリースの Microsoft Edge で使用可能な、ブラウザー関連のすべてのグループ ポリシーの一覧を示しています。 個々のポリシーに関する詳しい情報を取得するには、表内のリンクをお使いください。

|||
|-|-|
|[Application Guard の設定](#application-guard-settings)|[キャスト](#cast)|
|[コンテンツの設定](#content-settings)|[既定の検索プロバイダー](#default-search-provider)|
|[拡張機能](#extensions)|[HTTP 認証](#http-authentication)|
|[キオスク モードの設定](#kiosk-mode-settings)|[ネイティブ メッセージング](#native-messaging)|
|[パスワード マネージャーと保護](#password-manager-and-protection)|[パフォーマンス](#performance)|
|[印刷](#printing)|[プロキシ サーバー](#proxy-server)|
|[タブのスリープ設定](#sleeping-tabs-settings)|[SmartScreen の設定](#smartscreen-settings)|
|[スタートアップ、ホーム ページ、新規タブ ページ](#startup-home-page-and-new-tab-page)|[補足](#additional)|


### [*Application Guard の設定*](#application-guard-settings-policies)

|ポリシー名|キャプション|
|-|-|
|[ApplicationGuardContainerProxy](#applicationguardcontainerproxy)|Application Guard コンテナー プロキシ|
### [*キャスト*](#cast-policies)

|ポリシー名|キャプション|
|-|-|
|[EnableMediaRouter](#enablemediarouter)|Google Cast を有効にする|
|[ShowCastIconInToolbar](#showcasticonintoolbar)|ツール バーにキャスト アイコンを表示する|
### [*コンテンツの設定*](#content-settings-policies)

|ポリシー名|キャプション|
|-|-|
|[AutoSelectCertificateForUrls](#autoselectcertificateforurls)|これらのサイトのクライアント証明書を自動的に選択する|
|[CookiesAllowedForUrls](#cookiesallowedforurls)|特定のサイトでの Cookie を許可する|
|[CookiesBlockedForUrls](#cookiesblockedforurls)|特定のサイトでの Cookie のブロック|
|[CookiesSessionOnlyForUrls](#cookiessessiononlyforurls)|特定の Web サイトからの Cookie を現在のセッションに制限する|
|[DefaultCookiesSetting](#defaultcookiessetting)|Cookie を構成する|
|[DefaultFileSystemReadGuardSetting](#defaultfilesystemreadguardsetting)|読み取り用にファイル システム API の使用を制御する|
|[DefaultFileSystemWriteGuardSetting](#defaultfilesystemwriteguardsetting)|書き込み用にファイル システム API の使用を制御する|
|[DefaultGeolocationSetting](#defaultgeolocationsetting)|既定の位置情報の設定|
|[DefaultImagesSetting](#defaultimagessetting)|既定の画像の設定|
|[DefaultInsecureContentSetting](#defaultinsecurecontentsetting)|安全でないコンテンツの例外の使用を制御する|
|[DefaultJavaScriptSetting](#defaultjavascriptsetting)|既定の JavaScript の設定|
|[DefaultNotificationsSetting](#defaultnotificationssetting)|既定の通知の設定|
|[DefaultPluginsSetting](#defaultpluginssetting)|既定の Adobe Flash 設定 (不使用)|
|[DefaultPopupsSetting](#defaultpopupssetting)|既定のポップアップ ウィンドウの設定|
|[DefaultWebBluetoothGuardSetting](#defaultwebbluetoothguardsetting)|Web Bluetooth API の使用を制御する|
|[DefaultWebUsbGuardSetting](#defaultwebusbguardsetting)|WebUSB API の使用を制御する|
|[FileSystemReadAskForUrls](#filesystemreadaskforurls)|これらのサイトのファイル システム API を通して読み取りアクセスを許可する|
|[FileSystemReadBlockedForUrls](#filesystemreadblockedforurls)|これらのサイトのファイル システム API を通して読み取りアクセスをブロックする|
|[FileSystemWriteAskForUrls](#filesystemwriteaskforurls)|これらのサイトのファイルとディレクトリへの書き込みアクセスを許可する|
|[FileSystemWriteBlockedForUrls](#filesystemwriteblockedforurls)|これらのサイトのファイルとディレクトリへの書き込みアクセスをブロックする|
|[ImagesAllowedForUrls](#imagesallowedforurls)|これらのサイトでの画像の使用を許可する|
|[ImagesBlockedForUrls](#imagesblockedforurls)|特定のサイトでの 画像 のブロック|
|[InsecureContentAllowedForUrls](#insecurecontentallowedforurls)|特定のサイトでの安全でないコンテンツの使用を許可する|
|[InsecureContentBlockedForUrls](#insecurecontentblockedforurls)|特定のサイトでの安全でないコンテンツのブロック|
|[JavaScriptAllowedForUrls](#javascriptallowedforurls)|特定のサイトでの JavaScript を許可する|
|[JavaScriptBlockedForUrls](#javascriptblockedforurls)|特定のサイトでの JavaScript のブロック|
|[LegacySameSiteCookieBehaviorEnabled](#legacysamesitecookiebehaviorenabled)|既定のレガシ SameSite Cookie の動作設定を有効にする|
|[LegacySameSiteCookieBehaviorEnabledForDomainList](#legacysamesitecookiebehaviorenabledfordomainlist)|特定のサイトで Cookie のレガシ SameSite の動作に戻す|
|[NotificationsAllowedForUrls](#notificationsallowedforurls)|特定のサイトで通知を許可する|
|[NotificationsBlockedForUrls](#notificationsblockedforurls)|特定のサイトでの通知のブロック|
|[PluginsAllowedForUrls](#pluginsallowedforurls)|特定のサイトでの Adobe Flash プラグインの使用を許可する (不使用)|
|[PluginsBlockedForUrls](#pluginsblockedforurls)|特定のサイトでの Adobe Flash プラグインの使用をブロックする (不使用)|
|[PopupsAllowedForUrls](#popupsallowedforurls)|特定のサイトでのポップアップ ウィンドウの表示を許可する|
|[PopupsBlockedForUrls](#popupsblockedforurls)|特定のサイトでのポップアップ ウィンドウのブロック|
|[RegisteredProtocolHandlers](#registeredprotocolhandlers)|プロトコル ハンドラーを登録する|
|[SpotlightExperiencesAndRecommendationsEnabled](#spotlightexperiencesandrecommendationsenabled)|ユーザーがカスタマイズされた背景画像およびテキスト、提案、通知を受け取ることができるようにするかどうか選択する
そしてMicrosoft サービスのヒントも受け取るのかどうか|
|[WebUsbAllowDevicesForUrls](#webusballowdevicesforurls)|特定の USB デバイスに接続するために、特定のサイトへのアクセスを許可する|
|[WebUsbAskForUrls](#webusbaskforurls)|特定のサイトでの WebUSB を許可する|
|[WebUsbBlockedForUrls](#webusbblockedforurls)|特定のサイトでの WebUSB のブロック|
### [*既定の検索プロバイダー*](#default-search-provider-policies)

|ポリシー名|キャプション|
|-|-|
|[DefaultSearchProviderEnabled](#defaultsearchproviderenabled)|既定の検索プロバイダーを有効にする|
|[DefaultSearchProviderEncodings](#defaultsearchproviderencodings)|既定の検索プロバイダー エンコード|
|[DefaultSearchProviderImageURL](#defaultsearchproviderimageurl)|既定の検索プロバイダーの画像による検索機能を指定する|
|[DefaultSearchProviderImageURLPostParams](#defaultsearchproviderimageurlpostparams)|POST を使用する画像 URL のパラメーター|
|[DefaultSearchProviderKeyword](#defaultsearchproviderkeyword)|既定の検索プロバイダーのキーワード|
|[DefaultSearchProviderName](#defaultsearchprovidername)|既定の検索プロバイダー名|
|[DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl)|既定の検索プロバイダーの検索 URL|
|[DefaultSearchProviderSuggestURL](#defaultsearchprovidersuggesturl)|検索候補用の既定の検索プロバイダーの URL|
|[NewTabPageSearchBox](#newtabpagesearchbox)|新しいタブページ検索ボックスの機能を構成する|
### [*拡張機能*](#extensions-policies)

|ポリシー名|キャプション|
|-|-|
|[BlockExternalExtensions](#blockexternalextensions)|外部拡張機能がインストールされないようにブロックする|
|[ExtensionAllowedTypes](#extensionallowedtypes)|許可されている拡張機能の種類を構成する|
|[ExtensionInstallAllowlist](#extensioninstallallowlist)|特定の拡張機能のインストールを許可する|
|[ExtensionInstallBlocklist](#extensioninstallblocklist)|インストールできない拡張機能を制御する|
|[ExtensionInstallForcelist](#extensioninstallforcelist)|警告なしにインストールする拡張機能を制御する|
|[ExtensionInstallSources](#extensioninstallsources)|拡張機能とユーザー スクリプトのインストール ソースを構成する|
|[ExtensionSettings](#extensionsettings)|拡張機能管理設定を構成する|
### [*HTTP 認証*](#http-authentication-policies)

|ポリシー名|キャプション|
|-|-|
|[AllowCrossOriginAuthPrompt](#allowcrossoriginauthprompt)|cross-origin HTTP 認証プロンプトを許可する|
|[AuthNegotiateDelegateAllowlist](#authnegotiatedelegateallowlist)|Microsoft Edge がユーザーの資格情報を委任できるサーバーの一覧を指定する|
|[AuthSchemes](#authschemes)|サポートされる認証スキーム|
|[AuthServerAllowlist](#authserverallowlist)|許可されている認証サーバーの一覧を構成する|
|[BasicAuthOverHttpEnabled](#basicauthoverhttpenabled)|HTTP の基本認証を許可する|
|[DisableAuthNegotiateCnameLookup](#disableauthnegotiatecnamelookup)|Kerberos 認証をネゴシエートするときの CNAME ルックアップを無効にする|
|[EnableAuthNegotiatePort](#enableauthnegotiateport)|Kerberos SPN に標準以外のポートを含める|
|[NtlmV2Enabled](#ntlmv2enabled)|NTLMv2 認証を有効にするかどうかを制御する|
### [*キオスク モードの設定*](#kiosk-mode-settings-policies)

|ポリシー名|キャプション|
|-|-|
|[KioskAddressBarEditingEnabled](#kioskaddressbareditingenabled)|キオスクモードのパブリックブラウザーのエクスペリエンスを編集するアドレスバーを構成する|
|[KioskDeleteDownloadsOnExit](#kioskdeletedownloadsonexit)|Microsoft Edge が閉じたときに、キオスク セッションの一部としてダウンロードされたファイルを削除する|
### [*ネイティブ メッセージング*](#native-messaging-policies)

|ポリシー名|キャプション|
|-|-|
|[NativeMessagingAllowlist](#nativemessagingallowlist)|ユーザーが使用できるネイティブ メッセージング ホストを制御する|
|[NativeMessagingBlocklist](#nativemessagingblocklist)|ネイティブ メッセージング ブロック リストを構成する|
|[NativeMessagingUserLevelHosts](#nativemessaginguserlevelhosts)|(管理者のアクセス許可なしでインストールされた) ユーザー レベルのネイティブ メッセージング ホストを許可する|
### [*パスワード マネージャーと保護*](#password-manager-and-protection-policies)

|ポリシー名|キャプション|
|-|-|
|[PasswordManagerEnabled](#passwordmanagerenabled)|パスワードをパスワード マネージャーに保存できるようにする|
|[PasswordMonitorAllowed](#passwordmonitorallowed)|パスワードが安全でないことが判明した場合にユーザーに警告することを許可する|
|[PasswordProtectionChangePasswordURL](#passwordprotectionchangepasswordurl)|パスワード変更の URL を構成する|
|[PasswordProtectionLoginURLs](#passwordprotectionloginurls)|パスワード保護サービスがパスワードのソルト化ハッシュをキャプチャする必要があるエンタープライズ ログイン URL のリストを構成する|
|[PasswordProtectionWarningTrigger](#passwordprotectionwarningtrigger)|パスワード保護の警告トリガーを構成する|
|[PasswordRevealEnabled](#passwordrevealenabled)|[パスワードの表示] ボタンを有効にする|
### [*パフォーマンス*](#performance-policies)

|ポリシー名|キャプション|
|-|-|
|[StartupBoostEnabled](#startupboostenabled)|スタートアップ ブーストを有効にする|
### [*印刷*](#printing-policies)

|ポリシー名|キャプション|
|-|-|
|[DefaultPrinterSelection](#defaultprinterselection)|通常使うプリンターの選択ルール|
|[PrintHeaderFooter](#printheaderfooter)|ヘッダーとフッターを印刷する|
|[PrintPreviewUseSystemDefaultPrinter](#printpreviewusesystemdefaultprinter)|システムの既定のプリンターを通常使うプリンターに設定する|
|[PrinterTypeDenyList](#printertypedenylist)|拒否リストのプリンターの種類を無効にする|
|[PrintingAllowedBackgroundGraphicsModes](#printingallowedbackgroundgraphicsmodes)|バックグラウンド グラフィックス印刷モードを制限する|
|[PrintingBackgroundGraphicsDefault](#printingbackgroundgraphicsdefault)|既定の背景グラフィックス印刷モード|
|[PrintingEnabled](#printingenabled)|印刷を有効にする|
|[PrintingPaperSizeDefault](#printingpapersizedefault)|印刷の既定のページ サイズ|
|[UseSystemPrintDialog](#usesystemprintdialog)|システムの印刷ダイアログを使用して印刷する|
### [*プロキシ サーバー*](#proxy-server-policies)

|ポリシー名|キャプション|
|-|-|
|[ProxyBypassList](#proxybypasslist)|プロキシのバイパス ルールを構成する (非推奨)|
|[ProxyMode](#proxymode)|プロキシ サーバーの設定を構成する (非推奨)|
|[ProxyPacUrl](#proxypacurl)|プロキシ .pac ファイルの URL を設定する (非推奨)|
|[ProxyServer](#proxyserver)|プロキシ サーバーのアドレスまたは URL を構成する (非推奨)|
|[ProxySettings](#proxysettings)|プロキシの設定|
### [*タブのスリープ設定*](#sleeping-tabs-settings-policies)

|ポリシー名|キャプション|
|-|-|
|[SleepingTabsBlockedForUrls](#sleepingtabsblockedforurls)|特定のサイトでタブのスリープをブロックする|
|[SleepingTabsEnabled](#sleepingtabsenabled)|スリープ タブを構成する|
|[SleepingTabsTimeout](#sleepingtabstimeout)|タブをスリープ状態に設定するバックグラウンド タブの非アクティブタイムアウトを設定する|
### [*SmartScreen の設定*](#smartscreen-settings-policies)

|ポリシー名|キャプション|
|-|-|
|[PreventSmartScreenPromptOverride](#preventsmartscreenpromptoverride)|サイトに関する Microsoft Defender SmartScreen プロンプトをバイパスしない|
|[PreventSmartScreenPromptOverrideForFiles](#preventsmartscreenpromptoverrideforfiles)|ダウンロードに関する Microsoft Defender SmartScreen 警告のバイパスを防ぐ|
|[SmartScreenAllowListDomains](#smartscreenallowlistdomains)|Microsoft Defender SmartScreen が警告がトリガーしないドメインの一覧を構成する|
|[SmartScreenEnabled](#smartscreenenabled)|Microsoft Defender SmartScreen を構成する|
|[SmartScreenForTrustedDownloadsEnabled](#smartscreenfortrusteddownloadsenabled)|信頼のおけるソースからのダウンロードに対して Microsoft Defender SmartScreen のチェックを強制する|
|[SmartScreenPuaEnabled](#smartscreenpuaenabled)|Microsoft Defender SmartScreen を構成して望ましくない可能性のあるアプリをブロックする|
### [*スタートアップ &comma; ホーム ページ、新規タブ ページ*](#startup-home-page-and-new-tab-page-policies)

|ポリシー名|キャプション|
|-|-|
|[HomepageIsNewTabPage](#homepageisnewtabpage)|新規タブ ページをホーム ページとして設定する|
|[HomepageLocation](#homepagelocation)|ホーム ページの URL を構成する|
|[NewTabPageAllowedBackgroundTypes](#newtabpageallowedbackgroundtypes)|新しいタブページレイアウトに使用できる背景の種類を構成する|
|[NewTabPageCompanyLogo](#newtabpagecompanylogo)|新規タブ ページの会社のロゴを設定する (不使用)|
|[NewTabPageHideDefaultTopSites](#newtabpagehidedefaulttopsites)|新規タブ ページから既定のトップ サイトを非表示にする|
|[NewTabPageLocation](#newtabpagelocation)|新規タブ ページの URL を構成する|
|[NewTabPageManagedQuickLinks](#newtabpagemanagedquicklinks)|新規タブ ページのクイック リンクを設定する|
|[NewTabPagePrerenderEnabled](#newtabpageprerenderenabled)|新しいタブ ページの事前読み込みを有効にしてレンダリングを高速化する|
|[NewTabPageSetFeedType](#newtabpagesetfeedtype)|Microsoft Edge の新規タブ ページのエクスペリエンスを設定する (非推奨)|
|[RestoreOnStartup](#restoreonstartup)|起動時に実行する操作|
|[RestoreOnStartupURLs](#restoreonstartupurls)|ブラウザーの起動時に開くサイト|
|[ShowHomeButton](#showhomebutton)|ツールバーに [ホーム] ボタンを表示する|
### [*補足*](#additional-policies)

|ポリシー名|キャプション|
|-|-|
|[AddressBarMicrosoftSearchInBingProviderEnabled](#addressbarmicrosoftsearchinbingproviderenabled)|アドレス バーに表示される Bing の提案で Microsoft Search を有効にする|
|[AdsSettingForIntrusiveAdsSites](#adssettingforintrusiveadssites)|割り込み広告のあるサイトの広告設定|
|[AllowDeletingBrowserHistory](#allowdeletingbrowserhistory)|ブラウザーの履歴とダウンロードの履歴を削除できるようにする|
|[AllowFileSelectionDialogs](#allowfileselectiondialogs)|ファイル選択ダイアログを許可する|
|[AllowPopupsDuringPageUnload](#allowpopupsduringpageunload)|ページのアンロード中にポップアップを表示できます (廃止)|
|[AllowSurfGame](#allowsurfgame)|サーフィン ゲームを許可する|
|[AllowSyncXHRInPageDismissal](#allowsyncxhrinpagedismissal)|ページが同期 XHR 要求をページの解除中に送信できるようにする (非推奨)|
|[AllowTokenBindingForUrls](#allowtokenbindingforurls)|Microsoft Edge がトークンのバインドの確立を試行するサイトの一覧を構成する|
|[AllowTrackingForUrls](#allowtrackingforurls)|特定のサイトの追跡防止の例外を構成する|
|[AlternateErrorPagesEnabled](#alternateerrorpagesenabled)|Web ページが見つからない場合に、似通ったページを候補として表示する|
|[AlwaysOpenPdfExternally](#alwaysopenpdfexternally)|常に PDF ファイルを外部で開く|
|[AmbientAuthenticationInPrivateModesEnabled](#ambientauthenticationinprivatemodesenabled)|InPrivate プロファイルとゲスト プロファイルに対してアンビエント認証を有効にする|
|[AppCacheForceEnabled](#appcacheforceenabled)|既定でオフになっている場合でも、App Cache 機能を再度有効にすることを許可する|
|[ApplicationLocaleValue](#applicationlocalevalue)|アプリケーション ロケールを設定する|
|[AudioCaptureAllowed](#audiocaptureallowed)|オーディオ キャプチャの許可またはブロック|
|[AudioCaptureAllowedUrls](#audiocaptureallowedurls)|アクセス許可を要求することなくオーディオ キャプチャ デバイスにアクセスできるサイト|
|[AudioSandboxEnabled](#audiosandboxenabled)|オーディオ サンドボックスの実行を許可する|
|[AutoImportAtFirstRun](#autoimportatfirstrun)|初回実行時に、別のブラウザーのデータや設定を自動的にインポートする|
|[AutoLaunchProtocolsFromOrigins](#autolaunchprotocolsfromorigins)|ユーザーにプロンプ​​トを表示せずに、リストされたオリジンから外部アプリケーションを起動できるプロトコルのリストを定義する|
|[AutoOpenAllowedForURLs](#autoopenallowedforurls)|AutoOpenFileTypes を適用できる URL|
|[AutoOpenFileTypes](#autoopenfiletypes)|ダウンロード時に自動的に開く必要があるファイルの種類の一覧|
|[AutofillAddressEnabled](#autofilladdressenabled)|アドレスのオートフィルを有効にする|
|[AutofillCreditCardEnabled](#autofillcreditcardenabled)|クレジット カードのオートフィルを有効にする|
|[AutoplayAllowed](#autoplayallowed)|Web サイトのメディア自動再生を許可する|
|[BackgroundModeEnabled](#backgroundmodeenabled)|Microsoft Edge を終了した後も引き続きバックグラウンド アプリを実行する|
|[BackgroundTemplateListUpdatesEnabled](#backgroundtemplatelistupdatesenabled)|コレクションやテンプレートを使用する他の機能で利用可能なテンプレートの一覧をバックグラウンドで更新できるようにする|
|[BingAdsSuppression](#bingadssuppression)|Bing 検索結果でのすべての広告のブロック|
|[BlockThirdPartyCookies](#blockthirdpartycookies)|サード パーティの Cookie のブロック|
|[BrowserAddProfileEnabled](#browseraddprofileenabled)|ID のポップアップ メニューまたは [設定] ページからプロファイルの作成を有効にする|
|[BrowserGuestModeEnabled](#browserguestmodeenabled)|ゲスト モードを有効にする|
|[BrowserNetworkTimeQueriesEnabled](#browsernetworktimequeriesenabled)|ブラウザー ネットワーク時間サービスへのクエリを許可する|
|[BrowserSignin](#browsersignin)|ブラウザーへのサインイン設定|
|[BuiltInDnsClientEnabled](#builtindnsclientenabled)|組み込みの DNS クライアントを使用する|
|[BuiltinCertificateVerifierEnabled](#builtincertificateverifierenabled)|組み込みの証明書検証機能を使用してサーバー証明書を検証するかどうかを決定する (非推奨)|
|[CertificateTransparencyEnforcementDisabledForCas](#certificatetransparencyenforcementdisabledforcas)|subjectPublicKeyInfo ハッシュの一覧に対する証明書の透明性の強制を無効にする|
|[CertificateTransparencyEnforcementDisabledForLegacyCas](#certificatetransparencyenforcementdisabledforlegacycas)|レガシ証明機関の一覧に対する証明書の透明性の強制を無効にする|
|[CertificateTransparencyEnforcementDisabledForUrls](#certificatetransparencyenforcementdisabledforurls)|特定の URL に対する証明書の透明性の強制を無効にする|
|[ClearBrowsingDataOnExit](#clearbrowsingdataonexit)|Microsoft Edge の終了時に閲覧データをクリアする|
|[ClearCachedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit)|Microsoft Edge を閉じるときに、キャッシュされた画像とファイルをクリアする|
|[ClickOnceEnabled](#clickonceenabled)|ユーザーが ClickOnce プロトコルを使用してファイルを開けるようにする|
|[CollectionsServicesAndExportsBlockList](#collectionsservicesandexportsblocklist)|指定したサービスの一覧へのアクセスをブロックし、コレクション内のターゲットをエクスポートする|
|[CommandLineFlagSecurityWarningsEnabled](#commandlineflagsecuritywarningsenabled)|コマンドライン フラグのセキュリティ警告を有効にする|
|[ComponentUpdatesEnabled](#componentupdatesenabled)|Microsoft Edge でのコンポーネントの更新を有効にする|
|[ConfigureDoNotTrack](#configuredonottrack)|トラッキング拒否を構成する|
|[ConfigureFriendlyURLFormat](#configurefriendlyurlformat)|Microsoft Edge からコピーした URLの既定の貼り付け書式を構成し、他の形式をユーザーが利用できるようにするかどうかを決定する|
|[ConfigureOnPremisesAccountAutoSignIn](#configureonpremisesaccountautosignin)|Azure AD ドメイン アカウントがない場合、Active Directory ドメイン アカウントで自動サインインを構成する|
|[ConfigureOnlineTextToSpeech](#configureonlinetexttospeech)|オンラインでの音声合成を構成する|
|[ConfigureShare](#configureshare)|共有エクスペリエンスを構成する|
|[CustomHelpLink](#customhelplink)|カスタム ヘルプリンクを指定する|
|[DNSInterceptionChecksEnabled](#dnsinterceptionchecksenabled)|DNS の傍受チェックを有効にする|
|[DefaultBrowserSettingEnabled](#defaultbrowsersettingenabled)|Microsoft Edge を既定のブラウザーとして設定する|
|[DefaultSearchProviderContextMenuAccessAllowed](#defaultsearchprovidercontextmenuaccessallowed)|既定の検索プロバイダーのコンテキスト メニューへのアクセスを許可する|
|[DefaultSensorsSetting](#defaultsensorssetting)|既定のセンサーの設定|
|[DefaultSerialGuardSetting](#defaultserialguardsetting)|シリアル API の使用を制御する|
|[DelayNavigationsForInitialSiteListDownload](#delaynavigationsforinitialsitelistdownload)|タブ ナビゲーションの前にエンタープライズ モード サイト一覧が使用できるようにする|
|[DeleteDataOnMigration](#deletedataonmigration)|移行時に古いブラウザー データを削除する|
|[DeveloperToolsAvailability](#developertoolsavailability)|開発者ツールの使用を制御する|
|[DiagnosticData](#diagnosticdata)|ブラウザーの使用状況に関する必須およびオプションの診断データを送信する|
|[DirectInvokeEnabled](#directinvokeenabled)|ユーザーが DirectInvoke プロトコルを使用してファイルを開けるようにする|
|[Disable3DAPIs](#disable3dapis)|3D グラフィック API のサポートを無効にする|
|[DisableScreenshots](#disablescreenshots)|スクリーンショットの撮影を無効にする|
|[DiskCacheDir](#diskcachedir)|ディスク キャッシュ ディレクトリを設定する|
|[DiskCacheSize](#diskcachesize)|ディスク キャッシュ サイズをバイトに設定する|
|[DnsOverHttpsMode](#dnsoverhttpsmode)|DNS over HTTPS モードを制御する|
|[DnsOverHttpsTemplates](#dnsoverhttpstemplates)|目的の DNS over HTTPS リゾルバーの URI テンプレートを指定する|
|[DownloadDirectory](#downloaddirectory)|ダウンロード ディレクトリを設定する|
|[DownloadRestrictions](#downloadrestrictions)|ダウンロードの制限を許可する|
|[EdgeCollectionsEnabled](#edgecollectionsenabled)|コレクション機能を有効にする|
|[EdgeShoppingAssistantEnabled](#edgeshoppingassistantenabled)|Microsoft Edge でのショッピングを有効にする|
|[EditFavoritesEnabled](#editfavoritesenabled)|ユーザーがお気に入りを編集できるようにする|
|[EnableDeprecatedWebPlatformFeatures](#enabledeprecatedwebplatformfeatures)|(使われていない) 限られた期間のみ使用できます。|
|[EnableDomainActionsDownload](#enabledomainactionsdownload)|Microsoft からのドメイン アクションのダウンロードを有効にする (不使用)|
|[EnableOnlineRevocationChecks](#enableonlinerevocationchecks)|オンラインでの OCSP/CRL のチェックを有効にする|
|[EnableSha1ForLocalAnchors](#enablesha1forlocalanchors)|ローカルトラストアンカーによって発行されたときに SHA-1 を使用して署名された証明書を許可します (非推奨)|
|[EnterpriseHardwarePlatformAPIEnabled](#enterprisehardwareplatformapienabled)|マネージ拡張がエンタープライズ ハードウェア プラットフォーム API を使用できるようにする|
|[EnterpriseModeSiteListManagerAllowed](#enterprisemodesitelistmanagerallowed)|Enterprise Mode Site List Manager ツールへのアクセスを許可する|
|[ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](#exemptdomainfiletypepairsfromfiletypedownloadwarnings)|ドメイン上の指定されたファイルの種類のダウンロード ファイルの種類の拡張子ベースの警告を無効にする|
|[ExperimentationAndConfigurationServiceControl](#experimentationandconfigurationservicecontrol)|Experimentation and Configuration Service との通信を制御する|
|[ExternalProtocolDialogShowAlwaysOpenCheckbox](#externalprotocoldialogshowalwaysopencheckbox)|外部プロトコル ダイアログで [常に開く] チェックボックスを表示する|
|[FamilySafetySettingsEnabled](#familysafetysettingsenabled)|ファミリー セーフティをユーザーが構成できるようにする|
|[FavoritesBarEnabled](#favoritesbarenabled)|お気に入り バーを有効にする|
|[ForceBingSafeSearch](#forcebingsafesearch)|Bing セーフサーチを強制する|
|[ForceCertificatePromptsOnMultipleMatches](#forcecertificatepromptsonmultiplematches)|"AutoSelectCertificateForUrls" が構成されているサイトに対して複数の証明書が一致する場合、Microsoft Edge が自動的に証明書を選択するかどうかを構成する|
|[ForceEphemeralProfiles](#forceephemeralprofiles)|短期プロファイルの使用を有効にする|
|[ForceGoogleSafeSearch](#forcegooglesafesearch)|Google セーフサーチを強制する|
|[ForceLegacyDefaultReferrerPolicy](#forcelegacydefaultreferrerpolicy)|参照元がダウングレードされていない場合の既定の参照元ポリシーを使用する (廃止)|
|[ForceNetworkInProcess](#forcenetworkinprocess)|ブラウザー プロセスでネットワーク コードを強制的に実行する (不使用)|
|[ForceSync](#forcesync)|ブラウザーのデータを強制的に同期し、同期の同意プロンプトを表示しない|
|[ForceYouTubeRestrict](#forceyoutuberestrict)|最小限の YouTube 制限モードを強制的に実行する|
|[FullscreenAllowed](#fullscreenallowed)|全画面表示モードを許可する|
|[GloballyScopeHTTPAuthCacheEnabled](#globallyscopehttpauthcacheenabled)|グローバルにスコープが設定された HTTP 認証キャッシュを有効にする|
|[GoToIntranetSiteForSingleWordEntryInAddressBar](#gotointranetsiteforsinglewordentryinaddressbar)|アドレス バーへの 1 単語の入力による検索ではなく、ダイレクト イントラネット サイト ナビゲーションを強制的に実行する|
|[HSTSPolicyBypassList](#hstspolicybypasslist)|HSTS ポリシーのチェックをバイパスする名前の一覧を構成する|
|[HardwareAccelerationModeEnabled](#hardwareaccelerationmodeenabled)|使用可能な場合はハードウェア アクセラレータを使用する|
|[HideFirstRunExperience](#hidefirstrunexperience)|初回実行時のエクスペリエンスとスプラッシュ画面を非表示にする|
|[HideInternetExplorerRedirectUXForIncompatibleSitesEnabled](#hideinternetexplorerredirectuxforincompatiblesitesenabled)|Microsoft Edge でワンタイム リダイレクト ダイアログとバナーを非表示にする|
|[ImportAutofillFormData](#importautofillformdata)|オートフィル フォームのデータのインポートを許可する|
|[ImportBrowserSettings](#importbrowsersettings)|ブラウザーの設定のインポートを許可する|
|[ImportCookies](#importcookies)|Cookie のインポートを許可する|
|[ImportExtensions](#importextensions)|拡張機能のインポートを許可する|
|[ImportFavorites](#importfavorites)|お気に入りのインポートを許可する|
|[ImportHistory](#importhistory)|閲覧の履歴のインポートを許可する|
|[ImportHomepage](#importhomepage)|ホーム ページの設定のインポートを許可する|
|[ImportOpenTabs](#importopentabs)|開いているタブのインポートを許可する|
|[ImportPaymentInfo](#importpaymentinfo)|支払情報のインポートを許可する|
|[ImportSavedPasswords](#importsavedpasswords)|保存されたパスワードのインポートを許可する|
|[ImportSearchEngine](#importsearchengine)|検索エンジンの設定のインポートを許可する|
|[ImportShortcuts](#importshortcuts)|ショートカットのインポートを許可する|
|[InPrivateModeAvailability](#inprivatemodeavailability)|InPrivate モードの可用性を構成する|
|[InsecureFormsWarningsEnabled](#insecureformswarningsenabled)|セキュリティのないフォームに対する警告を有効にする|
|[IntensiveWakeUpThrottlingEnabled](#intensivewakeupthrottlingenabled)|IntensiveWakeUpThrottling 機能を制御する|
|[InternetExplorerIntegrationEnhancedHangDetection](#internetexplorerintegrationenhancedhangdetection)|Internet Explorer モードの拡張ハング検出を構成する|
|[InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel)|Internet Explorer 統合を構成する|
|[InternetExplorerIntegrationLocalFileAllowed](#internetexplorerintegrationlocalfileallowed)|Internet Explorer モードでローカル ファイルを起動できるようにする|
|[InternetExplorerIntegrationLocalFileExtensionAllowList](#internetexplorerintegrationlocalfileextensionallowlist)|Internet Explorer モードのローカル ファイルのファイル拡張子許可リストを開く|
|[InternetExplorerIntegrationLocalFileShowContextMenu](#internetexplorerintegrationlocalfileshowcontextmenu)|Internet Explorer モードでリンクを開くためのコンテキスト メニューを表示する|
|[InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist)|エンタープライズ モード サイト一覧を構成する|
|[InternetExplorerIntegrationSiteRedirect](#internetexplorerintegrationsiteredirect)|Internet Explorer モード ページから起動したときに未構成サイトへの「ページ内」ナビゲーションの動作を指定する|
|[InternetExplorerIntegrationTestingAllowed](#internetexplorerintegrationtestingallowed)|Internet Explorer モード テストを許可する|
|[IntranetRedirectBehavior](#intranetredirectbehavior)|イントラネット リダイレクトの動作|
|[IsolateOrigins](#isolateorigins)|特定のオリジンでのサイトの分離を有効にする|
|[LocalProvidersEnabled](#localprovidersenabled)|ローカル プロバイダーからのおすすめを許可する|
|[ManagedFavorites](#managedfavorites)|お気に入りを構成する|
|[ManagedSearchEngines](#managedsearchengines)|検索エンジンを管理する|
|[MaxConnectionsPerProxy](#maxconnectionsperproxy)|プロキシ サーバーへの同時接続の最大数|
|[MediaRouterCastAllowAllIPs](#mediaroutercastallowallips)|Google Cast がすべての IP アドレスのキャスト デバイスに接続できるようにする|
|[MetricsReportingEnabled](#metricsreportingenabled)|使用状況とクラッシュ関連のデータレポートを有効にする (廃止)|
|[NativeWindowOcclusionEnabled](#nativewindowocclusionenabled)|ネイティブ ウィンドウ オクルージョンを有効にする|
|[NavigationDelayForInitialSiteListDownloadTimeout](#navigationdelayforinitialsitelistdownloadtimeout)|エンタープライズ モード サイト一覧のタブ ナビゲーションの遅延時間を設定する|
|[NetworkPredictionOptions](#networkpredictionoptions)|ネットワーク予測を有効にする|
|[NonRemovableProfileEnabled](#nonremovableprofileenabled)|ユーザーが自分の職場または学校アカウントで自動的にログインする既定のプロファイルを常に持つかどうかを設定する|
|[OverrideSecurityRestrictionsOnInsecureOrigin](#overridesecurityrestrictionsoninsecureorigin)|セキュリティで保護されていないオリジンのセキュリティ制限が適用される場所を制御する|
|[PaymentMethodQueryEnabled](#paymentmethodqueryenabled)|利用可能な支払い方法について Web サイトがクエリを実行することを許可する|
|[PersonalizationReportingEnabled](#personalizationreportingenabled)|Microsoft に閲覧履歴を送信して、広告、検索、ニュースのカスタマイズを許可する|
|[PinningWizardAllowed](#pinningwizardallowed)|タスク バーへのピン留めウィザードを許可する|
|[ProactiveAuthEnabled](#proactiveauthenabled)|プロアクティブ認証を有効にする (非推奨)|
|[PromotionalTabsEnabled](#promotionaltabsenabled)|フルタブのプロモーション コンテンツを有効にする|
|[PromptForDownloadLocation](#promptfordownloadlocation)|ダウンロードしたファイルの保存場所を確認する|
|[QuicAllowed](#quicallowed)|QUIC プロトコルを許可する|
|[RedirectSitesFromInternetExplorerPreventBHOInstall](#redirectsitesfrominternetexplorerpreventbhoinstall)|Internet Explorer から Microsoft Edgeに互換性のないサイトを自動的にリダイレクトする|
|[RedirectSitesFromInternetExplorerRedirectMode](#redirectsitesfrominternetexplorerredirectmode)|互換性のないサイトを Internet Explorer から Microsoft Edgeに自動的にリダイレクトする|
|[RelaunchNotification](#relaunchnotification)|保留中の更新についてブラウザーの再起動が推奨されている、または必要であることをユーザーに通知する|
|[RelaunchNotificationPeriod](#relaunchnotificationperiod)|更新通知の期間を設定する|
|[RendererCodeIntegrityEnabled](#renderercodeintegrityenabled)|レンダラー コードの整合性を有効にする|
|[RequireOnlineRevocationChecksForLocalAnchors](#requireonlinerevocationchecksforlocalanchors)|ローカル トラスト アンカーにオンラインでの OCSP/CRL チェックが必要かどうかを指定する|
|[ResolveNavigationErrorsUseWebService](#resolvenavigationerrorsusewebservice)|Web サービスを使用したナビゲーション エラーの解決を有効にする|
|[RestrictSigninToPattern](#restrictsignintopattern)|Microsoft Edge のプライマリ アカウントとして使用できるアカウントを制限する|
|[RoamingProfileLocation](#roamingprofilelocation)|ローミング プロファイル ディレクトリを設定する|
|[RoamingProfileSupportEnabled](#roamingprofilesupportenabled)|Microsoft Edge プロファイル データのローミング コピーの使用を有効にする|
|[RunAllFlashInAllowMode](#runallflashinallowmode)|Adobe Flash のコンテンツ設定をすべてのコンテンツに拡張する (不使用)|
|[SSLErrorOverrideAllowed](#sslerroroverrideallowed)|HTTPS の警告ページから続行できるようにする|
|[SSLVersionMin](#sslversionmin)|最小限の TLS バージョンを有効にする|
|[SaveCookiesOnExit](#savecookiesonexit)|Microsoft Edge の終了時に cookie を保存する|
|[SavingBrowserHistoryDisabled](#savingbrowserhistorydisabled)|ブラウザー履歴の保存を無効にする|
|[ScreenCaptureAllowed](#screencaptureallowed)|画面キャプチャを許可または拒否する|
|[ScrollToTextFragmentEnabled](#scrolltotextfragmentenabled)|URL フラグメントで指定されたテキストへのスクロールを有効にする|
|[SearchSuggestEnabled](#searchsuggestenabled)|検索候補を有効にする|
|[SecurityKeyPermitAttestation](#securitykeypermitattestation)|直接的なセキュリティ キーの構成証明を使用するためのアクセス許可を必要としない Web サイトやドメイン|
|[SendIntranetToInternetExplorer](#sendintranettointernetexplorer)|すべてのイントラネット サイトを Internet Explorer に送る|
|[SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices)|Microsoft サービスを向上させるためにサイト情報を送信する (廃止)|
|[SensorsAllowedForUrls](#sensorsallowedforurls)|特定のサイトでのセンサーへのアクセスを許可する|
|[SensorsBlockedForUrls](#sensorsblockedforurls)|特定のサイトでのセンサーへのアクセスをブロックする|
|[SerialAskForUrls](#serialaskforurls)|特定のサイトでのシリアル API を許可する|
|[SerialBlockedForUrls](#serialblockedforurls)|特定のサイトでのシリアル API をブロックする|
|[ShowMicrosoftRewards](#showmicrosoftrewards)|Microsoft Rewards のエクスペリエンスを表示する|
|[ShowOfficeShortcutInFavoritesBar](#showofficeshortcutinfavoritesbar)|お気に入り バーにMicrosoft Office のショートカットを表示する (非推奨)|
|[SignedHTTPExchangeEnabled](#signedhttpexchangeenabled)|Signed HTTP Exchange (SXG) のサポートを有効にする|
|[SitePerProcess](#siteperprocess)|すべてのサイトでのサイトの分離を有効にする|
|[SpeechRecognitionEnabled](#speechrecognitionenabled)|Configure Speech Recognition|
|[SpellcheckEnabled](#spellcheckenabled)|スペルチェックを有効にする|
|[SpellcheckLanguage](#spellchecklanguage)|特定のスペルチェック言語を有効にする|
|[SpellcheckLanguageBlocklist](#spellchecklanguageblocklist)|スペルチェック言語の無効化を強制する|
|[StricterMixedContentTreatmentEnabled](#strictermixedcontenttreatmentenabled)|混在したコンテンツに対するより厳密な扱いを有効にする (非推奨)|
|[SuppressUnsupportedOSWarning](#suppressunsupportedoswarning)|サポートされていない OS の警告を非表示にする|
|[SyncDisabled](#syncdisabled)|Microsoft 同期サービスを使用してデータの同期を無効にする|
|[SyncTypesListDisabled](#synctypeslistdisabled)|同期から除外される種類の一覧を構成する|
|[TLS13HardeningForLocalAnchorsEnabled](#tls13hardeningforlocalanchorsenabled)|ローカル トラスト アンカーの TLS 1.3 セキュリティ機能を有効にする (不使用)|
|[TLSCipherSuiteDenyList](#tlsciphersuitedenylist)|無効にする TLS 暗号スイートを指定する|
|[TabFreezingEnabled](#tabfreezingenabled)|バックグラウンド タブのフリーズを許可する|
|[TargetBlankImpliesNoOpener](#targetblankimpliesnoopener)|_blank を対象とするリンクに window.opener を設定しない|
|[TaskManagerEndProcessEnabled](#taskmanagerendprocessenabled)|ブラウザーのタスク マネージャーで終了プロセスを有効にする|
|[TotalMemoryLimitMb](#totalmemorylimitmb)|Microsoft Edge インスタンス 1 つあたりの使用可能メモリ (MB) の制限を設定する|
|[TrackingPrevention](#trackingprevention)|ユーザーの Web 閲覧アクティビティの追跡のブロック|
|[TranslateEnabled](#translateenabled)|翻訳を有効にする|
|[URLAllowlist](#urlallowlist)|許可されている URL の一覧を定義する|
|[URLBlocklist](#urlblocklist)|URL の一覧へのアクセスをブロックする|
|[UpdatePolicyOverride](#updatepolicyoverride)|Microsoft Edge で利用できる更新プログラムを Microsoft Edge Update でどのように処理するかを指定します|
|[UserAgentClientHintsEnabled](#useragentclienthintsenabled)|ユーザー エージェント クライアント ヒント機能を有効にする (非推奨)|
|[UserDataDir](#userdatadir)|ユーザー データ ディレクトリを設定する|
|[UserDataSnapshotRetentionLimit](#userdatasnapshotretentionlimit)|緊急ロールバック時の使用のために保持するユーザーデータのスナップショット数を制限します。|
|[UserFeedbackAllowed](#userfeedbackallowed)|ユーザー フィードバックを許可する|
|[VerticalTabsAllowed](#verticaltabsallowed)|ブラウザーの側面にあるタブの垂直レイアウトの可用性を構成する|
|[VideoCaptureAllowed](#videocaptureallowed)|ビデオ キャプチャの許可またはブロック|
|[VideoCaptureAllowedUrls](#videocaptureallowedurls)|アクセス許可を要求することなくビデオ キャプチャ デバイスにアクセスできるサイト|
|[WPADQuickCheckEnabled](#wpadquickcheckenabled)|WPAD の最適化を設定する|
|[WebAppInstallForceList](#webappinstallforcelist)|強制インストールする Web アプリの一覧を構成する|
|[WebCaptureEnabled](#webcaptureenabled)|Microsoft Edge で Web キャプチャ機能を有効にする|
|[WebComponentsV0Enabled](#webcomponentsv0enabled)|M84 まで Web コンポーネント v0 API をもう一度有効にする (不使用)|
|[WebDriverOverridesIncompatiblePolicies](#webdriveroverridesincompatiblepolicies)|WebDriver が互換性のないポリシーを上書きすることを許可する (非推奨)|
|[WebRtcAllowLegacyTLSProtocols](#webrtcallowlegacytlsprotocols)|WebRTC で従来の TLS/DTLS ダウングレードを許可する (非推奨)|
|[WebRtcLocalIpsAllowedUrls](#webrtclocalipsallowedurls)|WebRTC によるローカル IP アドレスの公開を管理する|
|[WebRtcLocalhostIpHandling](#webrtclocalhostiphandling)|WebRTC によるローカル IP アドレスの公開を制限する|
|[WebRtcUdpPortRange](#webrtcudpportrange)|WebRTC が使用するローカル UDP ポートの範囲を制限する|
|[WebWidgetAllowed](#webwidgetallowed)|Web ウィジェットを許可する|
|[WebWidgetIsEnabledOnStartup](#webwidgetisenabledonstartup)|Windows 起動時に Web ウィジェットを有効にする|
|[WinHttpProxyResolverEnabled](#winhttpproxyresolverenabled)|Windows プロキシ リゾルバーを使用する (非推奨)|




  ## Application Guard の設定ポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### ApplicationGuardContainerProxy

  #### Application Guard コンテナー プロキシ

  
  
  #### サポートされているバージョン:

  - Windows での 84 以降

  #### 説明

  Microsoft Edge Application Guard のプロキシの設定を構成します。
このポリシーを有効にすると、Microsoft Edge Application Guard はプロキシ構成のその他のソースを無視します。

このポリシーを構成しない場合、Microsoft Edge Application Guard はホストのプロキシ構成を使用します。

このポリシーは、Application Guard (ホスト) 以外での Microsoft Edge のプロキシ構成には影響しません。

ProxyMode フィールドでは、Microsoft Edge Application Guard で使用するプロキシ サーバーを指定できます。

ProxyPacUrl フィールドはプロキシ .pac ファイルへの URL です。

ProxyServer フィールドはプロキシ サーバーの URL です。

'ProxyMode' として 'direct' の値を選択した場合、その他のフィールドはすべて無視されます。

"ProxyMode" として "auto_detect" の値を選択した場合、その他のフィールドはすべて無視されます。

'ProxyMode' として 'fixed_server' の値を選択した場合、'ProxyServer' フィールドが使用されます。

'ProxyMode' として 'pac_script' の値を選択した場合、'ProxyPacUrl' フィールドが使用されます。

デュアル プロキシを介した Application Guard トラフィックの識別の詳細については、[https://go.microsoft.com/fwlink/?linkid=2134653](https://go.microsoft.com/fwlink/?linkid=2134653)を参照してください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Dictionary

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ApplicationGuardContainerProxy
  - GP 名: Application Guard コンテナー プロキシ
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/Application Guard の設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ApplicationGuardContainerProxy
  - 値の種類: REG_SZ

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\ApplicationGuardContainerProxy = {
  "ProxyMode": "direct", 
  "ProxyPacUrl": "https://internal.site/example.pac", 
  "ProxyServer": "123.123.123.123:8080"
}
```

  ##### コンパクト サンプル値:

  ```
  SOFTWARE\Policies\Microsoft\Edge\ApplicationGuardContainerProxy = {"ProxyMode": "direct", "ProxyPacUrl": "https://internal.site/example.pac", "ProxyServer": "123.123.123.123:8080"}
  ```
  

  

  [ページのトップへ](#microsoft-edge---policies)

  ## キャストに関するポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### EnableMediaRouter

  #### Google Cast を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーを有効にすると、Google Cast が有効になります。 ユーザーは、[アプリ] メニュー、[ページ コンテキスト] メニュー、キャスト対応 Web サイトのメディア コントロール、(表示されていれば) [キャスト] ツール バーのアイコンから起動することができるようになります。

このポリシーを無効にすると、Google Cast が無効になります。

既定では、Google Cast は有効になっています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: EnableMediaRouter
  - GP 名: Google Cast を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/キャスト
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: EnableMediaRouter
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: EnableMediaRouter
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ShowCastIconInToolbar

  #### ツール バーにキャスト アイコンを表示する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーを true に設定すると、ツール バーや [オーバーフロー] メニューに [キャスト] ツール バーのアイコンが表示されます。 ユーザーが削除することはできません。

このポリシーを構成していない場合、またはこのポリシーを無効にしている場合、ユーザーは [コンテキスト] メニューを使用してアイコンをピン留めしたり、削除したりすることができます。

また、[EnableMediaRouter](#enablemediarouter) ポリシーを false に設定している場合、このポリシーは無視され、ツール バーのアイコンは表示されません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ShowCastIconInToolbar
  - GP 名: ツール バーにキャスト アイコンを表示する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/キャスト
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ShowCastIconInToolbar
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ShowCastIconInToolbar
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ## コンテンツの設定に関するポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### AutoSelectCertificateForUrls

  #### これらのサイトのクライアント証明書を自動的に選択する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ポリシーを設定すると、Microsoft Edge がクライアント証明書を自動的に選択できるサイトを指定する URL パターンのリストを作成できます。 値は文字列化された JSON 辞書の配列であり、それぞれの形式は { "pattern": "$URL_PATTERN", "filter" : $FILTER } です。ここで、$URL_PATTERN はコンテンツ設定パターンです。 $FILTER は、ブラウザが自動的に選択するクライアント証明書を制限します。 フィルターとは関係なく、サーバーの証明書要求に一致する証明書のみが選択されます。

$FILTER セクションの使用例:

* $FILTER が { "ISSUER": { "CN": "$ISSUER_CN" } } に設定されている場合、CommonName $ISSUER_CN の証明書によって発行されたクライアント証明書のみが選択されます。

* $FILTER に "ISSUER" セクションと "SUBJECT" セクションの両方が含まれている場合、両方の条件を満たすクライアント証明書のみが選択されます。

* $FILTER に "O" 値の "SUBJECT" セクションが含まれている場合、証明書を選択するには、指定した値に一致する組織が少なくとも 1 つ必要です。

* $FILTER に "OU" 値の "SUBJECT" セクションが含まれている場合、証明書を選択するには、指定した値に一致する組織単位が少なくとも 1 つ必要です。

* $FILTER が {} に設定されている場合、クライアント証明書の選択が追加で制限されることはありません。 Web サーバーが提供するフィルターが引き続き適用されることに注意してください。

ポリシーを未設定のままにすると、どのサイトに対しても自動選択は行われません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AutoSelectCertificateForUrls
  - GP 名: これらのサイトのクライアント証明書を自動的に選択する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\AutoSelectCertificateForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\AutoSelectCertificateForUrls\1 = "{\"pattern\":\"https://www.contoso.com\",\"filter\":{\"ISSUER\":{\"CN\":\"certificate issuer name\", \"L\": \"certificate issuer location\", \"O\": \"certificate issuer org\", \"OU\": \"certificate issuer org unit\"}, \"SUBJECT\":{\"CN\":\"certificate subject name\", \"L\": \"certificate subject location\", \"O\": \"certificate subject org\", \"OU\": \"certificate subject org unit\"}}}"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AutoSelectCertificateForUrls
  - サンプル値:
``` xml
<array>
  <string>{"pattern":"https://www.contoso.com","filter":{"ISSUER":{"CN":"certificate issuer name", "L": "certificate issuer location", "O": "certificate issuer org", "OU": "certificate issuer org unit"}, "SUBJECT":{"CN":"certificate subject name", "L": "certificate subject location", "O": "certificate subject org", "OU": "certificate subject org unit"}}}</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### CookiesAllowedForUrls

  #### 特定のサイトでの Cookie を許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Cookie の設定を許可するサイトの一覧を URL パターンに基づいて定義します。

このポリシーを構成していない場合、ユーザーの個人用の構成、または [DefaultCookiesSetting](#defaultcookiessetting) ポリシー (設定されている場合) からのグローバルな既定値がすべてのサイトで使用されます。

詳細については、[CookiesBlockedForUrls](#cookiesblockedforurls) と [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls) ポリシーを参照してください。

これらの 3 つのポリシー間で、競合する URL パターンを設定することはできません。

- [CookiesBlockedForUrls](#cookiesblockedforurls)

- CookiesAllowedForUrls

- [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls)

有効な URL パターンの詳細については、[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) をご覧ください。 * は、このポリシーで承認された値ではありません。

終了時に cookie を削除されないようにするには、 [SaveCookiesOnExit](#savecookiesonexit) ポリシーを構成します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: CookiesAllowedForUrls
  - GP 名: 特定のサイトでの Cookie を許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\CookiesAllowedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\CookiesAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CookiesAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: CookiesAllowedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### CookiesBlockedForUrls

  #### 特定のサイトでの Cookie のブロック

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Cookie を設定することができないサイトの一覧を URL パターンに基づいて定義します。

このポリシーを構成していない場合、ユーザーの個人用の構成、または [DefaultCookiesSetting](#defaultcookiessetting) ポリシー (設定されている場合) からのグローバルな既定値がすべてのサイトで使用されます。

詳細については、[CookiesAllowedForUrls](#cookiesallowedforurls) と [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls) ポリシーを参照してください。

これらの 3 つのポリシー間で、競合する URL パターンを設定することはできません。

- CookiesBlockedForUrls

- [CookiesAllowedForUrls](#cookiesallowedforurls)

- [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls)

有効な URL パターンの詳細については、[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) をご覧ください。 * は、このポリシーで承認された値ではありません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: CookiesBlockedForUrls
  - GP 名: 特定のサイトでの Cookie のブロック
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\CookiesBlockedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\CookiesBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CookiesBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: CookiesBlockedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### CookiesSessionOnlyForUrls

  #### 特定の Web サイトからの Cookie を現在のセッションに制限する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  定義した URL パターンに一致する Web サイトが作成した Cookie は、セッション終了時 (ウィンドウが閉じたとき) に削除されます。

パターンに一致しない Web サイトが作成した Cookie は、ユーザーの個人用の構成、または [DefaultCookiesSetting](#defaultcookiessetting) ポリシー (設定されている場合) によって制御されます。 これは、このポリシーを構成していない場合の既定動作でもあります。

Microsoft Edge がバックグラウンド モードで実行されている場合、最後のウィンドウが閉じたときにセッションが閉じない可能性があります。これは、ウィンドウが閉じたときに Cookie がクリアされないことを意味します。 Microsoft Edge がバックグラウンド モードで動作するときの構成については、[BackgroundModeEnabled](#backgroundmodeenabled) ポリシーを参照してください。

また、[CookieAllowedForUrls](#cookiesallowedforurls) と [CookieBlockedForUrls](#cookiesblockedforurls) ポリシーを使用して、Cookie を作成できる Web サイトを制御することもできます。

これらの 3 つのポリシー間で、競合する URL パターンを設定することはできません。

- [CookiesBlockedForUrls](#cookiesblockedforurls)

- [CookiesAllowedForUrls](#cookiesallowedforurls)

- CookiesSessionOnlyForUrls

有効な URL パターンの詳細については、[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) をご覧ください。 * は、このポリシーで承認された値ではありません。

[RestoreOnStartup](#restoreonstartup) ポリシーを設定して以前のセッションから URL を復元する場合、このポリシーは無視され、それらのサイトについての Cookie は永続的に保管されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: CookiesSessionOnlyForUrls
  - GP 名: 特定の Web サイトからの Cookie を現在のセッションに制限する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\CookiesSessionOnlyForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\CookiesSessionOnlyForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CookiesSessionOnlyForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: CookiesSessionOnlyForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultCookiesSetting

  #### Cookie を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Web サイトがユーザーのデバイス上で Cookie を作成できるかどうかを制御します。 このポリシーは、全体に対して適用するか、全く適用しないかのどちらかになります。すべての Web サイトが Cookie を作成できるようにするか、どの Web サイトにもクッキーを作成させないようにするかを選択します。 このポリシーを使用して、特定の Web サイトからの Cookie を有効にすることはできません。

ポリシーを "SessionOnly" に設定すると、セッションが閉じるときに Cookie がクリアされます。 Microsoft Edge がバックグラウンド モードで実行されている場合、最後のウィンドウが閉じたときにセッションが閉じない可能性があります。これは、ウィンドウが閉じたときに Cookie がクリアされないことを意味します。 Microsoft Edge がバックグラウンド モードで動作するときの構成については、[BackgroundModeEnabled](#backgroundmodeenabled) ポリシーを参照してください。

このポリシーを構成していない場合、既定の “AllowCookies" が使用され、ユーザーはこの設定を Microsoft Edge の設定で変更することができます。 (ユーザーがこの設定を変更できないようにしたい場合は、ポリシーを設定します。)

ポリシー オプション マッピング:

* AllowCookies (1) = すべてのサイトで Cookie を作成できるようにする

* BlockCookies (2) = どのサイトにも Cookie を作成させないようにする

* SessionOnly (4) = セッションの継続中に Cookie を保持する ([SaveCookiesOnExit](#savecookiesonexit) に記載されているものを除く)。

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultCookiesSetting
  - GP 名: Cookie を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultCookiesSetting
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultCookiesSetting
  - サンプル値:
``` xml
<integer>1</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultFileSystemReadGuardSetting

  #### 読み取り用にファイル システム API の使用を制御する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  このポリシーを 3 に設定すると、Web サイトでファイル システム API を使用して、ホスト オペレーティング システムのファイルシステムに対する読み取りアクセスを要求することができます。 このポリシーを 2 に設定すると、アクセスが拒否されます。

このポリシーを設定しない場合は、Web サイトでアクセスを要求することができます。 ユーザーはこの設定を変更できます。

ポリシー オプション マッピング:

* BlockFileSystemRead (2) = ファイル システム API を通してファイルとディレクトリへの読み取りアクセスを要求することはできません。

* AskFileSystemRead (3) = ファイル システム API を通してユーザーにファイルとディレクトリへの読み取りアクセス権を付与するよう要求することはできません。

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultFileSystemReadGuardSetting
  - GP 名: 読み取り用にファイル システム API の使用を制御する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultFileSystemReadGuardSetting
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultFileSystemReadGuardSetting
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultFileSystemWriteGuardSetting

  #### 書き込み用にファイル システム API の使用を制御する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  このポリシーを 3 に設定すると、Web サイトでファイル システム API を使用して、ホスト オペレーティング システムのファイルシステムに対する書き込みアクセスを要求することができます。 このポリシーを 2 に設定すると、アクセスが拒否されます。

このポリシーを設定しない場合は、Web サイトでアクセスを要求することができます。 ユーザーはこの設定を変更できます。

ポリシー オプション マッピング:

* BlockFileSystemWrite (2) = ファイルとディレクトリへの書き込みアクセスを要求することはできません。

* AskFileSystemWrite (3) = ユーザーにファイルとディレクトリへの書き込みアクセス権を付与するよう要求することはできません。

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultFileSystemWriteGuardSetting
  - GP 名: 書き込み用にファイル システム API の使用を制御する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultFileSystemWriteGuardSetting
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultFileSystemWriteGuardSetting
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultGeolocationSetting

  #### 既定の位置情報の設定

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Web サイトがユーザーの物理的な場所を追跡できるかどうかを設定します。 追跡を既定で許可したり ('AllowGeolocation')、既定で拒否したり ('BlockGeolocation')、Web サイトがユーザーの位置情報を要求するたびにユーザーに確認を求めたり ('AskGeolocation') することができます。

このポリシーを構成しない場合、'AskGeolocation' が使用され、ユーザーはこの設定を変更することができます。

ポリシー オプション マッピング:

* AllowGeolocation (1) = サイトがユーザーの物理的な場所を追跡できるようにする

* BlockGeolocation (2) = サイトがユーザーの物理的な場所を追跡できないようにする

* AskGeolocation (3) = サイトがユーザーの物理的な場所を追跡する場合は、必ず確認する

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultGeolocationSetting
  - GP 名: 既定の位置情報の設定
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultGeolocationSetting
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultGeolocationSetting
  - サンプル値:
``` xml
<integer>1</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultImagesSetting

  #### 既定の画像の設定

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Web サイトが画像を表示できるどうかを設定します。 すべてのサイトで画像を許可する ('AllowImages') か、すべてのサイトで画像をブロックする ('BlockImages') かを選択することができます。

このポリシーを構成していない場合、既定で画像が許可され、ユーザーはこの設定を変更することができます。

ポリシー オプション マッピング:

* AllowImages (1) = すべてのサイトに対してすべての画像の表示を許可する

* BlockImages (2) = すべてのサイトに対して画像の表示を許可しない

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultImagesSetting
  - GP 名: 既定の画像の設定
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultImagesSetting
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultImagesSetting
  - サンプル値:
``` xml
<integer>1</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultInsecureContentSetting

  #### 安全でないコンテンツの例外の使用を制御する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 80 以降

  #### 説明

  特定のサイトの混在したコンテンツを許可するために、ユーザーが例外を追加できるかどうかを設定することができます。

特定の URL パターンに対するこのポリシーは、[InsecureContentAllowedForUrls](#insecurecontentallowedforurls) と [InsecureContentBlockedForUrls](#insecurecontentblockedforurls) ポリシーを使用して、上書きすることができます。

このポリシーが設定されていない場合、ユーザーは、ブロック可能な混在したコンテンツを許可するための例外を追加し、任意でブロック可能な混在したコンテンツの自動アップグレードを無効にすることができます。

ポリシー オプション マッピング:

* BlockInsecureContent (2) = 混在したコンテンツの読み込みを、どのサイトにも、許可しない

* AllowExceptionsInsecureContent (3) = ユーザーが例外を追加して、混在したコンテンツを許可できるようにする

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultInsecureContentSetting
  - GP 名: 安全でないコンテンツの例外の使用を制御する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultInsecureContentSetting
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultInsecureContentSetting
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultJavaScriptSetting

  #### 既定の JavaScript の設定

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Web サイトが JavaScript を実行できるどうかを設定します。 すべてのサイトで使用できるようにする (' AllowJavaScript ') か、すべてのサイトに対してブロックすることができます (' BlockJavaScript ')。

このポリシーを構成していない場合、既定ですべてのサイトでの JavaScript の実行が許可され、ユーザーはこの設定を変更することができます。

ポリシー オプション マッピング:

* AllowJavaScript (1) = すべてのサイトで JavaScript の実行を許可する

* BlockJavaScript (2) = すべてのサイトで JavaScript の実行を許可しない

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultJavaScriptSetting
  - GP 名: 既定の JavaScript の設定
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultJavaScriptSetting
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultJavaScriptSetting
  - サンプル値:
``` xml
<integer>1</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultNotificationsSetting

  #### 既定の通知の設定

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Web サイトがデスクトップ通知を表示できるどうかを設定します。 デスクトップ通知を既定で許可したり ('AllowNotifications')、既定で拒否したり ('BlockNotifications')、Web サイトが通知を表示するたびにユーザーに確認を求めたり ('AskNotifications') することができます。

このポリシーを構成していない場合、既定で通知が許可され、ユーザーはこの設定を変更することができます。

ポリシー オプション マッピング:

* AllowNotifications (1) = サイトがデスクトップ通知を表示できるようにする

* BlockNotifications (2) = サイトがデスクトップ通知を表示できないようにする

* AskNotifications (3) = サイトがデスクトップ通知を表示するたびに確認を求める

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultNotificationsSetting
  - GP 名: 既定の通知の設定
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultNotificationsSetting
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultNotificationsSetting
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultPluginsSetting

  #### 既定の Adobe Flash 設定 (不使用)

  
  >不使用: このポリシーは廃止されており、Microsoft Edge 87 以降は機能しません。
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降、87 まで

  #### 説明

  Flash は Microsoft Edge でサポートされなくなったため、このポリシーは機能しません。

[PluginsAllowedForUrls](#pluginsallowedforurls) と [PluginsBlockedForUrls](#pluginsblockedforurls) が最初にチェックされ、その後、このポリシーがあります。 [ClickToPlay] と [BlockPlugins] のどちらかを選択できます。 このポリシーを ' BlockPlugins ' に設定すると、すべての web サイトでこのプラグインが拒否されます。 [ClickToPlay] は、フラッシュプラグインを実行しますが、ユーザーはプレースホルダーをクリックして起動します。

このポリシーを構成していない場合、ユーザーはこの設定を手動で変更することができます。

注: 自動再生は、[PluginsAllowedForUrls](#pluginsallowedforurls) ポリシーに明示的にリストされているドメインにのみ許可されます。 すべてのサイトに対して自動再生をオンにするには、許可されている Url のリストに http://* および https://* を追加します。

ポリシー オプション マッピング:

* BlockPlugins (2) = Adobe Flash プラグインをブロックする

* ClickToPlay (3) = クリックして再生する

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultPluginsSetting
  - GP 名: 既定の Adobe Flash 設定 (不使用)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultPluginsSetting
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultPluginsSetting
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultPopupsSetting

  #### 既定のポップアップ ウィンドウの設定

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Web サイトがポップアップ ウィンドウを表示できるかどうかを設定します。 すべての Web サイトでポップアップ ウィンドウを許可する ('AllowPopups') か、すべてのサイトでポップアップ ウィンドウをブロックする ('BlockPopups') かを選択することができます。

このポリシーを構成していない場合、既定でポップアップ ウィンドウがブロックされ、ユーザーはこの設定を変更することができます。

ポリシー オプション マッピング:

* AllowPopups (1) = すべてのサイトに対してポップアップの表示を許可する

* BlockPopups (2) = すべてのサイトに対してポップアップの表示を許可しない

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultPopupsSetting
  - GP 名: 既定のポップアップ ウィンドウの設定
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultPopupsSetting
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultPopupsSetting
  - サンプル値:
``` xml
<integer>1</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultWebBluetoothGuardSetting

  #### Web Bluetooth API の使用を制御する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Web サイトが近くの Bluetooth デバイスにアクセスできるかどうかを制御します。 アクセスを完全にブロックするか、サイトが Bluetooth デバイスにアクセスするときに毎回ユーザーに確認を求めるように設定することができます。

このポリシーを構成していない場合、既定値 ('AskWebBluetooth'、つまりユーザーが毎回確認を求められることを意味します) が使用され、ユーザーはこの設定を変更することができます。

ポリシー オプション マッピング:

* BlockWebBluetooth (2) = Web Bluetooth API を介して Bluetooth デバイスへのアクセスを要求するサイトを許可しない

* AskWebBluetooth (3) = 近くの Bluetooth デバイスへのアクセスを許可するようにサイトがユーザーに確認を求めることを許可する

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultWebBluetoothGuardSetting
  - GP 名: Web Bluetooth API の使用を制御する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultWebBluetoothGuardSetting
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultWebBluetoothGuardSetting
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultWebUsbGuardSetting

  #### WebUSB API の使用を制御する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Web サイトが接続されている USB デバイスにアクセスできるかどうかを設定します。 アクセスを完全にブロックするか、Web サイトが接続されている USB デバイスにアクセスするときに毎回ユーザーに確認を求めるように設定することができます。

特定の URL パターンに対するこのポリシーは、[WebUsbAskForUrls](#webusbaskforurls) と [WebUsbBlockedForUrls](#webusbblockedforurls) ポリシーを使用して、上書きすることができます。

このポリシーを構成していない場合、サイトは既定で接続された USB デバイス ('AskWebUsb') にアクセス可能かどうかをユーザーに確認することができ、ユーザーはこの設定を変更することができます。

ポリシー オプション マッピング:

* BlockWebUsb (2) = WebUSB API を介して USB デバイスへのアクセスを要求するサイトを許可しない

* AskWebUsb (3) = 接続されている USB デバイスへのアクセスを許可するようにサイトがユーザーに確認を求めることを許可する

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultWebUsbGuardSetting
  - GP 名: WebUSB API の使用を制御する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultWebUsbGuardSetting
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultWebUsbGuardSetting
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### FileSystemReadAskForUrls

  #### これらのサイトのファイル システム API を通して読み取りアクセスを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  ポリシーを設定すると、ファイル システム API を使用して、ユーザーにホスト オペレーティング システムのファイルまたはディレクトリに対する読み取りアクセス権を付与することを要求することができる URL パターンを指定できます。

ポリシーが設定されていないままだと、設定された場合に、[DefaultFileSystemReadGuardSetting](#defaultfilesystemreadguardsetting) がすべてのサイトに適用されます。 それ以外の場合、ユーザーの個人用設定が適用されます。

URL パターンは、 [FileSystemReadBlockedForUrls](#filesystemreadblockedforurls) と競合することはできません。 URL が両方と一致する場合、どちらのポリシーも優先されません。

有効な URL パターンの詳細については、https://cloud.google.com/docs/chrome-enterprise/policies/url-patterns をご覧ください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: FileSystemReadAskForUrls
  - GP 名: これらのサイトのファイル システム API を通して読み取りアクセスを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\FileSystemReadAskForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadAskForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadAskForUrls\2 = "[*.]example.edu"

```

  #### Mac の情報と設定
  
  - GP 固有の名前: FileSystemReadAskForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### FileSystemReadBlockedForUrls

  #### これらのサイトのファイル システム API を通して読み取りアクセスをブロックする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  このポリシーを設定した場合、ファイル システム API を使用して、ユーザーにホスト オペレーティング システムのファイルまたはディレクトリに対する読み取りアクセス権を付与することを要求することができる URL パターンを指定できます。

ポリシーが設定されない場合、設定された場合に、[DefaultFileSystemReadGuardSetting](#defaultfilesystemreadguardsetting) がすべてのサイトに適用されます。 それ以外の場合、ユーザーの個人用設定が適用されます。

URL パターンは、 [FileSystemReadAskForUrls](#filesystemreadaskforurls) と競合することはできません。 URL が両方と一致する場合、どちらのポリシーも優先されません。

有効な URL パターンの詳細については、https://cloud.google.com/docs/chrome-enterprise/policies/url-patterns をご覧ください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: FileSystemReadBlockedForUrls
  - GP 名: これらのサイトのファイル システム API を通して読み取りアクセスをブロックする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\FileSystemReadBlockedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadBlockedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadBlockedForUrls\2 = "[*.]example.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: FileSystemReadBlockedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### FileSystemWriteAskForUrls

  #### これらのサイトのファイルとディレクトリへの書き込みアクセスを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  このポリシーを設定した場合、ユーザーにホスト オペレーティング システムのファイルまたはディレクトリに対する書き込みアクセス権を付与することを要求することができる URL パターンを指定できます。

ポリシーが設定されない場合、設定された場合に、[DefaultFileSystemWriteGuardSetting](#defaultfilesystemwriteguardsetting) がすべてのサイトに適用されます。 それ以外の場合、ユーザーの個人用設定が適用されます。

URL パターンは、 [FileSystemWriteBlockedForUrls](#filesystemwriteblockedforurls) と競合することはできません。 URL が両方と一致する場合、どちらのポリシーも優先されません。

有効な URL パターンの詳細については、https://cloud.google.com/docs/chrome-enterprise/policies/url-patterns をご覧ください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: FileSystemWriteAskForUrls
  - GP 名: これらのサイトのファイルとディレクトリへの書き込みアクセスを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteAskForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteAskForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteAskForUrls\2 = "[*.]example.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: FileSystemWriteAskForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### FileSystemWriteBlockedForUrls

  #### これらのサイトのファイルとディレクトリへの書き込みアクセスをブロックする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  このポリシーを設定した場合、ユーザーにホスト オペレーティング システムのファイルまたはディレクトリに対する書き込みアクセス権を付与することを要求できなくする URL パターンを指定できます。

ポリシーが設定されない場合、設定された場合に、[DefaultFileSystemWriteGuardSetting](#defaultfilesystemwriteguardsetting) がすべてのサイトに適用されます。 それ以外の場合、ユーザーの個人用設定が適用されます。

URL パターンは、 [FileSystemWriteAskForUrls](#filesystemwriteaskforurls) と競合することはできません。 URL が両方と一致する場合、どちらのポリシーも優先されません。

有効な URL パターンの詳細については、https://cloud.google.com/docs/chrome-enterprise/policies/url-patterns をご覧ください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: FileSystemWriteBlockedForUrls
  - GP 名: これらのサイトのファイルとディレクトリへの書き込みアクセスをブロックする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteBlockedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteBlockedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteBlockedForUrls\2 = "[*.]example.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: FileSystemWriteBlockedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ImagesAllowedForUrls

  #### これらのサイトでの画像の使用を許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  画像を表示することができるサイトの一覧を URL パターンに基づいて定義します。

このポリシーを構成していない場合、ユーザーの個人用の構成、または [DefaultImagesSetting](#defaultimagessetting) ポリシー (設定されている場合) のいずれかからのグローバルな既定値が、すべてのサイトで使用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ImagesAllowedForUrls
  - GP 名: これらのサイトでの画像の使用を許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\ImagesAllowedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\ImagesAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\ImagesAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ImagesAllowedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ImagesBlockedForUrls

  #### 特定のサイトでの 画像 のブロック

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  画像の表示が許可されていないサイトの一覧を URL パターンに基づいて定義します。

このポリシーを構成していない場合、ユーザーの個人用の構成、または [DefaultImagesSetting](#defaultimagessetting) ポリシー (設定されている場合) からのグローバルな既定値がすべてのサイトで使用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ImagesBlockedForUrls
  - GP 名: 特定のサイトでの 画像 のブロック
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\ImagesBlockedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\ImagesBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\ImagesBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ImagesBlockedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### InsecureContentAllowedForUrls

  #### 特定のサイトでの安全でないコンテンツの使用を許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 80 以降

  #### 説明

  安全でない混在するコンテンツ（つまり、HTTPS サイトにある HTTP コンテンツ）を表示できるサイトを指定するための URL パターンの一覧を作成します。

このポリシーを構成していない場合、ブロック可能な混在するコンテンツがブロックされ、オプションでブロック可能な混在するコンテンツがアップグレードされます。 ただし、ユーザーは特定のサイトで安全でない混在するコンテンツを許可する例外を設定することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: InsecureContentAllowedForUrls
  - GP 名: 特定のサイトでの安全でないコンテンツの使用を許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\InsecureContentAllowedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\InsecureContentAllowedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\InsecureContentAllowedForUrls\2 = "[*.]example.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: InsecureContentAllowedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### InsecureContentBlockedForUrls

  #### 特定のサイトでの安全でないコンテンツのブロック

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 80 以降

  #### 説明

  URL パターンの一覧を作成して、ブロック可能な (つまりアクティブな) 混在するコンテンツ (つまり、HTTPS サイトにある HTTP コンテンツ) の表示を許可しないサイトと、オプションでブロック可能な混在するコンテンツのアップグレードを無効にするサイトを指定します。

このポリシーを構成していない場合、ブロック可能な混在するコンテンツがブロックされ、オプションでブロック可能な混在するコンテンツがアップグレードされます。 ただし、ユーザーは特定のサイトで安全でない混在するコンテンツを許可する例外を設定することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: InsecureContentBlockedForUrls
  - GP 名: 特定のサイトでの安全でないコンテンツのブロック
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\InsecureContentBlockedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\InsecureContentBlockedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\InsecureContentBlockedForUrls\2 = "[*.]example.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: InsecureContentBlockedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### JavaScriptAllowedForUrls

  #### 特定のサイトでの JavaScript を許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  JavaScript の実行が許可されているサイトの一覧を URL パターンに基づいて定義します。

このポリシーを構成していない場合、ユーザーの個人用の構成、または [DefaultJavaScriptSetting](#defaultjavascriptsetting) ポリシー (設定されている場合) からのグローバルな既定値がすべてのサイトで使用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: JavaScriptAllowedForUrls
  - GP 名: 特定のサイトでの JavaScript を許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\JavaScriptAllowedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\JavaScriptAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\JavaScriptAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: JavaScriptAllowedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### JavaScriptBlockedForUrls

  #### 特定のサイトでの JavaScript のブロック

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  JavaScript の実行が許可されていないサイトの一覧を URL パターンに基づいて定義します。

このポリシーを構成していない場合、ユーザーの個人用の構成、または [DefaultJavaScriptSetting](#defaultjavascriptsetting) ポリシー (設定されている場合) からのグローバルな既定値がすべてのサイトで使用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: JavaScriptBlockedForUrls
  - GP 名: 特定のサイトでの JavaScript のブロック
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\JavaScriptBlockedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\JavaScriptBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\JavaScriptBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: JavaScriptBlockedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### LegacySameSiteCookieBehaviorEnabled

  #### 既定のレガシ SameSite Cookie の動作設定を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 80 以降

  #### 説明

  すべての Cookie をレガシ SameSite の動作に戻します。 従来の動作に戻すと、SameSite 属性を指定しない Cookie は、"SameSite=None" であるかのように扱われ、"SameSite=None" Cookie が "Secure" 属性を保持する必要がなくなり、2 つのサイトが同じサイトであるかどうかを評価するときにスキームの比較がスキップされます。

このポリシーを設定しない場合、Cookie に対する既定の SameSite の動作は、SameSite-by-default 機能、Cookies-without-SameSite-must-be-secure 機能、および Schemeful Same-Site 機能の他の構成ソースに依存します。 これらの機能は、フィールド トライアルまたは edge://flags のsame-site-by-default-cookies フラグ、cookies-without-same-site-must-be-secure フラグ、または schemeful-same-site フラグによって構成することもできます。

ポリシー オプション マッピング:

* DefaultToLegacySameSiteCookieBehavior (1) = すべてのサイトの Cookie をレガシ SameSite の動作に戻す。

* DefaultToSameSiteByDefaultCookieBehavior (2) = すべてのサイトの Cookie に、SameSite-by-default の動作を使用する

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: LegacySameSiteCookieBehaviorEnabled
  - GP 名: 既定のレガシ SameSite Cookie の動作設定を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: LegacySameSiteCookieBehaviorEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: LegacySameSiteCookieBehaviorEnabled
  - サンプル値:
``` xml
<integer>1</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### LegacySameSiteCookieBehaviorEnabledForDomainList

  #### 特定のサイトで Cookie のレガシ SameSite の動作に戻す

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 80 以降

  #### 説明

  指定されたパターンに一致するドメインに設定された Cookie は、レガシ SameSite の動作に戻ります。

従来の動作に戻すと、SameSite 属性を指定しない Cookie は、"SameSite=None" であるかのように扱われ、"SameSite=None" Cookie が "Secure" 属性を保持する必要がなくなり、2 つのサイトが同じサイトであるかどうかを評価するときにスキームの比較がスキップされます。

このポリシーを設定していない場合、グローバルな既定値が使用されます。 グローバルな既定値では、指定したパターンの対象外ドメインの Cookie にも使用されます。

グローバルな既定値は、[LegacySameSiteCookieBehaviorEnabled](#legacysamesitecookiebehaviorenabled) ポリシーを使用して構成することができます。 [LegacySameSiteCookieBehaviorEnabled](#legacysamesitecookiebehaviorenabled) が設定されていない場合、グローバルな既定値がその他の構成ソースにフォールバックします。

このポリシーにリスト化したパターンは URL ではなくドメインとして扱われるので、スキームやポートを指定することはできません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: LegacySameSiteCookieBehaviorEnabledForDomainList
  - GP 名: 特定のサイトで Cookie のレガシ SameSite の動作に戻す
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\LegacySameSiteCookieBehaviorEnabledForDomainList
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\LegacySameSiteCookieBehaviorEnabledForDomainList\1 = "www.example.com"
SOFTWARE\Policies\Microsoft\Edge\LegacySameSiteCookieBehaviorEnabledForDomainList\2 = "[*.]example.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: LegacySameSiteCookieBehaviorEnabledForDomainList
  - サンプル値:
``` xml
<array>
  <string>www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### NotificationsAllowedForUrls

  #### 特定のサイトで通知を許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  通知の表示を許可するサイトを指定するための URL パターンのリストを作成できます。

このポリシーを設定していない場合、すべてのサイトにグローバルな既定値が使用されます。 この既定値は、[DefaultNotificationsSetting](#defaultnotificationssetting) ポリシーが設定されている場合はそのポリシーの値、またはユーザーの個人用の構成の値になります。 有効な URL パターンの詳細については、[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) をご覧ください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NotificationsAllowedForUrls
  - GP 名: 特定のサイトで通知を許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\NotificationsAllowedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\NotificationsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\NotificationsAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: NotificationsAllowedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### NotificationsBlockedForUrls

  #### 特定のサイトでの通知のブロック

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  通知の表示が許可されていないサイトを指定する URL パターンのリストを作成できます。

このポリシーを設定していない場合、すべてのサイトにグローバルな既定値が使用されます。 この既定値は、[DefaultNotificationsSetting](#defaultnotificationssetting) ポリシーが設定されている場合はそのポリシーの値、またはユーザーの個人用の構成の値になります。 有効な URL パターンの詳細については、[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) をご覧ください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NotificationsBlockedForUrls
  - GP 名: 特定のサイトでの通知のブロック
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\NotificationsBlockedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\NotificationsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\NotificationsBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: NotificationsBlockedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PluginsAllowedForUrls

  #### 特定のサイトでの Adobe Flash プラグインの使用を許可する (不使用)

  
  >不使用: このポリシーは廃止されており、Microsoft Edge 87 以降は機能しません。
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降、87 まで

  #### 説明

  Flash は Microsoft Edge でサポートされなくなったため、このポリシーは機能しません。

Adobe Flash プラグインを実行することができるサイトの一覧を URL パターンに基づいて定義します。

このポリシーを構成していない場合、ユーザーの個人用の構成、または [DefaultPluginsSetting](#defaultpluginssetting) ポリシー (設定されている場合) からのグローバルな既定値がすべてのサイトで使用されます。

有効な URL パターンの詳細については、[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) をご覧ください。 ただし、M85以降では、ホストで「\*」および「[\*.]」のワイルドカードを使用したパターンは、このポリシーではサポートされなくなりました。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PluginsAllowedForUrls
  - GP 名: 特定のサイトでの Adobe Flash プラグインの使用を許可する (不使用)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\PluginsAllowedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\PluginsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PluginsAllowedForUrls\2 = "http://contoso.edu:8080"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PluginsAllowedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>http://contoso.edu:8080</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PluginsBlockedForUrls

  #### 特定のサイトでの Adobe Flash プラグインの使用をブロックする (不使用)

  
  >不使用: このポリシーは廃止されており、Microsoft Edge 87 以降は機能しません。
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降、87 まで

  #### 説明

  Flash は Microsoft Edge でサポートされなくなったため、このポリシーは機能しません。

Adobe Flash プラグインの実行がブロックされているサイトの一覧を URL パターンに基づいて定義します。

このポリシーを構成していない場合、ユーザーの個人用の構成、または [DefaultPluginsSetting](#defaultpluginssetting) ポリシー (設定されている場合) からのグローバルな既定値がすべてのサイトで使用されます。

有効な URL パターンの詳細については、[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) をご覧ください。 ただし、M85以降では、ホストで「\*」および「[\*.]」のワイルドカードを使用したパターンは、このポリシーではサポートされなくなりました。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PluginsBlockedForUrls
  - GP 名: 特定のサイトでの Adobe Flash プラグインの使用をブロックする (不使用)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\PluginsBlockedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\PluginsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PluginsBlockedForUrls\2 = "http://contoso.edu:8080"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PluginsBlockedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>http://contoso.edu:8080</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PopupsAllowedForUrls

  #### 特定のサイトでのポップアップ ウィンドウの表示を許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ポップアップ ウィンドウを開くことができるサイトの一覧を URL パターンに基づいて定義します。

このポリシーを構成していない場合、ユーザーの個人用の構成、または [DefaultPopupsSetting](#defaultpopupssetting) ポリシー (設定されている場合) からのグローバルな既定値がすべてのサイトで使用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PopupsAllowedForUrls
  - GP 名: 特定のサイトでのポップアップ ウィンドウの表示を許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\PopupsAllowedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\PopupsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PopupsAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PopupsAllowedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PopupsBlockedForUrls

  #### 特定のサイトでのポップアップ ウィンドウのブロック

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ポップアップ ウィンドウのオープンがブロックされているサイトの一覧を URL パターンに基づいて定義します。

このポリシーを構成していない場合、ユーザーの個人用の構成、または [DefaultPopupsSetting](#defaultpopupssetting) ポリシー (設定されている場合) からのグローバルな既定値がすべてのサイトで使用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PopupsBlockedForUrls
  - GP 名: 特定のサイトでのポップアップ ウィンドウのブロック
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\PopupsBlockedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\PopupsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PopupsBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PopupsBlockedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### RegisteredProtocolHandlers

  #### プロトコル ハンドラーを登録する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  プロトコル ハンドラーの一覧を登録するには、このポリシーを設定します (推奨のみ)。 このリストは、ユーザーが登録したリストと結合され、両方を使用できます。

プロトコル ハンドラーを登録するには:

- プロトコル プロパティをスキームに設定します (例: "mailto")
- "protocol" フィールドで指定されたスキームを処理するアプリケーションの URL プロパティに、URL プロパティを設定します。 パターンには "%s" プレースホルダーを含めることができ、これは処理された URL に置き換えられます。

ユーザーは、このポリシーによって登録されたプロトコル ハンドラーを削除できません。 ただし、新しい既定のプロトコル ハンドラーをインストールし、既存のプロトコル ハンドラーを上書きすることができます。

  #### サポートされている機能:

  - 必須にすることができるか: いいえ
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Dictionary

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: RegisteredProtocolHandlers
  - GP 名: プロトコル ハンドラーを登録する
  - GP パス (必須): なし
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/コンテンツの設定
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): なし
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: RegisteredProtocolHandlers
  - 値の種類: REG_SZ

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\RegisteredProtocolHandlers = [
  {
    "default": true, 
    "protocol": "mailto", 
    "url": "https://mail.contoso.com/mail/?extsrc=mailto&url=%s"
  }
]
```

  ##### コンパクト サンプル値:

  ```
  SOFTWARE\Policies\Microsoft\Edge\RegisteredProtocolHandlers = [{"default": true, "protocol": "mailto", "url": "https://mail.contoso.com/mail/?extsrc=mailto&url=%s"}]
  ```
  

  #### Mac の情報と設定
  
  - 基本設定キーの名前: RegisteredProtocolHandlers
  - サンプル値:
``` xml
<key>RegisteredProtocolHandlers</key>
<array>
  <dict>
    <key>default</key>
    <true/>
    <key>protocol</key>
    <string>mailto</string>
    <key>url</key>
    <string>https://mail.contoso.com/mail/?extsrc=mailto&url=%s</string>
  </dict>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SpotlightExperiencesAndRecommendationsEnabled

  #### ユーザーがカスタマイズされた背景画像およびテキスト、提案、通知を受け取ることができるようにするかどうか選択する
そしてMicrosoft サービスのヒントも受け取るのかどうか

  
  
  #### サポートされているバージョン:

  - Windows での 86 以降

  #### 説明

  ユーザーがカスタマイズされた背景画像およびテキスト、提案、通知、Microsoft サービスのヒントを受信できるかどうかを選択します。

この設定を有効にした場合、またはこの設定を構成しなかった場合は、スポットライトの機能と推奨事項が有効になります。

この設定を無効にした場合は、スポットライトのエクスペリエンスと推奨事項が無効になります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SpotlightExperiencesAndRecommendationsEnabled
  - [GP name]: カスタマイズされた背景画像およびテキスト、提案、通知、Microsoft サービスのヒントをユーザーが受信できるかどうかを選択します。
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: SpotlightExperiencesAndRecommendationsEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### WebUsbAllowDevicesForUrls

  #### 特定の USB デバイスに接続するために、特定のサイトへのアクセスを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  指定されたベンダー ID と製品 ID を持つ USB デバイスへのアクセス許可を自動的に付与するサイトを指定する URL の一覧を設定します。 ポリシーを有効にするには、一覧の各項目にデバイスと URL の両方が含まれている必要があります。 デバイス内の各項目には、ベンダー ID と製品 ID のフィールドを含めることができます。 省略された ID は、1 つの例外を除いてワイルドカードとして扱われます。その例外とは、ベンダー ID を指定しない限り製品 ID を指定することができないという点です。 それ以外の場合、そのポリシーは有効にならず、無視されます。

USB アクセス許可モデルは、要求しているサイトの URL ("要求 URL") とトップレベル フレーム サイトの URL ("埋め込み URL") を使用して、要求 URL に USB デバイスへのアクセス許可を付与します。 要求しているサイトが iframe で読み込まれたときに、要求 URL が埋め込み URL と異なる場合があります。 したがって、"urls" フィールドには、コンマで区切られた最大 2 つの URL 文字列を含めることができ、要求 URL と埋め込み URL をそれぞれに指定することができます。 1 つの URL のみを指定した場合、埋め込みの状態に関係なく、要求しているサイトの URL がこの URL と一致した場合に、対応する USB デバイスへのアクセス許可が付与されます。 "urls" 内の URL は有効な URL である必要があり、それ以外の場合にはポリシーは無視されます。

このポリシーを設定していない場合、[DefaultWebUsbGuardSetting](#defaultwebusbguardsetting) ポリシー (設定されている場合) またはユーザーの個人用の構成からのグローバルな既定値がすべてのサイトで使用されます。

このポリシーの URL パターンは、[WebUsbBlockedForUrls](#webusbblockedforurls) を介して構成されたものと競合することはできません。 競合する場合、このポリシーは [WebUsbBlockedForUrls](#webusbblockedforurls) や [WebUsbAskForUrls](#webusbaskforurls) よりも優先されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Dictionary

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: WebUsbAllowDevicesForUrls
  - GP 名: 特定の USB デバイスに接続するために、特定のサイトへのアクセスを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: WebUsbAllowDevicesForUrls
  - 値の種類: REG_SZ

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\WebUsbAllowDevicesForUrls = [
  {
    "devices": [
      {
        "product_id": 5678, 
        "vendor_id": 1234
      }
    ], 
    "urls": [
      "https://contoso.com", 
      "https://fabrikam.com"
    ]
  }
]
```

  ##### コンパクト サンプル値:

  ```
  SOFTWARE\Policies\Microsoft\Edge\WebUsbAllowDevicesForUrls = [{"devices": [{"product_id": 5678, "vendor_id": 1234}], "urls": ["https://contoso.com", "https://fabrikam.com"]}]
  ```
  

  #### Mac の情報と設定
  
  - 基本設定キーの名前: WebUsbAllowDevicesForUrls
  - サンプル値:
``` xml
<key>WebUsbAllowDevicesForUrls</key>
<array>
  <dict>
    <key>devices</key>
    <array>
      <dict>
        <key>product_id</key>
        <integer>5678</integer>
        <key>vendor_id</key>
        <integer>1234</integer>
      </dict>
    </array>
    <key>urls</key>
    <array>
      <string>https://contoso.com</string>
      <string>https://fabrikam.com</string>
    </array>
  </dict>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### WebUsbAskForUrls

  #### 特定のサイトでの WebUSB を許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  USB デバイスへのアクセスをユーザーに対して確認することができるサイトの一覧を URL パターンに基づいて定義します。

このポリシーを構成していない場合、ユーザーの個人用の構成、または [DefaultWebUsbGuardSetting](#defaultwebusbguardsetting) ポリシー (設定されている場合) からのグローバルな既定値がすべてのサイトで使用されます。

このポリシーで定義された URL パターンは、[WebUsbBlockedForUrls](#webusbblockedforurls) ポリシーで構成されたものと競合することはできません。URL を許可することも、ブロックすることもできません。 有効な URL パターンの詳細については、[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) をご覧ください

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: WebUsbAskForUrls
  - GP 名: 特定のサイトでの WebUSB を許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\WebUsbAskForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\WebUsbAskForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\WebUsbAskForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: WebUsbAskForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### WebUsbBlockedForUrls

  #### 特定のサイトでの WebUSB のブロック

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  USB デバイスへのアクセス権の付与をユーザーに対して確認することができないサイトの一覧を URL パターンに基づいて定義します。

このポリシーを構成していない場合、ユーザーの個人用の構成、または [DefaultWebUsbGuardSetting](#defaultwebusbguardsetting) ポリシー (設定されている場合) からのグローバルな既定値がすべてのサイトで使用されます。

このポリシーの URL パターンは、[WebUsbAskForUrls](#webusbaskforurls) ポリシーで構成されたものと競合することはできません。 URL を許可することも、ブロックすることもできません。  有効な URL パターンの詳細については、[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) をご覧ください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: WebUsbBlockedForUrls
  - GP 名: 特定のサイトでの WebUSB のブロック
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/コンテンツの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\WebUsbBlockedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\WebUsbBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\WebUsbBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: WebUsbBlockedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ## 既定の検索プロバイダーに関するポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultSearchProviderEnabled

  #### 既定の検索プロバイダーを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  既定の検索プロバイダーを使用する機能を有効にします。

このポリシーを有効にしている場合、ユーザーは用語をアドレス バーに入力して検索することができます (入力するものが URL ではない場合のみ)。

残りの既定の検索ポリシーを有効にすることで、使用する既定の検索プロバイダーを指定することができます。 これらが空のまま (構成されていない)、または正しく構成されていない場合、ユーザーは既定のプロバイダーを選択することができます。

このポリシーを無効にしている場合、ユーザーはアドレス バーから検索することができなくなります。

このポリシーを有効または無効にしている場合、ユーザーはポリシーを変更したり上書きしたりすることができなくなります。

このポリシーを構成していない場合、既定の検索プロバイダーが有効になり、ユーザーは既定の検索プロバイダーを選択し、検索プロバイダーの一覧を設定することができます。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM の使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

Microsoft Edge 84 以降、このポリシーは推奨されるポリシーとして設定できます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultSearchProviderEnabled
  - GP 名: 既定の検索プロバイダーを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/既定の検索プロバイダー
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/既定の検索プロバイダー
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: DefaultSearchProviderEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultSearchProviderEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultSearchProviderEncodings

  #### 既定の検索プロバイダー エンコード

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  検索プロバイダーがサポートする文字エンコードを指定します。 エンコードは、UTF-8、GB2312、ISO-8859-1 などのコード ページ名です。 それらは提供された順序で試行されます。

このポリシーは省略可能です。 構成されていない場合、既定値である UTF-8 が使用されます。

このポリシーは、[DefaultSearchProviderEnabled](#defaultsearchproviderenabled) と [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) ポリシーを有効にした場合にのみ適用されます。

Microsoft Edge 84 以降、このポリシーは推奨されるポリシーとして設定できます。 ユーザーが既に既定の検索プロバイダーを設定している場合、この推奨ポリシーによって構成された既定の検索プロバイダーは、ユーザーが選択できる検索プロバイダーの一覧に追加されません。 必要な動作である場合は、[ManagedSearchEngines](#managedsearchengines) ポリシーを使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultSearchProviderEncodings
  - GP 名: 既定の検索プロバイダー エンコード
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/既定の検索プロバイダー
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/既定の検索プロバイダー
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended\DefaultSearchProviderEncodings
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\1 = "UTF-8"
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\2 = "UTF-16"
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\3 = "GB2312"
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\4 = "ISO-8859-1"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultSearchProviderEncodings
  - サンプル値:
``` xml
<array>
  <string>UTF-8</string>
  <string>UTF-16</string>
  <string>GB2312</string>
  <string>ISO-8859-1</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultSearchProviderImageURL

  #### 既定の検索プロバイダーの画像による検索機能を指定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  画像検索に使用する検索エンジンの URL を指定します。 検索要求は、GET メソッドを使用して送信されます。

このポリシーは省略可能です。 構成していない場合、画像検索を使用することはできません。

Bing の画像検索 URL を、"{bing:baseURL}images/detail/search?iss=sbiupload&FORM=ANCMS1#enterInsights" として指定します。

Google の画像検索 URL を、"{google:baseURL}searchbyimage/upload" として指定します。

画像検索の構成を終了する方法については、[DefaultSearchProviderImageURLPostParams](#defaultsearchproviderimageurlpostparams) ポリシーを参照してください。

このポリシーは、[DefaultSearchProviderEnabled](#defaultsearchproviderenabled) と [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) ポリシーを有効にした場合にのみ適用されます。

Microsoft Edge 84 以降、このポリシーは推奨されるポリシーとして設定できます。 ユーザーが既に既定の検索プロバイダーを設定している場合、この推奨ポリシーによって構成された既定の検索プロバイダーは、ユーザーが選択できる検索プロバイダーの一覧に追加されません。 必要な動作である場合は、[ManagedSearchEngines](#managedsearchengines) ポリシーを使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultSearchProviderImageURL
  - GP 名: 既定の検索プロバイダーの画像による検索機能を指定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/既定の検索プロバイダー
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/既定の検索プロバイダー
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: DefaultSearchProviderImageURL
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"https://search.contoso.com/searchbyimage/upload"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultSearchProviderImageURL
  - サンプル値:
``` xml
<string>https://search.contoso.com/searchbyimage/upload</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultSearchProviderImageURLPostParams

  #### POST を使用する画像 URL のパラメーター

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーを有効にしている場合、このポリシーは POST を使用して画像検索を行うときに使用するパラメーターを指定します。 ポリシーは、コンマで区切られた名前と値のペアで構成されています。 前の例の {imageThumbnail} のように値がテンプレート パラメーターである場合、これは実際の画像サムネイル データで置き換えられます。 このポリシーは、[DefaultSearchProviderEnabled](#defaultsearchproviderenabled) と [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) ポリシーを有効にした場合にのみ適用されます。

Bing の画像検索 URL のポスト パラメータを、"imageBin={google:imageThumbnailBase64}" として指定します。

Google の画像検索 URL のポスト パラメータを、"encoded_image={google:imageThumbnail},image_url={google:imageURL},sbisrc={google:imageSearchSource},original_width={google:imageOriginalWidth},original_height={google:imageOriginalHeight}" として指定します。

このポリシーを設定していない場合、画像検索要求は GET メソッドを使用して送信されます。

Microsoft Edge 84 以降、このポリシーは推奨されるポリシーとして設定できます。 ユーザーが既に既定の検索プロバイダーを設定している場合、この推奨ポリシーによって構成された既定の検索プロバイダーは、ユーザーが選択できる検索プロバイダーの一覧に追加されません。 必要な動作である場合は、[ManagedSearchEngines](#managedsearchengines) ポリシーを使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultSearchProviderImageURLPostParams
  - GP 名: POST を使用する画像 URL のパラメーター
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/既定の検索プロバイダー
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/既定の検索プロバイダー
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: DefaultSearchProviderImageURLPostParams
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"content={imageThumbnail},url={imageURL},sbisrc={SearchSource}"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultSearchProviderImageURLPostParams
  - サンプル値:
``` xml
<string>content={imageThumbnail},url={imageURL},sbisrc={SearchSource}</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultSearchProviderKeyword

  #### 既定の検索プロバイダーのキーワード

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このプロバイダーの検索をトリガーするためにアドレス バーで使用されるショートカットとして、キーワードを指定します。

このポリシーは省略可能です。 構成していない場合、キーワードは検索プロバイダーをアクティブ化しません。

このポリシーは、[DefaultSearchProviderEnabled](#defaultsearchproviderenabled) と [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) ポリシーを有効にした場合にのみ適用されます。

Microsoft Edge 84 以降、このポリシーは推奨されるポリシーとして設定できます。 ユーザーが既に既定の検索プロバイダーを設定している場合、この推奨ポリシーによって構成された既定の検索プロバイダーは、ユーザーが選択できる検索プロバイダーの一覧に追加されません。 必要な動作である場合は、[ManagedSearchEngines](#managedsearchengines) ポリシーを使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultSearchProviderKeyword
  - GP 名: 既定の検索プロバイダーのキーワード
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/既定の検索プロバイダー
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/既定の検索プロバイダー
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: DefaultSearchProviderKeyword
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"mis"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultSearchProviderKeyword
  - サンプル値:
``` xml
<string>mis</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultSearchProviderName

  #### 既定の検索プロバイダー名

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  既定の検索プロバイダー名を指定します。

このポリシーを有効にしている場合、既定の検索プロバイダー名が設定されます。

このポリシーを有効にしていないか、空のままにしている場合、検索 URL で指定されたホスト名が使用されます。

"DefaultSearchProviderName" には、DTBC-0008 で設定されている暗号化された検索プロバイダーに対応した組織承認済みの暗号化された検索プロバイダーを設定する必要があります。 このポリシーは、[DefaultSearchProviderEnabled](#defaultsearchproviderenabled) と [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) ポリシーを有効にした場合にのみ適用されます。

Microsoft Edge 84 以降、このポリシーは推奨されるポリシーとして設定できます。 ユーザーが既に既定の検索プロバイダーを設定している場合、この推奨ポリシーによって構成された既定の検索プロバイダーは、ユーザーが選択できる検索プロバイダーの一覧に追加されません。 必要な動作である場合は、[ManagedSearchEngines](#managedsearchengines) ポリシーを使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultSearchProviderName
  - GP 名: 既定の検索プロバイダー名
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/既定の検索プロバイダー
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/既定の検索プロバイダー
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: DefaultSearchProviderName
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"My Intranet Search"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultSearchProviderName
  - サンプル値:
``` xml
<string>My Intranet Search</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultSearchProviderSearchURL

  #### 既定の検索プロバイダーの検索 URL

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  既定の検索に使用する検索エンジンの URL を指定します。 URL には文字列 "{searchTerms}" が含まれており、この文字列はクエリ時にユーザーが検索する用語で置き換えられます。

Bing の検索 URL を次のように指定します。

"{bing:baseURL}search?q={searchTerms}"。

Google の検索 URL を、"{google:baseURL}search?q={searchTerms}&{google:RLZ}{google:originalQueryForSuggestion}{google:assistedQueryStats}{google:searchFieldtrialParameter}{google:searchClient}{google:sourceId}ie={inputEncoding}" として指定します。

このポリシーは、[DefaultSearchProviderEnabled](#defaultsearchproviderenabled) ポリシーを有効にしている場合に必要です。後者のポリシーを有効にしていない場合、このポリシーは無視されます。

Microsoft Edge 84 以降、このポリシーは推奨されるポリシーとして設定できます。 ユーザーが既に既定の検索プロバイダーを設定している場合、この推奨ポリシーによって構成された既定の検索プロバイダーは、ユーザーが選択できる検索プロバイダーの一覧に追加されません。 必要な動作である場合は、[ManagedSearchEngines](#managedsearchengines) ポリシーを使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultSearchProviderSearchURL
  - GP 名: 既定の検索プロバイダーの検索 URL
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/既定の検索プロバイダー
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/既定の検索プロバイダー
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: DefaultSearchProviderSearchURL
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"https://search.contoso.com/search?q={searchTerms}"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultSearchProviderSearchURL
  - サンプル値:
``` xml
<string>https://search.contoso.com/search?q={searchTerms}</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultSearchProviderSuggestURL

  #### 検索候補用の既定の検索プロバイダーの URL

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  検索候補の提供に使用する検索エンジンの URL を指定します。 URL には文字列 "{searchTerms}" が含まれており、この文字列はクエリ時にユーザーがこれまでに入力したテキストで置き換えられます。

このポリシーは省略可能です。 構成していない場合、ユーザーには検索候補が表示されません。閲覧の履歴とお気に入りからの候補が表示されます。

Bing の候補 URL は、次のように指定することができます。

"{bing:baseURL}qbox?query={searchTerms}"。

Google の候補 URL は、"{google:baseURL}complete/search?output=chrome&q={searchTerms}" として指定することができます。

このポリシーは、[DefaultSearchProviderEnabled](#defaultsearchproviderenabled) と [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) ポリシーを有効にした場合にのみ適用されます。

Microsoft Edge 84 以降、このポリシーは推奨されるポリシーとして設定できます。 ユーザーが既に既定の検索プロバイダーを設定している場合、この推奨ポリシーによって構成された既定の検索プロバイダーは、ユーザーが選択できる検索プロバイダーの一覧に追加されません。 必要な動作である場合は、[ManagedSearchEngines](#managedsearchengines) ポリシーを使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultSearchProviderSuggestURL
  - GP 名: 提案用の既定の検索プロバイダーの URL
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/既定の検索プロバイダー
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/既定の検索プロバイダー
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: DefaultSearchProviderSuggestURL
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"https://search.contoso.com/suggest?q={searchTerms}"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultSearchProviderSuggestURL
  - サンプル値:
``` xml
<string>https://search.contoso.com/suggest?q={searchTerms}</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### NewTabPageSearchBox

  #### 新しいタブページ検索ボックスの機能を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 85 以降

  #### 説明

  新しいタブで検索する場合は、新しいタブ ページの検索ボックスを [検索ボックス (推奨)] または [アドレス バー] を使用して設定できます。 このポリシーは、次の 2 つのポリシーを設定して、検索エンジンを Bing 以外の値に設定した場合にのみ機能します: [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) と [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl)。

 このポリシーを無効にしているか、構成していない場合、次のようになります:

- アドレス バーの既定の検索エンジンが Bing の場合、新しいタブ ページは検索ボックスを使用して新しいタブを検索します。
- アドレス バーの既定の検索エンジンが Bing ではない場合、新しいタブを検索するときに、ユーザーに追加の選択肢 ([アドレスバー] を使用) が提供されます。


このポリシーを有効にすると、次のようになります:

- [検索ボックス (推奨)] (bing)、新しいタブ ページは検索ボックスを使用して新しいタブを検索します。
- [アドレス バー] (リダイレクト)、新しいタブ ページの検索ボックスはアドレス バーを使用して新しいタブを検索します。

ポリシー オプション マッピング:

* bing (bing) = 検索ボックス (推奨)

* リダイレクト (リダイレクト) = アドレス バー

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NewTabPageSearchBox
  - GP 名: 新しいタブ ページ検索ボックスの機能を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/既定の検索プロバイダー
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/既定の検索プロバイダー
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: NewTabPageSearchBox
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"bing"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: NewTabPageSearchBox
  - サンプル値:
``` xml
<string>bing</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ## 拡張機能に関するポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### BlockExternalExtensions

  #### 外部拡張機能がインストールされないようにブロックする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 88 以降

  #### 説明

  外部拡張機能のインストールを制御します。

この設定を有効にすると、外部拡張機能はインストールされないようにブロックされます。

この設定を無効にした場合、または未設定のままにした場合、外部拡張機能のインストールは許可されます。

外部拡張機能とそのインストールについては、https://docs.microsoft.com/microsoft-edge/extensions-chromium/developer-guide/alternate-distribution-options で文書化されています。


  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: BlockExternalExtensions
  - GP 名: 外部拡張機能がインストールされないようにブロックする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/拡張機能
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: BlockExternalExtensions
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キー名: BlockExternalExtensions
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ExtensionAllowedTypes

  #### 許可されている拡張機能の種類を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ポリシーを設定することにより、Microsoft Edge にインストール可能なアプリや拡張機能、操作可能なホスト、ランタイム アクセスの制限を制御します。

このポリシーを設定しない場合、使用可能な拡張機能やアプリの種類に制限はありません。

リストにない種類の拡張機能やアプリはインストールされません。 それぞれの値は、次の文字列のいずれかである必要があります。

* "extension"

* "theme"

* "user_script"

* "hosted_app"

これらの種類の詳細については、「Microsoft Edge extensions documentation (Microsoft Edge 拡張機能ドキュメント)」を参照してください。

注: このポリシーは、[ExtensionInstallForcelist](#extensioninstallforcelist) を使用して強制インストールされる拡張機能やアプリにも影響します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ExtensionAllowedTypes
  - GP 名: 許可されている拡張機能の種類を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/拡張機能
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\ExtensionAllowedTypes
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionAllowedTypes\1 = "hosted_app"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ExtensionAllowedTypes
  - サンプル値:
``` xml
<array>
  <string>hosted_app</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ExtensionInstallAllowlist

  #### 特定の拡張機能のインストールを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーを設定すると、ブロックリストの対象ではない拡張機能が指定されます。

ブロックリスト値 * は、すべての拡張機能がブロックされ、ユーザーがインストールできるのは許可リストに記載されている拡張機能のみです。

既定では、すべての拡張機能が許可されています。 ただし、ポリシーによって拡張機能を禁止した場合は、許可されている拡張機能の一覧を使用してそのポリシーを変更できます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ExtensionInstallAllowlist
  - GP 名: 特定の拡張機能のインストールを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/拡張機能
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallAllowlist
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallAllowlist\1 = "extension_id1"
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallAllowlist\2 = "extension_id2"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ExtensionInstallAllowlist
  - サンプル値:
``` xml
<array>
  <string>extension_id1</string>
  <string>extension_id2</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ExtensionInstallBlocklist

  #### インストールできない拡張機能を制御する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ユーザーがインストールできない拡張機能を指定できます。 既にインストールされている拡張機能は、ユーザーが有効にする方法はなく、ブロックされた場合に無効になります。 無効化された拡張機能がブロックリストから削除されると、自動的に再有効化されます。

ブロックリスト値 '\*' は、allowlist に明示的に表示されていない限り、すべての拡張機能がブロックされます。

このポリシーが設定されていない場合、ユーザーは Microsoft Edge に任意の拡張機能をインストールできます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ExtensionInstallBlocklist
  - GP 名: インストールできない拡張機能を制御する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/拡張機能
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallBlocklist
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallBlocklist\1 = "extension_id1"
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallBlocklist\2 = "extension_id2"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ExtensionInstallBlocklist
  - サンプル値:
``` xml
<array>
  <string>extension_id1</string>
  <string>extension_id2</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ExtensionInstallForcelist

  #### 警告なしにインストールする拡張機能を制御する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーを設定すると、ユーザーの操作なしに自動的にインストールされるアプリや拡張機能の一覧が指定されます。 ユーザーがこの設定をアンインストールしたり、オフにしたりすることはできません。 アクセス許可は暗黙的に付与されます。これには enterprise.deviceAttributes や enterprise.platformKeys 拡張機能 API が含まれます。 注: これら 2 つの API は、強制インストールされていないアプリや拡張機能では使用できません。

このポリシーを設定していない場合、アプリや拡張機能は自動インストールされず、ユーザーは Microsoft Edge で任意のアプリをアンインストールすることができます。

このポリシーは、[ExtensionInstallBlocklist](#extensioninstallblocklist) ポリシーよりも優先されます。 以前に強制インストールされたアプリや拡張機能がこの一覧から削除された場合、Microsoft Edge はそのアプリや拡張機能を自動的にアンインストールします。

Microsoft Windows インスタンスでは、Microsoft Edge アドオン Web サイト以外からのアプリや拡張機能については、インスタンスが Microsoft Active Directory ドメインに参加しており、Windows 10 Pro を実行している場合にのみ、強制的にインストールすることができます。

macOS インスタンスでは、Microsoft Edge アドオン Web サイト以外からのアプリや拡張機能については、インスタンスが MDM 経由で管理されているか、MCX 経由でドメインに参加している場合にのみ、強制的にインストールすることができます。

ユーザーは開発者ツールを使用して任意の拡張機能のソース コードを変更することができ、その結果として拡張機能が正常に機能しなくなる可能性があります。 これが問題となる場合には、DeveloperToolsDisabled ポリシーを構成します。

ポリシーの各リスト アイテムは、拡張機能 ID と、セミコロン (;) で区切られたオプションの "更新" URL を含む文字列です。 拡張機能 ID は 32 文字の文字列で、たとえば開発者モードの場合には、edge://extensions で見つけることができます。 指定する場合には、"更新" URL は更新プログラム マニフェスト XML ドキュメント ([https://go.microsoft.com/fwlink/?linkid=2095043](https://go.microsoft.com/fwlink/?linkid=2095043)) を指している必要があります。 既定では、Microsoft Edge アドオン Web サイトの更新 URL が使用されます。 このポリシーで設定されている "更新" URL は、初回のインストールにのみ使用され、以降の拡張機能の更新では、拡張機能のマニフェスト内の更新 URL が使用されます。

注: このポリシーは InPrivate モードには適用されません。 拡張機能のホスティングについて読む (https://docs.microsoft.com/microsoft-edge/extensions-chromium/enterprise/hosting-and-updating)。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ExtensionInstallForcelist
  - GP 名: 警告なしにインストールする拡張機能を制御する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/拡張機能
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallForcelist
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallForcelist\1 = "gbchcmhmhahfdphkhkmpfmihenigjmpp;https://edge.microsoft.com/extensionwebstorebase/v1/crx"
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallForcelist\2 = "abcdefghijklmnopabcdefghijklmnop"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ExtensionInstallForcelist
  - サンプル値:
``` xml
<array>
  <string>gbchcmhmhahfdphkhkmpfmihenigjmpp;https://edge.microsoft.com/extensionwebstorebase/v1/crx</string>
  <string>abcdefghijklmnopabcdefghijklmnop</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ExtensionInstallSources

  #### 拡張機能とユーザー スクリプトのインストール ソースを構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  拡張機能やテーマをインストールできる URL を定義します。

パッケージを edge://extensions ページにドラッグ アンド ドロップすることなく、拡張機能やテーマを直接インストールできる URL を定義します。

このリストの各項目は、拡張子スタイルの一致パターンです ([https://go.microsoft.com/fwlink/?linkid=2095039](https://go.microsoft.com/fwlink/?linkid=2095039) を参照してください)。 ユーザーは、このリストの項目に一致する URL から簡単にアイテムをインストールすることができます。 *.crx ファイルの場所と、ダウンロードを開始するページ (つまり参照元) の両方が、これらのパターンで許可されている必要があります。 認証が必要な場所では、ファイルをホストしないでください。

[ExtensionInstallBlocklist](#extensioninstallblocklist) ポリシーは、このポリシーよりも優先されます。 ブロック リストに登録されている拡張機能は、このリストに登録されているサイトからのものであっても、インストールされません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ExtensionInstallSources
  - GP 名: 拡張機能とユーザー スクリプトのインストール ソースを構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/拡張機能
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallSources
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallSources\1 = "https://corp.contoso.com/*"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ExtensionInstallSources
  - サンプル値:
``` xml
<array>
  <string>https://corp.contoso.com/*</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ExtensionSettings

  #### 拡張機能管理設定を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーを設定すると、既存の拡張機能関連ポリシーによって制御される設定を含め、Microsoft Edge の拡張機能管理設定が制御されます。 このポリシーは、設定されている可能性がある従来のポリシーより優先されます。

このポリシーは、拡張機能 ID または更新 URL を特定の設定にのみマップします。 特別な ID "*" に対して既定の構成を設定できます。この構成は、このポリシーのカスタム構成なしですべての拡張機能に適用されます。 更新 URL を使用すると、拡張機能マニフェスト ( [https://go.microsoft.com/fwlink/?linkid=2095043](https://go.microsoft.com/fwlink/?linkid=2095043) )に記載されている正確な更新 URL を持つ拡張機能に構成が適用されます。

特定のサード パーティ ストアの拡張機能をブロックするには、そのストアの update_url をブロックする必要があります。 たとえば、Chrome Web ストアの拡張機能をブロックする場合は、次の JSON を使用できます。

{"update_url: https://clients2.google.com/service/update2/crx ":{"installation_mode":"blocked"}}

前の例で JSON を使用してストアがブロックされている場合でも、[ExtensionInstallForcelist](#extensioninstallforcelist) と [ExtensionInstallAllowlist](#extensioninstallallowlist) を使用して特定の拡張機能のインストールを許可または強制することができることに注意してください。

注: Microsoft Active Directory ドメインに参加していない Windows インスタンスの場合、強制インストールは Microsoft Edge アドオン Web サイトに記載されているアプリと拡張機能に限定されます。


  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Dictionary

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ExtensionSettings
  - GP 名: 拡張機能管理設定を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/拡張機能
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ExtensionSettings
  - 値の種類: REG_SZ

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings = {
  "*": {
    "allowed_types": [
      "hosted_app"
    ], 
    "blocked_install_message": "Custom error message.", 
    "blocked_permissions": [
      "downloads", 
      "bookmarks"
    ], 
    "install_sources": [
      "https://company-intranet/apps"
    ], 
    "installation_mode": "blocked", 
    "runtime_allowed_hosts": [
      "*://good.contoso.com"
    ], 
    "runtime_blocked_hosts": [
      "*://*.contoso.com"
    ]
  }, 
  "abcdefghijklmnopabcdefghijklmnop": {
    "blocked_permissions": [
      "history"
    ], 
    "installation_mode": "allowed", 
    "minimum_version_required": "1.0.1"
  }, 
  "bcdefghijklmnopabcdefghijklmnopa": {
    "allowed_permissions": [
      "downloads"
    ], 
    "installation_mode": "force_installed", 
    "runtime_allowed_hosts": [
      "*://good.contoso.com"
    ], 
    "runtime_blocked_hosts": [
      "*://*.contoso.com"
    ], 
    "update_url": "https://contoso.com/update_url"
  }, 
  "cdefghijklmnopabcdefghijklmnopab": {
    "blocked_install_message": "Custom error message.", 
    "installation_mode": "blocked"
  }, 
  "defghijklmnopabcdefghijklmnopabc,efghijklmnopabcdefghijklmnopabcd": {
    "blocked_install_message": "Custom error message.", 
    "installation_mode": "blocked"
  }, 
  "fghijklmnopabcdefghijklmnopabcde": {
    "blocked_install_message": "Custom removal message.", 
    "installation_mode": "removed"
  }, 
  "update_url:https://www.contoso.com/update.xml": {
    "allowed_permissions": [
      "downloads"
    ], 
    "blocked_permissions": [
      "wallpaper"
    ], 
    "installation_mode": "allowed"
  }
}
```

  ##### コンパクト サンプル値:

  ```
  SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings = {"*": {"allowed_types": ["hosted_app"], "blocked_install_message": "Custom error message.", "blocked_permissions": ["downloads", "bookmarks"], "install_sources": ["https://company-intranet/apps"], "installation_mode": "blocked", "runtime_allowed_hosts": ["*://good.contoso.com"], "runtime_blocked_hosts": ["*://*.contoso.com"]}, "abcdefghijklmnopabcdefghijklmnop": {"blocked_permissions": ["history"], "installation_mode": "allowed", "minimum_version_required": "1.0.1"}, "bcdefghijklmnopabcdefghijklmnopa": {"allowed_permissions": ["downloads"], "installation_mode": "force_installed", "runtime_allowed_hosts": ["*://good.contoso.com"], "runtime_blocked_hosts": ["*://*.contoso.com"], "update_url": "https://contoso.com/update_url"}, "cdefghijklmnopabcdefghijklmnopab": {"blocked_install_message": "Custom error message.", "installation_mode": "blocked"}, "defghijklmnopabcdefghijklmnopabc,efghijklmnopabcdefghijklmnopabcd": {"blocked_install_message": "Custom error message.", "installation_mode": "blocked"}, "fghijklmnopabcdefghijklmnopabcde": {"blocked_install_message": "Custom removal message.", "installation_mode": "removed"}, "update_url:https://www.contoso.com/update.xml": {"allowed_permissions": ["downloads"], "blocked_permissions": ["wallpaper"], "installation_mode": "allowed"}}
  ```
  

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ExtensionSettings
  - サンプル値:
``` xml
<key>ExtensionSettings</key>
<dict>
  <key>*</key>
  <dict>
    <key>allowed_types</key>
    <array>
      <string>hosted_app</string>
    </array>
    <key>blocked_install_message</key>
    <string>Custom error message.</string>
    <key>blocked_permissions</key>
    <array>
      <string>downloads</string>
      <string>bookmarks</string>
    </array>
    <key>install_sources</key>
    <array>
      <string>https://company-intranet/apps</string>
    </array>
    <key>installation_mode</key>
    <string>blocked</string>
    <key>runtime_allowed_hosts</key>
    <array>
      <string>*://good.contoso.com</string>
    </array>
    <key>runtime_blocked_hosts</key>
    <array>
      <string>*://*.contoso.com</string>
    </array>
  </dict>
  <key>abcdefghijklmnopabcdefghijklmnop</key>
  <dict>
    <key>blocked_permissions</key>
    <array>
      <string>history</string>
    </array>
    <key>installation_mode</key>
    <string>allowed</string>
    <key>minimum_version_required</key>
    <string>1.0.1</string>
  </dict>
  <key>bcdefghijklmnopabcdefghijklmnopa</key>
  <dict>
    <key>allowed_permissions</key>
    <array>
      <string>downloads</string>
    </array>
    <key>installation_mode</key>
    <string>force_installed</string>
    <key>runtime_allowed_hosts</key>
    <array>
      <string>*://good.contoso.com</string>
    </array>
    <key>runtime_blocked_hosts</key>
    <array>
      <string>*://*.contoso.com</string>
    </array>
    <key>update_url</key>
    <string>https://contoso.com/update_url</string>
  </dict>
  <key>cdefghijklmnopabcdefghijklmnopab</key>
  <dict>
    <key>blocked_install_message</key>
    <string>Custom error message.</string>
    <key>installation_mode</key>
    <string>blocked</string>
  </dict>
  <key>defghijklmnopabcdefghijklmnopabc,efghijklmnopabcdefghijklmnopabcd</key>
  <dict>
    <key>blocked_install_message</key>
    <string>Custom error message.</string>
    <key>installation_mode</key>
    <string>blocked</string>
  </dict>
  <key>fghijklmnopabcdefghijklmnopabcde</key>
  <dict>
    <key>blocked_install_message</key>
    <string>Custom removal message.</string>
    <key>installation_mode</key>
    <string>removed</string>
  </dict>
  <key>update_url:https://www.contoso.com/update.xml</key>
  <dict>
    <key>allowed_permissions</key>
    <array>
      <string>downloads</string>
    </array>
    <key>blocked_permissions</key>
    <array>
      <string>wallpaper</string>
    </array>
    <key>installation_mode</key>
    <string>allowed</string>
  </dict>
</dict>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ## HTTP 認証に関するポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### AllowCrossOriginAuthPrompt

  #### cross-origin HTTP 認証プロンプトを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ページ上のサードパーティの画像に認証プロンプトを表示するかどうかを制御します。

通常、これはフィッシング詐欺への防御として無効になっています。 このポリシーを設定しない場合、ポリシーは無効になり、サードパーティの画像は認証プロンプトを表示できません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AllowCrossOriginAuthPrompt
  - GP 名: cross-origin HTTP 認証プロンプトを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/HTTP 認証
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AllowCrossOriginAuthPrompt
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AllowCrossOriginAuthPrompt
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AuthNegotiateDelegateAllowlist

  #### Microsoft Edge がユーザーの資格情報を委任できるサーバーの一覧を指定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge が委任できるサーバーの一覧を構成します。

複数のサーバー名をコンマで区切ります。 ワイルドカード (*) を指定することができます。

このポリシーを構成していない場合、サーバーがイントラネットとして検出された場合でも、Microsoft Edge はユーザーの資格情報を委任しません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AuthNegotiateDelegateAllowlist
  - GP 名: Microsoft Edge がユーザーの資格情報を委任できるサーバーの一覧を指定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/HTTP 認証
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AuthNegotiateDelegateAllowlist
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"contoso.com"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AuthNegotiateDelegateAllowlist
  - サンプル値:
``` xml
<string>contoso.com</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AuthSchemes

  #### サポートされる認証スキーム

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  サポートされる HTTP 認証スキームを指定します。

"basic"、"digest"、"ntlm"、"negotiate" の値を使用してポリシーを構成することができます。 コンマで複数の値を区切ります。

このポリシーを構成していない場合、4 つのスキームがすべて使用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AuthSchemes
  - GP 名: サポートされる認証スキーム
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/HTTP 認証
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AuthSchemes
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"basic,digest,ntlm,negotiate"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AuthSchemes
  - サンプル値:
``` xml
<string>basic,digest,ntlm,negotiate</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AuthServerAllowlist

  #### 許可されている認証サーバーの一覧を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  統合認証を有効にするサーバーを指定します。 統合認証が有効になるのは、Microsoft Edge がプロキシまたはこのリスト内のサーバーから認証チャレンジを受信した場合のみです。

複数のサーバー名をコンマで区切ります。 ワイルドカード (*) を指定することができます。

このポリシーを構成していない場合、Microsoft Edge はサーバーがイントラネット上にあるかどうかを検出しようと試みます。その後でのみ、IWA の要求に応答します。 サーバーがインターネット上にある場合、サーバーからの IWA 要求は Microsoft Edge により無視されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AuthServerAllowlist
  - GP 名: 許可されている認証サーバーの一覧を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/HTTP 認証
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AuthServerAllowlist
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"*contoso.com,contoso.com"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AuthServerAllowlist
  - サンプル値:
``` xml
<string>*contoso.com,contoso.com</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### BasicAuthOverHttpEnabled

  #### HTTP の基本認証を許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 88 以降

  #### 説明

  このポリシーを有効にした場合、または未設定のままにした場合は、セキュリティで保護されていない HTTP で受け取った基本認証チャレンジが許可されます。

このポリシーを無効にした場合は、基本認証スキームでセキュリティ保護されていない HTTP 要求はブロックされ、セキュリティで保護された HTTPS だけが許可されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - 一意の GP 名: BasicAuthOverHttpEnabled
  - GP 名: HTTP の基本認証を許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/HTTP 認証
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: BasicAuthOverHttpEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - Preference Key Name: BasicAuthOverHttpEnabled
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DisableAuthNegotiateCnameLookup

  #### Kerberos 認証をネゴシエートするときの CNAME ルックアップを無効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  生成された Kerberos SPN が正規 DNS 名 (CNAME) に基づいているか、入力された元の名前に基づいているかを決定します。

このポリシーを有効にすると、CNAME ルックアップはスキップされ、サーバー名 (入力されたもの) が使用されます。

このポリシーを無効にしているか、構成していない場合、サーバーの正規名が使用されます。  これは、CNAME ルックアップを通して決定されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DisableAuthNegotiateCnameLookup
  - GP 名: Kerberos 認証をネゴシエートするときの CNAME ルックアップを無効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/HTTP 認証
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DisableAuthNegotiateCnameLookup
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DisableAuthNegotiateCnameLookup
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### EnableAuthNegotiatePort

  #### Kerberos SPN に標準以外のポートを含める

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  生成された Kerberos SPN に標準以外のポートを含める必要があるかどうかを指定します。

このポリシーを有効にしているか、ユーザが URL に標準以外のポート (80 または 443 以外のポート) を含めている場合、そのポートは生成された Kerberos SPN に含まれます。

このポリシーを設定していないか、無効にしている場合、生成された Kerberos SPN にはどのような場合でもポートは含まれません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: EnableAuthNegotiatePort
  - GP 名: Kerberos SPN に標準以外のポートを含める
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/HTTP 認証
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: EnableAuthNegotiatePort
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: EnableAuthNegotiatePort
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### NtlmV2Enabled

  #### NTLMv2 認証を有効にするかどうかを制御する

  
  
  #### サポートされているバージョン:

  - macOS での 77 以降

  #### 説明

  NTLMv2 を有効にするかどうかを制御します。

Samba と Windows Server の最新バージョンは、すべて NTLMv2 をサポートしています。 NTLMv2 を無効にすると認証のセキュリティが低下するため、下位互換性に関する問題に対処しなければならない場合にのみ無効にします。

このポリシーを構成していない場合、NTLMv2 は既定で有効になります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  

  #### Mac の情報と設定
  
  - 基本設定キーの名前: NtlmV2Enabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ## キオスク モードの設定ポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### KioskAddressBarEditingEnabled

  #### キオスクモードのパブリックブラウザーのエクスペリエンスを編集するアドレスバーを構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 87 以降

  #### 説明

  このポリシーは、パブリック ブラウジングエ クスペリエンスを使用しているときの Microsoft Edge キオスクモードにのみ適用されます。

このポリシーを有効にすると、ユーザーがアドレスバーのURLを変更できなくなります。

このポリシーを無効にするか、構成しなかった場合、ユーザーはアドレスバーのURLを変更できます。

キオスク モードの構成の詳細については、「[https://go.microsoft.com/fwlink/?linkid=2137578](https://go.microsoft.com/fwlink/?linkid=2137578)」を参照してください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: KioskAddressBarEditingEnabled
  - GP 名: キオスクモードのパブリックブラウザーのエクスペリエンスを編集するアドレスバーを構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/キオスク モードの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - GP 一意の名前: KioskAddressBarEditingEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 設定キー名: KioskAddressBarEditingEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### KioskDeleteDownloadsOnExit

  #### Microsoft Edge が閉じたときに、キオスク セッションの一部としてダウンロードされたファイルを削除する

  
  
  #### サポートされているバージョン:

  - Windows での 87 以降

  #### 説明

  このポリシーは、Microsoft Edge キオスクモードにのみ適用されます。

このポリシーを有効にすると、キオスク セッションの一部としてダウンロードされたファイルは、Microsoft Edge が閉じるたびに削除されます。

このポリシーを無効にするか、構成しない場合、キオスク セッションの一部としてダウンロードされたファイルは、Microsoft Edge を閉じても削除されません。

キオスク モードの構成の詳細については、「[https://go.microsoft.com/fwlink/?linkid=2137578](https://go.microsoft.com/fwlink/?linkid=2137578)」を参照してください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: KioskDeleteDownloadsOnExit
  - GP 名: Microsoft Edge が閉じたときに、キオスク セッションの一部としてダウンロードされたファイルを削除する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/キオスク モードの設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: KioskDeleteDownloadsOnExit
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ## ネイティブ メッセージングに関するポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### NativeMessagingAllowlist

  #### ユーザーが使用できるネイティブ メッセージング ホストを制御する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ポリシーを設定すると、拒否リストの対象とされないネイティブ メッセージング ホストが指定されます。 拒否リストの値 * は、明示的に許可されていない限り、すべてのネイティブ メッセージング ホストが拒否されるという意味です。

既定では、すべてのネイティブ メッセージング ホストが許可されます。 ただし、ネイティブ メッセージング ホストがポリシーによって拒否された場合、管理者は許可リストを使用してそのポリシーを変更できます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NativeMessagingAllowlist
  - GP 名: ユーザーが使用できるネイティブ メッセージング ホストを制御する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/ネイティブ メッセージング
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\NativeMessagingAllowlist
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingAllowlist\1 = "com.native.messaging.host.name1"
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingAllowlist\2 = "com.native.messaging.host.name2"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: NativeMessagingAllowlist
  - サンプル値:
``` xml
<array>
  <string>com.native.messaging.host.name1</string>
  <string>com.native.messaging.host.name2</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### NativeMessagingBlocklist

  #### ネイティブ メッセージング ブロック リストを構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーを設定すると、読み込まれてはならないネイティブ メッセージング ホストが指定されます。 拒否リストの値 * は、明示的に許可されていない限り、すべてのネイティブ メッセージング ホストが拒否されるという意味です。

このポリシーを未設定のままにすると、Microsoft Edge はインストール済みのすべてのネイティブ メッセージング ホストを読み込みます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NativeMessagingBlocklist
  - GP 名: ネイティブ メッセージング ブロック リストを構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/ネイティブ メッセージング
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\NativeMessagingBlocklist
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingBlocklist\1 = "com.native.messaging.host.name1"
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingBlocklist\2 = "com.native.messaging.host.name2"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: NativeMessagingBlocklist
  - サンプル値:
``` xml
<array>
  <string>com.native.messaging.host.name1</string>
  <string>com.native.messaging.host.name2</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### NativeMessagingUserLevelHosts

  #### (管理者のアクセス許可なしでインストールされた) ユーザー レベルのネイティブ メッセージング ホストを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーを [有効] に設定した場合、または未設定のままにした場合、Microsoft Edge では、ユーザー レベルでインストールされているネイティブ メッセージング ホストを使用できます。

このポリシーを無効に設定した場合、Microsoft Edge は、システム レベルでインストールされている場合にのみ、これらのホストを使用できます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NativeMessagingUserLevelHosts
  - GP 名: (管理者のアクセス許可なしでインストールされた) ユーザー レベルのネイティブ メッセージング ホストを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/ネイティブ メッセージング
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: NativeMessagingUserLevelHosts
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: NativeMessagingUserLevelHosts
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ## パスワード マネージャーと保護に関するポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### PasswordManagerEnabled

  #### パスワードをパスワード マネージャーに保存できるようにする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge がユーザーのパスワードを保存できるようにします。

このポリシーを有効にしている場合、ユーザーは Microsoft Edge に自分のパスワードを保存することができます。 次回ユーザーがこのサイトにアクセスするときには、Microsoft Edge が自動的にパスワードを入力します。

このポリシーを無効にしている場合、ユーザーは新しいパスワードを保存することはできませんが、以前保存したパスワードを使用することはできます。

このポリシーを有効または無効にしている場合、ユーザーは Microsoft Edge でポリシーを変更したり上書きしたりすることができなくなります。 構成していない場合、ユーザーはこの機能をオフにするだけでなく、パスワードを保存することもできます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PasswordManagerEnabled
  - GP 名: パスワードをパスワード マネージャーに保存できるようにする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/パスワード マネージャーと保護
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/パスワード マネージャーと保護
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: PasswordManagerEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PasswordManagerEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PasswordMonitorAllowed

  #### パスワードが安全でないことが判明した場合にユーザーに警告することを許可する

  
  
  #### サポートされているバージョン:

  - Windows での 85 以降

  #### 説明

  Microsoft Edge でユーザー パスワードの監視を許可します。

このポリシーを有効にし、ユーザーがポリシーを有効にすることに同意すると、Microsoft Edge に保存されているパスワードのいずれかが安全ではないと判明した場合、ユーザーに警告が表示されます。 Microsoft Edge には警告が表示されます。この情報は、[設定] > [パスワード] > [パスワード モニター] でも確認できます。

このポリシーを無効にすると、ユーザーはこの機能を有効にするためのアクセス許可を求められません。 パスワードはスキャンされず、警告も出されません。

ポリシーを有効にするか構成しなかった場合、ユーザーはこの機能を有効または無効にすることができます。

Microsoft Edge が安全でないパスワードを検出する方法の詳細については、[https://go.microsoft.com/fwlink/?linkid=2133833](https://go.microsoft.com/fwlink/?linkid=2133833) を参照してください

追加のガイダンス:

このポリシーは、[おすすめ] と [必須] の両方として設定できますが、重要なコールアウトがあります。

[必須] の有効化: 個々のユーザーの同意が特定のユーザーに対してこの機能を有効にするための前提条件であることを考えると、このポリシーには必須の有効化設定がありません。 ポリシーが [必須] を有効に設定している場合、設定の UI は変更されず、次のエラーメッセージが edge://policy に表示されます

エラー状態メッセージの例: 「パスワード モニターをオンにするには、個々のユーザーの同意が必要なので、このポリシー値は無視されます。 組織のユーザーに、[設定]、[プロフィール]、[パスワード] の順に移動して機能を有効にするよう依頼できます。」

[おすすめ] の有効化: ポリシーが [おすすめ] を有効に設定している場合、[設定] の UI は [オフ] の状態のままになりますが、ブリーフケース アイコンが横に表示され、この説明がホバーに表示されます - 「組織はこの設定に特定の値をおすすめしておりますが、別の値を選択しています」

[必須] および [おすすめ] が無効な場合: これらはいずれも通常の方法で動作し、通常のキャプションがユーザーに表示されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PasswordMonitorAllowed
  - GP 名: パスワードが安全でないことが判明した場合にユーザーに警告することを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/パスワード マネージャーと保護
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/パスワード マネージャーと保護
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: PasswordMonitorAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### PasswordProtectionChangePasswordURL

  #### パスワード変更の URL を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  パスワード変更の URL を構成します (HTTP と HTTPS スキームのみ)。

パスワード保護サービスは、ブラウザーで警告を見た後にパスワードを変更するために、ユーザーをこの URL に送ります。

このポリシーを有効にしている場合、パスワード保護サービスは、パスワードを変更するためにユーザーをこの URL に送ります。

このポリシーを無効にしているか、構成していない場合、パスワード保護サービスは、ユーザーをパスワード変更の URL にリダイレクトしません。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PasswordProtectionChangePasswordURL
  - GP 名: パスワード変更の URL を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/パスワード マネージャーと保護
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: PasswordProtectionChangePasswordURL
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"https://contoso.com/change_password.html"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PasswordProtectionChangePasswordURL
  - サンプル値:
``` xml
<string>https://contoso.com/change_password.html</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PasswordProtectionLoginURLs

  #### パスワード保護サービスがパスワードのソルト化ハッシュをキャプチャする必要があるエンタープライズ ログイン URL のリストを構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge がパスワードのソルト化ハッシュをキャプチャしてパスワードの再利用の検出に使用する、エンタープライズ ログイン URL のリスト (HTTP と HTTPS スキームのみ) を構成します。

このポリシーを有効にしている場合、パスワード保護サービスは、定義された URL のパスワードのフィンガープリントをキャプチャします。

このポリシーを無効にしているか、構成していない場合、パスワードのフィンガープリントはキャプチャされません。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PasswordProtectionLoginURLs
  - GP 名: パスワード保護サービスがパスワードのソルト化ハッシュをキャプチャする必要があるエンタープライズ ログイン URL のリストを構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/パスワード マネージャーと保護
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\PasswordProtectionLoginURLs
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\PasswordProtectionLoginURLs\1 = "https://contoso.com/login.html"
SOFTWARE\Policies\Microsoft\Edge\PasswordProtectionLoginURLs\2 = "https://login.contoso.com"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PasswordProtectionLoginURLs
  - サンプル値:
``` xml
<array>
  <string>https://contoso.com/login.html</string>
  <string>https://login.contoso.com</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PasswordProtectionWarningTrigger

  #### パスワード保護の警告トリガーを構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  パスワード保護の警告をいつトリガーするかを制御することができます。 パスワード保護は、保護されたパスワードを疑わしい可能性があるサイトで再利用する場合にユーザーに警告を表示します。

[PasswordProtectionLoginURLs](#passwordprotectionloginurls) と [PasswordProtectionChangePasswordURL](#passwordprotectionchangepasswordurl) ポリシーを使用して、保護するパスワードを構成することができます。

例外: [PasswordProtectionLoginURLs](#passwordprotectionloginurls)、[PasswordProtectionChangePasswordURL](#passwordprotectionchangepasswordurl)、[SmartScreenAllowListDomains](#smartscreenallowlistdomains) にリストされているサイトのパスワードは、パスワード保護の警告をトリガーしません。

"PasswordProtectionWarningOff" に設定すると、パスワード保護の警告を表示しないようになります。

"PasswordProtectionWarningOnPasswordReuse" に設定すると、ユーザーが許可リストに登録されていないサイトで保護されているパスワードを再利用した場合に、パスワード保護の警告を表示します。

このポリシーを無効にしているか、構成していない場合、警告トリガーは表示されません。

ポリシー オプション マッピング:

* PasswordprotectionWarningOff (0) = パスワード保護の警告がオフになっています

* PasswordprotectionwarningOnpasswordReuse (1) = パスワード保護の警告は、パスワードの再利用でトリガーされます。

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PasswordProtectionWarningTrigger
  - GP 名: パスワード保護の警告トリガーを構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/パスワード マネージャーと保護
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: PasswordProtectionWarningTrigger
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PasswordProtectionWarningTrigger
  - サンプル値:
``` xml
<integer>1</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PasswordRevealEnabled

  #### [パスワードの表示] ボタンを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 87 以降

  #### 説明

  Web サイトのパスワード入力フィールドのブラウザ パスワード表示ボタンのデフォルト表示を設定できます。

このポリシーを有効にするか、構成しない場合、ブラウザのユーザー設定はデフォルトで [パスワードの表示] ボタンを表示します。

このポリシーを無効にすると、ブラウザーのユーザー設定には、[パスワードの表示] ボタンが表示されません。

アクセシビリティのために、ユーザーはブラウザの設定をデフォルトのポリシーから変更できます。

このポリシーは、ブラウザの [パスワードの表示] ボタンにのみ影響し、Web サイトのカスタム表示ボタンには影響しません。

  #### サポートされている機能:

  - 必須にすることができるか: いいえ
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PasswordRevealEnabled
  - GP 名: [パスワードの表示] ボタンを有効にする
  - GP パス (必須): なし
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/パスワード マネージャーと保護
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): なし
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: PasswordRevealEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PasswordRevealEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ## パフォーマンス ポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### StartupBoostEnabled

  #### スタートアップ ブーストを有効にする

  
  
  #### サポートされているバージョン:

  - Windows での 88 以降

  #### 説明

  Microsoft Edge のプロセスが OS へのサインイン時に起動し、最後のブラウザー ウィンドウを閉じた後もバックグラウンドで再起動することができるようになります。

Microsoft Edge がバックグラウンド モードで実行されている場合、最後のウィンドウが閉じたときにブラウザーが閉じない可能性があり、ウィンドウが閉じてもブラウザーはバックグラウンドで再起動しません。 Microsoft Edge のバックグラウンド モードの動作を構成した後の動作に関する情報については、[BackgroundModeEnabled](#backgroundmodeenabled) ポリシーを参照してください。

このポリシーを有効にしている場合、スタートアップ ブーストがオンになります。

このポリシーを無効にしている場合、スタートアップ ブーストがオフになります。

このポリシーを構成していない場合、スタートアップ ブーストは初期状態でオフまたはオンのいずれかになっている場合があります。 ユーザーはその動作を edge://settings/system で構成することができます。

スタートアップ ブーストについての詳細情報: [https://go.microsoft.com/fwlink/?linkid=2147018](https://go.microsoft.com/fwlink/?linkid=2147018)

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: StartupBoostEnabled
  - GP 名: スタートアップ ブーストを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/パフォーマンス
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/パフォーマンス
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: StartupBoostEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ## 印刷に関するポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultPrinterSelection

  #### 通常使うプリンターの選択ルール

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge の通常使うプリンターの選択ルールを上書きします。 このポリシーは、Microsoft Edge で通常使うプリンターを選択するときのルールを決定します。これは、ユーザーが初めてページを印刷しようとしたときに発生します。

このポリシーが設定されている場合、Microsoft Edge は、指定されている属性にすべて一致するプリンターを見つけようとし、そのプリンターを通常使うプリンターとして使用します。 条件を満たすプリンターが複数ある場合、最初に一致したプリンターが使用されます。

このポリシーを構成していないか、タイムアウト期間内に一致するプリンターが見つからない場合、プリンターは内蔵の PDF プリンターを既定とするか、PDF プリンターが利用できない場合にはプリンターを使用しません。

値は、以下のスキーマに準拠する JSON オブジェクトとして解析されます: { "type": "object", "properties": { "idPattern": { "description": "プリンター ID に一致する正規表現。", "type": "string" }, "namePattern": { "description": "プリンターの表示名に一致する正規表現。", "type": "string" } } }

フィールドを省略すると、すべての値が一致します。たとえば、接続性を指定しない場合、印刷プレビューではあらゆる種類のローカル プリンターが検出されます。 正規表現パターンは JavaScript RegExp 構文に従う必要があり、一致では大文字と小文字は区別されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultPrinterSelection
  - GP 名: 通常使うプリンターの選択ルール
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/印刷
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultPrinterSelection
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"{ \"idPattern\": \".*public\", \"namePattern\": \".*Color\" }"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultPrinterSelection
  - サンプル値:
``` xml
<string>{ "idPattern": ".*public", "namePattern": ".*Color" }</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PrintHeaderFooter

  #### ヘッダーとフッターを印刷する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  印刷ダイアログで、"ヘッダーとフッター"を強制的にオンまたはオフにします。

このポリシーを構成していない場合、ユーザーがヘッダーとフッターを印刷するかどうかを決めることができます。

このポリシーを無効にしている場合、ユーザーはヘッダーとフッターを印刷することができません。

このポリシーを有効にしている場合、ユーザーはヘッダーとフッターを常に印刷します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PrintHeaderFooter
  - GP 名: ヘッダーとフッターを印刷する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/印刷
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/印刷
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: PrintHeaderFooter
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PrintHeaderFooter
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PrintPreviewUseSystemDefaultPrinter

  #### システムの既定のプリンターを通常使うプリンターに設定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  印刷プレビューで、最近使用したプリンターではなく、通常使うプリンターを既定の選択として使用するように Microsoft Edge に指示します。

このポリシーを無効にしているか、構成していない場合、印刷プレビューでは、最近使用したプリンターが既定の接続先として選択されます。

このポリシーを有効にしている場合、印刷プレビューでは、OS の通常使うプリンターが既定の接続先として選択されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PrintPreviewUseSystemDefaultPrinter
  - GP 名: システムの既定のプリンターを通常使うプリンターに設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/印刷
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/印刷
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: PrintPreviewUseSystemDefaultPrinter
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PrintPreviewUseSystemDefaultPrinter
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PrinterTypeDenyList

  #### 拒否リストでプリンターの種類を無効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 88 以降

  #### 説明

  拒否リストにあるプリンターの種類は検出されないか、機能が取得されません。

すべての種類のプリンターを拒否リストに配置すると、ドキュメントの印刷先がないため、印刷が事実上無効になります。

このポリシーを構成しない場合、またはプリンター リストが空の場合、すべての種類のプリンターを検出できます。

プリンター出力先には、内線プリンターとローカル プリンターが含まれます。 拡張プリンターは、印刷プロバイダーの出力先とも呼ばれ、Microsoft Edge 拡張機能に属するすべての出力先が含まれます。
ローカル プリンターは、ネイティブの出力先とも呼ばれ、ローカル コンピューターと共有ネットワーク プリンターで利用可能な出力先が含まれます。

ポリシー オプション マッピング:

* privet (privet) = Zeroconf ベース (mDNS + DNS-SD) プロトコルの出力先

* extension (extension) = Extension ベースの出力先

* pdf (pdf) = 「PDF として保存」の出力先

* local (local) = ローカル プリンター出力先

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PrinterTypeDenyList
  - GP 名: 拒否リストでプリンターの種類を無効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/印刷
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\PrinterTypeDenyList
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\PrinterTypeDenyList\1 = "local"
SOFTWARE\Policies\Microsoft\Edge\PrinterTypeDenyList\2 = "privet"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PrinterTypeDenyList
  - サンプル値:
``` xml
<array>
  <string>local</string>
  <string>privet</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PrintingAllowedBackgroundGraphicsModes

  #### バックグラウンド グラフィックス印刷モードを制限する

  
  
  #### サポートされているバージョン:

  - 89 以降の Windows および MacOS の場合

  #### 説明

  バックグラウンド グラフィックス印刷モードを制限します。 このポリシーが設定されていない場合、背景グラフィックスの印刷に制限はありません。

ポリシー オプション マッピング:

* any (任意) = バックグラウンド グラフィックスを使用した印刷と印刷なしを許可する

* 有効 (有効) = バックグラウンド グラフィックスでのみ印刷を許可する

* 無効 (無効) = バックグラウンド グラフィックスがない場合にのみ印刷を許可する

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 一意の名前: PrintingAllowedBackgroundGraphicsModes
  - GP 名: バックグラウンド グラフィックス印刷モードを制限する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/印刷
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: PrintingAllowedBackgroundGraphicsModes
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"enabled"
```

  #### Mac の情報と設定
  
  - Preference Key Name: PrintingAllowedBackgroundGraphicsModes
  - サンプル値:
``` xml
<string>enabled</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PrintingBackgroundGraphicsDefault

  #### 既定の背景グラフィックス印刷モード

  
  
  #### サポートされているバージョン:

  - 89 以降の Windows および MacOS の場合

  #### 説明

  既定の背景グラフィックス印刷モードを上書きします。

ポリシー オプション マッピング:

* 有効 (有効) = 既定でバックグラウンド グラフィックス印刷モードを有効にする

* 無効 (無効) = 既定でバックグラウンド グラフィックス印刷モードを無効にする

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 一意の名前: PrintingBackgroundGraphicsDefault
  - GP 名: 既定のバックグラウンド グラフィックス印刷モード
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/印刷
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: PrintingBackgroundGraphicsDefault
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"enabled"
```

  #### Mac の情報と設定
  
  - Preference Key Name: PrintingBackgroundGraphicsDefault
  - サンプル値:
``` xml
<string>enabled</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PrintingEnabled

  #### 印刷を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge での印刷を有効にし、ユーザーがこの設定を変更できないようにします。

このポリシーを有効にしているか、設定していない場合、ユーザーは印刷することができます。

このポリシーを無効にしている場合、ユーザーは Microsoft Edge から印刷することができません。 レンチ メニュー、拡張機能、JavaScript アプリケーションなどでは、印刷は無効になっています。 ユーザーは、印刷中に Microsoft Edge をバイパスするプラグインから印刷することができます。 たとえば、一部の Adobe Flash アプリケーションでは、コンテキスト メニューに印刷オプションがありますが、これはこのポリシーの対象外です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PrintingEnabled
  - GP 名: 印刷を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/印刷
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: PrintingEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PrintingEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PrintingPaperSizeDefault

  #### 印刷の既定のページ サイズ

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  印刷の既定のページ サイズを上書きします。

名前には、一覧に必要な用紙サイズが含まれていない場合に、指定した書式または 'Custom' のいずれかを含める必要があります。 'Custom' 値が指定されている場合は custom_size プロパティを指定する必要があります。 このファイルでは、必要な高さと幅がマイクロメートル単位で示されます。 それ以外の custom_size プロパティは指定できません。 これらのルールに違反するポリシーは無視されます。

ユーザーが選んだプリンターのページ サイズが使用できない場合、このポリシーは無視されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Dictionary

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PrintingPaperSizeDefault
  - GP 名: 印刷の既定のページ サイズ
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/印刷
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: PrintingPaperSizeDefault
  - 値の種類: REG_SZ

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\PrintingPaperSizeDefault = {
  "custom_size": {
    "height": 297000, 
    "width": 210000
  }, 
  "name": "custom"
}
```

  ##### コンパクト サンプル値:

  ```
  SOFTWARE\Policies\Microsoft\Edge\PrintingPaperSizeDefault = {"custom_size": {"height": 297000, "width": 210000}, "name": "custom"}
  ```
  

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PrintingPaperSizeDefault
  - サンプル値:
``` xml
<key>PrintingPaperSizeDefault</key>
<dict>
  <key>custom_size</key>
  <dict>
    <key>height</key>
    <integer>297000</integer>
    <key>width</key>
    <integer>210000</integer>
  </dict>
  <key>name</key>
  <string>custom</string>
</dict>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### UseSystemPrintDialog

  #### システムの印刷ダイアログを使用して印刷する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  印刷プレビューの代わりに、システムの印刷ダイアログを表示します。

このポリシーを有効にしている場合、Microsoft Edge では、ユーザーがページを印刷するときに組み込みの印刷プレビューではなく、システムの印刷ダイアログが開きます。

このポリシーを構成していないか、無効にしている場合、印刷コマンドは Microsoft Edge の印刷プレビュー画面をトリガーします。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: UseSystemPrintDialog
  - GP 名: システムの印刷ダイアログを使用して印刷する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/印刷
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: UseSystemPrintDialog
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: UseSystemPrintDialog
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ## プロキシ サーバーに関するポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### ProxyBypassList

  #### プロキシのバイパス ルールを構成する (非推奨)

  >非推奨: このポリシーは推奨されなくなっています。 現在はサポートされていますが、将来のリリースで廃止されます。
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーは推奨されなくなっています。代わりに [ProxySettings](#proxysettings) を使用してください。 Microsoft Edge バージョン 91 では機能しません。

Microsoft Edge がプロキシをバイパスするホストの一覧を定義します。

このポリシーは [ProxySettings](#proxysettings) ポリシーが指定されておらず、[ProxyMode](#proxymode) ポリシーで fixed_servers を選択している場合にのみ適用されます。 プロキシ ポリシーを構成するために別のモードを選択した場合は、このポリシーを有効にしたり、構成したりしないでください。

このポリシーを有効にしている場合、Microsoft Edge がプロキシを使用しないホストの一覧を作成することができます。

このポリシーを構成していない場合、Microsoft Edge がプロキシをバイパスするホストの一覧は作成されません。 プロキシ ポリシーを構成するために別の方法を指定している場合、このポリシーは未構成のままにしておきます。

より詳細な例については、「[https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936)」を参照してください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ProxyBypassList
  - GP 名: プロキシのバイパス ルールを構成する (非推奨)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/プロキシ サーバー
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ProxyBypassList
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"https://www.contoso.com, https://www.fabrikam.com"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ProxyBypassList
  - サンプル値:
``` xml
<string>https://www.contoso.com, https://www.fabrikam.com</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ProxyMode

  #### プロキシ サーバーの設定を構成する (非推奨)

  >非推奨: このポリシーは推奨されなくなっています。 現在はサポートされていますが、将来のリリースで廃止されます。
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーは推奨されなくなっています。代わりに [ProxySettings](#proxysettings) を使用してください。 Microsoft Edge バージョン 91 では機能しません。

このポリシーを有効にすると、Microsoft Edge が使用するプロキシ サーバーを指定して、ユーザーがプロキシの設定を変更できないようにすることができます。 Microsoft Edge は、コマンド ラインから指定されたプロキシ関連のオプションをすべて無視します。 このポリシーは、[ProxySettings](#proxysettings) ポリシーが指定されていない場合にのみ適用されます。

以下のオプションのいずれかを選択した場合、その他のオプションは無視されます。
  * direct = プロキシ サーバーを使用せず、常に直接接続する
  * system = システムのプロキシ設定を使用する
  * auto_detect = プロキシ サーバーを自動検出する

以下を選択して使用する場合:
  * fixed_servers = 固定プロキシ サーバー。 [ProxyServer](#proxyserver) と [ProxyBypassList](#proxybypasslist) を使用してさらにオプションを指定することができます。
  * pac_script = .pac プロキシ スクリプト。 [ProxyPacUrl](#proxypacurl) を使用して、プロキシ .pac ファイルの URL を設定します。

詳細な例については、「[https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936)」を参照してください。

このポリシーを構成していない場合、ユーザーは自分のプロキシ設定を選択することができます。

ポリシー オプション マッピング:

* ProxyDisabled (direct) = プロキシを使わない

* ProxyAutoDetect (auto_detect) = 自動検出プロキシの設定

* ProxyPacScript (pac_script) = .pac プロキシ スクリプトを使用する

* ProxyFixedServers (fixed_servers) = 固定プロキシ サーバーを使用します。

* ProxyUseSystem (system) = システムのプロキシ設定を使用する

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ProxyMode
  - GP 名: プロキシ サーバーの設定を構成する (非推奨)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/プロキシ サーバー
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ProxyMode
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"direct"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ProxyMode
  - サンプル値:
``` xml
<string>direct</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ProxyPacUrl

  #### プロキシ .pac ファイルの URL を設定する (非推奨)

  >非推奨: このポリシーは推奨されなくなっています。 現在はサポートされていますが、将来のリリースで廃止されます。
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーは推奨されなくなっています。代わりに [ProxySettings](#proxysettings) を使用してください。 Microsoft Edge バージョン 91 では機能しません。

プロキシの自動構成 (PAC) ファイルの URL を指定します。

このポリシーは [ProxySettings](#proxysettings) ポリシーが指定されておらず、[ProxyMode](#proxymode) ポリシーで pac_script を選択している場合にのみ適用されます。 プロキシ ポリシーを構成するために別のモードを選択した場合は、このポリシーを有効にしたり、構成したりしないでください。

このポリシーを有効にしている場合、ブラウザーが特定の Web サイトを取得するための適切なプロキシ サーバーを自動選択する方法を定義する PAC ファイルの URL を指定することができます。

このポリシーを無効にしているか、構成していない場合、PAC ファイルは指定されません。 プロキシ ポリシーを構成するために別の方法を指定している場合、このポリシーは未構成のままにしておきます。

詳細な例については、「[https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936)」を参照してください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ProxyPacUrl
  - GP 名: プロキシ .pac ファイルの URL を設定する (非推奨)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/プロキシ サーバー
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ProxyPacUrl
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"https://internal.contoso.com/example.pac"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ProxyPacUrl
  - サンプル値:
``` xml
<string>https://internal.contoso.com/example.pac</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ProxyServer

  #### プロキシ サーバーのアドレスまたは URL を構成する (非推奨)

  >非推奨: このポリシーは推奨されなくなっています。 現在はサポートされていますが、将来のリリースで廃止されます。
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーは推奨されなくなっています。代わりに [ProxySettings](#proxysettings) を使用してください。 Microsoft Edge バージョン 91 では機能しません。

プロキシ サーバーの URL を指定します。

このポリシーは [ProxySettings](#proxysettings) ポリシーが指定されておらず、[ProxyMode](#proxymode) ポリシーで fixed_servers を選択している場合にのみ適用されます。 プロキシ ポリシーを構成するために別のモードを選択した場合は、このポリシーを有効にしたり、構成したりしないでください。

このポリシーを有効にしている場合、このポリシーで構成されたプロキシ サーバーがすべての URL に使用されます。

このポリシーを無効にしているか、構成していない場合、ユーザーはこのプロキシ モードの間、自分のプロキシ設定を選択することができます。 プロキシ ポリシーを構成するために別の方法を指定している場合、このポリシーは未構成のままにしておきます。

オプションや詳細な例については、「[https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936)」を参照してください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ProxyServer
  - GP 名: プロキシ サーバーのアドレスまたは URL を構成する (非推奨)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/プロキシ サーバー
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ProxyServer
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"123.123.123.123:8080"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ProxyServer
  - サンプル値:
``` xml
<string>123.123.123.123:8080</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ProxySettings

  #### プロキシの設定

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge のプロキシの設定を構成します。

このポリシーを有効にしている場合、Microsoft Edge は、コマンド ラインから指定されたプロキシ関連のオプションをすべて無視します。

このポリシーを構成していない場合、ユーザーは自分のプロキシ設定を選択することができます。

このポリシーは以下のポリシーを個別に上書きします。

[ProxyMode](#proxymode)
[ProxyPacUrl](#proxypacurl)
[ProxyServer](#proxyserver)
[ProxyBypassList](#proxybypasslist)

[ProxySettings](#proxysettings) ポリシーの設定は、以下のフィールドを受け入れます。
  * Microsoft Edge で使用するプロキシ サーバーを指定し、ユーザーがプロキシの設定を変更できないようにする ProxyMode
  * ProxyPacUrl、プロキシ .pac ファイルへの URL
  * ProxyServer、プロキシ サーバーの URL
  * ProxyBypassList、Microsoft Edge がバイパスするプロキシ ホストの一覧

ProxyMode の場合に、以下の値を選択すると:
  * direct の場合、プロキシは使用されず、その他すべてのフィールドは無視されます。
  * system の場合、システムのプロキシが使用され、その他すべてのフィールドは無視されます。
  * auto_detect の場合、その他すべてのフィールドは無視されます。
  * fixed_server の場合、ProxyServer と ProxyBypassList フィールドが使用されます。
  * pac_script の場合、ProxyPacUrl と ProxyBypassList フィールドが使用されます。

より詳細な例については、「[https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936)」を参照してください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Dictionary

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ProxySettings
  - GP 名: プロキシ設定の構成
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/プロキシ サーバー
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ProxySettings
  - 値の種類: REG_SZ

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\ProxySettings = {
  "ProxyBypassList": "https://www.example1.com,https://www.example2.com,https://internalsite/", 
  "ProxyMode": "direct", 
  "ProxyPacUrl": "https://internal.site/example.pac", 
  "ProxyServer": "123.123.123.123:8080"
}
```

  ##### コンパクト サンプル値:

  ```
  SOFTWARE\Policies\Microsoft\Edge\ProxySettings = {"ProxyBypassList": "https://www.example1.com,https://www.example2.com,https://internalsite/", "ProxyMode": "direct", "ProxyPacUrl": "https://internal.site/example.pac", "ProxyServer": "123.123.123.123:8080"}
  ```
  

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ProxySettings
  - サンプル値:
``` xml
<key>ProxySettings</key>
<dict>
  <key>ProxyBypassList</key>
  <string>https://www.example1.com,https://www.example2.com,https://internalsite/</string>
  <key>ProxyMode</key>
  <string>direct</string>
  <key>ProxyPacUrl</key>
  <string>https://internal.site/example.pac</string>
  <key>ProxyServer</key>
  <string>123.123.123.123:8080</string>
</dict>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ## スリーピング タブの設定に関するポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### SleepingTabsBlockedForUrls

  #### 特定のサイトでタブのスリープをブロックする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 88 以降

  #### 説明

  スリーピング タブによってスリープ状態にされないサイトのリストを URL パターンに基づいて定義します。

ポリシー [SleepingTabsEnabled](#sleepingtabsenabled) が無効になっている場合、このリストは使用されず、サイトが自動的にスリープ状態になることはありません。

このポリシーを構成しない場合、ユーザーの個人用構成でブロックされていない限り、すべてのサイトはスリープ状態にすることができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - 一意の GP 名: SleepingTabsBlockedForUrls
  - GP 名: 特定のサイトでスリーピング タブをブロックする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/スリーピング タブの設定
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/スリーピング タブの設定
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\SleepingTabsBlockedForUrls
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended\SleepingTabsBlockedForUrls
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\SleepingTabsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SleepingTabsBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SleepingTabsBlockedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SleepingTabsEnabled

  #### スリープ タブを構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 88 以降

  #### 説明

  このポリシー設定を使用すると、スリーピング タブを有効にするかどうかを構成できます。 スリーピング タブは、アイドル状態のバックグラウンド タブをスリープ状態にすることで、CPU、バッテリー、メモリの使用量を削減します。 Microsoft Edge ではヒューリスティックを使用して、通知の表示、サウンドの再生、動画のストリーミングなど、バックグラウンドで役に立つ作業を行うタブをスリープ状態にしないようにします。 既定では、スリーピング タブはオンになっています。

ポリシー [SleepingTabsBlockedForUrls](#sleepingtabsblockedforurls) を構成することで、個々のサイトがスリープ状態にされるのをブロックすることができます。

この設定を有効にすると、スリーピング タブはオンになります。

この設定を無効にすると、スリーピング タブはオフになります。

この設定を構成しない場合、ユーザーはスリーピング タブを使うかどうかを選ぶことができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - 一意の GP 名: SleepingTabsEnabled
  - GP 名: スリーピング タブを構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/スリーピング タブの設定
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/スリーピング タブの設定
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: SleepingTabsEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SleepingTabsEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SleepingTabsTimeout

  #### タブをスリープ状態に設定するバックグラウンド タブの非アクティブタイムアウトを設定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 88 以降

  #### 説明

  このポリシー設定を使用すると、スリーピング タブが有効になっている場合に、非アクティブなバックグラウンド タブが自動的にスリープ状態になるまでのタイムアウト (秒単位) を構成できます。 既定では、このタイムアウトは 7, 200 秒 (2 時間) です。

ポリシー [SleepingTabsEnabled](#sleepingtabsenabled) が有効になっているか、構成されておらず、ユーザーがスリーピング タブの設定を有効にしている場合にのみ、タブは自動的にスリープ状態になります。

このポリシーを構成しない場合、ユーザーはタイムアウト値を選ぶことができます。

ポリシー オプション マッピング:

* 5Minutes (300) = 5 分間の非アクティブ状態

* 15Minutes (900) = 15 分間の非アクティブ状態

* 30Minutes (1800) = 30 分間の非アクティブ状態

* 1Hour (3600) = 1 時間 の非アクティブ状態

* 2Hours (7200) = 2 時間の非アクティブ状態

* 3Hours (10800) = 3 時間の非アクティブ状態

* 6Hours (21600) = 6 時間の非アクティブ状態

* 12Hours (43200) = 12時間の非アクティブ状態

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - 一意の GP 名: SleepingTabsTimeout
  - GP 名: スリーピング タブ用にバックグラウンド タブの非アクティブ タイムアウトを設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/スリーピング タブの設定
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/スリーピング タブの設定
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: SleepingTabsTimeout
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000384
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SleepingTabsTimeout
  - サンプル値:
``` xml
<integer>900</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ## SmartScreen の設定に関するポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### PreventSmartScreenPromptOverride

  #### サイトに関する Microsoft Defender SmartScreen プロンプトをバイパスしない

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシー設定では、悪意があると考えられる Web サイトに関する Microsoft Defender SmartScreen の警告を、ユーザーが無視できるかどうかを決定できます。

この設定を有効にした場合、ユーザーは Microsoft Defender SmartScreen の警告を無視できず、サイトへのアクセスが中断されます。

この設定を無効にしているか、構成していない場合、ユーザーは Microsoft Defender SmartScreen の警告を無視し、サイトへのアクセスを続行できます。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PreventSmartScreenPromptOverride
  - GP 名: サイトに関する Microsoft Defender SmartScreen プロンプトをバイパスしない
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/SmartScreen の設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: PreventSmartScreenPromptOverride
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PreventSmartScreenPromptOverride
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PreventSmartScreenPromptOverrideForFiles

  #### ダウンロードに関する Microsoft Defender SmartScreen 警告のバイパスを防ぐ

  
  
  #### サポートされているバージョン:

  - Windows での 77 以降
  - macOS での 79 以降

  #### 説明

  このポリシーでは、確認されていないダウンロードに関する Microsoft Defender SmartScreen の警告をユーザーが上書きできるかどうかを決定することができます。

このポリシーを有効にしている場合、組織内のユーザーは Microsoft Defender SmartScreen の警告を無視することができないため、確認されていないダウンロードの完了を防止することができます。

このポリシーを無効にしているか、構成していない場合、ユーザーは Microsoft Defender SmartScreen の警告を無視し、確認されていないダウンロードを完了させることができます。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PreventSmartScreenPromptOverrideForFiles
  - GP 名: ダウンロードに関する Microsoft Defender SmartScreen 警告のバイパスを防ぐ
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/SmartScreen の設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: PreventSmartScreenPromptOverrideForFiles
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PreventSmartScreenPromptOverrideForFiles
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SmartScreenAllowListDomains

  #### Microsoft Defender SmartScreen が警告がトリガーしないドメインの一覧を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Defender SmartScreen に信頼されているドメインの一覧を構成します。 つまり、Microsoft Defender SmartScreen は、ソース URL がこれらのドメインに一致する場合、フィッシング ソフトウェアやその他のマルウェアのような悪意があると考えられるリソースをチェックしません。
Microsoft Defender SmartScreen ダウンロード保護サービスは、これらのドメインでホストされているダウンロードをチェックしません。

このポリシーを有効にしている場合、Microsoft Defender SmartScreen はこれらのドメインを信頼します。
このポリシーを無効にしているか、設定していない場合、既定の Microsoft Defender SmartScreen 保護がすべてのリソースに適用されます。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。
また、お客様の組織が Microsoft Defender Advanced Threat Protection を有効にしている場合、このポリシーは適用されません。 代わりに Microsoft Defender セキュリティ センターで許可リストとブロック リストを構成する必要があります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SmartScreenAllowListDomains
  - GP 名: Microsoft Defender SmartScreen が警告がトリガーしないドメインの一覧を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/SmartScreen の設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\SmartScreenAllowListDomains
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\SmartScreenAllowListDomains\1 = "mydomain.com"
SOFTWARE\Policies\Microsoft\Edge\SmartScreenAllowListDomains\2 = "myuniversity.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SmartScreenAllowListDomains
  - サンプル値:
``` xml
<array>
  <string>mydomain.com</string>
  <string>myuniversity.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SmartScreenEnabled

  #### Microsoft Defender SmartScreen を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシー設定では、Microsoft Defender SmartScreen を有効にするかどうかを構成することができます。 Microsoft Defender SmartScreen では、潜在的なフィッシング詐欺と悪意のあるソフトウェアからユーザーを保護するために、警告メッセージが表示されます。 既定では、Microsoft Defender SmartScreen はオンになっています。

この設定を有効にしている場合、Microsoft Defender SmartScreen はオンになります。

この設定を無効にしている場合、Microsoft Defender SmartScreen はオフになります。

この設定を構成していない場合、ユーザーは Microsoft Defender SmartScreen を使用するかどうかを選ぶことができます。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SmartScreenEnabled
  - GP 名: Microsoft Defender SmartScreen を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/SmartScreen の設定
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/SmartScreen の設定
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: SmartScreenEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SmartScreenEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SmartScreenForTrustedDownloadsEnabled

  #### 信頼のおけるソースからのダウンロードに対して Microsoft Defender SmartScreen のチェックを強制する

  
  
  #### サポートされているバージョン:

  - Windows での 78 以降

  #### 説明

  このポリシー設定では、信頼のおけるソースからのダウンロード評価を Microsoft Defender SmartScreen がチェックするかどうかを構成することができます。

この設定を有効にしているか、構成していない場合、Microsoft Defender SmartScreen はソースに関係なくダウンロード評価をチェックします。

この設定を無効にしている場合、Microsoft Defender SmartScreen は信頼のおけるソースからのダウンロードを実行するときにダウンロード評価をチェックしません。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンスか、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SmartScreenForTrustedDownloadsEnabled
  - GP 名: 信頼のおけるソースからのダウンロードに対して Microsoft Defender SmartScreen のチェックを強制する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/SmartScreen の設定
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/SmartScreen の設定
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: SmartScreenForTrustedDownloadsEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### SmartScreenPuaEnabled

  #### Microsoft Defender SmartScreen を構成して望ましくない可能性のあるアプリをブロックする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 80 以降

  #### 説明

  このポリシー設定では、Microsoft Defender SmartScreen を使用して、望ましくない可能性のあるアプリをブロックするかどうかを構成することができます。 Microsoft Defender SmartScreen による望ましくない可能性のあるアプリのブロックは、アドウェア、コイン マイナー、バンドルウェア、Web サイトでホストされている評価の低いアプリなどからユーザーを保護するための警告メッセージを提供します。 Microsoft Defender SmartScreen による望ましくない可能性のあるアプリのブロックは、既定でオフになっています。

この設定を有効にしている場合、Microsoft Defender SmartScreen を使用した望ましくない可能性のあるアプリのブロックがオンになります。

この設定を無効にしている場合、Microsoft Defender SmartScreen を使用した望ましくない可能性のあるアプリのブロックがオフになります。

この設定を構成していない場合、ユーザーは Microsoft Defender SmartScreen を使用して望ましくない可能性のあるアプリをブロックするかどうかを選ぶことができます。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SmartScreenPuaEnabled
  - GP 名: Microsoft Defender SmartScreen を構成して望ましくない可能性のあるアプリをブロックする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/SmartScreen の設定
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/SmartScreen の設定
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: SmartScreenPuaEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SmartScreenPuaEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ## スタートアップ &comma; ホーム ページ、新規タブ ページに関するポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### HomepageIsNewTabPage

  #### 新規タブ ページをホーム ページとして設定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge の既定のホーム ページを構成します。 ホーム ページを指定した URL に設定したり、新規タブ ページに設定したりすることができます。

このポリシーを有効にしている場合、新規タブ ページが常にホーム ページに使用され、ホーム ページの URL の場所は無視されます。

このポリシーを無効にしている場合、URL が "edge://newtab" に設定されていない限り、新規タブ ページをユーザーのホーム ページにすることはできません。

構成されていない場合、ユーザーは新規タブ ページを自分のホーム ページにするかどうかを選択することができます。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: HomepageIsNewTabPage
  - GP 名: 新規タブ ページをホーム ページとして設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/スタートアップ、ホーム ページ、新規タブ ページ
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/スタートアップ、ホーム ページ、新規タブ ページ
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: HomepageIsNewTabPage
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: HomepageIsNewTabPage
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### HomepageLocation

  #### ホーム ページの URL を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge の既定のホーム ページの URL を構成します。

ホーム ページとは、[ホーム] ボタンから開いたページのことです。 起動時に開くページは、[RestoreOnStartup](#restoreonstartup) ポリシーによって制御されます。

ここに URL を設定するか、新規タブ ページを開くホーム ページを設定します。 新規タブ ページのオープンを選択した場合、このポリシーは有効になりません。

このポリシーを有効にしている場合、ホーム ページの URL をユーザーが変更することはできませんが、ユーザーは新規タブ ページをホーム ページとして使用することができます。

このポリシーを無効にしているか、構成していない場合、[HomepageIsNewTabPage](#homepageisnewtabpage) ポリシーが有効になっていない限り、ユーザーは自分のホーム ページを選択することができます。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: HomepageLocation
  - GP 名: ホーム ページの URL を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/スタートアップ、ホーム ページ、新規タブ ページ
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/スタートアップ、ホーム ページ、新規タブ ページ
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: HomepageLocation
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"https://www.contoso.com"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: HomepageLocation
  - サンプル値:
``` xml
<string>https://www.contoso.com</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### NewTabPageAllowedBackgroundTypes

  #### 新しいタブページレイアウトに使用できる背景の種類を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  Microsoft Edge の新しいタブページレイアウトに使用できる、背景画像の種類を構成できます。

このポリシーを設定しない場合、新しいタブ ページのすべての背景画像の種類が有効になります。

ポリシー オプション マッピング:

* DisableImageOfTheDay (1) = 日ごとの背景画像を無効にする

* DisableCustomImage (2) = ユーザー設定の背景画像を無効にする

* DisableAll (3) = すべての背景画像を無効にする

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NewTabPageAllowedBackgroundTypes
  - GP 名: 新しいタブ ページ レイアウトに使用できる背景の種類を構成します。
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/スタートアップ、ホーム ページ、新規タブ ページ
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: NewTabPageAllowedBackgroundTypes
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - プリファレンス キー名: NewTabPageAllowedBackgroundTypes
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### NewTabPageCompanyLogo

  #### 新規タブ ページの会社のロゴを設定する (不使用)

  
  >不使用: このポリシーは廃止されており、Microsoft Edge 85 以降は機能しません。
  #### サポートされているバージョン:

  - Windows と macOS での 79 以降、85 まで

  #### 説明

  このポリシーは、運用要件の変更のため、期待どおりに動作しませんでした。 そのため、使用しないでください。

Microsoft Edge の新規タブ ページで使用する会社のロゴを指定します。

ポリシーは、ロゴを JSON 形式で表現する文字列として構成されている必要があります。 たとえば、以下のようになります: { "default_logo": { "url": "https://www.contoso.com/logo.png", "hash": "cd0aa9856147b6c5b4ff2b7dfee5da20aa38253099ef1b4a64aced233c9afe29" }, "light_logo": { "url": "https://www.contoso.com/light_logo.png", "hash": "517d286edb416bb2625ccfcba9de78296e90da8e32330d4c9c8275c4c1c33737" } }

Microsoft Edge がロゴをダウンロードできる URL と、ダウンロードの整合性を検証するために使用される暗号化ハッシュ (SHA-256) を指定して、このポリシーを構成します。 ロゴは PNG または SVG 形式である必要があり、ファイル サイズが 16 MB を超えることはできません。 ロゴはダウンロードされてからキャッシュされ、URL またはハッシュが変更されるたびに再ダウンロードされます。 URL は、認証なしでアクセスできる URL である必要があります。

"default_logo" が必須となり、これは背景画像がない場合に使用されます。 "light_logo" が提供されている場合、これはユーザーの新規タブ ページに背景画像があるときに使用されます。 背景が透明な横長のロゴは、左寄せで垂直方向中央に配置するのがお勧めです。 ロゴの高さは最小 32 ピクセルで、アスペクト比は 1:1 から 4:1 までです。 "default_logo" は白と黒の背景に対して適切なコントラストを保ち、"light_logo" は背景画像に対して適切なコントラストを保つ必要があります。

このポリシーを有効にしている場合、Microsoft Edge では指定されたロゴがダウンロードされ、新規タブ ページに表示されます。 ユーザーがロゴを上書きしたり、非表示にしたりすることはできません。

このポリシーを無効にしているか、構成していない場合、Microsoft Edge では新規タブ ページに会社のロゴや Microsoft のロゴは表示されません。

SHA-256 ハッシュの確認方法については、「https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-filehash」を参照してください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Dictionary

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NewTabPageCompanyLogo
  - GP 名: 新規タブ ページの会社のロゴを設定する (不使用)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/スタートアップ、ホーム ページ、新規タブ ページ
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: NewTabPageCompanyLogo
  - 値の種類: REG_SZ

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\NewTabPageCompanyLogo = {
  "default_logo": {
    "hash": "cd0aa9856147b6c5b4ff2b7dfee5da20aa38253099ef1b4a64aced233c9afe29", 
    "url": "https://www.contoso.com/logo.png"
  }, 
  "light_logo": {
    "hash": "517d286edb416bb2625ccfcba9de78296e90da8e32330d4c9c8275c4c1c33737", 
    "url": "https://www.contoso.com/light_logo.png"
  }
}
```

  ##### コンパクト サンプル値:

  ```
  SOFTWARE\Policies\Microsoft\Edge\NewTabPageCompanyLogo = {"default_logo": {"hash": "cd0aa9856147b6c5b4ff2b7dfee5da20aa38253099ef1b4a64aced233c9afe29", "url": "https://www.contoso.com/logo.png"}, "light_logo": {"hash": "517d286edb416bb2625ccfcba9de78296e90da8e32330d4c9c8275c4c1c33737", "url": "https://www.contoso.com/light_logo.png"}}
  ```
  

  #### Mac の情報と設定
  
  - 基本設定キーの名前: NewTabPageCompanyLogo
  - サンプル値:
``` xml
<key>NewTabPageCompanyLogo</key>
<dict>
  <key>default_logo</key>
  <dict>
    <key>hash</key>
    <string>cd0aa9856147b6c5b4ff2b7dfee5da20aa38253099ef1b4a64aced233c9afe29</string>
    <key>url</key>
    <string>https://www.contoso.com/logo.png</string>
  </dict>
  <key>light_logo</key>
  <dict>
    <key>hash</key>
    <string>517d286edb416bb2625ccfcba9de78296e90da8e32330d4c9c8275c4c1c33737</string>
    <key>url</key>
    <string>https://www.contoso.com/light_logo.png</string>
  </dict>
</dict>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### NewTabPageHideDefaultTopSites

  #### 新規タブ ページから既定のトップ サイトを非表示にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge の新規タブ ページから既定のトップ サイトを非表示にします。

このポリシーを true に設定している場合、既定のトップ サイトのタイルが非表示になります。

このポリシーを false に設定しているか、構成していない場合、既定のトップ サイトのタイルが表示されたままになります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NewTabPageHideDefaultTopSites
  - GP 名: 新規タブ ページから既定のトップ サイトを非表示にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/スタートアップ、ホーム ページ、新規タブ ページ
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: NewTabPageHideDefaultTopSites
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: NewTabPageHideDefaultTopSites
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### NewTabPageLocation

  #### 新規タブ ページの URL を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  新規タブ ページの既定の URL を構成します。

このポリシーの推奨バージョンは現在機能せず、必須バージョンとまったく同じように機能します。

このポリシーは、新規タブを作成したとき (新規ウィンドウを開いたときを含む) に開くページを決定します。 また、新規タブ ページを開くように設定されている場合には、スタートアップ ページにも影響します。

このポリシーは、起動時に開くページについては決定しません。これは [RestoreOnStartup](#restoreonstartup) ポリシーによって制御されます。 また、新規タブ ページを開くように設定されている場合には、ホーム ページには影響しません。

このポリシーを構成していない場合、既定の新規タブ ページが使用されます。

このポリシー * と *[NewTabPageSetFeedType](#newtabpagesetfeedtype) ポリシーを構成している場合、このポリシーが優先されます。

無効な URL が提供されている場合、新規タブは about://blank で開きます。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NewTabPageLocation
  - GP 名: 新規タブ ページの URL を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/スタートアップ、ホーム ページ、新規タブ ページ
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/スタートアップ、ホーム ページ、新規タブ ページ
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: NewTabPageLocation
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"https://www.fabrikam.com"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: NewTabPageLocation
  - サンプル値:
``` xml
<string>https://www.fabrikam.com</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### NewTabPageManagedQuickLinks

  #### 新規タブ ページのクイック リンクを設定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 79 以降

  #### 説明

  既定では、ユーザーが追加したショートカットや閲覧履歴に基づくトップ サイトからのクイック リンクが、Microsoft Edge の新規タブ ページに表示されるようになっています。 このポリシーでは、以下のような JSON オブジェクトとして表現された新規タブ ページ上のクイック リンク タイルを、最大 3 つまで構成することができます。

[ { "url": "https://www.contoso.com", "title": "Contoso ポータル", "pinned": true/false }, ... ]

"url" フィールドは必須であり、"title" と "pinned" はオプションです。 "title" が指定されていない場合、URL が既定のタイトルとして使用されます。 "pinned" が指定されていない場合、 false が既定値になります。

Microsoft Edge では左から順にピン留めされたタイルがすべて表示され、ピン留めされていないタイルがその後に表示されます。

ポリシーが必須として設定されている場合、"pinned" フィールドは無視され、すべてのタイルがピン留めされます。 タイルはユーザーが削除することはできず、常にクイック リンク一覧の先頭に表示されます。

ポリシーが推奨通りに設定されている場合、ピン留めされているタイルは一覧に残りますが、ユーザーはそれらを編集したり削除したりすることができます。 ピン留めされていないクイック リンク タイルは既定のトップ サイトと同じように動作し、他の Web サイトの訪問頻度が上がった場合には一覧から追い出されます。 このポリシーを介してピン留めされていないリンクを既存のブラウザー プロファイルに適用する場合、ユーザーの閲覧履歴と比較したランク付け状況によっては、リンクが全く表示されない場合があります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Dictionary

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NewTabPageManagedQuickLinks
  - GP 名: 新規タブ ページのクイック リンクを設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/スタートアップ、ホーム ページ、新規タブ ページ
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/スタートアップ、ホーム ページ、新規タブ ページ
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: NewTabPageManagedQuickLinks
  - 値の種類: REG_SZ

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\NewTabPageManagedQuickLinks = [
  {
    "pinned": true, 
    "title": "Contoso Portal", 
    "url": "https://contoso.com"
  }, 
  {
    "title": "Fabrikam", 
    "url": "https://fabrikam.com"
  }
]
```

  ##### コンパクト サンプル値:

  ```
  SOFTWARE\Policies\Microsoft\Edge\NewTabPageManagedQuickLinks = [{"pinned": true, "title": "Contoso Portal", "url": "https://contoso.com"}, {"title": "Fabrikam", "url": "https://fabrikam.com"}]
  ```
  

  #### Mac の情報と設定
  
  - 基本設定キーの名前: NewTabPageManagedQuickLinks
  - サンプル値:
``` xml
<key>NewTabPageManagedQuickLinks</key>
<array>
  <dict>
    <key>pinned</key>
    <true/>
    <key>title</key>
    <string>Contoso Portal</string>
    <key>url</key>
    <string>https://contoso.com</string>
  </dict>
  <dict>
    <key>title</key>
    <string>Fabrikam</string>
    <key>url</key>
    <string>https://fabrikam.com</string>
  </dict>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### NewTabPagePrerenderEnabled

  #### 新しいタブ ページの事前読み込みを有効にしてレンダリングを高速化する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 85 以降

  #### 説明

  このポリシーを構成した場合、[新しいタブ] ページが事前に読み込まれ、ユーザーはこの設定を変更できません。 このポリシーを構成しない場合、事前読み込みが有効になり、ユーザーはこの設定を変更できません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NewTabPagePrerenderEnabled
  - GP 名: 新しいタブ ページの事前読み込みを有効にしてレンダリングを高速化する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/スタートアップ、ホーム ページ、新規タブ ページ
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/スタートアップ、ホーム ページ、新規タブ ページ
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: NewTabPagePrerenderEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: NewTabPagePrerenderEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### NewTabPageSetFeedType

  #### Microsoft Edge の新規タブ ページのエクスペリエンスを設定する (非推奨)

  >非推奨: このポリシーは推奨されなくなっています。 現在はサポートされていますが、将来のリリースで廃止されます。
  
  #### サポートされているバージョン:

  - Windows と macOS での 79 以降

  #### 説明

  新しいバージョンのエンタープライズの新しいタブページでは、異なるコンテンツタイプから選択する必要がなくなったため、このポリシーは非推奨になりました。 代わりに、ユーザーに表示されるコンテンツは、Microsoft 365 管理センターを通して制御できます。 Microsoft 365管理センターにアクセスするには、管理者アカウントで https://admin.microsoft.com にサインインします。 このポリシーは Microsoft Edge バージョン 90 で廃止されます。

新規タブ ページのフィード エクスペリエンスを、Microsoft News または Office 365 のどちらかから選択することができます。

このポリシーを 'News' に設定すると、ユーザーは新規タブ ページに Microsoft News フィード エクスペリエンスを表示することができます。

このポリシーを 'Office' に設定すると、Azure Active Directory ブラウザーにサインインしているユーザーは、新規タブ ページに Office 365 フィード エクスペリエンスを表示することができます。

このポリシーを無効にしているか、構成していない場合、次のようになります。

- Azure Active Directory ブラウザーにサインインしているユーザーには、標準の新規タブ ページ フィード エクスペリエンスに加えて、Office 365 の新規タブ ページ フィード エクスペリエンスが提供されます。

- Azure Active Directory ブラウザーにサインインしていないユーザーには、標準の新規タブ ページ エクスペリエンスを表示します。

このポリシー * と *[NewTabPageLocation](#newtabpagelocation) ポリシーを構成している場合、[NewTabPageLocation](#newtabpagelocation) ポリシーが優先されます。

既定の設定: 無効または未構成。

ポリシー オプション マッピング:

* News (0) = Microsoft News フィード エクスペリエンス

* Office (1) = Office 365 フィード エクスペリエンス

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NewTabPageSetFeedType
  - Microsoft Edge の新規タブ ページのエクスペリエンスを設定する (非推奨)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/スタートアップ、ホーム ページ、新規タブ ページ
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/スタートアップ、ホーム ページ、新規タブ ページ
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: NewTabPageSetFeedType
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: NewTabPageSetFeedType
  - サンプル値:
``` xml
<integer>0</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### RestoreOnStartup

  #### 起動時に実行する操作

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge の起動時の動作を指定します。

起動時に常に新しいタブを開く場合は、[RestoreOnStartupIsNewTabPage] を選択します。

最後に Microsoft Edge を閉じたときに開いていた URL をもう一度開く場合は、[RestoreOnStartupIsLastSession] を選択します。 閲覧セッションは元の状態に復元されます。 このオプションを使用すると、セッションに依存する設定や、終了時にアクションを実行する設定 (終了時の閲覧データのクリアや、セッションのみの Cookie など) は無効になります。

特定の URL のセットを開く場合は、[RestoreOnStartupIsURLs] を選択します。

この設定を無効にすることは、構成されていないままにしておくことと同じです。 ユーザーは Microsoft Edge でこの設定を変更できるようになります。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

ポリシー オプション マッピング:

* RestoreOnStartupIsNewTabPage (5) = 新しいタブを開く

* RestoreOnStartupIsLastSession (1) = 最後のセッションを復元する

* RestoreOnStartupIsURLs (4) = URL の一覧を開く

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: RestoreOnStartup
  - GP 名: 起動時に実行する操作
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/スタートアップ、ホーム ページ、新規タブ ページ
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/スタートアップ、ホーム ページ、新規タブ ページ
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: RestoreOnStartup
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000004
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: RestoreOnStartup
  - サンプル値:
``` xml
<integer>4</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### RestoreOnStartupURLs

  #### ブラウザーの起動時に開くサイト

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ブラウザーの起動時に自動的に開く Web サイトの一覧を指定します。 このポリシーを構成していない場合、起動時にサイトは開きません。

このポリシーは、[RestoreOnStartup](#restoreonstartup) ポリシーを "URL の一覧を開く" (4) に設定した場合にのみ機能します。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: RestoreOnStartupURLs
  - GP 名: ブラウザーが起動したときに開くサイト
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/スタートアップ、ホーム ページ、新規タブ ページ
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/スタートアップ、ホーム ページ、新規タブ ページ
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\RestoreOnStartupURLs
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended\RestoreOnStartupURLs
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\RestoreOnStartupURLs\1 = "https://contoso.com"
SOFTWARE\Policies\Microsoft\Edge\RestoreOnStartupURLs\2 = "https://www.fabrikam.com"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: RestoreOnStartupURLs
  - サンプル値:
``` xml
<array>
  <string>https://contoso.com</string>
  <string>https://www.fabrikam.com</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ShowHomeButton

  #### ツールバーに [ホーム] ボタンを表示する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge のツール バーに [ホーム] ボタンを表示します。

このポリシーを有効にすると、常に [ホーム] ボタンが表示されます。 このポリシーを無効にすると、[ホーム] ボタンは表示されません。

このポリシーを構成していない場合、ユーザーは [ホーム] ボタンを表示するかどうかを選択することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ShowHomeButton
  - GP 名: ツール バーに [ホーム] ボタンを表示する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/スタートアップ、ホーム ページ、新規タブ ページ
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/スタートアップ、ホーム ページ、新規タブ ページ
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ShowHomeButton
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ShowHomeButton
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ## 追加のポリシー

  [ページのトップへ](#microsoft-edge---policies)

  ### AddressBarMicrosoftSearchInBingProviderEnabled

  #### アドレス バーに表示される Bing の提案で Microsoft Search を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 81 以降

  #### 説明

  ユーザーがアドレス バーに検索文字列を入力したときに、アドレス バーの提案一覧に関連する Bing での Microsoft Search の提案を表示するようにします。 このポリシーを有効にしているか、構成していない場合、ユーザーは Microsoft Edge のアドレス バーの提案一覧に、Bing での Microsoft Search を利用した内部結果を表示することができます。 Bing での Microsoft Search の結果を表示するには、ユーザーはその組織の Azure AD アカウントを使用して Microsoft Edge にサインインしている必要があります。
このポリシーを無効にしている場合、ユーザーは Microsoft Edge のアドレス バーの提案一覧に、内部結果を表示することができなくなります。
Microsoft Edge バージョン 89 から、Bing がユーザーの既定の検索プロバイダーではない場合でも、Bing の Microsoft Search の候補を利用できます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AddressBarMicrosoftSearchInBingProviderEnabled
  - GP 名: アドレス バーに表示される Bing の提案で Microsoft Search を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AddressBarMicrosoftSearchInBingProviderEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AddressBarMicrosoftSearchInBingProviderEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AdsSettingForIntrusiveAdsSites

  #### 割り込み広告のあるサイトの広告設定

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 78 以降

  #### 説明

  割り込み広告のあるサイトで広告をブロックするかどうかを制御します。

ポリシー オプション マッピング:

* AllowAds (1) = すべてのサイトで広告を許可します

* BlockAds (2) = 煩わしい広告のあるサイトの広告をブロックします。 (既定値)

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AdsSettingForIntrusiveAdsSites
  - GP 名: 割り込み広告のあるサイトの広告設定
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AdsSettingForIntrusiveAdsSites
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AdsSettingForIntrusiveAdsSites
  - サンプル値:
``` xml
<integer>1</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AllowDeletingBrowserHistory

  #### ブラウザーの履歴とダウンロードの履歴を削除できるようにする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ブラウザーの履歴やダウンロードの履歴の削除を有効にし、ユーザーがこの設定を変更できないようにします。

このポリシーが無効になっている場合でも、閲覧やダウンロードの履歴が保持される保証はありません。ユーザーは直接履歴データベース ファイルを編集したり削除したりすることができ、ブラウザー自体は履歴項目の一部またはすべてをいつでも削除 (有効期限に基づいて) したり、アーカイブしたりすることができます。

このポリシーを有効にしているか、構成していない場合、ユーザーは閲覧の履歴やダウンロードの履歴を削除することができます。

このポリシーを無効している場合、ユーザーは閲覧やダウンロードの履歴を削除することができず、履歴の同期は無効になります。

このポリシーを有効にしている場合、[ClearBrowsingDataOnExit](#clearbrowsingdataonexit) ポリシーは有効にしないでください。なぜなら、どちらもデータの削除に対応しているからです。 両方のポリシーを有効にしている場合、[ClearBrowsingDataOnExit](#clearbrowsingdataonexit) ポリシーが優先され、このポリシーがどのように構成されているかにかかわらず、Microsoft Edge の終了時にすべてのデータが削除されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AllowDeletingBrowserHistory
  - GP 名: ブラウザーの履歴とダウンロードの履歴を削除できるようにする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AllowDeletingBrowserHistory
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AllowDeletingBrowserHistory
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AllowFileSelectionDialogs

  #### ファイル選択ダイアログを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge にファイル選択ダイアログを表示し、ローカル ファイルへのアクセスを許可します。

このポリシーを有効にしているか、構成していない場合、ユーザーは通常通りにファイル選択ダイアログを開くことができます。

このポリシーを無効にしている場合、ユーザーがファイル選択ダイアログのトリガーとなるアクション (お気に入りのインポート、ファイルのアップロード、リンクの保存など) を実行するたびにメッセージが表示され、ユーザーはファイル選択ダイアログで [キャンセル] をクリックしたものとみなされます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AllowFileSelectionDialogs
  - GP 名: ファイル選択ダイアログを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AllowFileSelectionDialogs
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AllowFileSelectionDialogs
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AllowPopupsDuringPageUnload

  #### ページのアンロード中にポップアップを表示できます (廃止)

  
  >不使用: このポリシーは廃止されており、Microsoft Edge 87 以降は機能しません。
  #### サポートされているバージョン:

  - Windows と macOS での 78 以降、87 まで

  #### 説明

  このポリシーでは、管理者は、ページのアンロード中にポップアップを表示できるように指定することができるようになります。

このポリシーを有効に設定すると、ページのアンロード中にポップアップを表示できるようになります。

このポリシーを無効に設定するか、設定しない場合、ページのアンロード中にポップアップを表示できなくなります。 これは仕様どおりです: (https://html.spec.whatwg.org/#apis-for-creating-and-navigating-browsing-contexts-by-name))。

このポリシーは Microsoft Edge 88 で削除され、設定されている場合は無視されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - 一意の GP 名: AllowPopupsDuringPageUnload
  - GP 名: ページのアンロード中にポップアップを表示できます (廃止)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AllowPopupsDuringPageUnload
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AllowPopupsDuringPageUnload
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AllowSurfGame

  #### サーフィン ゲームを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 83 以降

  #### 説明

  このポリシーを無効にしている場合、デバイスがオフラインのときや、ユーザーが edge://surf に移動したときに、ユーザーはサーフィン ゲームをプレイすることができなくなります。

このポリシーを有効にしているか、構成していない場合、ユーザーはサーフィン ゲームをプレイすることができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AllowSurfGame
  - GP 名: サーフィン ゲームを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AllowSurfGame
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AllowSurfGame
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AllowSyncXHRInPageDismissal

  #### ページが同期 XHR 要求をページの解除中に送信できるようにする (非推奨)

  >非推奨: このポリシーは推奨されなくなっています。 現在はサポートされていますが、将来のリリースで廃止されます。
  
  #### サポートされているバージョン:

  - Windows と macOS での 79 以降

  #### 説明

  このポリシーは、企業の Web コンテンツがページ解除中に XHR 要求の同期を却下する変更と互換していないことが判明した場合に、Web コンテンツの更新に時間を割くための短期のメカニズムとしてのみ機能することを目的としているため、推奨されていません。 Microsoft Edge バージョン 88 では機能しません。

このポリシーでは、ページの解除中にページが同期 XHR 要求を送信できるように指定することができます。

このポリシーを有効にしている場合、ページは同期 XHR 要求をページの解除中に送信することができます。

このポリシーを無効にしているか、構成していない場合、ページは同期 XHR 要求をページの解除中に送信することができません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AllowSyncXHRInPageDismissal
  - GP 名: ページが同期 XHR 要求をページの解除中に送信できるようにする (非推奨)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AllowSyncXHRInPageDismissal
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AllowSyncXHRInPageDismissal
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AllowTokenBindingForUrls

  #### Microsoft Edge がトークンのバインドの確立を試行するサイトの一覧を構成する

  
  
  #### サポートされているバージョン:

  - Windows での 83 以降

  #### 説明

  ブラウザーがトークンのバインド プロトコルを実行しようと試みるサイトの URL パターンの一覧を設定します。
この一覧にあるドメインの場合、ブラウザーはトークンのバインドの ClientHello を TLS ハンドシェイクで送信します (https://tools.ietf.org/html/rfc8472) を参照してください)。
サーバが有効な ServerHello 応答を返した場合、ブラウザーは後続の HTTPS 要求でトークンのバインド メッセージを作成して送信します。 詳細については、「https://tools.ietf.org/html/rfc8471」を参照してください。

この一覧が空の場合、トークンのバインドは無効になります。

このポリシーは、仮想保護モード機能を備えた Windows 10 デバイスでのみ使用できます。

Microsoft Edge 86 以降、このポリシーでは動的更新はサポートされなくなりました。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AllowTokenBindingForUrls
  - GP 名: Microsoft Edge がトークンのバインドの確立を試行するサイトの一覧を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\AllowTokenBindingForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\AllowTokenBindingForUrls\1 = "mydomain.com"
SOFTWARE\Policies\Microsoft\Edge\AllowTokenBindingForUrls\2 = "[*.]mydomain2.com"
SOFTWARE\Policies\Microsoft\Edge\AllowTokenBindingForUrls\3 = "[*.].mydomain2.com"

```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### AllowTrackingForUrls

  #### 特定のサイトの追跡防止の例外を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 78 以降

  #### 説明

  追跡防止の対象外となる URL パターンの一覧を構成します。

このポリシーを構成している場合、構成した URL パターンの一覧は追跡防止の対象外となります。

このポリシーを構成していない場合、ユーザーの個人用の構成、または "ユーザーの Web 閲覧アクティビティの追跡のブロック" ポリシー (設定されている場合) からのグローバルな既定値がすべてのサイトで使用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AllowTrackingForUrls
  - GP 名: 特定のサイトの追跡防止の例外を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\AllowTrackingForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\AllowTrackingForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\AllowTrackingForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AllowTrackingForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AlternateErrorPagesEnabled

  #### Web ページが見つからない場合に、似通ったページを候補として表示する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 80 以降

  #### 説明

  Microsoft Edge が Webサービスへの接続を発行し、DNS エラーなどの接続に関する問題に対する URL や検索候補を生成します。

このポリシーを有効にしている場合、Web サービスを使用してネットワーク エラーに関する URL や検索候補が生成されます。

このポリシーを無効にしている場合、Web サービスの呼び出しは行われず、標準のエラー ページが表示されます。

このポリシーを構成していない場合、Microsoft Edge は、edge://settings/privacy のサービスで設定されているユーザー設定を尊重します。
具体的には、[**Web ページが見つからない場合に、似通ったページを候補として表示する**] トグルがあり、ユーザーはこれをオンまたはオフに切り替えることができます。 このポリシー (AlternateErrorPagesEnabled) を有効にしている場合、[Web ページが見つからない場合に、似通ったページを候補として表示する] 設定はオンになっていますが、ユーザーがトグルを使用して設定を変更することはできません。 このポリシーを無効にしている場合、[Web ページが見つからない場合に、似通ったページを候補として表示する] 設定はオフになっており、ユーザーがトグルを使用して設定を変更することはできません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AlternateErrorPagesEnabled
  - GP 名: Web ページが見つからない場合に、似通ったページを候補として表示する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: AlternateErrorPagesEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AlternateErrorPagesEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AlwaysOpenPdfExternally

  #### 常に PDF ファイルを外部で開く

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge の内部 PDF ビューアーを無効にします。

このポリシーを有効にしている場合、Microsoft Edge では PDF ファイルはダウンロードとして扱われ、ユーザーは既定のアプリケーションを使用して PDF ファイルを開くことができます。

このポリシーを構成してしないか、無効にしている場合、Microsoft Edge は (ユーザーが無効にしない限り) PDF ファイルを開きます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AlwaysOpenPdfExternally
  - GP 名: 常に PDF ファイルを外部で開く
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AlwaysOpenPdfExternally
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AlwaysOpenPdfExternally
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AmbientAuthenticationInPrivateModesEnabled

  #### InPrivate プロファイルとゲスト プロファイルに対してアンビエント認証を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 81 以降

  #### 説明

  このポリシーを設定すると、Microsoft Edge の InPrivate プロファイルとゲスト プロファイルのアンビエント認証を許可または禁止することができます。

アンビエント認証は、NTLM/Kerberos/ネゴシエート チャレンジ/応答などのスキームを介して明示的な資格情報が提供されていない場合に、既定の資格情報を使用して HTTP 認証を行うものです。

ポリシーを [RegularOnly] に設定している場合、標準のセッションのみでアンビエント認証が許可されます。 InPrivate セッションとゲスト セッションでは、アンビエント認証は許可されません。

ポリシーを [InPrivateAndRegular] に設定している場合、InPrivate セッションと標準のセッションでアンビエント認証が許可されます。 ゲスト セッションでは、アンビエント認証は許可されません。

ポリシーを [GuestAndRegular] に設定している場合、ゲスト セッションと標準のセッションでアンビエント認証が許可されます。 InPrivate セッションでは、アンビエント認証は許可されません。

ポリシーを [All] に設定している場合、すべてのセッションでアンビエント認証が許可されます。

通常のプロファイルでは、アンビエント認証は常に許可されています。

Microsoft Edge のバージョン 81 以降では、ポリシーを設定しないままにしておくと、通常のセッションでのみアンビエント認証が有効になります。

ポリシー オプション マッピング:

* RegularOnly (0) = 通常のセッションでのみアンビエント認証を有効にする

* InPrivateAndRegular (1) = InPrivate セッションと通常のセッションでアンビエント認証を有効にする

* GuestAndRegular (2) = ゲスト セッションと通常のセッションでアンビエント認証を有効にする

* All (3) = 通常のセッション、InPrivate セッション、ゲスト セッションでアンビエント認証を有効にする

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AmbientAuthenticationInPrivateModesEnabled
  - GP 名: InPrivate プロファイルとゲスト プロファイルに対してアンビエント認証を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AmbientAuthenticationInPrivateModesEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AmbientAuthenticationInPrivateModesEnabled
  - サンプル値:
``` xml
<integer>0</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AppCacheForceEnabled

  #### 既定でオフになっている場合でも、App Cache 機能を再度有効にすることを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 84 以降

  #### 説明

  このポリシーを true に設定すると、Microsoft Edge の AppCache が既定で利用できない場合でも、AppCache が有効になります。

このポリシーを false に設定した場合、または設定しなかった場合、AppCache は Microsoft Edge の既定値に従います。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AppCacheForceEnabled
  - GP 名: 既定でオフになっている場合でも、App Cache 機能を再度有効にすることを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AppCacheForceEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AppCacheForceEnabled
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ApplicationLocaleValue

  #### アプリケーション ロケールを設定する

  
  
  #### サポートされているバージョン:

  - Windows での 77 以降

  #### 説明

  Microsoft Edge でアプリケーション ロケールを構成し、ユーザーがロケールを変更できないようにします。

このポリシーを有効にしている場合、Microsoft Edge は指定されたロケールを使用します。 構成されたロケールがサポートされていない場合、代わりに "en-US" が使用されます。

この設定を無効にしているか、構成していない場合、Microsoft Edge では、ユーザーが指定した優先ロケール (設定されている場合) か、フォールバック ロケールである "en-US" のいずれかが使用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ApplicationLocaleValue
  - GP 名: アプリケーション ロケールを設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ApplicationLocaleValue
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"en"
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### AudioCaptureAllowed

  #### オーディオ キャプチャの許可またはブロック

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Web サイトへのアクセス権をオーディオ キャプチャ デバイスに付与するためのメッセージをユーザーに表示するかどうかを設定することができます。 このポリシーは、[AudioCaptureAllowedUrls](#audiocaptureallowedurls) 一覧で構成されたものを除くすべての URL に適用されます。

このポリシーを有効にしているか、構成していない場合 (既定の設定)、[AudioCaptureAllowedUrls](#audiocaptureallowedurls) 一覧の URL 以外のオーディオ キャプチャへのアクセスに対して、確認を求めるメッセージが表示されます。 一覧に記載されている URL については、確認のメッセージなしでアクセス許可が付与されます。

このポリシーを無効にしている場合、ユーザーに確認を求めるメッセージは表示されず、オーディオ キャプチャは [AudioCaptureAllowedUrls](#audiocaptureallowedurls) で構成されている URL に対してのみアクセスが許可されます。

このポリシーは内蔵マイクだけでなく、あらゆる種類の音声入力に影響します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AudioCaptureAllowed
  - GP 名: オーディオ キャプチャの許可またはブロック
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AudioCaptureAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AudioCaptureAllowed
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AudioCaptureAllowedUrls

  #### アクセス許可を要求することなくオーディオ キャプチャ デバイスにアクセスできるサイト

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  URL パターンに基づいて、ユーザーにアクセス許可を求めずにオーディオ キャプチャ デバイスを使用することができる Web サイトを指定します。 この一覧のパターンは、要求 URL のセキュリティ オリジンと照合されます。 それらが一致する場合、サイトには自動的にオーディオ キャプチャ デバイスへのアクセス許可が付与されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前:: AudioCaptureAllowedUrls
  - GP 名: アクセス許可を要求することなくオーディオ キャプチャ デバイスにアクセスできるサイト
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\AudioCaptureAllowedUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\AudioCaptureAllowedUrls\1 = "https://www.contoso.com/"
SOFTWARE\Policies\Microsoft\Edge\AudioCaptureAllowedUrls\2 = "https://[*.]contoso.edu/"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AudioCaptureAllowedUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com/</string>
  <string>https://[*.]contoso.edu/</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AudioSandboxEnabled

  #### オーディオ サンドボックスの実行を許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 81 以降

  #### 説明

  このポリシーは、オーディオ プロセスのサンドボックスを制御します。

このポリシーを有効にしている場合、オーディオ プロセスはセキュリティで保護された状態で実行されます。

このポリシーを無効にしている場合、オーディオ プロセスはセキュリティ保護なしで実行され、WebRTC オーディオ処理モジュールはレンダラー プロセスで実行されます。
これにより、オーディオ サブシステムがセキュリティ保護されていない状態で実行されることに関連するセキュリティ リスクにさらされることになります。

このポリシーを構成していない場合、オーディオ サンドボックスの既定の構成が使用されますが、これはプラットフォームによって異なる可能性があります。

このポリシーは、企業がサンドボックスに干渉するセキュリティ ソフトウェアのセットアップを使用している場合に、オーディオ サンドボックスを無効にする柔軟性を提供することを目的としています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AudioSandboxEnabled
  - GP 名: オーディオ サンドボックスの実行を許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AudioSandboxEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AudioSandboxEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AutoImportAtFirstRun

  #### 初回実行時に、別のブラウザーのデータや設定を自動的にインポートする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーを有効にしている場合、指定したブラウザーからサポートされているすべてのデータの種類と設定が、初回実行時に警告なしに自動でインポートされます。 最初の実行エクスペリエンスの間は、インポート セクションもスキップされます。

Microsoft Edge 従来版からのブラウザー データは、このポリシーの値に関係なく、初回実行時に常に警告なしで移行されます。

このポリシーが [FromDefaultBrowser] に設定されている場合、管理対象デバイスの既定のブラウザーに対応するデータの種類がインポートされます。

このポリシーの値として指定されたブラウザーが管理対象デバイスに存在しない場合、Microsoft Edge はユーザーへの通知なしにそのままインポートをスキップします。

このポリシーを "DisabledAutoImport" に設定している場合、最初の実行エクスペリエンスのインポート セクションは完全にスキップされ、Microsoft Edge はブラウザーのデータや設定を自動的にインポートしません。

このポリシーを [FromInternetExplorer] に設定している場合、以下のデータの種類が Internet Explorer からインポートされます。
1. お気に入りまたはブックマーク
2. 保存されたパスワード
3. 検索エンジン
4. 閲覧の履歴
5. ホーム ページ

このポリシーを [FromGoogleChrome] に設定している場合、以下のデータの種類が Google Chrome からインポートされます。
1. お気に入り
2. 保存されたパスワード
3. アドレスなど
4. 支払い情報
5. 閲覧の履歴
6. 設定
7. ピン留めされているタブと開いているタブ
8. 拡張機能
9. Cookie

注: Google Chrome からインポートされるものの詳細については、「[https://go.microsoft.com/fwlink/?linkid=2120835](https://go.microsoft.com/fwlink/?linkid=2120835)」を参照してください。 

このポリシーを [FromSafari] に設定すると、ユーザー データは Microsoft Edge にインポートされなくなります。 これは、Mac でのフルディスクアクセスの仕組みによるものです。
macOS Mojave 以降では、Safari データを自動的に、または無人で Microsoft Edge にインポートすることはできません。

Microsoft Edge のバージョン 83 以降で、このポリシーを [FromMozillaFirefox] に設定している場合、以下のデータの種類が Mozilla Firefox からインポートされます。
1. お気に入りまたはブックマーク
2. 保存されたパスワード
3. アドレスなど
4. 閲覧の履歴

管理されているデバイスで特定のデータの種類をインポートできないように制限したい場合は、このポリシーを [ImportAutofillFormData](#importautofillformdata)、[ImportBrowserSettings](#importbrowsersettings)、[ImportFavorites](#importfavorites) などの他のポリシーと一緒に使用することができます。

ポリシー オプション マッピング:

* FromDefaultBrowser (0) = サポートされているすべてのデータの種類と設定を、既定のブラウザーから自動的にインポートする

* FromInternetExplorer (1) = サポートされているすべてのデータの種類と設定を、Internet Explorer から自動的にインポートする

* FromGoogleChrome (2) = サポートされているすべてのデータの種類と設定を、Google Chrome から自動的にインポートする

* FromSafari (3) = サポートされているすべてのデータの種類と設定を、Safari から自動的にインポートする

* DisabledAutoImport (4) = 自動インポートを無効にし、最初の実行エクスペリエンスのインポート セクションをスキップする

* FromMozillaFirefox (5) = サポートされているすべてのデータの種類と設定を、Mozilla Firefox から自動的にインポートする

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AutoImportAtFirstRun
  - GP 名: 初回実行時に、別のブラウザーのデータや設定を自動的にインポートする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AutoImportAtFirstRun
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AutoImportAtFirstRun
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AutoLaunchProtocolsFromOrigins

  #### ユーザーにプロンプ​​トを表示せずに、リストされたオリジンから外部アプリケーションを起動できるプロトコルのリストを定義する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 85 以降

  #### 説明

  プロトコル リストを設定し、プロトコルごとに許可されたオリジンのパターンの関連リストを設定できます。これにより、ユーザーにプロンプ​​トを表示せずに外部アプリケーションを起動できます。 プロトコルを一覧表示するときは、末尾のセパレータを含めないでください。 たとえば、「skype:」または「skype://」の代わりに「skype」を使用します。

このポリシーを構成すると、次の場合にのみ、プロトコルはポリシーによるプロンプトを表示せずに外部アプリケーションを起動できます。

- プロトコルが一覧表示されます。

- プロトコルを起動しようとするサイトのオリジンは、そのプロトコルの allowed_blood リスト内のオリジンのパターンの 1 つと一致します。

いずれかの条件が false の場合、外部プロトコルの起動プロンプトはポリシーで省略されません。

このポリシーを構成しないと、プロンプトなしでプロトコルを起動できません。 ユーザーは、[External Protocol DialogShowAlwaysOpenCheckbox](#externalprotocoldialogshowalwaysopencheckbox) ポリシーが [無効] に設定されていない限り、プロトコルごとまたはサイトごとにプロンプトからオプションを選択できます。 このポリシーは、ユーザーによって設定されたプロトコルごとまたはサイトごとのプロンプト除外には影響しません。

オリジンの一致パターンは、[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) で文書化されている [URLBlocklist](#urlblocklist) ポリシーの場合と同様の形式を使用します。

ただし、このポリシーのオリジンの一致パターンには、「/path」または「@query」要素を含めることはできません。 「/path」または「@query」要素を含むパターンは無視されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Dictionary

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AutoLaunchProtocolsFromOrigins
  - GP 名: ユーザーにプロンプ​​トを表示せずに、リストされたオリジンから外部アプリケーションを起動できるプロトコルのリストを定義する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AutoLaunchProtocolsFromOrigins
  - 値の種類: REG_SZ

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\AutoLaunchProtocolsFromOrigins = [
  {
    "allowed_origins": [
      "example.com", 
      "http://www.example.com:8080"
    ], 
    "protocol": "spotify"
  }, 
  {
    "allowed_origins": [
      "https://example.com", 
      "https://.mail.example.com"
    ], 
    "protocol": "teams"
  }, 
  {
    "allowed_origins": [
      "*"
    ], 
    "protocol": "outlook"
  }
]
```

  ##### コンパクト サンプル値:

  ```
  SOFTWARE\Policies\Microsoft\Edge\AutoLaunchProtocolsFromOrigins = [{"allowed_origins": ["example.com", "http://www.example.com:8080"], "protocol": "spotify"}, {"allowed_origins": ["https://example.com", "https://.mail.example.com"], "protocol": "teams"}, {"allowed_origins": ["*"], "protocol": "outlook"}]
  ```
  

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AutoLaunchProtocolsFromOrigins
  - サンプル値:
``` xml
<key>AutoLaunchProtocolsFromOrigins</key>
<array>
  <dict>
    <key>allowed_origins</key>
    <array>
      <string>example.com</string>
      <string>http://www.example.com:8080</string>
    </array>
    <key>protocol</key>
    <string>spotify</string>
  </dict>
  <dict>
    <key>allowed_origins</key>
    <array>
      <string>https://example.com</string>
      <string>https://.mail.example.com</string>
    </array>
    <key>protocol</key>
    <string>teams</string>
  </dict>
  <dict>
    <key>allowed_origins</key>
    <array>
      <string>*</string>
    </array>
    <key>protocol</key>
    <string>outlook</string>
  </dict>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AutoOpenAllowedForURLs

  #### AutoOpenFileTypes を適用できる URL

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 85 以降

  #### 説明

  [AutoOpenFileTypes](#autoopenfiletypes) が適用される URL の一覧。 このポリシーは、ダウンロード シェルフ... > [常にこの種類のファイルを開く] メニュー エントリを介してユーザーが設定した自動的に開く値には影響しません。

このポリシーで URL を設定すると、URL がこのセットの一部であり、ファイルの種類が [AutoOpenFileTypes](#autoopenfiletypes) に記載されている場合にのみ、ポリシーによってファイルが自動的に開きます。 いずれかの条件が false の場合、ダウンロードはポリシーによって自動的に開かれません。

このポリシーを設定しない場合、ファイルの種類が [AutoOpenFileTypes](#autoopenfiletypes) にあるすべてのダウンロードが自動的に開きます。

URL パターンは [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) に応じて書式設定する必要があります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AutoOpenAllowedForURLs
  - GP 名: AutoOpenFileTypes を適用できる URL
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\1 = "example.com"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\2 = "https://ssl.server.com"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\3 = "hosting.com/good_path"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\4 = "https://server:8080/path"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\5 = ".exact.hostname.com"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AutoOpenAllowedForURLs
  - サンプル値:
``` xml
<array>
  <string>example.com</string>
  <string>https://ssl.server.com</string>
  <string>hosting.com/good_path</string>
  <string>https://server:8080/path</string>
  <string>.exact.hostname.com</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AutoOpenFileTypes

  #### ダウンロード時に自動的に開く必要があるファイルの種類の一覧

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 85 以降

  #### 説明

  このポリシーは、ダウンロード時に自動的に開く必要があるファイルの種類の一覧を設定します。 注: ファイルの種類を記載するときは、先頭の区切り記号を含めないでください。したがって、".txt" の代わりに "txt" のようにしてください。

既定では、これらのファイルの種類はすべての URL で自動的に開かれます。 [AutoOpenAllowedForURLs](#autoopenallowedforurls) ポリシーを使用して、これらのファイルの種類を自動的に開く URL を制限できます。

自動的に開く必要があるファイルの種類は、有効になっている Microsoft Defender SmartScreen チェックに従い、チェックに失敗した場合は開きません。

ユーザーが自動的に開くように既に指定したファイルの種類は、ダウンロードしても引き続き実行されます。 ユーザーは引き続き、自動的に開くファイルの種類を指定できます。

このポリシーを設定しない場合、ユーザーが自動的に開くように既に指定したファイルの種類のみ、ダウンロードしても実行されます。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AutoOpenFileTypes
  - GP 名: ダウンロード時に自動的に開く必要があるファイルの種類の一覧
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\AutoOpenFileTypes
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\AutoOpenFileTypes\1 = "exe"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenFileTypes\2 = "txt"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AutoOpenFileTypes
  - サンプル値:
``` xml
<array>
  <string>exe</string>
  <string>txt</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AutofillAddressEnabled

  #### アドレスのオートフィルを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ユーザーがオートフィル機能を有効にし、以前に格納された情報を使用して、Web フォームのアドレス情報を自動的に入力できるようにします。

このポリシーを無効にしている場合、オートフィルがアドレス情報を提案したり入力したりすることはなく、また、Web 閲覧中にユーザーが送信する可能性のある追加のアドレス情報を保存したりすることもありません。

このポリシーを有効にしているか、構成していない場合、ユーザーはユーザー インターフェイスでのアドレスのオートフィルを制御することができます。

このポリシーを無効にしている場合、支払いとパスワード フォームを除くすべての Web フォームでのすべてのアクティビティも停止されます。 これ以上の入力内容は保存されず、Microsoft Edge が以前の入力内容を元に提案をしたり、オートフィルを実行したりすることはありません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AutofillAddressEnabled
  - GP 名: 住所のオートフィルを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: AutofillAddressEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AutofillAddressEnabled
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AutofillCreditCardEnabled

  #### クレジット カードのオートフィルを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ユーザーが Microsoft Edge のオートフィル機能を有効にし、以前に格納された情報を使用して、Web フォームのクレジット カード情報を自動的に入力できるようにします。

このポリシーを無効にしている場合、オートフィルがクレジット カード情報を提案したり入力したりすることはなく、また、Web 閲覧中にユーザーが送信する可能性のある追加のクレジット カード情報を保存したりすることもありません。

このポリシーを有効にしているか、構成していない場合、ユーザーはクレジット カードのオートフィルを制御することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AutofillCreditCardEnabled
  - GP 名: クレジット カードのオートフィルを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: AutofillCreditCardEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AutofillCreditCardEnabled
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### AutoplayAllowed

  #### Web サイトのメディア自動再生を許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 78 以降

  #### 説明

  このポリシーでは、Web サイトのメディア自動再生ポリシーを設定します。

既定の設定である "未構成" は、現在のメディア自動再生の設定を尊重し、ユーザーが自動再生の設定を構成できるようにします。

"有効" に設定すると、メディア自動再生が "許可" に設定されます。  すべての Web サイトでのメディア自動再生が許可されます。 ユーザーがこのポリシーを上書きすることはできません。

"無効" に設定すると、メディア自動再生が "ブロック" に設定されます。  Web サイトでのメディア自動再生が禁止されます。 ユーザーがこのポリシーを上書きすることはできません。

このポリシーを有効にするには、一度タブを閉じてから、もう一度開く必要があります。


  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: AutoplayAllowed
  - GP 名: Web サイトのメディア自動再生を許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: AutoplayAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: AutoplayAllowed
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### BackgroundModeEnabled

  #### Microsoft Edge を終了した後も引き続きバックグラウンド アプリを実行する

  
  
  #### サポートされているバージョン:

  - Windows での 77 以降

  #### 説明

  Microsoft Edge のプロセスが OS へのサインイン時に起動し、最後のブラウザー ウィンドウを閉じた後も実行し続けることができるようになります。 このシナリオでは、バックグラウンド アプリと現在の閲覧セッションは、セッション Cookie を含めてアクティブなままになります。 開いているバックグラウンド プロセスについてはシステム トレイにアイコンが表示され、そこからいつでも閉じることができます。

このポリシーを有効にしている場合、バックグラウンド モードがオンになります。

このポリシーを無効にしている場合、バックグラウンド モードがオフになります。

このポリシーを構成していない場合、初期状態ではバックグラウンド モードがオフになり、ユーザーは edge://settings/system でその動作を構成することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: BackgroundModeEnabled
  - GP 名: Microsoft Edge を終了した後も引き続きバックグラウンド アプリを実行する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: BackgroundModeEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### BackgroundTemplateListUpdatesEnabled

  #### コレクションやテンプレートを使用する他の機能で利用可能なテンプレートの一覧をバックグラウンドで更新できるようにする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 79 以降

  #### 説明

  コレクションやテンプレートを使用する他の機能で利用可能なテンプレートの一覧をバックグラウンドで更新できるようにする機能を有効または無効にすることができるようになります。  テンプレートは、ページをコレクションに保存するときに、Web ページからリッチなメタデータを抽出するために使用されます。

この設定を有効にしているか、設定が未構成の場合、利用可能なテンプレートの一覧が 24 時間ごとに Microsoft サービスからバックグラウンドでダウンロードされます。

この設定を無効にしている場合、利用可能なテンプレートの一覧がオンデマンドでダウンロードされます。 この種類のダウンロードは、コレクションやその他の機能のパフォーマンスを多少低下させてしまう可能性があります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: BackgroundTemplateListUpdatesEnabled
  - GP 名: コレクションやテンプレートを使用する他の機能で利用可能なテンプレートの一覧をバックグラウンドで更新できるようにする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: BackgroundTemplateListUpdatesEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: BackgroundTemplateListUpdatesEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### BingAdsSuppression

  #### Bing 検索結果でのすべての広告のブロック

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 83 以降

  #### 説明

  Bing.com で広告のない検索エクスペリエンスを有効にします。

このポリシーを有効にしている場合、ユーザーは bing.com で検索するときに広告のない検索エクスペリエンスを利用できるようになります。 同時に、セーフサーチの設定は "Strict" に設定され、ユーザーが変更することはできません。

このポリシーを構成していない場合、既定のエクスペリエンスでは、bing.com での検索結果に広告が表示されます。 既定ではセーフサーチは "標準" に設定されており、ユーザーが変更することができます。

このポリシーは、Microsoft によって EDU テナントとして識別された K-12 SKU でのみ利用可能です。

このポリシーについての詳細を調べる場合や、以下のシナリオに当てはまる場合には、「[https://go.microsoft.com/fwlink/?linkid=2119711](https://go.microsoft.com/fwlink/?linkid=2119711)」を参照してください。

* EDU のテナントがあるのに、ポリシーが機能しない場合。

* 広告のない検索エクスペリエンスを実行したことで、IP アドレスがホワイトリストに登録された場合。

* Microsoft Edge 従来版で広告のない検索エクスペリエンスを実行していて、新しいバージョンの Microsoft Edge へとアップグレードしたい場合。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: BingAdsSuppression
  - GP 名: Bing 検索結果でのすべての広告のブロック
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: BingAdsSuppression
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: BingAdsSuppression
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### BlockThirdPartyCookies

  #### サード パーティの Cookie のブロック

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  アドレス バーに表示されているドメイン以外からの Web ページの要素による Cookie の設定をブロックします。

このポリシーを有効にしている場合、アドレス バーに表示されているドメイン以外からの Web ページの要素は、Cookie を設定することができません。

このポリシーを無効にしている場合、アドレス バーに表示されているドメイン以外からの Web ページの要素が、Cookie を設定することができるようになります。

このポリシーを構成していない場合、サードパーティの Cookie は有効になっており、ユーザーはこの設定を変更することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: BlockThirdPartyCookies
  - GP 名: サード パーティの Cookie のブロック
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: BlockThirdPartyCookies
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: BlockThirdPartyCookies
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### BrowserAddProfileEnabled

  #### ID のポップアップ メニューまたは [設定] ページからプロファイルの作成を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  **プロファイルの追加**オプションを使用して、ユーザーが新しいプロファイルを作成できるようにします。
このポリシーを有効にしているか、構成していない場合、Microsoft Edge では、ユーザーが [ID] ポップアップ メニューの**プロファイルの追加**や [設定] ページを使用して新しいプロファイルを作成できるようになります。

このポリシーを無効にしている場合、ユーザーは [ID] ポップアップ メニューや [設定] ページから新しいプロファイルを追加することができなくなります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: BrowserAddProfileEnabled
  - GP 名: ID のポップアップ メニューまたは [設定] ページからプロファイルの作成を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: BrowserAddProfileEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: BrowserAddProfileEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### BrowserGuestModeEnabled

  #### ゲスト モードを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge でゲスト プロファイルの使用を許可するオプションを有効にします。 ゲスト プロファイルでは、ブラウザーは既存のプロファイルから閲覧データをインポートせず、すべてのゲスト プロファイルが閉じられたときに閲覧データを削除します。

このポリシーを有効にしているか、構成していない場合、Microsoft Edge では、ユーザーがゲスト プロファイルで閲覧できるようになります。

このポリシーを無効にしている場合、Microsoft Edge では、ユーザーにゲスト プロファイルでの閲覧を許可しません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: BrowserGuestModeEnabled
  - GP 名: ゲスト モードを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: BrowserGuestModeEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: BrowserGuestModeEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### BrowserNetworkTimeQueriesEnabled

  #### ブラウザー ネットワーク時間サービスへのクエリを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge が不定期にブラウザー ネットワーク時間サービスにクエリを送信し、正確なタイムスタンプを取得することを防止します。

このポリシーを無効にしている場合、Microsoft Edge はブラウザー ネットワーク時間サービスにクエリを送信しなくなります。

このポリシーを有効にしているか、構成していない場合、Microsoft Edge は不定期にブラウザー ネットワーク時間サービスにクエリを送信します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: BrowserNetworkTimeQueriesEnabled
  - GP 名: ブラウザー ネットワーク時間サービスへのクエリを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: BrowserNetworkTimeQueriesEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: BrowserNetworkTimeQueriesEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### BrowserSignin

  #### ブラウザーへのサインイン設定

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ユーザーが自分のアカウントで Microsoft Edge にサインインし、同期やシングル サインオンなどのアカウント関連サービスを利用できるかどうかを指定します。 同期の可用性を制御するには、代わりに [SyncDisabled](#syncdisabled) ポリシーを使用します。

このポリシーを 「無効にする」 に設定する場合、[NonRemovableProfileEnabled](#nonremovableprofileenabled) ポリシーも無効に設定します。これは、[NonRemovableProfileEnabled](#nonremovableprofileenabled) が、自動的にサインインしたブラウザーのプロファイルの作成を無効にするためです。 両方のポリシーが設定されている場合、Microsoft Edge は "ブラウザーへのサインインを無効にする" ポリシーを使用し、[NonRemovableProfileEnabled](#nonremovableprofileenabled) が無効に設定されているかのように動作します。

このポリシーを 「有効にする」 に設定している場合、ユーザーはブラウザーにサインインできるようになります。 ブラウザーにサインインしても、既定で同期がオンになっているわけではありません。この機能を使用するには、ユーザーが別途オプトインする必要があります。

このポリシーを "強制する" に設定している場合、ユーザーがブラウザーを使用するには、プロファイルにサインインする必要があります。 ドメイン管理者によって同期が無効にされているか、または [SyncDisabled](#syncdisabled) ポリシーで同期が無効にされていない限り、既定ではこれによりユーザーが自分のアカウントに同期するかどうかを選択できるようになります。 [BrowserGuestModeEnabled](#browserguestmodeenabled) ポリシーの既定値は、false に設定されています。

このポリシーを構成していない場合、ユーザーはブラウザーへのサインイン オプションを有効にするかどうかを決定し、適切な方法で使用することができます。

ポリシー オプション マッピング:

* Disable (0) = ブラウザーへのサインインを無効にする

* Enable (1) = ブラウザーへのサインインを有効にする

* Force (2) = ユーザーのブラウザーの使用について、サインインを強制する

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: BrowserSignin
  - GP 名: ブラウザーへのサインイン設定
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: BrowserSignin
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: BrowserSignin
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### BuiltInDnsClientEnabled

  #### 組み込みの DNS クライアントを使用する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  組み込みの DNS クライアントを使用するかどうかを制御します。

これは使用されるDNS サーバーに影響を与えるものではありません。サーバーとの通信に使用されるソフトウェア スタックにのみ影響を与えます。 たとえば、オペレーティング システムがエンタープライズ DNS サーバーを使用するように構成されている場合、そのサーバーは組み込みの DNS クライアントによって使用される可能性があります。 ただし、組み込みの DNS クライアントが DNS over TLS のような先進的な DNS 関連プロトコルを使用することで、異なる方法でサーバーにアドレスを指定することが可能です。

このポリシーを有効にしている場合、組み込みの DNS クライアントが利用可能であればそれが使用されます。

このポリシーを無効にしている場合、クライアントは使用されません。

このポリシーを構成していない場合、MacOS では組み込み DNS クライアントが既定で有効になっており、ユーザーは edge://flags を編集するか、コマンドライン フラグを指定することで、組み込み DNS クライアントを使用するかどうかを変更することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: BuiltInDnsClientEnabled
  - GP 名: 組み込みの DNS クライアントを使用する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: BuiltInDnsClientEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: BuiltInDnsClientEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### BuiltinCertificateVerifierEnabled

  #### 組み込みの証明書検証機能を使用してサーバー証明書を検証するかどうかを決定する (非推奨)

  >非推奨: このポリシーは推奨されなくなっています。 現在はサポートされていますが、将来のリリースで廃止されます。
  
  #### サポートされているバージョン:

  - macOS での 83 以降

  #### 説明

  このポリシーは、企業の環境が組み込みの証明書検証ツールとは互換していないことが判明した場合に、環境の更新と問題の報告に時間を割くための短期のメカニズムとしてのみ機能することを目的としているため、推奨されていません。

Mac OS X のレガシ証明書検証機能のサポートの削除が予定されている Microsoft Edge のバージョン 87 では機能しません。


  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  

  #### Mac の情報と設定
  
  - 基本設定キーの名前: BuiltinCertificateVerifierEnabled
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### CertificateTransparencyEnforcementDisabledForCas

  #### subjectPublicKeyInfo ハッシュの一覧に対する証明書の透明性の強制を無効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  subjectPublicKeyInfo ハッシュの一覧に対する証明書の透明性要件の強制を無効にします。

このポリシーでは、指定された subjectPublicKeyInfo ハッシュのいずれかを持つ証明書を含む証明書チェーンに対する証明書の透明性の開示要件を無効にします。 これにより、適切に開示されていなかったために信頼されていなかった証明書を、エンタープライズ ホストでも使用できるようになります。

このポリシーが設定されているときに証明書の透明性の強制を無効にするには、以下のいずれかの条件のセットを満たす必要があります。
1. ハッシュがサーバー証明書の subjectPublicKeyInfo のハッシュである。
2. ハッシュが証明書チェーン内の CA 証明書に含まれている subjectPublicKeyInfo のハッシュであり、その CA 証明書は X.509v3 nameConstraints 拡張を介して制約されており、1 つ以上の directoryName nameConstraints が permittedSubtrees 内に存在し、directoryName には organizationName 属性が含まれている。
3. ハッシュが証明書チェーン内の CA 証明書に含まれている subjectPublicKeyInfo のハッシュであり、CA 証明書の証明書のサブジェクトには 1 つ以上の organizationName 属性があり、サーバーの証明書には同じ数の organizationName 属性が、同じ順序で、バイト単位で同じ値として含まれている。

ハッシュ アルゴリズム名、"/" 文字、DER 形式でエンコードされている指定された証明書の subjectPublicKeyInfo に適用されたハッシュ アルゴリズムの Base64 エンコードを連結して、subjectPublicKeyInfo ハッシュが指定されている。 このBase64 エンコードは、RFC 7469 のセクション 2.4 で定義されている SPKI フィンガープリントと同じ形式です。 認識されないハッシュ アルゴリズムは、無視されます。 現時点でサポートされているハッシュ アルゴリズムは、"sha256" のみです。

このポリシーを無効にしているか、構成していない場合、証明書の透明性を介して公開されている必要がある証明書が、証明書の透明性ポリシーに従って公開されていない場合、信頼されていないものとして扱われます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: CertificateTransparencyEnforcementDisabledForCas
  - GP 名: subjectPublicKeyInfo ハッシュの一覧に対する証明書の透明性の強制を無効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForCas
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForCas\1 = "sha256/AAAAAAAAAAAAAAAAAAAAAA=="
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForCas\2 = "sha256//////////////////////w=="

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: CertificateTransparencyEnforcementDisabledForCas
  - サンプル値:
``` xml
<array>
  <string>sha256/AAAAAAAAAAAAAAAAAAAAAA==</string>
  <string>sha256//////////////////////w==</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### CertificateTransparencyEnforcementDisabledForLegacyCas

  #### レガシ証明機関の一覧に対する証明書の透明性の強制を無効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  レガシ証明機関の一覧 (CAS) に対する証明書の透明性要件の強制を無効にします。

このポリシーでは、指定された subjectPublicKeyInfo ハッシュのいずれかを持つ証明書を含む証明書チェーンに対する証明書の透明性の開示要件を無効にします。 これにより、適切に開示されていなかったために信頼されていなかった証明書を、エンタープライズ ホストでも継続して使用できるようになります。

証明書の透明性の強制を無効にするには、レガシ証明機関 (CA) として認識されている CA 証明書に記載されている subjectPublicKeyInfo にハッシュを設定する必要があります。 レガシ CA とは、Microsoft Edge がサポートする 1 つ以上のオペレーティング システムで、既定で公的に信頼されている CA のことです。

ハッシュ アルゴリズム名、"/" 文字、DER 形式でエンコードされている指定された証明書の subjectPublicKeyInfo に適用されたハッシュ アルゴリズムの Base64 エンコードを連結して、subjectPublicKeyInfo ハッシュを指定します。 このBase64 エンコードは、RFC 7469 のセクション 2.4 で定義されている SPKI フィンガープリントと同じ形式です。 認識されないハッシュ アルゴリズムは、無視されます。 現時点でサポートされているハッシュ アルゴリズムは、"sha256" のみです。

このポリシーを構成していない場合、証明書の透明性を介して公開されている必要がある証明書が、証明書の透明性ポリシーに従って公開されていない場合、信頼されていないものとして扱われます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: CertificateTransparencyEnforcementDisabledForLegacyCas
  - GP 名: レガシ証明機関の一覧に対する証明書の透明性の強制を無効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForLegacyCas
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForLegacyCas\1 = "sha256/AAAAAAAAAAAAAAAAAAAAAA=="
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForLegacyCas\2 = "sha256//////////////////////w=="

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: CertificateTransparencyEnforcementDisabledForLegacyCas
  - サンプル値:
``` xml
<array>
  <string>sha256/AAAAAAAAAAAAAAAAAAAAAA==</string>
  <string>sha256//////////////////////w==</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### CertificateTransparencyEnforcementDisabledForUrls

  #### 特定の URL に対する証明書の透明性の強制を無効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  リストされている URL に対する証明書の透明性要件の強制を無効にします。

このポリシーでは、指定された URL のホスト名のついての証明書を、証明書の透明性を介して開示しないようにします。 これにより、適適切に開示されていなかったために信頼されていなかった証明書を使用することができるようになりますが、これらのホストに対して発行された証明書の誤発行を検出することが難しくなります。

[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) に従って、URL パターンを形成します。 証明書は、スキーム、ポート、パスに関係なく指定されたホスト名に対して有効であるため、URL のホスト名の部分のみが考慮されます。 ワイルドカード ホストはサポートされていません。

このポリシーを構成していない場合、証明書の透明性を介して公開されている必要がある証明書が、公開されていない場合、信頼されていないものとして扱われます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: CertificateTransparencyEnforcementDisabledForUrls
  - GP 名: 特定の URL に対する証明書の透明性の強制を無効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForUrls\1 = "contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForUrls\2 = ".contoso.com"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: CertificateTransparencyEnforcementDisabledForUrls
  - サンプル値:
``` xml
<array>
  <string>contoso.com</string>
  <string>.contoso.com</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ClearBrowsingDataOnExit

  #### Microsoft Edge の終了時に閲覧データをクリアする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 78 以降

  #### 説明

  既定では、Microsoft Edge を終了しても閲覧データはクリアされません。 閲覧データには、フォームに入力された情報やパスワード、閲覧した Web サイトの情報などが含まれます。

このポリシーを有効にしている場合、Microsoft Edge を終了するたびにすべての閲覧データが削除されます。 このポリシーを有効にしている場合、[DefaultCookiesSetting](#defaultcookiessetting) の設定内容よりもこのポリシーが優先されます。

このポリシーを無効にしているか、構成していない場合、ユーザーは [設定] の [閲覧データのクリア] オプションを設定することができます。

このポリシーを有効にしている場合、[AlllowDeletingBrowserHistory](#allowdeletingbrowserhistory) や [ClearCachedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit) ポリシーは設定しないでください。なぜなら、どちらも閲覧データの削除に対応しているからです。 前述のポリシーとこのポリシーを構成している場合、[AlllowDeletingBrowserHistory](#allowdeletingbrowserhistory) や [ClearCachedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit) をどのように構成したかにかかわらず、Microsoft Edge の終了時にはすべての閲覧データが削除されます。

終了時に cookie を削除されないようにするには、 [SaveCookiesOnExit](#savecookiesonexit) ポリシーを構成します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ClearBrowsingDataOnExit
  - GP 名: Microsoft Edge の終了時に閲覧データをクリアする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ClearBrowsingDataOnExit
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ClearBrowsingDataOnExit
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ClearCachedImagesAndFilesOnExit

  #### Microsoft Edge を閉じるときに、キャッシュされた画像とファイルをクリアする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 83 以降

  #### 説明

  既定では、Microsoft Edge を終了してもキャッシュされた画像やファイルはクリアされません。

このポリシーを有効にしている場合、Microsoft Edge を終了するたびにキャッシュされた画像やファイルが削除されます。

このポリシーを無効にしている場合、ユーザーは edge://settings/clearBrowsingDataOnClose で、キャッシュされた画像やファイルのオプションを構成できなくなります。

このポリシーを構成していない場合、ユーザーはキャッシュされた画像とファイルを終了時にクリアするかどうかを選択することができます。

このポリシーを無効にしている場合、[ClearBrowsingDataOnExit](#clearbrowsingdataonexit) ポリシーは有効にしないでください。なぜなら、どちらもデータの削除に対応しているからです。 両方のポリシーを構成している場合、[ClearBrowsingDataOnExit](#clearbrowsingdataonexit) ポリシーが優先され、[ClearCachedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit) ポリシーがどのように構成されているかにかかわらず、Microsoft Edge の終了時にすべてのデータが削除されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ClearCachedImagesAndFilesOnExit
  - GP 名: Microsoft Edge を閉じるときに、キャッシュされた画像とファイルをクリアする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ClearCachedImagesAndFilesOnExit
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ClearCachedImagesAndFilesOnExit
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ClickOnceEnabled

  #### ユーザーが ClickOnce プロトコルを使用してファイルを開けるようにする

  
  
  #### サポートされているバージョン:

  - Windows での 78 以降

  #### 説明

  ユーザーが ClickOnce プロトコルを使用してファイルを開けるようにします。 ClickOnce プロトコルは、ユーザーのコンピューターやデバイス上にある ClickOnce ファイル ハンドラーを使用して、Web サイトが特定の URL からのファイルを開くようブラウザーに要求できるようにします。

このポリシーを構成している場合、ユーザーは ClickOnce プロトコルを使用してファイルを開くことができるようになります。 このポリシーは、edge://flags/ ページでのユーザーによる ClickOnce 設定を上書きします。

このポリシーを無効にしている場合、ユーザーは ClickOnce プロトコルを使用してファイルを開くことができません。 代わりに、ブラウザーを使用してファイル システムへとファイルが保存されます。 このポリシーは、edge://flags/ ページでのユーザーによる ClickOnce 設定を上書きします。

このポリシーを構成していない場合、Microsoft edge 87 以前のバージョンの Microsoft Edge を使用しているユーザーは、既定で ClickOnce プロトコルを使用してファイルを開くことができません。 ただし、ユーザーは edge://flags/ ページで ClickOnce プロトコルの使用を有効にするオプションを設定することができます。 Microsoft Edge バージョン 87 以降を使用しているユーザーは、既定で ClickOnce プロトコルを使用してファイルを開くことができますが、edge://flags/ページで ClickOnce プロトコルを無効にすることができます。

ClickOnce を無効にすると、ClickOnce アプリケーション (.application ファイル) が正常に起動しなくなる場合があります。

ClickOnce の詳細については、「[https://go.microsoft.com/fwlink/?linkid=2103872](https://go.microsoft.com/fwlink/?linkid=2103872)」と「[https://go.microsoft.com/fwlink/?linkid=2099880](https://go.microsoft.com/fwlink/?linkid=2099880)」を参照してください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ClickOnceEnabled
  - GP 名: ユーザーが ClickOnce プロトコルを使用してファイルを開けるようにする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ClickOnceEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### CollectionsServicesAndExportsBlockList

  #### 指定したサービスの一覧へのアクセスをブロックし、コレクション内のターゲットをエクスポートする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  Microsoft Edge のコレクション機能で、ユーザーがアクセスできない特定のサービスとエクスポート ターゲットを一覧表示します。 これには、Bing からの追加データの表示と、Microsoft 製品または外部パートナーへのコレクションのエクスポートが含まれます。

このポリシーを有効にすると、指定したリストと一致するサービスとエクスポート ターゲットがブロックされます。

このポリシーを構成しない場合、使用可能なサービスとエクスポート ターゲットに対する制限は強制されません。

ポリシー オプション マッピング:

* pinterest_suggestions (pinterest_suggestions) = Pinterest の提案

* collections_share (collections_share) = コレクションの共有

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: CollectionsServicesAndExportsBlockList
  - GP 名: 指定したサービスの一覧へのアクセスをブロックし、コレクション内のターゲットをエクスポートする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - Path (必須): SOFTWARE\Policies\Microsoft\Edge\CollectionsServicesAndExportsBlockList
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\CollectionsServicesAndExportsBlockList\1 = "pinterest_suggestions"
SOFTWARE\Policies\Microsoft\Edge\CollectionsServicesAndExportsBlockList\2 = "collections_share"

```

  #### Mac の情報と設定
  
  - プリファレンス キーの名前: CollectionsServicesAndExportsBlockList
  - サンプル値:
``` xml
<array>
  <string>pinterest_suggestions</string>
  <string>collections_share</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### CommandLineFlagSecurityWarningsEnabled

  #### コマンドライン フラグのセキュリティ警告を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 78 以降

  #### 説明

  このポリシーを無効にしている場合、危険性のあるコマンドライン フラグを使用して Microsoft Edge を起動したときに、セキュリティ警告が表示されないようになります。

このポリシーを有効にしているか、未設定の場合、これらのコマンドライン フラグを使用して Microsoft Edge を起動すると、セキュリティ警告が表示されます。

たとえば、--disable-gpu-sandbox フラグを使用すると、このような警告が表示されます: サポートされていないコマンドライン フラグを使用しています: --disable-gpu-sandbox。 これは、安定性とセキュリティ上のリスクをもたらします。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: CommandLineFlagSecurityWarningsEnabled
  - GP 名: コマンドライン フラグのセキュリティ警告を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: CommandLineFlagSecurityWarningsEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: CommandLineFlagSecurityWarningsEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ComponentUpdatesEnabled

  #### Microsoft Edge でのコンポーネントの更新を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーを有効にしているか、構成していない場合、Microsoft Edge でのコンポーネントの更新が有効になります。

このポリシーを無効にしているか、false に設定している場合、Microsoft Edge のすべてのコンポーネントでコンポーネントの更新が無効になります。

ただし、一部のコンポーネントはこのポリシーの対象外となります。 これには、実行可能なコードが含まれておらず、ブラウザーの動作を大幅に変更しない、セキュリティ上重要なコンポーネントが含まれています。 つまり、このポリシーを無効にしても、"セキュリティ上重要" であると判断された更新プログラムは適用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ComponentUpdatesEnabled
  - GP 名: Microsoft Edge でのコンポーネントの更新を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ComponentUpdatesEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ComponentUpdatesEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ConfigureDoNotTrack

  #### トラッキング拒否を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  トラッキング情報を要求する Web サイトにトラッキング拒否要求を送信するかどうかを指定します。 トラッキング拒否要求は、訪問した Web サイトに対し、閲覧アクティビティを追跡されたくないことを知らせます。 既定では、Microsoft Edge はトラッキング拒否要求を送信しませんが、ユーザーがこの要求を送信するためにこの機能をオンにすることができます。

このポリシーを有効にしている場合、トラッキング拒否要求はトラッキング情報を要求する Web サイトに対して常に送信されます。

このポリシーを無効にしている場合、要求は送信されません。

このポリシーを構成していない場合、ユーザーはこれらの要求を送信するかどうかを選択することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ConfigureDoNotTrack
  - GP 名: トラッキング拒否を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ConfigureDoNotTrack
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ConfigureDoNotTrack
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ConfigureFriendlyURLFormat

  #### Microsoft Edge からコピーした URLの既定の貼り付け書式を構成し、他の形式をユーザーが利用できるようにするかどうかを決定する

  
  
  #### サポートされているバージョン:

  - Windows での 87 以降
  - macOS での 88 以降

  #### 説明

  FriendlyURL が有効になっている場合、Microsoft Edge は URL の追加の表現を計算し、クリップボードに配置します。

このポリシーは、ユーザーが外部アプリケーションに貼り付けるとき、または [名前を付けて貼り付け] コンテキストメニュー項目なしで Microsoft Edge 内に貼り付けるときに貼り付ける形式を構成します。

構成済みの場合、このポリシーはユーザーに代わって選択を行います。 edge://settings/shareCopyPaste のオプションはグレー表示され、[名前を付けて貼り付け]コンテキストメニューのオプションは使用できなくなります。

* 未構成 = ユーザーは好みの貼り付け形式を選択できます。 デフォルトでは、これはフレンドリ URL 形式に設定されています。 [名前を付けて貼り付け] メニューは、Microsoft Edge で使用できるようになります。

* 1 = 追加のフォーマットはクリップボードに保存されません。 Microsoft Edge には [名前を付けて貼り付け] コンテキストメニュー項目はなく、貼り付けることができる形式はプレーンテキストの URL 形式のみです。 事実上、フレンドリ URL 機能は無効になります。

* 3 = ユーザーは、リッチテキストを受け入れるサーフェスに貼り付けるたびにフレンドリ URL を取得します。 プレーン URL は、リッチでないサーフェスでも引き続き使用できます。 Microsoft Edge には [名前を付けて貼り付け] メニューはありません。

* 4 = (現在は使用されていません)

一部の貼り付け先や Web サイトでは、より豊富な形式が十分にサポートされていない場合があります。 そのため、このポリシーを構成する場合は、プレーン URL オプションをお勧めします。

ポリシー オプション マッピング:

* PlainText (1) = ページのタイトルなどの追加情報を含まないプレーンURL。 これは、このポリシーが構成されている場合に推奨されるオプションです。 詳細については、説明を参照してください。

* TitledHyperlink (3) = Titled Hyperlink: コピーされた URL を指すハイパーリンクですが、表示されるテキストはリンク先ページのタイトルです。 これは、フレンドリ URL 形式です。

* WebPreview (4) = まもなく使用可能になります。 設定されている場合、'Plain URL' と同じように動作します。

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ConfigureFriendlyURLFormat
  - GP 名: Microsoft Edge からコピーした URLの既定の貼り付け書式を構成し、他の形式をユーザーが利用できるようにするかどうかを決定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - GP 固有の名前: ConfigureFriendlyURLFormat
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000003
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ConfigureFriendlyURLFormat
  - サンプル値:
``` xml
<integer>3</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ConfigureOnPremisesAccountAutoSignIn

  #### Azure AD ドメイン アカウントがない場合、Active Directory ドメイン アカウントで自動サインインを構成する

  
  
  #### サポートされているバージョン:

  - Windows での 81 以降

  #### 説明

  ユーザーのコンピューターがドメインに参加していて、環境がハイブリッド参加していない場合、Active Directory アカウントを自動サインインに使用できるようにします。 代わりにユーザーが Azure Active Directory アカウントを使用して自動的にサインインできるようにする場合は、Azure AD 参加 (詳細については [https://go.microsoft.com/fwlink/?linkid=2118197](https://go.microsoft.com/fwlink/?linkid=2118197) を参照してください) またはハイブリッド参加 (詳細については [https://go.microsoft.com/fwlink/?linkid=2118365](https://go.microsoft.com/fwlink/?linkid=2118365) を参照してください) を使用して環境を参加させます。

起動させるたびに、実行された最初のプロファイルがサインインしていないか、または以前に自動サインインが行われていない限り、Microsoft Edge はこのポリシーを使用してサインインを試みようとします。

[BrowserSignin](#browsersignin) ポリシーを無効として構成している場合、このポリシーは有効になりません。

このポリシーを有効にし、"SignInAndMakeDomainAccountNonRemovable" に設定している場合、Microsoft Edge は、ドメインに参加しているコンピューターにいるユーザーを Active Directory アカウントを使用して自動的にサインインさせます。

このポリシーを "無効" に設定しているか、設定していない場合、Microsoft Edge は、Active Directory アカウントを持ちドメインに参加しているコンピューター上のユーザーを自動的にサインインさせません。

Microsoft Edge 89 以降、同期が無効になっている既存のオンプレミスのプロファイルが存在し、コンピューターがハイブリッドに参加している場合の例 Azure AD アカウントを所有する場合は、オンプレミスのプロファイルを Azure AD プロファイルに自動アップグレードして、Azure AD 同期機能を完全に取得します。

ポリシー オプション マッピング:

* Disabled (0) = 無効

* SignInAndMakeDomainAccountNonRemovable (1) = サインインして、ドメインアカウントを削除できないようにする

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ConfigureOnPremisesAccountAutoSignIn
  - GP 名: Azure AD ドメイン アカウントがない場合、Active Directory ドメイン アカウントで自動サインインを構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ConfigureOnPremisesAccountAutoSignIn
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### ConfigureOnlineTextToSpeech

  #### オンラインでの音声合成を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ブラウザーが Azure Cognitive Services の一部であるオンラインでの音声合成の音声フォントを活用できるかどうかを設定します。 これらの音声フォントは、プレインストールされているシステムの音声フォントよりも高品質です。

このポリシーを有効にしているか、構成していない場合、SpeechSynthesis API を使用する Web ベースのアプリケーションは、オンラインでの音声合成の音声フォントを使用することができます。

このポリシーを無効にしている場合、音声フォントは利用できません。

この機能の詳細については、以下を参照してください。SpeechSynthesis API: [https://go.microsoft.com/fwlink/?linkid=2110038](https://go.microsoft.com/fwlink/?linkid=2110038) Cognitive Services: [https://go.microsoft.com/fwlink/?linkid=2110141](https://go.microsoft.com/fwlink/?linkid=2110141)

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ConfigureOnlineTextToSpeech
  - GP 名: オンラインでの音声合成を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ConfigureOnlineTextToSpeech
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ConfigureOnlineTextToSpeech
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ConfigureShare

  #### 共有エクスペリエンスを構成する

  
  
  #### サポートされているバージョン:

  - Windows での 83 以降

  #### 説明

  このポリシーを "ShareAllowed" (既定値) に設定している場合、ユーザーは Microsoft Edge の [設定] と [その他] メニューから Windows 10 の共有エクスペリエンスにアクセスして、システム上の別のアプリと共有することができるようになります。

このポリシーを "ShareDisallowed" に設定している場合、ユーザーは Windows 10 の共有エクスペリエンスにアクセスすることができなくなります。 [共有] ボタンがツール バーにある場合には、それも非表示になります。

ポリシー オプション マッピング:

* ShareAllowed (0) = 共有エクスペリエンスの使用を許可する

* ShareDisallowed (1) = 共有エクスペリエンスの使用を許可しない

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ConfigureShare
  - GP 名: 共有エクスペリエンスを構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ConfigureShare
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### CustomHelpLink

  #### カスタム ヘルプリンクを指定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 79 以降

  #### 説明

  [ヘルプ] メニューや F1 キーのリンクを指定します。

このポリシーを有効にしている場合、管理者は [ヘルプ] メニューや F1 キーのリンクを指定することができます。

このポリシーを無効にしているか、構成していない場合、[ヘルプ] メニューや F1 キーの既定のリンクが使用されます。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: CustomHelpLink
  - GP 名: カスタム ヘルプリンクを指定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: CustomHelpLink
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"https://go.microsoft.com/fwlink/?linkid=2080734"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: CustomHelpLink
  - サンプル値:
``` xml
<string>https://go.microsoft.com/fwlink/?linkid=2080734</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DNSInterceptionChecksEnabled

  #### DNS の傍受チェックを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 80 以降

  #### 説明

  このポリシーでは、DNS の傍受チェックを無効にするために使用するローカル スイッチを構成します。 これらのチェックは、ブラウザーが不明なホスト名をリダイレクトするプロキシを介しているかどうかを検出します。

ネットワーク構成がわかっているエンタープライズ環境では、この検出が必要ない可能性があります。 これを無効にすると、起動時や DNS 構成の変更のたびに発生する追加の DNS と HTTP トラフィックを回避することができます。

このポリシーを有効にしているか、設定していない場合、DNS の傍受チェックが実行されます。

このポリシーを無効にしている場合、DNS の傍受チェックは実行されません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DNSInterceptionChecksEnabled
  - GP 名: DNS の傍受チェックを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DNSInterceptionChecksEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DNSInterceptionChecksEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultBrowserSettingEnabled

  #### Microsoft Edge を既定のブラウザーとして設定する

  
  
  #### サポートされているバージョン:

  - Windows 7 と macOS での 77 以降

  #### 説明

  このポリシーを True に設定すると、Microsoft Edge は起動時に既定のブラウザーであるかどうかを常にチェックし、可能であれば自動的に登録します。

このポリシーを False に設定すると、Microsoft Edge はそれが既定であるかどうかの確認を停止し、このオプションのユーザー コントロールをオフにします。

このポリシーを設定しない場合、Microsoft Edge により、ユーザーはそれが既定かどうかを制御でき、既定でない場合はユーザー通知を表示するかどうかを制御できます。

Windows 管理者への注意: このポリシーは、Windows 7 を実行している PC でのみ機能します。 Windows のそれ以降のバージョンでは、Microsoft Edge を HTTPS と HTTP プロトコル (または、オプションで FTP プロトコルや .html、.htm、.pdf、.svg、.webp などのファイル形式) のハンドラーにする "既定のアプリケーションの関連付け" ファイルを展開する必要があります。 詳細については、「[https://go.microsoft.com/fwlink/?linkid=2094932](https://go.microsoft.com/fwlink/?linkid=2094932)」を参照してください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultBrowserSettingEnabled
  - GP 名: Microsoft Edge を既定のブラウザーとして設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultBrowserSettingEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultBrowserSettingEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultSearchProviderContextMenuAccessAllowed

  #### 既定の検索プロバイダーのコンテキスト メニューへのアクセスを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 85 以降

  #### 説明

  コンテキストメニューで、既定の検索プロバイダーの使用を有効にします。

このポリシーを無効に設定すると、既定の検索プロバイダーとサイド バー検索に依存している検索コンテキスト メニュー項目は利用できなくなります。

このポリシーが有効または設定されていない場合、既定の検索プロバイダーとサイド バー検索のコンテキスト メニュー項目が使用可能になります。

ポリシー値は、[DefaultSearchProviderEnabled](#defaultsearchproviderenabled) ポリシーが有効になっている場合にのみ適用され、それ以外の場合は適用されません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultSearchProviderContextMenuAccessAllowed
  - GP 名: 既定の検索プロバイダー コンテキスト メニューの検索アクセスを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultSearchProviderContextMenuAccessAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - プリファレンス キー名: DefaultSearchProviderContextMenuAccessAllowed
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultSensorsSetting

  #### 既定のセンサーの設定

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  Web サイトが動画センサーや光センサーなどのセンサーにアクセスして使用できるかどうかを設定します。 Web サイトがセンサーにアクセスするのを阻止することも、許可することもできます。

ポリシーを1に設定すると、web サイトがセンサーにアクセスして使用できるようになります。 ポリシーを2に設定すると、センサーへのアクセスが拒否されます。

[SensorsAllowedForUrls](#sensorsallowedforurls)および[SensorsBlockedForUrls](#sensorsblockedforurls)ポリシーを使用して、 特定の URL パターンに対するこのポリシーを上書きできます。

このポリシーを構成していない場合、web サイトはセンサーにアクセスして使用することができますが、ユーザーはこの設定を変更できます。 これは、 [SensorsAllowedForUrls](#sensorsallowedforurls)および [SensorsBlockedForUrls](#sensorsblockedforurls)のグローバル既定値です。

ポリシー オプション マッピング:

* AllowSensors (1) = サイトがセンサーにアクセスできるようにする

* BlockSensors (2) = センサーへのアクセスを許可しない

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultSensorsSetting
  - GP 名: 既定のセンサーの設定
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultSensorsSetting
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 優先キー名: DefaultSensorsSetting
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DefaultSerialGuardSetting

  #### シリアル API の使用を制御する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  Web サイトがシリアルポートにアクセスできるかどうかを設定します。 アクセスを完全にブロックするか、Web サイトがシリアルポートにアクセスするときに毎回ユーザーに確認を求めるように設定することができます。

ポリシーを3に設定すると、web サイトがシリアルポートへのアクセス許可を要求します。 ポリシーを2に設定すると、シリアルポートへのアクセスが拒否されます。

特定の URL パターンに対するこのポリシーは、[WebUsbAskForUrls](#serialaskforurls) と [WebUsbBlockedForUrls](#serialblockedforurls) ポリシーを使用して、上書きすることができます。

このポリシーを構成していない場合、既定でウェブサイトはシリアルポート にアクセス可能かどうかをユーザーに確認することができ、ユーザーはこの設定を変更することができます。

ポリシー オプション マッピング:

* BlockSerial (2) =いかなるサイトも シリアル API を経由してシリアルポートへのアクセスを要求することはできません。

* AskSerial (3) = ユーザーがシリアルポートにアクセスするためのアクセス許可をユーザーに要求できるようにします。

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DefaultSerialGuardSetting
  - GP 名: Serial APIの使用を制御する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DefaultSerialGuardSetting
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DefaultWebUsbGuardSetting
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DelayNavigationsForInitialSiteListDownload

  #### タブ ナビゲーションの前にエンタープライズ モード サイト一覧が使用できるようにする

  
  
  #### サポートされているバージョン:

  - Windows での 84 以降

  #### 説明

  ブラウザーが最初のエンタープライズ モード サイト一覧をダウンロードするまで、Microsoft Edge タブがナビケートを待機するかどうかを指定できます。 この設定は、ブラウザーのホームページを Internet Explorer モードで読み込む必要があるシナリオを対象としています。 IE モードが有効にされた後、最初にブラウザーを実行することが重要です。 このシナリオが存在しない場合は、ホームページの読み込みのパフォーマンスに悪影響を及ぼす可能性があるため、この設定を有効にしないことをお勧めします。 この設定は、IE モードが有効にされた後に最初に実行されるブラウザなど、Microsoft Edge にキャッシュされたエンタープライズ モード サイト一覧がない場合にのみ適用されます。

この設定は、"IEMode" に設定されている [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) と、一覧に少なくとも 1 つのエントリがある [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist) ポリシーと連動します。

このポリシーのタイムアウト動作は、[NavigationDelayForInitialSiteListDownloadTimeout](#navigationdelayforinitialsitelistdownloadtimeout) ポリシーで構成できます。

このポリシーを [All] に設定すると、Microsoft Edge にエンタープライズ モード サイト一覧のキャッシュ バージョンがない場合、ブラウザーがサイト リストをダウンロードするまで、タブのナビゲートが遅延します。 サイト リストによって Internet Explorer モードで開くように構成されているサイトは、ブラウザーの最初のナビゲーション中であっても、Internet Explorer モードで読み込まれます。 http:、https:、file:、ftp: 以外のスキームを持つサイトなど、Internet Explorer で開くように構成できない可能性のあるサイトは、ナビゲートを遅らせず、Edge モードですぐに読み込みます。

このポリシーを [None] に設定した場合、または構成しない場合、Microsoft Edge にエンタープライズ モード サイト一覧のキャッシュ バージョンがないときには、タブはすぐにナビゲートし、ブラウザーがエンタープライズ モード サイト一覧をダウンロードするのを待ちません。 サイト リストによって Internet Explorer モードで開くように構成されているサイトは、ブラウザーがエンタープライズ モード サイト一覧のダウンロードを完了するまで Microsoft Edge モードで開きます。

ポリシー オプション マッピング:

* None (0) = None

* All (1) = 対象のすべてのナビゲーション

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DelayNavigationsForInitialSiteListDownload
  - GP 名: タブ ナビゲーションの前にエンタープライズ モード サイト一覧が使用できるようにする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DelayNavigationsForInitialSiteListDownload
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### DeleteDataOnMigration

  #### 移行時に古いブラウザー データを削除する

  
  
  #### サポートされているバージョン:

  - Windows での 83 以降

  #### 説明

  このポリシーは、Microsoft Edge のバージョン 81 以降に移行した後に Microsoft Edge 従来版からのユーザーの閲覧データを削除するかどうかを決定します。

このポリシーを "有効" に設定している場合、Microsoft Edge のバージョン 81 以降に移行した後の Microsoft Edge 従来版からの閲覧データは、すべて削除されます。 このポリシーは既存の閲覧データに影響を与えるため、Microsoft Edge のバージョン 81 以降に移行する前に設定しておく必要があります。

このポリシーを "無効" に設定しているか、構成されていない場合、Microsoft Edge のバージョン 83 以降に移行しても、ユーザーの閲覧データは削除されません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DeleteDataOnMigration
  - GP 名: 移行時に古いブラウザー データを削除する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DeleteDataOnMigration
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### DeveloperToolsAvailability

  #### 開発者ツールの使用を制御する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  開発者ツールの使用を制御します。

このポリシーを "DeveloperToolsDisalllowedForForceInstalledExtensions" (既定値) に設定している場合、ユーザーは開発者ツールや JavaScript コンソール全般にアクセスできますが、エンタープライズ ポリシーによってインストールされた拡張機能のコンテキストにはアクセスできません。

このポリシーを "DeveloperToolsAllowed" に設定している場合、ユーザーはエンタープライズ ポリシーによってインストールされた拡張機能を含め、すべてのコンテキストで開発者ツールや JavaScript コンソールにアクセスできるようになります。

このポリシーを "DeveloperToolsDisallowed" に設定している場合、ユーザーが開発者ツールにアクセスしたり、Webサイトの要素を検査したりすることができなくなります。 開発者ツールや JavaScript コンソールを開くキーボード ショートカット、メニュー、コンテキスト メニュー項目は無効になっています。

ポリシー オプション マッピング:

* DeveloperToolsDisallowedForForceInstalledExtensions (0) = エンタープライズ ポリシーによってインストールされた拡張機能の開発者ツールをブロックし、その他のコンテキストで許可する

* DeveloperToolsAllowed (1) = 開発者ツールの使用を許可する

* DeveloperToolsDisallowed (2) = 開発者ツールの使用を許可しない

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DeveloperToolsAvailability
  - GP 名: 開発者ツールの使用を制御する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DeveloperToolsAvailability
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DeveloperToolsAvailability
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DiagnosticData

  #### ブラウザーの使用状況に関する必須およびオプションの診断データを送信する

  
  
  #### サポートされているバージョン:

  - Windows 7 と macOS での 86 以降

  #### 説明

  このポリシーでは、ブラウザーの使用に関する必須およびオプションの診断データを Microsoft に送信します。

必須診断データが収集されることで Microsoft Edge のセキュリティを維持し、常に最新の状態で動作することが期待できます。

オプションの診断データには、製品およびサービスの改善のためにブラウザーの使用状況に関するデータ、アクセスした Web サイト、Microsoft へのクラッシュ レポートが含まれます。

このポリシーは、Windows 10 デバイスではサポートされていません。 Windows 10 でこのデータの収集を制御するには、IT 管理者が Windows 診断データ グループ ポリシーを使用する必要があります。 このポリシーは、使用している Windows のバージョンに応じて、「利用統計情報を許可する」か、「診断データを許可する」かを決定します。 収集されるすべての Windows 10 診断データについて、以下のとおり説明します。[https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)

このポリシーを構成するには、次のいずれかの設定を使用します。

'オフ' にすると、必須およびオプションの診断データの収集をオフにします。 このオプションは推奨されません。

'RequiredData' は、必須診断データを送信しますが、オプションの診断データの収集をオフにします。 Microsoft Edge では、セキュリティが最新の状態に維持され、期待どおりに動作するために、診断診断データが送信されます。

'OptionalData' は、ブラウザーの使用状況に関するデータ、アクセスされた Web サイト、製品およびサービスの改善のために Microsoft に送信されたクラッシュ レポートを含むオプションの診断データを送信します。

Windows 7 または macOS のこのポリシーでは、必須およびオプションの診断データを Microsoft に送信します。

このポリシーを構成しなかった場合、または無効にした場合は、Microsoft Edge は既定でユーザーの設定に従います。

ポリシー オプション マッピング:

* オフ (0) = オフ (非推奨)

* RequiredData (1) = 必須データ

* OptionalData (2) = オプションのデータ

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DiagnosticData
  - GP 名: ブラウザーの使用状況に関する必須およびオプションの診断データを送信する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DiagnosticData
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 優先順位キー名: DiagnosticData
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DirectInvokeEnabled

  #### ユーザーが DirectInvoke プロトコルを使用してファイルを開けるようにする

  
  
  #### サポートされているバージョン:

  - Windows での 78 以降

  #### 説明

  ユーザーが DirectInvoke プロトコルを使用してファイルを開けるようにします。 DirectInvoke プロトコルは、ユーザーのコンピューターやデバイス上にある特定のファイル ハンドラーを使用して、Web サイトが特定の URL からのファイルを開くようブラウザーに要求できるようにします。

このポリシーを有効にしているか、構成していない場合、ユーザーは DirectInvoke プロトコルを使用してファイルを開くことができます。

このポリシーを構成していない場合、ユーザーは DirectInvoke プロトコルを使用してファイルを開くことができません。 代わりに、ファイル システムにファイルが保存されます。

注: DirectInvoke を無効にすると、Microsoft SharePoint Online の一部の機能が期待通りに動作しない場合があります。

DirectInvoke の詳細については、「[https://go.microsoft.com/fwlink/?linkid=2103872](https://go.microsoft.com/fwlink/?linkid=2103872)」と「[https://go.microsoft.com/fwlink/?linkid=2099871](https://go.microsoft.com/fwlink/?linkid=2099871)」を参照してください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DirectInvokeEnabled
  - GP 名: ユーザーが DirectInvoke プロトコルを使用してファイルを開けるようにする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DirectInvokeEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### Disable3DAPIs

  #### 3D グラフィック API のサポートを無効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Web ページがグラフィックス処理装置 (GPU) にアクセスできないようにします。 具体的には、Web ページは WebGL API にアクセスできず、プラグインは Pepper 3D API を使用することができません。

このポリシーを設定していないか、無効にしている場合、Web ページが WebGL API を使用したり、プラグインが Pepper 3D API を使用したりすることができるようになる可能性があります。 既定では、Microsoft Edge にはこれらの API を使用するためにコマンドライン引数を渡す必要がある可能性があります。

[HardwareAccelerationModeEnabled](#hardwareaccelerationmodeenabled) ポリシーが false に設定されている場合、"Disable3DAPIs" ポリシーの設定は無視されます。これは、"Disable3DAPIs" ポリシーを true に設定した場合と同じです。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: Disable3DAPIs
  - GP 名: 3D グラフィック API のサポートを無効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: Disable3DAPIs
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: Disable3DAPIs
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DisableScreenshots

  #### スクリーンショットの撮影を無効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ユーザーがブラウザー ページのスクリーンショットを撮影できるかどうかを制御します。

有効にしている場合、キーボード ショートカットや拡張 API を使用してスクリーンショットを撮影することができなくなります。

このポリシーを無効にしているか、構成していない場合、ユーザーはスクリーンショットを撮影することができます。

このポリシーは、ブラウザー内で撮影されたスクリーンショットを制御します。 このポリシーを有効にしていても、ユーザーはブラウザー以外の方法 (オペレーティング システムの機能や、別のアプリケーションを使用するなど) でスクリーンショットを撮影することができる可能性があります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DisableScreenshots
  - GP 名: スクリーンショットの撮影を無効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DisableScreenshots
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DisableScreenshots
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DiskCacheDir

  #### ディスク キャッシュ ディレクトリを設定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  キャッシュされたファイルの保存に使用するディレクトリを構成します。

このポリシーを有効にしている場合、ユーザーが "--disk-cache-dir" フラグを指定したかどうかにかかわらず、Microsoft Edge は指定されたディレクトリを使用します。 データの損失や予期しないエラーを避けるために、ボリュームのルート ディレクトリや別の目的で使用されているディレクトリには、このポリシーを構成しないでください。なぜなら、Microsoft Edge がコンテンツを管理しているからです。

ディレクトリやパスを指定するときに使用できる変数の一覧については、「[https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041)」を参照してください。

このポリシーを構成していない場合、既定のキャッシュ ディレクトリが使用され、ユーザーは "--disk-cache-dir" コマンドライン フラグを使用して既定値を上書きすることができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DiskCacheDir
  - GP 名: ディスク キャッシュ ディレクトリを設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DiskCacheDir
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"${user_home}/Edge_cache"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DiskCacheDir
  - サンプル値:
``` xml
<string>${user_home}/Edge_cache</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DiskCacheSize

  #### ディスク キャッシュ サイズをバイトに設定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ディスク上のファイルを保存するために使用するキャッシュ サイズをバイト単位で構成します。

このポリシーを有効にしている場合、ユーザーが "--disk-cache-size" フラグを指定したかどうかにかかわらず、Microsoft Edge は指定されたキャッシュ サイズを使用します。 このポリシーで指定された値は厳格な境界線ではなく、むしろキャッシュ システムへの提案です。数メガバイト以下の値は小さすぎるため、妥当な最小値へと切り上げられます。

このポリシーの値を 0 に設定している場合、既定のキャッシュ サイズが使用され、ユーザーがこれを変更することはできません。

このポリシーを構成していない場合、既定のサイズが使用されますが、ユーザーは "--disk-cache-size" フラグを使用してそれを上書きすることができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DiskCacheSize
  - GP 名: ディスク キャッシュ サイズをバイトに設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DiskCacheSize
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x06400000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DiskCacheSize
  - サンプル値:
``` xml
<integer>104857600</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DnsOverHttpsMode

  #### DNS over HTTPS モードを制御する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 83 以降

  #### 説明

  GP 名: DNS over HTTPS リゾルバーのモードを制御します。 このポリシーは、各クエリの既定のモードのみを設定します。 このモードは、DNS over HTTPS サーバーのホスト名を解決するための要求などの特殊な種類のクエリのために上書きすることができます。

"オフ" モードでは、DNS over HTTPS は無効になります。

"自動" モードでは、DNS over HTTPS サーバーが利用可能な場合、最初に DNS over HTTPS クエリを送信し、エラー時には安全でないクエリの送信へとフォールバックする場合があります。

"保護" モードでは、DNS over HTTPS クエリのみを送信し、エラー時には解決に失敗します。

このポリシーを構成していない場合、ブラウザーは、ユーザーの構成済みシステム リゾルバーに関連付けられたリゾルバーに DNS over HTTPS 要求を送信する可能性があります。

ポリシー オプション マッピング:

* オフ (オフ) = DNS over HTTPS を無効にする

* 自動 (自動) = 安全でないフォールバックで DNS-over-HTTPS を有効にする

* 安全 (安全) = 安全でないフォールバックなしで DNS-over-HTTPS を有効にする

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DnsOverHttpsMode
  - GP 名: DNS over HTTPS モードを制御する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DnsOverHttpsMode
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"off"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DnsOverHttpsMode
  - サンプル値:
``` xml
<string>off</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DnsOverHttpsTemplates

  #### 目的の DNS over HTTPS リゾルバーの URI テンプレートを指定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 83 以降

  #### 説明

  目的の DNS over HTTPS リゾルバーの URI テンプレートです。 複数の DNS over HTTPS リゾルバーを指定するには、対応する URI テンプレートをスペースで区切ります。

[DnsOverHttpsMode](#dnsoverhttpsmode) を "保護" に設定している場合、このポリシーを設定する必要があり、空にすることはできません。

[DnsOverHttpsMode](#dnsoverhttpsmode) を "自動" に設定し、このポリシーが設定されている場合、指定された URI テンプレートが使用されます。 このポリシーを設定していない場合、ハードコードされたマッピングを使用して、ユーザーの現在の DNS リゾルバーを同じプロバイダーが運用している DoH リゾルバーへとアップグレードしようとします。

URI テンプレートが dns 変数を含んでいる場合、リゾルバーへの要求は GET を使用します。それ以外の場合には、要求は POST を使用します。

適切に書式設定されていないテンプレートは、無視されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DnsOverHttpsTemplates
  - GP 名: 目的の DNS over HTTPS リゾルバーの URI テンプレートを指定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: DnsOverHttpsTemplates
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"https://dns.example.net/dns-query{?dns}"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DnsOverHttpsTemplates
  - サンプル値:
``` xml
<string>https://dns.example.net/dns-query{?dns}</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DownloadDirectory

  #### ダウンロード ディレクトリを設定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ファイルをダウンロードするときに使用するディレクトリを構成します。

このポリシーを有効にしている場合、ユーザーがディレクトリを指定したか、ダウンロード先の確認を求めるメッセージを毎回表示するように選択したかどうかにかかわらず、Microsoft Edge は指定されたディレクトリを使用します。 使用できる変数の一覧については、「[https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041)」を参照してください。

このポリシーを無効にしているか、構成していない場合、既定のダウンロード ディレクトリが使用され、ユーザーはそれを変更することができます。

無効なパスを設定すると、Microsoft Edge はユーザーの既定のダウンロード ディレクトリを既定値として設定します。

パスで指定されているフォルダーが存在しない場合、ダウンロードは保存場所を確認するメッセージをトリガーします。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DownloadDirectory
  - GP 名: ダウンロード ディレクトリを設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: DownloadDirectory
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"\n      Linux-based OSes (including Mac): /home/${user_name}/Downloads\n      Windows: C:\\Users\\${user_name}\\Downloads"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DownloadDirectory
  - サンプル値:
``` xml
<string>
      Linux-based OSes (including Mac): /home/${user_name}/Downloads
      Windows: C:\Users\${user_name}\Downloads</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### DownloadRestrictions

  #### ダウンロードの制限を許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ユーザーにセキュリティの決定を上書きさせずに、Microsoft Edge が完全にブロックするダウンロードの種類を構成します。

"BlockDangerousDownloads" を設定すると、Microsoft Defender SmartScreen の警告を表示するものを除くすべてのダウンロードが許可されます。

"BlockPotentiallyDangerousDownloads" を設定すると、危険性のあるまたは不要なダウンロードに関する Microsoft Defender SmartScreen の警告を表示するものを除くすべてのダウンロードが許可されます。

"BlockAllDownloads" を設定すると、すべてのダウンロードがブロックされます。

このポリシーを構成していない場合、または "DefaultDownloadSecurity" オプションを設定している場合、ダウンロードは Microsoft Defender SmartScreen の分析結果に基づく通常のセキュリティ制限を通過します。

これらの制限は、Web ページのコンテンツからのダウンロードや、[ダウンロード リンク] コンテキスト メニュー オプションにも適用されます。 これらの制限は、現在表示されているページの保存やダウンロードには適用されず、印刷オプションの [PDF として保存] オプションにも適用されません。

Microsoft Defender SmartScreen の詳細については、「[https://go.microsoft.com/fwlink/?linkid=2094934](https://go.microsoft.com/fwlink/?linkid=2094934)」を参照してください。

ポリシー オプション マッピング:

* DefaultDownloadSecurity (0) = 特別な制限はありません

* BlockDangerousDownloads (1) = 危険なダウンロードをブロックする

* BlockPotentiallyDangerousDownloads (2) = 危険な可能性があるダウンロードまたは不要なダウンロードをブロックする

* BlockAllDownloads (3) = すべてのダウンロードをブロックする

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: DownloadRestrictions
  - GP 名: ダウンロードの制限を許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: DownloadRestrictions
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: DownloadRestrictions
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### EdgeCollectionsEnabled

  #### コレクション機能を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 78 以降

  #### 説明

  ユーザーがコレクション機能にアクセスできるようにすることで、コンテンツの収集、整理、共有、エクスポートをより効率的に行うことができ、Office との統合も可能になります。

このポリシーを有効にしているか、構成していない場合、ユーザーは Microsoft Edge のコレクション機能にアクセスして使用することができます。

このポリシーを無効にしている場合、ユーザーが Microsoft Edge のコレクションにアクセスして使用することはできません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: EdgeCollectionsEnabled
  - GP 名: コレクション機能を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: EdgeCollectionsEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: EdgeCollectionsEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### EdgeShoppingAssistantEnabled

  #### Microsoft Edge でのショッピングを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 87 以降

  #### 説明

  このポリシーにより、ユーザーは閲覧中の商品の価格を比較したり、アクセスしている Web サイトからクーポンを取得したり、チェックアウト時にクーポンを自動適用したりできます。

このポリシーを有効にするか、構成しない場合、価格比較やクーポンなどのショッピング機能がリテール ドメインに自動的に適用されます。 現在の小売業者のクーポンと他の小売業者からの価格はサーバーから取得されます。

このポリシーを無効にすると、リテール ドメインで価格比較やクーポンなどのショッピング機能が自動的に検出されなくなります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: EdgeShoppingAssistantEnabled
  - GP 名: Microsoft Edge でのショッピングを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: EdgeShoppingAssistantEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: EdgeShoppingAssistantEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### EditFavoritesEnabled

  #### ユーザーがお気に入りを編集できるようにする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーを有効にしている場合、ユーザーはお気に入りを追加、削除、変更することができるようになります。 これは、このポリシーを構成していない場合の既定動作です。

このポリシーを無効にしている場合、ユーザーはお気に入りを追加、削除、変更することができません。 ユーザーは既存のお気に入りをそのまま使用することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: EditFavoritesEnabled
  - GP 名: ユーザーがお気に入りを編集できるようにする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: EditFavoritesEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: EditFavoritesEnabled
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### EnableDeprecatedWebPlatformFeatures

  #### (使われていない) 限られた期間のみ使用できます。

  
  >不使用: このポリシーは廃止されており、Microsoft Edge 86 以降は機能しません。
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降、86 まで

  #### 説明

  このポリシーは、個々の web プラットフォームの deprecations の管理に専用の web プラットフォームポリシーが使用されるようになりました。これは時代遅れです。

一時的にもう一度有効にする非推奨の Web プラットフォーム機能の一覧を指定します。

このポリシーでは、一定期間の間、非推奨の Web プラットフォーム機能を再び有効にすることができます。 機能は、文字列タグで識別されます。

このポリシーを構成していない、一覧が空である、サポートされている文字列タグのいずれかに機能が一致しない場合、非推奨の Web プラットフォーム機能はすべて無効のままになります。

ポリシー自体は上記のプラットフォームでサポートされていますが、このポリシーが有効化する機能については、これらのプラットフォームすべてで利用できるわけではない可能性があります。 すべての非推奨の Web プラットフォーム機能を再び有効にすることができるわけではありません。 以下に明示的に記載されているもののみを再び有効にすることができ、機能ごとに異なる限られた期間のみ有効にすることができます。 Web プラットフォーム機能の変更の背景については、「https://bit.ly/blinkintents」で確認することができます。

文字列タグの一般的な形式は、[DeprecatedFeatureName]_EffectiveUntil[yyyymmdd] です。

ポリシー オプション マッピング:

* ExampleDeprecatedFeature (ExampleDeprecatedFeature_EffectiveUntil20080902) = 2008/09/02 まで ExampleDeprecatedFeature API を有効にする

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: EnableDeprecatedWebPlatformFeatures
  - GP 名: 一定期間の間、非推奨の Web プラットフォーム機能を再び有効にする (不使用)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\EnableDeprecatedWebPlatformFeatures
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\EnableDeprecatedWebPlatformFeatures\1 = "ExampleDeprecatedFeature_EffectiveUntil20080902"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: EnableDeprecatedWebPlatformFeatures
  - サンプル値:
``` xml
<array>
  <string>ExampleDeprecatedFeature_EffectiveUntil20080902</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### EnableDomainActionsDownload

  #### Microsoft からのドメイン アクションのダウンロードを有効にする (不使用)

  
  >不使用: このポリシーは廃止されており、Microsoft Edge 84 以降は機能しません。
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降、84 まで

  #### 説明

  このポリシーは、矛盾した状態を回避するため、機能しません。 このポリシーは、ドメイン アクション一覧のダウンロードの有効化または無効化に使用されましたが、常に目的の状態になるとは限りませんでした。 ダウンロードを処理する Experimentation and Configuration Service では、サービスからダウンロードするものを独自のポリシーで設定しています。 代わりに、[ExperimentationAndConfigurationServiceControl](#experimentationandconfigurationservicecontrol) ポリシーを使用します。

Microsoft Edge では、ドメイン アクションはブラウザーが Web 上で正常に動作するための一連の互換性機能を表しています。

Microsoft は、互換性の理由から特定のドメインで選択するアクションの一覧を保持しています。 たとえば、Microsoft Edge の新しいユーザー エージェント文字列によって Web サイトが壊れている場合、ブラウザーがその Web サイトのユーザー エージェント文字列を上書きする場合があります。 これらのアクションは、Microsoft がサイトの所有者との間で問題を解決しようとする間、一時的に行われることを意図しています。

ブラウザーが起動した後、ブラウザーは定期的に実行すべき最新の互換性アクションの一覧を含む Experimentation and Configuration Service へと連絡します。 この一覧は最初に取得した後にローカルへと保存されるので、サーバーのコピーが変更された場合にのみ、後続の要求が一覧を更新します。

このポリシーを有効にしている場合、ドメイン アクション一覧は、Experimentation and Configuration Service から引き続きダウンロードされます。

このポリシーを無効にしている場合、ドメイン アクション一覧は、Experimentation and Configuration Service からはもうダウンロードされません。

このポリシーを構成していない場合、ドメイン アクション一覧は、Experimentation and Configuration Service から引き続きダウンロードされます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: EnableDomainActionsDownload
  - GP 名: Microsoft からのドメイン アクションのダウンロードを有効にする (不使用)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: EnableDomainActionsDownload
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: EnableDomainActionsDownload
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### EnableOnlineRevocationChecks

  #### オンラインでの OCSP/CRL のチェックを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  オンラインでの失効チェックはセキュリティ上の大きなメリットがなく、既定では無効にされています。

このポリシーを有効にしている場合、Microsoft Edge は、ソフト フェイルやオンラインでの OCSP/CRL のチェックを実行します。 "ソフト フェイル" とは、失効サーバーに到達できない場合に、証明書が有効であるとみなされることを意味します。

ポリシーを無効にしているか、構成していない場合、Microsoft Edge はオンラインでの失効チェックを実行しません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: EnableOnlineRevocationChecks
  - GP 名: オンラインでの OCSP/CRL のチェックを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: EnableOnlineRevocationChecks
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: EnableOnlineRevocationChecks
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### EnableSha1ForLocalAnchors

  #### ローカルトラストアンカーによって発行されたときに SHA-1 を使用して署名された証明書を許可します (非推奨)

  >非推奨: このポリシーは推奨されなくなっています。 現在はサポートされていますが、将来のリリースで廃止されます。
  
  #### サポートされているバージョン:

  - Windows と macOS での 85 以降

  #### 説明

  この設定を有効にすると、Microsoft Edge では、証明書がローカルにインストールされたルート証明書にチェーン接続されていて有効である限り、 SHA-1 署名付き証明書で保護された接続を許可します。

このポリシーは、SHA-1 署名を許可しているオペレーティング システム (OS) の証明書検証スタックに依存します。 OS の更新プログラムが、SHA-1 証明書の OS 処理を変更した場合、このポリシーは無効になる可能性があります。  さらに、このポリシーは、SHA-1 から移行するための時間を企業に与える一時的な回避策となることを意図しています。 このポリシーは、2021 年半ばにリリースされる Microsoft Edge 92 で削除されます。

このポリシーを設定しない、または false に設定した場合、または SHA-1 証明書が公に信頼されている証明書ルートにチェーンされている場合、Microsoft Edge は SHA-1 で署名された証明書を許可しません。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: EnableSha1ForLocalAnchors
  - GP 名: ローカル トラスト アンカーによって発行されたときに SHA-1 を使用して署名された証明書を許可します (非推奨)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: EnableSha1ForLocalAnchors
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - プリファレンス キーの名前: EnableSha1ForLocalAnchors
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### EnterpriseHardwarePlatformAPIEnabled

  #### マネージ拡張がエンタープライズ ハードウェア プラットフォーム API を使用できるようにする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 78 以降

  #### 説明

  このポリシーを有効に設定している場合、エンタープライズ ポリシーによってインストールされた拡張機能が、エンタープライズ ハードウェア プラットフォーム API を使用することができるようになります。
このポリシーを無効に設定しているか、設定されていない場合、拡張機能がエンタープライズ ハードウェア プラットフォーム API を使用することはできません。
このポリシーは、コンポーネントの拡張機能にも適用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: EnterpriseHardwarePlatformAPIEnabled
  - GP 名: マネージ拡張がエンタープライズ ハードウェア プラットフォーム API を使用できるようにする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: EnterpriseHardwarePlatformAPIEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: EnterpriseHardwarePlatformAPIEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### EnterpriseModeSiteListManagerAllowed

  #### Enterprise Mode Site List Manager ツールへのアクセスを許可する

  
  
  #### サポートされているバージョン:

  - Windows での 86 以降

  #### 説明

  Enterprise Mode Site List Manager をユーザーが使用できるかどうかを設定できます。

このポリシーを有効にすると、edge://compat ページに [Enterprise Mode Site List Manager] のナビゲーション ボタンがユーザーに表示され、ツールに移動して使用することができます。

このポリシーを無効または構成しなかった場合、[Enterprise Mode Site List Manager] のナビゲーションボタンはユーザーに表示されず、使用することはできません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: EnterpriseModeSiteListManagerAllowed
  - GP 名: Enterprise Mode Site List Manager ツールへのアクセスを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: EnterpriseModeSiteListManagerAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### ExemptDomainFileTypePairsFromFileTypeDownloadWarnings

  #### ドメイン上の指定されたファイルの種類のダウンロード ファイルの種類の拡張子ベースの警告を無効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 85 以降

  #### 説明

  このポリシーを有効にして、ファイルの種類の拡張子に基づくダウンロード警告から除外される、対応するドメインのリストを含むファイルの種類の拡張子の辞書を作成できます。 これにより、エンタープライズ管理者は、リストされたドメインに関連付けられているファイルについて、ファイルの種類の拡張子ベースのダウンロード警告をブロックできます。 たとえば、「jnlp」拡張子が「website1.com」に関連付けられている場合、「website1.com」から「jnlp」ファイルをダウンロードするときに警告は表示されませんが、「website2.com」から「jnlp」ファイルをダウンロードするときにダウンロード警告が表示されます。

このポリシーで識別されるドメインに指定されたファイルの種類の拡張子を持つファイルは、混合コンテンツのダウンロード警告や Microsoft Defender SmartScreen 警告など、ファイルの種類の拡張子ベースではないセキュリティ警告の影響を受けます。

このポリシーを無効にするか、または構成しない場合、拡張子ベースのダウンロード警告をトリガーするファイルの種類は、ユーザーに警告を表示します。

このポリシーを有効にした場合:

* URL パターンは [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) に応じて書式設定する必要があります。
* 入力するファイルの種類の拡張子は、小文字の ASCII にする必要があります。 ファイルの種類の拡張子を記載するときは、先頭の区切り記号を含めないでください。したがって、「.jnlp」の代わりに「jnlp」を使用する必要があります。

例:

次の例の値は、*.contoso.com ドメインの swf、exe、および jnlp 拡張子に対するファイルの種類の拡張子ベースのダウンロード警告を防ぎます。 他のドメインでは、exe および jnlp ファイルのファイルの種類の拡張子ベースのダウンロード警告が表示されますが、swf ファイルの場合は表示されません。

[ { "file_extension": "jnlp", "domains": ["contoso.com"] }, { "file_extension": "exe", "domains": ["contoso.com"] }, { "file_extension": "swf", "domains": ["*"] } ]

上記の例は、すべてのドメインの「swf」ファイルに対するファイルの種類の拡張子ベースのダウンロード警告の抑制を示していますが、危険性のあるファイルの種類の拡張子に対してすべてのドメインにそのような警告の抑制を適用することは、セキュリティ上の理由からお勧めできません。 例では、そうする能力を示すためにのみ示しています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ExemptDomainFileTypePairsFromFileTypeDownloadWarnings
  - GP 名: ドメイン上の指定されたファイルの種類のダウンロード ファイルの種類の拡張子ベースの警告を無効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\ExemptDomainFileTypePairsFromFileTypeDownloadWarnings
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\ExemptDomainFileTypePairsFromFileTypeDownloadWarnings\1 = {"domains": ["https://contoso.com", "contoso2.com"], "file_extension": "jnlp"}
SOFTWARE\Policies\Microsoft\Edge\ExemptDomainFileTypePairsFromFileTypeDownloadWarnings\2 = {"domains": ["*"], "file_extension": "swf"}

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ExemptDomainFileTypePairsFromFileTypeDownloadWarnings
  - サンプル値:
``` xml
<array>
  <string>{'domains': ['https://contoso.com', 'contoso2.com'], 'file_extension': 'jnlp'}</string>
  <string>{'domains': ['*'], 'file_extension': 'swf'}</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ExperimentationAndConfigurationServiceControl

  #### Experimentation and Configuration Service との通信を制御する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge では、Experimentation and Configuration Service を使用して試験ペイロードと構成ペイロードを展開します。

試験ペイロードは、Microsoft がテストとフィードバックのために有効にしている開発初期の機能の一覧で構成されています。

構成ペイロードは、Microsoft がユーザー エクスペリエンスを最適化するために Microsoft Edge へと展開したいと考えている設定の一覧で構成されています。 たとえば、設定ペイロードは、Microsoft Edge が最新のペイロードを取得するために Experimentation and Configuration Service に要求を送信する頻度を指定することができます。

加えて設定ペイロードには、互換性の理由から特定のドメインで選択するアクションの一覧を含めることもできます。 たとえば、Microsoft Edge の新しいユーザー エージェント文字列によって Web サイトが壊れている場合、ブラウザーがその Web サイトのユーザー エージェント文字列を上書きする場合があります。 これらのアクションは、Microsoft がサイトの所有者との間で問題を解決しようとする間、一時的に行われることを意図しています。

このポリシーを "'FullMode" に設定している場合、Experimentation and Configuration Service からペイロードのすべてがダウンロードされます。 これには、試験ペイロードと構成ペイロードの両方が含まれます。

このポリシーを "ConfigurationsOnlyMode" モードに設定している場合、構成ペイロードのみが配信されます。

このポリシーを 'RestrictedMode' に設定すると、実験および構成サービスとの通信は完全に停止します。

このポリシーを構成していない場合、安定版やベータ版チャネルの管理対象デバイスでは、動作は "ConfigurationsOnlyMode" モードと同じになります。

このポリシーを構成していない場合、管理されていないデバイスでは、動作は "FullMode" と同じになります。

ポリシー オプション マッピング:

* FullMode (2) = 構成と試験を取得する

* ConfigurationsOnlyMode (1) = 構成のみを取得する

* RestrictedMode (0) = Experimentation and Configuration Service との通信を無効にする

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ExperimentationAndConfigurationServiceControl
  - GP 名: Experimentation and Configuration Service との通信を制御する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ExperimentationAndConfigurationServiceControl
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ExperimentationAndConfigurationServiceControl
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ExternalProtocolDialogShowAlwaysOpenCheckbox

  #### 外部プロトコル ダイアログで [常に開く] チェックボックスを表示する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 79 以降

  #### 説明

  このポリシーは、外部プロトコルの起動を確認するメッセージに [Always allow this site to open links of this type] (この種類のリンクを開くのに常にこのサイトを許可する) チェックボックスを表示するかどうかを制御します。 このポリシーは https://links にのみ適用されます。

このポリシーを有効にしている場合、外部プロトコルの確認メッセージが表示されたときに、ユーザーは [常に許可] を選択して、このサイト上のプロトコルに関する今後の確認メッセージをすべてスキップすることができます。

このポリシーを無効にしている場合、[常に許可] チェックボックスは表示されません。 外部プロトコルが呼び出されるたびに、ユーザーはメッセージの確認を求められます。

Microsoft Edge 83 より前のバージョンでは、このポリシーを構成しない場合、[常に許可する] チェックボックスは表示されません。 外部プロトコルが呼び出されるたびに、ユーザーはメッセージの確認を求められます。

Microsoft Edge 83 では、このポリシーを構成していない場合、チェックボックスの表示は、edge://flags の「プロトコル起動のプロンプト設定の記憶を有効にする」フラグによって制御されます。

Microsoft Edge 84 以降、このポリシーを構成しない場合、外部プロトコルの確認メッセージが表示されたときに、ユーザーは [常に許可] を選択して、このサイト上のプロトコルに関する今後の確認メッセージをすべてスキップすることができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ExternalProtocolDialogShowAlwaysOpenCheckbox
  - GP 名: 外部プロトコル ダイアログで [常に開く] チェックボックスを表示する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ExternalProtocolDialogShowAlwaysOpenCheckbox
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ExternalProtocolDialogShowAlwaysOpenCheckbox
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### FamilySafetySettingsEnabled

  #### ファミリー セーフティをユーザーが構成できるようにする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 83 以降

  #### 説明

  このポリシーは、[設定] の [ファミリー セーフティ] ページを無効にし、完全に非表示にします。 edge://settings/familysafety へのナビゲーションもブロックされます。 [ファミリー セーフティ] ページでは、ファミリ グループで利用できる機能と、ファミリ グループに参加する方法について説明しています。 ファミリー セーフティの詳細については、「[https://go.microsoft.com/fwlink/?linkid=2098432](https://go.microsoft.com/fwlink/?linkid=2098432)」を参照してください。

このポリシーを有効にしているか、構成していない場合、[ファミリー セーフティ] ページは表示されます。

このポリシーを無効にしている場合、[ファミリー セーフティ] ページは表示されません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: FamilySafetySettingsEnabled
  - GP 名: ファミリー セーフティをユーザーが構成できるようにする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: FamilySafetySettingsEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: FamilySafetySettingsEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### FavoritesBarEnabled

  #### お気に入り バーを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  お気に入り バーを有効または無効にします。

このポリシーを有効にしている場合、ユーザーにお気に入り バーが表示されます。

このポリシーを無効にしている場合、ユーザーにお気に入り バーは表示されません。

このポリシーを設定していない場合、お気に入り バーを使用するかどうかをユーザーが決定することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: FavoritesBarEnabled
  - GP 名: お気に入り バーを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: FavoritesBarEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: FavoritesBarEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ForceBingSafeSearch

  #### Bing セーフサーチを強制する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Bing Web 検索のクエリが、指定された値にセーフサーチを設定して実行されるようにします。 ユーザーがこの設定を変更することはできません。

このポリシーを 'BingSafeSearchNoRestrictionsMode' に構成すると、Bing 検索のセーフサーチは bing.com の値に戻ります。

このポリシーを "BingSafeSearchModerateMode" に構成している場合、セーフサーチでは標準設定が使用されます。 標準設定では、成人向けの動画や画像はフィルター処理されますが、検索結果のテキストはフィルター処理されません。

このポリシーを "BingSafeSearchStrictMode" に設定している場合、セーフサーチでは厳密設定が使用されます。 厳密設定では、成人向けのテキスト、画像、動画をフィルター処理します。

このポリシーを無効にしているか、構成していない場合、Bing 検索でのセーフサーチは強制されず、ユーザーは bing.com で好きな値を設定することができます。

ポリシー オプション マッピング:

* BingSafeSearchNoRestrictionsMode (0) = Bing で検索制限を構成しない

* BingSafeSearchModerateMode (1) = Bing で標準の検索制限を構成する

* BingSafeSearchStrictMode (2) = Bing で厳密な検索制限を構成する

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ForceBingSafeSearch
  - GP 名: Bing セーフサーチを強制する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ForceBingSafeSearch
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ForceBingSafeSearch
  - サンプル値:
``` xml
<integer>0</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ForceCertificatePromptsOnMultipleMatches

  #### "AutoSelectCertificateForUrls" が構成されているサイトに対して複数の証明書が一致する場合、Microsoft Edge が自動的に証明書を選択するかどうかを構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 81 以降

  #### 説明

  複数の証明書が利用可能で、サイトに [AutoSelectCertificateForUrls](#autoselectcertificateforurls) が構成されている場合に、ユーザーに証明書の選択を確認するメッセージを表示するかどうかを切り替えます。 サイトに対して [AutoSelectCertificateForUrls](#autoselectcertificateforurls) を構成していない場合、ユーザーには常に証明書の選択を求めるメッセージが表示されます。

このポリシーを true に設定している場合、Microsoft Edge は、証明書が複数ある場合にのみ、[AutoSelectCertificateForUrls](#autoselectcertificateforurls) で定義されている一覧にあるサイトの証明書の選択を求めるメッセージをユーザーに表示します。

このポリシーを false に設定しているか、構成していない場合、一致する証明書が複数が見つかったとしても、Microsoft Edge は証明書を自動的に選択します。 ユーザーには、[AutoSelectCertificateForUrls](#autoselectcertificateforurls) で定義されている一覧のサイトの証明書を選択するよう求めるメッセージは表示されません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ForceCertificatePromptsOnMultipleMatches
  - GP 名: "AutoSelectCertificateForUrls" が構成されているサイトに対して複数の証明書が一致する場合、Microsoft Edge が自動的に証明書を選択するかどうかを構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ForceCertificatePromptsOnMultipleMatches
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ForceCertificatePromptsOnMultipleMatches
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ForceEphemeralProfiles

  #### 短期プロファイルの使用を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ユーザー プロファイルを短期モードに切り替えるかどうかを制御します。 短期プロファイルはセッションの開始時に作成され、セッションの終了時に削除され、ユーザーの元のプロファイルに関連付けられます。

このポリシーを有効にしている場合、プロファイルは短期モードで実行されます。 これにより、ユーザーは閲覧データを自分のデバイスに保存せずに、それらのデバイスから作業を行うことができます。 このポリシーを OS ポリシーとして有効にすると (たとえば、Windows で GPO を使用するなど)、システム上のすべてのプロファイルに適用されます。

このポリシーを無効にしているか、構成していない場合、ユーザーはブラウザーにサインインしたときに通常のプロファイルを取得します。

短期モードでは、プロファイルのデータはユーザー セッションの長さのみがディスクに保存されます。 ブラウザーの履歴、拡張機能とそのデータ、Cookie などの Web データ、Web データベースなどの機能は、ブラウザーを閉じた後には保存されません。 これは、ユーザが手動でディスクにデータをダウンロードしたり、ページを保存したり印刷したりすることを防止するものではありません。 ユーザーが同期を有効にしている場合、通常のプロファイルと同様に、すべてのデータがユーザーの同期アカウントに保存されます。 明示的に無効にしない限り、ユーザーが短期モードで InPrivate ブラウズを使用することも可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ForceEphemeralProfiles
  - GP 名: 短期プロファイルの使用を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ForceEphemeralProfiles
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ForceEphemeralProfiles
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ForceGoogleSafeSearch

  #### Google セーフサーチを強制する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  強制的に Google Web 検索のクエリをセーフサーチをアクティブに設定した状態で実行し、ユーザーがこの設定を変更できないようにします。

このポリシーを有効にしている場合、Google 検索のセーフサーチは常にアクティブになります。

このポリシーを無効にしているか、構成していない場合、Google 検索でのセーフサーチは強制されません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ForceGoogleSafeSearch
  - GP 名: Google セーフサーチを強制する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ForceGoogleSafeSearch
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ForceGoogleSafeSearch
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ForceLegacyDefaultReferrerPolicy

  #### 参照元がダウングレードされていない場合の既定の参照元ポリシーを使用する (廃止)

  
  >不使用: このポリシーは廃止されており、Microsoft Edge 88 以降は機能しません。
  #### サポートされているバージョン:

  - Windows と macOS での 81 以降、88 まで

  #### 説明

  このポリシーは、企業の Web コンテンツが新しい既定の参照元ポリシーと互換していないことが判明した場合に、Web コンテンツの更新に時間を割くための短期のメカニズムとしてのみ機能することを目的としているため、機能しません。

Microsoft Edge の既定の参照元ポリシーは、no-referrer-when-downgrade の値から、より安全性の高い strict-origin-when-cross-origin に強化されました。

このエンタープライズ ポリシーを有効にすると、Microsoft Edge の既定の参照元ポリシーは、以前の値である no-referrer-when-downgrade に設定されます。

このエンタープライズ ポリシーは、既定では無効になっています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - 一意の GP 名: ForceLegacyDefaultReferrerPolicy
  - GP 名: no-referrer-when-downgrade の既定の参照元ポリシーを使用する (廃止)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ForceLegacyDefaultReferrerPolicy
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ForceLegacyDefaultReferrerPolicy
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ForceNetworkInProcess

  #### ブラウザー プロセスでネットワーク コードを強制的に実行する (不使用)

  
  >不使用: このポリシーは廃止されており、Microsoft Edge 83 以降は機能しません。
  #### サポートされているバージョン:

  - Windows での 78 以降 83 まで

  #### 説明

  このポリシーは、企業に対する Networking API のフックに依存しないサードパーティ製ソフトウェアへの移行の機会を提供する時間を割くための短期メカニズムとして機能することを目的としていたため、機能しません。 LSP や Win32 API の修正よりも、プロキシ サーバーの使用をお勧めします。

このポリシーは、ブラウザー プロセスでネットワーク コードを強制的に実行します。

このポリシーは、既定では無効になっています。 有効にしている場合、ネットワーキング プロセスがサンドボックス内で動作しているときに、ユーザーはセキュリティの問題にさらされます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ForceNetworkInProcess
  - GP 名: ブラウザー プロセスでネットワーク コードを強制的に実行する (不使用)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ForceNetworkInProcess
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### ForceSync

  #### ブラウザーのデータを強制的に同期し、同期の同意プロンプトを表示しない

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  Microsoft Edge でのデータを強制的に同期します。 このポリシーでは、ユーザーも同期をオフにすることはできません。

このポリシーを構成しない場合、ユーザーは同期をオンまたはオフにすることができます。 このポリシーを有効にした場合、ユーザーは同期をオフにすることはできません。

このポリシーが意図したとおりに動作するためには、 [BrowserSignin](#browsersignin) ポリシーが構成されていないか、または有効に設定する必要があります。 [BrowserSignin](#browsersignin) が無効に設定されている場合、[ForceSync](#forcesync) は有効になりません。

[SyncDisabled](#syncdisabled)を構成することはできません。または False に設定する必要があります。  この設定が True に設定されている場合、 [ForceSync](#forcesync) は有効になりません。

0 = 自動的に同期が開始されず、同期の同意が表示されない(既定) 1 = Azure AD/Azure AD-Degradedユーザープロファイルに対して強制的に同期を有効にする-同期の同意のプロンプトが表示されない

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ForceSync
  - GP 名: ブラウザーデータを強制的に同期し、同期の同意のプロンプトを表示しない
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ForceSync
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ForceSync
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ForceYouTubeRestrict

  #### 最小限の YouTube 制限モードを強制的に実行する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  YouTube で最小限の制限モードを強制し、ユーザーがより制限少ないモードを選択することを防止します。

[厳密] に設定すると、YouTube で 厳密な制限モードを強制します。

[標準] に設定すると、標準の制限モードと厳密な制限モードのみを YouTube で使用するようユーザーに強制します。 ユーザーが制限モードを無効にすることはできません。

[オフ] に設定するか、このポリシーを構成しない場合、YouTube での制限モードを強制しません。 YouTube ポリシーのような外部のポリシーによって、制限モードが強制される可能性があります。

ポリシー オプション マッピング:

* オフ (0) = YouTube で制限モードを強制しない

* 標準 (1) = YouTube で、少なくとも標準の制限モードを強制する

* 厳密 (2) = YouTube で厳密な制限モードを強制する

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ForceYouTubeRestrict
  - GP 名: 最小限の YouTube 制限モードを強制的に実行する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ForceYouTubeRestrict
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ForceYouTubeRestrict
  - サンプル値:
``` xml
<integer>0</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### FullscreenAllowed

  #### 全画面表示モードを許可する

  
  
  #### サポートされているバージョン:

  - Windows での 77 以降

  #### 説明

  全画面表示モードの可用性を設定します。すべての Microsoft Edge UI が非表示になり、Web コンテンツのみが表示されます。

このポリシーを有効にしているか、構成していない場合、適切なアクセス許可を持っているユーザー、アプリ、拡張機能が全画面表示モードを開始することができるようになります。

このポリシーを無効にしている場合、ユーザー、アプリ、拡張機能が全画面表示モードを開始することはできません。

全画面表示モードを無効にしている場合、コマンドラインを使用したキオスク モードで Microsoft Edge を開くことはできません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: FullscreenAllowed
  - GP 名: 全画面表示モードを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: FullscreenAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### GloballyScopeHTTPAuthCacheEnabled

  #### グローバルにスコープが設定された HTTP 認証キャッシュを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 81 以降

  #### 説明

  このポリシーでは、HTTP サーバー認証の資格情報を使用して、プロファイルごとに単一のグローバル キャッシュを構成します。

このポリシーを無効にしているか、設定していない場合、ブラウザーはクロスサイト認証の既定の動作を使用します。バージョン 80 の時点では、この動作により、トップレベル サイトによる HTTP サーバー認証の資格情報がスコープに含まれます。 そのため、同じ認証ドメインからのリソースを 2 つのサイトが使用している場合、資格情報は両方のサイトのコンテキストで個別に提供される必要があります。 キャッシュされたプロキシの資格情報は、サイト間をまたいで再利用されます。

このポリシーを有効にしている場合、あるサイトのコンテキストで入力された HTTP 認証の資格情報は、もう 1 つのサイトのコンテキストでも自動的に使用されます。

このポリシーを有効にしている場合、サイトには一部のクロスサイト攻撃にさらされる可能性があり、URL に埋め込まれた資格情報を使用して HTTP 認証キャッシュにエントリを追加することで、Cookie がなくてもユーザーをサイト間で追跡することができます。

このポリシーは、従来の動作に依存している企業に対するログイン手順の更新の機会の提供を目的としており、将来的には削除されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: GloballyScopeHTTPAuthCacheEnabled
  - GP 名: グローバルにスコープが設定された HTTP 認証キャッシュを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: GloballyScopeHTTPAuthCacheEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: GloballyScopeHTTPAuthCacheEnabled
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### GoToIntranetSiteForSingleWordEntryInAddressBar

  #### アドレス バーへの 1 単語の入力による検索ではなく、ダイレクト イントラネット サイト ナビゲーションを強制的に実行する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 78 以降

  #### 説明

  このポリシーを有効にしている場合、アドレス バーに入力されたテキストが句読点のない単一の単語であるときに、アドレス バーの提案一覧の先頭にある自動提案の結果にイントラネット サイトが表示されます。

句読点のない単一の単語を入力した場合の既定のナビゲーションは、入力されたテキストに一致するイントラネット サイトの表示を行います。

このポリシーを有効にしている場合、アドレス バーに入力されたテキストが句読点のない単一の単語であるときに、アドレス バーの提案一覧の 2 番目にある自動提案の結果が入力されたとおりの Web 検索を実行します。 Web 検索を防止するポリシーが有効になっていない限り、既定の検索プロバイダーが使用されます。

このポリシーを有効にすると、次の 2 つの効果が現れます。

通常であれば履歴項目に解決されるはずの単一の単語のクエリに対応したサイトへの移動は、もう起こらなくなります。 その代わりに、ブラウザーは組織のイントラネットに存在しない場合がある内部サイトへの移動を試みます。 これは、404 エラーを返す結果になります。

よく使われる単一の単語のよる検索用語については、適切に検索を行うために検索候補を手動で選択する必要があります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: GoToIntranetSiteForSingleWordEntryInAddressBar
  - GP 名: アドレス バーへの 1 単語の入力による検索ではなく、ダイレクト イントラネット サイト ナビゲーションを強制的に実行する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: GoToIntranetSiteForSingleWordEntryInAddressBar
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: GoToIntranetSiteForSingleWordEntryInAddressBar
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### HSTSPolicyBypassList

  #### HSTS ポリシーのチェックをバイパスする名前の一覧を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 79 以降

  #### 説明

  この一覧で指定されたホスト名は、"http://" から "https://" へと要求をアップグレードする可能性のある HSTS ポリシー チェックの対象外となります。 このポリシーでは、単一ラベルのホスト名のみが許可されます。 ホスト名は正規化する必要があります。 すべての IDN は A ラベル形式に変換され、すべての ASCII 文字は小文字である必要があります。 このポリシーは指定された特定のホスト名にのみ適用され、リスト内の名前のサブドメインには適用されません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: HSTSPolicyBypassList
  - GP 名: HSTS ポリシーのチェックをバイパスする名前の一覧を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\HSTSPolicyBypassList
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\HSTSPolicyBypassList\1 = "meet"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: HSTSPolicyBypassList
  - サンプル値:
``` xml
<array>
  <string>meet</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### HardwareAccelerationModeEnabled

  #### 使用可能な場合はハードウェア アクセラレータを使用する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  使用可能であれば、ハードウェア アクセラレータを使用するように指定します。 このポリシーを有効にしているか、構成していない場合、GPU 機能が明示的にブロックされていない限り、ハードウェア アクセラレータは有効になります。

このポリシーを無効にしている場合、ハードウェア アクセラレータは無効になります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: HardwareAccelerationModeEnabled
  - GP 名: 使用可能な場合はハードウェア アクセラレータを使用する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: HardwareAccelerationModeEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: HardwareAccelerationModeEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### HideFirstRunExperience

  #### 初回実行時のエクスペリエンスとスプラッシュ画面を非表示にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 80 以降

  #### 説明

  このポリシーを有効にしている場合、ユーザーが初めて Microsoft Edge を起動したときに、初回実行時のエクスペリエンスとスプラッシュ画面が表示されなくなります。

初回実行時のエクスペリエンスに表示される構成オプションについては、ブラウザーの既定では以下のようになります。

- 新規タブ ページでは、フィードの種類が MSN ニュースに、レイアウトがインスピレーションに設定されます。

- Windows アカウントが Azure AD または MSA の種類の場合でも、ユーザーは自動的に Microsoft Edge へとサインインします。

- 同期は既定では有効になりません。ユーザーはブラウザーの起動時に同期するかどうかを選択するように求められます。 [ForceSync](#forcesync) または [SyncDisabled](#syncdisabled) ポリシーを使用して、同期および同期の同意プロンプトを構成できます。

このポリシーを無効にしているか、構成していない場合、初回実行時のエクスペリエンスとスプラッシュ画面は表示されます。

注: 初回実行時のエクスペリエンスでユーザーに表示される特定の構成オプションは、その他の特定のポリシーを使用して管理することもできます。 これらのポリシーと組み合わせて HideFirstRunExperience ポリシーを使用して、管理対象デバイスで特定のブラウザー エクスペリエンスを構成することができます。 その他のポリシーには、次のものがあります。

-[AutoImportAtFirstRun](#autoimportatfirstrun)

-[NewTabPageLocation](#newtabpagelocation)

-[NewTabPageSetFeedType](#newtabpagesetfeedtype)

-[ForceSync](#forcesync)

-[SyncDisabled](#syncdisabled)

-[BrowserSignin](#browsersignin)

-[NonRemovableProfileEnabled](#nonremovableprofileenabled)

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: HideFirstRunExperience
  - GP 名: 初回実行時のエクスペリエンスとスプラッシュ画面を非表示にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: HideFirstRunExperience
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: HideFirstRunExperience
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### HideInternetExplorerRedirectUXForIncompatibleSitesEnabled

  #### Microsoft Edge でワンタイム リダイレクト ダイアログとバナーを非表示にする

  
  
  #### サポートされているバージョン:

  - Windows での 87 以降

  #### 説明

  このポリシーは、ワンタイム リダイレクト ダイアログとバナーを無効にするオプションを提供します。 このポリシーを有効にすると、ユーザーにはワンタイム ダイアログとバナーの両方が表示されなくなります。
Internet Explorer で互換性のない Web サイトに遭遇した場合、ユーザーは引き続き Microsoft Edge にリダイレクトされますが、閲覧データはインポートされません。

- このポリシーを有効にすると、ワンタイム リダイレクト ダイアログとバナーがユーザーに表示されることはありません。 リダイレクトが発生した場合、ユーザーの閲覧データはインポートされません。

- このポリシーを無効にするか設定しない場合、リダイレクト ダイアログは最初のリダイレクトに表示され、永続的なリダイレクト バナーはリダイレクトで始まるセッションのユーザーに表示されます。 ユーザーの閲覧データは、(ユーザーがワンタイム ダイアログでそれに同意した場合のみ) ユーザーがそのようなリダイレクトに遭遇するたびにインポートされます。


  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: HideInternetExplorerRedirectUXForIncompatibleSitesEnabled
  - GP 名: Microsoft Edge でワンタイム リダイレクト ダイアログとバナーを非表示にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - Value Name: HideInternetExplorerRedirectUXForIncompatibleSitesEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### ImportAutofillFormData

  #### オートフィル フォームのデータのインポートを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  別のブラウザーから Microsoft Edge へと、オートフィル フォームのデータをユーザーがインポートできるようになります。

このポリシーを有効にしている場合、オートフィルのデータを手動でインポートするオプションが自動的に選択されます。

このポリシーを無効にしている場合、オートフィル フォームのデータは初回実行時にはインポートされず、ユーザーが手動でインポートすることはできません。

このポリシーを構成していない場合、オートフィル データは初回実行時にインポートされ、その後のブラウジング セッション中にこのデータを手動でインポートするかどうかをユーザーが選択できるようになります。

このポリシーは、推奨として設定することができます。 これは、Microsoft Edge が初回実行時にオートフィルのデータをインポートすることを意味しますが、ユーザーは手動インポート中に**オートフィルのデータ** オプションを選択するか、クリアすることができます。

**注**: このポリシーは現在、Google Chrome (Windows 7、8、10、macOS 上)、Mozilla Firefox (Windows 7、8、10、macOS 上) ブラウザーからのインポートを管理しています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ImportAutofillFormData
  - GP 名: オートフィル フォームのデータのインポートを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ImportAutofillFormData
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ImportAutofillFormData
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ImportBrowserSettings

  #### ブラウザーの設定のインポートを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 78 以降

  #### 説明

  別のブラウザーから Microsoft Edge へと、ブラウザーの設定をユーザーがインポートできるようになります。

このポリシーを有効にしている場合、[**Import browser data**] (ブラウザーのデータのインポート) ダイアログ ボックスの [**ブラウザーの設定**] チェックボックスが自動的に選択されます。

このポリシーを無効にしている場合、ブラウザーの設定は初回実行時にインポートされず、ユーザーが手動でインポートすることはできません。

このポリシーを構成していない場合、ブラウザーの設定は初回実行時にインポートされ、その後のブラウジング セッション中にこれらを手動でインポートするかどうかをユーザーが選択できるようになります。

このポリシーは推奨として設定することもできます。 これは、Microsoft Edge が初回実行時に設定をインポートすることを意味しますが、ユーザーは手動インポート中に**ブラウザーの設定** オプションを選択するか、クリアすることができます。

**注**: このポリシーは現在、Google Chrome (Windows 7、8、10、macOS 上) のインポートを管理しています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ImportBrowserSettings
  - GP 名: ブラウザーの設定のインポートを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ImportBrowserSettings
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ImportBrowserSettings
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ImportCookies

  #### Cookie のインポートを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 81 以降

  #### 説明

  別のブラウザーから Microsoft Edge へと、Cookie をユーザーがインポートできるようになります。

このポリシーを無効にしている場合、Cookie は初回実行時にインポートされません。

このポリシーを構成していない場合、Cookie は初回実行時にインポートされます。

このポリシーは推奨として設定することもできます。 これは、Microsoft Edge が初回実行時に Cookie をインポートすることを意味します。

**注**: このポリシーは現在、Google Chrome (Windows 7、8、10、macOS 上) のインポートを管理しています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ImportCookies
  - GP 名: Cookie のインポートを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ImportCookies
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ImportCookies
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ImportExtensions

  #### 拡張機能のインポートを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 81 以降

  #### 説明

  別のブラウザーから Microsoft Edge へと、拡張機能をユーザーがインポートできるようになります。

このポリシーを有効にしている場合、[**Import browser data**] (ブラウザーのデータのインポート) ダイアログ ボックスの [**拡張機能**] チェックボックスが自動的に選択されます。

このポリシーを無効にしている場合、拡張機能は初回実行時にインポートされず、ユーザーが手動でインポートすることはできません。

このポリシーを構成していない場合、拡張機能は初回実行時にインポートされ、その後のブラウジング セッション中にこれらを手動でインポートするかどうかをユーザーが選択できるようになります。

このポリシーは推奨として設定することもできます。 これは、Microsoft Edge が初回実行時に拡張機能をインポートすることを意味しますが、ユーザーは手動インポート中に**お気に入り** オプションを選択するか、クリアすることができます。

**注**: このポリシーは現在、Google Chrome (Windows 7、8、10、macOS 上) からのインポートのみをサポートしています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ImportExtensions
  - GP 名: 拡張機能のインポートを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ImportExtensions
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ImportExtensions
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ImportFavorites

  #### お気に入りのインポートを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  別のブラウザーから Microsoft Edge へと、お気に入りをユーザーがインポートできるようになります。

このポリシーを有効にしている場合、[**Import browser data**] (ブラウザーのデータのインポート) ダイアログ ボックスの [**お気に入り**] チェックボックスが自動的に選択されます。

このポリシーを無効にしている場合、お気に入りは初回実行時にインポートされず、ユーザーが手動でインポートすることはできません。

このポリシーを構成していない場合、お気に入りは初回実行時にインポートされ、その後のブラウジング セッション中にこれらを手動でインポートするかどうかをユーザーが選択できるようになります。

このポリシーは推奨として設定することもできます。 これは、Microsoft Edge が初回実行時にお気に入りをインポートすることを意味しますが、ユーザーは手動インポート中に**お気に入り** オプションを選択するか、クリアすることができます。

**注**: このポリシーは現在、Internet Explorer (Windows 7、8、10 上)、Google Chrome (Windows 7、8、10、macOS 上)、Mozilla Firefox (Windows 7、8、10、macOS 上)、Apple Safari (macOS 上) ブラウザーからのインポートを管理しています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ImportFavorites
  - GP 名: お気に入りのインポートを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ImportFavorites
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ImportFavorites
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ImportHistory

  #### 閲覧の履歴のインポートを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  別のブラウザーから Microsoft Edge へと、閲覧の履歴をユーザーがインポートできるようになります。

このポリシーを有効にしている場合、[**Import browser data**] (ブラウザーのデータのインポート) ダイアログ ボックスの [**閲覧の履歴**] チェックボックスが自動的に選択されます。

このポリシーを無効にしている場合、閲覧の履歴データは初回実行時にはインポートされず、ユーザーがこのデータを手動でインポートすることはできません。

このポリシーを構成していない場合、閲覧の履歴データは初回実行時にインポートされ、その後のブラウジング セッション中にこのデータを手動でインポートするかどうかをユーザーが選択できるようになります。

このポリシーは推奨として設定することもできます。 これは、Microsoft Edge が初回実行時に閲覧の履歴をインポートすることを意味しますが、ユーザーは手動インポート中に**履歴** オプションを選択するか、クリアすることができます。

**注**: このポリシーは現在、Internet Explorer (Windows 7、8、10 上)、Google Chrome (Windows 7、8、10、macOS 上)、Mozilla Firefox (Windows 7、8、10、macOS 上)、Apple Safari (macOS) ブラウザーからのインポートを管理しています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ImportHistory
  - GP 名: 閲覧の履歴のインポートを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ImportHistory
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ImportHistory
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ImportHomepage

  #### ホーム ページの設定のインポートを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  別のブラウザーから Microsoft Edge へと、ホーム ページの設定をユーザーがインポートできるようになります。

このポリシーを有効にしている場合、ホーム ページの設定を手動でインポートするオプションが自動的に選択されます。

このポリシーを無効にしている場合、ホーム ページの設定は初回実行時にはインポートされず、ユーザーが手動でインポートすることはできません。

このポリシーを構成していない場合、ホーム ページの設定は初回実行時にインポートされ、その後のブラウジング セッション中にこのデータを手動でインポートするかどうかをユーザーが選択できるようになります。

このポリシーは、推奨として設定することができます。 これは、Microsoft Edge が初回実行時にホーム ページの設定をインポートすることを意味しますが、ユーザーは手動インポート中に**ホーム ページ** オプションを選択するか、クリアすることができます。

**注**: このポリシーは現在、Internet Explorer (Windows 7、8、10 上) からのインポートを管理しています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ImportHomepage
  - GP 名: ホーム ページの設定のインポートを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ImportHomepage
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ImportHomepage
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ImportOpenTabs

  #### 開いているタブのインポートを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 79 以降

  #### 説明

  別のブラウザーから Microsoft Edge へと、開いているタブとピン留めされているタブをユーザーがインポートできるようになります。

このポリシーを有効にしている場合、[**Import browser data**] (ブラウザーのデータのインポート) ダイアログ ボックスの [**開いているタブ**] チェックボックスが自動的に選択されます。

このポリシーを無効にしている場合、開いているタブは初回実行時にインポートされず、ユーザーが手動でインポートすることはできません。

このポリシーを構成していない場合、開いているタブは初回実行時にインポートされ、その後のブラウジング セッション中にこれらを手動でインポートするかどうかをユーザーが選択できるようになります。

このポリシーは推奨として設定することもできます。 これは、Microsoft Edge が初回実行時に開いているタブをインポートすることを意味しますが、ユーザーは手動インポート中に**開いているタブ** オプションを選択するか、クリアすることができます。

**注**: このポリシーは現在、Google Chrome (Windows 7、8、10、macOS 上) からのインポートのみをサポートしています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ImportOpenTabs
  - GP 名: 開いているタブのインポートを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ImportOpenTabs
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ImportOpenTabs
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ImportPaymentInfo

  #### 支払情報のインポートを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  別のブラウザーから Microsoft Edge へと、支払い情報をユーザーがインポートできるようになります。

このポリシーを有効にしている場合、[**Import browser data**] (ブラウザーのデータのインポート) ダイアログ ボックスの [**支払い情報**] チェックボックスが自動的に選択されます。

このポリシーを無効にしている場合、支払い情報は初回実行時にはインポートされず、ユーザーが手動でインポートすることはできません。

このポリシーを構成していない場合、支払い情報は初回実行時にインポートされ、その後のブラウジング セッション中にこのデータを手動でインポートするかどうかをユーザーが選択できるようになります。

このポリシーは推奨として設定することもできます。 これは、Microsoft Edge が初回実行時に支払い情報をインポートすることを意味しますが、ユーザーは手動インポート中に**支払い情報** オプションを選択するか、クリアすることができます。

**注**: このポリシーは現在、Google Chrome (Windows 7、8、10、macOS 上) からのインポートを管理しています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ImportPaymentInfo
  - GP 名: 支払情報のインポートを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ImportPaymentInfo
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ImportPaymentInfo
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ImportSavedPasswords

  #### 保存されたパスワードのインポートを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  別のブラウザーから Microsoft Edge へと、保存されたパスワードをユーザーがインポートできるようになります。

このポリシーを有効にしている場合、保存されたパスワードを手動でインポートするオプションが自動的に選択されます。

このポリシーを無効にしている場合、保存されたパスワードは初回実行時にインポートされず、ユーザーが手動でインポートすることはできません。

このポリシーを構成していない場合、パスワードは初回実行時にインポートされ、その後のブラウジング セッション中にこれらを手動でインポートするかどうかをユーザーが選択できるようになります。

このポリシーは、推奨として設定することができます。 これは、Microsoft Edge が初回実行時にパスワードをインポートすることを意味しますが、ユーザーは手動インポート中に**パスワード** オプションを選択するか、クリアすることができます。

**注**: このポリシーは現在、Internet Explorer (Windows 7、8、10 上)、Google Chrome (Windows 7、8、10、macOS 上)、Mozilla Firefox (Windows 7、8、10、macOS 上) ブラウザーからのインポートを管理しています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ImportSavedPasswords
  - GP 名: 保存されたパスワードのインポートを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ImportSavedPasswords
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ImportSavedPasswords
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ImportSearchEngine

  #### 検索エンジンの設定のインポートを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  別のブラウザーから Microsoft Edge へと、検索エンジンの設定をユーザーがインポートできるようになります。

このポリシーを有効にしている場合、検索エンジンの設定をインポートするオプションが自動的に選択されます。

このポリシーを無効にしている場合、検索エンジンの設定は初回実行時にインポートされず、ユーザーが手動でインポートすることはできません。

このポリシーを構成していない場合、検索エンジンの設定は初回実行時にインポートされ、その後のブラウジング セッション中にこのデータを手動でインポートするかどうかをユーザーが選択できるようになります。

このポリシーは、推奨として設定することができます。 これは、Microsoft Edge が初回実行時に検索エンジンの設定をインポートすることを意味しますが、ユーザーは手動インポート中に**検索エンジン** オプションを選択するか、クリアすることができます。

**注**: このポリシーは現在、Internet Explorer (Windows 7、8、10 上) からのインポートを管理しています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ImportSearchEngine
  - GP 名: 検索エンジンの設定のインポートを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ImportSearchEngine
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ImportSearchEngine
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ImportShortcuts

  #### ショートカットのインポートを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 81 以降

  #### 説明

  別のブラウザーから Microsoft Edge へと、ショートカットをユーザーがインポートできるようになります。

このポリシーを無効にしている場合、ショートカットは初回実行時にインポートされません。

このポリシーを構成していない場合、ショートカットは初回実行時にインポートされます。

このポリシーは推奨として設定することもできます。 これは、Microsoft Edge が初回実行時にショートカットをインポートすることを意味します。

**注**: このポリシーは現在、Google Chrome (Windows 7、8、10、macOS 上) からのインポートを管理しています。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ImportShortcuts
  - GP 名: ショートカットのインポートを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ImportShortcuts
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ImportShortcuts
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### InPrivateModeAvailability

  #### InPrivate モードの可用性を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge で、ユーザーが InPrivate モードでページを開くことができるかどうかを指定します。

このポリシーを構成していないか、"有効" に設定している場合、ユーザーは InPrivate モードでページを開くことができます。

このポリシーを "無効" に設定すると、ユーザーが InPrivate モードを使用できなくなります。

このポリシーを "強制" に設定すると、常に InPrivate モードでの使用になります。

ポリシー オプション マッピング:

* 有効 (0) = InPrivate モードを使用可能にする

* 無効 (1) = InPrivate モードを無効にする

* 強制 (2) = InPrivate モードを強制する

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: InPrivateModeAvailability
  - GP 名: InPrivate モードの可用性を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: InPrivateModeAvailability
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: InPrivateModeAvailability
  - サンプル値:
``` xml
<integer>1</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### InsecureFormsWarningsEnabled

  #### セキュリティのないフォームに対する警告を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  このポリシーでは、ブラウザーのセキュリティで保護された (HTTPS) サイトに埋め込まれたセキュリティで保護されていないフォーム (HTTP 経由で送信されたフォーム) の処理を制御します。
このポリシーを有効にした場合、または設定しない場合は、セキュリティで保護されていないフォームが送信されると、ページ全体の警告が表示されます。 フォーカスがある場合は、フォームフィールドの横に警告バブルが表示されます。そのようなフォームのオートフィルは無効になります。
このポリシーを無効にすると、セキュリティで保護されていないフォームの警告が表示されなくなります。オートフィルは正常に機能します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: InsecureFormsWarningsEnabled
  - GP 名: セキュリティで保護されていないフォームに対する警告を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: InsecureFormsWarningsEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 優先順位キーの名前: InsecureFormsWarningsEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### IntensiveWakeUpThrottlingEnabled

  #### IntensiveWakeUpThrottling 機能を制御する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 85 以降

  #### 説明

  IntensiveWakeUpThrottling 機能を有効にすると、バックグラウンド タブの Javascript タイマーが積極的に抑制および合体され、ページが 5 分以上バックグラウンド化された後、毎分 1 回だけ実行されます。

これは Web 標準に準拠した機能ですが、特定の操作を最大 1 分遅延させることにより、一部の Web サイトの機能を損なう可能性があります。 ただし、有効にすると、CPU とバッテリーを大幅に節約できます。 詳細については、https://bit.ly/30b1XR4 を参照してください。

このポリシーを有効にすると、機能が強制的に有効になり、ユーザーはこの設定を上書きできなくなります。
このポリシーを無効にすると、機能が強制的に無効になり、ユーザーはこの設定を上書きできなくなります。
このポリシーを構成しない場合、機能は独自の内部ロジックによって制御されます。 ユーザーはこの設定を手動で構成できます。

ポリシーはレンダラー プロセスごとに適用され、レンダラー プロセスの開始時にポリシー設定の最新の値が有効になることに注意してください。 読み込まれたすべてのタブが一貫したポリシー設定を受け取るようにするには、完全な再起動が必要です。 このポリシーの異なる値でプロセスを実行することは無害です。


  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: IntensiveWakeUpThrottlingEnabled
  - GP 名: IntensiveWakeUpThrottling 機能を制御する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: IntensiveWakeUpThrottlingEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: IntensiveWakeUpThrottlingEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### InternetExplorerIntegrationEnhancedHangDetection

  #### Internet Explorer モードの拡張ハング検出を構成する

  
  
  #### サポートされているバージョン:

  - Windows での 84 以降

  #### 説明

  拡張ハング検出は、スタンドアロンの Internet Explorer が使用するものよりも、Internet Explorer モードでの Web ページのハングを検出するより詳細なアプローチです。 ハングした Web ページが検出されると、ブラウザーには緩和策が適用され、ブラウザーの残りの部分がハングしないようにします。

この設定では、Web サイトに互換性のない問題が発生した場合に備えて、拡張ハング検出の使用を構成することができます。 Internet Explorer モードでは、「(Web サイト) が応答していません」などの通知が表示され、スタンドアロンの Internet Explorer では表示されない場合にのみ、このポリシーを無効にすることをお勧めします。

この設定は、"IEMode" に設定されている [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) と、一覧に少なくとも 1 つのエントリがある [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist) ポリシーと連動します。

このポリシーを [有効] に設定するか、構成しない場合、Internet Explorer モードで実行中の Web サイトでは、拡張ハング検出が使用されます。

このポリシーを [無効] に設定すると、拡張ハング検出が無効になり、ユーザーは基本的な Internet Explorer ハング検出動作を取得します。

Internet Explorer モードの詳細については、「[https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)」を参照してください

ポリシー オプション マッピング:

* 無効 (0) = 拡張ハング検出が無効になっている

* 有効 (1) = 拡張ハング検出が有効になっている

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: InternetExplorerIntegrationEnhancedHangDetection
  - GP 名: Internet Explorer モードの拡張ハング検出を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: InternetExplorerIntegrationEnhancedHangDetection
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### InternetExplorerIntegrationLevel

  #### Internet Explorer 統合を構成する

  
  
  #### サポートされているバージョン:

  - Windows での 77 以降

  #### 説明

  Internet Explorer モードで最適なエクスペリエンスを構成する方法については、「[https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)」を参照してください

ポリシー オプション マッピング:

* None (0) = None

* IEMode (1) = Internet Explorer モード

* NeedIE (2) = Internet Explorer 11

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: InternetExplorerIntegrationLevel
  - GP 名: Internet Explorer 統合を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: InternetExplorerIntegrationLevel
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### InternetExplorerIntegrationLocalFileAllowed

  #### Internet Explorer モードでローカル ファイルを起動できるようにする

  
  
  #### サポートされているバージョン:

  - Windows での 88 以降

  #### 説明

  このポリシーは、コマンド ラインで指定されたローカル ファイルを使用して Microsoft Edge を Internet Explorer モードで起動するために使用される --ie-mode-file-url コマンド ライン引数の可用性を制御します。

この設定は、次と連携して機能します。[InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) は「IEMode」に設定されます。

このポリシーを true に設定するか、構成しない場合、ユーザーは --ie-mode-file-url コマンド ライン引数を使用して、Internet Explorer モードでローカル ファイルを起動できます。

このポリシーを false に設定する場合、ユーザーは --ie-mode-file-url コマンド ライン引数を使用して、Internet Explorer モードでローカル ファイルを起動できません。

Internet Explorer モードの詳細については、「[https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)」を参照してください

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: InternetExplorerIntegrationLocalFileAllowed
  - GP 名: Internet Explorer モードでローカル ファイルを起動できるようにする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: InternetExplorerIntegrationLocalFileAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### InternetExplorerIntegrationLocalFileExtensionAllowList

  #### Internet Explorer モードのローカル ファイルのファイル拡張子許可リストを開く

  
  
  #### サポートされているバージョン:

  - Windows での 88 以降

  #### 説明

  このポリシーは、ファイル拡張子に基づいて、どの file:// URL を Internet Explorer モードで起動できるかを制限します。

この設定は、次と連携して機能します。[InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) は「IEMode」に設定されます。

file:// URL が Internet Explorer モードでの起動を要求された場合、URL を Internet Explorer モードで起動できるようにするには、URL のファイル拡張子がこのリストに存在する必要があります。 Internet Explorer モードで開くことがブロックされている URL は、代わりに Edge モードで開きます。

このポリシーを特別な値「*」に設定するか、構成しない場合、すべてのファイル拡張子が許可されます。

Internet Explorer モードの詳細については、「[https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)」を参照してください

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: InternetExplorerIntegrationLocalFileExtensionAllowList
  - GP 名: Internet Explorer モードのローカル ファイルのファイル拡張子許可リストを開く
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\InternetExplorerIntegrationLocalFileExtensionAllowList
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\InternetExplorerIntegrationLocalFileExtensionAllowList\1 = ".mht"
SOFTWARE\Policies\Microsoft\Edge\InternetExplorerIntegrationLocalFileExtensionAllowList\2 = ".pdf"
SOFTWARE\Policies\Microsoft\Edge\InternetExplorerIntegrationLocalFileExtensionAllowList\3 = ".vsdx"

```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### InternetExplorerIntegrationLocalFileShowContextMenu

  #### Internet Explorer モードでリンクを開くためのコンテキスト メニューを表示する

  
  
  #### サポートされているバージョン:

  - Windows での 88 以降

  #### 説明

  このポリシーは、file:// links のコンテキスト メニューの [新しい Internet Explorer モード タブでリンクを開く] オプションの表示を制御します。

この設定は、次と連携して機能します。[InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) は「IEMode」に設定されます。

このポリシーを true に設定すると、「新しい Internet Explorer モード タブでリンクを開く」コンテキスト メニュー項目が file:// リンクで使用できるようになります。

このポリシーを false に設定するか、構成しない場合、コンテキスト メニュー項目は追加されません。

Internet Explorer モードの詳細については、「[https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)」を参照してください

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: InternetExplorerIntegrationLocalFileShowContextMenu
  - GP 名: Internet Explorer モードでリンクを開くためのコンテキスト メニューを表示する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: InternetExplorerIntegrationLocalFileShowContextMenu
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### InternetExplorerIntegrationSiteList

  #### エンタープライズ モード サイト一覧を構成する

  
  
  #### サポートされているバージョン:

  - Windows での 78 以降

  #### 説明

  Internet Explorer モードで最適なエクスペリエンスを構成する方法については、「[https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)」を参照してください

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: InternetExplorerIntegrationSiteList
  - GP 名: エンタープライズ モード サイト一覧を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: InternetExplorerIntegrationSiteList
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"https://internal.contoso.com/sitelist.xml"
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### InternetExplorerIntegrationSiteRedirect

  #### Internet Explorer モード ページから起動したときに未構成サイトへの「ページ内」ナビゲーションの動作を指定する

  
  
  #### サポートされているバージョン:

  - Windows での 81 以降

  #### 説明

  “ページ内“ ナビゲーションは、現在のページのリンク、スクリプト、またはフォームから開始されます。 また、前回の“ページ内“ ナビゲーションの試行のサーバー側リダイレクトにもなります。 逆に、ユーザーはブラウザーの制御で、現在のページから独立した “ページ内“ ではないナビゲーションを開始することができます。 たとえば、アドレス バー、[戻る] ボタン、またはお気に入りリンクを使用する場合です。

この設定では、Internet Explorer モードで読み込んだページから未構成のサイト (エンタープライズ モードのサイト一覧に構成されていないサイト) への移動を Microsoft Edge に切り替えるか、Internet Explorer モードのままにするかどうかを指定することができます。

この設定は、"IEMode" に設定されている [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) と、一覧に少なくとも 1 つのエントリがある [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist) ポリシーと連動します。

このポリシーを無効にしているか、構成していない場合、Internet Explorer モードで開くように構成されたサイトのみが、そのモードで開きます。 Internet Explorer モードで開くように構成されていないサイトは、Microsoft Edge にリダイレクトされます。

このポリシーを [既定値] に設定している場合、Internet Explorer モードで開くように構成されたサイトのみが、そのモードで開きます。 Internet Explorer モードで開くように構成されていないサイトは、Microsoft Edge にリダイレクトされます。

このポリシーを [AutomaticNavigationsOnly] に設定している場合、未構成サイトへのすべての自動ナビゲーション （302 リダイレクトなど） が Internet Explorer モードで保持されることを除いて、既定のエクスペリエンスが取得されます。

このポリシーを [AllInPageNavigations] に設定している場合、IE モードで読み込まれたページから未構成サイトへのすべてのナビゲーションは、Internet Explorer モードで保持されます (推奨しません)。

Internet Explorer モードの詳細については、「[https://go.microsoft.com/fwlink/?linkid=2105106](https://go.microsoft.com/fwlink/?linkid=2105106)」を参照してください

ポリシー オプション マッピング:

* 既定値 (0) = 既定値

* AutomaticNavigationsOnly (1) = Internet Explorer モードでの自動的に行ったナビゲーションのみを保持する

* AllInPageNavigations (2) = Internet Explorer モードですべてのページ内ナビゲーションを保持する

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: InternetExplorerIntegrationSiteRedirect
  - GP 名: Internet Explorer モード ページから起動したときに未構成サイトへの「ページ内」ナビゲーションの動作を指定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: InternetExplorerIntegrationSiteRedirect
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### InternetExplorerIntegrationTestingAllowed

  #### Internet Explorer モードテストを許可する

  
  
  #### サポートされているバージョン:

  - Windows での 86 以降

  #### 説明

  このポリシーでは、ユーザーが Microsoft Edge で Internet Explorer モードのタブを開き、Internet Explorer モードでアプリケーションをテストできるようにします。

ユーザーは、[Open sites in Internet Explorer mode] (Internet Explorer モードでサイトを開く) を選択することで、[その他のツール] メニューからこの操作を行うことができます。

さらに、[Open sites in Edge mode] (Microsoft Edge モードでサイトを開く) オプションを使用すると、サイトの一覧からアプリケーションを削除することなく最新のブラウザーでアプリケーションをテストすることができます。

この設定は、"IEMode" に設定されている [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) と、一覧に少なくとも 1 つのエントリがある [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist) ポリシーと連動します。

このポリシーを有効にすると、[その他のツール] の下に [Open sites in Internet Explorer mode] (Internet Explorer モードでサイトを開く) というオプションが表示されます。 ユーザーは、このタブ上で Internet Explorer モードを使用してサイトを表示することができます。サイト一覧からサイトを削除することなく最新のブラウザーでサイトをテストする場合に役立つように、[Open sites in Edge mode] (Microsoft Edge モードでサイトを開く) という別のオプションも [その他のツール] の下に表示されます。

このポリシーを無効にしているか、または構成していない場合、[その他のツール] メニューの [Open sites in Internet Explorer mode] (Internet Explorer モードでサイトを開く) と [Open sites in Edge mode] (Microsoft Edge モードでサイトを開く) のオプションは表示されなくなります。 ただし、ユーザーはこれらのオプションを --ie-mode-test フラグを使用して構成することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: InternetExplorerIntegrationTestingAllowed
  - GP 名: Internet Explorer モードテストを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: InternetExplorerIntegrationTestingAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### IntranetRedirectBehavior

  #### イントラネット リダイレクトの動作

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 88 以降

  #### 説明

  このポリシーは、DNS の傍受チェックを介したイントラネット リダイレクトの動作を構成します。 これらのチェックは、ブラウザーが不明なホスト名をリダイレクトするプロキシを介しているかどうかを検出します。

このポリシーが構成されていない場合、ブラウザーは DNS の傍受チェックとイントラネット リダイレクトの提案の既定の動作を使用します。 M88 では、これらは既定で有効になっていますが、将来のリリースでは既定で無効になる予定です。

[DNSInterceptionChecksEnabled](#dnsinterceptionchecksenabled) は、DNS の傍受チェックも無効にする可能性のある関連ポリシーです。 ただし、このポリシーはより柔軟なバージョンであり、イントラネット リダイレクト情報バーを個別に制御する可能性があり、将来拡張される可能性があります。
[DNSInterceptionChecksEnabled](#dnsinterceptionchecksenabled) またはこのポリシーのいずれかが傍受チェックを無効にするように要求すると、チェックは無効になります。
このポリシーによって DNS の傍受チェックが無効になっているが、[GoToIntranetSiteForSingleWordEntryInAddressBar](#gotointranetsiteforsinglewordentryinaddressbar) が有効になっている場合でも、シングル ワード クエリはイントラネット ナビゲーションになります。

ポリシー オプション マッピング:

* Default (0) = 既定のブラウザー動作を使用します。

* DisableInterceptionChecksDisableInfobar (1) = DNS の傍受チェックと「http://intranetsite/」情報バーを無効にします。

* DisableInterceptionChecksEnableInfobar (2) = DNS の傍受チェックと「http://intranetsite/」情報バーを無効にします。

* EnableInterceptionChecksEnableInfobar (3) = DNS の傍受チェックと「http://intranetsite/」情報バーを有効にします。

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: IntranetRedirectBehavior
  - GP 名: イントラネット リダイレクトの動作
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: IntranetRedirectBehavior
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: IntranetRedirectBehavior
  - サンプル値:
``` xml
<integer>1</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### IsolateOrigins

  #### 特定のオリジンでのサイトの分離を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  独自のプロセスで分離して実行するオリジンを指定します。

このポリシーは、サブドメインで指定されたオリジンも分離します。たとえば https://contoso.com/ を指定すると、https://foo.contoso.com/ が https://contoso.com/ サイトの一部として分離されます。

このポリシーを有効にしている場合、コンマで区切られた一覧に含まれる指定されたオリジンは、それぞれ独自のプロセスで実行されます。

このポリシーを無効にしている場合、“IsolateOrigins“ と “SitePerProcess“ の両方の機能が無効になります。 ユーザーは、コマンドライン フラグを使用して手動で “IsolateOrigins“ ポリシーを有効にすることができます。

このポリシーを構成していない場合、ユーザーはこの設定を変更することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: IsolateOrigins
  - GP 名: 特定のオリジンでのサイトの分離を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: IsolateOrigins
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"https://contoso.com/,https://fabrikam.com/"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: IsolateOrigins
  - サンプル値:
``` xml
<string>https://contoso.com/,https://fabrikam.com/</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### LocalProvidersEnabled

  #### ローカル プロバイダーからのおすすめを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 83 以降

  #### 説明

  お気に入りや閲覧の履歴などのデバイス上の提案プロバイダー (ローカル プロバイダー) からの提案を、Microsoft Edge のアドレス バーや自動提案一覧で許可します。

このポリシーを有効にしている場合、ローカル プロバイダーからの提案が使用されます。

このポリシーを無効にしている場合、ローカル プロバイダーからの提案は使用されません。 ローカルの履歴やお気に入りの提案は表示されません。

このポリシーを構成していない場合、ローカル プロバイダーからの提案は許可されますが、ユーザーは設定トグルを使用して変更することができます。

この機能を無効にするポリシーが適用されている場合、一部の機能が使用できない場合があります。 たとえば、[SavingBrowserHistoryDisabled](#savingbrowserhistorydisabled) ポリシーを有効にしている場合、閲覧の履歴の提案は使用することができません。

このポリシーの適用を完了させるには、ブラウザーの再起動が必要です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: LocalProvidersEnabled
  - GP 名: ローカル プロバイダーからのおすすめを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: LocalProvidersEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: LocalProvidersEnabled
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ManagedFavorites

  #### お気に入りを構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  管理されているお気に入りの一覧を構成します。

このポリシーは、お気に入りの一覧を作成します。 それぞれのお気に入りには、お気に入りの名前とターゲットを保持する “name“ と “url“ というキーが含まれています。 “url“ キーを持たないお気に入りを定義することでサブフォルダーを構成することができますが、上記で定義したお気に入りの一覧を含む追加の “子“ キーを持つことで、サブフォルダを構成することができます (そのうちのいくつかは再びフォルダーになる可能性があります)。 Microsoft Edge では、不完全な URL がアドレス バーを介して送信されたかのように修正されます。たとえば、"microsoft.com" は "https://microsoft.com/" になります。

これらのお気に入りは、ユーザーが変更することができないフォルダーに配置されます (ただし、ユーザーはお気に入り バーからそれを非表示にすることができます)。 既定では、フォルダー名は “管理されているお気に入り“ となっていますが、お気に入りの一覧に “toplevel_name“ というキーを含む辞書を追加し、目的のフォルダー名を値として追加することで、フォルダー名を変更することができます。

管理されているお気に入りはユーザー アカウントに同期されず、拡張機能が変更することはできません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Dictionary

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ManagedFavorites
  - GP 名: お気に入りを構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ManagedFavorites
  - 値の種類: REG_SZ

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\ManagedFavorites = [
  {
    "toplevel_name": "My managed favorites folder"
  }, 
  {
    "name": "Microsoft", 
    "url": "microsoft.com"
  }, 
  {
    "name": "Bing", 
    "url": "bing.com"
  }, 
  {
    "children": [
      {
        "name": "Microsoft Edge Insiders", 
        "url": "www.microsoftedgeinsider.com"
      }, 
      {
        "name": "Microsoft Edge", 
        "url": "www.microsoft.com/windows/microsoft-edge"
      }
    ], 
    "name": "Microsoft Edge links"
  }
]
```

  ##### コンパクト サンプル値:

  ```
  SOFTWARE\Policies\Microsoft\Edge\ManagedFavorites = [{"toplevel_name": "My managed favorites folder"}, {"name": "Microsoft", "url": "microsoft.com"}, {"name": "Bing", "url": "bing.com"}, {"children": [{"name": "Microsoft Edge Insiders", "url": "www.microsoftedgeinsider.com"}, {"name": "Microsoft Edge", "url": "www.microsoft.com/windows/microsoft-edge"}], "name": "Microsoft Edge links"}]
  ```
  

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ManagedFavorites
  - サンプル値:
``` xml
<key>ManagedFavorites</key>
<array>
  <dict>
    <key>toplevel_name</key>
    <string>My managed favorites folder</string>
  </dict>
  <dict>
    <key>name</key>
    <string>Microsoft</string>
    <key>url</key>
    <string>microsoft.com</string>
  </dict>
  <dict>
    <key>name</key>
    <string>Bing</string>
    <key>url</key>
    <string>bing.com</string>
  </dict>
  <dict>
    <key>children</key>
    <array>
      <dict>
        <key>name</key>
        <string>Microsoft Edge Insiders</string>
        <key>url</key>
        <string>www.microsoftedgeinsider.com</string>
      </dict>
      <dict>
        <key>name</key>
        <string>Microsoft Edge</string>
        <key>url</key>
        <string>www.microsoft.com/windows/microsoft-edge</string>
      </dict>
    </array>
    <key>name</key>
    <string>Microsoft Edge links</string>
  </dict>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ManagedSearchEngines

  #### 検索エンジンを管理する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  最大 10 個の検索エンジンを一覧に設定でき、そのうちの 1 つは既定の検索エンジンとしてマークする必要があります。
エンコードを指定する必要はありません。 Microsoft Edge 80 以降では、suggest_url と image_search_url パラメーターはオプションです。 オプションのパラメーターである image_search_post_params (コンマで区切られた名前と値のペアで構成されています) は、Microsoft Edge 80 から利用可能です。

Microsoft Edge 83 以降では、allow_search_engine_discovery というオプションのパラメーターを使用して、検索エンジンの検出を有効にすることができます。 このパラメーターは、一覧の最初の項目である必要があります。 allow_search_engine_discovery を指定していない場合、検索エンジンの検出は既定で無効になります。 Microsoft Edge 84 以降、このポリシーは、検索プロバイダーの検出を許可するために推奨されるポリシーとして設定できます。 省略可能なパラメーター allow_search_engine_discovery を追加する必要はありません。

このポリシーを有効にしている場合、ユーザーは一覧で任意の検索エンジンを追加、削除、または変更することができなくなります。 ユーザーは、一覧で任意の検索エンジンを既定の検索エンジンとして設定することができます。

このポリシーを無効にしているか、構成していない場合、ユーザーは検索エンジンの一覧を必要に応じて変更することができます。

[DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) ポリシーが設定されている場合、このポリシー (ManagedSearchEngines) は無視されます。 このポリシーの適用を完了するには、ユーザーはブラウザーを再起動する必要があります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Dictionary

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ManagedSearchEngines
  - GP 名: 検索エンジンを管理する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ManagedSearchEngines
  - 値の種類: REG_SZ

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\ManagedSearchEngines = [
  {
    "allow_search_engine_discovery": true
  }, 
  {
    "is_default": true, 
    "keyword": "example1.com", 
    "name": "Example1", 
    "search_url": "https://www.example1.com/search?q={searchTerms}", 
    "suggest_url": "https://www.example1.com/qbox?query={searchTerms}"
  }, 
  {
    "image_search_post_params": "content={imageThumbnail},url={imageURL},sbisrc={SearchSource}", 
    "image_search_url": "https://www.example2.com/images/detail/search?iss=sbiupload", 
    "keyword": "example2.com", 
    "name": "Example2", 
    "search_url": "https://www.example2.com/search?q={searchTerms}", 
    "suggest_url": "https://www.example2.com/qbox?query={searchTerms}"
  }, 
  {
    "encoding": "UTF-8", 
    "image_search_url": "https://www.example3.com/images/detail/search?iss=sbiupload", 
    "keyword": "example3.com", 
    "name": "Example3", 
    "search_url": "https://www.example3.com/search?q={searchTerms}", 
    "suggest_url": "https://www.example3.com/qbox?query={searchTerms}"
  }, 
  {
    "keyword": "example4.com", 
    "name": "Example4", 
    "search_url": "https://www.example4.com/search?q={searchTerms}"
  }
]
```

  ##### コンパクト サンプル値:

  ```
  SOFTWARE\Policies\Microsoft\Edge\ManagedSearchEngines = [{"allow_search_engine_discovery": true}, {"is_default": true, "keyword": "example1.com", "name": "Example1", "search_url": "https://www.example1.com/search?q={searchTerms}", "suggest_url": "https://www.example1.com/qbox?query={searchTerms}"}, {"image_search_post_params": "content={imageThumbnail},url={imageURL},sbisrc={SearchSource}", "image_search_url": "https://www.example2.com/images/detail/search?iss=sbiupload", "keyword": "example2.com", "name": "Example2", "search_url": "https://www.example2.com/search?q={searchTerms}", "suggest_url": "https://www.example2.com/qbox?query={searchTerms}"}, {"encoding": "UTF-8", "image_search_url": "https://www.example3.com/images/detail/search?iss=sbiupload", "keyword": "example3.com", "name": "Example3", "search_url": "https://www.example3.com/search?q={searchTerms}", "suggest_url": "https://www.example3.com/qbox?query={searchTerms}"}, {"keyword": "example4.com", "name": "Example4", "search_url": "https://www.example4.com/search?q={searchTerms}"}]
  ```
  

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ManagedSearchEngines
  - サンプル値:
``` xml
<key>ManagedSearchEngines</key>
<array>
  <dict>
    <key>allow_search_engine_discovery</key>
    <true/>
  </dict>
  <dict>
    <key>is_default</key>
    <true/>
    <key>keyword</key>
    <string>example1.com</string>
    <key>name</key>
    <string>Example1</string>
    <key>search_url</key>
    <string>https://www.example1.com/search?q={searchTerms}</string>
    <key>suggest_url</key>
    <string>https://www.example1.com/qbox?query={searchTerms}</string>
  </dict>
  <dict>
    <key>image_search_post_params</key>
    <string>content={imageThumbnail},url={imageURL},sbisrc={SearchSource}</string>
    <key>image_search_url</key>
    <string>https://www.example2.com/images/detail/search?iss=sbiupload</string>
    <key>keyword</key>
    <string>example2.com</string>
    <key>name</key>
    <string>Example2</string>
    <key>search_url</key>
    <string>https://www.example2.com/search?q={searchTerms}</string>
    <key>suggest_url</key>
    <string>https://www.example2.com/qbox?query={searchTerms}</string>
  </dict>
  <dict>
    <key>encoding</key>
    <string>UTF-8</string>
    <key>image_search_url</key>
    <string>https://www.example3.com/images/detail/search?iss=sbiupload</string>
    <key>keyword</key>
    <string>example3.com</string>
    <key>name</key>
    <string>Example3</string>
    <key>search_url</key>
    <string>https://www.example3.com/search?q={searchTerms}</string>
    <key>suggest_url</key>
    <string>https://www.example3.com/qbox?query={searchTerms}</string>
  </dict>
  <dict>
    <key>keyword</key>
    <string>example4.com</string>
    <key>name</key>
    <string>Example4</string>
    <key>search_url</key>
    <string>https://www.example4.com/search?q={searchTerms}</string>
  </dict>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### MaxConnectionsPerProxy

  #### プロキシ サーバーへの同時接続の最大数

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  プロキシ サーバーへの同時接続の最大数を指定します。

プロキシ サーバーの中には、クライアントごとの同時接続数が多い場合に処理することができないものがあります。このポリシーをより低い値に設定することで、この問題を解決することができます。

このポリシーの値は、100 以下で 6 以上である必要があります。 既定値は 32 です。

一部の Web アプリは、ハングしている GET で多くの接続を消費することが知られています。最大接続数を 32 以下に下げると、こういった種類の Web アプリがあまりにも多く開かれている場合、ブラウザー ネットワークのハングにつながる場合があります。

このポリシーを構成していない場合、既定値 (32) が使用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: MaxConnectionsPerProxy
  - GP 名: プロキシ サーバーへの同時接続の最大数
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: MaxConnectionsPerProxy
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000020
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: MaxConnectionsPerProxy
  - サンプル値:
``` xml
<integer>32</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### MediaRouterCastAllowAllIPs

  #### Google Cast がすべての IP アドレスのキャスト デバイスに接続できるようにする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーを有効にしている場合、Google Cast は RFC1918/RFC4193 のプライベート アドレスだけでなく、すべての IP アドレスのキャスト デバイスに接続できるようになります。

このポリシーを無効にしている場合、RFC1918/RFC4193 のプライベート アドレスのキャスト デバイスに Google Cast を制限します。

このポリシーを構成していない場合、CastAllowAllIPs 機能を有効にしない限り、Google Cast は RFC1918/RFC4193 のプライベート アドレス上の Cast デバイスにのみ接続します。

[EnableMediaRouter](#enablemediarouter) ポリシーが無効になっている場合、このポリシーには何の効果もありません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: MediaRouterCastAllowAllIPs
  - GP 名: Google Cast がすべての IP アドレスのキャスト デバイスに接続できるようにする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: MediaRouterCastAllowAllIPs
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: MediaRouterCastAllowAllIPs
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### MetricsReportingEnabled

  #### 使用状況とクラッシュ関連のデータレポートを有効にする (廃止)

  
  >不使用: このポリシーは廃止されており、Microsoft Edge 88 以降は機能しません。
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降、88 まで

  #### 説明

  このポリシーはサポートされなくなりました。 このポリシーは [DiagnosticData](#diagnosticdata) に置き換えられ (Windows 7、Windows 8、および macOS)、Windows 10 ([https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)) でテレメトリが許可されます。

このポリシーによって、Microsoft Edge の使用状況およびクラッシュに関連するデータの Microsoft への送信が有効になります。

使用状況およびクラッシュに関連するデータのレポートを Microsoft に送信するには、このポリシーを有効にします。 このデータを Microsoft に送信しない場合は、このポリシーを無効にします。 いずれの場合でも、ユーザーがこの設定を変更または上書きすることはできません。

Windows 10 では、このポリシーを構成していない場合、Microsoft Edge は Windows 診断データの設定を既定値として設定します。 このポリシーを有効にしている場合、Windows 診断データの設定が［拡張］または［完全］に設定されている場合にのみ、Microsoft Edge は使用状況データを送信します。 このポリシーを無効にしている場合、Microsoft Edge は使用状況データを送信しません。 クラッシュに関連するデータは、Windows 診断データの設定に基づいて送信されます。 Windows 診断データの設定については、「[https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)」を参照してください

Windows 7、Windows 8、macOS では、このポリシーによって、使用状況とクラッシュに関連するデータの送信が制御されます。 このポリシーを構成しない場合、Microsoft Edge は既定でユーザーの設定に従います。

このポリシーを有効にするには、[SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices) を有効に設定する必要があります。 [MetricsReportingEnabled](#metricsreportingenabled) または [SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices) が構成されていないか、または無効になっている場合は、このデータは Microsoft に送信されません。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンス、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンス、もしくは MDM を使用するか MDM を使用してドメインに参加する macOS インスタンスでのみ利用可能です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - 一意の GP 名: MetricsReportingEnabled
  - GP 名: 使用状況とクラッシュ関連のデータレポートを有効にする (廃止)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: MetricsReportingEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: MetricsReportingEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### NativeWindowOcclusionEnabled

  #### ネイティブ ウィンドウ オクルージョンを有効にする

  
  
  #### サポートされているバージョン:

  - Windows での 84 以降

  #### 説明

  Microsoft Edge のネイティブ ウィンドウ オクルージョンを有効にします。

この設定を有効にしている場合、CPU と電力の消費を削減するために、Microsoft Edge はウィンドウが他のウィンドウに覆われていることを検出したときにピクセルの描画作業を中断します。

この設定を無効にしている場合、ウィンドウが他のウィンドウに覆われていることを Microsoft Edge は検出しません。

このポリシーが設定されていない場合、ウィンドウが覆われていることについての検出は有効になります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NativeWindowOcclusionEnabled
  - GP 名: ネイティブ ウィンドウ オクルージョンを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: NativeWindowOcclusionEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### NavigationDelayForInitialSiteListDownloadTimeout

  #### エンタープライズ モード サイト一覧のタブ ナビゲーションの遅延時間を設定する

  
  
  #### サポートされているバージョン:

  - Windows での 84 以降

  #### 説明

  ブラウザーが最初のエンタープライズ モード サイト一覧をダウンロードするまで、Microsoft Edge タブがナビケートを待機する時間 (秒単位) を設定できます。

この設定は、[IEMode] に設定されている [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel)、一覧に少なくとも 1 つのエントリがある [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist) ポリシー、[対象のすべてのナビゲーション] (1) に設定されている [DelayNavigationsForInitialSiteListDownload](#delaynavigationsforinitialsitelistdownload) と連動します。

タブを使用すると、エンタープライズ モード サイト一覧をダウンロードするためのタイムアウト時間を超えることはありません。 時間切れになってもブラウザーがエンタープライズ モード サイト一覧のダウンロードを完了していない場合、Microsoft Edge タブは引き続きナビゲートします。 タイムアウトの値は、20 秒以下、1 秒以上にする必要があります。

このポリシーのタイムアウトを既定の 2 秒より大きい値に設定すると、ユーザーには 2 秒後に情報バーが表示されます。 情報バーには、ユーザーがエンタープライズ モード サイト一覧のダウンロードを完了するまでの待機を終了するボタンがあります。

このポリシーを構成していない場合、既定のタイムアウトの 2 秒が使用されます。 この既定値は、将来変更される可能性があります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NavigationDelayForInitialSiteListDownloadTimeout
  - GP 名: エンタープライズ モード サイト一覧のタブ ナビゲーションの遅延時間を設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: NavigationDelayForInitialSiteListDownloadTimeout
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x0000000a
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### NetworkPredictionOptions

  #### ネットワーク予測を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ネットワーク予測を有効にし、ユーザーがこの設定を変更できないようにします。

このポリシーは、DNS のプリフェッチ、TCP および SSL のプリコネクション、Web ページのプリレンダリングを制御します。

このポリシーを構成していない場合、ネットワーク予測が有効になりますが、ユーザーはこの設定を変更することができます。

ポリシー オプション マッピング:

* NetworkPredictionAlways (0) = 任意のネットワーク接続のネットワーク アクションを予測する

* NetworkPredictionWifiOnly (1) = サポートされていません。この値を使用すると、[ネットワーク接続でのネットワークアクションを予測する] (0) が設定されたものとして扱われます。

* NetworkPredictionNever (2) = 任意のネットワーク接続のネットワーク アクションを予測しない

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NetworkPredictionOptions
  - GP 名: ネットワーク予測を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: NetworkPredictionOptions
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: NetworkPredictionOptions
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### NonRemovableProfileEnabled

  #### ユーザーが自分の職場または学校アカウントで自動的にログインする既定のプロファイルを常に持つかどうかを設定する

  
  
  #### サポートされているバージョン:

  - Windows での 78 以降

  #### 説明

  このポリシーでは、ユーザーが自分の職場または学校アカウントで自動的にサインインした Microsoft Edge プロファイルを削除できるかどうかを決定します。

このポリシーを有効にしている場合、Windows 上のユーザーの職場または学校アカウントを使用して、削除不可のプロファイルが作成されます。 このプロファイルは、サインアウトしたり削除したりすることができません。 プロファイルがオンプレミスのアカウントまたは OS サインイン アカウントと一致する Azure AD アカウントでサインインしている場合にのみ、プロファイルは非リムーバブルになります。

このポリシーを無効にしているか、構成していない場合、Windows 上のユーザーの職場または学校のアカウントを使用して自動的にサインインしたプロファイルは、ユーザーによってサインアウトしたり、削除したりすることができます。

ブラウザーのサインインを構成する場合は、[BrowserSignin](#browsersignin) ポリシーを使用します。

このポリシーは、Microsoft Active Directory ドメインに参加している Windows インスタンスか、デバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンスでのみ利用可能です。

Microsoft Edge 89 以降、同期が無効になっている既存のオンプレミス プロファイルが存在し、コンピューターがハイブリッドに参加している場合は、新しい非リムーバブルの Azure AD プロファイルを作成する代わりにオンプレミス プロファイルを Azure AD プロファイルに自動アップグレードして非リムーバブルにします。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: NonRemovableProfileEnabled
  - GP 名: ユーザーが自分の職場または学校アカウントで自動的にログインする既定のプロファイルを常に持つかどうかを設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: NonRemovableProfileEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### OverrideSecurityRestrictionsOnInsecureOrigin

  #### セキュリティで保護されていないオリジンのセキュリティ制限が適用される場所を制御する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  安全でないオリジンに対するセキュリティ制限が適用されないオリジン (URL) やホスト名のパターン ("*.contoso.com" など) の一覧を指定します。

このポリシーでは、TLS を展開できないレガシ アプリケーションの許可されたオリジンを指定したり、内部 Web 開発用のステージング サーバーをセットアップしたりすることができます。これにより、開発者はステージング サーバーに TLS を展開することなく、安全なコンテキストを必要とする機能をテストすることができます。 また、このポリシーにより、オリジンがオムニボックスに "セキュリティ保護なし" と表示されることも防止することができます。

このポリシーで URL の一覧を設定することは、コマンドライン フラグ “--unsafely-treat-insecure-origin-as-secure“ を同じ URL のコンマ区切りリストに設定する場合と同じ効果があります。 このポリシーを有効にしている場合、このポリシーはコマンドライン フラグを上書きします。

安全なコンテキストの詳細については、「https://www.w3.org/TR/secure-contexts/」を参照してください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: OverrideSecurityRestrictionsOnInsecureOrigin
  - GP 名: セキュリティで保護されていないオリジンのセキュリティ制限が適用される場所を制御する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\OverrideSecurityRestrictionsOnInsecureOrigin
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\OverrideSecurityRestrictionsOnInsecureOrigin\1 = "http://testserver.contoso.com/"
SOFTWARE\Policies\Microsoft\Edge\OverrideSecurityRestrictionsOnInsecureOrigin\2 = "*.contoso.com"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: OverrideSecurityRestrictionsOnInsecureOrigin
  - サンプル値:
``` xml
<array>
  <string>http://testserver.contoso.com/</string>
  <string>*.contoso.com</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PaymentMethodQueryEnabled

  #### 利用可能な支払い方法について Web サイトがクエリを実行することを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 80 以降

  #### 説明

  ユーザーが支払い方法を保存しているかどうかを Web サイトが確認できるかどうかを設定することができます。

このポリシーを無効にしている場合、PaymentRequest.canMakePayment またはPaymentRequest.hasEnrolledInstrument API を使用している Web サイトは、使用可能な支払い方法がないことを通知されます。

このポリシーを有効にしているか、設定していない場合、Web サイトはユーザーが支払い方法を保存しているかどうかを確認することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PaymentMethodQueryEnabled
  - GP 名: 利用可能な支払い方法について Web サイトがクエリを実行することを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: PaymentMethodQueryEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PaymentMethodQueryEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PersonalizationReportingEnabled

  #### Microsoft に閲覧履歴を送信して、広告、検索、ニュースのカスタマイズを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 80 以降

  #### 説明

  このポリシーは、Microsoft がユーザーの Microsoft Edge の閲覧の履歴を収集して、広告、検索、ニュース、その他の Microsoft サービスをカスタマイズするために使用することを防止します。

この設定は、Microsoft アカウントを持つユーザーのみが使用できます。 この設定は、お子様のアカウントやエンタープライズ アカウントでは使用できません。

このポリシーを無効にしている場合、ユーザーは設定を変更したり上書きしたりすることができなくなります。 このポリシーが有効になっているか、または構成されていない場合、Microsoft Edge は既定でユーザーの設定に従います。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PersonalizationReportingEnabled
  - GP 名: Microsoft に閲覧履歴を送信して、広告、検索、ニュースのカスタマイズを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: PersonalizationReportingEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PersonalizationReportingEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PinningWizardAllowed

  #### タスク バーへのピン留めウィザードを許可する

  
  
  #### サポートされているバージョン:

  - Windows での 80 以降

  #### 説明

  Microsoft Edge では、タスク バーへのピン留めウィザードを使用して、ユーザーが提案されたサイトをタスク バーにピン留めすることができます。 タスクバーへのピン留めウィザード機能は既定で有効になっており、ユーザーは [設定] と [その他] メニューからアクセスすることができます。

このポリシーを有効にしているか、構成していない場合、ユーザーは [設定] と [その他] メニューからタスクバーへのピン留めウィザードを呼び出すことができます。 ウィザードは、プロトコルの起動を介して呼び出すこともできます。

このポリシーを無効にしている場合、タスクバーへのピン留めウィザードはメニューで無効になり、プロトコルの起動を介して呼び出すことはできなくなります。

タスクバーへのピン留めウィザードを有効または無効にするユーザー設定は、利用できません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PinningWizardAllowed
  - GP 名: タスク バーへのピン留めウィザードを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: PinningWizardAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### ProactiveAuthEnabled

  #### プロアクティブ認証を有効にする (非推奨)

  >非推奨: このポリシーは推奨されなくなっています。 現在はサポートされていますが、将来のリリースで廃止されます。
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーは、ブラウザーのサインインとは独立して機能しないため、非推奨となりました。 Microsoft Edge バージョン 91 では機能しません。 ブラウザーのサインインを構成する場合は、[BrowserSignin](#browsersignin) ポリシーを使用します。

Microsoft Edge でプロアクティブ認証を有効にするかどうかを構成できます。

このポリシーを有効にすると、Microsoft Edge は、ブラウザーにサインインしているアカウントを使用して、Web サイトやサービスに対するシームレスな認証を試みます。

このポリシーを無効にすると、Microsoft Edge は、シングルサインオン (SSO) を使って、Web サイトまたはサービスに対する認証を試みることはありません。 エンタープライズの新しいタブ ページなどの認証されたエクスペリエンスは機能しません (たとえば、最近使用した Office ドキュメントとおすすめの Office ドキュメントは使用できません)。

このポリシーを構成していない場合、プロアクティブ認証がオンになります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ProactiveAuthEnabled
  - GP 名: プロアクティブ認証を有効にする (非推奨)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ProactiveAuthEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ProactiveAuthEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PromotionalTabsEnabled

  #### フルタブのプロモーション コンテンツを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  フルタブのプロモーションや教育用のコンテンツの表示を制御します。 この設定では、ユーザーが Microsoft Edge にサインインしたり、既定のブラウザーを選択したり、製品の機能についての情報を確認したりするときに役立つウェルカム ページのプレゼンテーションを制御します。

このポリシーを有効にしている (true に設定する) か、構成していない場合、Microsoft Edge では、製品情報を提供するためにフルタブのコンテンツをユーザーに表示することができます。

このポリシーを無効にしている (false に設定する) 場合、Microsoft Edge ではフルタブのコンテンツをユーザーに表示することができなくなります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PromotionalTabsEnabled
  - GP 名: フルタブのプロモーション コンテンツを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: PromotionalTabsEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PromotionalTabsEnabled
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### PromptForDownloadLocation

  #### ダウンロードしたファイルの保存場所を確認する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ファイルをダウンロードする前に、保存する場所を確認するどうかを設定します。

このポリシーを有効にしている場合、ユーザーはダウンロードする前に各ファイルの保存先を求められます。構成していない場合、ユーザーへの確認はなく、ファイルは自動的に既定の場所に保存されます。

このポリシーを構成していない場合、ユーザーはこの設定を変更することができるようになります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: PromptForDownloadLocation
  - GP 名: ダウンロードしたファイルの保存場所を確認する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: PromptForDownloadLocation
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: PromptForDownloadLocation
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### QuicAllowed

  #### QUIC プロトコルを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge での QUIC プロトコルの使用を許可します。

このポリシーを有効にしているか、構成していない場合、QUIC プロトコルが許可されます。

このポリシーを無効にしている場合、QUIC プロトコルはブロックされます。

QUIC は、現在 TCP を使用している Web アプリケーションのパフォーマンスを向上させることができるトランスポート層ネットワーク プロトコルです。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: QuicAllowed
  - GP 名: QUIC プロトコルを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: QuicAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: QuicAllowed
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### RedirectSitesFromInternetExplorerPreventBHOInstall

  #### Internet Explorer から Microsoft Edgeに互換性のないサイトを自動的にリダイレクトする

  
  
  #### サポートされているバージョン:

  - Windows での 87 以降

  #### 説明

  この設定では、最新のブラウザーを必要とするサイトに互換性のないサイトを Internet Explorer から Microsoft Edge にリダイレクトできるようにするブラウザー ヘルパー オブジェクト (BHO) のインストールをブロックするかどうかを指定できます。

このポリシーを有効にすると、BHOはインストールされません。 すでにインストールされている場合は、次の Microsoft Edge アップデートでアンインストールされます。

このポリシーが構成されていないか無効になっている場合、BHO がインストールされます。

互換性のないサイトリダイレクトを発生させるには BHO が必要ですが、リダイレクトが発生するかどうかは、[RedirectSitesFromInternetExplorerRedirectMode](#redirectsitesfrominternetexplorerredirectmode) によっても制御されます。

このポリシーの詳細については、[https://go.microsoft.com/fwlink/?linkid=2141715](https://go.microsoft.com/fwlink/?linkid=2141715) を参照してください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: RedirectSitesFromInternetExplorerPreventBHOInstall
  - GP 名: 互換性のないサイトを Internet Explorer から Microsoft Edg eにリダイレクトするための BHO のインストールを防止する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - Value Name: RedirectSitesFromInternetExplorerPreventBHOInstall
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### RedirectSitesFromInternetExplorerRedirectMode

  #### 互換性のないサイトを Internet Explorer から Microsoft Edgeに自動的にリダイレクトする

  
  
  #### サポートされているバージョン:

  - Windows での 87 以降

  #### 説明

  この設定では、Internet Explorer が最新のブラウザーを必要とするサイトにナビゲーションをリダイレクトするかどうかを Microsoft Edge に指定できます。

このポリシーを構成しないか、「サイトリスト」に設定しない場合、M87 以降の Internet Explorer は最新のブラウザーを必要とするサイトを Microsoft Edge にリダイレクトします。

サイトが Internet Explorer から Microsoft Edge にリダイレクトされると、以前のコンテンツがない場合、そのサイトの読み込みを開始した [Internet Explorer] タブが閉じられます。 それ以外の場合、サイトが Microsoft Edge にリダイレクトされた理由を説明する Microsoft のヘルプページに移動します。

IE からサイトをロードするために Microsoft Edge を起動すると、サイトが最新のブラウザーで最適に機能することを説明する情報バーがユーザーに表示されます。

このポリシーを [無効] に設定すると、Internet Explorer はトラフィックを Microsoft Edge にリダイレクトしません。

このポリシーの詳細については、[https://go.microsoft.com/fwlink/?linkid=2141715](https://go.microsoft.com/fwlink/?linkid=2141715) を参照してください。

ポリシー オプション マッピング:

* Disable (0) = 無効にする

* Sitelist (1) = 互換性のないサイトのサイトリストに基づいてサイトをリダイレクトする

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: RedirectSitesFromInternetExplorerRedirectMode
  - GP 名: 互換性のないサイトを Internet Explorer から Microsoft Edgeにリダイレクトする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - GP 固有の名前: RedirectSitesFromInternetExplorerRedirectMode
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### RelaunchNotification

  #### 保留中の更新についてブラウザーの再起動が推奨されている、または必要であることをユーザーに通知する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  保留中の更新を適用するために、Microsoft Edge を再起動する必要があることをユーザーに通知します。

このポリシーを構成していない場合、Microsoft Edge のトップ メニュー バーの右端に [リサイクル] アイコンが追加され、更新プログラムを適用するためにユーザーにブラウザーの再起動を促すメッセージを表示します。

このポリシーを有効にして “推奨“ に設定している場合、再起動を勧める内容の警告がユーザーに対して繰り返し表示されます。 ユーザーは、この警告を無視して、再起動を延期することができます。

このポリシーを “必須“ に設定している場合、通知期間が過ぎると自動的にブラウザーが再起動されることを確認する内容の警告がユーザーに対して繰り返し表示されます。 既定の期間は 7 日です。 この期間は、[RelaunchNotificationPeriod](#relaunchnotificationperiod) ポリシーで構成することができます。

ユーザーのセッションは、ブラウザーの再起動時に復元されます。

ポリシー オプション マッピング:

* 推奨 (1) = 推奨 - 再起動が推奨されていることを示すメッセージをユーザーに対して繰り返し表示する

* 必須 (2) = 必須 - 再起動が必須であることを示すメッセージをユーザーに対して繰り返し表示する

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: RelaunchNotification
  - GP 名: 保留中の更新についてブラウザーの再起動が推奨されている、または必要であることをユーザーに通知する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: RelaunchNotification
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: RelaunchNotification
  - サンプル値:
``` xml
<integer>1</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### RelaunchNotificationPeriod

  #### 更新通知の期間を設定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  保留中の更新プログラムを適用するために Microsoft Edge の再起動が必要な場合に、その内容をユーザーに通知する期間をミリ秒単位で設定することができます。

この期間の間、ユーザーには更新が必要であることが繰り返し通知されます。 Microsoft Edge では、通知期間の 3 分の 1 が経過するとアプリ メニューが変化し、再起動が必要であることを通知します。 この通知は、通知期間の 3 分の 2 が経過すると色が変化し、全通知期間が経過すると再び色が変化します。 [RelaunchNotification](#relaunchnotification) ポリシーで有効になっている追加の通知は、これと同じスケジュールに従います。

設定されていない場合、既定の期間である 604800000 ミリ秒 (1週間) が使用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: RelaunchNotificationPeriod
  - GP 名: 更新通知の期間を設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: RelaunchNotificationPeriod
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x240c8400
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: RelaunchNotificationPeriod
  - サンプル値:
``` xml
<integer>604800000</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### RendererCodeIntegrityEnabled

  #### レンダラー コードの整合性を有効にする

  
  
  #### サポートされているバージョン:

  - Windows での 78 以降

  #### 説明

  ポリシーを [有効] に設定するか、設定を解除すると、レンダラーのコード整合性が有効になります。
ポリシーを無効に設定すると、Microsoft Edge のセキュリティと安定性に有害な影響が及び、不明で、潜在的に危険なコードが Microsoft Edge のレンダラー プロセス内に読み込まれる可能性があります。 Microsoft Edge のレンダラー プロセス内で実行する必要があるサード パーティ製ソフトウェアとの互換性の問題がある場合にのみ、ポリシーをオフにします。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: RendererCodeIntegrityEnabled
  - GP 名: レンダラー コードの整合性を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: RendererCodeIntegrityEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### RequireOnlineRevocationChecksForLocalAnchors

  #### ローカル トラスト アンカーにオンラインでの OCSP/CRL チェックが必要かどうかを指定する

  
  
  #### サポートされているバージョン:

  - Windows での 77 以降

  #### 説明

  オンラインでの失効チェック (OCSP/CRLチェック) を必須にするかどうかを制御します。 Microsoft Edge が失効状態の情報を取得できない場合、これらの証明書は失効したものとして扱われます ("ハード フェイル")。

このポリシーを有効にしている場合、Microsoft Edge では、検証に成功し、ローカルにインストールされた CA 証明書によって署名されたサーバー証明書の失効チェックが常に行われます。

このポリシーを構成していないか、無効にしている場合、Microsoft Edge は、既存のオンラインでの失効チェックの設定を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: RequireOnlineRevocationChecksForLocalAnchors
  - GP 名: ローカル トラスト アンカーにオンラインでの OCSP/CRL チェックが必要かどうかを指定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: RequireOnlineRevocationChecksForLocalAnchors
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### ResolveNavigationErrorsUseWebService

  #### Web サービスを使用したナビゲーション エラーの解決を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ホテルや空港の Wi-Fi などの場合に、Microsoft Edge が Web サービスにデータレス接続を発行して、ネットワークの接続性を調べることができるようにします。

このポリシーを有効にしている場合、ネットワーク接続性テストに Web サービスが使用されます。

このポリシーを無効にしている場合、Microsoft Edge はネイティブ API を使用して、ネットワークの接続性とナビゲーションの問題の解決を試みます。

**注**: Windows 8 以降のバージョンの Windows を除き、Microsoft Edge は*常に*ネイティブ API を使用して接続性の問題を解決します。

このポリシーを構成していない場合、Microsoft Edge は、edge://settings/privacy のサービスで設定されているユーザー設定を尊重します。
具体的には、ユーザーがオン/オフを切り替えることができる [**Use a web service to help resolve navigation errors**] (Web サービスを使用してナビゲーション エラーを解決する) トグルがあります。 このポリシー (ResolveNavigationErrorsUseWebService) を有効にしている場合、[**Use a web service to help resolve navigation errors**] (Web サービスを使用してナビゲーション エラーを解決する) の設定はオンになっていますが、ユーザーがトグルを使用して設定を変更することはできません。 このポリシーを無効にしている場合、[**Use a web service to help resolve navigation errors**] (Web サービスを使用してナビゲーション エラーを解決する) の設定はオフになっており、ユーザーがトグルを使用して設定を変更することはできません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ResolveNavigationErrorsUseWebService
  - GP 名: Web サービスを使用したナビゲーション エラーの解決を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ResolveNavigationErrorsUseWebService
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ResolveNavigationErrorsUseWebService
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### RestrictSigninToPattern

  #### Microsoft Edge のプライマリ アカウントとして使用できるアカウントを制限する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge でブラウザーのプライマリ アカウントとして設定できるアカウント (Sync オプトイン フローで選択されたアカウント) を決定します。

ユーザーがこのパターンに一致しないユーザー名でブラウザーのプライマリ アカウントを構成しようとした場合、ユーザーはブロックされ、適切なエラー メッセージが表示されます。 パターンに Perl 形式の正規表現を使用して、このポリシーを複数のアカウントに一致するように構成することができます。 パターン一致では、大文字と小文字が区別されます。 使用する正規表現ルールの詳細については、https://go.microsoft.com/fwlink/p/?linkid=2133903を参照してください。

このポリシーを構成していないか、このポリシーを空白のままにしている場合、ユーザーは Microsoft Edge で任意のアカウントをブラウザーのプライマリ アカウントとして設定することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: RestrictSigninToPattern
  - GP 名: Microsoft Edge のプライマリ アカウントとして使用できるアカウントを制限する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: RestrictSigninToPattern
  - 値の種類: REG_SZ

  ##### サンプル値:

```
".*@contoso.com"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: RestrictSigninToPattern
  - サンプル値:
``` xml
<string>.*@contoso.com</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### RoamingProfileLocation

  #### ローミング プロファイル ディレクトリを設定する

  
  
  #### サポートされているバージョン:

  - Windows での 85 以降

  #### 説明

  プロファイルのローミング コピーを格納するために使用するディレクトリを構成します。

このポリシーを有効にすると、[RoamingProfileSupportEnabled](#roamingprofilesupportenabled) ポリシーも有効にしている限り、Microsoft Edge は提供されたディレクトリを使用してプロファイルのローミング コピーを保存します。 [RoamingProfileSupportEnabled](#roamingprofilesupportenabled) ポリシーを無効にするか、構成しない場合、このポリシーに格納されている値は使用されません。

使用できる変数の一覧については、「[https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041)」を参照してください。

このポリシーを構成していない場合、既定のローミング プロファイル パスが使用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: RoamingProfileLocation
  - GP 名: ローミング プロファイル ディレクトリを設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: RoamingProfileLocation
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"${roaming_app_data}\\edge-profile"
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### RoamingProfileSupportEnabled

  #### Microsoft Edge プロファイル データのローミング コピーの使用を有効にする

  
  
  #### サポートされているバージョン:

  - Windows での 85 以降

  #### 説明

  Windows でローミング プロファイルを使用するには、このポリシーを有効にします。 Microsoft Edge プロファイルに保存されている設定 (お気に入りと基本設定) は、ローミング ユーザー プロファイル フォルダー (または管理者が [RoamingProfileLocation](#roamingprofilelocation) ポリシーを通じて指定した場所) に保存されているファイルにも保存されます。

このポリシーを無効にした場合、または構成しない場合は、通常のローカル プロファイルだけが使用されます。

[SyncDisabled](#syncdisabled) ポリシーは、すべてのデータ同期を無効にし、ポリシーを上書きします。

ローミング ユーザー プロファイルの使用の詳細については、https://docs.microsoft.com/windows-server/storage/folder-redirection/deploy-roaming-user-profiles を参照してください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: RoamingProfileSupportEnabled
  - GP 名: Microsoft Edge プロファイル データのローミング コピーの使用を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: RoamingProfileSupportEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### RunAllFlashInAllowMode

  #### Adobe Flash のコンテンツ設定をすべてのコンテンツに拡張する (不使用)

  
  >不使用: このポリシーは廃止されており、Microsoft Edge 87 以降は機能しません。
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降、87 まで

  #### 説明

  Flash は Microsoft Edge でサポートされなくなったため、このポリシーは機能しません。

このポリシーを有効にしている場合、ユーザーまたはエンタープライズ ポリシーによってコンテンツ設定で Adobe Flash を許可するように設定されている Web サイトに埋め込まれているすべての Adobe Flash コンテンツが実行されます。 これには、その他のオリジンおよび/または小さなコンテンツからのコンテンツが含まれています。

Adobe Flash の実行を許可する Web サイトを制御するには、[DefaultPluginsSetting](#defaultpluginssetting)、[PluginsAllowedForUrls](#pluginsallowedforurls)、[PluginsBlockedForUrls](#pluginsblockedforurls) ポリシーの仕様を参照してください。

このポリシーを無効にしているか、構成していない場合、その他のオリジン (すぐ上で挙げた 3 つのポリシーで指定されていないサイト) からの Adobe Flash コンテンツや、小さなコンテンツがブロックされる可能性があります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: RunAllFlashInAllowMode
  - GP 名: Adobe Flash のコンテンツ設定をすべてのコンテンツに拡張する (不使用)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: RunAllFlashInAllowMode
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: RunAllFlashInAllowMode
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SSLErrorOverrideAllowed

  #### HTTPS の警告ページから続行できるようにする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge では、SSL エラーが発生しているサイトにユーザーがアクセスすると、警告ページが表示されます。

このポリシーを有効にしているか、構成していない (既定) 場合、ユーザーはこれらの警告ページをクリック スルーできます。

このポリシーを無効にしている場合、ユーザーは警告ページをクリックしてもブロックされます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SSLErrorOverrideAllowed
  - GP 名: HTTPS の警告ページから続行できるようにする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: SSLErrorOverrideAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SSLErrorOverrideAllowed
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SSLVersionMin

  #### 最小限の TLS バージョンを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  TLS の最小限のサポート バージョンを設定します。 このポリシーを構成しない場合、Microsoft Edge では TLS 1.0 と TLS 1.1 にエラーが表示されますが、ユーザーはこれを回避することができます。

このポリシーを有効にすると、Microsoft Edge は指定されたバージョンより前のバージョンの SSL/TLS を使用しなくなります。 認識されない値は、無視されます。

ポリシー オプション マッピング:

* TLSv1 (tls1) = TLS 1.0

* TLSv 1.1 (tls 1.1) = TLS 1.1

* TLSv 1.2 (tls 1.2) = TLS 1.2

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SSLVersionMin
  - GP 名: 最小限の TLS バージョンを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: SSLVersionMin
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"tls1"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SSLVersionMin
  - サンプル値:
``` xml
<string>tls1</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SaveCookiesOnExit

  #### Microsoft Edge の終了時に cookie を保存する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  このポリシーを有効にすると、ブラウザーの終了時に、指定した cookie のセットが削除されません。 このポリシーは、次の場合にのみ有効です。
- 'cookie およびその他のサイト データ' の切り替えは、[設定/プライバシー]、[サービス/終了時に閲覧データをクリア]、または
- ポリシー [ClearBrowsingDataOnExit](#clearbrowsingdataonexit) が有効な場合、または
- ポリシー [DefaultCookiesSetting](#defaultcookiessetting) が ' セッションの間、cookie を保持する ' に設定されている場合です。

セッション間で cookie が保存される URL パターンに基づいて、サイト一覧を定義することができます。

注: ユーザーは、URL を追加または削除するために cookie サイト一覧を引き続き編集できます。 ただし、管理者が追加した URL は削除できません。

このポリシーを有効にすると、ブラウザーが終了したときに cookie のリストがクリアされません。

このポリシー設定を無効にするか、または構成しなかった場合は、ユーザーの個人構成が使用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SaveCookiesOnExit
  - GP 名: Microsoft Edge の終了時に cookie を保存する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\SaveCookiesOnExit
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\SaveCookiesOnExit\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SaveCookiesOnExit\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 優先順位キー名: SaveCookiesOnExit
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SavingBrowserHistoryDisabled

  #### ブラウザー履歴の保存を無効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ブラウザーの履歴の保存を無効にし、ユーザーがこの設定を変更できないようにします。

このポリシーを有効にしている場合、閲覧の履歴は保存されません。 これを無効にすると、タブの同期も無効になります。

このポリシーを無効にしているか、構成していない場合、閲覧の履歴は保存されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SavingBrowserHistoryDisabled
  - GP 名: ブラウザー履歴の保存を無効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: SavingBrowserHistoryDisabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SavingBrowserHistoryDisabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ScreenCaptureAllowed

  #### 画面キャプチャを許可または拒否する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 83 以降

  #### 説明

  このポリシーを有効にしているか、構成していない場合、Web ページは画面キャプチャに画面の共有 API (たとえば、getDisplayMedia() や デスクトップ キャプチャ拡張 API) を使用することができます。
このポリシーを無効にしている場合、画面の共有 API の呼び出しは失敗します。 たとえば、Web ベースのオンライン会議を使用している場合、ビデオや画面共有は機能しません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ScreenCaptureAllowed
  - GP 名: 画面キャプチャを許可または拒否する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ScreenCaptureAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ScreenCaptureAllowed
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ScrollToTextFragmentEnabled

  #### URL フラグメントで指定されたテキストへのスクロールを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 83 以降

  #### 説明

  この機能により、Web ページの読み込みが終了した後にハイパーリンクやアドレス バーの URL ナビゲーションが、Web ページの特定のテキストをターゲットにしてスクロールできるようになります。

このポリシーを有効にしているか、構成していない場合、URL を介した特定のテキスト フラグメントへの Web ページのスクロールが有効になります。

このポリシーを無効にしている場合、URL を介した特定のテキスト フラグメントへの Web ページのスクロールは無効になります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ScrollToTextFragmentEnabled
  - GP 名: URL フラグメントで指定されたテキストへのスクロールを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ScrollToTextFragmentEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ScrollToTextFragmentEnabled
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SearchSuggestEnabled

  #### 検索候補を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge のアドレス バーと自動提案一覧での Web 検索候補を有効にし、ユーザーがこのポリシーを変更できないようにします。

このポリシーを有効にしている場合、Web 検索候補は使用されます。

このポリシーを無効にしている場合、Web 検索候補は使用されませんが、ローカルの履歴やお気に入りの提案は表示されます。 このポリシーを無効にしている場合、入力した文字も訪問した URL も、Microsoft へのテレメトリには含まれません。

このポリシーを設定していない場合、検索候補は有効になりますが、ユーザーはそれを変更することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SearchSuggestEnabled
  - GP 名: 検索候補を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: SearchSuggestEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SearchSuggestEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SecurityKeyPermitAttestation

  #### 直接的なセキュリティ キーの構成証明を使用するためのアクセス許可を必要としない Web サイトやドメイン

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  セキュリティ キーからの構成証明書を要求するときに、明示的なユーザーのアクセス許可を必要としない Web サイトやドメインを指定します。 さらに、個別の構成証明が使用できることを示すシグナルがセキュリティ キーに送信されます。 これが設定されていない場合、サイトがセキュリティ キーの構成証明を要求するたびに、ユーザーに確認を求めるメッセージが表示されます。

サイト (https://contoso.com/some/path) など) は U2F appID としてのみ一致します。 ドメイン (contoso.com など) は webauthn RP ID としてのみ一致します。 指定されたサイトの U2F と webauthn API の両方をカバーするには、appID URL とドメインの両方をリスト化する必要があります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SecurityKeyPermitAttestation
  - GP 名: 直接的なセキュリティ キーの構成証明を使用するためのアクセス許可を必要としない Web サイトやドメイン
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\SecurityKeyPermitAttestation
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\SecurityKeyPermitAttestation\1 = "https://contoso.com"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SecurityKeyPermitAttestation
  - サンプル値:
``` xml
<array>
  <string>https://contoso.com</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SendIntranetToInternetExplorer

  #### すべてのイントラネット サイトを Internet Explorer に送る

  
  
  #### サポートされているバージョン:

  - Windows での 77 以降

  #### 説明

  Internet Explorer モードで最適なエクスペリエンスを構成する方法については、「[https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)」を参照してください

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SendIntranetToInternetExplorer
  - GP 名: すべてのイントラネット サイトを Internet Explorer に送る
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: SendIntranetToInternetExplorer
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### SendSiteInfoToImproveServices

  #### Microsoft サービスを向上させるためにサイト情報を送信する (廃止)

  
  >不使用: このポリシーは廃止されており、Microsoft Edge 88 以降は機能しません。
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降、88 まで

  #### 説明

  このポリシーはサポートされなくなりました。 このポリシーは [DiagnosticData](#diagnosticdata) に置き換えられ (Windows 7、Windows 8、および macOS)、Windows 10 ([https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)) でテレメトリが許可されます。

このポリシーでは、検索などのサービスの品質を向上させるために Microsoft Edge で訪問した Web サイトに関する情報を Microsoft に送信できます。

Microsoft Edge でアクセスした Web サイトに関する情報を Microsoft に送信する場合は、このポリシーを有効にします。 Microsoft Edge でアクセスした Web サイトに関する情報を Microsoft に送信しない場合は、このポリシーを無効にします。 いずれの場合でも、ユーザーがこの設定を変更または上書きすることはできません。

Windows 10 では、このポリシーを構成していない場合、Microsoft Edge は Windows 診断データの設定を既定値として設定します。 このポリシーが有効になっている場合、Microsoft Edge は、Windows 診断データの設定が [完全] に設定されている場合にのみ、Microsoft Edge でアクセスした Web サイトに関する情報を送信します。 このポリシーが無効になっている場合、Microsoft Edge はアクセスした Web サイトに関する情報を送信しません。 Windows 診断データの設定については、「[https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)」を参照してください

Windows 7、windows 8、macOS では、このポリシーはアクセスした Web サイトに関する情報の送信を制御します。 このポリシーを構成しない場合、Microsoft Edge は既定でユーザーの設定に従います。

このポリシーを有効にするには、 [MetricsReportingEnabled](#metricsreportingenabled) を有効に設定する必要があります。 [SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices) または [MetricsReportingEnabled](#metricsreportingenabled) が構成されていないか、または無効になっている場合は、このデータは Microsoft に送信されません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - 一意の GP 名: SendSiteInfoToImproveServices
  - GP 名: Microsoft サービスを向上させるためにサイト情報を送信する (廃止)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: SendSiteInfoToImproveServices
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SendSiteInfoToImproveServices
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SensorsAllowedForUrls

  #### 特定のサイトでのセンサーへのアクセスを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  モーションセンサーや光センサーなどのセンサーにアクセスして使用できるサイトのリストを URL パターンに基づいて定義します。

このポリシーを構成していない場合、 [DefaultPopupsSetting](#defaultsensorssetting) ポリシー (設定されている場合) からのグローバルな既定値またはユーザーの個人用の構成がすべてのサイトで使用されます。

このポリシーと一致しない URL のパターンの場合、以下が優先順位となります： [SensorsBlockedForUrls](#sensorsblockedforurls) ポリシー (一致している場合)、 [DefaultSensorsSetting](#defaultsensorssetting) ポリシー (設定されている場合)、またはユーザーの個人用設定

このポリシーで定義されている URL パターンは、 [SensorsBlockedForUrls](#sensorsblockedforurls) ポリシーで構成されているものと競合することはできません。 URL を許可することも、ブロックすることもできません。

有効な URL パターンの詳細については、[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) をご覧ください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SensorsAllowedForUrls
  - GP 名: 特定のサイトのセンサーへのアクセスを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\PopupsAllowedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\SensorsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SensorsAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キー名: SensorsAllowedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SensorsBlockedForUrls

  #### 特定のサイトでのセンサーへのアクセスをブロックする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  モーションセンサーや光センサーなどのセンサーにアクセスできないサイトのリストを、URL パターンに基づいて定義します。

このポリシーを構成していない場合、 [DefaultPopupsSetting](#defaultsensorssetting) ポリシー (設定されている場合) からのグローバルな既定値またはユーザーの個人用の構成がすべてのサイトで使用されます。

このポリシーと一致しない URL のパターンの場合、次の優先順位が使用されます。 [SensorsAllowedForUrls Urls](#sensorsallowedforurls)ポリシー (一致するものがある場合)、[DefaultSensorsSetting](#defaultsensorssetting) policy (設定されている場合)、またはユーザーの個人用設定です。

このポリシーで定義されている URL パターンは、 [SensorsAllowedForUrls](#sensorsallowedforurls) ポリシーで構成されているものと競合することはできません。 URL を許可することも、ブロックすることもできません。

有効な URL パターンの詳細については、[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) をご覧ください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SensorsBlockedForUrls
  - GP 名: 特定のサイトのセンサーへのアクセスをブロックする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\PopupsBlockedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\SensorsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SensorsBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SensorsBlockedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SerialAskForUrls

  #### 特定のサイトでのシリアル API を許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  シリアルポートへのアクセスをユーザーに対して確認することができるサイトの一覧を URL パターンに基づいて定義します。

このポリシーを構成していない場合、[DefaultWebUsbGuardSetting](#defaultserialguardsetting) ポリシー (設定されている場合) からのグローバルな既定値または、ユーザーの個人用の構成がすべてのサイトで使用されます。

このポリシーと一致しない URL のパターンの場合、以下が優先順位です：[SerialBlockedForUrls](#serialblockedforurls) ポリシー (一致している場合)、 [DefaultSerialGuardSetting](#defaultserialguardsetting) ポリシー (設定されている場合)、またはユーザーの個人用設定

このポリシーで定義されている URL パターンは、 [SerialBlockedForUrls](#serialblockedforurls) ポリシーで構成されているものと競合することはできません。 URL を許可することも、ブロックすることもできません。

有効な URL パターンの詳細については、[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) をご覧ください

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SerialAskForUrls
  - GP 名: 特定のサイトのシリアル API を許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\SerialAskForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\SerialAskForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SerialAskForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SerialAskForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SerialBlockedForUrls

  #### 特定のサイトでのシリアル API をブロックする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  シリアルポートへのアクセス権の付与をユーザーに対して確認することができないサイトの一覧を URL パターンに基づいて定義します。

このポリシーを構成していない場合、[DefaultWebUsbGuardSetting](#defaultserialguardsetting) ポリシー (設定されている場合) からのグローバルな既定値または、ユーザーの個人用の構成がすべてのサイトで使用されます。

このポリシーと一致しない URL のパターンの場合、以下の優先順位が使用されます： [SerialAskForUrls](#serialaskforurls) ポリシー (一致している場合)、 [DefaultSerialGuardSetting](#defaultserialguardsetting) ポリシー (設定されている場合)、またはユーザーの個人用設定

このポリシーの URL パターンは、[WebUsbAskForUrls](#serialaskforurls) ポリシーで構成されたものと競合することはできません。 URL を許可することも、ブロックすることもできません。

有効な URL パターンの詳細については、[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) をご覧ください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SerialBlockedForUrls
  - GP 名: 特定のサイトのシリアル API をブロックする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\SerialBlockedForUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\SerialBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SerialBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SerialBlockedForUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ShowMicrosoftRewards

  #### Microsoft Rewards のエクスペリエンスを表示する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 88 以降

  #### 説明

  Microsoft Rewards のエクスペリエンスと通知を表示します。
このポリシーを有効にした場合:
   - 検索とポイント獲得を利用している Microsoft アカウント ユーザー (Azure AD アカウントを除く) は、Microsoft Edge のユーザー プロファイルに Microsoft Rewards のエクスペリエンスが表示されます。
   - Microsoft Edge の設定での Microsoft Rewards の設定は有効になり、オンになります。

このポリシーを無効にした場合:
   - 検索とポイント獲得を利用している Microsoft アカウント ユーザー (Azure AD アカウントを除く) は、Microsoft Edge のユーザー プロファイルに Microsoft Rewards のエクスペリエンスが表示されません。
   - Microsoft Edge の設定での Microsoft Rewards の設定は無効になり、オフになります。

このポリシーを構成しない場合:
   - 検索とポイント獲得を利用している Microsoft アカウント ユーザー (Azure AD アカウントを除く) は、Microsoft Edge のユーザー プロファイルに Microsoft Rewards のエクスペリエンスが表示されます。
   - Microsoft Edge の設定での Microsoft Rewards の設定は有効になり、オンになります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ShowMicrosoftRewards
  - GP 名: Microsoft Rewards エクスペリエンスを表示する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: ShowMicrosoftRewards
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ShowMicrosoftRewards
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### ShowOfficeShortcutInFavoritesBar

  #### お気に入り バーにMicrosoft Office のショートカットを表示する (非推奨)

  >非推奨: このポリシーは推奨されなくなっています。 現在はサポートされていますが、将来のリリースで廃止されます。
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーは、運用要件の変更のため、期待どおりに動作しませんでした。 そのため、使用されません。

お気に入り バーに Office.com へのショートカットを表示するどうかを指定します。 Microsoft Edge にサインインしているユーザーの場合、ショートカットはユーザーを Microsoft Office のアプリやドキュメントへと移動させます。このポリシーを有効にしているか、構成していない場合、ユーザーはお気に入り バーのコンテキスト メニューのトグルを変更することで、ショートカットを表示するかどうかを選択することができます。
このポリシーを無効にすると、ショートカットが表示されなくなります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ShowOfficeShortcutInFavoritesBar
  - GP 名: お気に入り バーに Microsoft Office のショートカットを表示する（非推奨）
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: ShowOfficeShortcutInFavoritesBar
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: ShowOfficeShortcutInFavoritesBar
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SignedHTTPExchangeEnabled

  #### Signed HTTP Exchange (SXG) のサポートを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 78 以降

  #### 説明

  Signed HTTP Exchange (SXG) のサポートを有効にします。

このポリシーを設定していないか、有効にしている場合、Microsoft Edge は Signed HTTP Exchange として提供されている Web コンテンツを受け入れます。

このポリシーを無効に設定している場合、Signed HTTP Exchange を読み込むことはできません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SignedHTTPExchangeEnabled
  - GP 名: Signed HTTP Exchange (SXG) のサポートを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: SignedHTTPExchangeEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SignedHTTPExchangeEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SitePerProcess

  #### すべてのサイトでのサイトの分離を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  "SitePerProcess" ポリシーは、すべてのサイトを分離する既定の動作をユーザーがオプトアウトしないようにするために使用することができます。 [IsolateOrigins](#isolateorigins) ポリシーを使用して、さらに詳細な追加のオリジンを分離することもできます。

このポリシーを有効にしている場合、各サイトが独自のプロセスで実行する既定の動作をユーザーがオプトアウトすることができなくなります。

このポリシーを無効にしているか、構成していない場合、ユーザーはサイトの分離をオプトアウトすることができます。  (たとえば edge://flags の "サイトの分離を無効にする" エントリを使用して) ポリシーを無効にしたり、または構成しなかったりしても、サイトの分離はオフにはなりません。


  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SitePerProcess
  - GP 名: すべてのサイトでのサイトの分離を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: SitePerProcess
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SitePerProcess
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SpeechRecognitionEnabled

  #### Configure Speech Recognition

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 87 以降

  #### 説明

  Set whether websites can use the W3C Web Speech API to recognize speech from the user. Microsoft Edge 実装では、Azure の認識サービスを使用しているため、音声データはコンピューターから離脱します。

If you enable or don't configure this policy, web-based applications that use the Web Speech API can use Speech Recognition.

If you disable this policy, Speech Recognition is not available through the Web Speech API.

この機能の詳細については、以下を参照してください。SpeechRecognition API: [https://go.microsoft.com/fwlink/?linkid=2143388](https://go.microsoft.com/fwlink/?linkid=2143388) Cognitive Services: [https://go.microsoft.com/fwlink/?linkid=2143680](https://go.microsoft.com/fwlink/?linkid=2143680)

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP unique name: SpeechRecognitionEnabled
  - GP name: Configure Speech Recognition
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - Value Name: SpeechRecognitionEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - Preference Key Name: SpeechRecognitionEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SpellcheckEnabled

  #### スペルチェックを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーを有効にしているか、構成していない場合、ユーザーはスペルチェックを使用することができます。

このポリシーを無効にしている場合、ユーザーはスペルチェックを使用できなくなり、[SpellcheckLanguage](#spellchecklanguage) ポリシーと [SpellcheckLanguageBlocklist](#spellchecklanguageblocklist) ポリシーも無効になります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SpellcheckEnabled
  - GP 名: スペルチェックを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: SpellcheckEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SpellcheckEnabled
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SpellcheckLanguage

  #### 特定のスペルチェック言語を有効にする

  
  
  #### サポートされているバージョン:

  - Windows での 77 以降

  #### 説明

  スペルチェックに使用する異なる言語を有効にします。 認識されない言語を指定している場合には、その言語は無視されます。

このポリシーを有効にしている場合、指定されている言語やユーザーが有効にした言語に対してスペルチェックが有効になります。

このポリシーを構成していないか、または無効の場合、ユーザーのスペルチェックの設定は変更されません。

[SpellcheckEnabled](#spellcheckenabled) ポリシーが無効になっている場合、このポリシーには何の効果もありません。

"SpellcheckLanguage" ポリシーと [SpellcheckLanguageBlocklist](#spellchecklanguageblocklist) ポリシーの両方に言語が含まれている場合、スペルチェック言語は有効になります。

サポートされている言語は、以下の通りです: af、bg、ca、cs、cy、da、de、el、en-AU、en-CA、en-GB、en-US、es、es-419、es-AR、es-ES、es-MX、es-US、et、fa、fo、fr、he、hi、hr、hu、id、it、ko、lt、lv、nb、nl、pl、pt-BR、pt-PT、ro、ru、sh、sk、sl、sq、sr、sv、ta、tg、tr、uk、vi。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SpellcheckLanguage
  - GP 名: 特定のスペルチェック言語を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguage
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguage\1 = "fr"
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguage\2 = "es"

```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### SpellcheckLanguageBlocklist

  #### スペルチェック言語の無効化を強制する

  
  
  #### サポートされているバージョン:

  - Windows での 78 以降

  #### 説明

  スペルチェック言語の無効化を強制します。 そのリスト内の認識されない言語は、無視されます。

このポリシーを有効にしている場合、指定した言語に対するスペルチェックは無効になります。 ユーザーは、リストにない言語のスペルチェックも有効または無効にすることができます。

このポリシーを構成しないか、または無効にする場合、ユーザーのスペルチェックの設定は変更されません。

[SpellcheckEnabled](#spellcheckenabled) ポリシーが無効に設定されている場合、このポリシーには何の効果もありません。

[SpellcheckLanguage](#spellchecklanguage) ポリシーと "SpellcheckLanguageBlocklist" ポリシーの両方に言語が含まれている場合、スペルチェック言語は有効になります。

現在サポートされている言語は、以下の通りです: af、bg、ca、cs、da、de、el、en-AU、en-CA、en-GB、en-US、es、es-419、es-AR、es-ES、es-MX、es-US、et、fa、fo、fr、he、hi、hr、hu、id、it、ko、lt、lv、nb、nl、pl、pt-BR、pt-PT、ro、ru、sh、sk、sl、sq、sr、sv、ta、tg、tr、uk、vi。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SpellcheckLanguageBlocklist
  - GP 名: スペルチェック言語の無効化を強制する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguageBlocklist
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguageBlocklist\1 = "fr"
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguageBlocklist\2 = "es"

```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### StricterMixedContentTreatmentEnabled

  #### 混在したコンテンツに対するより厳密な扱いを有効にする (非推奨)

  >非推奨: このポリシーは推奨されなくなっています。 現在はサポートされていますが、将来のリリースで廃止されます。
  
  #### サポートされているバージョン:

  - Windows と macOS での 81 以降

  #### 説明

  このポリシーは、企業の Web コンテンツが、混在したコンテンツのより厳密な扱いと互換していないことが判明した場合に、Web コンテンツの更新に時間を割くための短期のメカニズムとしてのみ機能することを目的としているため、推奨されていません。 Microsoft Edge バージョン 85 では機能しません。

このポリシーでは、混在したコンテンツ (HTTPS サイト内の HTTP コンテンツ) のブラウザーでの処理を制御します。

このポリシーを true に設定しているか、設定していない場合、音声と動画の混在したコンテンツは自動的に HTTPS へとアップグレードされ (つまり、リソースが HTTPS で利用できない場合でも、フォールバックなしで URL が HTTPS として書き換えられます)、画像の混在したコンテンツの URL バーには「セキュリティ保護なし」という警告が表示されます。

このポリシーを false に設定している場合、音声と動画では自動アップグレードが無効になり、画像では警告が表示されなくなります。

このポリシーは、音声、動画、画像以外の混在したコンテンツには影響しません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: StricterMixedContentTreatmentEnabled
  - GP 名: 混在したコンテンツに対するより厳密な扱いを有効にする (非推奨)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: StricterMixedContentTreatmentEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: StricterMixedContentTreatmentEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SuppressUnsupportedOSWarning

  #### サポートされていない OS の警告を非表示にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  サポート対象外のコンピューターまたはオペレーティング システムで Microsoft Edge が実行されている場合に表示される警告を抑制します。

このポリシーを false に設定しているか、設定していない場合、そういったサポート対象外のコンピューターやオペレーティング システムに対しては警告が表示されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SuppressUnsupportedOSWarning
  - GP 名: サポートされていない OS の警告を非表示にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: SuppressUnsupportedOSWarning
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SuppressUnsupportedOSWarning
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SyncDisabled

  #### Microsoft 同期サービスを使用してデータの同期を無効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge でのデータ同期を無効にします。 また、このポリシーにより、同期に対する同意を確認するメッセージも表示されなくなります。

このポリシーを設定していないか、推奨通りに適用していない場合、ユーザーは同期のオン/オフを切り替えることができるようになります。 このポリシーを必須として適用している場合、ユーザーは同期をオンにすることができなくなります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SyncDisabled
  - GP 名: Microsoft 同期サービスを使用してデータの同期を無効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: SyncDisabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SyncDisabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### SyncTypesListDisabled

  #### 同期から除外される種類の一覧を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 83 以降

  #### 説明

  このポリシーを有効にしている場合、指定されたすべてのデータの種類が同期から除外されます。 このポリシーを使用して、Microsoft Edge 同期サービスにアップロードされるデータの種類を制限することができます。

このポリシーには、次のデータの種類のいずれかを指定することができます: "favorites"、"settings"、"passwords"、"addressesAndMore"、"extensions"、"history"、"openTabs"、および "collections"。 これらのデータの種類の名前は、大文字と小文字を区別します。

ユーザーが無効なデータの種類を上書きすることはできません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: SyncTypesListDisabled
  - GP 名: 同期から除外される種類の一覧を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\SyncTypesListDisabled
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\SyncTypesListDisabled\1 = "favorites"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: SyncTypesListDisabled
  - サンプル値:
``` xml
<array>
  <string>favorites</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### TLS13HardeningForLocalAnchorsEnabled

  #### ローカル トラスト アンカーの TLS 1.3 セキュリティ機能を有効にする (不使用)

  
  >不使用: このポリシーは廃止されており、Microsoft Edge 85 以降は機能しません。
  #### サポートされているバージョン:

  - Windows と macOS での 81 以降、85 まで

  #### 説明

  このポリシーは、企業が影響を受けるプロキシをアップグレードする時間を確保するための短期メカニズムとして機能することを目的としていたため、機能しません。

このポリシーでは、ダウングレード攻撃から接続を保護する TLS 1.3 のセキュリティ機能を制御します。 これには下位互換性があり、準拠している TLS 1.2 サーバーやプロキシへの接続には影響しません。 しかし、一部の TLS インターセプト プロキシの古いバージョンには実装上の欠陥があり、互換性がありません。

このポリシーを有効にしているか、設定していない場合、Microsoft Edge はすべての接続に対してこれらのセキュリティ保護を有効にします。

このポリシーを無効にしている場合、Microsoft Edge は、ローカルにインストールされた CA 証明書で認証された接続に対して、これらのセキュリティ保護を無効にします。 これらの保護は、公的に信頼されている CA 証明書で認証された接続に対しては常に有効になっています。

このポリシーは、影響を受けるプロキシのテストやそれらのアップグレードに使用される場合があります。 影響を受けるプロキシは、ERR_TLS13_DOWNGRADE_DETECTED のエラー コードとともに接続に失敗することが予想されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: TLS13HardeningForLocalAnchorsEnabled
  - GP 名: ローカル トラスト アンカーの TLS 1.3 セキュリティ機能を有効にする (不使用)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: TLS13HardeningForLocalAnchorsEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: TLS13HardeningForLocalAnchorsEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### TLSCipherSuiteDenyList

  #### 無効にする TLS 暗号スイートを指定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 85 以降

  #### 説明

  TLS 接続に対して無効になっている暗号スイートのリストを構成します。

このポリシーを構成する場合、TLS 接続を確立するときに、構成済みの暗号スイートのリストが使用されることはありません。

このポリシーを構成しない場合は、ブラウザーによって、使用する TLS 暗号スイートが選択されます。

無効にする暗号スイート値は、16 ビット 16 進値として指定されます。 これらの値は、Internet Assigned Numbers Authority (IANA) レジストリによって割り当てられます。

TLS 1.3 暗号スイート TLS_AES_128_GCM_SHA256 (0x1301) は TLS 1.3 に必要です。このポリシーでは無効にすることはできません。

このポリシーは、QUIC ベースの接続には影響しません。 QUIC は、[QuicAllowed](#quicallowed) ポリシーによってオフにすることができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: TLSCipherSuiteDenyList
  - GP 名: 無効にする TLS 暗号スイートを指定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\TLSCipherSuiteDenyList
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\TLSCipherSuiteDenyList\1 = "0x1303"
SOFTWARE\Policies\Microsoft\Edge\TLSCipherSuiteDenyList\2 = "0xcca8"
SOFTWARE\Policies\Microsoft\Edge\TLSCipherSuiteDenyList\3 = "0xcca9"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: TLSCipherSuiteDenyList
  - サンプル値:
``` xml
<array>
  <string>0x1303</string>
  <string>0xcca8</string>
  <string>0xcca9</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### TabFreezingEnabled

  #### バックグラウンド タブのフリーズを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 79 以降

  #### 説明

  Microsoft Edge がバックグラウンドにあるタブを 5 分以上フリーズさせることができるかどうかを制御します。

タブのフリーズは、CPU、バッテリー、メモリの使用量を削減します。 Microsoft Edge では、通知の表示、サウンドの再生、動画のストリーミングなど、バックグラウンドで役に立つ作業を行うタブのフリーズを回避するためにヒューリスティックを使用します。

このポリシーを有効にしているか、構成していない場合、バックグラウンドで少なくとも 5 分以上経過したタブがフリーズする可能性があります。

このポリシーを無効にしている場合、タブはフリーズしません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: TabFreezingEnabled
  - GP 名: バックグラウンド タブのフリーズを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: TabFreezingEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: TabFreezingEnabled
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### TargetBlankImpliesNoOpener

  #### _blank を対象とするリンクに window.opener を設定しない

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 88 以降

  #### 説明

  このポリシーを有効にするか、設定しないままにした場合、アンカーで rel="opener" が指定されていない限り、window.opener プロパティは null に設定されます。

このポリシーを無効にした場合、_blank を対象とするポップアップが (JavaScript 経由で) ポップアップを開くことを要求するページにアクセスすることが許可されます。

このポリシーは、Microsoft Edge バージョン 95 で廃止されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - 一意の GP 名: TargetBlankImpliesNoOpener
  - GP 名: _blank を対象とするリンクに window.opener を設定しない
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: TargetBlankImpliesNoOpener
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - Preference Key Name: TargetBlankImpliesNoOpener
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### TaskManagerEndProcessEnabled

  #### ブラウザーのタスク マネージャーで終了プロセスを有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  このポリシーを有効にしているか、構成していない場合、ユーザーはブラウザーのタスク マネージャーでプロセスを終了することができます。 無効にしている場合、ユーザーはプロセスを終了することができず、ブラウザーのタスク マネージャーの [プロセスの終了] ボタンが無効になります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: TaskManagerEndProcessEnabled
  - GP 名: ブラウザーのタスク マネージャーで終了プロセスを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: TaskManagerEndProcessEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: TaskManagerEndProcessEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### TotalMemoryLimitMb

  #### Microsoft Edge インスタンス 1 つあたりの使用可能メモリ (MB) の制限を設定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 80 以降

  #### 説明

  メモリを節約するためにタブが破棄される前に、単一の Microsoft Edge インスタンスが使用できるメモリの容量を構成します。 タブが使用していたメモリは解放され、切り替え時にはタブを再読み込みする必要があります。

このポリシーを有効にしている場合、制限を超えたときにブラウザーはメモリを節約するためにタブの破棄を開始します。 ただし、ブラウザが常に制限以下で動作するという保証はありません。 1024 未満の値は、1024 へと切り上げられます。

このポリシーを設定していない場合、ブラウザーは、コンピューターの物理メモリ量が少ないことが検出された場合にのみ、メモリの節約を試みます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: TotalMemoryLimitMb
  - GP 名: Microsoft Edge インスタンス 1 つあたりの使用可能メモリ (MB) の制限を設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: TotalMemoryLimitMb
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000800
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: TotalMemoryLimitMb
  - サンプル値:
``` xml
<integer>2048</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### TrackingPrevention

  #### ユーザーの Web 閲覧アクティビティの追跡のブロック

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 78 以降

  #### 説明

  ユーザーの Web 閲覧アクティビティを追跡する Web サイトをブロックするかどうかを決定することができます。

このポリシーを無効にしているか、構成していない場合、ユーザーは追跡防止のレベルを独自に設定することができます。

ポリシー オプション マッピング:

* TrackingPreventionOff (0) = オフ (追跡防止なし)

* TrackingPreventionBasic (1) = 基本 (有害なトラッカーをブロックし、コンテンツや広告はカスタマイズされます)

* TrackingPreventionBalanced (2) = バランス (有害なトラッカーとユーザーが訪問したことのないサイトからのトラッカーをブロックします。コンテンツと広告は、あまりカスタマイズされません)

* TrackingPreventionStrict (3) = 厳密 (すべてのサイトからの有害なトラッカーと大多数のトラッカーをブロックします。コンテンツと広告は、最小限のもののみカスタマイズされます。 サイトの一部が動作しない可能性があります)

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: TrackingPrevention
  - GP 名: ユーザーの Web 閲覧アクティビティの追跡のブロック
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: TrackingPrevention
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000002
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: TrackingPrevention
  - サンプル値:
``` xml
<integer>2</integer>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### TranslateEnabled

  #### 翻訳を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge で、統合された Microsoft 翻訳サービスを有効にします。

このポリシーを有効にしている場合、Microsoft Edge では、統合された翻訳ポップアップが必要に応じて表示され、右クリック コンテキスト メニューに翻訳オプションが表示されることで、ユーザーに翻訳機能が提供されます。

このポリシーを無効にしている場合、すべての組み込み翻訳機能が無効になります。

このポリシーを構成していない場合、ユーザーは翻訳機能を使用するかどうかを選択することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: TranslateEnabled
  - GP 名: 翻訳を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): 管理用テンプレート/Microsoft Edge - 既定の設定 (ユーザーが上書き可能)/
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 値の名前: TranslateEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: TranslateEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### URLAllowlist

  #### 許可されている URL の一覧を定義する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ポリシーを設定すると、[URLBlocklist](#urlblocklist) の例外として、リストされた URL へのアクセスが提供されます。

[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) に従って、URL パターンを書式設定します。

このポリシーを使用して、制限付きブロック一覧の例外を開くことができます。 たとえば、ブロック一覧に "\*" を含めることですべての要求をブロックし、その上でこのポリシーを使用して限定した URL 一覧へのアクセスを許可することができます。 このポリシーを使用して、特定のスキーム、他のドメインのサブドメイン、ポート、特定のパスに対する例外を開くことができます。

最も具体的なフィルターが、URL がブロックされるか、または許可されるかを決定します。 許可一覧は、ブロック一覧よりも優先されます。

このポリシーは 1000 エントリに制限されており、それ以降のエントリは無視されます。

このポリシーを使用すると、ブラウザーは、"tel:" や "ssh:" のようなプロトコルのプロトコル ハンドラーとして登録されている外部アプリケーションを自動的に呼び出すことができます。

このポリシーを構成していない場合、[URLBlocklist](#urlblocklist) ポリシーのブロック リストに例外はなくなります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: URLAllowlist
  - GP 名: 許可されている URL の一覧を定義する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\URLAllowlist
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\1 = "contoso.com"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\2 = "https://ssl.server.com"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\3 = "hosting.com/good_path"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\4 = "https://server:8080/path"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\5 = ".exact.hostname.com"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: URLAllowlist
  - サンプル値:
``` xml
<array>
  <string>contoso.com</string>
  <string>https://ssl.server.com</string>
  <string>hosting.com/good_path</string>
  <string>https://server:8080/path</string>
  <string>.exact.hostname.com</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### URLBlocklist

  #### URL の一覧へのアクセスをブロックする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ブロックされている (ユーザーが読み込むことができない) サイトの一覧を URL パターンに基づいて定義します。

[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) に従って、URL パターンを書式設定します。

[URLAllowlist](#urlallowlist) ポリシーで、例外を定義することができます。 これらのポリシーは 1000 エントリに制限されており、それ以降のエントリは無視されます。

内部の "edge://*" URL をブロックすることは、お勧めできません。予期しないエラーを引き起こす場合があります。

このポリシーは、JavaScript による動的なページの更新を防止するものではありません。 たとえば、"contoso.com/abc" をブロックしても、ページが更新されない限り、ユーザーは "contoso.com" にアクセスし、"contoso.com/abc" へのリンクをクリックして訪問することができる可能性があります。

このポリシーを構成していない場合、ブロックされる URL はなくなります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: URLBlocklist
  - GP 名: URL の一覧へのアクセスのブロック
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\URLBlocklist
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\1 = "contoso.com"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\2 = "https://ssl.server.com"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\3 = "hosting.com/bad_path"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\4 = "https://server:8080/path"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\5 = ".exact.hostname.com"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\6 = "file://*"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\7 = "custom_scheme:*"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\8 = "*"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: URLBlocklist
  - サンプル値:
``` xml
<array>
  <string>contoso.com</string>
  <string>https://ssl.server.com</string>
  <string>hosting.com/bad_path</string>
  <string>https://server:8080/path</string>
  <string>.exact.hostname.com</string>
  <string>file://*</string>
  <string>custom_scheme:*</string>
  <string>*</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### UpdatePolicyOverride

  #### Microsoft Edge で利用できる更新プログラムを Microsoft Edge Update でどのように処理するかを指定します

  
  
  #### サポートされているバージョン:

  - macOS での 89 以降

  #### 説明

  このポリシーを有効にした場合、Microsoft Edge Update では、以下のオプションの構成方法に従って Microsoft Edge の更新プログラムを処理します。

- [自動サイレント更新のみ]: 更新プログラムは、定期的な更新チェックで検出された場合にのみ適用されます。

- [手動更新のみ]: 更新プログラムは、ユーザーが実行した手動更新チェックで検出された場合にのみ適用されます。 (アプリによっては、このオプション用のインターフェイスがない場合もあります。)

手動で更新する場合は、Microsoft Autoupdate を使用して、更新プログラムを定期的に確認してください。

このポリシーを有効にして構成しない場合、Microsoft Edge Update は自動的に更新プログラムを確認します。


ポリシー オプション マッピング:

* automatic-silent-only (automatic-silent-only) = 更新プログラムは、定期的な更新チェックで検出された場合にのみ適用されます。

* manual-only (manual-only) = 更新が適用されるのは、ユーザーが手動更新チェックを実行した場合のみです。 (アプリによっては、このオプション用のインターフェイスがない場合もあります。)

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: はい
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - String

  

  #### Mac の情報と設定
  
  - 基本設定キーの名前: UpdatePolicyOverride
  - サンプル値:
``` xml
<string>automatic-silent-only</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### UserAgentClientHintsEnabled

  #### ユーザー エージェント クライアント ヒント機能を有効にする (非推奨)

  >非推奨: このポリシーは推奨されなくなっています。 現在はサポートされていますが、将来のリリースで廃止されます。
  
  #### サポートされているバージョン:

  - Windows と macOS での 86 以降

  #### 説明

  このポリシーは、企業の Web コンテンツが ユーザーエージェント クライアントのヒント機能と互換していないことが判明した場合に、Web コンテンツの更新に時間を割くための短期のメカニズムとしてのみ機能することを目的としているため、推奨されていません。 Microsoft Edge バージョン 89 では機能しません。

ユーザー エージェント クライアント ヒント機能を有効にすると、ユーザー ブラウザー (ブラウザーのバージョンなど) と環境 (システム アーキテクチャなど) に関する情報を提供する細かな要求ヘッダーが送信されます。

これは追加機能ですが、新しいヘッダーにより、要求に含まれる文字を制限している一部の Web サイトが破損する場合があります。

このポリシーを有効にした場合、または構成しなかった場合は、ユーザー エージェント クライアント ヒント機能は有効になります。 このポリシーを無効にすると、この機能は使用できません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: UserAgentClientHintsEnabled
  - GP 名: ユーザー エージェント クライアント ヒント機能を有効にする (非推奨)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: UserAgentClientHintsEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - プリファレンス キーの名前: UserAgentClientHintsEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### UserDataDir

  #### ユーザー データ ディレクトリを設定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ユーザー データを保存するディレクトリを設定します。

このポリシーを有効にしている場合、ユーザーが "--user-data-dir" コマンドライン フラグを設定したかどうかにかかわらず、Microsoft Edge は指定されたディレクトリを使用します。

このポリシーを有効にしていない場合、既定のプロファイル パスが使用されますが、ユーザは "--user-data-dir" フラグを使用してそれを上書きすることができます。 プロファイルのディレクトリは、プロファイル パスの下の edge://version/ にあります。

データの損失やその他のエラーを避けるために、ボリュームのルート ディレクトリや別の目的で使用されているディレクトリには、このポリシーを構成しないでください。なぜなら、Microsoft Edge がコンテンツを管理しているからです。

使用できる変数の一覧については、「[https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041)」を参照してください。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: UserDataDir
  - GP 名: ユーザー データ ディレクトリを設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: UserDataDir
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"${users}/${user_name}/Edge"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: UserDataDir
  - サンプル値:
``` xml
<string>${users}/${user_name}/Edge</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### UserDataSnapshotRetentionLimit

  #### 緊急ロールバック時の使用のために保持するユーザーデータのスナップショット数を制限します。

  
  
  #### サポートされているバージョン:

  - Windows での 86 以降

  #### 説明

  主要なバージョンの更新の後、Microsoft Edge では、一時的なバージョンロールバックを必要とするような緊急事態に備えて、ユーザーの閲覧データの部分的スナップショットを作成します。 ユーザーが対応するスナップショットを持つバージョンについて一時的なロールバックを実行すると、スナップショット内のデータが復元されます。 これにより、ユーザーがブックマークやオートフィルデータなどの設定を保持できます。

このポリシーを設定しない場合、既定値の3スナップショットが使用されます。

このポリシーが設定されている場合、ユーザーが設定した制限数に応じて、古いスナップショットが削除されます。 このポリシーを0に設定すると、スナップショットは作成されません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - Integer

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: UserDataSnapshotRetentionLimit
  - GP 名: 緊急ロールバックの場合に使用されるユーザーデータのスナップショット数を制限します。
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: UserDataSnapshotRetentionLimit
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000003
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### UserFeedbackAllowed

  #### ユーザー フィードバックを許可する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge では、Edge フィードバック機能 (既定で有効) を使用して、ユーザーがフィードバック、提案、顧客アンケートを送信したり、ブラウザーの問題を報告したりすることができます。 また、既定では、ユーザーは Edge フィードバック機能を無効にする (オフにする) ことはできません。

このポリシーを有効にしているか、設定していない場合、ユーザーは Edge フィードバックを呼び出すことができます。

このポリシーを無効にしている場合、ユーザーは Edge フィードバックを呼び出すことができません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: UserFeedbackAllowed
  - GP 名: ユーザー フィードバックを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: UserFeedbackAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: UserFeedbackAllowed
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### VerticalTabsAllowed

  #### ブラウザーの側面にあるタブの垂直レイアウトの可用性を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 88 以降

  #### 説明

  タブがブラウザーの上部ではなく側面に垂直に配置されている別のレイアウトにユーザーがアクセスできるかどうかを構成します。
複数のタブが開いている場合、このレイアウトによってタブの表示と管理が容易になります。 サイト タイトルの視認性が向上し、整列されたアイコンをスキャンしやすくなり、タブを管理および閉じるためのスペースが増えました。

このポリシーを無効にすると、ユーザーは垂直タブ レイアウトをオプションとして使用できなくなります。

このポリシーを有効または無効にしても、タブ レイアウトは最上部に表示されますが、ユーザーは側面の垂直タブをオンにすることができます。


  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: VerticalTabsAllowed
  - GP 名: ブラウザーの側面にあるタブの垂直レイアウトの可用性を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - GP 固有の名前: VerticalTabsAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: VerticalTabsAllowed
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### VideoCaptureAllowed

  #### ビデオ キャプチャの許可またはブロック

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  サイトが動画をキャプチャできるかどうかを制御します。

有効にしているか、構成していない場合 (既定)、ユーザーは [VideoCaptureAllowedUrls](#videocaptureallowedurls) ポリシーの一覧で構成されている URL を持つサイトを除くすべてのサイトでビデオ キャプチャ アクセスについて確認を求められますが、一覧で構成されている URL を持つサイトでは、確認を求めるメッセージなしでアクセスが許可されます。

このポリシーを無効にしている場合、ユーザーに確認を求めるメッセージは表示されず、ビデオ キャプチャは [VideoCaptureAllowedUrls](#videocaptureallowedurls) ポリシーで構成されている URL に対してのみ許可されます。

このポリシーは内蔵カメラだけでなく、あらゆる種類のビデオ入力に影響します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: VideoCaptureAllowed
  - GP 名: ビデオ キャプチャの許可またはブロック
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: VideoCaptureAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: VideoCaptureAllowed
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### VideoCaptureAllowedUrls

  #### アクセス許可を要求することなくビデオ キャプチャ デバイスにアクセスできるサイト

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  URL パターンに基づいて、ユーザーにアクセス許可を求めずにビデオ キャプチャ デバイスを使用することができる Web サイトを指定します。 この一覧のパターンは、要求 URL のセキュリティ オリジンと照合されます。 それらが一致する場合、サイトには自動的にビデオ キャプチャ デバイスへのアクセス許可が付与されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: VideoCaptureAllowedUrls
  - GP 名: アクセス許可を要求することなくビデオ キャプチャ デバイスにアクセスできるサイト
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\VideoCaptureAllowedUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\VideoCaptureAllowedUrls\1 = "https://www.contoso.com/"
SOFTWARE\Policies\Microsoft\Edge\VideoCaptureAllowedUrls\2 = "https://[*.]contoso.edu/"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: VideoCaptureAllowedUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com/</string>
  <string>https://[*.]contoso.edu/</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### WPADQuickCheckEnabled

  #### WPAD の最適化を設定する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  Microsoft Edge で、WPAD (Web プロキシ自動発見) の最適化をオフにすることができます。

このポリシーを無効にしている場合、WPAD の最適化は無効になり、ブラウザーは DNS ベースの WPAD サーバーにより長く待機させられるようになります。

ポリシーを有効にしているか、構成していない場合、WPAD の最適化が有効になります。

このポリシーが有効かどうかや、有効にするための方法に関係なく、ユーザーが WPAD の最適化設定を変更することはできません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: WPADQuickCheckEnabled
  - GP 名: WPAD の最適化を設定する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: WPADQuickCheckEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: WPADQuickCheckEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### WebAppInstallForceList

  #### 強制インストールする Web アプリの一覧を構成する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 80 以降

  #### 説明

  このポリシーを構成して、ユーザーの操作なしでサイレント インストールし、ユーザーがアンインストールまたはオフにできない Web アプリの一覧を指定します。

ポリシーの各リスト アイテムは、必須のメンバー URL (インストールする Web アプリの URL) を持つオブジェクトです。

3 つのオプション メンバー:
- default_launch_container (新しいタブで Web アプリが開くウィンドウ モードが既定に指定されます。)

- create_desktop_shortcut (Linux および Windows デスクトップ ショートカットを作成する場合は True。)

- override_app_name (Microsoft Edge 89 以降、プログレッシブ Web アプリではない場合はアプリ名を上書きできます。または、プログレッシブ Web アプリの場合は一時的にインストールされますが、インストールを完了する前に認証が必要なアプリ名です。)

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - Dictionary

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: WebAppInstallForceList
  - GP 名: 強制インストールする Web アプリの一覧を構成する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: WebAppInstallForceList
  - 値の種類: REG_SZ

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\WebAppInstallForceList = [
  {
    "create_desktop_shortcut": true, 
    "default_launch_container": "window", 
    "url": "https://www.contoso.com/maps"
  }, 
  {
    "default_launch_container": "tab", 
    "url": "https://app.contoso.edu"
  }, 
  {
    "default_launch_container": "window", 
    "override_app_name": "Editor", 
    "url": "https://app.contoso.com/editor"
  }
]
```

  ##### コンパクト サンプル値:

  ```
  SOFTWARE\Policies\Microsoft\Edge\WebAppInstallForceList = [{"create_desktop_shortcut": true, "default_launch_container": "window", "url": "https://www.contoso.com/maps"}, {"default_launch_container": "tab", "url": "https://app.contoso.edu"}, {"default_launch_container": "window", "override_app_name": "Editor", "url": "https://app.contoso.com/editor"}]
  ```
  

  #### Mac の情報と設定
  
  - 基本設定キーの名前: WebAppInstallForceList
  - サンプル値:
``` xml
<key>WebAppInstallForceList</key>
<array>
  <dict>
    <key>create_desktop_shortcut</key>
    <true/>
    <key>default_launch_container</key>
    <string>window</string>
    <key>url</key>
    <string>https://www.contoso.com/maps</string>
  </dict>
  <dict>
    <key>default_launch_container</key>
    <string>tab</string>
    <key>url</key>
    <string>https://app.contoso.edu</string>
  </dict>
  <dict>
    <key>default_launch_container</key>
    <string>window</string>
    <key>override_app_name</key>
    <string>Editor</string>
    <key>url</key>
    <string>https://app.contoso.com/editor</string>
  </dict>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### WebCaptureEnabled

  #### Microsoft Edge で Web キャプチャ機能を有効にする

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 87 以降

  #### 説明

  Microsoft Edge の Web キャプチャ機能を有効にします。これにより、ユーザーが Web コンテンツをキャプチャし、インクツールを使用してキャプチャに注釈を付けることができます。
このポリシーを有効にするか、構成しない場合、Web キャプチャ オプションはコンテキスト メニュー、[その他の設定] メニューに表示され、キーボード ショートカットのCTRL + SHIFT + Sを使用します。
このポリシーを無効にすると、ユーザーは Microsoft Edge の Web キャプチャ機能にアクセスできなくなります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: WebCaptureEnabled
  - GP 名: Microsoft Edge で Web キャプチャ機能を有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: WebCaptureEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: WebCaptureEnabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### WebComponentsV0Enabled

  #### M84 まで Web コンポーネント v0 API をもう一度有効にする (不使用)

  
  >不使用: このポリシーは廃止されており、Microsoft Edge 84 以降は機能しません。
  #### サポートされているバージョン:

  - Windows と macOS での 80 以降、84 まで

  #### 説明

  このポリシーは、Microsoft Edge バージョン 85 までこれらの機能を選択的に再度有効にすることができるため、機能しません。 Web Components v0 API (Shadow DOM v0、Custom Elements v0、HTML Imports) は 2018 年に非推奨となっており、Microsoft Edge バージョン 80 以降は既定で無効化されています。

このポリシーを True に設定している場合、すべてのサイトで Web Components v0 の機能が有効になります。

このポリシーを false に設定しているか、設定していない場合、Web Components v0 の機能は Microsoft Edge バージョン 80 以降は既定で無効化されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: WebComponentsV0Enabled
  - GP 名: M84 まで Web コンポーネント v0 API をもう一度有効にする (不使用)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: WebComponentsV0Enabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: WebComponentsV0Enabled
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### WebDriverOverridesIncompatiblePolicies

  #### WebDriver が互換性のないポリシーを上書きすることを許可する (非推奨)

  >非推奨: このポリシーは推奨されなくなっています。 現在はサポートされていますが、将来のリリースで廃止されます。
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降、84 まで

  #### 説明

  WebDriver は既存のすべてのポリシーと互換性を持つようになったため、このポリシーは機能しません。

このポリシーでは、WebDriver 機能のユーザーがその操作を妨げる可能性のあるポリシーを上書きすることができます。

現在このポリシーは、[SitePerProcess](#siteperprocess) と [IsolateOrigins](#isolateorigins) ポリシーを無効にしています。

このポリシーを有効にしている場合、WebDriver は互換性のないポリシーを上書きすることができるようになります。
このポリシーを無効にしているか、構成していない場合、WebDriver が互換性のないポリシーを上書きすることはできません。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: WebDriverOverridesIncompatiblePolicies
  - GP 名: WebDriver が互換性のないポリシーを上書きすることを許可する (非推奨)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: WebDriverOverridesIncompatiblePolicies
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: WebDriverOverridesIncompatiblePolicies
  - サンプル値:
``` xml
<true/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### WebRtcAllowLegacyTLSProtocols

  #### WebRTC で従来の TLS/DTLS ダウングレードを許可する (非推奨)

  >非推奨: このポリシーは推奨されなくなっています。 現在はサポートされていますが、将来のリリースで廃止されます。
  
  #### サポートされているバージョン:

  - Windows と macOS での 88 以降

  #### 説明

  このポリシーを有効にすると、WebRTC ピア接続は、TLS/DTLS (DTLS 1.0、TLS 1.0、および TLS 1.1) プロトコルの不使用バージョンにダウングレードできます。
このポリシーを無効にするか、設定しない場合、これらの TLS/DTLS バージョンは無効になります。

このポリシーは一時的なものであり、Microsoft Edge の将来のバージョンで削除される予定です。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: WebRtcAllowLegacyTLSProtocols
  - GP 名: WebRTC で従来の TLS/DTLS ダウングレードを許可する (非推奨)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: WebRtcAllowLegacyTLSProtocols
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000000
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: WebRtcAllowLegacyTLSProtocols
  - サンプル値:
``` xml
<false/>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### WebRtcLocalIpsAllowedUrls

  #### WebRTC によるローカル IP アドレスの公開を管理する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 80 以降

  #### 説明

  WebRTC が公開する必要があるローカル IP アドレスのオリジン (URL) やホスト名のパターン ("*contoso.com*" など) の一覧を指定します。

このポリシーを有効にし、オリジン (URL) やホスト名のパターンの一覧を設定している場合、edge://flags/#enable-webrtc-hide-local-ips-with-mdns が有効になっているときに、WebRTC は一覧のパターンに一致するローカル IP アドレスを公開します。

このポリシーを無効にしているか、構成していない状態で、edge://flags/#enable-webrtc-hide-local-ips-with-mdns が有効になっている場合、WebRTC はローカル IP アドレスを公開しません。 ローカル IP アドレスは、mDNS ホスト名で隠されています。

このポリシーを有効または無効にしているか、構成していない状態で、edge://flags/#enable-webrtc-hide-local-ips-with-mdns が無効になっている場合、WebRTC はローカル IP アドレスを公開します。

このポリシーは、管理者が必要とする可能性のあるローカル IP アドレスの保護を弱めます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: WebRtcLocalIpsAllowedUrls
  - GP 名: WebRTC によるローカル IP アドレスの公開を管理する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge\WebRtcLocalIpsAllowedUrls
  - パス (推奨): なし
  - 値の名前: 1、2、3、...
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\WebRtcLocalIpsAllowedUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\WebRtcLocalIpsAllowedUrls\2 = "*contoso.com*"

```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: WebRtcLocalIpsAllowedUrls
  - サンプル値:
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>*contoso.com*</string>
</array>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### WebRtcLocalhostIpHandling

  #### WebRTC によるローカル IP アドレスの公開を制限する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  ユーザーのローカル IP アドレスを WebRTC が公開するかどうかを設定することができます。

このポリシーを "AllowAllInterfaces" または "AllowPublicAndPrivateInterfaces" に設定している場合、WebRTC はローカル IP アドレスを公開します。

このポリシーを "AllowPublicInterfaceOnly" または "DisableNonProxiedUdp" に設定している場合、WebRTC はローカル IP アドレスを公開しません。

このポリシーを設定していないか、無効にしている場合、WebRTC はローカル IP アドレスを公開します。

ポリシー オプション マッピング:

* AllowAllInterfaces (既定) = すべてのインターフェイスを許可します。 これは、ローカル IP アドレスを公開します

* AllowPublicAndPrivateInterfaces (default_public_and_private_interfaces) = HTTP の既定のルート上でパブリック インターフェイスとプライベート インターフェイスを許可します。 これは、ローカル IP アドレスを公開します

* AllowPublicInterfaceOnly (default_public_interface_only) = HTTP の既定のルート上でパブリック インターフェイスを許可します。 これは、ローカル IP アドレスを公開しません

* DisableNonProxiedUdp (disable_non_proxied_udp) = プロキシ サーバーが UDP をサポートしていない限り、TCP を使用します。 これは、ローカル IP アドレスを公開しません

このポリシーを構成する場合は、上記の情報を使用します。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: WebRtcLocalhostIpHandling
  - GP 名: WebRTC によるローカル IP アドレスの公開を制限する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: WebRtcLocalhostIpHandling
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"default"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: WebRtcLocalhostIpHandling
  - サンプル値:
``` xml
<string>default</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### WebRtcUdpPortRange

  #### WebRTC が使用するローカル UDP ポートの範囲を制限する

  
  
  #### サポートされているバージョン:

  - Windows と macOS での 77 以降

  #### 説明

  WebRTC が使用する UDP ポートの範囲を、指定したポート間隔に制限します (エンドポイントを含む)。

このポリシーを構成することで、WebRTC が使用できるローカル UDP ポートの範囲を指定します。

このポリシーを構成していないか、空の文字列または無効なポート範囲に対して設定した場合、WebRTC は任意の利用可能なローカル UDP ポートを使用することができます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - String

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: WebRtcUdpPortRange
  - GP 名: WebRTC が使用するローカル UDP ポートの範囲を制限する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: WebRtcUdpPortRange
  - 値の種類: REG_SZ

  ##### サンプル値:

```
"10000-11999"
```

  #### Mac の情報と設定
  
  - 基本設定キーの名前: WebRtcUdpPortRange
  - サンプル値:
``` xml
<string>10000-11999</string>
```
  

  [ページのトップへ](#microsoft-edge---policies)

  ### WebWidgetAllowed

  #### Web ウィジェットを許可する

  
  
  #### サポートされているバージョン:

  - Windows での 88 以降

  #### 説明

  Web ウィジェットを有効にします。 有効にすると、ユーザーはウィジェットを使用してデスクトップやアプリケーションから Web を検索することができます。 このウィジェットは、Web 提案を表示し、すべての Web 検索を Microsoft Edge で開く検索ボックスを提供します。 検索ボックスは、検索 (Powered by Bing) と URL の提案を提供します。 ウィジェットにはフィード タイルも含まれており、ユーザーがクリックすると新しい Microsoft Edge ブラウザーのタブやウィンドウで msn.com の詳細情報を閲覧することができます。 フィード タイルには広告が含まれている場合があります。 ウィジェットは、Microsoft Edge の設定か Microsoft Edge の [その他のツール] メニューから起動することができます。

このポリシーを有効にしているか、または構成していない場合、Web ウィジェットはすべてのプロファイルで自動的に有効になります。
Microsoft Edge の設定では、ウィジェットを起動するためのオプションが表示されます。
Microsoft Edge の設定では、ユーザーに対して Windows の起動時にウィジェットを実行するためのメニュー項目が表示されます (自動起動)。
起動時にウィジェットを有効にするオプションは、[WebWidgetIsEnabledOnStartup](#webwidgetisenabledonstartup) ポリシーが有効な場合に切り替えられます。
[WebWidgetIsEnabledOnStartup](#webwidgetisenabledonstartup) が無効になっているか、または構成されていない場合、起動時にウィジェットを有効にするオプションはオフに切り替えられます。
ユーザーに対しては、Microsoft Edge の [その他のツール] メニューからウィジェットを起動するためのメニュー項目が表示されます。 ユーザーは [その他のツール] からウィジェットを起動することができます。
ウィジェットは、システム トレイの "終了" オプションでオフにするか、タスク バーからウィジェットを閉じることでオフにすることができます。 自動起動が有効になっている場合、システムの再起動時にウィジェットも再起動されます。

このポリシーを無効にすると、Web ウィジェットはすべてのプロファイルで無効になります。
Microsoft Edge の設定からウィジェットを起動するオプションは無効になります。
Windows の起動時にウィジェットを起動するオプション (自動起動) は無効になります。
Microsoft Edge の [その他のツール] メニューからウィジェットを起動するオプションは無効になります。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: WebWidgetAllowed
  - GP 名: Web ウィジェットを有効にする
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: WebWidgetAllowed
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### WebWidgetIsEnabledOnStartup

  #### Windows 起動時に Web ウィジェットを有効にする

  
  
  #### サポートされているバージョン:

  - Windows での 88 以降

  #### 説明

  Windows の起動時に Web ウィジェットが起動するようにします。

有効にしている場合: 既定で Windows の起動時に Web ウィジェットが起動します。
[WebWidgetAllowed](#webwidgetallowed) ポリシーを介してウィジェットが無効化されている場合、このポリシーは Windows の起動時にウィジェットを起動しません。

このポリシーを無効している場合: Web ウィジェットはすべてのプロファイルで Windows の起動時に起動しません。
Windows の起動時にウィジェットを起動するオプションは、Microsoft Edge の設定で無効化され、オフに切り替えられます。

このポリシーを構成していない場合: Web ウィジェットはすべてのプロファイルで Windows の起動時に起動しません。
Windows の起動時にウィジェットを起動するオプションは、Microsoft Edge の設定でオフに切り替えられます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: WebWidgetIsEnabledOnStartup
  - GP 名: Windows の起動時に Web ウィジェットを許可する
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: WebWidgetIsEnabledOnStartup
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)

  ### WinHttpProxyResolverEnabled

  #### Windows プロキシ リゾルバーを使用する (非推奨)

  >非推奨: このポリシーは推奨されなくなっています。 現在はサポートされていますが、将来のリリースで廃止されます。
  
  #### サポートされているバージョン:

  - Windows での 84 以降

  #### 説明

  このポリシーは、将来のリリースで同様の機能に置き換えられるため、廃止されました。https://crbug.com/1032820 を参照してください。

Windows を使用して、Microsoft Edge に組み込まれているプロキシ リゾルバーの代わりに、すべてのブラウザー ネットワークのプロキシを解決します。 Windows プロキシ リゾルバーは、DirectAccess/NRPT などの Windows プロキシ機能を有効にします。

このポリシーには、https://crbug.com/644030 で説明される問題が含まれます。 [ProxyPacUrl](#proxypacurl) ポリシーを介して設定された PAC ファイルを含む、PAC ファイルが Windows コードによりフェッチおよび実行されます。 PAC ファイルのネットワーク フェッチは Microsoft Edge コードの代わりに Windows 経由で発生するので、[DnsOverHttpsMode](#dnsoverhttpsmode) などのネットワーク ポリシーは PAC ファイルのネットワーク フェッチには適用されません。

このポリシーを有効にすると、Windows プロキシ リゾルバーが使用されます。

このポリシーを無効にするか、構成しない場合は、Microsoft Edge プロキシ リゾルバーが使用されます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: いいえ - ブラウザの再起動が必要

  #### ［データの種類］:

  - ブール値

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: WinHttpProxyResolverEnabled
  - GP 名: Windows プロキシ リゾルバーを使用する (非推奨)
  - GP パス (必須): 管理用テンプレート/Microsoft Edge/
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdge.admx

  ##### Windows レジストリの設定

  - パス (必須): SOFTWARE\Policies\Microsoft\Edge
  - パス (推奨): なし
  - 値の名前: WinHttpProxyResolverEnabled
  - 値の種類: REG_DWORD

  ##### サンプル値:

```
0x00000001
```

  

  [ページのトップへ](#microsoft-edge---policies)


## 関連項目

- [Microsoft Edge の構成](configure-microsoft-edge.md)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Office セキュリティ ベースライン ブログ](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)