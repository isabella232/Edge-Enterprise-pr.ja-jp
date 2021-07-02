---
title: Enterprise Site Discovery ステップ バイ ステップ ガイド
ms.author: collw
author: appcompatguy
manager: saudm
ms.date: 05/19/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Enterprise Site Discovery を使用して IE モードを準備する
ms.openlocfilehash: f6298b801cceeb96d9285f3597de2a6abe8ee36e
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617477"
---
# <a name="enterprise-site-discovery-step-by-step-guide"></a>Enterprise Site Discovery ステップ バイ ステップ ガイド

>[!Note]
> Internet Explorer 11 デスクトップ アプリケーションは廃止され、2022 年 6 月 15 日にサポートが終了します (スコープ内の一覧については、[FAQ を参照してください](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549))。 現在使用しているものと同じ IE11 アプリとサイトを、Internet Explorer モードの Microsoft Edge で開くことができます。 [こちらをご覧ください](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

この記事は、Microsoft Endpoint Configuration Manager で Enterprise Site Discovery を使用するためのステップ バイ ステップ ガイドです。

Enterprise Site Discovery は、Enterprise Mode Site List を構成するのに役立ちます。 Enterprise Site Discovery は次のことに役立ちます。

- 従来のドキュメント モードを使用しているサイトを検出する。 このようなサイトは、サイトが最新のブラウザーを検出して異なる HTML を提供する場合を除き、IE モードを使用することが必要になる可能性があります。
- ActiveX コントロールを使用しているサイトを検出する。 Microsoft Edge では、ActiveX コントロールをサポートしていません。 このようなサイトは、サイトが最新のブラウザーを検出して異なる HTML を提供する場合を除き、IE モードを使用することが必要になる可能性があります。

> [!NOTE]
> この記事は、Microsoft Edge version 77 (**Stable**、**Beta**、および **Dev** チャネル) 以降に適用されます。

## <a name="prerequisites"></a>前提条件

このガイドは、読者に Microsoft Endpoint Configuration Manager の使用経験があり、次のサービスとロールがインストールされていることを前提としています。

1. Microsoft Endpoint Configuration Manager
2. Microsoft SQL Reporting Services
3. (オプション) Configuration Manager Reporting Services ポイント ロールが構成されている

## <a name="download-enterprise-site-discovery-tools"></a>Enterprise Site Discovery ツールをダウンロードする

次のツールをダウンロードします。

- [Enterprise Site Discovery のセットアップと構成パッケージ](https://go.microsoft.com/fwlink/p/?LinkId=517719)
- [Microsoft Report Builder](https://www.microsoft.com/download/details.aspx?id=53613)

## <a name="enable-enterprise-site-discovery"></a>Enterprise Site Discovery を有効にする

Windows Management Instrumentation (WMI) に接続してサイト検出データを取得するには、まず、WMI クラス プロバイダーをデバイスに展開する必要があります。

**Enterprise Site Discovery のセットアップと構成パッケージ**から、確定版ソフトウェア ライブラリのファイル共有内のフォルダーにコンテンツを抽出します。 例: **\\\\DSL\\EnterpriseSiteDiscovery**。

次に、[ドキュメント](/configmgr/apps/deploy-use/packages-and-programs)の説明に従って Microsoft Endpoint Configuration Manager にパッケージを作成し、次のオプションを選択します。

- **[パッケージ]** ページで、**[名前]** を選択し、名前を **[Site Discovery を有効にする]** に指定します。
- **[パッケージ]** ページで、**[このパッケージはソース ファイルを含む]** を選択します。
- **[パッケージ]** ページで、ファイルの抽出先ソース フォルダー (例: **\\\\DSL\\EnterpriseSiteDiscovery**) を指定します。
- **[プログラムの種類]** ページで、**[標準プログラム]** を選択します。
- **[標準プログラム]** ページで、次のようにコマンド ラインを入力して、デバイスに Site Discovery を構成します。
  ```dos
  powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1
  ```
  > [!NOTE]
  > このスクリプトでは、`-ZoneAllowList` と `-SiteAllowList` のスイッチを使用することができます。 このステップ バイ ステップでは、グループ ポリシーを使用してこれらのオプションを構成します (後述)。
- **[標準プログラム]** ページで、**[非表示]** を実行するためのオプションを選択します。
- **[標準プログラム]** ページの **[プログラムの実行条件]** で、**[ユーザーがログインしているかどうか]** を選択します。

パッケージを作成したら、パッケージ名の **[Site Discovery を有効にする]** をダブルクリックして、そのプロパティを表示します。 **[実行後]** プロパティで、**[Configuration Manager がコンピューターを再起動する]** を選択します。 デバイスが再起動すると、WMI データの収集が開始されます。

> [!NOTE]
> [クライアント設定ドキュメント](/configmgr/core/clients/deploy/about-client-settings#computer-restart)の説明に従って、デバイスを再起動するまでの時間の長さを設定できます。

## <a name="configure-enterprise-site-discovery-via-group-policy"></a>グループ ポリシーを使用して Enterprise Site Discovery を構成する

Enterprise Site Discovery が有効になっていると、どんなデータを収集するかを設定できます。 [こちら](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery#what-data-is-collected)の説明に従って、地域の法律と規制要件をご検討ください。

1. グループ ポリシー エディターを開きます。
2. **[コンピューターの構成]** > **[管理用テンプレート]** > **[Windows コンポーネント]** > **[Internet Explorer]** をクリックします。 
3. **[サイト探索 WMI 出力を有効にする]** をダブルクリックします。
4. **[有効]** を選択します。
5. **[OK]** または **[適用]** をクリックして、このポリシー設定を保存します。

サイト データを収集するゾーンを制限できます。

1. **[サイト探索の出力をゾーンで制限する]** をダブルクリックします。
2. **[有効]** を選択します。
3. 次に関して、サイト検出を有効にするゾーンを示すビットマスクを入力します。
    1. 制限付きサイト ゾーン
    2. イントラネット ゾーン
    3. 信頼済みサイト ゾーン
    4. ローカル イントラネット ゾーン
    5. ローカル マシン ゾーン
    
    例 1: **00010** に指定すると、ローカル イントラネット ゾーンのデータのみが収集されます。

    例 2： **10111** に指定すると、インターネット ゾーンを除くすべてのゾーンのデータが収集されます。
4. **[OK]** または **[適用]** をクリックして、このポリシー設定を保存します。

サイト データを収集するドメインを制限できます。

1. **[サイト探索の出力をドメインで制限する]** をダブルクリックします。
2. **[有効]** を選択します。
3. データを収集するドメインを、1 行につき 1 ドメインとなるように入力します。
4. **[OK]** または **[適用]** をクリックして、このポリシー設定を保存します。

## <a name="collect-site-discovery-data-using-configuration-manager"></a>Configuration Manager を使用して Site Discovery のデータを収集する

デバイスでデータが生成されるようになったので、今度はこのデータを Configuration Manager で収集します。

1. Configuration Manager コンソールで、**[管理]** > **[クライアント設定]** > **[既定のクライアント設定]** の順に選択します。
2. **[ホーム]** タブの **[プロパティ]** グループで、**[プロパティ]** を選択します。
3. **[既定のクライアント設定]** ダイアログ ボックスで、**[ハードウェア インベントリ]** を選択します。
4. **[デバイス設定]** の一覧で、**[クラスの設定]** を選択します。
5. **[ハードウェア インベントリ クラス]** ダイアログ ボックスで、**[追加]** を選択します。
6. **[ハードウェア インベントリ クラスの追加]** ダイアログ ボックスで、**[接続]** をクリックします。
7. **[Windows Management Instrumentation (WMI) に接続]** ダイアログ ボックスに、Enterprise Site Discovery が構成されているコンピューターの名前を入力します。 別のコンピューターに接続する場合は、WMI にアクセスするためのアクセス許可を持つ資格情報が必要です。
8. **[WMI 名前空間]** に、「**root\cimv2\IETelemetry**」と入力します。
9. **[接続]** を選択します。
10. **[ハードウェア インベントリ クラスの追加]** ダイアログ ボックスの **[インベントリ クラス]** の一覧で、WMI クラスの **IESystemINfo**、**IEUrlInfo**、および **IECountInfo* を選択します。
11. **[OK]** をクリックして、**[クラスの修飾子]** ダイアログ ボックス、および開いている他のすべてのダイアログを閉じます。

クライアントが管理ポイントから設定を更新すると、次にハードウェア インベントリが実行されたときに (既定では 7 日ごと) データがレポートされます。

## <a name="import-site-discovery-reports"></a>Site Discovery のレポートをインポートする

Enterprise Site Discovery パッケージには、2 つのサンプル レポートが含まれています。 1 つのレポートは ActiveX コントロールを使用しているサイトを示すもので、もう 1 つのレポートは従来のドキュメント モードを使用しているサイトを示すものです。

### <a name="configure-the-site-discovery-sample-report"></a>Site Discovery サンプル レポートを構成する

次の手順を使用して、サンプル レポートを作成します。このサンプル レポートでは、ユーザーが訪問したサイト、サイトのシステム情報、サイトで使用されるドキュメント モードの 3 つのデータ ソースを使用します。 このレポートは、従来のドキュメント モードに依存している可能性があるサイトを特定するのに役立ちます。

1. レポート **SCCM_Report-Site_Discovery.rdl** を Configuration Manager サーバーにコピーします。
2. [Microsoft Report Builder](/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15) をインストールします。
3. **SCCM_Report-Site_Discovery.rdl** をダブルクリックして、Report Builder でレポートを開きます。
4. ユーザーが初めてレポートを開こうとすると、レポートが作成されたサーバーへの接続が試みられます。 **[Connect to Report Server](レポート サーバーに接続)** するように求められたら、**[いいえ]** をクリックします。
5. レポートが開いたら、**[データ ソース]** を展開し、**[DataSource1]** をダブルクリックします。
6. **[データ ソースのプロパティ]** ウィンドウで、**[レポートに埋め込まれた接続を使用する]** を選択し、**[ビルド...]** ボタンをクリックします。
7. **[接続のプロパティ]** ウィンドウで、**[サーバー名]** を選択し、Configuration Manager サーバーの名前を入力します。 次に、**[データベース名の選択または入力]** で、ドロップダウン リストから Configuration Manager データベースの名前を選択します。
8. **[OK]** をクリックして、**[接続のプロパティ]** ウィンドウを閉じます。
9. **[接続テスト]** をクリックして、接続をテストします。 接続が成功したら、**[OK]** をクリックして、**[データ ソースのプロパティ]** ウィンドウを閉じます。
10. **Data Source 2** についても、手順 5 から 9 を繰り返します。
11. **[データセット]** を展開し、**[DataSet1]** をダブルクリックします。
12. **[データセットのプロパティ]** ウィンドウで、**[クエリ:]** テキストボックスをクリックし、**[USE CM_A1B]** を手順 7 で選択したデータベース名に置き換えます。
13. **[DataSet2]**、**[DataSet3]**、**[DataSet4]** についても、手順 11 から 12 を繰り返します。
14. リボンの **[ホーム]** タブで、**[実行]** ボタンをクリックして、レポートをテストします。
15. レポートを保存します。
16. Microsoft レポート ビルダを終了します。
17. ファイル名を **Site Discovery.rdl** に変更します。

### <a name="configure-the-activex-sample-report"></a>ActiveX サンプル レポートを構成する

次の手順を使用して、サンプル レポートを作成します。このサンプル レポートでは、ActiveX コントロールを使用するサイトという 1 つのデータ ソースを使用します。 ActiveX コントロールをサポートするブラウザーは Internet Explorer のみなので、これらのサイトには IE モードが必要になる場合があります。

1. レポート **SCCM Report Sample - ActiveX.rdl** を Configuration Manager サーバーにコピーします。
2. [Microsoft Report Builder](/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15) をインストールします。
3. **SCCM Report Sample - ActiveX.rdl** をダブルクリックして、Report Builder でレポートを開きます。
4. ユーザーが初めてレポートを開こうとすると、レポートが作成されたサーバーへの接続が試みられます。 **[Connect to Report Server](レポート サーバーに接続)** するように求められたら、**[いいえ]** をクリックします。
5. レポートが開いたら、**[データ ソース]** を展開し、**[AutoGen__5C6358F2_4BB6_4a1b_A16E_8D96795D8602_]** をダブルクリックします。
6. **[データ ソースのプロパティ]** ウィンドウで、**[レポートに埋め込まれた接続を使用する]** を選択し、**[ビルド...]** ボタンをクリックします。
7. **[接続のプロパティ]** ウィンドウで、**[サーバー名]** を選択し、Configuration Manager サーバーの名前を入力します。 次に、**[データベース名の選択または入力]** で、ドロップダウン リストから Configuration Manager データベースの名前を選択します。
8. **[OK]** をクリックして、**[接続のプロパティ]** ウィンドウを閉じます。
9. **[接続テスト]** をクリックして、接続をテストします。 接続が成功したら、**[OK]** をクリックして、**[データ ソースのプロパティ]** ウィンドウを閉じます。
10. **[データセット]** を展開し、**[DataSet1]** をダブルクリックします。
11. **[データセットのプロパティ]** ウィンドウで、**[クエリ:]** テキストボックスをクリックし、**[USE CM_A1B]** を手順 7 で選択したデータベース名に置き換えます。
12. リボンの **[ホーム]** タブで、**[実行]** ボタンをクリックして、レポートをテストします。
13. レポートを保存します。
14. Microsoft レポート ビルダを終了します。
15. ファイル名を **ActiveX** に変更します。

### <a name="upload-configured-reports-to-microsoft-sql-server-reporting-services"></a>構成されたレポートを Microsoft SQL Server Reporting Services にアップロードする

使用している環境のレポートを構成したら、それらをレポート サーバーにアップロードします。

1. **Reporting Services Configuration Manager** アプリケーションを起動します。
2. **[レポート サーバーの接続]** ウィンドウで、**[接続]** をクリックし、**[Web Portal Site Identification](Web ポータル サイト ID)** にリストされている URL をクリックします。
3. ブラウザー ウィンドウが開いて、**[SQL Server Reporting Services] ページ**が表示されます。お使いの SCCM サイト コードの **[ConfigMgr_SCCMSiteCode]** フォルダーをクリックします。
4. リボンで、**[新規]** の上にマウス ポインターを置き、**[フォルダー]** メニュー項目をクリックします。
5. 「**Enterprise Site Discovery**」などのフォルダー名を入力し、**[作成]** をクリックします。
6. **[Enterprise Site Discovery]** フォルダーをクリックします。
7. リボンで、**[アップロード]** ボタンをクリックします。
8. **[Site Discovery]** レポートを選択し、**[OK]** をクリックします。
9. **ActiveX** レポートについて、手順 7 と 8 を繰り返します。

### <a name="view-reports-in-configuration-manager"></a>Configuration Manager でレポートを表示する

レポートのカスタマイズとアップロードが済んだので、Configuration Manager でレポートを表示することができます。

1. Configuration Manager コンソールで、**[監視]** > **[レポート]** > **[レポート]** > **[Enterprise Site Discovery]** の順に選択します。
2. レポートをダブルクリックして表示します。

## <a name="disable-enterprise-site-discovery"></a>Enterprise Site Discovery を無効にする

データの収集が完了したら、Enterprise Site Discovery を無効にする必要があります。 [ドキュメント](/configmgr/apps/deploy-use/packages-and-programs)の説明に従って、Enterprise Site Discovery を無効にするための 2 つ目のパッケージを Microsoft Endpoint Configuration Manager に作成し、次のオプションを選択します。

- **[パッケージ]** ページで、**[名前]** を選択し、名前を **[Site Discovery を無効にする]** に指定します。
- **[パッケージ]** ページで、**[このパッケージはソース ファイルを含む]** を選択します。
- **[パッケージ]** ページで、ファイルの抽出先ソース フォルダー (例: **\\\\DSL\\EnterpriseSiteDiscovery**) を指定します。
- **[プログラムの種類]** ページで、**[標準プログラム]** を選択します。
- **[標準プログラム]** ページで、デバイスの Site Discovery を無効にするコマンド ラインを次のように入力します。
  ```dos
  powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1 -IEFeatureOff
  ```
- **[標準プログラム]** ページで、**[非表示]** を実行するためのオプションを選択します。
- **[標準プログラム]** ページの **[プログラムの実行条件]** で、**[ユーザーがログインしているかどうか]** を選択します。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [IE モードの概要](./edge-ie-mode.md)
- [その他のエンタープライズ モード情報](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [その他の Enterprise Site Discovery の情報](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)