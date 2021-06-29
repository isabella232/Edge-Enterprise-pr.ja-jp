---
title: Beta チャネルに関する Microsoft Edge のリリース ノート
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 06/25/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Beta チャネルに関する Microsoft Edge のリリース ノート
ms.openlocfilehash: a4ef80420bfa87bf5fcfa154937ebe52b7cb375f
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617937"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge Beta チャネルのリリースノート

これらのリリース ノートでは、Microsoft Edge Beta チャネルに含まれている新機能とセキュリティ以外の更新プログラムに関する情報を提供します。 これらのリリース ノートのアーカイブ バージョンは、[こちら](microsoft-edge-relnote-archive-beta-channel.md)から入手できます。

> [!NOTE]
> Microsoft Edge Web プラットフォームは、ユーザー エクスペリエンス、セキュリティ、およびプライバシーを向上させるために絶えず進化しています。 詳細については、「[Microsoft Edge 向けのサイトの互換性に影響する変更点](/microsoft-edge/web-platform/site-impacting-changes)」を参照してください。

## <a name="version-92090222-june-21"></a>バージョン 92.0.902.22: 6 月 21 日

### <a name="feature-updates"></a>機能更新プログラム

- **ユーザーは、Microsoft Edge で Internet Explorer モードに簡単にアクセスできます**。 Microsoft Edge バージョン 92 から、ユーザーは、Enterprise モード サイト一覧でサイトが構成されるのを待っている間、スタンドアロンの IE 11 アプリケーションに依存する代わりに、Microsoft Edge の Internet Explorer モードでサイトを再読み込みできます。 ユーザーは、サイトをローカル サイト リストに追加するように求められます。Microsoft Edge で同じページに移動すると、次の 30 日間 IE モードで自動的にレンダリングされます。 *[InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed)* ポリシーを使用して、このエクスペリエンスを構成し、IE モードのエントリ ポイントへのアクセスと、ローカル サイト リストにサイトを追加する機能を許可できます。 *[InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays)* ポリシーを使用して、サイトをローカル サイト リストに保持する日数を調整できます。
Windows 10 バージョン 1909 の場合、KB5003698 以降が必要であることに注意してください。エンド ツー エンドのエクスペリエンスを実現するには、Windows 10 バージョン 2004、Windows 10 バージョン 20H2、または Windows 10 バージョン 21H1 の場合、 KB5003690 以降が必要です。

- **MHTML ファイルは、既定では Internet Explorer モードで開きます**。 Microsoft Edge バージョン 92 Stable 以降、MHTML ファイルの種類は、Internet Explorer (IE11) アプリケーションではなく、Microsoft Edge の Internet Explorer モードで自動的に開きます。 これは、ブラウザーで Outlook のメールを表示しようとしているときに最もよく見られます。 この変更は、IE11 がこのファイルの種類の既定のハンドラーである場合にのみ発生します。 これを変更したい場合は、[このガイダンス](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)を使用して、Stable バージョン 92 更新プログラムをインストールする前に実行できます。

- **支払い手段がデバイス間で同期されるようになりました**。 Microsoft Edge バージョン 92 以降には、サインインしたデバイス間で支払い情報を同期するオプションがあります。
注: これは制御された機能ロールアウトであり、現在 50% です。 この機能が表示されない場合は、ロールアウトを続行しますので、しばらくしてからもう一度確認してください。

- **"開発者モード拡張機能を無効にする" という警告は完全に無視できます**。 Microsoft Edge バージョン 92 以降では、[これを再度表示しない] オプションをクリックして、"開発者モード拡張機能を無効にする" という警告をオフにすることができます。
注: これは制御された機能ロールアウトであり、現在 25% です。 この機能が表示されない場合は、ロールアウトを続行しますので、しばらくしてからもう一度確認してください。

- **ツール バーから直接拡張機能を管理します**。 ツール バーのまったく新しい拡張機能メニューを使用すると、拡張機能を簡単に非表示またはピン留めできます。 拡張機能を管理し、新しい拡張機能を検索するためのクイック リンクでは、新しい拡張機能を簡単に見つけて、既存の拡張機能を管理できます。
注: これは制御された機能ロールアウトであり、現在 25% です。 この機能が表示されない場合は、ロールアウトを続行しますので、しばらくしてからもう一度確認してください。

- **自動 HTTPS**。 ユーザーには、このより安全なプロトコルをサポートする可能性が高いドメインで、ナビゲーションを HTTP から HTTPS にアップグレードするオプションがあります。 このサポートは、すべてのドメインに対して HTTPS 経由での配信を試行するように構成することもできます。
注: この機能は実験中です。実験をオプトアウトした場合、この動作は見られません。

- **フォント レンダリングパフォーマンスの改善**。 テキストのレンダリングが改善され、明瞭性が向上し、ぼやけ感が軽減されました。
注: これは制御された機能ロールアウトであり、現在 25% です。 この機能が表示されない場合は、ロールアウトを続行しますので、しばらくしてからもう一度確認してください。

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
- [AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) このプロファイルを使用した職場または学校のサイトへのシングル サインオンが有効になっています。
- [AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) 自動 HTTPS を構成します。
- [HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) ヘッドレス モードの使用を制御します。
- [InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) 安全でない Web サイトが、よりプライベートなネットワーク エンドポイントに対して要求を行うのを許可するかどうかを指定します。
- [InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) リストされたサイトが安全でないコンテキストからよりプライベートなネットワーク エンドポイントに要求を行うのを許可します。
- [InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) サイトがローカル IE モード サイト リストに残る日数を指定します。
- [InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) Internet Explorer モードで未構成のサイトを再度読み込みできるようにします。
- [SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) 非クロスオリジン分離コンテキストで SharedArrayBuffers を使用できるかどうかを指定します。

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
