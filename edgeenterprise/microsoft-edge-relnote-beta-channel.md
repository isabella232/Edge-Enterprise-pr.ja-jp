---
title: Beta チャネルに関する Microsoft Edge のリリース ノート
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 09/09/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Beta チャネルに関する Microsoft Edge のリリース ノート
ms.openlocfilehash: d455b2ccab734ba8792754b81994ac381b974f73
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980227"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge Beta チャネルのリリースノート

これらのリリース ノートでは、Microsoft Edge Beta チャネルに含まれている新機能とセキュリティ以外の更新プログラムに関する情報を提供します。 これらのリリース ノートのアーカイブ バージョンは、[こちら](microsoft-edge-relnote-archive-beta-channel.md)から入手できます。

> [!NOTE]
> Microsoft Edge Web プラットフォームは、ユーザー エクスペリエンス、セキュリティ、およびプライバシーを向上させるために絶えず進化しています。 詳細については、「[Microsoft Edge のサイトの互換性に影響する変更点](/microsoft-edge/web-platform/site-impacting-changes)」を参照してください。

## <a name="version-94099214-september-7"></a>バージョン 94.0.992.14: 9 月 7 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-9409929-september-2"></a>バージョン 94.0.992.9: 9 月 2 日

### <a name="feature-updates"></a>機能更新プログラム

- **Microsoft Edgeと安定したチャネルの更新プログラムの 4 週間のケイデンスに移行します。**  メジャー バージョンには、新しい 4 週間のリリース サイクルを採用します。 決定の詳細については、次の記事を参照してください。 https://blogs.windows.com/msedgedev/2021/03/12/new-release-cycles-microsoft-edge-extended-stable/

- **新しい拡張された安定したオプションが提供されています。**  お客様の管理下の顧客に新しい Extended Stable オプションをEnterpriseしています。 [拡張安定] オプションは、番号が付いたリビジョンでも維持され、8 週間ごとに更新されます。 隔年でセキュリティ更新プログラムが適用されます。  詳細については、次の情報を参照してください。 https://blogs.windows.com/msedgedev/2021/07/15/opt-in-extended-stable-release-cycle/

- **MHTML ファイルを開く既定の動作の改善。**  MHTML ファイルが Microsoft Edge から保存されていない限り (Microsoft Edge の [名前を付けて保存] または [ページに名前を付けて保存] オプションを使用して) IE モードが有効になっている場合、MHTML ファイルは IE モードで開き続けます。 ファイルがファイルから保存されている場合Microsoft Edge、ファイルは新しいファイルで開Microsoft Edge。  この変更により、MHTML ファイルを IE モードで開く際に発生したレンダリングの問題が修正Microsoft Edge。

- **プライベート ネットワーク要求をセキュリティで保護されたコンテキストに制限します。** インターネット上のページからローカル (イントラネット) ネットワーク上のリソースにアクセスするには、それらのページを HTTPS 経由で配信する必要があります。 この変更は、Microsoft Edge に基づく Chromium プロジェクトで発生します。 詳細については、「[Chrome プラットフォームの状態エントリ](https://chromestatus.com/feature/5436853517811712)」に移動します。 セキュリティ保護されていないページとの互換性を維持する必要があるシナリオをサポートするには [、InsecurePrivateNetworkRequestAllowed](/deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) と [InsecurePrivateNetworkRequestAllowedForUrls](/deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls)の 2 つの互換性ポリシーを使用できます。

- **混在コンテンツのダウンロードをブロックします。** セキュリティで保護されたページは、他のセキュリティで保護されたページでホストされているファイルのみをダウンロードし、セキュリティで保護されていない (HTTPS 以外の) ページでホストされているダウンロードは、セキュリティで保護されたページから開始されるとブロックされます。 この変更は、Microsoft Edge に基づく Chromium プロジェクトで発生します。 詳細については、Google セキュリティ ブログ エントリ [に移動します](https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html)。

- **オンプレミス アカウントの暗黙的なサインインを有効にする。**   OnlyOnPremisesImplicitSigninEnabled ポリシーを有効にすると、暗黙的なサインインに対してオンプレミス アカウントだけが有効になります。  Microsoft Edge は、MSA または AAD アカウントに暗黙的にサインインしようとしません。 オンプレミス アカウントから AAD アカウントへのアップグレードも停止されます。

- **PDF ドキュメントに追加された自由形式のテキスト ボックス。**  フォームに入力し、目に見えるメモを追加するために使用できる無料のフォーム テキスト ボックスを PDF ドキュメントに追加する機能がサポートされています。

- **パスワードを簡単に更新します。**  ブラウザーは、特定の Web サイトの [パスワードの変更] ページに直接移動し、ページに手動で移動する必要が生じなく、時間とクリックを節約します。 このページにアクセスすると、ブラウザーは既存のパスワードを自動入力し、強力で一意の新しいパスワードを提案します。  注: 現在、この機能は限られた数のサイトで利用できます。  

- **新しいアクセシビリティ設定ページ。** アクセシビリティ関連の設定を 1 つのページにまとめました。 メインの設定リストの下 edge://settings/accessibility 新しいページが表示されます。 ここでは、Web ページを大きくするための設定、フォーカス領域の周囲に高い可視性のアウトラインを表示する設定、および Web 閲覧エクスペリエンスの向上に役立つその他の設定を示します。 今後のバージョンの新しい設定は、引き続きここに追加Microsoft Edge。

***新しいポリシー***

- [ApplicationGuardPassiveModeEnabled](/DeployEdge/microsoft-edge-policies#applicationguardpassivemodeenabled) Application Guard サイト一覧の構成を無視し、通常はエッジを参照する
- [OnlyOnPremisesImplicitSigninEnabled](/DeployEdge/microsoft-edge-policies#onlyonpremisesimplicitsigninenabled) 暗黙的なサインインに対して有効になっているオンプレミス アカウントのみ
- [WebRtcRespectOsRoutingTableEnabled](/DeployEdge/microsoft-edge-policies#webrtcrespectosroutingtableenabled)WebRTC 経由でピアツーピア接続をWindows OS ルーティング テーブル ルールのサポートを有効にする

***非推奨ポリシー***

- [UserAgentClientHintsEnabled](/DeployEdge/microsoft-edge-policies#useragentclienthintsenabled) クライアント ヒントUser-Agent有効にする

## <a name="version-93096133-august-27"></a>バージョン 93.0.961.33: 8 月 27 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-93096127-august-20"></a>バージョン 93.0.961.27: 8 月 20 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-93096124-august-18"></a>バージョン 93.0.961.24: 8 月 18 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-93096111-august-3"></a>バージョン 93.0.961.11: 8 月 3 日

### <a name="feature-updates"></a>機能更新プログラム

- **Microsoft Edge での初期ユーザー設定。**  バージョン 93 Microsoft Edgeを開始すると、初期Microsoft Edgeが追加されたと、エンタープライズへの展開が[容易になります](/deployedge/initial-preferences-support-on-microsoft-edge-browser)。

- **Microsoft Edge の IE モードでは、"マージなし" 動作がサポートされます。**  バージョン 93 Microsoft Edgeから、IE モードは Microsoft Edge"no-merge" をサポートします。 エンド ユーザーの場合、IE モード アプリケーションから新しいブラウザー ウィンドウを起動すると、IE11 の動作と同様に、別のセッションになります。 セッション共有を防止する必要があるサイトを構成するには、サイト一覧を調整する必要があります。 Microsoft Edge のウィンドウごとに、指定された "マージなし" サイトの 1 つである場合、そのウィンドウ内で IE モード タブに初めてアクセスした場合、少なくともそのウィンドウで最後の IE モード タブが閉じるまで、そのウィンドウは他のすべての Microsoft Edge ウィンドウとは異なる "マージなし" IE セッションにロックされます。 [こちら](/deployedge/edge-ie-mode-faq#does-ie-mode-on-microsoft-edge-support-the--no-merge--option-that-was-supported-in-internet-explorer-11-)をご覧ください。

- **タブ グループ。**  タブをユーザー定義グループに分類する機能は、複数のワークストリーム間でタブを効率的に検索、切り替え、管理するのに役立ちます。 これを有効にするには、バージョン 93 で始まるタブ グループMicrosoft Edgeオンにします。

- **垂直タブを使用している間は、タイトル バーを非表示にします。**  垂直タブでブラウザーのタイトル バーを非表示にすることで、余分な数ピクセルを取得します。 Microsoft Edge バージョン 93 から、edge://settings/appearance に移動し、[ツールバーのカスタマイズ] セクションで、垂直タブ モードの間にタイトル バーを非表示にするオプションを選択します。

- **ホバー ツールバーからのピクチャ イン ピクチャ (PiP) のビデオ。**  バージョン 93 Microsoft Edge、ピクチャ (PiP) モードに入る方がさらに簡単になります。 サポートされているビデオにカーソルを合わせると、ツール バーが表示され、そのビデオを PiP ウィンドウで表示できます。  注: これは現在、macOS のユーザー Microsoft Edge使用できます。  ユーザーへのロールアウトを続行する場合は、Windowsしてください。

- **TLS での 3DES の削除。**  バージョン 93 Microsoft Edge、暗号化スイートのサポートTLS_RSA_WITH_3DES_EDE_CBC_SHA削除されます。 この変更は、Microsoft Edge に基づく Chromium プロジェクトで発生します。 詳細については、「[Chrome プラットフォームの状態エントリ](https://chromestatus.com/feature/6678134168485888)」に移動します。 さらに、Microsoft Edge バージョン 93 では、[TripleDESEnabled](/deployedge/microsoft-edge-policies#tripledesenabled) ポリシーを使用すると、旧型のサーバーとの互換性を維持する必要があるシナリオをサポートできます。 この互換性ポリシーは廃止され、Microsoft Edge バージョン 95 で機能を停止します。 その前に、影響を受けるサーバーを更新してください。

- **ClickOnce および DirectInvoke プロンプトをバイパスするポリシー。**  ポリシーを更新して、ClickOnce のプロンプトと DirectInvoke のアプリが指定されたドメインから指定されたファイルの種類にバイパスできるようになりました。 これを行うには、次の手順を実行します。

  - [ClickOnceEnabled](/deployedge/microsoft-edge-policies#clickonceenabled) または [DirectInvokeEnabled](/deployedge/microsoft-edge-policies#directinvokeenabled) を有効にする
  - [AutoOpenFileTypes](/deployedge/microsoft-edge-policies#autoopenfiletypes) ポリシーを有効にし、DirectInvoke と ClickOnce を無効にする必要がある特定のファイルの種類の一覧を設定する
  - [AutoOpenAllowedForURLs](/deployedge/microsoft-edge-policies#autoopenallowedforurls)ポリシーを有効にし、ユーザーと DirectInvoke が無効になる特定ClickOnceの一覧を設定する

  注: AutoOpenAllowedForURLs は、AutoOpenFileTypes 用のサポート ポリシーです。 AutoOpenAllowedForURLs が設定されておらず、AutoOpenFileTypes が設定されている場合、一覧表示されているファイルの種類は、すべての URL で自動的に開きます。

### <a name="new-policies"></a>新しいポリシー

- [AutoplayAllowlist](/DeployEdge/microsoft-edge-policies#autoplayallowlist) 特定のサイトでメディアの自動再生を許可する
- [CECPQ2Enabled](/DeployEdge/microsoft-edge-policies#cecpq2enabled) TLS に対して有効な CECPQ2 ポストクォンタム キーアグリーメント
- [ConfigureViewInFileExplorer](/DeployEdge/microsoft-edge-policies#configureviewinfileexplorer)[エクスプローラーで表示] 機能を構成して、SharePointページのページMicrosoft Edge
- [DefaultJavaScriptJitSetting](/DeployEdge/microsoft-edge-policies#defaultjavascriptjitsetting) JavaScript JIT の使用を制御する
- [ShowPDFDefaultRecommendationsEnabled](/DeployEdge/microsoft-edge-policies#showpdfdefaultrecommendationsenabled)既定の PDF リーダーとしてMicrosoft Edge通知の設定を許可する
- [FeatureFlagOverridesControl](/DeployEdge/microsoft-edge-policies#featureflagoverridescontrol) ユーザーが機能フラグを上書きする機能を構成する
- [ImplicitSignInEnabled](/DeployEdge/microsoft-edge-policies#implicitsigninenabled) 暗黙的なサインインを有効にする
- [InternetExplorerIntegrationCloudSiteList](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudsitelist)クラウド モード Enterprise一覧を構成する
- [InternetExplorerIntegrationSiteListRefreshInterval](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationsitelistrefreshinterval)[モード サイト一覧Enterprise更新する頻度を構成する
- [JavaScriptJitAllowedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitallowedforsites) JavaScript がこれらのサイトで JIT を使用するを許可する
- [JavaScriptJitBlockedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitblockedforsites) これらのサイトで JavaScript による JIT の使用をブロックする
- [LocalBrowserDataShareEnabled](/DeployEdge/microsoft-edge-policies#localbrowserdatashareenabled)ローカル Windows閲覧データを検索Microsoft Edge有効にする
- [MAUEnabled](/DeployEdge/microsoft-edge-policies#mauenabled)Microsoft AutoUpdate を常に更新プログラムとして使用Microsoft Edge
- [MSAWebSiteSSOUsingThisProfileAllowed](/DeployEdge/microsoft-edge-policies#msawebsitessousingthisprofileallowed) このプロファイルを使用して Microsoft サイトのシングル サインオンを許可する
- [OneAuthAuthenticationEnforced](/DeployEdge/microsoft-edge-policies#oneauthauthenticationenforced)OneAuth 認証Flowサインインに適用される
- [PasswordGeneratorEnabled](/DeployEdge/microsoft-edge-policies#passwordgeneratorenabled) ユーザーがオンラインでアカウントを作成するたびに強力なパスワードの提案を受け取る
- [PrimaryPasswordSetting](/DeployEdge/microsoft-edge-policies#primarypasswordsetting) パスワード自動入力の使用中にユーザーにデバイス パスワードの入力を求める設定を構成します。
- [PrintingWebpageLayout](/DeployEdge/microsoft-edge-policies#printingwebpagelayout) 印刷のレイアウトを設定する
- [RemoteDebuggingAllowed](/DeployEdge/microsoft-edge-policies#remotedebuggingallowed) リモート デバッグを許可する
- [RelaunchWindow](/DeployEdge/microsoft-edge-policies#relaunchwindow) 再起動の時間間隔を設定する
- [TravelAssistanceEnabled](/DeployEdge/microsoft-edge-policies#travelassistanceenabled) 旅行支援を有効にする
- [TripleDESEnabled](/DeployEdge/microsoft-edge-policies#tripledesenabled) TLS で 3DES 暗号スイートを有効にする

#### <a name="deprecated-policy"></a>非推奨のポリシー

- [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) 従来の SameSite Cookie の既定の動作設定を有効にする

#### <a name="obsoleted-policy"></a>非推奨ポリシー

- [NewTabPageSetFeedType](/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype)新しいタブ Microsoft Edgeエクスペリエンスを構成する

#### <a name="additional-change"></a>その他の変更

- [ConfigureShare](/DeployEdge/microsoft-edge-policies#configureshare) Mac プラットフォームのサポートを追加する

## <a name="version-93096118-august-10"></a>バージョン 93.0.961.18: 8 月 10 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-92090262-july-29"></a>バージョン 92.0.902.62: 7 月 29 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-92090255-july-21"></a>バージョン 92.0.902.55: 7 月 21 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-92090245-july-12"></a>バージョン 92.0.902.45: 7 月 12 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-92090240-july-6"></a>バージョン 92.0.902.40: 7 月 6 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-92090222-june-21"></a>バージョン 92.0.902.22: 6 月 21 日

### <a name="feature-updates"></a>機能更新プログラム

- **アドレス バーのブラウザー履歴の自然言語検索**。 探している記事/Web サイトを見つけることは、アドレス バーから自然言語検索を行うので簡単になりました。 タイトル/URL キーワードの一致だけでなく、ページのコンテンツ/説明/タイミング (「先週のケーキレシピ」など) に基づいて検索結果を検索できます。
注: これは「制御された機能ロールアウト」です。 この機能が表示されない場合、ロールアウトは続行しますので、しばらくしてからもう一度確認してください。

- **ユーザーは、Microsoft Edge で Internet Explorer モードに簡単にアクセスできます**。 Microsoft Edge バージョン 92 から、ユーザーは、Enterprise モード サイト一覧でサイトが構成されるのを待っている間、スタンドアロンの IE 11 アプリケーションに依存する代わりに、Microsoft Edge の Internet Explorer モードでサイトを再読み込みできます。 ユーザーは、サイトをローカル サイト リストに追加するように求められます。Microsoft Edge で同じページに移動すると、次の 30 日間 IE モードで自動的にレンダリングされます。 *[InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed)* ポリシーを使用して、このエクスペリエンスを構成し、IE モードのエントリ ポイントへのアクセスと、ローカル サイト リストにサイトを追加する機能を許可できます。 *[InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays)* ポリシーを使用して、サイトをローカル サイト リストに保持する日数を調整できます。
Windows 10 バージョン 1909 の場合、KB5003698 以降が必要であることに注意してください。エンド ツー エンドのエクスペリエンスを実現するには、Windows 10 バージョン 2004、Windows 10 バージョン 20H2、または Windows 10 バージョン 21H1 の場合、 KB5003690 以降が必要です。

- **MHTML ファイルは、既定では Internet Explorer モードで開きます**。 Microsoft Edge バージョン 92 Stable 以降、MHTML ファイルの種類は、Internet Explorer (IE11) アプリケーションではなく、Microsoft Edge の Internet Explorer モードで自動的に開きます。 これは、ブラウザーで Outlook のメールを表示しようとしているときに最もよく見られます。 この変更は、IE11 がこのファイルの種類の既定のハンドラーである場合にのみ発生します。 これを変更したい場合は、[このガイダンス](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)を使用して、Stable バージョン 92 更新プログラムをインストールする前に実行できます。

- **支払い手段がデバイス間で同期されるようになりました**。 Microsoft Edge バージョン 92 以降には、サインインしたデバイス間で支払い情報を同期するオプションがあります。
注: これは「制御された機能ロールアウト」です。 この機能が表示しない場合は、ロールアウトを続行する間にもう一度確認してください。

- **"開発者モード拡張機能を無効にする" という警告は完全に無視できます**。 Microsoft Edge バージョン 92 以降では、[これを再度表示しない] オプションをクリックして、"開発者モード拡張機能を無効にする" という警告をオフにすることができます。
注: これは「制御された機能ロールアウト」です。 この機能が表示しない場合は、ロールアウトを続行する間にもう一度確認してください。

- **直接ツール バーから拡張情報を管理します**。 ツール バーのまったく新しい拡張機能メニューを使用すると、拡張機能を簡単に非表示またはピン留めできます。 拡張機能を管理し、新しい拡張機能を検索するためのクイック リンクでは、新しい拡張機能を簡単に見つけて、既存の拡張機能を管理できます。
注: これは「制御された機能ロールアウト」です。 この機能が表示しない場合は、ロールアウトを続行する間にもう一度確認してください。

- **自動 HTTPS**。 ユーザーには、このより安全なプロトコルをサポートする可能性が高いドメインで、ナビゲーションを HTTP から HTTPS にアップグレードするオプションがあります。 このサポートは、すべてのドメインに対して HTTPS 経由での配信を試行するように構成することもできます。
注: この機能は実験中です。実験をオプトアウトした場合、この動作は見られません。

- **フォント レンダリングパフォーマンスの改善**。 テキストのレンダリングが改善され、明瞭性が向上し、ぼやけ感が軽減されました。
注: これは「制御された機能ロールアウト」です。 この機能が表示しない場合は、ロールアウトを続行する間にもう一度確認してください。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

8 つの新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://www.microsoft.com/edge/business/download)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) このプロファイルを使用した職場または学校のサイトへのシングル サインオンが有効になっています。
- [AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) 自動 HTTPS を構成する
- [HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) ヘッドレス モードの使用を制御する
- [InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) 安全でない Web サイトが、よりプライベートなネットワーク エンドポイントに対して要求を行うのを許可するかどうかを指定します。
- [InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) リストされたサイトが安全でないコンテキストからよりプライベートなネットワーク エンドポイントに要求を行うのを許可する
- [InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) サイトがローカル IE モード サイト リストに残る日数を指定する
- [InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) Internet Explorer モードで未構成のサイトを再度読み込みできるようにする
- [SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) 非クロスオリジン分離コンテキストで SharedArrayBuffers を使用できるかどうかを指定する

#### <a name="obsoleted-policy"></a>非推奨ポリシー

- [EnableSha1ForLocalAnchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) ローカル信頼アンカーによって発行された SHA-1 を使用して署名された証明書を許可します。

## <a name="version-9209029-june-8"></a>バージョン 92.0.902.9: 6 月 8 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-91086441-june-3"></a>バージョン 91.0.864.41: 6 月 3 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-91086437-may-27"></a>バージョン 91.0.864.37: 5 月 27 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-91086436-may-26"></a>バージョン 91.0.864.36: 5 月 26 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-91086433-may-21"></a>バージョン 91.0.864.33: 5 月 21 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-91086427-may-14"></a>バージョン 91.0.864.27: 5 月 14 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-91086419-may-7"></a>バージョン 91.0.864.19: 5 月 7 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-91086415-may-3"></a>バージョン 91.0.864.15: 5 月 3 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-91086411-april-30"></a>バージョン 91.0.864.11: 4 月 30 日

### <a name="feature-updates"></a>機能更新プログラム

- **プロキシ レベルで Microsoft Defender Application Guard コンテナーから発信されたネットワーク トラフィックを特定します**。 Microsoft Edge バージョン 91 以降、Application Guard コンテナーから発信されるネットワーク トラフィックにタグ付けするためのサポートが組み込まれたため、企業はそれらを識別し、特定のポリシーを適用できます。

- **ホストから Edge Application Guard コンテナーへのお気に入りの同期を許可するサポート オプション**。 Microsoft Edge バージョン 91 以降、ユーザーには、ホストからコンテナーにお気に入りを同期するように Application Guard を構成するオプションがあります。 これにより、新しいお気に入りがコンテナーにも表示されます。

- **音声認識 API のサポート**。 Microsoft Edge バージョン 91 以降、Google.com および同様のサイトでの音声認識コマンドの API サポートが追加されます。 この機能は、実験を有効にしたユーザーのランダムに選択されたグループに限定されます。 これらのユーザーは、機能チームにフィードバックを提供しています。

- **新しいテーマの色でブラウザーをカスタマイズします**。 [設定] > [デザイン ページ] にある 14 の新しいテーマ カラーの 1 つを使用して、Microsoft Edge を独自のものにします。 Microsoft Edge アドオン サイトからカスタム テーマをインストールすることもできます。 [詳細情報](https://techcommunity.microsoft.com/t5/articles/make-microsoft-edge-your-own-with-themes/m-p/2083165)

- **ダウンロードの中断** Microsoft Edge バージョン 91 以降、ブラウザーは、ユーザー操作なしでダウンロードが開始され、SmartScreen アプリケーション評価チェックでサポートされない場合に、コンピューターに害を及ぼす可能性のある種類のダウンロードを自動的に中断します。 ユーザーは、ダウンロード アイテムを右クリックして [保持] を選択することにより、上書きしてダウンロードを続行できます。
企業の管理者は、次の 2 つのポリシーのいずれかでこの動作をオプトアウトできます。
    - [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - ドメイン上の指定されたファイルの種類のダウンロード ファイルの種類の拡張子に基づいた警告を無効にする 詳細については、「[Microsoft Edge セキュリティのダウンロードの中断](/deployedge/microsoft-edge-security-downloads-interruptions)」を参照してください

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

6 つの新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://www.microsoft.com/edge/business/download)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) - Application Guard トラフィック ID
- [ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) - 明示的に許可されたネットワーク ポート
- [ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) - スタートアップ ページ設定のインポートを許可する
- [MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) - ユーザーが数学の問題を切り取って、Microsoft Edge の段階的な説明で解決策を得ることができる
- [NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) - 新しいタブ ページで Microsoft ニュース コンテンツを許可する
- [NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) - 新しいタブ ページでクイック リンクを許可する

#### <a name="obsoleted-policy"></a>非推奨ポリシー

- [ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - プロアクティブ認証を有効にする
<!-- end major 91 -->

## <a name="version-90081846-april-22"></a>バージョン 90.0.818.46: 4 月 22 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-90081842-april-20"></a>バージョン 90.0.818.42: 4 月 20 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-90081841-april-16"></a>バージョン 90.0.818.41: 4 月 16 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-90081838-april-14"></a>バージョン 90.0.818.38: 4 月 14 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-90081836-april-12"></a>バージョン 90.0.818.36: 4 月 12 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-90081827-april-2"></a>バージョン 90.0.818.27: 4 月 2 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-90081822-march-29"></a>バージョン 90.0.818.22: 3 月 29 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-90081814-march-22"></a>バージョン 90.0.818.14: 3 月 22 日

さまざまなバグとパフォーマンスの問題を修正しました。
<!-- begin major 90 -->
## <a name="version-9008188-march-16"></a>バージョン 90.0.818.8: 3 月 16 日

### <a name="feature-updates"></a>機能更新プログラム

- **シングル サインオン (SSO) は、Mac OS の Azure Active Directory (Azure AD) アカウントと Microsoft アカウント (MSA) で利用できます**。 macOS で Microsoft Edge にサインインしたユーザーは、Work アカウントと Microsoft アカウント (bing.com、office.com、msn.com、outlook.com など) でシングル サインオンを許可するように構成された Web サイトに自動的にサインインします。

- **キオスク モード。** Microsoft Edge バージョン 90 以降、UI の印刷設定をロックダウンして、構成済みのプリンターと [PDFに印刷] オプションのみを許可しました。 また、割り当てられたアクセスのシングル アプリ キオスク モード内で改善を行い、ブラウザーからの他のアプリケーションの起動を制限しました。 キオスク モードの機能の詳細については、[こちら](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features)をご覧ください。

- **印刷:**

  - **PostScript プリンターではないプリンター向けの新しい印刷ラスタライズ モード**。 Microsoft Edge バージョン 90 より、管理者は新しいポリシーを使用して、ユーザーの印刷ラスタライズ モードを定義できます。 このポリシーは、Windows の PostScript プリンターではないプリンターから Microsoft Edge で印刷する方法を制御します。  PostScript プリンターではないプリンターの印刷ジョブが正しく印刷されるようにラスター化する必要がある場合があります。 印刷オプションには「フル」と 「高速」が表示されます。

  - **追加された、印刷用のページ拡大/縮小オプション**。 ユーザーは、追加のオプションを使用して Web ページや PDF ドキュメントを印刷しながらスケーリングをカスタマイズできるようにりました。 [ページサイズに合わせて印刷] オプションを使用すると、印刷用に選択した "用紙サイズ" に Web ページまたはドキュメントを収めることがきます。 「実際のサイズ」オプションを選択すと、選択した「用紙サイズ」に関係なく、印刷されるコンテンツのサイズに変更が加えられないようにします。

- **生産性:**

  - **オートフィル候補が拡張され、クリップボードのアドレス フィールドのコンテンツが含まれるようになりました**。 クリップボードの内容は、オートフィル候補として表示するプロフィール フィールドまたはアドレス フィールド (電話番号、メールアドレス、郵便番号、市区町間、州など) をクリックすると解析されます。

  - **ユーザーは、フォームやフィールドが候補として検出されない場合でも、オートフィル候補を検索できます**。 現在、Microsoft Edge に情報を保存している場合、オートフィル候補が自動的にポップアップ表示され、フォームに入力する時間を節約できます。 オートフィルでフォームが見つからない場合や、通常オートフィルを設定しないフォーム (一時的なフォームなど) のデータを取得する場合は、オートフィルを使用して情報を検索することができます。

- **Access はメニュー バーのフライアウトからダウンロードしています**。 ダウンロードは右上隅に表示され、アクティブなすべてのダウンロードが 1 か所に表示されます。 このメニューは簡単に閉じることができるので、ユーザーは作業を中断することなく、閲覧を続けることができます。また、ダウンロードの全体的な進行状況をツールバーからすぐに監視できます。 [詳しくはこちらをご覧ください](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551)。


### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

7 個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://www.microsoft.com/edge/business/download)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [ApplicationGuardFaitesSyncEnabled](./microsoft-edge-policies.md#applicationguardfavoritessyncenabled) - Application Guard のお気に入りの同期の有効化
- [ManagedConfigurationPerOrigin](./microsoft-edge-policies.md#managedconfigurationperorigin) - Web サイトの管理された構成値を特定のオリジンに設定する
- [PrintRasterizationMode](./microsoft-edge-policies.md#printrasterizationmode) - 印刷ラスタライズ モード
- [QuickViewOfficeFilesEnabled](./microsoft-edge-policies.md#quickviewofficefilesenabled) - Microsoft Edge で QuickView Office ファイル機能を管理する
- [SSLErrorOvererrorallowedForOrigins](./microsoft-edge-policies.md#sslerroroverrideallowedfororigins) - 特定の生成元の HTTPS 警告ページからユーザーが進むのを許可する
- [WindowOcclusionEnabled](./microsoft-edge-policies.md#windowocclusionenabled) - Window Occlusion を有効にする
- [WindowsHelloForHTTPAuthEnabled](./microsoft-edge-policies.md#windowshelloforhttpauthenabled) - HTTP 認証用 Windows Hello を有効にする

#### <a name="deprecated-policies"></a>廃止されたポリシー

- [NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - ネイティブ ウィンドウ オクルージョンを有効にする。
- [SSLVersionMin](./microsoft-edge-policies.md#sslversionmin)- 最小限の TLS バージョンを有効になっています
<!-- end major 90 -->

## <a name="version-89077454-march-13"></a>バージョン 89.0.774.54: 3 月 13 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-89077450-march-10"></a>バージョン 89.0.774.50: 3 月 10 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-89077448-march-8"></a>バージョン 89.0.774.48: 3 月 8 日

さまざまなバグとパフォーマンスの問題を修正しました。

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

<!--- Archived from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 ---->
<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
