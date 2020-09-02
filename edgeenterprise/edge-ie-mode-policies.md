---
title: IE モード ポリシーの構成
ms.author: cjacks
author: cjacks
manager: saudm
ms.date: 03/25/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: IE モード ポリシーの構成
ms.openlocfilehash: 2d2ded3a3fb338bdf2d815d681b52249007945ac
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980400"
---
# <span data-ttu-id="cb130-103">IE モード ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="cb130-103">Configure IE mode policies</span></span>

<span data-ttu-id="cb130-104">この記事では、IE モード ポリシーの構成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cb130-104">This article explains how to configure IE mode policies.</span></span>

> [!NOTE]
> <span data-ttu-id="cb130-105">この記事は、Microsoft Edge version 77 (**Stable**、**Beta**、および **Dev** チャネル) 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="cb130-105">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>

<span data-ttu-id="cb130-106">IE モードを構成するには、次の3つの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb130-106">Configuring IE mode requires three steps:</span></span>

1. [<span data-ttu-id="cb130-107">Internet Explorer 統合を構成する</span><span class="sxs-lookup"><span data-stu-id="cb130-107">Configure Internet Explorer integration</span></span>](#configure-internet-explorer-integration)
2. [<span data-ttu-id="cb130-108">サイトを Microsoft Edge から IE モードにリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="cb130-108">Redirect sites from Microsoft Edge to IE mode</span></span>](#redirect-sites-from-microsoft-edge-to-ie-mode)
3. <span data-ttu-id="cb130-109">(省略可能) [サイトを IE から Microsoft Edge にリダイレクトする](#redirect-sites-from-ie-to-microsoft-edge)</span><span class="sxs-lookup"><span data-stu-id="cb130-109">(Optional) [Redirect sites from IE to Microsoft Edge](#redirect-sites-from-ie-to-microsoft-edge)</span></span>

> [!NOTE]
> <span data-ttu-id="cb130-110">IE モードを有効にするポリシーは、Intune を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="cb130-110">Policies to enable IE mode can be configured through Intune.</span></span> <span data-ttu-id="cb130-111">詳しくは、「[Microsoft Edge for Windows 10 を Microsoft Intune に追加する](https://docs.microsoft.com/intune/apps/apps-windows-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)」および「[Microsoft Intune を使って Microsoft Edge ポリシー設定を構成する](https://docs.microsoft.com/DeployEdge/configure-edge-with-intune)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cb130-111">For more information, see [Add Microsoft Edge to Microsoft Intune](https://docs.microsoft.com/intune/apps/apps-windows-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json) and [Configure Microsoft Edge policies with Microsoft Intune](https://docs.microsoft.com/DeployEdge/configure-edge-with-intune).</span></span>

## <span data-ttu-id="cb130-112">Internet Explorer 統合を構成する</span><span class="sxs-lookup"><span data-stu-id="cb130-112">Configure Internet Explorer integration</span></span>

<span data-ttu-id="cb130-113">Microsoft Edge (IE モード) 内で直接開くように、Internet Explorer を構成できます。</span><span class="sxs-lookup"><span data-stu-id="cb130-113">You can configure Internet Explorer to open directly within Microsoft Edge (IE mode).</span></span> <span data-ttu-id="cb130-114">スタンドアロンの Internet Explorer 11 ウィンドウで開くように、Internet Explorer を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="cb130-114">You can also configure Internet Explorer to open with a standalone Internet Explorer 11 window.</span></span> <span data-ttu-id="cb130-115">ほとんどのユーザーは、Microsoft Edge の IE モードでサイトを直接開くことを希望します。</span><span class="sxs-lookup"><span data-stu-id="cb130-115">Most users prefer when sites open directly within Microsoft Edge in IE mode.</span></span>

### <span data-ttu-id="cb130-116">グループ ポリシーを使用して Internet Explorer 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="cb130-116">Enable Internet Explorer integration using Group Policy</span></span>

1. <span data-ttu-id="cb130-117">最新の [Microsoft Edge ポリシー テンプレート](https://www.microsoft.com/en-us/edge/business/download)をダウンロードして使用します。</span><span class="sxs-lookup"><span data-stu-id="cb130-117">Download and use the latest [Microsoft Edge Policy Template](https://www.microsoft.com/en-us/edge/business/download).</span></span>
2. <span data-ttu-id="cb130-118">グループ ポリシー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="cb130-118">Open Group Policy Editor.</span></span>
3. <span data-ttu-id="cb130-119">**[コンピューターの構成]** > **[管理用テンプレート]** > **[Microsoft Edge]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb130-119">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
4. <span data-ttu-id="cb130-120">**[Internet Explorer 統合を構成する]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb130-120">Double-click **Configure Internet Explorer integration**.</span></span>
5. <span data-ttu-id="cb130-121">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb130-121">Select **Enabled**.</span></span>
6. <span data-ttu-id="cb130-122">**[オプション]** で、ドロップダウンの値を次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="cb130-122">Under **Options**, set the dropdown value to</span></span> 
   -  <span data-ttu-id="cb130-123">**[Internet Explorer モード]**: サイトを Microsoft Edge の IE モードで開く場合</span><span class="sxs-lookup"><span data-stu-id="cb130-123">**Internet Explorer mode** if you want sites to open in IE mode on Microsoft Edge</span></span>
   -  <span data-ttu-id="cb130-124">**[Internet Explorer 11]**: サイトをスタンドアロンの Internet Explorer 11 のウィンドウで開く場合</span><span class="sxs-lookup"><span data-stu-id="cb130-124">**Internet Explorer 11** if you want sites to open in a standalone Internet Explorer 11 window</span></span>
   -  <span data-ttu-id="cb130-125">**[なし]**: ユーザーが edge://flags またはコマンド ラインを使用して Internet Explorer モードを構成できないようにする場合</span><span class="sxs-lookup"><span data-stu-id="cb130-125">**None** if you want to stop users from configuring Internet Explorer mode via edge://flags or through the command line</span></span>

   > [!NOTE]
   > <span data-ttu-id="cb130-126">このポリシーを **[無効]** に設定することは、IE モードがポリシーによって無効になることを意味していますが、IE モードは edge://flags またはコマンド ライン オプションを使用して設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="cb130-126">Setting the policy to **Disabled** implies IE mode is disabled by policy, but can be set through edge://flags or command line options.</span></span>
7. <span data-ttu-id="cb130-127">**[OK]** または **[適用]** をクリックして、このポリシー設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="cb130-127">Click **OK** or **Apply** to save this policy setting.</span></span>

## <span data-ttu-id="cb130-128">サイトを Microsoft Edge から IE モードにリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="cb130-128">Redirect sites from Microsoft Edge to IE mode</span></span>

<span data-ttu-id="cb130-129">IE モードで開くサイトを識別するには、次の2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="cb130-129">There are two options for identifying which sites should open in IE mode:</span></span>

- <span data-ttu-id="cb130-130">(推奨) [エンタープライズ サイト一覧のサイトを構成する](#configure-sites-on-the-enterprise-site-list)</span><span class="sxs-lookup"><span data-stu-id="cb130-130">(Recommended) [Configure sites on the Enterprise Site list](#configure-sites-on-the-enterprise-site-list)</span></span>
- [<span data-ttu-id="cb130-131">すべてのイントラネット サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="cb130-131">Configure all Intranet sites</span></span>](#configure-all-intranet-sites)

### <span data-ttu-id="cb130-132">エンタープライズ サイト一覧のサイトを構成する</span><span class="sxs-lookup"><span data-stu-id="cb130-132">Configure sites on the Enterprise Site list</span></span>

<span data-ttu-id="cb130-133">特定のサイトを IE モードで開くには、次のグループ ポリシーを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="cb130-133">You can use the following group policies to configure specific sites to open in IE mode:</span></span>

- <span data-ttu-id="cb130-134">[エンタープライズ モードの IE Web サイト一覧を使う](#configure-using-the-use-the-enterprise-mode-ie-website-list-policy) (Internet Explorer)</span><span class="sxs-lookup"><span data-stu-id="cb130-134">[Use the Enterprise Mode IE website list](#configure-using-the-use-the-enterprise-mode-ie-website-list-policy) (Internet Explorer)</span></span>
- <span data-ttu-id="cb130-135">[エンタープライズ モード サイト一覧を構成する](#configure-using-the-configure-the-enterprise-mode-site-list-policy) (Microsoft Edge version 78 以降)</span><span class="sxs-lookup"><span data-stu-id="cb130-135">[Configure the Enterprise Mode Site List](#configure-using-the-configure-the-enterprise-mode-site-list-policy) (Microsoft Edge, version 78 or later)</span></span><br/><span data-ttu-id="cb130-136">このポリシーでは、Microsoft Edge に対して別個のエンタープライズ モード サイト リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cb130-136">This policy lets you create a separate Enterprise Mode Site list for Microsoft Edge.</span></span> <span data-ttu-id="cb130-137">このポリシーを有効にすると、[Internet Explorer 統合を構成する] が有効になっている場合に [エンタープライズ モードの IE Web サイト一覧を使う] ポリシーの設定がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="cb130-137">Enabling this policy overrides the settings in the "Use the Enterprise Mode IE website list" policy, if "Configure Internet Explorer integration" is enabled.</span></span> <span data-ttu-id="cb130-138">このポリシーを無効にした場合または構成しなかった場合、[Internet Explorer 統合を構成する] ポリシーの既定の動作には影響しません。</span><span class="sxs-lookup"><span data-stu-id="cb130-138">Disabling or not configuring this policy doesn't affect the default behavior of the "Configure Internet Explorer integration" policy.</span></span>
    > [!NOTE]
    > <span data-ttu-id="cb130-139">Microsoft Edge ポリシーの構成は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="cb130-139">It is not mandatory to configure the Microsoft Edge policy.</span></span> <span data-ttu-id="cb130-140">多くの組織では、これをオーバーライドとして使用します。これにより、最新のサイト リストで IE ポリシーが有効なすべてのユーザーを対象とし、より簡単に更新バージョンを対象として Microsoft Edge ポリシーの使用をパイロットすることができます。</span><span class="sxs-lookup"><span data-stu-id="cb130-140">Many organizations use this as an override, allowing them to target the current Site List at all users with the IE policy, and more easily target an updated version to pilot uses with the Microsoft Edge policy.</span></span>

<span data-ttu-id="cb130-141">エンタープライズ モード サイト一覧について詳しくは、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cb130-141">For more information about Enterprise Mode Site lists, see:</span></span>

- [<span data-ttu-id="cb130-142">Enterprise Mode Site List Manager の使用</span><span class="sxs-lookup"><span data-stu-id="cb130-142">Use the Enterprise Mode Site List Manager</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/use-the-enterprise-mode-site-list-manager)
- <span data-ttu-id="cb130-143">[ファイルと Enterprise Mode Site List Manager (スキーマ v.2) を使ってエンタープライズ モード サイト一覧に複数のサイトを追加する](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/add-multiple-sites-to-enterprise-mode-site-list-using-the-version-2-schema-and-enterprise-mode-tool)</span><span class="sxs-lookup"><span data-stu-id="cb130-143">[Add multiple sites to the Enterprise Mode site list using a file and the Enterprise Mode Site List Manager (schema v.2)](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/add-multiple-sites-to-enterprise-mode-site-list-using-the-version-2-schema-and-enterprise-mode-tool).</span></span>

### <span data-ttu-id="cb130-144">[エンタープライズ モードの IE Web サイト一覧を使う] ポリシーの使用を構成する</span><span class="sxs-lookup"><span data-stu-id="cb130-144">Configure using the Use the Enterprise Mode IE website list policy</span></span>

<span data-ttu-id="cb130-145">IE モードでは、Internet Explorer のエンタープライズ サイト リストを構成する既存のポリシーを使用して、単一のリストを作成し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="cb130-145">IE mode can use the existing policy configuring the Enterprise Site List for Internet Explorer, allowing you to create and maintain a single list.</span></span>

1. <span data-ttu-id="cb130-146">サイト リスト XML を作成または再利用します。</span><span class="sxs-lookup"><span data-stu-id="cb130-146">Create or reuse a Site List XML</span></span>
    1. <span data-ttu-id="cb130-147">要素 _\<open-in\>IE11\</open-in\>_ が含まれているすべてのサイトが IE モードで開くようになります。</span><span class="sxs-lookup"><span data-stu-id="cb130-147">All sites that have the element _\<open-in\>IE11\</open-in\>_ will now open in IE mode.</span></span>
2. <span data-ttu-id="cb130-148">グループ ポリシー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="cb130-148">Open Group Policy Editor.</span></span>
3. <span data-ttu-id="cb130-149">**[コンピューターの構成]** > **[管理用テンプレート]** > **[Windows コンポーネント]** > **[Internet Explorer]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb130-149">Click **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Internet Explorer**.</span></span>
4. <span data-ttu-id="cb130-150">**[エンタープライズ モードの IE Web サイト一覧を使う]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb130-150">Double-click **Use the Enterprise Mode IE website list**.</span></span>
5. <span data-ttu-id="cb130-151">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb130-151">Select **Enabled**.</span></span>
6. <span data-ttu-id="cb130-152">**[オプション]** で、Web サイト一覧の場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="cb130-152">Under **Options**, type the location of website list.</span></span> <span data-ttu-id="cb130-153">次のいずれかの場所を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb130-153">You can use one of the following locations:</span></span>
    - <span data-ttu-id="cb130-154">(推奨) HTTPS の場所: **https**:**//iemode/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="cb130-154">(Recommended) HTTPS location: **https**:**//iemode/sites.xml**</span></span>
    - <span data-ttu-id="cb130-155">ローカル ネットワーク ファイル: **\\\network\shares\sites.xml**</span><span class="sxs-lookup"><span data-stu-id="cb130-155">Local network file: **\\\network\shares\sites.xml**</span></span>
    - <span data-ttu-id="cb130-156">ローカル ファイル: **file:///c:/Users/\<user\>/Documents/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="cb130-156">Local file: **file:///c:/Users/\<user\>/Documents/sites.xml**</span></span>
7. <span data-ttu-id="cb130-157">**[OK]** または **[適用]** をクリックして、これらの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="cb130-157">Click **OK** or **Apply** to save these settings.</span></span>

### <span data-ttu-id="cb130-158">[エンタープライズ モード サイト リストを構成する] ポリシーの使用を構成する</span><span class="sxs-lookup"><span data-stu-id="cb130-158">Configure using the Configure the Enterprise Mode Site List policy</span></span>

<span data-ttu-id="cb130-159">Microsoft Edge に対して別個のポリシーを使用して IE モードを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="cb130-159">You can also configure IE mode with a separate policy for Microsoft Edge.</span></span> <span data-ttu-id="cb130-160">この追加のポリシーを使用すると、IE サイト リストをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="cb130-160">This additional policy allows you to override the IE site list.</span></span> <span data-ttu-id="cb130-161">たとえば、一部の組織は、生産サイト リストの対象をすべてのユーザーにします。</span><span class="sxs-lookup"><span data-stu-id="cb130-161">For example, some organizations will target the production site list to all users.</span></span> <span data-ttu-id="cb130-162">その後、このポリシーを使用して、パイロット サイト リストを少数のユーザー グループに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="cb130-162">You can then deploy the pilot site list to a small group of users using this policy.</span></span>

1. <span data-ttu-id="cb130-163">サイト リスト XML を作成または再利用します。</span><span class="sxs-lookup"><span data-stu-id="cb130-163">Create or reuse a Site List XML</span></span>
    1. <span data-ttu-id="cb130-164">要素 _\<open-in\>IE11\</open-in\>_ が含まれているすべてのサイトが IE モードで開くようになります。</span><span class="sxs-lookup"><span data-stu-id="cb130-164">All sites that have the element _\<open-in\>IE11\</open-in\>_ will now open in IE mode.</span></span>
2. <span data-ttu-id="cb130-165">グループ ポリシー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="cb130-165">Open Group Policy Editor.</span></span>
3. <span data-ttu-id="cb130-166">**[コンピューターの構成]** > **[管理用テンプレート]** > **[Microsoft Edge]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb130-166">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
4. <span data-ttu-id="cb130-167">**[エンタープライズ モード サイト一覧を構成する]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb130-167">Double-click **Configure the Enterprise Mode Site List**.</span></span>
5. <span data-ttu-id="cb130-168">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb130-168">Select **Enabled**.</span></span>
6. <span data-ttu-id="cb130-169">**[オプション]** で、Web サイト一覧の場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="cb130-169">Under **Options**, type the location of website list.</span></span> <span data-ttu-id="cb130-170">次のいずれかの場所を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb130-170">You can use one of the following locations:</span></span>
    - <span data-ttu-id="cb130-171">(推奨) HTTPS の場所: **https**:**//iemode/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="cb130-171">(Recommended) HTTPS location: **https**:**//iemode/sites.xml**</span></span> <!--Trying to keep this from being an active link in MD -->
    - <span data-ttu-id="cb130-172">ローカル ネットワーク ファイル: **\\\network\shares\sites.xml**</span><span class="sxs-lookup"><span data-stu-id="cb130-172">Local network file: **\\\network\shares\sites.xml**</span></span>
    - <span data-ttu-id="cb130-173">ローカル ファイル: **file:///c:/Users/\<user\>/Documents/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="cb130-173">Local file: **file:///c:/Users/\<user\>/Documents/sites.xml**</span></span>
7. <span data-ttu-id="cb130-174">**[OK]** または **[適用]** をクリックして、これらの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="cb130-174">Click **OK** or **Apply** to save these settings.</span></span>

### <span data-ttu-id="cb130-175">すべてのイントラネット サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="cb130-175">Configure all intranet sites</span></span>

<span data-ttu-id="cb130-176">IE モードは、ローカル イントラネット ゾーンのすべてのサイトに対して構成できます。</span><span class="sxs-lookup"><span data-stu-id="cb130-176">IE mode can be configured as for all sites in the Local Intranet zone.</span></span> <span data-ttu-id="cb130-177">エンタープライズ モード サイト リストを使用して、個々のサイトを IE モードから削除できます。</span><span class="sxs-lookup"><span data-stu-id="cb130-177">You can remove individual sites from IE mode using an Enterprise Mode Site List.</span></span>

>[!NOTE]
>
> <span data-ttu-id="cb130-178">ローカル イントラネット ゾーンには明示的に追加されたサイトが含まれますが、ヒューリスティックを使用してサイトをこのゾーンに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cb130-178">The Local Intranet zone contains explicitly added sites, but also assigns sites to this zone using heuristics.</span></span> <span data-ttu-id="cb130-179">これには、ドットなしのホスト名 (**https**:**//payroll** など) や、プロキシ構成スクリプトでプロキシをバイパスするように構成されているサイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cb130-179">This can include dotless host names (e.g. **https**:**//payroll**) and sites that the proxy configuration script configures to bypass the proxy.</span></span> <span data-ttu-id="cb130-180">外部関係者が DNS またはプロキシを制御している場合、Web サイトを強制的に IE モードにする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cb130-180">If an external party controls DNS or proxy, they could potentially force websites into IE mode.</span></span>

1. <span data-ttu-id="cb130-181">ローカル グループ ポリシー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="cb130-181">Open Local Group Policy Editor.</span></span>
2. <span data-ttu-id="cb130-182">**[コンピューターの構成]** > **[管理用テンプレート]** > **[Microsoft Edge]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb130-182">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
3. <span data-ttu-id="cb130-183">**[すべてのイントラネット サイトを Internet Explorer に送る]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb130-183">Double-click **Send all intranet sites to Internet Explorer**.</span></span>
4. <span data-ttu-id="cb130-184">**[有効]** を選択し、**[OK]** または **[適用]** をクリックしてポリシー設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="cb130-184">Select **Enabled**, and then click **OK** or **Apply** to save the policy settings.</span></span>

## <span data-ttu-id="cb130-185">サイトを IE から Microsoft Edge にリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="cb130-185">Redirect sites from IE to Microsoft Edge</span></span>

<span data-ttu-id="cb130-186">Internet Explorer を必要としないサイトで、ユーザーが Internet Explorer を使用できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cb130-186">You can prevent your users from using Internet Explorer for sites that don't need it.</span></span> <span data-ttu-id="cb130-187">サイト リストにないサイトの場合、Internet Explorer ではそのサイトを自動的に Microsoft Edge にリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="cb130-187">Internet Explorer can automatically redirect sites to Microsoft Edge if they aren't on your site list.</span></span>

1. <span data-ttu-id="cb130-188">グループ ポリシー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="cb130-188">Open Group Policy Editor.</span></span>
2. <span data-ttu-id="cb130-189">**[コンピューターの構成]** > **[管理ツール]** > **[Windows コンポーネント]** > **[Internet Explorer]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb130-189">Click **Computer Configuration** > **Administrative Tools** > **Windows Components** > **Internet Explorer**.</span></span>
3. <span data-ttu-id="cb130-190">**[エンタープライズ モード サイト一覧に含まれていないすべてのサイトを Microsoft Edge に送信します]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb130-190">Double-click **Send all sites not included in the Enterprise Mode Site List to Microsoft Edge.**</span></span>
4. <span data-ttu-id="cb130-191">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb130-191">Select **Enabled**</span></span>
5. <span data-ttu-id="cb130-192">**[OK]** または **[適用]** をクリックして、これらの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="cb130-192">Click **OK** or **Apply** to save these settings.</span></span>
6. <span data-ttu-id="cb130-193">**[リダイレクトされたサイトを開くときに使用する Microsoft Edge のチャネルを構成する]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb130-193">Double-click **Configure which channel of Microsoft Edge to use for opening redirected sites**.</span></span>
7. <span data-ttu-id="cb130-194">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb130-194">Select **Enabled**.</span></span>
8. <span data-ttu-id="cb130-195">**[オプション]** で、使用する上位 3 つのチャネルを選択します。Internet Explorer では、ユーザーがデバイスにインストールした、最も高くランク付けされたチャネルにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="cb130-195">Under **Options**, select your top three choices for the channel to use - Internet Explorer will redirect to the highest ranked choice that the user has installed on that device:</span></span>
   - <span data-ttu-id="cb130-196">Microsoft Edge Stable</span><span class="sxs-lookup"><span data-stu-id="cb130-196">Microsoft Edge Stable</span></span>
   - <span data-ttu-id="cb130-197">Microsoft Edge Beta バージョン 77 以降</span><span class="sxs-lookup"><span data-stu-id="cb130-197">Microsoft Edge Beta version 77 or later</span></span>
   - <span data-ttu-id="cb130-198">Microsoft Edge Dev バージョン 77 以降</span><span class="sxs-lookup"><span data-stu-id="cb130-198">Microsoft Edge Dev version 77 or later</span></span>
   - <span data-ttu-id="cb130-199">Microsoft Edge Canary バージョン 77 以降</span><span class="sxs-lookup"><span data-stu-id="cb130-199">Microsoft Edge Canary version 77 or later</span></span>
   - <span data-ttu-id="cb130-200">Microsoft Edge バージョン 45 以前</span><span class="sxs-lookup"><span data-stu-id="cb130-200">Microsoft Edge version 45 or earlier</span></span>
9. <span data-ttu-id="cb130-201">**[OK]** または **[適用]** をクリックして、これらの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="cb130-201">Click **OK** or **Apply** to save these settings.</span></span>

## <span data-ttu-id="cb130-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb130-202">See also</span></span>

- [<span data-ttu-id="cb130-203">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="cb130-203">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="cb130-204">IE モードの概要</span><span class="sxs-lookup"><span data-stu-id="cb130-204">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="cb130-205">その他のエンタープライズ モード情報</span><span class="sxs-lookup"><span data-stu-id="cb130-205">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)