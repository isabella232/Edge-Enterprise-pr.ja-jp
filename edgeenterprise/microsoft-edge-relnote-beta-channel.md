---
title: Beta チャネルに関する Microsoft Edge のリリース ノート
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 03/22/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Beta チャネルに関する Microsoft Edge のリリース ノート
ms.openlocfilehash: 9d9bec56a3629f18f7a9f64553858558a2864100
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447571"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge Beta チャネルのリリースノート

これらのリリース ノートでは、Microsoft Edge Beta チャネルに含まれている新機能とセキュリティ以外の更新プログラムに関する情報を提供します。 これらのリリース ノートのアーカイブ バージョンは、[こちら](microsoft-edge-relnote-archive-beta-channel.md)から入手できます。

> [!NOTE]
> Microsoft Edge Beta [バージョン 89.0.774.18: 2 月 3 日](#version-89077418-february-3)のリリース ノートを更新して、リリースされた機能を反映させました。

## <a name="version-90081814-march-22"></a>バージョン 90.0.818.14: 3 月 22 日

さまざまなバグとパフォーマンスの問題を修正しました。
<!-- begin major 90 -->
## <a name="version-9008188-march-16"></a>バージョン 90.0.818.8: 3 月 16 日

### <a name="feature-updates"></a>機能更新プログラム

- **シングル サインオン (SSO) は、Mac OS の Azure Active Directory (Azure AD) アカウントと Microsoft アカウント (MSA) で利用できます**。 macOS で Microsoft Edge にサインインしたユーザーは、Work アカウントと Microsoft アカウント (bing.com、office.com、msn.com、outlook.com など) でシングル サインオンを許可するように構成された Web サイトに自動的にサインインします。

- **印刷**

  - **PostScript プリンターではないプリンター向けの新しい印刷ラスタライズ モード**。 Microsoft Edge バージョン 90 より、管理者は新しいポリシーを使用して、ユーザーの印刷ラスタライズ モードを定義できます。 このポリシーは、Windows の PostScript プリンターではないプリンターから Microsoft Edge で印刷する方法を制御します。  PostScript プリンターではないプリンターの印刷ジョブが正しく印刷されるようにラスター化する必要がある場合があります。 印刷オプションには「フル」と 「高速」が表示されます。

  - **追加された、印刷用のページ拡大/縮小オプション**。 ユーザーは、追加のオプションを使用して Web ページや PDF ドキュメントを印刷しながらスケーリングをカスタマイズできるようにりました。 [ページサイズに合わせて印刷] オプションを使用すると、印刷用に選択した "用紙サイズ" に Web ページまたはドキュメントを収めることがきます。 「実際のサイズ」オプションを選択すと、選択した「用紙サイズ」に関係なく、印刷されるコンテンツのサイズに変更が加えられないようにします。

- **生産性:**

  - **オートフィル候補が拡張され、クリップボードのアドレス フィールドのコンテンツが含まれるようになりました**。 クリップボードの内容は、オートフィル候補として表示するプロフィール フィールドまたはアドレス フィールド (電話番号、メールアドレス、郵便番号、市区町間、州など) をクリックすると解析されます。

  - **ユーザーは、フォームやフィールドが候補として検出されない場合でも、オートフィル候補を検索できます**。 現在、Microsoft Edge に情報を保存している場合、オートフィル候補が自動的にポップアップ表示され、フォームに入力する時間を節約できます。 オートフィルでフォームが見つからない場合や、通常オートフィルを設定しないフォーム (一時的なフォームなど) のデータを取得する場合は、オートフィルを使用して情報を検索することができます。

- **Access はメニュー バーのフライアウトからダウンロードしています**。 ダウンロードは右上隅に表示され、アクティブなすべてのダウンロードが 1 か所に表示されます。 このメニューは簡単に閉じることができるので、ユーザーは作業を中断することなく、閲覧を続けることができます。また、ダウンロードの全体的な進行状況をツールバーからすぐに監視できます。 [詳しくはこちらをご覧ください](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551)。

- **フォント レンダリングパフォーマンスの改善**。 Microsoft Edge バージョン 90 より、テキストのレンダリング機能が改善され、テキストの明瞭度が向上し、ぼやけた感じが軽減されました。 フォント レンダリングの改善の一部はベータ バージョン 90 にて適用されますが、既定では無効になっています。


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

<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)