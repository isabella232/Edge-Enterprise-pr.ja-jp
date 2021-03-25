---
title: Microsoft Edge Stable チャネルのアーカイブされたリリース ノート
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 03/03/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Stable チャネルのアーカイブされたリリース ノート
ms.openlocfilehash: b12d8c34e2936b7f1c8dbc0573672273a74beabc
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11448011"
---
# <a name="archived-release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge Stable チャネルのアーカイブされたリリース ノート

これらのリリース ノートでは、Microsoft Edge Stable チャネルに含まれている新機能とセキュリティ以外の更新プログラムに関する情報を提供します。 すべてのセキュリティの更新プログラムは、[ここ](microsoft-edge-relnotes-security.md)に記載されています。

## <a name="version-86062238-october-9"></a>バージョン 86.0.622.38 : 10 月 9 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#october-9-2020)に記載されています

### <a name="feature-updates"></a>機能更新プログラム

* **Microsoft Edge の以前のバージョンにロールバック。** ロールバック機能では、Microsoft Edge の最新バージョンに問題がある場合、管理者は Microsoft Edge を既知の正常なバージョンに戻すことができます。 **注:** Stable バージョン 86.0.622.38 は、ロールバック先となることができる最初のバージョンです。これは、安定バージョン87が、ロールバック元となる準備ができた最初のバージョンという意味でもあります。 [詳しくはこちらをご覧ください](edge-learnmore-rollback.md)。

* **エンタープライズ全体で、同期の有効化を既定で強制できます。**  管理者は既定で、[ForceSync](./microsoft-edge-policies.md#forcesync) ポリシーを使用して、Azure Active Directory (Azure AD) アカウントに対して同期を有効にできます。

* **Windows 7および8.1 でのプロファイル の自動切り替え。** 現在 Windows 10 の Microsoft Edge で利用可能なプロフィールの自動切り替えは、ダウンレベルの Windows (Windows 7、8.1) に拡張されました。 詳細については、ブログ記事「[プロファイルの自動切り替え](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/)」を参照してください。

* **SameSite=既定で緩い Cookie**。 Web セキュリティとプライバシーを向上させるために、Cookie は、既定では、[SameSite=Lax](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite) 処理に設定されます。 つまり、Cookie はファーストパーティのコンテキストでのみ送信され、サードパーティに送信される要求では省略されます。 この変更により、サードパーティのリソースが正しく機能するために Cookie を必要とする Web サイトに互換性の影響が生じる可能性があります。 このような Cookie を許可するために、Web 開発者は、Cookie の設定時に明示的な `SameSite=none` および `Secure` 属性を追加することにより、サードパーティのコンテキストから設定および送信する必要がある Cookie にマークを付けることができます。 特定のサイトをこの変更から除外することを希望する企業は、[LegacySameSiteCookieBehaviorEnabledForDomainList](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabledfordomainlist) ポリシーを使用してこれを行うか、[LegacySameSiteCookieBehaviorEnabled](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabled) ポリシーを使用してすべてのサイトにわたる変更をオプトアウトできます。

* **HTML5 アプリケーション キャッシュ API の削除。**  Microsoft Edge バージョン 86 以降、Web ページのオフライン使用を可能にするレガシ アプリケーション キャッシュ API は Microsoft Edge から削除されます。 Web 開発者は、[WebDev ドキュメント](https://web.dev/appcache-removal/)で、アプリケーション キャッシュ API のサービス ワーカーへの置き換えに関する情報を確認する必要があります。  重要: Microsoft Edge バージョン 90 まで、サイトが非推奨のアプリケーション キャッシュ API を引き続き使用できるようにする [AppCache OriginTrial Token](https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673) を要求できます。

* **プライバシーとセキュリティ**

  * ダウンレベルの Windows と macOS で [MetricsReportingEnabled]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) と [SendSiteInformationToImproveServices]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) ポリシーを置き換えます。 これらのポリシーは Microsoft Edge バージョン 86 では非推奨で、Microsoft Edge バージョン 89 で廃止されます。<br>
これらのポリシーは、Windows 10 では[利用統計情報の許可](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)に、その他すべてのプラットフォームでは新しい [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) ポリシーに置き換えられます。 これにより、ユーザーは Windows 7、8、8.1、macOS で、Microsoft に送信される診断データを管理できるようになります。
  * セキュリティで保護された DNS (DNS-over-HTTPS) のサポート。  Microsoft Edge バージョン 86 以降、セキュリティ保護された DNS を制御する設定が、管理されていないデバイスで利用可能になりました。 ユーザーは管理されたデバイスでこれらの設定にアクセスできませんが、IT 管理者は [dnsoverhttpsmode](./microsoft-edge-policies.md#dnsoverhttpsmode) グラウンド ポリシーを使用して、セキュリティ保護された DNS を有効または無効にすることができます。

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

- [CollectionsServicesAndExportsBlockList](./microsoft-edge-policies.md#collectionsservicesandexportsblocklist) - 指定したサービスの一覧へのアクセスをブロックし、コレクション内のターゲットをエクスポートします。
- [DefaultFileSystemReadGuardSetting](./microsoft-edge-policies.md#defaultfilesystemreadguardsetting) -読み取り用のファイルシステム API の使用を制御します。
- [DefaultFileSystemWriteGuardSetting](./microsoft-edge-policies.md#defaultfilesystemwriteguardsetting)-書き込みにファイルシステム API の使用を制御します。
- [DefaultSensorsSetting](./microsoft-edge-policies.md#defaultsensorssetting) - 既定のセンサーの設定。
- [DefaultSerialGuardSetting](./microsoft-edge-policies.md#defaultserialguardsetting) - シリアル API の使用を制御します。
- [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) - ブラウザーの使用状況に関する必須およびオプションの診断データを送信します。
- [EnterpriseModeSiteListManagerAllowed](./microsoft-edge-policies.md#enterprisemodesitelistmanagerallowed) - Enterprise Mode Site List Manager ツールへのアクセスを許可します。
- [FileSystemReadAskForUrls](./microsoft-edge-policies.md#filesystemreadaskforurls) - これらのサイトのファイル システム API を通して読み取りアクセスを許可します。
- [FileSystemReadBlockedForUrls](./microsoft-edge-policies.md#filesystemreadblockedforurls) -これらのサイトのファイルシステム API を使用した読み取りアクセスをブロックします。
- [FileSystemWriteAskForUrls](./microsoft-edge-policies.md#filesystemwriteaskforurls) - これらのサイトのファイルとディレクトリへの書き込みアクセスを許可します。
- [FileSystemWriteBlockedForUrls](./microsoft-edge-policies.md#filesystemwriteblockedforurls) -これらのサイトのファイルとディレクトリの書き込みアクセスをブロックします。
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
- [UserAgentClientHintsEnabled](./microsoft-edge-policies.md#useragentclienthintsenabled) - ユーザー エージェント クライアント ヒント機能を有効にします。
- [UserDataSnapshotRetentionLimit](./microsoft-edge-policies.md#userdatasnapshotretentionlimit) - 緊急ロールバックの場合に使用されるユーザー データのスナップショット数を制限します。

#### <a name="deprecated-policies"></a>廃止されたポリシー

- [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) - 使用状況とクラッシュ関連のデータレポートを有効にします。
- [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) - Microsoft サービスを改善するためにサイト情報を送信します。

#### <a name="obsoleted-policy"></a>非推奨ポリシー

[TLS13HardeningForLocalAnchorsEnabled](./microsoft-edge-policies.md#tls13hardeningforlocalanchorsenabled) - ローカル トラスト アンカーの TLS 1.3 セキュリティ機能を有効にします。

## <a name="version-85056470-october-6"></a>バージョン 85.0.564.70 : 10 月 6 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-85056468-october-1"></a>バージョン 85.0.564.68: 10 月 1 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-85056463-september-23"></a>バージョン 85.0.564.63: 9 月 23 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#september-23-2020)に記載されています

## <a name="version-85056451-september-9"></a>バージョン 85.0.564.51: 9 月 9 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#september-9-2020)に記載されています

## <a name="version-85056444-august-31"></a>バージョン 85.0.564.44: 8 月 31 日

さまざまなバグとパフォーマンスの問題を修正しました。

<!-- 85.0.564.41: August 27 -->

## <a name="version-85056441-august-27"></a>バージョン 85.0.564.41: 8 月 27 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#august-27-2020)に記載されています

### <a name="feature-updates"></a>機能更新プログラム

- **[お気に入り]と[設定]のオンプレミス同期**。 クラウド同期を必要とせずに、自分の環境内の Active Directory プロファイル間でブラウザーのお気に入りと設定を同期できます。

- **確認メッセージを表示せずに、信頼するサイトとアプリの組み合わせを起動するための Microsoft Edge グループ ポリシー サポート**。 管理者が、確認メッセージを表示せずに、信頼されているサイトとアプリの組み合わせ を追加できるようにしたグループポリシーのサポートが追加されました。 これにより、管理者は、アプリプロトコルを含む URL に移動するときに、エンドユーザーが確認メッセージを表示しないようにするために、信頼されたプロトコル/オリジンの組み合わせ (Microsoft 365 アプリなど) を構成できます。

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
- [TLSCsipherSuiteDenyList](./microsoft-edge-policies.md#tlsciphersuitedenylist) - TLS 暗号スイートを無効に指定します。

#### <a name="obsoleted-policies"></a>不使用のポリシー

- [EnableDomainActionsDownload](./microsoft-edge-policies.md#enabledomainactionsdownload) - Microsoft からのドメイン アクションのダウンロードを有効にします。
- [WebComponentsV0Enabled](./microsoft-edge-policies.md#webcomponentsv0enabled) - Web コンポーネント v0 API ユニット M84 を再有効化する。
- [WebDriverOverridesIncompatiblePolicies](./microsoft-edge-policies.md#webdriveroverridesincompatiblepolicies) - WebDriverに 互換性のないポリシーのオーバーライドを許可します。

## <a name="version-84052263-august-20"></a>バージョン 84.0.522.63: 8 月 20 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#august-20-2020)に記載されています。

## <a name="version-84052261-august-17"></a>バージョン 84.0.522.61: 8 月 17 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-84052259-august-11"></a>バージョン 84.0.522.59: 8 月 11 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#august-11-2020)に記載されています

## <a name="version-84052258-august-10"></a>バージョン 84.0.522.58: 8 月 10 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-84052252-august-1"></a>バージョン 84.0.522.52: 8 月 1 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-84052250-july-31"></a>バージョン 84.0.522.50: 7 月 31 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-84052249-july-29"></a>バージョン 84.0.522.49: 7 月 29 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#july-29-2020)に記載されています

## <a name="version-84052248-july-28"></a>バージョン 84.0.522.48: 7 月 28 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-84052244-july-23"></a>バージョン 84.0.522.44: 7 月 23 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-84052240-july-16"></a>バージョン 84.0.522.40: 7 月 16 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#july-16-2020)に記載されています

### <a name="feature-updates"></a>機能更新プログラム

- このバージョンの Microsoft Edge では、Internet Explorer モードでのサイト一覧のダウンロード時間が改善されました。 キャッシュされたサイト リストがない場合、Internet Explorer モードのサイト一覧のダウンロードのダウンロード遅延が0秒に削減されました （以前の60秒待ちから短縮）。 また、サイト一覧がダウンロードされるまで、Internet Explorer モードのホームページ ナビゲーションを遅延する必要がある場合のために、グループ ポリシーのサポートも追加しました。 詳細については、「[DelayNavigationsForInitialSiteListDownload](./microsoft-edge-policies.md#delaynavigationsforinitialsitelistdownload)」 を参照してください。

- Microsoft Edge では、Windows 10 で "管理者として実行" する場合に、ユーザーがブラウザーにサインインできるようになりました。 これにより、Windows サーバーで Microsoft Edge を実行しているユーザー、またはリモートデスクトップやサンドボックスのシナリオでの使用に役立ちます。

- Microsoft Edge は、全画面表示モードでフル マウス サポートが提供されるようになりました。 これで、全画面表示モードを終了しなくても、マウスを使用してタブ、アドレス バーなどの項目にアクセスできます。

- オンライン購入を改善します。 保存したデビット カードやクレジット カードにカスタム ニックネームを追加します。 これで、オンライン購入時に、クレジット カードを区別して差別化できるようになりました。 デビット カードやクレジット eカードにニックネームを付けることで、オートフィルを使用して支払い方法を選択する際に正しいカードを選ぶことができます。

- TLS/1.0 および TLS/1.1 は既定では無効になっています。  [SSLVersionMin](./microsoft-edge-policies.md#sslversionmin) ポリシーにより、TLS/1.0 と TLS/1.1 を再有効化することが可能になります。 このポリシーは、Microsoft Edge バージョン88以上で利用可能になります。 詳細については、「[Microsoft Edge 向けのサイトの互換性に影響する変更点](/microsoft-edge/web-platform/site-impacting-changes)」 を参照してください。

- コレクションの改善

  - ノート機能が追加され、コレクション内のアイテムにメモやコメントを追加することができます。 メモはグループ化されるため、コレクションの中でアイテムを並べ替えても、アイテムにくっついたままです。 この新機能を試すには、アイテムを右クリックし、[メモの追加] を選択します。
  - コレクション内にあるメモの背景色を変更できます。 [色分け] を使用すると、情報を整理して生産性を高めることが可能です。
  - パフォーマンスが大幅に改善されました。これにより、以前のバージョンの Microsoft Edge よりも短時間で Excel にコレクションをエクスポートできるようになりました。

- その他の Microsoft Edge API サポートは、次のとおりです。

  - ストレージ アクセス API は実験用に有効化されています。。 この機能は、[ExperimentationAndConfigurationServiceControl](./microsoft-edge-policies.md#experimentationandconfigurationservicecontrol) ポリシーが「フル」に設定されているホーム ユーザーおよびエンタープライズ ユーザーに対して有効です。 この機能は、Microsoft Edge Stable チャネル バージョン 85 のすべてのユーザーに対して既定で有効になります。
  
    プライバシーは、ユーザーにとっての重要性がますます高まっているため、より厳格なブラウザの規定値とサードパーティ製ストレージへのアクセスをすべてブロックするようなユーザー オプトイン設定の要求は、ますます一般的になっています。 これらの設定は、プライバシーを改善し、不明な、または信頼されていないパーテによるの不要なアクセスをブロックするのに役立ちますが、ユーザーが表示したいと思うコンテンツ (たとえば、ソーシャル メディアや埋め込まれたメディア コンテンツ) へのアクセスをブロックするなど、不要な副作用をもたらす可能性があります。

    Storage Access APIは、ブラウザーの現在の構成によってブロックされる可能性があるストレージをユーザーが直接許可できるようにするために、サードパーティのコンテキストでファーストパーティ ストレージにアクセスできるようにします。 詳細については、「[記憶域アクセスAPI](https://www.chromestatus.com/feature/5612590694662144)」を参照してください。

  - ネイティブファイルシステム API は、この API を使用してファイルまたはフォルダーを編集するためのアクセス許可をサイトに付与できるものです。

- PDF の改善点は、次のとおりです。

  - PDF 用の音声読み上げを行うことで、ユーザーは、重要なタスクを実行しながら PDF コンテンツを聞くことができます。 また、視聴覚学習者がコンテンツの閲覧に集中するのに役立つため、学習しやすくなります。
  - PDF ファイル編集機能が改善されました。 PDF を編集するたびにコピーを保存するのではなく、編集内容を PDF に保存してファイルに戻すことができるようになりました。

- Microsoft Edge では、イマーシブ リーダーの翻訳が可能になります。 ユーザーがイマーシブ リーダー ビューを開くと、ページを目的の言語に翻訳するためのオプションが表示されます。

- VS コードに一致するようにキーボード ショートカットをカスタマイズしたり、ハイ コントラストで DevTools を表示したりするためのサポートを含む、いくつかの DevTools の更新。  詳細については、「[DevTools の新着情報 (Microsoft Edge 84)](/microsoft-edge/devtools-guide-chromium/whats-new/2020/05/devtools)」を参照してください。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

7 個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [AppCacheForceEnabled](./microsoft-edge-policies.md#appcacheforceenabled) - 既定でオフになっている場合でも、App Cache 機能を再度有効にすることを許可します。
- [ApplicationGuardContainerProxy](./microsoft-edge-policies.md#applicationguardcontainerproxy) - Application Guard コンテナー プロキシの設定を構成します。
- [DelayNavigationsForInitialSiteListDownload](./microsoft-edge-policies.md#delaynavigationsforinitialsitelistdownload) - タブ ナビゲーションの前にエンタープライズ モード サイト一覧が使用できるようにします。
- [WinHttpProxyResolverEnabled](./microsoft-edge-policies.md#winhttpproxyresolverenabled) - Windows プロキシ リゾルバーを使用します。
- [InternetExplorerIntegrationEnhancedHangDetection](./microsoft-edge-policies.md#internetexplorerintegrationenhancedhangdetection) - Internet Explorer モードの拡張ハング検出を構成します。
- [NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - CPU と電力の消費を削減するために、Microsoft Edge はウィンドウが他のウィンドウに覆われていることを検出したときにピクセルの描画作業を中断します。
- [NavigationDelayForInitialSiteListDownloadTimeout](./microsoft-edge-policies.md#navigationdelayforinitialsitelistdownloadtimeout) - エンタープライズ モード サイト一覧のタブ ナビゲーションの遅延時間を設定します。

#### <a name="deprecated-policies"></a>廃止されたポリシー

- [AllowSyncXHRInPageDismissal](./microsoft-edge-policies.md#allowsyncxhrinpagedismissal) - ページが同期 XHR 要求をページの解除中に送信できるようにします。
- [BuiltinCertificateVerifierEnabled](./microsoft-edge-policies.md#builtincertificateverifierenabled) - 組み込みの証明書検証機能を使用してサーバー証明書を検証するかどうかを決定します。
- [StricterMixedContentTreatmentEnabled](./microsoft-edge-policies.md#strictermixedcontenttreatmentenabled) - 混合コンテンツに対してより厳密な処理を有効にします。

#### <a name="obsoleted-policy"></a>非推奨ポリシー

[ForceNetworkInProcess](./microsoft-edge-policies.md#forcenetworkinprocess) - ブラウザー プロセスでネットワーク コードを強制的に実行します。

<!-- End 84 -->
## <a name="version-83047864-july-13"></a>バージョン 83.0.478.64: 7 月 13 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-83047861-july-7"></a>バージョン 83.0.478.61: 7 月 7 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-83047858-june-30"></a>バージョン 83.0.478.58: 6 月 30 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-83047856-june-24"></a>バージョン 83.0.478.56: 6 月 24 日

さまざまなバグとパフォーマンスの問題を修正しました。

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#june-24-2020)に記載されています

## <a name="version-83047854-june-17"></a>バージョン 83.0.478.54: 6 月 17 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#june-17-2020)に記載されています

## <a name="version-83047850-june-15"></a>バージョン 83.0.478.50: 6 月 15 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-83047845-june-4"></a>バージョン 83.0.478.45: 6 月 4 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#june-4-2020)に記載されています

## <a name="version-83047844-june-1"></a>Version 83.0.478.44: 6月1日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-83047837-may-21"></a>バージョン 83.0.478.37: 5 月 21 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#may-21-2020)に記載されています

### <a name="feature-updates"></a>機能更新プログラム

- Microsoft Edge の更新プログラムは徐々に展開されます。 今後、Microsoft Edge の更新プログラムは数日間にわたってユーザーに公開されます。 これにより、誤ったバグのある更新プログラムからより多くのユーザーを保護できるようになり、更新エクスペリエンスが向上します。 ユーザーは引き続きシームレスな自動更新を取得できます。 組織が自動更新に登録されていない場合、この変更による影響はありません。 詳細については、「[段階的なロールアウトの記事](microsoft-edge-update-progressive-rollout.md)」をご覧ください。
- Microsoft Defender SmartScreen の改善: 読み込み時にリダイレクトする悪意のあるサイトからの保護が強化され、悪意のあるサイトを Microsoft Defender SmartScreen の安全ページに完全に置き換えるトップレベルのフレーム ブロックなど、Microsoft Defender SmartScreen サービスにいくつかの改良を加えました。 トップレベルのフレーム ブロックにより、悪意のあるサイトからの音声やその他のメディアの再生が防止され、より簡単かつわかりやすくなります。

- ユーザーのフィードバックに応えて、ユーザーはブラウザーが閉じたときに特定の Cookie を自動的に消去しないように設定できます。 このオプションは、ユーザーのサインアウトは望まないが、ブラウザーを閉じたときに他のすべての Cookie をクリアしたいサイトがある場合に役立ちます。 この機能を使用するには、*edge://settings/clearBrowsingDataOnClose* に移動して、[Cookie およびその他のサイト データ] トグルを有効にします。

- 自動プロファイル切り替えが利用可能になり、プロファイル間でより簡単に作業内容にアクセスできるようになりました。 職場で複数のプロファイルを使用している場合は、個人用プロファイルを使用しているときに、職場または学校のアカウントから認証を必要とするサイトに移動して、プロファイルを確認できます。 これを検出すると、仕事用プロファイルに切り替えて、認証なしでそのサイトにアクセスするよう求めるプロンプトが表示されます。 切り替えたい仕事用プロファイルを選択すると、仕事用プロファイルで Web サイトが開きます。 このプロファイル切り替え機能により、仕事用データと個人データの分離が可能となり、作業コンテンツに簡単にアクセスできるようになります。 この機能でプロファイルを切り替えるように求められないようにする場合は、[今後表示しない] オプションを選択すると、邪魔になりません。

- コレクション機能の改善:
  - ドラッグ アンド ドロップを使用して、コレクションを開かずにコレクションにアイテムを追加できます。 ドラッグ アンド ドロップ中に、コレクション リストでアイテムを配置する場所を選択することもできます。
  - 一度に 1 つのアイテムを追加する代わりに、コレクションに複数のアイテムを追加できます。 複数のアイテムを追加するには、アイテムを選択して、コレクションにドラッグします。 または、アイテムを選択して右クリックし、アイテムを配置するコレクションを選択することもできます。

- Microsoft Edge ウィンドウのすべてのタブを個別に追加せず、新しいコレクションに追加できます。 これを行うには、任意のタブを右クリックし、[すべてのタブを新しいコレクションに追加] を選択します。

- 拡張機能の同期が利用可能になりました。 すべてのデバイスで拡張機能を同期できるようになりました。 Microsoft Store と Chrome ウェブストアの両方から入手した拡張機能が Microsoft Edge と同期します。 この機能を使用するには: メニュー バーの省略記号 (**…**) をクリックし、[**設定**] を選択します。 [プロファイル] で、[**同期**] をクリックして、同期オプションを表示します。 **Profiles/Sync** で、トグルを使用して拡張機能を有効にします。 [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) グループ ポリシーを使用して、拡張機能の同期を無効にすることができます。

- ブロックされた安全でないダウンロードに関するダウンロード管理ページのメッセージを改善しました。

- イマーシブ リーダーの改善:
  - イマーシブ リーダーの品詞エクスペリエンスで副詞のサポートが追加されました。 イマーシブ リーダーで記事を読みながら、文法ツールを開き、品詞内の副詞をオンにして、ページ上のすべての副詞を強調表示します。
  - Web ページ上の任意のコンテンツを選択し、イマーシブ リーダーで開く機能が追加されました。 この機能により、ユーザーはすべての Web サイトでイマーシブ リーダーとすべての学習ツール (行フォーカスや 音声読み上げなど) を使用できます。

- Link doctor では、ユーザーが URL を誤って入力したときにホスト修正が行われ、検索クエリがユーザーに提供されます。 次に、例を示します。 <br>
ユーザーが "powerbi" を誤って "powerbbi".com と入力したとします。 Link doctor からは、修正案として "powerbi".com が提案され、ユーザーが別の違うサイトを探している場合も想定し "powerbbi" を検索するためのリンクが作成されます。

- ユーザーは、特定のサイトの外部プロトコルを起動するという設定を保存できます。 ユーザーは、[ExternalProtocolDialogShowAlwaysOpenCheckbox]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#externalprotocoldialogshowalwaysopencheckbox) ポリシーを構成して、この機能を有効または無効にすることができます。

- ユーザーは、Microsoft Edge の **[設定]** から直接 Microsoft Edge を既定のブラウザーとして設定できます。 これにより、ユーザーは、オペレーティング システムの設定を検索せずに、ブラウザー自体のコンテキスト内で既定のブラウザーを簡単に変更することができます。 この機能を使用するには、*edge://settings/defaultBrowser* に移動し、**[既定に設定]** をクリックします。

- 新しいリモート デバッグのサポートや UI の改善など、DevTools の機能もいくつか更新されています。 詳細については、「[DevTools の新着情報 (Microsoft Edge 83)](/microsoft-edge/devtools-guide-chromium/whats-new/2020/03/devtools)」を参照してください。

- MCAS (Microsoft Cloud Access Security) 警告シナリオが利用可能になりました。 これにより、管理者はユーザーが MCAS ブロック ページを上書きできる MCAS ブロックの新しいカテゴリである警告を設定できます。 MDATP E5 ブロックは、シームレスなエクスペリエンスのために Microsoft Edge の SmartScreen ブロックとネイティブに統合されています。 このエクスペリエンスでは、トースト通知だけでなく、「この Web サイトは組織によってブロックされています」というメッセージが表示された赤いページ全体がブロックされます。

- ページを離れる際の同期 XmlHttpRequest を禁止します。 Web ページをアンロード中の同期 XmlHttpRequests の送信は、削除されます。 この変更により、ブラウザーのパフォーマンスと信頼性が向上しますが、sendBeacon や fetch など、最新の Web Api を使用するように更新されていない Web アプリケーションに影響する可能性があります。 この変更を無効にして、ページを離れる際の同期 XHR を許可するグループ ポリシーは、Microsoft Edge 88 までに公開される予定です。 詳細については、「[Microsoft Edge 向けのサイトの互換性に影響する変更点](/microsoft-edge/web-platform/site-impacting-changes)」 を参照してください。

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

<!-- end 83 -->

## <a name="version-81041677-may-18"></a>バージョン 81.0.416.77: 5 月 18 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-81041672-may-7"></a>バージョン 81.0.416.72: 5 月 7 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#may-7-2020)に記載されています

## <a name="version-81041668-april-29"></a>バージョン 81.0.416.68: 4 月 29 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#april-29-2020)に記載されています

## <a name="version-81041664-april-23"></a>バージョン 81.0.416.64: 4 月 23 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#april-23-2020)に記載されています

## <a name="version-81041658-april-17"></a>バージョン 81.0.416.58: 4 月 17 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#april-17-2020)に記載されています

## <a name="version-81041653-april-13"></a>バージョン 81.0.416.53: 4 月 13 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#april-13-2020)に記載されています

### <a name="feature-updates"></a>機能更新プログラム

- Windows 情報保護 (WIP) のサポートが追加されました。これにより、企業の機密データが無断で開示されるのを防ぐことができます。 [詳細情報](./microsoft-edge-security-windows-information-protection.md)。

- コレクションが使用できるようになりました。 開始するには、アドレス バーの横にある [コレクション] アイコンをクリックします。 これにより、[コレクション] ウィンドウが開き、コレクションを作成、編集、表示できます。 Microsoft は、Web 上で行った操作に基づいて、コレクションを設計しています。 買い物客に、旅行者に、教師に、学生に、コレクションが役立ちます。 [詳しくはこちらをご覧ください](https://blogs.windows.com/msedgedev/2019/12/09/improvements-collections-sync-microsoft-edge/#LuDPRDUDCgdgdOVt.97)。

- 整合性を維持するために、Microsoft Edge ツールバーから [コレクション] ボタンを削除 (ツールバーから非表示にする) できるようにします。

- オンプレミスの Active Directory アカウントの自動サインインは、有効になっている組織に対してのみ有効です。  ユーザーがオンプレミスの AD アカウントで既にサインインしている場合は、そのアカウントからサインアウトすることができます。 Microsoftアカウント または Azure AD アカウントの場合は、オペレーティング システムのプライマリ アカウントで自動的にサインインが行われます。 管理者は、ConfigureOnPremisesAccountAutoSignIn ポリシーを使用して、オンプレミス AD アカウントで自動サインインを有効にすることができます。

- Application Guard。 拡張機能のサポートがコンテナで利用可能になりました。

- ユーザーが Internet Explorer モードで開くように構成されているページに移動したときに、Internet Explorer がインストールされていないことをユーザーに通知するメッセージが追加されました。

- Microsoft Edge DevTools の 3D ビュー ツールを更新して、z-index スタッキング コンテキストのデバッグに役立つ新機能を追加しました。 3D ビューには、色とスタックを使用した DOM (ドキュメント オブジェクト モデル) の奥行きが表示され、z-Index インデックス ビューは、ページのさまざまなスタッキング コンテキストを分離することができます。 [詳しくはこちらをご覧ください](https://blogs.windows.com/msedgedev/2020/01/23/debug-z-index-3d-view-edge-devtools/)。

- F12 開発ツールが 10 の新しい言語にローカライズされたため、ブラウザーの他の部分で使用されている言語と同じになります。 [詳しくはこちらをご覧ください](https://blogs.windows.com/msedgedev/2020/02/04/localizing-edge-devtools/)。

- ドルビー ビジョン再生のサポートが追加されました。 ドルビー ビジョン Windows 10 ビルド 17134 (April 2018 Update) では、ドルビー ビジョン コンテンツを表示できます。 [Netflix](https://help.netflix.com/en/node/42384) でドルビー ビジョン コンテンツを有効にする方法を参照してください。

- Microsoft Edge は、重複したお気に入りフォルダーを識別して削除し、同じ名前のフォルダーをマージできるようになりました。 ツールにアクセスするには、ブラウザーのツールバーのスターをクリックして、[重複したお気に入りを削除] を選択します。  変更を確認でき、お気に入りの更新はデバイス間で同期されます。

- ユーザーから、両方のウィンドウ フレームが暗いため、暗いテーマの通常のブラウジング ウィンドウと InPrivate ウィンドウを区別するのが難しい場合があるという意見が寄せられました。 右上隅の新しい青く塗りつぶされた InPrivate を示す丸記号により、ユーザーは、InPrivate ブラウズを行っていることを確認できます。

- 正しいブラウザー プロファイルで外部リンクを開きます。 外部アプリ用に開かれているリンクに対する規定プロファイルを選択し、*edge://settings/multiProfileSettings* から開きます。

- あるアカウントを使ってブラウザー プロファイルにサインインするユーザーに、別のアカウントで以前サインインしていたことを通知する警告が追加されました。 この警告により、意図しないデータの結合を防ぐことができます。

- Microsoft アカウントに支払カード情報を保存している場合は、支払フォームに入力するとき、Microsoft Edge でそれらを使用できます。 Microsoft アカウントにおけるカード情報はデスクトップ デバイス間で同期され、二要素認証 (CVC コードとMicrosoft ID) の後、すべての詳細が Web サイトと共有されます。利便性を高めるために、認証中にカードのコピーをデバイスに安全に保存することを選択できます。

- 行フォーカスは、ユーザーが読み取る際にコンテンツの一部のみに注目できるように設計されています。 これにより、ページの残りの部分を暗くして、ユーザーは一度に 1 行、3 行、5 行に注目できるため、気を散らすことなく読むことができます。 ユーザーはタッチまたは方向キーを使用してスクロールすることができます。フォーカスはそれに応じて移動します。

- Microsoft Edge は、Windows プラットフォーム8.1以降で、Windows Speller と統合されました。 この統合により、より多くの言語辞書アクセスし、Windows カスタム辞書を使用できるため、より優れた言語サポートが提供されます。 言語が OS の設定で追加されている場合、それ以上のユーザーのアクションは必要ありません。 また、Microsoft Edge の設定では、言語のスペルチェック トグルが有効になっています。

- Microsoft Edge を使用して PDF ドキュメントを開くと、ユーザーはハイライトの作成、色の変更、ハイライトの削除ができるようになります。 この機能により、後でドキュメントの重要な部分を参照したり、コラボレーションしたりすることができます。

- Web 用に最適化された長い PDF ドキュメントを読み込む場合、ドキュメントの残りの部分が読み込まれてる間、ユーザーが表示しているページは、より速く、並行して読み込まれます。

- F9 キーを押すだけで、Web サイトのイマーシブ リーダーを簡単に起動できるようになりました。

- キーボード ショートカット (Ctrl + Shift + U) を使用して、音声で読み上げる機能を簡単に起動できるようになりました。

- MSI コマンド ライン パラメーターを追加しました。これを使用すると、Microsoft Edge をインストールするときにデスクトップ アイコンの作成を抑制できます。 次の例では、この新しいパラメーターを使用する方法を示します。 <br>
`MicrosoftEdgeEnterpriseX64.msi DONOTCREATEDESKTOPSHORTCUT=true`<br>
今後のリリースでは、この機能をサポートするためのグループ ポリシーが用意されます。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

11 個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [AmbientAuthenticationInPrivateModesEnabled](./microsoft-edge-policies.md#ambientauthenticationinprivatemodesenabled) - InPrivate およびゲスト プロファイルの環境認証を有効にします。 
- [AudioSandboxEnabled](./microsoft-edge-policies.md#audiosandboxenabled) - オーディオ サンドボックスの実行を許可します。
- [ForceLegacyDefaultReferrerPolicy](./microsoft-edge-policies.md#forcelegacydefaultreferrerpolicy) - no-referrer-when-downgrade の既定の参照元ポリシーを使用します。
- [GloballyScopeHTTPAuthCacheEnabled](./microsoft-edge-policies.md#globallyscopehttpauthcacheenabled) - グローバル スコープの HTTP 認証キャッシュを有効にします。
- [ImportExtensions](./microsoft-edge-policies.md#importextensions) - 拡張機能のインポートを許可します。
- [ImportCookies](./microsoft-edge-policies.md#importcookies) - Cookie のインポートを許可します。
- [ImportShortcuts](./microsoft-edge-policies.md#importshortcuts) - ショートカットのインポートを許可します。
- [InternetExplorerIntegrationSiteRedirect](./microsoft-edge-policies.md#internetexplorerintegrationsiteredirect) - Internet Explorer モード ページから起動した場合、未構成サイトへの「ページ内」ナビゲーションの動作を指定します。
- [StricterMixedContentTreatmentEnabled](./microsoft-edge-policies.md#strictermixedcontenttreatmentenabled) - 混合コンテンツに対してより厳密な処理を有効にします。
- [TLS13HardeningForLocalAnchorsEnabled](./microsoft-edge-policies.md#tls13hardeningforlocalanchorsenabled) - ローカル トラスト アンカーの TLS 1.3 セキュリティ機能を有効にします。
- [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin) - Azure AD ドメイン アカウントがない場合、Active Directory ドメイン アカウントで自動サインインを構成します。

#### <a name="policy-name-and-caption-changes"></a>ポリシー名とキャプションの変更

ポリシー `OmniboxMSBProviderEnabled` は [AddressBarMicrosoftSearchInBingProviderEnabled](//DeployEdge/microsoft-edge-policies#addressbarmicrosoftsearchinbingproviderenabled) に変更されます。ポリシーのキャプションは、"アドレス バーにある Bing の候補で Microsoft Search を有効にする" です。

#### <a name="deprecated-policies"></a>廃止されたポリシー

このリリースでは、次のポリシーが引き続き機能します。 これらは、将来のリリースで「廃止」される予定です。

- [WebComponentsV0Enabled](./microsoft-edge-policies.md#webcomponentsv0enabled) - M84 まで Web コンポーネント v0 API を再度有効にします。
- [WebDriverOverridesIncompatiblePolicies](./microsoft-edge-policies.md#webdriveroverridesincompatiblepolicies) - WebDriverに 互換性のないオーバーライドを許可します。

#### <a name="resolved-issues"></a>解決した問題

- ファイルをダウンロードした後も Microsoft Edge の IE モードで [ダウンロード中] ダイアログが表示される問題が修正されました。
- 既に IE モードで呼び出されたページが新しい IE モード タブを開くときに、Microsoft Edge がセッション Cookie を削除する問題が修正されました。

## <a name="version-800361111-april-7"></a>バージョン 80.0.361.111: 4 月 7 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-800361109-april-1"></a>バージョン 80.0.361.109: 4 月 1 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#april-1-2020)に記載されています

## <a name="version-80036169-march-19"></a>バージョン 80.0.361.69: 3 月 19 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#march-19-2020)に記載されています

## <a name="version-80036166-march-4"></a>バージョン 80.0.361.66: 3 月 4 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#march-4-2020)に記載されています

## <a name="version-80036162-february-25"></a>バージョン 80.0.361.62: 2 月 25 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#february-25-2020)に記載されています

## <a name="version-80036157-february-20"></a>バージョン 80.0.361.57: 2 月 20 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#february-20-2020)に記載されています

## <a name="version-80036156-february-19"></a>バージョン 80.0.361.56: 2 月 19 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-80036154-february-14"></a>バージョン 80.0.361.54: 2 月 14 日

### <a name="resolved-issues"></a>解決した問題

- Microsoft Edge でパスワード、支払い、および Cookie のインポートが失敗した場合の問題を修正しました。

## <a name="version-80036150-february-11"></a>バージョン 80.0.361.50: 2 月 11

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-80036148-february-7"></a>バージョン 80.0.361.48: 2 月 7 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#february-7-2020)に記載されています

### <a name="feature-updates"></a>機能更新プログラム

- 望ましくない可能性のあるアプリのダウンロードに対する SmartScreen 保護が追加されました。 [詳細情報](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus)
- ドルビー ビジョン再生のサポートが追加されました。
- Windows Mixed Reality のユーザーが VR ヘッドセットで 360° ビデオを表示できるようにしました。
- 文字間隔を広くするためのオプションを閲覧表示に追加しました。
- Surface ペンの消しゴムを使用してリンクを消去するためのサポートが追加されました。
- エディター モードで方向キーとスペース バーを使用してフィードバックのスクリーンショットを描くためのサポートが追加されました。
- フィードバックを送信するときに真っ黒い画面になってしまわないように、スクリーンショットの信頼性を向上させました。
- デバイスがインターネットに接続されていないときに表示されるローカルの新しいタブ ページに、濃色テーマのサポートが追加されました。
- 更新、クラッシュなどの後にブラウザー セッションが復元されるときに、アプリとしてインストールされた Web サイトが復元される機能が追加されました。
- ブラウザーがグループ ポリシーによって管理されている場合に、PDF UI に濃色テーマのサポートが追加されました。
- Adobe Flash がバージョン32.0.0.321 に更新されました。 [詳細情報](https://helpx.adobe.com/flash-player/release-note/fp_32_air_32_release_notes.html)

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

16 個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [AlternateErrorPagesEnabled](./microsoft-edge-policies.md#alternateerrorpagesenabled) - Web ページが見つからない場合に、似通ったページを候補とし表示する。
- [DefaultInsecureContentSetting](./microsoft-edge-policies.md#defaultinsecurecontentsetting)  - 安全でないコンテンツの例外の使用を制御する。
- [DNSInterceptionChecksEnabled](./microsoft-edge-policies.md#dnsinterceptionchecksenabled) - DNS 傍受の確認が有効になっている。
- [HideFirstRunExperience](./microsoft-edge-policies.md#hidefirstrunexperience) - 初回実行時のエクスペリエンスとスプラッシュ画面を非表示にする。
- [InsecureContentAllowedForUrls](./microsoft-edge-policies.md#insecurecontentallowedforurls) - 指定されたサイトの安全でないコンテンツを許可する。
- [InsecureContentBlockedForUrls](./microsoft-edge-policies.md#insecurecontentblockedforurls) - 指定されたサイトの安全でないコンテンツをブロックする。
- [LegacySameSiteCookieBehaviorEnabled](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabled) - 既定のレガシ SameSite cookie の動作設定を有効にする。
- [LegacySameSiteCookieBehaviorEnabledForDomainList](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabledfordomainlist) - 指定されたサイトの cookie をレガシ SameSite の動作に戻す。
- [PaymentMethodQueryEnabled](./microsoft-edge-policies.md#paymentmethodqueryenabled) - 利用可能な支払い方法について Web サイトがクエリを実行することを許可する。
- [PersonalizationReportingEnabled](./microsoft-edge-policies.md#personalizationreportingenabled) - Microsoft に閲覧履歴を送信して、広告、検索、ニュースのカスタマイズを許可する。
- [PinningWizardAllowed](./microsoft-edge-policies.md#pinningwizardallowed) - タスクバーへのピン留めウィザードを許可する。
- [SmartScreenPuaEnabled](./microsoft-edge-policies.md#smartscreenpuaenabled) - Microsoft Defender SmartScreen を構成して望ましくない可能性のあるアプリをブロックする。
- [TotalMemoryLimitMb](./microsoft-edge-policies.md#totalmemorylimitmb) - Microsoft Edge インスタンス 1 つあたりの使用可能メモリ (MB) の制限を設定する。
- [WebAppInstallForceList](./microsoft-edge-policies.md#webappinstallforcelist) - 強制インストールする Web アプリの一覧を構成する。
- [WebComponentsV0Enabled](./microsoft-edge-policies.md#webcomponentsv0enabled) - Web コンポーネント v0 API ユニット M84 を再有効化する。
- [WebRtcLocalIpsAllowedUrls](./microsoft-edge-policies.md#webrtclocalipsallowedurls) - WebRTC によるローカル IP アドレスの公開を管理する。

#### <a name="deprecated-policies"></a>廃止されたポリシー

以下のポリシーは廃止されました。

- [NewTabPageCompanyLogo](./microsoft-edge-policies.md#newtabpagecompanylogo) - 新しいタブ ページの会社ロゴを設定する。

### <a name="resolved-issues"></a>解決した問題

- Citrix 環境でオーディオが動作しない問題が修正されました。
- Microsoft Edge と従来の Microsoft Edge の同時実行環境で、従来のリンクが破損してクラッシュする問題が修正されました。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)