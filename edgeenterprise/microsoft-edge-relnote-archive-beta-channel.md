---
title: Microsoft Edge Beta チャネルのアーカイブされたリリース ノート
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 03/17/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Beta チャネルのアーカイブされたリリース ノート
ms.openlocfilehash: fd61e531db52d380e07588c1f12df4595f161841
ms.sourcegitcommit: 6a3787dead062e4a0860adbc570229974dcaee07
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442413"
---
# <a name="archived-release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge Beta チャネルのアーカイブされたリリース ノート

これらのリリース ノートでは、Microsoft Edge Beta チャネルに含まれている新機能とセキュリティ以外の更新プログラムに関する情報を提供します。 Microsoft Edge チャネルを理解するには、「[Microsoft Edge チャネルの概要](microsoft-edge-channels.md)」を参照してください。 すべてのセキュリティの更新プログラムは、[ここ](microsoft-edge-relnotes-security.md)に記載されています。

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
<!-- major 86 -->
## <a name="version-86062211-september-9"></a>バージョン 86.0.622.11: 9 月 9 日

### <a name="feature-updates"></a>機能更新プログラム

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

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

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

#### <a name="deprecated-policies"></a>廃止されたポリシー

- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - 使用状況とクラッシュ関連のデータレポートを有効にします。
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Microsoft サービスを改善するためにサイト情報を送信します。

#### <a name="obsoleted-policy"></a>非推奨ポリシー

[TLS13HardeningForLocalAnchorsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#tls13hardeningforlocalanchorsenabled) - ローカル トラスト アンカーの TLS 1.3 セキュリティ機能を有効にします。

#### <a name="policy-caption-changed"></a>変更されたポリシーのキャプション

[NativeWindowOcclusionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled) - ネイティブ ウィンドウ オクルージョンを有効にします。

#### <a name="policy-description-changed"></a>変更されたポリシーの説明

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

- **DevToolsの更新** 次の更新プログラムの詳細については、 [DevTools の新機能 (Microsoft Edge 85)](https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/whats-new/2020/06/devtools)を参照してください。

   - Microsoft Edge の DevTools は Surface Duo エミュレーションをサポートしています。 Microsoft Edge の DevTools を使用して Surface Duo をエミュレートすることができます。これにより、ユーザーのweb コンテンツの表示をデュアルスクリーンデバイスでテストできます。 このテストを DevTools で有効にするには、Windows の場合はCtrl+Shift+Mを押しながら、Device Modeに入るか、macOSの場合は、 Command + Shift + M キーを押して、デバイスのドロップダウンリストから Surface Duo を選択します。
   - Microsoft Edge DevTools を使用すると、キーボードショートカットを VS コードと一致させることができます。 Microsoft Edge の DevTools では、使用しているエディターや IDE に合わせて DevTools のキーボードショートカットをカスタマイズできます。 Microsoft Edge 85 で、VS コードに対して DevTools のキーボードショートカットを一致させる機能を追加します。 この変更は、VS コードと DevTools の生産性向上に役立ちます。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

13 個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [AutoLaunchProtocolsFromOrigins](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autolaunchprotocolsfromorigins) -ユーザーにプロンプ​​トを表示せずに、リストされたオリジンから外部アプリケーションを起動できるプロトコルのリストを定義します。
- [AutoOpenAllowedForURLs](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoopenallowedforurls) -AutoOpenFileTypes を適用できるURL。
- [AutoOpenFileTypes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoopenfiletypes) -ダウンロード時に自動的に開く必要があるファイルの種類の一覧。
- [DefaultSearchProviderContextMenuAccessAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultsearchprovidercontextmenuaccessallowed) -既定の検索プロバイダーコンテキストメニューの検索アクセスを許可します。
- [EnableSha1ForLocalAnchors](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors)-ローカルトラストアンカーによって発行されたときに SHA-1 を使用して署名された証明書を許可します。
- [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings)-ドメイン上の指定したファイルの種類についての警告に基づいて、ダウンロードファイルの種類の拡張子を無効にします。
- [IntensiveWakeUpThrottlingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#intensivewakeupthrottlingenabled)-IntensiveWakeUpThrottling 機能を制御します。
- [NewTabPagePrerenderEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpageprerenderenabled)-新しいタブページのプリロードを有効にして、表示を高速化します。
- [NewTabPageSearchBox](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesearchbox) - 新しいタブ ページ検索ボックスの機能を構成します。
- [PasswordMonitorAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordmonitorallowed) - パスワードが安全でないことが判明した場合にユーザーに警告することを許可します。
- [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled)-Microsoft Edgeプロファイルデータ のローミングコピーの使用を有効にします。
- [RoamingProfileLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilelocation)-移動プロファイルディレクトリを設定します。
- [TLSCipherSuiteDenyList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#tlsciphersuitedenylist)-TLS 暗号スイートを無効に指定します。

#### <a name="obsoleted-policies"></a>不使用のポリシー

- [EnableDomainActionsDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledomainactionsdownload) - Microsoft からのドメイン アクションのダウンロードを有効にします。
- [WebComponentsV0Enabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcomponentsv0enabled) - Web コンポーネント v0 API ユニット M84 を再有効化する。
- [WebDriverOverridesIncompatiblePolicies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webdriveroverridesincompatiblepolicies) - WebDriverに 互換性のないポリシーのオーバーライドを許可します。

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

- このバージョンの Microsoft Edge では、Internet Explorer モードでのサイト一覧のダウンロード時間が改善されました。  キャッシュされたサイト リストがない場合、Internet Explorer モードのサイト一覧のダウンロードのダウンロード遅延が0秒に削減されました （以前の60秒待ちから短縮）。 また、サイト一覧がダウンロードされるまで、Internet Explorer モードのホームページ ナビゲーションを遅延する必要がある場合のために、グループ ポリシーのサポートも追加しました。 詳細については、「[DelayNavigationsForInitialSiteListDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#delaynavigationsforinitialsitelistdownload)」 を参照してください。

- Microsoft Edge では、Windows 10 で "管理者として実行" する場合に、ユーザーがブラウザーにサインインできるようになりました。 これにより、Windows サーバーで Microsoft Edge を実行しているユーザー、またはリモートデスクトップやサンドボックスのシナリオでの使用に役立ちます。

- Microsoft Edge は、全画面表示モードでフル マウス サポートが提供されるようになりました。 これで、全画面表示モードを終了しなくても、マウスを使用してタブ、アドレス バーなどの項目にアクセスできます。

- オンライン購入を改善します。 保存したデビット カードやクレジット カードにカスタム ニックネームを追加します。 これで、オンライン購入時に、クレジット カードを区別して差別化できるようになりました。 デビット カードやクレジット eカードにニックネームを付けることで、オートフィルを使用して支払い方法を選択する際に正しいカードを選ぶことができます。

- TLS/1.0 および TLS/1.1 は既定では無効になっています。 影響を受けるサイトを検出するには、[*edge://flags/#display-レガシ-tls 警告*] フラグを設定すると、Microsoft Edge で、レガシー TLS プロトコルを必要とするページを読み込むときに、ブロック不可の "セキュリティで保護されていない" という通知が表示されます。 [SSLVersionMin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#sslversionmin) ポリシーにより、TLS/1.0 と TLS/1.1 を再有効化することが可能になります。 このポリシーは、Microsoft Edge バージョン88以上で利用可能になります。 詳細については、「[Microsoft Edge 向けのサイトの互換性に影響する変更点](https://docs.microsoft.com/microsoft-edge/web-platform/site-impacting-changes)」 を参照してください。

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

- [AppCacheForceEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#appcacheforceenabled) - 既定でオフになっている場合でも、App Cache 機能を再度有効にすることを許可します。
- [ApplicationGuardContainerProxy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#applicationguardcontainerproxy) - Application Guard コンテナー プロキシです。
- [DelayNavigationsForInitialSiteListDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#delaynavigationsforinitialsitelistdownload) - タブ ナビゲーションの前にエンタープライズ モード サイト一覧が使用できるようにします。
- [NativeWindowOcclusionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled) - ネイティブ ウィンドウを非表示にします。
- [NavigationDelayForInitialSiteListDownloadTimeout](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#navigationdelayforinitialsitelistdownloadtimeout) - エンタープライズ モード サイト一覧のタブ ナビゲーションの遅延時間を設定します。

#### <a name="deprecated-policies"></a>廃止されたポリシー

- [AllowSyncXHRInPageDismissal](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#allowsyncxhrinpagedismissal) - ページが同期 XHR 要求をページの解除中に送信できるようにします。
- [BuiltinCertificateVerifierEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#builtincertificateverifierenabled) - 組み込みの証明書検証機能を使用してサーバー証明書を検証するかどうかを決定します。
- [StricterMixedContentTreatmentEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#strictermixedcontenttreatmentenabled) - 混合コンテンツに対してより厳密な処理を有効にします。

#### <a name="obsoleted-policy"></a>非推奨ポリシー

[ForceNetworkInProcess](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcenetworkinprocess) - ブラウザー プロセスでネットワーク コードを強制的に実行します。

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

- 拡張機能の同期が利用可能になりました。 すべてのデバイスで拡張機能を同期できるようになりました。 Microsoft Store と Chrome ウェブストアの両方から入手した拡張機能が Microsoft Edge と同期します。 この機能を使用するには: メニュー バーの省略記号 (**…**) をクリックし、[**設定**] を選択します。 [プロファイル] で、[**同期**] をクリックして、同期オプションを表示します。 **Profiles/Sync** で、トグルを使用して拡張機能を有効にします。 [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) グループ ポリシーを使用して、拡張機能の同期を無効にすることができます。

- ブロックされた安全でないダウンロードに関するダウンロード管理ページのメッセージを改善しました。

- イマーシブ リーダーの改善:
  - イマーシブ リーダーの品詞エクスペリエンスで副詞のサポートが追加されました。 イマーシブ リーダーで記事を読みながら、文法ツールを開き、品詞内の副詞をオンにして、ページ上のすべての副詞を強調表示します。
  - Web ページ上の任意のコンテンツを選択し、イマーシブ リーダーで開く機能が追加されました。 この機能により、ユーザーはすべての Web サイトでイマーシブ リーダーとすべての学習ツール (行フォーカスや 音声読み上げなど) を使用できます。

- Link doctor では、ユーザーが URL を誤って入力したときにホスト修正が行われ、検索クエリがユーザーに提供されます。 次に、例を示します。 <br>
ユーザーが "powerbi" を誤って "powerbbi".com と入力したとします。 Link doctor からは、修正案として "powerbi".com が提案され、ユーザーが別の違うサイトを探している場合も想定し "powerbbi" を検索するためのリンクが作成されます。

- ユーザーは、特定のサイトの外部プロトコルを起動するという設定を保存できます。 ユーザーは、[ExternalProtocolDialogShowAlwaysOpenCheckbox]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#externalprotocoldialogshowalwaysopencheckbox) ポリシーを構成して、この機能を有効または無効にすることができます。

- ユーザーは、Microsoft Edge の **[設定]** から直接 Microsoft Edge を既定のブラウザーとして設定できます。 この機能により、ユーザーは、オペレーティング システムの設定を検索せずに、ブラウザー自体のコンテキスト内で既定のブラウザーを簡単に変更することができます。 この機能を使用するには、*edge://settings/defaultBrowser* に移動し、**[既定に設定]** をクリックします。

- 新しいリモート デバッグのサポートや UI の改善など、DevTools の機能もいくつか更新されています。 詳細については、「[DevTools の新着情報 (Microsoft Edge 83)](https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/whats-new/2020/03/devtools)」 を参照してください。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

15 個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [AllowSurfGame](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#allowsurfgame) - ゲームのサーフィンを許可します。
- [AllowTokenBindingForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#allowtokenbindingforurls) - Microsoft Edge がトークンのバインドの確立を試行するサイトのリストを構成します。
- [BingAdsSuppression](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#bingadssuppression) - Bing 検索結果ですべての広告をブロックします。
- [BuiltinCertificateVerifierEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#builtincertificateverifierenabled) - 組み込みの証明書検証機能を使用してサーバー証明書を検証するかどうかを決定します。
- [ClearCachedImagesAndFilesOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#clearcachedimagesandfilesonexit) - Microsoft Edge を閉じるときに、キャッシュされた画像とファイルをクリアします。
- [ConfigureShare](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureshare) - 共有エクスペリエンスを構成します。
- [DeleteDataOnMigration](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#deletedataonmigration) - 移行時に古いブラウザー データを削除します。
- [DnsOverHttpsMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#dnsoverhttpsmode) - DNS over HTTPS モードを制御します。
- [DnsOverHttpsTemplates](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#dnsoverhttpstemplates) - 目的の DNS over HTTPS リゾルバーの URI テンプレートを指定します。
- [FamilySafetySettingsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#familysafetysettingsenabled) - ユーザーがファミリー セーフティを設定できるようにします。
- [LocalProvidersEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#localprovidersenabled) - ローカル プロバイダーからのおすすめを許可します。
- [ScrollToTextFragmentEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#scrolltotextfragmentenabled) - URL フラグメントで指定されたテキストへのスクロールを有効にします。
- [ScreenCaptureAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#screencaptureallowed) - 画面キャプチャを許可または拒否します。
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) - 同期から除外される種類の一覧を構成します。
- [NativeWindowOcclusionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled) - ネイティブ ウィンドウを非表示にします。

#### <a name="deprecated-policy"></a>廃止されたポリシー

このリリースでは、次のポリシーが引き続き機能します。 これは、将来のリリースで「廃止」される予定です。

[EnableDomainActionsDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledomainactionsdownload) Microsoft からのドメイン アクションのダウンロードを有効にする

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

- [AmbientAuthenticationInPrivateModesEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#ambientauthenticationinprivatemodesenabled) - InPrivate およびゲスト プロファイルの環境認証を有効にします。 
- [AudioSandboxEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#audiosandboxenabled) - オーディオ サンドボックスの実行を許可します。
- [ForceLegacyDefaultReferrerPolicy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcelegacydefaultreferrerpolicy) - no-referrer-when-downgrade の既定の参照元ポリシーを使用します。
- [GloballyScopeHTTPAuthCacheEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#globallyscopehttpauthcacheenabled) - グローバル スコープの HTTP 認証キャッシュを有効にします。
- [ImportExtensions](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#importextensions) - 拡張機能のインポートを許可します。
- [ImportCookies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#importcookies) - Cookie のインポートを許可します。
- [ImportShortcuts](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#importshortcuts) - ショートカットのインポートを許可します。
- [InternetExplorerIntegrationSiteRedirect](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationsiteredirect) - Internet Explorer モード ページから起動した場合、未構成サイトへの「ページ内」ナビゲーションの動作を指定します。
- [OmniboxMSBProviderEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#omniboxmsbproviderenabled) - Omnibox で Microsoft Search for Business プロバイダーを有効にします。 
- [StricterMixedContentTreatmentEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#strictermixedcontenttreatmentenabled) - 混合コンテンツに対してより厳密な処理を有効にします。
- [TLS13HardeningForLocalAnchorsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#tls13hardeningforlocalanchorsenabled) - ローカル トラスト アンカーの TLS 1.3 セキュリティ機能を有効にします。
- [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin) - Azure AD ドメイン アカウントがない場合、Active Directory ドメイン アカウントで自動サインインを構成します。

#### <a name="deprecated-policies"></a>廃止されたポリシー

このリリースでは、次のポリシーが引き続き機能します。 これらは、将来のリリースで「廃止」される予定です。

- [WebComponentsV0Enabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcomponentsv0enabled) - M84 まで Web コンポーネント v0 API を再度有効にします。
- [WebDriverOverridesIncompatiblePolicies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webdriveroverridesincompatiblepolicies) - WebDriverに 互換性のないオーバーライドを許可します。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)