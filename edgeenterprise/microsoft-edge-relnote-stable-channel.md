---
title: Stable チャネルに関する Microsoft Edge リリース ノート
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 03/25/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Stable チャネルに関する Microsoft Edge リリース ノート
ms.openlocfilehash: 36f6e5fe462fcb4c43862754603bef7902fcf670
ms.sourcegitcommit: 93851b83dc11422924646a04a9e0f60ff2554af7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470275"
---
# <a name="release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge Stable チャネルのリリース ノート

これらのリリース ノートでは、Microsoft Edge Stable チャネルに含まれている新機能とセキュリティ以外の更新プログラムに関する情報を提供します。

- すべてのセキュリティの更新プログラムは、[ここ](microsoft-edge-relnotes-security.md)に記載されています。
- Microsoft Edge 安定チャネルのアーカイブされたリリース ノートは、[こちら](microsoft-edge-relnote-archive-stable-channel.md)にあります。

 Microsoft Edge チャネルを理解するには、「[Microsoft Edge チャネルの概要](microsoft-edge-channels.md)」を参照してください。

> [!NOTE]
> 安定チャネルの場合、更新は 1 日以上かけて段階的に公開されます。 詳細については、「[Microsoft Edge 更新プログラムの段階的なロールアウト](microsoft-edge-update-progressive-rollout.md)」を参照してください。

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

- **起動ブーストを使用して Microsoft Edge の起動速度を向上します**。 Microsoft Edge の起動速度を向上させるために、スタートアップ ブーストという名前の機能を開発しました。 起動ブーストにより、Microsoft Edge をバックグラウンドで実行することで、Microsoft Edge の起動速度が向上します。 注: この機能は、実験を有効にしたユーザーのランダムに選択されたグループに限定されます。 これらのユーザーは、機能チームにフィードバックを提供しています。

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

<!-- Archive from 86.0.622.38-october-9 to beta 86.0.62.215-september-14  ->
<!-- Archived to version 84.0.522.40: July 16 -->

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)