---
title: Microsoft Edge Stable チャネルのアーカイブされたリリース ノート
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Stable チャネルのアーカイブされたリリース ノート
ms.openlocfilehash: 53fe8fa4eae90f6d101cbf1394a276bc37f82b5a
ms.sourcegitcommit: 85818deae134b48d7f2766e53b4400a1b4d4277d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "12034456"
---
# <a name="archived-release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge Stable チャネルのアーカイブされたリリース ノート

これらのリリース ノートでは、Microsoft Edge Stable チャネルに含まれている新機能とセキュリティ以外の更新プログラムに関する情報を提供します。 すべてのセキュリティの更新プログラムは、[ここ](microsoft-edge-relnotes-security.md)に記載されています。


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
>この更新プログラムには[CVE-2021-21224](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21224)の修正プログラムが含まれているが、これは Chromium チームによって悪用されたと報告されている。 詳細については、「[セキュリティ更新プログラム ガイド](https://msrc.microsoft.com/update-guide)」を参照してください。

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
>この更新プログラムには[、cve-2021-21206](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21206)および[CVE-2021-21220](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21220)の修正プログラムが含まれている。これは、Chromium チームがワイルドで悪用を行ったと報告されています。  詳細については、「[セキュリティ更新プログラム ガイド](https://msrc.microsoft.com/update-guide)」を参照してください。

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

## <a name="version"></a>バージョン

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

## <a name="version-88070581-february-25"></a>バージョン 88.0.705.81: 2 月 25 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-88070574-february-17"></a>バージョン 88.0.705.74: 2 月 17 日

安定したチャネル セキュリティ更新プログラムの一覧は[こちら](./microsoft-edge-relnotes-security.md#february-17-2021)にです。

## <a name="version-88070568-february-11"></a>バージョン 88.0.705.68: 2 月 11 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-88070563-february-5"></a>バージョン 88.0.705.63: 2 月 5 日

> [!IMPORTANT]
> この更新プログラムには、[CVE-2021-21148](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21148) が含まれています。これについては、Chromium チームにより実際に感染報告がある悪用が報告されています。

安定したチャネル セキュリティ更新プログラムの一覧は[こちら](./microsoft-edge-relnotes-security.md#february-5-2021)にです。

## <a name="version-88070562-february-4"></a>バージョン 88.0.705.62: 2 月 4 日

安定したチャネル セキュリティ更新プログラムの一覧は[こちら](./microsoft-edge-relnotes-security.md#february-4-2021)にです。

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-88070556-january-28"></a>バージョン 88.0.705.56: 1 月 28 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-88070553-january-26"></a>バージョン 88.0.705.53: 1 月 26 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-88070550-january-21"></a>バージョン 88.0.705.50: 1 月 21 日

安定したチャネル セキュリティ更新プログラムの一覧は[こちら](./microsoft-edge-relnotes-security.md#january-21-2021)にです。

<!--- begin major 88  --->
### <a name="feature-updates"></a>機能更新プログラム

- **非推奨:**

  - FTP プロトコルのサポートを廃止します。 従来の FTP プロトコルのサポートは Microsoft Edge から削除されました。 FTP リンクに移動しようとすると、ブラウザーは、FTP リンクを処理する外部アプリケーションを開く操作をオペレーティング システムに指示します。 または、IT 管理者は、FTP プロトコルに依存するサイトで IE モードを使用する Microsoft Edge を構成できます。
  - Adobe Flash のサポートは削除されます。 Microsoft Edge Beta バージョン 88 から、Adobe Flash の機能とサポートは削除されます。 詳細: [Adobe Flash Player のサポート終了に関する更新プログラム - Microsoft Edge ブログ (windows.com)](https://blogs.windows.com/msedgedev/2020/09/04/update-adobe-flash-end-support/)

- **認証:**

  - シングル サインオン (SSO) は、ダウンレベル Windows の Azure Active Directory (Azure AD) アカウントと Microsoft アカウント (MSA) で利用できます。 ダウンレベルの Microsoft Windows (7、8.1) で Microsoft Edge にサインインしたユーザーは、Work アカウントと Microsoft アカウント (bing.com、office.com、msn.com、outlook.com など) でシングル サインオンを許可するように構成された Web サイトに自動的にサインインします。<br>注: この機能を利用するには、ユーザーが Microsoft Edge 88 より前のバージョンで Microsoft Edge にサインインした場合、サインアウトしてからサインインしなおす必要がある場合があります。
  
  - シングル サインオン (SSO) は、Azure AD 以外の Microsoft Edge プロファイルのシステム上で任意の Windows Azure Active Directory (Azure AD) アカウントを使用することによってサイトで使用できます。 この機能は、職場または学校アカウントでサインインしていない、ゲストやプライベートではないプロファイルに対して有効にできます。また、そのプロファイルのオペレーティング システムでサインインしている任意の職場または学校アカウントを使用できます。 この機能は、**[設定]** > **[プロファイル]** > **[プロファイルの基本設定]** > **[このプロファイルを使用して、職場または学校のサイトにシングル サインオンを許可する]** で構成できます。
  
    > [!NOTE]
    > 「Microsoft Edge プロファイルを使用しているすべての Windows アカウントのシングル サインオン (SSO)」は、1 月 21 日のリリース ノートの更新です。

- **セッションを終了するキオスク モード オプション**。 [セッションの終了] ボタンは、キオスク モードのパブリック ブラウズ エクスペリエンスで利用できます。 この機能により、Microsoft Edge を閉じたときにブラウザーのデータと設定が削除されます。 キオスク モード機能とロードマップの詳細については 、「[Microsoft Edge キオスク モードを構成する](./microsoft-edge-configure-kiosk-mode.md)」を参照してください。

- **セキュリティとプライバシー:**

  - ユーザーのパスワードのオンラインでの漏洩が見つかると、警告が生成されます。 ユーザーのパスワードは、侵害された資格情報のリポジトリと照合され、一致するものが見つかるとユーザーに警告を通知します。 セキュリティとプライバシーを確保するために、ユーザーのパスワードは漏洩した資格情報のデータベースと照合するときにハッシュ化され、暗号化されます。
  - 混在コンテンツを自動的にアップグレードします。 HTTPS 経由で配信されるセキュリティで保護されたページには、セキュリティ保護されていない HTTP 経由で提供される参照イメージが含まれる場合があります。 Microsoft Edge 88 のプライバシーとセキュリティを向上させるために、これらの画像は HTTPS 経由で取得されます。 HTTPS 経由で画像を利用できない場合、画像は読み込まれません。
  - サイトの権限をサイト別および最近のアクティビティ別に表示します。 Microsoft Edge 88 から、ユーザーはサイトのアクセス許可を簡単に管理できます。 アクセス許可の種類ではなく、Web サイト別にアクセス許可を表示できます。 さらに、サイトのアクセス許可に対する最近の変更すべてがユーザーに表示される最近のアクティビティ セクションが追加されました。
  - ブラウザーの Cookie の制御が向上しました。 Microsoft Edge 88 から、ユーザーはファースト パーティの Cookie に影響を及ぼさずにサード パーティの Cookie を削除できます。 また、ユーザーは、ファースト パーティまたはサード パーティによって Cookie をフィルター処理し、名前、Cookie の数、および保存および最終変更されたデータの量で並べ替えすることもできます。

- **パスワード:**

  - パスワード ジェネレーター。 Microsoft Edge には、新しいアカウントにサインアップするとき、または既存のパスワードを変更するときに使用できる強力なパスワード ジェネレーターが組み込まれています。 パスワード フィールドでブラウザーが推奨するパスワードのドロップダウンを探すだけで、選択すると自動的にブラウザーに保存され、後で簡単に使用できるようにデバイス間で同期されます。
  - パスワード モニター。 ブラウザーに保存されたパスワードのいずれかが、漏洩された一覧のリストに表示されているパスワードと一致すると、Microsoft Edge から通知され、パスワードを更新するように求められます。 パスワード モニターは、ユーザーに代わって一致をスキャンし、既定でオンになっています。
  - パスワードの編集。 Microsoft Edge の設定で、保存したパスワードを直接編集できます。 Microsoft Edge の外部でパスワードが更新された場合はいつでも、[設定] で保存されたエントリを編集することで、保存された古いパスワードを新しいパスワードに簡単に置き換えることができます。 

- **スタートアップ ブーストを使用して Microsoft Edge の起動速度を向上します**。 Microsoft Edge の起動速度を向上させるために、スタートアップ ブーストという名前の機能を開発しました。 スタートアップ ブーストにより、Microsoft Edge をバックグラウンドで実行することで、Microsoft Edge の起動速度が向上します。 注: この機能は、実験を有効にしたユーザーのランダムに選択されたグループに限定されます。 これらのユーザーは、機能チームにフィードバックを提供しています。

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

- [BasicAuthOverHttpEnabled](./microsoft-edge-policies.md#basicauthoverhttpenabled) - HTTP の基本認証を許可します。
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
- [TargetBlankImpliesNoOpener](./microsoft-edge-policies.md#targetblankimpliesnoopener) - _blank を対象とするリンクに window.opener を設定しません。
- [UpdatePolicyOverride](./microsoft-edge-policies.md#updatepolicyoverride) - Microsoft Edge で利用できる更新プログラムを Microsoft Edge Update でどのように処理するかを指定します。
- [VerticalTabsAllowed](./microsoft-edge-policies.md#verticaltabsallowed) - ブラウザーの横にあるタブの垂直方向のレイアウトの可用性を構成します。
- [WebRtcAllowLegacyTLSProtocols](./microsoft-edge-policies.md#webrtcallowlegacytlsprotocols) - WebRTC で従来の TLS/DTLS ダウングレードを許可します。
- [WebWidgetAllowed](./microsoft-edge-policies.md#webwidgetallowed) - Web ウィジェットを有効にします。
- [WebWidgetIsEnabledOnStartup](./microsoft-edge-policies.md#webwidgetisenabledonstartup) - Windows 起動時に Web ウィジェットを許可します。

#### <a name="deprecated-policies"></a>廃止されたポリシー

- [ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - プロアクティブ認証を有効にします。
- [ProxyBypassList](./microsoft-edge-policies.md#proxybypasslist) - プロキシ バイパス ルールを構成します。
- [ProxyMode](./microsoft-edge-policies.md#proxymode) - プロキシ サーバー設定を構成します。
- [ProxyPacUrl](./microsoft-edge-policies.md#proxypacurl) - プロキシの .pac ファイルの URL を設定します。
- [ProxyServer](./microsoft-edge-policies.md#proxyserver) - プロキシ サーバーのアドレスまたは URL を構成します。
- [WebDriverOverridesIncompatiblePolicies](./microsoft-edge-policies.md#webdriveroverridesincompatiblepolicies) - WebDriver が互換性のないポリシーを上書きすることを許可します。

### <a name="obsoleted-policies"></a>非推奨ポリシー

- [AllowPopupsDuringPageUnload](./microsoft-edge-policies.md#allowpopupsduringpageunload) - ページのアンロード中にポップアップを表示できます。
- [DefaultPluginsSetting](./microsoft-edge-policies.md#defaultpluginssetting) - 既定の Adobe Flash 設定です。
- [PluginsAllowedForUrls](./microsoft-edge-policies.md#pluginsallowedforurls) - 特定のサイトで Adobe Flash プラグインを許可します。
- [PluginsBlockedForUrls](./microsoft-edge-policies.md#pluginsblockedforurls) - 特定のサイトで Adobe Flash プラグインをブロックします。
- [RunAllFlashInAllowMode](./microsoft-edge-policies.md#runallflashinallowmode) - Adobe Flash コンテンツ設定をすべてのコンテンツに拡張します。
<!--- end major 88  --->
## <a name="version-87066475-january-7"></a>バージョン 87.0.664.75: 1 月 7 日

安定したチャネル セキュリティ更新プログラムの一覧は[こちら](./microsoft-edge-relnotes-security.md#january-7-2021)にです。

## <a name="version-87066466-december-17"></a>バージョン 87.0.664.66: 12 月 17 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-87066460-december-10"></a>バージョン 87.0.664.60: 12 月 10 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-87066457-december-7"></a>バージョン 87.0.664.57: 12 月 7 日

さまざまなバグとパフォーマンスの問題を修正しました。 安定したチャネル セキュリティ更新プログラムの一覧は[こちら](./microsoft-edge-relnotes-security.md#december-7-2020)にです。

## <a name="version-87066455-december-3"></a>バージョン 87.0.664.55: 12 月 3 日

さまざまなバグとパフォーマンスの問題を修正しました。 このリリースでは、次の機能が更新されました。

- **ショッピングは既定で有効になっています**。 Microsoft Edge バージョン 87 から、エンタープライズ ユーザーは Microsoft Edge でのショッピングを利用できます。 ショッピング機能を備えた Microsoft Edge は、オンラインでショッピングしながらクーポンやお得な価格を見つけるのに役立ちます。 (クーポンの機能は、Stable バージョン 87.0.664.41 とともにリリースされました。) この更新プログラムで、価格比較エクスペリエンスを利用できるようになりました。 この機能は、[EdgeShoppingAssistantEnabled](./microsoft-edge-policies.md#edgeshoppingassistantenabled) ポリシーを使って構成できます。 Microsoft ショッピングについては、[ブログ](https://blogs.windows.com/windowsexperience/2020/11/19/finish-up-that-holiday-shopping-with-new-features-from-microsoft-edge-and-bing/)および[詳細情報](/microsoft-edge/privacy-whitepaper#shopping)をご覧ください。

## <a name="version-87066452-november-30"></a>バージョン 87.0.664.52: 11 月 30 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-87066447-november-23"></a>バージョン 87.0.664.47: 11 月 23 日

さまざまなバグとパフォーマンスの問題を修正しました。

<!-- begin major 87 --->
## <a name="version-87066441-november-19"></a>バージョン 87.0.664.41: 11 月 19 日

安定したチャネル セキュリティ更新プログラムの一覧は[こちら](./microsoft-edge-relnotes-security.md#november-19-2020)にです。

### <a name="feature-updates"></a>機能更新プログラム

- **互換性のないサイトを Internet Explorer から Microsoft Edgeにリダイレクトします**。 Microsoft Edge 87 Stable の更新以降、Internet Explorer で互換性のないメッセージを表示する公開 Web サイトは自動的に Microsoft Edge にリダイレクトされます。 詳細とこのエクスペリエンスの構成については、「[互換性のないサイトのリダイレクト](./edge-learnmore-neededge.md)」を参照してください。

- **キオスク モードのプライバシー機能を有効にします**。 Microsoft Edge バージョン 87 以降では、ユーザー データのプライバシーに関して企業に役立つキオスク モードの機能が有効になります。 これらの機能により、終了時にユーザーデータをクリアしたり、ダウンロードしたファイルを削除したり、一定のアイドル時間が経過した後に、構成されていたスタート操作をリセットしたりできます。 [Microsoft Edge キオスク モードを構成する方法](./microsoft-edge-configure-kiosk-mode.md)の詳細情報

- **既定で有効になっているショッピング機能**。 Microsoft Edge バージョン 87 以降では、エンタープライズ ユーザーは、Edge でのショッピングを利用することもできます。 ショッピング機能を備えた Microsoft Edge は、オンラインでショッピングしながらクーポンやお得な価格を見つけるのに役立ちます。 この更新プログラムではクーポン エクスペリエンスが利用可能であり、価格比較は Microsoft Edge 87 の今後の更新プログラムでリリースされます。 この機能は、[EdgeShoppingAssistantEnabled](./microsoft-edge-policies.md#edgeshoppingassistantenabled) ポリシーを使用して構成できます。 Microsoft ショッピングについては、[ブログ](https://blogs.windows.com/windowsexperience/2020/11/19/finish-up-that-holiday-shopping-with-new-features-from-microsoft-edge-and-bing/)および[詳細情報](/microsoft-edge/privacy-whitepaper#shopping)をご覧ください。

- **ClickOnce の展開が既定で有効になっています**。 Microsoft Edge 87 では、ClickOnce が既定で有効になっています。これにより、企業がソフトウェアを展開する際の障壁を減らし、Microsoft Edge のレガシブラウザーの動作に合わせることができます。 Microsoft Edge 87 以降、ClickOnceEnabled policyが"未構成"の 状態の場合は、新しい既定の「有効化が ClickOnceの状態」（以前の規定が無効だった状態と異なり）に反映されます。

- **エンタープライズ新しいタブページ (NTP)は、カスタマイズ可能な仕事関連のフィードコンテンツと生産性を結びつけます**。 エンタープライズ NTP は、職場または学校アカウントでサインインしているユーザーに対して提供される Office 365 生産性向上ページだけでなく、カスタマイズされた、仕事関連の企業や業界のコンテンツを1ページにまとめて提供いたします。 ユーザーは、使い慣れた Office 365 のコンテンツと、Bing で提供されている一般法人向け Microsoft Search を目にすることでしょう。 さらに、組織で利用可能なコンテンツとモジュールから最も関連性の高いコンテンツを選択することで、「マイ フィード」を簡単にカスタマイズできます。 IT 管​​理者は、Microsoft 365 管理センターにアクセスして、Microsoft Edge の新しいタブ ページで選択した業界を含む、組織のニュース フィード設定を制御できます。 [詳細情報](https://blogs.windows.com/msedgedev/2020/10/29/enterprise-new-tab-page-my-feed/)

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
- [EdgeShoppingAssistantEnabled](./microsoft-edge-policies.md#edgeshoppingassistantenabled) -Microsoft Edge でのショッピングが有効になります。
- [HideInternetExplorerRedirectUXForIncompatibleSitesEnabled](./microsoft-edge-policies.md#hideinternetexplorerredirectuxforincompatiblesitesenabled) -Microsoft Edge のワンタイム リダイレクト ダイアログとバナーを非表示にします。
- [KioskAddressBarEditingEnabled](./microsoft-edge-policies.md#kioskaddressbareditingenabled) -キオスクモードのパブリックブラウザーのエクスペリエンスを編集するアドレスバーを構成します。
- [KioskDeleteDownloadsOnExit](./microsoft-edge-policies.md#kioskdeletedownloadsonexit) -Microsoft Edge が終了したときに、キオスク セッションの一部としてダウンロードされたファイルを削除します。
- [PasswordRevealEnabled](./microsoft-edge-policies.md#passwordrevealenabled) -パスワード表示ボタンを有効にします。
- [RedirectSitesFromInternetExplorerPreventBHOInstall](./microsoft-edge-policies.md#redirectsitesfrominternetexplorerpreventbhoinstall) -Internet Explorer から Microsoft Edge に互換性のないサイトをリダイレクトするためにブラウザー ヘルパー オブジェクト (BHO) をインストールできないようにします。
- [RedirectSitesFromInternetExplorerRedirectMode](./microsoft-edge-policies.md#redirectsitesfrominternetexplorerredirectmode) -Internet Explorer から Microsoft Edge に互換性のないサイトをリダイレクトします。
- [SpeechRecognitionEnabled](./microsoft-edge-policies.md#speechrecognitionenabled) -音声認識を構成します。
- [WebCaptureEnabled](./microsoft-edge-policies.md#webcaptureenabled) -Microsoft Edge で Web キャプチャ機能を有効にします。

#### <a name="deprecated-policy"></a>廃止されたポリシー

[NewTabPageSetFeedType](./microsoft-edge-policies.md#newtabpagesetfeedtype) - Microsoft Edge の新規タブ ページのエクスペリエンスを設定する

#### <a name="obsoleted-policy"></a>非推奨ポリシー

[EnableDeprecatedWebPlatformFeatures](./microsoft-edge-policies.md#enabledeprecatedwebplatformfeatures) -廃止された Web プラットフォームの機能を一定期間、再度有効にします。

<!-- end major 87 -->

## <a name="version-86062269-november-13"></a>バージョン 86.0.622.69: 11 月 13 日

> [!IMPORTANT]
> この更新プログラムには、[CVE-2020-16013](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16013) と [CVE-2020-16017](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16017) が含まれています。これらについては、Chromium チームにより実際に感染報告がある悪用が報告されています。

安定したチャネル セキュリティ更新プログラムの一覧は[こちら](./microsoft-edge-relnotes-security.md#november-13-2020)にです。

## <a name="version-86062268-november-11"></a>バージョン 86.0.622.68: 11 月 11 日

安定したチャネル のセキュリティ更新プログラムの一覧は[こちら](./microsoft-edge-relnotes-security.md#november-11-2020)です

## <a name="version-86062263-november-4"></a>バージョン 86.0.622.63: 11 月 4 日

> [!IMPORTANT]
> この更新プログラムには、[CVE-2020-16009](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16009) が含まれています。これについては、Chromium チームにより実際に感染報告がある悪用が報告されています。

安定したチャネル セキュリティ更新プログラムの一覧は[こちら](./microsoft-edge-relnotes-security.md#november-4-2020)にです。

## <a name="version-86062261-november-2"></a>バージョン 86.0.622.61: 11 月 2 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-86062258-october-29"></a>バージョン 86.0.622.58: 10 月 29 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-86062256-october-27"></a>バージョン 86.0.622.56: 10 月 27 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-86062251-october-22"></a>バージョン 86.0.622.51: 10 月 22 日

安定したチャネル のセキュリティ更新プログラムの一覧は[こちら](./microsoft-edge-relnotes-security.md#october-22-2020)です

## <a name="version-86062248-october-20"></a>バージョン 86.0.622.48: 10 月 20 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-86062243-october-15"></a>バージョン 86.0.622.43 : 10 月 15 日

さまざまなバグとパフォーマンスの問題を修正しました。

## <a name="version-86062238-october-9"></a>バージョン 86.0.622.38 : 10 月 9 日

セキュリティの更新プログラムは、[ここ](./microsoft-edge-relnotes-security.md#october-9-2020)に記載されています

### <a name="feature-updates"></a>機能更新プログラム

* **Microsoft Edge の以前のバージョンにロールバック。** ロールバック機能では、Microsoft Edge の最新バージョンに問題がある場合、管理者は Microsoft Edge を既知の正常なバージョンに戻すことができます。 **注:** Stable バージョン 86.0.622.38 は、ロールバック先となることができる最初のバージョンです。これは、安定バージョン87が、ロールバック元となる準備ができた最初のバージョンという意味でもあります。 [詳しくはこちらをご覧ください](edge-learnmore-rollback.md)。

* **エンタープライズ全体で、同期の有効化を既定で強制できます。**  管理者は既定で、[ForceSync](./microsoft-edge-policies.md#forcesync) ポリシーを使用して、Azure Active Directory (Azure AD) アカウントに対して同期を有効にできます。

* **Windows 7および8.1 でのプロファイル の自動切り替え。** 現在 Windows 10 の Microsoft Edge で利用可能なプロフィールの自動切り替えは、ダウンレベルの Windows (Windows 7、8.1) に拡張されました。 詳細については、ブログ記事「[プロファイルの自動切り替え](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/)」を参照してください。

* **SameSite=既定で緩い Cookie**。 Web セキュリティとプライバシーを向上させるために、Cookie は、既定では、[SameSite=Lax](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite) 処理に設定されます。 つまり、Cookie はファーストパーティのコンテキストでのみ送信され、サードパーティに送信される要求では省略されます。 この変更により、サードパーティのリソースが正しく機能するために Cookie を必要とする Web サイトに互換性の影響が生じる可能性があります。 このような Cookie を許可するために、Web 開発者は、Cookie の設定時に明示的な `SameSite=none` および `Secure` 属性を追加することにより、サードパーティのコンテキストから設定および送信する必要がある Cookie にマークを付けることができます。 特定のサイトをこの変更から除外することを希望する企業は、[LegacySameSiteCookieBehaviorEnabledForDomainList](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabledfordomainlist) ポリシーを使用してこれを行うか、[LegacySameSiteCookieBehaviorEnabled](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabled) ポリシーを使用してすべてのサイトにわたる変更をオプトアウトできます。

* **HTML5 アプリケーション キャッシュ API の削除。**  Microsoft Edge バージョン 86 以降、Web ページのオフライン使用を可能にするレガシ アプリケーション キャッシュ API は Microsoft Edge から削除されます。 Web 開発者は、[WebDev ドキュメント](https://web.dev/appcache-removal/)で、アプリケーション キャッシュ API のサービス ワーカーへの置き換えに関する情報を確認する必要があります。  重要: Microsoft Edge バージョン 90 まで、サイトが非推奨のアプリケーション キャッシュ API を引き続き使用できるようにする [AppCache OriginTrial Token](https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673) を要求できます。

* **プライバシーとセキュリティ**

  * ダウンレベルの Windows と macOS で [MetricsReportingEnabled](/DeployEdge/microsoft-edge-policies#metricsreportingenabled) と [SendSiteInformationToImproveServices](/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) ポリシーを置き換えます。 これらのポリシーは Microsoft Edge バージョン 86 では非推奨で、Microsoft Edge バージョン 89 で廃止されます。<br>
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

- ユーザーは、特定のサイトの外部プロトコルを起動するという設定を保存できます。 ユーザーは、[ExternalProtocolDialogShowAlwaysOpenCheckbox](/DeployEdge/microsoft-edge-policies#externalprotocoldialogshowalwaysopencheckbox) ポリシーを構成して、この機能を有効または無効にすることができます。

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