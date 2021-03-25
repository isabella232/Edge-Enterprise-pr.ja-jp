---
title: Enterprise Site Discovery ステップ バイ ステップ ガイド
ms.author: cjacks
author: appcompatguy
manager: saudm
ms.date: 04/07/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Enterprise Site Discovery を使用して IE モードを準備する
ms.openlocfilehash: 2557544a93222b03aaa0961149aa0d3c5d7d8806
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447721"
---
# <a name="enterprise-site-discovery-step-by-step-guide"></a><span data-ttu-id="36a7b-103">Enterprise Site Discovery ステップ バイ ステップ ガイド</span><span class="sxs-lookup"><span data-stu-id="36a7b-103">Enterprise Site Discovery Step-by-Step Guide</span></span>

<span data-ttu-id="36a7b-104">この記事は、Microsoft Endpoint Configuration Manager で Enterprise Site Discovery を使用するためのステップ バイ ステップ ガイドです。</span><span class="sxs-lookup"><span data-stu-id="36a7b-104">This article provides a step-by-step guide to using Enterprise Site Discovery with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="36a7b-105">Enterprise Site Discovery は、Enterprise Mode Site List を構成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-105">Enterprise Site Discovery can help you configure your Enterprise Mode Site List.</span></span> <span data-ttu-id="36a7b-106">Enterprise Site Discovery は次のことに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-106">Enterprise Site Discovery will help you:</span></span>

- <span data-ttu-id="36a7b-107">従来のドキュメント モードを使用しているサイトを検出する。</span><span class="sxs-lookup"><span data-stu-id="36a7b-107">Discover which sites are using legacy document modes.</span></span> <span data-ttu-id="36a7b-108">このようなサイトは、サイトが最新のブラウザーを検出して異なる HTML を提供する場合を除き、IE モードを使用することが必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="36a7b-108">Unless these sites are detecting modern browsers and providing different HTML, they probably need to use IE mode.</span></span>
- <span data-ttu-id="36a7b-109">ActiveX コントロールを使用しているサイトを検出する。</span><span class="sxs-lookup"><span data-stu-id="36a7b-109">Discover which sites are using ActiveX controls.</span></span> <span data-ttu-id="36a7b-110">Microsoft Edge では、ActiveX コントロールをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="36a7b-110">Microsoft Edge doesn't support ActiveX controls.</span></span> <span data-ttu-id="36a7b-111">このようなサイトは、サイトが最新のブラウザーを検出して異なる HTML を提供する場合を除き、IE モードを使用することが必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="36a7b-111">Unless these sites are detecting modern browsers and providing different HTML, they probably need to use IE mode.</span></span>

> [!NOTE]
> <span data-ttu-id="36a7b-112">この記事は、Microsoft Edge version 77 (**Stable**、**Beta**、および **Dev** チャネル) 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-112">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36a7b-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="36a7b-113">Prerequisites</span></span>

<span data-ttu-id="36a7b-114">このガイドは、読者に Microsoft Endpoint Configuration Manager の使用経験があり、次のサービスとロールがインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="36a7b-114">This guide assumes you're experienced with using Microsoft Endpoint Configuration Manager and have the following services and roles installed:</span></span>

1. <span data-ttu-id="36a7b-115">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="36a7b-115">Microsoft Endpoint Configuration Manager</span></span>
2. <span data-ttu-id="36a7b-116">Microsoft SQL Reporting Services</span><span class="sxs-lookup"><span data-stu-id="36a7b-116">Microsoft SQL Server Reporting Services</span></span>
3. <span data-ttu-id="36a7b-117">(オプション) Configuration Manager Reporting Services ポイント ロールが構成されている</span><span class="sxs-lookup"><span data-stu-id="36a7b-117">(Optional) Configuration Manager Reporting Services Point Role configured</span></span>

## <a name="download-enterprise-site-discovery-tools"></a><span data-ttu-id="36a7b-118">Enterprise Site Discovery ツールをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="36a7b-118">Download Enterprise Site Discovery Tools</span></span>

<span data-ttu-id="36a7b-119">次のツールをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-119">Download the following tools:</span></span>

- [<span data-ttu-id="36a7b-120">Enterprise Site Discovery のセットアップと構成パッケージ</span><span class="sxs-lookup"><span data-stu-id="36a7b-120">Enterprise Site Discovery Setup and Configuration Package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517719)
- [<span data-ttu-id="36a7b-121">Microsoft Report Builder</span><span class="sxs-lookup"><span data-stu-id="36a7b-121">Microsoft Report Builder</span></span>](https://www.microsoft.com/download/details.aspx?id=53613)

## <a name="enable-enterprise-site-discovery"></a><span data-ttu-id="36a7b-122">Enterprise Site Discovery を有効にする</span><span class="sxs-lookup"><span data-stu-id="36a7b-122">Enable Enterprise Site Discovery</span></span>

<span data-ttu-id="36a7b-123">Windows Management Instrumentation (WMI) に接続してサイト検出データを取得するには、まず、WMI クラス プロバイダーをデバイスに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36a7b-123">Before you can connect to Windows Management Instrumentation (WMI) to retrieve site discovery data, you must first deploy the WMI class provider to the device.</span></span>

<span data-ttu-id="36a7b-124">**Enterprise Site Discovery のセットアップと構成パッケージ**から、確定版ソフトウェア ライブラリのファイル共有内のフォルダーにコンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-124">From the **Enterprise Site Discovery Setup and Configuration Package**, extract the contents to a folder in your definitive software library file share.</span></span> <span data-ttu-id="36a7b-125">例: **\\\\DSL\\EnterpriseSiteDiscovery**。</span><span class="sxs-lookup"><span data-stu-id="36a7b-125">Example: **\\\\DSL\\EnterpriseSiteDiscovery**.</span></span>

<span data-ttu-id="36a7b-126">次に、[ドキュメント](/configmgr/apps/deploy-use/packages-and-programs)の説明に従って Microsoft Endpoint Configuration Manager にパッケージを作成し、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-126">Next, create a package in Microsoft Endpoint Configuration Manager, as described in the [documentation](/configmgr/apps/deploy-use/packages-and-programs), selecting the following options:</span></span>

- <span data-ttu-id="36a7b-127">**[パッケージ]** ページで、**[名前]** を選択し、名前を **[Site Discovery を有効にする]** に指定します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-127">On the **Package** page, select **Name** and specify the name **Enable Site Discovery**</span></span>
- <span data-ttu-id="36a7b-128">**[パッケージ]** ページで、**[このパッケージはソース ファイルを含む]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-128">On the **Package** page, select **This package contains source files**</span></span>
- <span data-ttu-id="36a7b-129">**[パッケージ]** ページで、ファイルの抽出先ソース フォルダー (例: **\\\\DSL\\EnterpriseSiteDiscovery**) を指定します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-129">On the **Package** page, specify the source folder you extracted the files to (for example, **\\\\DSL\\EnterpriseSiteDiscovery**)</span></span>
- <span data-ttu-id="36a7b-130">**[プログラムの種類]** ページで、**[標準プログラム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-130">On the **Program Type** page, choose **Standard Program**</span></span>
- <span data-ttu-id="36a7b-131">**[標準プログラム]** ページで、次のようにコマンド ラインを入力して、デバイスに Site Discovery を構成します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-131">On the **Standard Program** page, enter the command line to configure Site Discovery on the device as follows:</span></span>
  ```dos
  powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1
  ```
  > [!NOTE]
  > <span data-ttu-id="36a7b-132">このスクリプトでは、`-ZoneAllowList` と `-SiteAllowList` のスイッチを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-132">The script supports using command line switches for `-ZoneAllowList` and `-SiteAllowList`.</span></span> <span data-ttu-id="36a7b-133">このステップ バイ ステップでは、グループ ポリシーを使用してこれらのオプションを構成します (後述)。</span><span class="sxs-lookup"><span data-stu-id="36a7b-133">For this step-by-step, we will configure these options via group policy (below).</span></span>
- <span data-ttu-id="36a7b-134">**[標準プログラム]** ページで、**[Hidden](非表示)** を実行するためのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-134">On the **Standard Program** page, select the option to run **Hidden**.</span></span>
- <span data-ttu-id="36a7b-135">**[標準プログラム]** ページの **[プログラムの実行条件]** で、**[Whether or not a user is logged in](ユーザーがログインしているかどうか)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-135">On the **Standard Program** page, under **Program can run**, select the option **Whether or not a user is logged in**</span></span>

<span data-ttu-id="36a7b-136">パッケージを作成したら、パッケージ名の **[Site Discovery を有効にする]** をダブルクリックして、そのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-136">After creating the package, double-click on the package name **Enable Site Discovery** to view its properties.</span></span> <span data-ttu-id="36a7b-137">**[実行後]** プロパティで、**[Configuration Manager がコンピューターを再起動する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-137">In the **After running** property, select **Configuration manager restarts computer**.</span></span> <span data-ttu-id="36a7b-138">デバイスが再起動すると、WMI データの収集が開始されます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-138">WMI data collection will begin after the devices reboot.</span></span>

> [!NOTE]
> <span data-ttu-id="36a7b-139">[クライアント設定ドキュメント](/configmgr/core/clients/deploy/about-client-settings#computer-restart)の説明に従って、デバイスを再起動するまでの時間の長さを設定できます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-139">You can configure the amount of time a user has to restart the device as described in the [client settings documentation](/configmgr/core/clients/deploy/about-client-settings#computer-restart).</span></span>

## <a name="configure-enterprise-site-discovery-via-group-policy"></a><span data-ttu-id="36a7b-140">グループ ポリシーを使用して Enterprise Site Discovery を構成する</span><span class="sxs-lookup"><span data-stu-id="36a7b-140">Configure Enterprise Site Discovery via Group Policy</span></span>

<span data-ttu-id="36a7b-141">Enterprise Site Discovery が有効になっていると、どんなデータを収集するかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-141">With Enterprise Site Discovery enabled, you can configure what data you'll collect.</span></span> <span data-ttu-id="36a7b-142">[こちら](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery#what-data-is-collected)の説明に従って、地域の法律と規制要件をご検討ください。</span><span class="sxs-lookup"><span data-stu-id="36a7b-142">Consider local laws and regulatory requirements as described [here](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery#what-data-is-collected).</span></span>

1. <span data-ttu-id="36a7b-143">グループ ポリシー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-143">Open Group Policy Editor</span></span>
2. <span data-ttu-id="36a7b-144">**[コンピューターの構成]** > **[管理用テンプレート]** > **[Windows コンポーネント]** > **[Internet Explorer]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-144">Click **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Internet Explorer**</span></span> 
3. <span data-ttu-id="36a7b-145">**[サイト探索 WMI 出力を有効にする]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-145">Double-click **Turn on Site Discovery WMI output**</span></span>
4. <span data-ttu-id="36a7b-146">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-146">Select **Enabled**</span></span>
5. <span data-ttu-id="36a7b-147">**[OK]** または **[適用]** をクリックして、このポリシー設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-147">Click **OK** or **Apply** to save this policy setting</span></span>

<span data-ttu-id="36a7b-148">サイト データを収集するゾーンを制限できます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-148">You can limit the zones in which you collect site data:</span></span>

1. <span data-ttu-id="36a7b-149">**[サイト探索の出力をゾーンで制限する]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-149">Double-click **Limit Site Discovery output by Zone**</span></span>
2. <span data-ttu-id="36a7b-150">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-150">Select **Enabled**</span></span>
3. <span data-ttu-id="36a7b-151">次に関して、サイト検出を有効にするゾーンを示すビットマスクを入力します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-151">Enter a bitmask indicating which zones to enable site discover for:</span></span>
    1. <span data-ttu-id="36a7b-152">制限付きサイト ゾーン</span><span class="sxs-lookup"><span data-stu-id="36a7b-152">Restricted Sites zone</span></span>
    2. <span data-ttu-id="36a7b-153">イントラネット ゾーン</span><span class="sxs-lookup"><span data-stu-id="36a7b-153">Internet zone</span></span>
    3. <span data-ttu-id="36a7b-154">信頼済みサイト ゾーン</span><span class="sxs-lookup"><span data-stu-id="36a7b-154">Trusted Sites zone</span></span>
    4. <span data-ttu-id="36a7b-155">ローカル イントラネット ゾーン</span><span class="sxs-lookup"><span data-stu-id="36a7b-155">Local Intranet zone</span></span>
    5. <span data-ttu-id="36a7b-156">ローカル マシン ゾーン</span><span class="sxs-lookup"><span data-stu-id="36a7b-156">Local Machine zone</span></span>
    
    <span data-ttu-id="36a7b-157">例 1: **00010** に指定すると、ローカル イントラネット ゾーンのデータのみが収集されます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-157">Example 1: **00010** will collect data only for the Local Intranet zone</span></span>

    <span data-ttu-id="36a7b-158">例 2： **10111** に指定すると、インターネット ゾーンを除くすべてのゾーンのデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-158">Example 2: **10111** will collect data for all zones except the Internet zone</span></span>
4. <span data-ttu-id="36a7b-159">**[OK]** または **[適用]** をクリックして、このポリシー設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-159">Click **OK** or **Apply** to save this policy setting</span></span>

<span data-ttu-id="36a7b-160">サイト データを収集するドメインを制限できます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-160">You can limit the domains for which you collect site data:</span></span>

1. <span data-ttu-id="36a7b-161">**[サイト探索の出力をドメインで制限する]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-161">Double-click **Limit Site Discovery output by domain**</span></span>
2. <span data-ttu-id="36a7b-162">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-162">Select **Enabled**</span></span>
3. <span data-ttu-id="36a7b-163">データを収集するドメインを、1 行につき 1 ドメインとなるように入力します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-163">Enter the domains you want to collect data for, one domain per line</span></span>
4. <span data-ttu-id="36a7b-164">**[OK]** または **[適用]** をクリックして、このポリシー設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-164">Click **OK** or **Apply** to save this policy setting</span></span>

## <a name="collect-site-discovery-data-using-configuration-manager"></a><span data-ttu-id="36a7b-165">Configuration Manager を使用して Site Discovery のデータを収集する</span><span class="sxs-lookup"><span data-stu-id="36a7b-165">Collect Site Discovery data using Configuration Manager</span></span>

<span data-ttu-id="36a7b-166">デバイスでデータが生成されるようになったので、今度はこのデータを Configuration Manager で収集します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-166">Now that your devices are generating data, it's time to collect this data in Configuration Manager.</span></span>

1. <span data-ttu-id="36a7b-167">Configuration Manager コンソールで、**[管理]** > **[クライアント設定]** > **[既定のクライアント設定]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-167">In the Configuration Manager console, choose **Administration** > **Client Settings** > **Default Client Settings**</span></span>
2. <span data-ttu-id="36a7b-168">**[ホーム]** タブの **[プロパティ]** グループで、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-168">On the **Home** tab, in the **Properties** group, choose **Properties**</span></span>
3. <span data-ttu-id="36a7b-169">**[既定のクライアント設定]** ダイアログ ボックスで、**[ハードウェア インベントリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-169">In the **Default Client Settings** dialog box, choose **Hardware Inventory**</span></span>
4. <span data-ttu-id="36a7b-170">**[デバイス設定]** の一覧で、**[クラスの設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-170">In the **Device Settings** list, choose **Set Classes**</span></span>
5. <span data-ttu-id="36a7b-171">**[ハードウェア インベントリ クラス]** ダイアログ ボックスで、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-171">In the **Hardware Inventory Classes** dialog box, choose **Add**</span></span>
6. <span data-ttu-id="36a7b-172">**[ハードウェア インベントリ クラスの追加]** ダイアログ ボックスで、**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-172">In the **Add Hardware Inventory Class** dialog box, click **Connect**</span></span>
7. <span data-ttu-id="36a7b-173">**[Windows Management Instrumentation (WMI) に接続]** ダイアログ ボックスに、Enterprise Site Discovery が構成されているコンピューターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-173">In the **Connect to Windows Management Instrumentation (WMI)** dialog box, enter the name of a computer where Enterprise Site Discovery is configured.</span></span> <span data-ttu-id="36a7b-174">別のコンピューターに接続する場合は、WMI にアクセスするためのアクセス許可を持つ資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="36a7b-174">If you're connecting to another computer, you'll need credentials with permission to access WMI.</span></span>
8. <span data-ttu-id="36a7b-175">**[WMI 名前空間]** に、「**root\cimv2\IETelemetry**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-175">In the **WMI Namespace** text box, enter **root\cimv2\IETelemetry**</span></span>
9. <span data-ttu-id="36a7b-176">**[接続]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-176">Choose **Connect**</span></span>
10. <span data-ttu-id="36a7b-177">**[ハードウェア インベントリ クラスの追加]** ダイアログ ボックスの **[インベントリ クラス]** の一覧で、WMI クラスの **IESystemINfo**、**IEUrlInfo**、および \**IECountInfo* を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-177">In the **Add Hardware Inventory Class** dialog box, in the **Inventory classes** list, select the WMI classes **IESystemINfo**, **IEUrlInfo**, and \**IECountInfo*.</span></span>
11. <span data-ttu-id="36a7b-178">**[OK]** をクリックして、**[クラスの修飾子]** ダイアログ ボックス、および開いている他のすべてのダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-178">Click **OK** to close the **Class qualifiers** dialog box and the other open dialogs.</span></span>

<span data-ttu-id="36a7b-179">クライアントが管理ポイントから設定を更新すると、次にハードウェア インベントリが実行されたときに (既定では 7 日ごと) データがレポートされます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-179">After the client updates settings from the management point, data will be reported when the next hardware inventory runs (by default every seven days).</span></span>

## <a name="import-site-discovery-reports"></a><span data-ttu-id="36a7b-180">Site Discovery のレポートをインポートする</span><span class="sxs-lookup"><span data-stu-id="36a7b-180">Import Site Discovery reports</span></span>

<span data-ttu-id="36a7b-181">Enterprise Site Discovery パッケージには、2 つのサンプル レポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="36a7b-181">The Enterprise Site Discovery package includes two sample reports.</span></span> <span data-ttu-id="36a7b-182">1 つのレポートは ActiveX コントロールを使用しているサイトを示すもので、もう 1 つのレポートは従来のドキュメント モードを使用しているサイトを示すものです。</span><span class="sxs-lookup"><span data-stu-id="36a7b-182">One report shows sites using ActiveX controls, and another shows sites using legacy document modes.</span></span>

### <a name="configure-the-site-discovery-sample-report"></a><span data-ttu-id="36a7b-183">Site Discovery サンプル レポートを構成する</span><span class="sxs-lookup"><span data-stu-id="36a7b-183">Configure the Site Discovery sample report</span></span>

<span data-ttu-id="36a7b-184">次の手順を使用して、サンプル レポートを作成します。このサンプル レポートでは、ユーザーが訪問したサイト、サイトのシステム情報、サイトで使用されるドキュメント モードの 3 つのデータ ソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-184">Use the following procedure to create a sample report that uses three data sources: the sites a user visits, information about their system, and the document modes used by the sites.</span></span> <span data-ttu-id="36a7b-185">このレポートは、従来のドキュメント モードに依存している可能性があるサイトを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-185">This report helps you identify sites that may depend on legacy document modes.</span></span>

1. <span data-ttu-id="36a7b-186">レポート **SCCM_Report-Site_Discovery.rdl** を Configuration Manager サーバーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-186">Copy the report **SCCM_Report-Site_Discovery.rdl** to your Configuration Manager server.</span></span>
2. <span data-ttu-id="36a7b-187">[Microsoft Report Builder](/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-187">Install [Microsoft Report Builder](/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15).</span></span>
3. <span data-ttu-id="36a7b-188">**SCCM_Report-Site_Discovery.rdl** をダブルクリックして、Report Builder でレポートを開きます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-188">Double-click **SCCM_Report-Site_Discovery.rdl** to open the report in Report Builder.</span></span>
4. <span data-ttu-id="36a7b-189">ユーザーが初めてレポートを開こうとすると、レポートが作成されたサーバーへの接続が試みられます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-189">The first time you try to open the report, it will try to contact the server where it was created.</span></span> <span data-ttu-id="36a7b-190">**[Connect to Report Server](レポート サーバーに接続)** するように求められたら、**[いいえ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-190">When prompted to **Connect to Report Server**, click **No**.</span></span>
5. <span data-ttu-id="36a7b-191">レポートが開いたら、**[データ ソース]** を展開し、**[DataSource1]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-191">After the report opens, expand **Data Sources** and double-click **DataSource1**.</span></span>
6. <span data-ttu-id="36a7b-192">**[データ ソースのプロパティ]** ウィンドウで、**[Use a connection embedded in my report](レポートに埋め込まれた接続を使用する)** を選択し、**[Build...](ビルド...)** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-192">In the **Data Source Properties** window, select **Use a connection embedded in my report** and then click the **Build...** button.</span></span>
7. <span data-ttu-id="36a7b-193">**[接続のプロパティ]** ウィンドウで、**[サーバー名]** を選択し、Configuration Manager サーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-193">In the **Connection Properties** window, select **Server Name** and enter the name of the Configuration Manager server.</span></span> <span data-ttu-id="36a7b-194">次に、**[データベース名の選択または入力]** で、ドロップダウン リストから Configuration Manager データベースの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-194">Then, in **Select or enter a database name** select the name of the Configuration Manager database from the dropdown list.</span></span>
8. <span data-ttu-id="36a7b-195">**[OK]** をクリックして、**[接続のプロパティ]** ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-195">Click **OK** to close the **Connection Properties** window.</span></span>
9. <span data-ttu-id="36a7b-196">**[Test Connection](接続テスト)** をクリックして、接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-196">Click **Test Connection** to test the connection.</span></span> <span data-ttu-id="36a7b-197">接続が成功したら、**[OK]** をクリックして、**[データ ソースのプロパティ]** ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-197">If the connection is successful, click **OK** to close the **Data Source Properties** window.</span></span>
10. <span data-ttu-id="36a7b-198">**Data Source 2** についても、手順 5 から 9 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-198">Repeat Steps 5 through 9 for **Data Source 2**.</span></span>
11. <span data-ttu-id="36a7b-199">**[データセット]** を展開し、**[DataSet1]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-199">Expand **Datasets** and double-click **DataSet1**.</span></span>
12. <span data-ttu-id="36a7b-200">**[データセットのプロパティ]** ウィンドウで、**[クエリ:]** テキストボックスをクリックし、**[USE CM_A1B]** を手順 7 で選択したデータベース名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-200">In the **Dataset Properties** window, click in the **Query:** textbox and replace **USE CM_A1B** with the database name you selected in Step 7.</span></span>
13. <span data-ttu-id="36a7b-201">**[DataSet2]**、**[DataSet3]**、**[DataSet4]** についても、手順 11 から 12 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-201">Repeat steps 11 through 12 for **DataSet2**, **DataSet3**, and **DataSet4**.</span></span>
14. <span data-ttu-id="36a7b-202">リボンの **[ホーム]** タブで、**[実行]** ボタンをクリックして、レポートをテストします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-202">In the **Home** tab of the ribbon, click the **Run** button to test the report.</span></span>
15. <span data-ttu-id="36a7b-203">レポートを保存します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-203">Save the report.</span></span>
16. <span data-ttu-id="36a7b-204">Microsoft レポート ビルダを終了します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-204">Close Microsoft Report Builder.</span></span>
17. <span data-ttu-id="36a7b-205">ファイル名を **Site Discovery.rdl** に変更します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-205">Rename the file to **Site Discovery.rdl**</span></span>

### <a name="configure-the-activex-sample-report"></a><span data-ttu-id="36a7b-206">ActiveX サンプル レポートを構成する</span><span class="sxs-lookup"><span data-stu-id="36a7b-206">Configure the ActiveX sample report</span></span>

<span data-ttu-id="36a7b-207">次の手順を使用して、サンプル レポートを作成します。このサンプル レポートでは、ActiveX コントロールを使用するサイトという 1 つのデータ ソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-207">Use the following procedure to create a sample report that uses one data source: the sites that are using ActiveX controls.</span></span> <span data-ttu-id="36a7b-208">ActiveX コントロールをサポートするブラウザーは Internet Explorer のみなので、これらのサイトには IE モードが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="36a7b-208">Since Internet Explorer is the only browser that support ActiveX controls, these sites may require IE mode.</span></span>

1. <span data-ttu-id="36a7b-209">レポート **SCCM Report Sample - ActiveX.rdl** を Configuration Manager サーバーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-209">Copy the report **SCCM Report Sample - ActiveX.rdl** to your Configuration Manager server.</span></span>
2. <span data-ttu-id="36a7b-210">[Microsoft Report Builder](/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-210">Install [Microsoft Report Builder](/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15).</span></span>
3. <span data-ttu-id="36a7b-211">**SCCM Report Sample - ActiveX.rdl** をダブルクリックして、Report Builder でレポートを開きます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-211">Double-click **SCCM Report Sample - ActiveX.rdl** to open the report in Report Builder.</span></span>
4. <span data-ttu-id="36a7b-212">ユーザーが初めてレポートを開こうとすると、レポートが作成されたサーバーへの接続が試みられます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-212">The first time you try to open the report, it will try to contact the server where it was created.</span></span> <span data-ttu-id="36a7b-213">**[Connect to Report Server](レポート サーバーに接続)** するように求められたら、**[いいえ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-213">When prompted to **Connect to Report Server**, click **No**.</span></span>
5. <span data-ttu-id="36a7b-214">レポートが開いたら、**[データ ソース]** を展開し、**[AutoGen__5C6358F2_4BB6_4a1b_A16E_8D96795D8602_]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-214">After the report opens, expand **Data Sources** and double-click **AutoGen__5C6358F2_4BB6_4a1b_A16E_8D96795D8602_**.</span></span>
6. <span data-ttu-id="36a7b-215">**[データ ソースのプロパティ]** ウィンドウで、**[Use a connection embedded in my report](レポートに埋め込まれた接続を使用する)** を選択し、**[Build...](ビルド...)** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-215">In the **Data Source Properties** window, select **Use a connection embedded in my report** and then click the **Build...** button.</span></span>
7. <span data-ttu-id="36a7b-216">**[接続のプロパティ]** ウィンドウで、**[サーバー名]** を選択し、Configuration Manager サーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-216">In the **Connection Properties** window, select **Server Name** and enter the name of the Configuration Manager server.</span></span> <span data-ttu-id="36a7b-217">次に、**[データベース名の選択または入力]** で、ドロップダウン リストから Configuration Manager データベースの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-217">Then, in **Select or enter a database name** select the name of the Configuration Manager database from the dropdown list.</span></span>
8. <span data-ttu-id="36a7b-218">**[OK]** をクリックして、**[接続のプロパティ]** ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-218">Click **OK** to close the **Connection Properties** window.</span></span>
9. <span data-ttu-id="36a7b-219">**[Test Connection](接続テスト)** をクリックして、接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-219">Click **Test Connection** to test the connection.</span></span> <span data-ttu-id="36a7b-220">接続が成功したら、**[OK]** をクリックして、**[データ ソースのプロパティ]** ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-220">If the connection is successful, click **OK** to close the **Data Source Properties** window.</span></span>
10. <span data-ttu-id="36a7b-221">**[データセット]** を展開し、**[DataSet1]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-221">Expand **Datasets** and double-click **DataSet1**.</span></span>
11. <span data-ttu-id="36a7b-222">**[データセットのプロパティ]** ウィンドウで、**[クエリ:]** テキストボックスをクリックし、**[USE CM_A1B]** を手順 7 で選択したデータベース名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-222">In the **Dataset Properties** window, click in the **Query:** textbox and replace **USE CM_A1B** with the database name you selected in Step 7.</span></span>
12. <span data-ttu-id="36a7b-223">リボンの **[ホーム]** タブで、**[実行]** ボタンをクリックして、レポートをテストします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-223">In the **Home** tab of the ribbon, click the **Run** button to test the report.</span></span>
13. <span data-ttu-id="36a7b-224">レポートを保存します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-224">Save the report.</span></span>
14. <span data-ttu-id="36a7b-225">Microsoft レポート ビルダを終了します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-225">Close Microsoft Report Builder.</span></span>
15. <span data-ttu-id="36a7b-226">ファイル名を **ActiveX** に変更します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-226">Rename the file to **ActiveX**</span></span>

### <a name="upload-configured-reports-to-microsoft-sql-server-reporting-services"></a><span data-ttu-id="36a7b-227">構成されたレポートを Microsoft SQL Server Reporting Services にアップロードする</span><span class="sxs-lookup"><span data-stu-id="36a7b-227">Upload configured reports to Microsoft SQL Server Reporting Services</span></span>

<span data-ttu-id="36a7b-228">使用している環境のレポートを構成したら、それらをレポート サーバーにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-228">After you've configured the reports for your environment, upload them to the reporting server.</span></span>

1. <span data-ttu-id="36a7b-229">**Reporting Services Configuration Manager** アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-229">Launch the **Reporting Services Configuration Manager** application.</span></span>
2. <span data-ttu-id="36a7b-230">**[レポート サーバーの接続]** ウィンドウで、**[接続]** をクリックし、**[Web Portal Site Identification](Web ポータル サイト ID)** にリストされている URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-230">In the **Report Server Connection** window, click **Connect** and then click on the URL listed under **Web Portal Site Identification**</span></span>
3. <span data-ttu-id="36a7b-231">ブラウザー ウィンドウが開いて、**[SQL Server Reporting Services] ページ**が表示されます。お使いの SCCM サイト コードの **[ConfigMgr_SCCMSiteCode]** フォルダーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-231">In the browser window that opens, you should be on the **SQL Server Reporting Services Page** - click the **ConfigMgr_SCCMSiteCode** folder for your SCCM Site Code.</span></span>
4. <span data-ttu-id="36a7b-232">リボンで、**[新規]** の上にマウス ポインターを置き、**[フォルダー]** メニュー項目をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-232">In the ribbon, hover over **+New** and click the **Folder** menu item.</span></span>
5. <span data-ttu-id="36a7b-233">「**Enterprise Site Discovery**」などのフォルダー名を入力し、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-233">Enter a folder name, such as **Enterprise Site Discovery**, and then click the **Create** button.</span></span>
6. <span data-ttu-id="36a7b-234">**[Enterprise Site Discovery]** フォルダーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-234">Click on the **Enterprise Site Discovery** folder.</span></span>
7. <span data-ttu-id="36a7b-235">リボンで、**[アップロード]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-235">In the ribbon, click the **Upload** button.</span></span>
8. <span data-ttu-id="36a7b-236">**[Site Discovery]** レポートを選択し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a7b-236">Select the **Site Discovery** report, and click **OK**.</span></span>
9. <span data-ttu-id="36a7b-237">**ActiveX** レポートについて、手順 7 と 8 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-237">Repeat steps 7 and 8 for the **ActiveX** report.</span></span>

### <a name="view-reports-in-configuration-manager"></a><span data-ttu-id="36a7b-238">Configuration Manager でレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="36a7b-238">View reports in Configuration Manager</span></span>

<span data-ttu-id="36a7b-239">レポートのカスタマイズとアップロードが済んだので、Configuration Manager でレポートを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="36a7b-239">Now that you've customized and uploaded the reports, you can view them in Configuration Manager.</span></span>

1. <span data-ttu-id="36a7b-240">Configuration Manager コンソールで、**[監視]** > **[レポート]** > **[レポート]** > **[Enterprise Site Discovery]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-240">In the Configuration Manager console, choose **Monitoring** > **Reporting** > **Reports** > **Enterprise Site Discovery**</span></span>
2. <span data-ttu-id="36a7b-241">レポートをダブルクリックして表示します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-241">Double-click on a report to view it.</span></span>

## <a name="disable-enterprise-site-discovery"></a><span data-ttu-id="36a7b-242">Enterprise Site Discovery を無効にする</span><span class="sxs-lookup"><span data-stu-id="36a7b-242">Disable Enterprise Site Discovery</span></span>

<span data-ttu-id="36a7b-243">データの収集が完了したら、Enterprise Site Discovery を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="36a7b-243">When you're finished collecting data, you should disable Enterprise Site Discovery.</span></span> <span data-ttu-id="36a7b-244">[ドキュメント](/configmgr/apps/deploy-use/packages-and-programs)の説明に従って、Enterprise Site Discovery を無効にするための 2 つ目のパッケージを Microsoft Endpoint Configuration Manager に作成し、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-244">Create a second package to disable Enterprise Site Discovery in Microsoft Endpoint Configuration Manager, as described in the [documentation](/configmgr/apps/deploy-use/packages-and-programs), selecting the following options:</span></span>

- <span data-ttu-id="36a7b-245">**[パッケージ]** ページで、**[名前]** を選択し、名前を **[Site Discovery を無効にする]** に指定します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-245">On the **Package** page, select **Name** and specify the name **Disable Site Discovery**</span></span>
- <span data-ttu-id="36a7b-246">**[パッケージ]** ページで、**[このパッケージはソース ファイルを含む]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-246">On the **Package** page, select **This package contains source files**</span></span>
- <span data-ttu-id="36a7b-247">**[パッケージ]** ページで、ファイルの抽出先ソース フォルダー (例: **\\\\DSL\\EnterpriseSiteDiscovery**) を指定します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-247">On the **Package** page, specify the source folder you extracted the files to (for example, **\\\\DSL\\EnterpriseSiteDiscovery**)</span></span>
- <span data-ttu-id="36a7b-248">**[プログラムの種類]** ページで、**[標準プログラム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-248">On the **Program Type** page, choose **Standard Program**</span></span>
- <span data-ttu-id="36a7b-249">**[標準プログラム]** ページで、デバイスの Site Discovery を無効にするコマンド ラインを次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-249">On the **Standard Program** page, enter the command line that will disable Site Discovery on the device as follows:</span></span>
  ```dos
  powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1 -IEFeatureOff
  ```
- <span data-ttu-id="36a7b-250">**[標準プログラム]** ページで、**[Hidden](非表示)** を実行するためのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-250">On the **Standard Program** page, select the option to run **Hidden**</span></span>
- <span data-ttu-id="36a7b-251">**[標準プログラム]** ページの **[プログラムの実行条件]** で、**[Whether or not a user is logged in](ユーザーがログインしているかどうか)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a7b-251">On the **Standard Program** page, under **Program can run**, select the option **Whether or not a user is logged in**</span></span>

## <a name="see-also"></a><span data-ttu-id="36a7b-252">関連項目</span><span class="sxs-lookup"><span data-stu-id="36a7b-252">See also</span></span>

- [<span data-ttu-id="36a7b-253">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="36a7b-253">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="36a7b-254">IE モードの概要</span><span class="sxs-lookup"><span data-stu-id="36a7b-254">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="36a7b-255">その他のエンタープライズ モード情報</span><span class="sxs-lookup"><span data-stu-id="36a7b-255">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="36a7b-256">その他の Enterprise Site Discovery の情報</span><span class="sxs-lookup"><span data-stu-id="36a7b-256">Additional Enterprise Site Discovery information</span></span>](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)