---
title: Stable チャネルに関する Microsoft Edge リリース ノート
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 08/19/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Stable チャネルに関する Microsoft Edge リリース ノート
ms.openlocfilehash: 6a4c65d253a88384da7393ab846777093dc86e86
ms.sourcegitcommit: 584a6a9877ae0c3fcb9acc0b8c158e280b0360ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11912062"
---
# <a name="release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge Stable チャネルのリリース ノート

これらのリリース ノートでは、Microsoft Edge Stable チャネルに含まれている新機能とセキュリティ以外の更新プログラムに関する情報を提供します。

- すべてのセキュリティの更新プログラムは、[ここ](microsoft-edge-relnotes-security.md)に記載されています。
- Microsoft Edge 安定チャネルのアーカイブされたリリース ノートは、[こちら](microsoft-edge-relnote-archive-stable-channel.md)にあります。

 Microsoft Edge チャネルを理解するには、「[Microsoft Edge チャネルの概要](microsoft-edge-channels.md)」を参照してください。

> [!NOTE]
> 安定チャネルの場合、更新は 1 日以上かけて段階的に公開されます。 詳細については、「[Microsoft Edge 更新プログラムの段階的なロールアウト](microsoft-edge-update-progressive-rollout.md)」を参照してください。
>
> Microsoft Edge Web プラットフォームは、ユーザー エクスペリエンス、セキュリティ、およびプライバシーを向上させるために絶えず進化しています。 詳細については、「[Microsoft Edge のサイトの互換性に影響する変更点](/microsoft-edge/web-platform/site-impacting-changes)」を参照してください。

## <a name="version-92090278-august-19"></a>バージョン 92.0.902.78: 8 月 19 日

安定したチャネルのセキュリティ更新プログラムは[こちら](/deployedge/microsoft-edge-relnotes-security#august-19-2021)に記載されています。

## <a name="version-92090273-august-12"></a>バージョン 92.0.902.73: 8 月 12 日

様々なバグとパフォーマンスの問題を修正しました。

## <a name="version-92090267-august-5"></a>バージョン 92.0.902.67: 8 月 5 日

Stable チャネルのセキュリティ更新プログラムは[こちら](/deployedge/microsoft-edge-relnotes-security#august-05-2021)に記載されています。

## <a name="version-92090262-july-29"></a>バージョン 92.0.902.62: 7 月 29 日

いくつかのバグとパフォーマンスの問題を修正しました。

### <a name="modified-policy"></a>変更されたポリシー

- AutoplayAllowed – "無効" に設定すると、メディアの自動再生が "制限" に設定されるようになりました

## <a name="version-92090255-july-22"></a>バージョン 92.0.902.55: 7 月 22 日

Stable チャネルのセキュリティ更新プログラムは[こちら](/deployedge/microsoft-edge-relnotes-security#july-22-2021)に記載されています。

### <a name="feature-updates"></a>機能更新プログラム

**ユーザーは、Microsoft Edge で Internet Explorer モードに簡単にアクセスできます**。 Microsoft Edge バージョン 92 から、ユーザーは、Enterprise モード サイト一覧でサイトが構成されるのを待っている間、スタンドアロンの IE 11 アプリケーションに依存する代わりに、Microsoft Edge の Internet Explorer モードでサイトを再読み込みできます。 ユーザーは、サイトをローカル サイト リストに追加するように求められます。Microsoft Edge で同じページに移動すると、次の 30 日間 IE モードで自動的にレンダリングされます。 [InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) ポリシーを使用して、このエクスペリエンスを構成し、IE モードのエントリ ポイントへのアクセスと、ローカル サイト リストにサイトを追加する機能を許可できます。 [InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) ポリシーを使用して、サイトをローカル サイト リストに保持する日数を調整できます。 Windows 10 バージョン 1909 の場合、KB5003698 以降が必要であることに注意してください。エンド ツー エンドのエクスペリエンスを実現するには、Windows 10 バージョン 2004、Windows 10 バージョン 20H2、または Windows 10 バージョン 21H1 の場合、 KB5003690 以降が必要です。 詳細については、[「IE モードのローカル サイト一覧」](/deployedge/edge-ie-mode-local-site-list)を参照してください。

**MHTML ファイルは、既定では Internet Explorer モードで開きます**。 Microsoft Edge バージョン 92 Stable 以降、MHTML ファイルの種類は、Internet Explorer (IE11) アプリケーションではなく、Microsoft Edge の Internet Explorer モードで自動的に開きます。 これは、ブラウザーで Outlook のメールを表示しようとしているときに最もよく見られます。 この変更は、IE11 がこのファイルの種類の既定のハンドラーである場合にのみ発生します。 これを変更したい場合は、[このガイダンス](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)を使用して、Stable バージョン 92 更新プログラムをインストールする前に実行できます。

**"開発者モード拡張機能を無効にする" という警告は 2 週間の間完全に無視できます**。 Microsoft Edge バージョン 92 以降、警告ダイアログのドロップダウンでオプションを選択することで、"開発者モードの拡張機能を無効にする "という警告を 2 週間スヌーズすることができます。

**直接ツール バーから拡張情報を管理します**。 ツール バーのまったく新しい拡張機能メニューを使用すると、拡張機能を簡単に非表示またはピン留めできます。 拡張機能を管理し、新しい拡張機能を検索するためのクイック リンクでは、新しい拡張機能を簡単に見つけて、既存の拡張機能を管理できます。

**自動再生の既定値は [制限] に設定されます**。  持続的にオンラインへフォーカスしていくために、Microsoft Edge バージョン 92 から、メディアの自動再生の既定値が [許可] から [制限] に変更されます。

**支払い手段がデバイス間で同期されるようになりました**。 Microsoft Edge バージョン 92 以降には、サインインしたデバイス間で支払い情報を同期するオプションがあります。 注: これは「制御された機能ロールアウト」です。 この機能が表示されない場合、ロールアウトは続行しますので、しばらくしてからもう一度確認してください。
現在、この機能は米国でのみ使用可能で、MSA ユーザー向けのみ (AAD ではありません) 使用可能です

**フォント レンダリングの改善**。 テキストのレンダリングが改善され、明瞭性が向上し、ぼやけ感が軽減されました。 注: これは「制御された機能ロールアウト」です。 この機能が表示されない場合、ロールアウトは続行しますので、しばらくしてからもう一度確認してください。

**[お気に入り] や [コレクション] のようなツール バー ボタン 機能は、ウィンドウの側面にピン留めして、ユーザーの選択を保存します**。 既定で有効になっています。ユーザーがツール バー ボタンをピン留めする選択をした場合、ピン留めを解除するまで、常にピン留め状態で開きます。

**ユーザーは、グループ ポリシーを使用して [このプロファイルを使用して、職場または学校サイトにシングル サインオンを許可する] オプションを管理できます**。  [このプロファイルを使用して、職場または学校サイトにシングル サインオンを許可する] は、AAD 以外のプロファイルには、コンピューターにある職場または学校の資格情報を使用して、職場または学校サイトでシングル サインオンを使用できるようになります。 このオプションは、AAD 以外のプロファイルに対してのみ、エンド ユーザー向けにトグルとして、[設定] -> [プロファイル] -> [プロファイルのユーザー設定] に表示されます。  [AADWebSiteSSOUsingThisProfileEnabled](/deployedge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled)ポリシーを使用して動作を構成できます。  

**パスワードの正常性** オンラインで安全を保つには、さまざまなアカウントのすべてに渡って強力で個別にパスワードを使用することが重要です。 ただし、これは行うよりも言うは易しで、ほとんどのユーザーは、推測しやすい弱いパスワードの使用や、複数のアカウントに跨って強力だが同一のパスワードを再利用するなど、脆弱なパスワード習慣の傾向を示します。

この最新バージョンの Microsoft Edge で、強力で個別のパスワードを使用するタスクが少しだけ簡単になります。 Microsoft Edge は、保存されたパスワードが十分に強力であるかどうかを示し、そして複数のサイトで使用されたかどうかを指摘することで、オンラインでの安全性の維持に役立ちます。 パスワードの正常性は、 edge://settings/passwords にある保存済みパスワードの一覧で確認できます。
  
**保存したパスワードのプライバシーを追加しました** 他のユーザーと共有しているデバイスを使用している場合や、何らかの理由でコンピューターのロックを解除したまま離席した場合に、他のユーザーが Web サイトのパスワードにアクセスできないように、デバイスのパスワードを使用した 2 段階検証を選択できます。 シンプル!

**Outlook 拡張子**。  Microsoft Outlook の受信箱、予定表、タスクその他を、新規のブラウザ ウィンドウを開かずとも、その上部に表示します。  新しい Outlook 拡張機能はこちらで入手できます: [Microsoft Outlook - Microsoft Edge Addons](https://microsoftedge.microsoft.com/addons/detail/microsoft-outlook/kkpalkknhlklpbflpcpkepmmbnmfailf?hl=en-US)

**Chromium オープン ソース プロジェクトに合わせて、Microsoft Edge では表のレンダリング方法を更新しています**。 この変更で既知の問題が修正され、Microsoft Edge では表を改善し Web やその他のブラウザー間で適切にレンダリングできるようにしました。 予期しない問題が発生した場合は、環境内の重要なワークフローをテストすることをお勧めします。 詳細な説明については、[こちら](https://docs.google.com/document/d/16PFD1GtMI9Zgwu0jtPaKZJ75Q2wyZ9EZnVbBacOfiNA/edit) を参照してください。

### <a name="new-policies"></a>新しいポリシー

- [AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) 職場または学校サイトへのシングル サインオンを有効化したプロファイル
- [AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) 自動 HTTPS を構成する
- [HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) ヘッドレス モードの使用を制御する
- [InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) 安全でない Web サイトが、よりプライベートなネットワーク エンドポイントに対して要求を行うことを許可するかどうかを指定します。
- [InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) リストされたサイトが安全でないコンテキストから、よりプライベートなネットワーク エンドポイントに要求を行うことを許可する
- [InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) サイトがローカル IE モード サイト リストに残る日数を指定する
- [InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) Internet Explorer モードで未構成のサイトを再度読み込みできるようにする
- [SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) 非クロスオリジン分離コンテキストで SharedArrayBuffers を使用できるかどうかを指定する

### <a name="deprecated-policy"></a>非推奨のポリシー

- [InternetExplorerIntegrationTestingAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) Internet Explorer モードのテストを許可する

### <a name="obsoleted-policy"></a>廃止されたポリシー

- [EnableSha1ForLocalAnchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) ローカル トラスト アンカーによって発行され、SHA-1 を使用して署名された証明書を許可する

## <a name="version-91086471-july-19"></a>バージョン 91.0.864.71: 7 月 19 日

> [!Important]
>この更新プログラムには、[CVE-2021-30563](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30563) が含まれています。これについては、Chromium チームより実際に悪用された事例が報告されています。 詳細については、「[セキュリティ更新プログラム ガイド](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)」を参照してください。

Stable チャネルのセキュリティ更新プログラムは[こちら](/deployedge/microsoft-edge-relnotes-security#july-19-2021)に記載されています。

## <a name="version-91086467-july-8"></a>バージョン 91.0.864.67: 7 月 8 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-91086464-july-2"></a>バージョン 91.0.864.64: 7 月 2 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-91086459-june-24"></a>バージョン 91.0.864.59: 6 月 24 日

安定したチャネルのセキュリティ更新プログラムは[こちら](/deployedge/microsoft-edge-relnotes-security#june-24-2021)に記載されています。

## <a name="version-91086454-june-18"></a>バージョン 91.0.864.54: 6 月 18 日

> [!Important]
> この更新プログラムには、[CVE-2021-30554](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30554) が含まれています。これについては、Chromium チームにより実際に感染報告がある悪用が報告されています。 詳細については、「[セキュリティ更新プログラム ガイド](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)」を参照してください。

安定したチャネルのセキュリティ更新プログラムは[こちら](/deployedge/microsoft-edge-relnotes-security#june-18-2021)に記載されています。

## <a name="version-91086448-june-11"></a>バージョン 91.0.864.48: 6 月 11 日

> [!Important]
>この更新プログラムには、[CVE-2021-30551](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30551) が含まれています。これについては、Chromium チームにより実際に感染報告がある悪用が報告されています。 詳細については、「[セキュリティ更新プログラム ガイド](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)」を参照してください。

安定したチャネルのセキュリティ更新プログラムは[こちら](/deployedge/microsoft-edge-relnotes-security#june-11-2021)に記載されています。

## <a name="version-91086441-june-3"></a>バージョン 91.0.864.41: 6 月 3 日

安定したチャネルのセキュリティ更新プログラムは[こちら](/deployedge/microsoft-edge-relnotes-security#june-3-2021)に記載されています。

## <a name="version-91086437-may-27"></a>バージョン 91.0.864.37: 5 月 27 日

安定したチャネルのセキュリティ更新プログラムは[こちら](/deployedge/microsoft-edge-relnotes-security#may-27-2021)に記載されています。

### <a name="feature-updates"></a>機能更新プログラム

- **プロキシ レベルで Microsoft Defender Application Guard コンテナーから発信されたネットワーク トラフィックを特定します**。 Microsoft Edge バージョン 91 以降、Application Guard コンテナーから発信されるネットワーク トラフィックにタグ付けするためのサポートが組み込まれたため、企業はそれらを識別し、特定のポリシーを適用できます。

- **ホストから Edge Application Guard コンテナーへのお気に入りの同期を許可するサポート オプション**。 Microsoft Edge バージョン 91 以降、ユーザーには、ホストからコンテナーにお気に入りを同期するように Application Guard を構成するオプションがあります。 これにより、新しいお気に入りがコンテナーにも表示されます。

- **Microsoft Edge バージョン 91 以降、ブラウザーは、ユーザー操作なしでダウンロードが開始され、SmartScreen アプリケーション評価チェックでサポートされない場合に、コンピューターに害を及ぼす可能性のある種類のダウンロードを自動的に中断します**。 ユーザーは、ダウンロード アイテムを右クリックして [保持] を選択することにより、上書きしてダウンロードを続行できます。 企業の管理者は、次のポリシーを構成することにより、この動作をオプトアウトできます。
  - [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings.md) - ドメイン上の指定されたファイルの種類のダウンロード ファイルの種類の拡張子に基づいた警告を無効にする

    詳細については、「[Microsoft Edge セキュリティのダウンロードの中断](microsoft-edge-security-downloads-interruptions.md)」を参照してください。

- **音声認識 API のサポート**。 Microsoft Edge バージョン 91 以降、Google.com および同様のサイトでの音声認識コマンドの API サポートが追加されます。 この機能は、実験を有効にしたユーザーのランダムに選択されたグループに限定されます。 これらのユーザーは、機能チームにフィードバックを提供しています。

- **新しいテーマの色でブラウザーをカスタマイズします**。 [設定] > [デザイン ページ] にある 14 の新しいテーマ カラーの 1 つを使用して、Microsoft Edge を独自のものにします。 Microsoft Edge アドオン サイトからカスタム テーマをインストールすることもできます。 [詳細情報](https://techcommunity.microsoft.com/t5/articles/make-microsoft-edge-your-own-with-themes/m-p/2083165)

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

## <a name="version-90081866-may-20"></a>バージョン 90.0.818.66: 5 月 20 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-90081862-may-13"></a>バージョン 90.0.818.62: 5 月 13 日

安定したチャネルのセキュリティ更新プログラムは[こちら](/deployedge/microsoft-edge-relnotes-security#may-13-2021)に記載されています。

## <a name="version-90081856-may-6"></a>バージョン 90.0.818.56: 5 月 6 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-90081851-april-29"></a>バージョン 90.0.818.51: 4 月 29 日

安定したチャネルのセキュリティ更新プログラムは[こちら](/deployedge/microsoft-edge-relnotes-security#april-29-2021)に記載されています。

## <a name="version-90081849-april-26"></a>バージョン 90.0.818.49: 4 月 26 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-90081846-april-22"></a>バージョン 90.0.818.46: 4 月 22 日 ##

安定したチャネルのセキュリティ更新プログラムは[こちら](/deployedge/microsoft-edge-relnotes-security#april-22-2021)に記載されています。

## <a name="version-90081842-april-19"></a>バージョン 90.0.818.42: 4 月 19 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-90081841-april-16"></a>バージョン 90.0.818.41: 4 月 16 日 ##

> [!Important]
>この更新プログラムには[CVE-2021-21224](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21224)が含まれているが、これは、Chromiumチームによって悪用されたと報告されています。 詳細については、「[セキュリティ更新プログラム ガイド](https://msrc.microsoft.com/update-guide)」を参照してください。

安定したチャネルのセキュリティ更新プログラムは[こちら](/deployedge/microsoft-edge-relnotes-security#april-16-2021)に記載されています。

## <a name="version-90081839-april-15"></a>バージョン 90.0.818.39: 4 月 15 日 ##

安定したチャネルのセキュリティ更新プログラムは[こちら](/deployedge/microsoft-edge-relnotes-security#april-15-2021)に記載されています。

## <a name="feature-updates"></a>機能更新プログラム ##

-    **シングル サインオン (SSO) は、macOS の Azure Active Directory (Azure AD) アカウントと Microsoft アカウント (MSA) で利用できます。** macOS で Microsoft Edge にサインインしたユーザーは、Work アカウントと Microsoft アカウント (bing.com、office.com、msn.com、outlook.com など) でシングル サインオンを許可するように構成された Web サイトに自動的にサインインします。

- **キオスク モード。** Microsoft Edge バージョン 90 以降、UI の印刷設定をロックダウンして、構成済みのプリンターと [PDFに印刷] オプションのみを許可しました。 また、割り当てられたアクセスのシングル アプリ キオスク モード内で改善を行い、ブラウザーからの他のアプリケーションの起動を制限しました。 キオスク モードの機能の詳細については、[こちら](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features)をご覧ください。

- **ダウンロードの中断** Microsoft Edge バージョン 91 以降、ブラウザーは、ユーザー操作なしでダウンロードが開始され、SmartScreen アプリケーション評価チェックでサポートされない場合に、コンピューターに害を及ぼす可能性のある種類のダウンロードを自動的に中断します。 ユーザーは、ダウンロード アイテムを右クリックして [保持] を選択することにより、上書きしてダウンロードを続行できます。
企業の管理者は、次の 2 つのポリシーのいずれかでこの動作をオプトアウトできます。
- [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - ドメイン上の指定されたファイルの種類のダウンロード ファイルの種類の拡張子に基づいた警告を無効にする 詳細については、「[Microsoft Edge セキュリティのダウンロードの中断](/deployedge/microsoft-edge-security-downloads-interruptions)」を参照してください

- **印刷**:

    - **PostScript プリンターではないプリンター向けの新しい印刷ラスタライズ モード。** Microsoft Edge バージョン 90 より、管理者は新しいポリシーを使用して、ユーザーの印刷ラスタライズ モードを定義できます。 このポリシーは、Microsoft Edge が Windows 上の PostScript プリンターではないプリンターに印刷する方法を制御します。 PostScript プリンターではないプリンターの印刷ジョブが正しく印刷されるようにラスター化する必要がある場合があります。 印刷オプションには "Full (フル)" と "Fast (高速)"が表示されます。
    
  - **追加された、印刷用のページ拡大/縮小オプション。** ユーザーは、追加のオプションを使用して Web ページや PDF ドキュメントを印刷しながらスケーリングをカスタマイズできるようになりました。 [ページサイズに合わせて印刷] オプションを使用すると、印刷用に選択した "用紙サイズ" に Web ページまたはドキュメントを収めることがきます。 「実際のサイズ」オプションを選択すと、選択した「用紙サイズ」に関係なく、印刷されるコンテンツのサイズに変更が加えられないようにします。

-   **生産性:**

    -   **オートフィル候補が拡張され、クリップボードのアドレス フィールドのコンテンツが含まれるようになりました。** クリップボードの内容は、オートフィル候補として表示するプロフィール フィールドまたはアドレス フィールド (電話番号、メールアドレス、郵便番号、市区町間、州など) をクリックすると解析されます。

    -   **ユーザーは、フォームやフィールドが候補として検出されない場合でも、オートフィル候補を検索できます。** 現在、Microsoft Edge に情報を保存している場合、オートフィル候補が自動的にポップアップ表示され、フォームに入力する時間を節約できます。 オートフィルでフォームが見つからない場合や、通常オートフィルを設定しないフォーム (一時的なフォームなど) のデータを取得する場合は、オートフィルを使用して情報を検索することができます。

-   **Access はメニュー バーのフライアウトからダウンロードしています。** ダウンロードは右上隅に表示され、アクティブなすべてのダウンロードが 1 か所に表示されます。 このメニューは簡単に閉じることができるので、ユーザーは作業を中断することなく、閲覧を続けることができます。また、ダウンロードの全体的な進行状況をツールバーからすぐに監視できます。 [詳しくはこちらをご覧ください](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551)。

-   **フォント レンダリングパフォーマンスの改善。** Microsoft Edge バージョン 90 より、テキストのレンダリング機能が改善され、テキストの明瞭度が向上し、ぼやけた感じが軽減されました。 フォント レンダリングの改善の一部はベータ バージョン 90 にて適用されますが、既定では無効になっています。

- **キッズ モード。** ポリシーを更新して、ポリシーを有効にすると、家族の安全に加えて、キッズ モード機能が無効になります。 キッズ モードの詳細については、[こちら](https://go.microsoft.com/fwlink/?linkid=2146910)を参照してください

## <a name="policy-updates"></a>ポリシーの更新

## <a name="new-policies"></a>新しいポリシー

8 つの新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://www.microsoft.com/edge/business/download)からダウンロードしてください。 次の新しいポリシーが追加されました。
-   [ApplicationGuardFaitesSyncEnabled](/DeployEdge/microsoft-edge-policies#applicationguardfavoritessyncenabled) - Application Guard のお気に入りの同期の有効化
- [ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) Application Guard トラフィック ID
- [ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) 明示的に許可されたネットワーク ポート
- [ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) スタートアップ ページ設定のインポートを許可する
- [MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) ユーザーが数学の問題を切り取って、Microsoft Edge の段階的な説明で解決策を得ることができる
- [NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) 新しいタブ ページで Microsoft ニュース コンテンツを許可する
- [NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) 新しいタブ ページでクイック リンクを許可する
-   [FetchKeepaliveDurationSecondsOnShutdown](/DeployEdge/microsoft-edge-policies#fetchkeepalivedurationsecondsonshutdown) - シャットダウン時にキープアライブ期間をフェッチする
-   [ManagedConfigurationPerOrigin](/DeployEdge/microsoft-edge-policies#managedconfigurationperorigin) - Web サイトの管理された構成値を特定のオリジンに設定する
-   [PrintRasterizationMode](/DeployEdge/microsoft-edge-policies#printrasterizationmode) - 印刷ラスタライズ モード
-   [QuickViewOfficeFilesEnabled](/DeployEdge/microsoft-edge-policies#quickviewofficefilesenabled) - Microsoft Edge で QuickView Office ファイル機能を管理する
-   [SSLErrorOvererrorallowedForOrigins](/DeployEdge/microsoft-edge-policies#sslerroroverrideallowedfororigins) - 特定の生成元の HTTPS 警告ページからユーザーが進むのを許可する
-   [WindowOcclusionEnabled](/DeployEdge/microsoft-edge-policies#windowocclusionenabled) - Window Occlusion を有効にする
-   [WindowsHelloForHTTPAuthEnabled](/DeployEdge/microsoft-edge-policies#windowshelloforhttpauthenabled) - HTTP 認証用 Windows Hello を有効にする

## <a name="deprecated-policies"></a>廃止されたポリシー

- [ProactiveAuthEnabled](/DeployEdge/microsoft-edge-policies#proactiveauthenabled) プロアクティブ認証を有効にする
-   [NativeWindowOcclusionEnabled](/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled) - ネイティブ ウィンドウ オクルージョンを有効にする
-   [SSLVersionMin](/DeployEdge/microsoft-edge-policies#sslversionmin) - 最小限の TLS バージョンを有効にする

## <a name="version-89077477-april-14"></a>バージョン 89.0.774.77: 4 月 14 日

> [!Important]
>この更新プログラムには、[CVE-2021-21206](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21206) と [CVE-2021-21220](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21220) が含まれています。これについては、Chromium チームにより実際に感染報告がある悪用が報告されています。  詳細については、「[セキュリティ更新プログラム ガイド](https://msrc.microsoft.com/update-guide)」を参照してください。

安定したチャネルのセキュリティ更新プログラムは[こちら](/deployedge/microsoft-edge-relnotes-security#april-14-2021)に記載されています。

## <a name="version-89077476-april-12"></a>バージョン 89.0.774.76: 4 月 12 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-89077475-april-8"></a>バージョン 89.0.774.75: 4 月 8 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-89077468-april-1"></a>バージョン 89.0.774.68: 4 月 1 日

安定したチャネルのセキュリティ更新プログラムは[こちら](./microsoft-edge-relnotes-security.md#april-1-2021)に記載されています。

## <a name="version-89077463-march-25"></a>バージョン 89.0.774.63: 3 月 25 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-89077457-march-18"></a>バージョン 89.0.774.57: 3 月 18 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-89077454-march-13"></a>バージョン 89.0.774.54: 3 月 13 日

> [!IMPORTANT]
> この更新プログラムには [CVE-2021-21193](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21193) が含まれているが、これはクロム チームによって悪用されたと報告されています。 詳細については、「[セキュリティ更新プログラム ガイド](https://msrc.microsoft.com/update-guide)」を参照してください。

安定したチャネル セキュリティ更新プログラムの一覧は[こちら](./microsoft-edge-relnotes-security.md#march-13-2021)にです。

## <a name="version-89077450-march-10"></a>バージョン 89.0.774.50: 3 月 10 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-89077448-march-8"></a>バージョン 89.0.774.48: 3 月 8 日

さまざまなバグとパフォーマンスの問題を修正しました。

<!-- begin major 89 -->
## <a name="version-89077445-march-4"></a>バージョン 89.0.774.45: 3 月 4 日

> [!IMPORTANT]
> この更新プログラムには、[CVE-2021-21166](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21166) が含まれています。これについては、Chromium チームにより実際に感染報告がある悪用が報告されています。 詳細については、「[セキュリティ更新プログラム ガイド](https://msrc.microsoft.com/update-guide)」を参照してください。

安定したチャネル セキュリティ更新プログラムの一覧は[こちら](./microsoft-edge-relnotes-security.md#march-4-2021)にです。

### <a name="resolved-issues"></a>解決した問題

- **タスク バーとスタート メニューのショートカットの更新と修正:**
  - [スタート] メニューで Microsoft Edge ショートカットを右クリックすると、Microsoft Edge がピン留めされているときに、タスク バーから Microsoft Edge のピン留めを解除するオプションが正しく表示されるようになりました。
  - Microsoft Edge をタスクバーにピン留めするための[タスクバーの設定](/windows/configuration/configure-windows-10-taskbar)を含むスタート レイアウトでは、2 つ目の Microsoft Edge ショートカットがタスクバーにピン留めされなくなりました。 
  - Windows ローミング プロファイルを使用している組織では、ユーザーが Windows にログオンしたときに、タスク バーの Microsoft Edge アイコンの代わりに空白の白いアイコンが表示されなくなります。

### <a name="feature-updates"></a>機能更新プログラム

- **キオスク モードでは、追加のロックダウン機能が有効になります**。 Microsoft Edge バージョン 89 から、キオスク モード内にロックダウン機能が追加され、お客様は生産性が高く、より安全なエクスペリエンスでジョブを実行できます。 [詳細はこちらをご覧ください](microsoft-edge-configure-kiosk-mode.md#kiosk-mode-supported-features)。

- **Enterprise Mode Site List Manager ツールは、*edge://compat* ページを経由したブラウザーで使用可能です**。 このツールを使用して、Microsoft Edge で Internet Explorer モード向けのサイト一覧 XML を作成、編集、およびエクスポートできます。 必要に応じて、グループ ポリシーを経由してこのツールへのアクセスを有効にできます。 [詳細はこちらをご覧ください](./edge-ie-mode-site-list-manager.md)。

- **タブをスリープ状態にし、ブラウザーのパフォーマンスを向上させます**。 タブをスリープすると、アクティブでないタブをスリープ状態にすることでブラウザーのパフォーマンスが向上し、メモリや CPU などのシステム リソースが解放され、アクティブなタブや他のアプリケーションで使用できます。 ユーザーは、サイトがスリープ状態になるのを防ぎ、非アクティブなタブがスリープ状態になる前の時間の長さを構成できます。 ユーザーのフローを維持するために、イントラネット サイトなど、特定のサイトがスリープ状態になるのを防ぐための[ヒューリスティック](https://techcommunity.microsoft.com/t5/articles/sleeping-tabs-faq/m-p/1705434)も用意されています。 この機能は、グループ ポリシーを使用して管理できます。

- **クラウド内の Microsoft Edge 同期データを手動でリセットします**。 Microsoft Edge の同期データを製品内からリセットする方法を導入しています。 これにより、お使いのデータは、Microsoft サービスからクリアされます。また、以前ならサポートチケットを必要としていたような特定の製品の問題を解決することもできます。

- **すべての WindowsAzure Active Directory (Azure AD) アカウントに対するシングル サインオン (SSO) のインテリジェントな有効化は、単一の非 Azure AD Microsoft Edge プロファイルを持つユーザーを対象としています**。  この機能で最も便利になる可能性のあるユーザーに対して、この設定を自動的にオンにします。 ユーザーが Microsoft Edge プロファイルを 1 つしか持っていない場合 (Azure AD またはキッズ モードではない場合)、Microsoft Edge の起動時に設定が自動的にオンになります。 この自動切り替えは、ユーザーが後で Azure AD アカウントを使用して別の Microsoft Edge プロファイルにサインインすることを選択した場合にも自動的にオフになります。 ユーザーは、**[設定]、[プロファイル]、[プロファイルの設定]、[このプロファイルを使用して職場または学校のサイトへのシングル サインオンを許可する]** の順に移動し、この機能の設定を手動で更新できます。

- **PDF ドキュメント内でのテキストの選択エクスペリエンスが向上しました**。 ユーザーは、Microsoft Edge バージョン 89 以降で開いた PDF ドキュメント全体で、よりスムーズでより一貫性の高いテキスト選択エクスペリエンスを実現できるようになります。

- **オートフィルでサポートされる生年月日フィールド**。 現在、Microsoft Edge は、住所、名前、電話番号などのデータを自動入力することで、フォームに入力し、オンラインでアカウントを作成する場合に時間と労力を節約するのに役立ちます。Microsoft Edge バージョン 89 以降で、保存して自動入力できる別のフィールド (生年月日) のサポートが追加されています。 この情報は、プロファイル設定でいつでも表示、編集、削除できます。

### <a name="policy-updates"></a>ポリシーの更新

#### <a name="new-policies"></a>新しいポリシー

7 個の新しいポリシーが追加されました。 更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://www.microsoft.com/edge/business/download)からダウンロードしてください。 次の新しいポリシーが追加されました。

- [BrowsingDataLifetime](./microsoft-edge-policies.md#browsingdatalifetime) - データの有効期間設定の参照
- [MAMEnabled](./microsoft-edge-policies.md#mamenabled) - モバイル アプリ管理の有効化
- [DefinePreferredLanguages](./microsoft-edge-policies.md#definepreferredlanguages) - サイトが言語をサポートしている場合に Web サイトが表示する優先言語の順序付きリストを定義する
- [ShowRecommendationsEnabled](./microsoft-edge-policies.md#showrecommendationsenabled) - Edge からの推奨事項とプロモーション通知を許可する
- [PrintingAllowedBackgroundGraphicsModes](./microsoft-edge-policies.md#printingallowedbackgroundgraphicsmodes) - バックグラウンド グラフィックス印刷モードを制限する
- [PrintingBackgroundGraphicsDefault](./microsoft-edge-policies.md#printingbackgroundgraphicsdefault) - 既定の背景グラフィックス印刷モード
- [SmartActionsBlockList](./microsoft-edge-policies.md#smartactionsblocklist) - サービスの一覧に対するスマート アクションをブロックする

#### <a name="obsoleted-policies"></a>非推奨ポリシー

次のポリシーは廃止されました。

- [ForceLegacyDefaultReferrerPolicy](./microsoft-edge-policies.md#forcelegacydefaultreferrerpolicy) - no-referrer-when-downgrade の既定の参照元ポリシーを使用します
- [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) - 使用状況とクラッシュ関連のデータ レポートを有効にします
- [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) - Microsoft サービスを向上させるためにサイト情報を送信する
<!-- end major 89 -->

<!-- Archive from 86.0.622.43: October 15 to beta 88.0.705.81: February 25  ->
<!-- Archive from 86.0.622.38-october-9 to beta 86.0.62.215-september-14  ->
<!-- Archived to version 84.0.522.40: July 16 -->

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
