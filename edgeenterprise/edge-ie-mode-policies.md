---
title: IE モード ポリシーの構成
ms.author: collw
author: AndreaLBarr
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: IE モード ポリシーの構成
ms.openlocfilehash: 57d0db97a96baf361f88ca8ec90812373440c3d8
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641473"
---
# <a name="configure-ie-mode-policies"></a><span data-ttu-id="fb14c-103">IE モード ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="fb14c-103">Configure IE mode policies</span></span>

>[!Note]
> <span data-ttu-id="fb14c-104">Internet Explorer 11 デスクトップ アプリケーションは廃止され、2022 年 6 月 15 日にサポートが終了します (スコープ内の一覧については、[FAQ を参照してください](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549))。</span><span class="sxs-lookup"><span data-stu-id="fb14c-104">The Internet Explorer 11 desktop application will be retired and go out of support on June 15, 2022 (for a list of what’s in scope, [see the FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span></span> <span data-ttu-id="fb14c-105">現在使用しているものと同じ IE11 アプリとサイトを、Internet Explorer モードの Microsoft Edge で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-105">The same IE11 apps and sites you use today can open in Microsoft Edge with Internet Explorer mode.</span></span> <span data-ttu-id="fb14c-106">[こちらをご覧ください](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。</span><span class="sxs-lookup"><span data-stu-id="fb14c-106">[Learn more here](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span></span>

<span data-ttu-id="fb14c-107">この記事では、IE モード ポリシーの構成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-107">This article explains how to configure IE mode policies.</span></span>

> [!NOTE]
> <span data-ttu-id="fb14c-108">この記事は、Microsoft Edge version 77 (**Stable**、**Beta**、および **Dev** チャネル) 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-108">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>

<span data-ttu-id="fb14c-109">IE モードを構成するには、次の3つの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb14c-109">Configuring IE mode requires three steps:</span></span>

1. [<span data-ttu-id="fb14c-110">Internet Explorer 統合を構成する</span><span class="sxs-lookup"><span data-stu-id="fb14c-110">Configure Internet Explorer integration</span></span>](#configure-internet-explorer-integration)
2. [<span data-ttu-id="fb14c-111">サイトを Microsoft Edge から IE モードにリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="fb14c-111">Redirect sites from Microsoft Edge to IE mode</span></span>](#redirect-sites-from-microsoft-edge-to-ie-mode)
3. <span data-ttu-id="fb14c-112">(省略可能) [サイトを IE から Microsoft Edge にリダイレクトする](#redirect-sites-from-ie-to-microsoft-edge)</span><span class="sxs-lookup"><span data-stu-id="fb14c-112">(Optional) [Redirect sites from IE to Microsoft Edge](#redirect-sites-from-ie-to-microsoft-edge)</span></span>

    1. <span data-ttu-id="fb14c-113">IE11 アプリを無効にする準備ができている場合は、「[Internet Explorer 11 を無効にする](/deployedge/edge-ie-disable-ie11)」の手順に従います</span><span class="sxs-lookup"><span data-stu-id="fb14c-113">If you are ready to disable the IE11 app, follow the steps in [Disable Internet Explorer 11](/deployedge/edge-ie-disable-ie11)</span></span>
    2. <span data-ttu-id="fb14c-114">それ以外の場合は、「[サイトを IE から Microsoft Edge にリダイレクトする](/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge)」の残りの手順に従います</span><span class="sxs-lookup"><span data-stu-id="fb14c-114">Otherwise,  follow the rest of the steps in [Redirect sites from IE to Microsoft Edge](/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge)</span></span>

> [!NOTE]
> <span data-ttu-id="fb14c-115">IE モードを有効にするポリシーは、Intune を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-115">Policies to enable IE mode can be configured through Intune.</span></span> <span data-ttu-id="fb14c-116">詳しくは、「[Microsoft Edge for Windows 10 を Microsoft Intune に追加する](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)」および「[Microsoft Intune を使って Microsoft Edge ポリシー設定を構成する](./configure-edge-with-intune.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fb14c-116">For more information, see [Add Microsoft Edge to Microsoft Intune](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json) and [Configure Microsoft Edge policies with Microsoft Intune](./configure-edge-with-intune.md).</span></span>

## <a name="configure-internet-explorer-integration"></a><span data-ttu-id="fb14c-117">Internet Explorer 統合を構成する</span><span class="sxs-lookup"><span data-stu-id="fb14c-117">Configure Internet Explorer integration</span></span>

<span data-ttu-id="fb14c-118">Microsoft Edge (IE モード) 内で直接開くように、Internet Explorer を構成できます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-118">You can configure Internet Explorer to open directly within Microsoft Edge (IE mode).</span></span> <span data-ttu-id="fb14c-119">スタンドアロンの Internet Explorer 11 ウィンドウで開くように、Internet Explorer を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-119">You can also configure Internet Explorer to open with a standalone Internet Explorer 11 window.</span></span> <span data-ttu-id="fb14c-120">ほとんどのユーザーは、Microsoft Edge の IE モードでサイトを直接開くことを希望します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-120">Most users prefer when sites open directly within Microsoft Edge in IE mode.</span></span>

### <a name="enable-internet-explorer-integration-using-group-policy"></a><span data-ttu-id="fb14c-121">グループ ポリシーを使用して Internet Explorer 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="fb14c-121">Enable Internet Explorer integration using Group Policy</span></span>

1. <span data-ttu-id="fb14c-122">最新の [Microsoft Edge ポリシー テンプレート](https://www.microsoft.com/en-us/edge/business/download)をダウンロードして使用します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-122">Download and use the latest [Microsoft Edge Policy Template](https://www.microsoft.com/en-us/edge/business/download).</span></span>
2. <span data-ttu-id="fb14c-123">グループ ポリシー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-123">Open Group Policy Editor.</span></span>
3. <span data-ttu-id="fb14c-124">**[ユーザーの構成/コンピューターの構成]** > **[管理用テンプレート]** > **[Microsoft Edge]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb14c-124">Click **User Configuration/Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
4. <span data-ttu-id="fb14c-125">**[Internet Explorer 統合を構成する]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb14c-125">Double-click **Configure Internet Explorer integration**.</span></span>
5. <span data-ttu-id="fb14c-126">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-126">Select **Enabled**.</span></span>
6. <span data-ttu-id="fb14c-127">**[オプション]** で、ドロップダウンの値を次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-127">Under **Options**, set the dropdown value to</span></span> 
   -  <span data-ttu-id="fb14c-128">**[Internet Explorer モード]**: サイトを Microsoft Edge の IE モードで開く場合</span><span class="sxs-lookup"><span data-stu-id="fb14c-128">**Internet Explorer mode** if you want sites to open in IE mode on Microsoft Edge</span></span>
   -  <span data-ttu-id="fb14c-129">**[Internet Explorer 11]**: サイトをスタンドアロンの Internet Explorer 11 のウィンドウで開く場合</span><span class="sxs-lookup"><span data-stu-id="fb14c-129">**Internet Explorer 11** if you want sites to open in a standalone Internet Explorer 11 window</span></span>
   -  <span data-ttu-id="fb14c-130">**[なし]**: ユーザーが edge://flags またはコマンド ラインを使用して Internet Explorer モードを構成できないようにする場合</span><span class="sxs-lookup"><span data-stu-id="fb14c-130">**None** if you want to stop users from configuring Internet Explorer mode via edge://flags or through the command line</span></span>

   > [!NOTE]
   > <span data-ttu-id="fb14c-131">このポリシーを **[無効]** に設定することは、IE モードがポリシーによって無効になることを意味していますが、IE モードは edge://flags またはコマンド ライン オプションを使用して設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-131">Setting the policy to **Disabled** implies IE mode is disabled by policy, but can be set through edge://flags or command line options.</span></span>
7. <span data-ttu-id="fb14c-132">**[OK]** または **[適用]** をクリックして、このポリシー設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-132">Click **OK** or **Apply** to save this policy setting.</span></span>

## <a name="redirect-sites-from-microsoft-edge-to-ie-mode"></a><span data-ttu-id="fb14c-133">サイトを Microsoft Edge から IE モードにリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="fb14c-133">Redirect sites from Microsoft Edge to IE mode</span></span>

<span data-ttu-id="fb14c-134">IE モードで開くサイトを識別するには、次の2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="fb14c-134">There are two options for identifying which sites should open in IE mode:</span></span>

- <span data-ttu-id="fb14c-135">(推奨) [エンタープライズ サイト一覧のサイトを構成する](#configure-sites-on-the-enterprise-site-list)</span><span class="sxs-lookup"><span data-stu-id="fb14c-135">(Recommended) [Configure sites on the Enterprise Site list](#configure-sites-on-the-enterprise-site-list)</span></span>
- [<span data-ttu-id="fb14c-136">すべてのイントラネット サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="fb14c-136">Configure all Intranet sites</span></span>](#configure-all-intranet-sites)

### <a name="configure-sites-on-the-enterprise-site-list"></a><span data-ttu-id="fb14c-137">エンタープライズ サイト一覧のサイトを構成する</span><span class="sxs-lookup"><span data-stu-id="fb14c-137">Configure sites on the Enterprise Site list</span></span>

<span data-ttu-id="fb14c-138">特定のサイトを IE モードで開くには、次のグループ ポリシーを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-138">You can use the following group policies to configure specific sites to open in IE mode:</span></span>

- <span data-ttu-id="fb14c-139">[エンタープライズ モードの IE Web サイト一覧を使う](#configure-using-the-use-the-enterprise-mode-ie-website-list-policy) (Internet Explorer)</span><span class="sxs-lookup"><span data-stu-id="fb14c-139">[Use the Enterprise Mode IE website list](#configure-using-the-use-the-enterprise-mode-ie-website-list-policy) (Internet Explorer)</span></span>
- <span data-ttu-id="fb14c-140">[エンタープライズ モード サイト一覧を構成する](#configure-using-the-configure-the-enterprise-mode-site-list-policy) (Microsoft Edge version 78 以降)</span><span class="sxs-lookup"><span data-stu-id="fb14c-140">[Configure the Enterprise Mode Site List](#configure-using-the-configure-the-enterprise-mode-site-list-policy) (Microsoft Edge, version 78 or later)</span></span><br/><span data-ttu-id="fb14c-141">このポリシーでは、Microsoft Edge に対して別個のエンタープライズ モード サイト リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-141">This policy lets you create a separate Enterprise Mode Site list for Microsoft Edge.</span></span> <span data-ttu-id="fb14c-142">このポリシーを有効にすると、[Internet Explorer 統合を構成する] が有効になっている場合に [エンタープライズ モードの IE Web サイト一覧を使う] ポリシーの設定がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-142">Enabling this policy overrides the settings in the "Use the Enterprise Mode IE website list" policy, if "Configure Internet Explorer integration" is enabled.</span></span> <span data-ttu-id="fb14c-143">このポリシーを無効にした場合または構成しなかった場合、[Internet Explorer 統合を構成する] ポリシーの既定の動作には影響しません。</span><span class="sxs-lookup"><span data-stu-id="fb14c-143">Disabling or not configuring this policy doesn't affect the default behavior of the "Configure Internet Explorer integration" policy.</span></span>
    > [!NOTE]
    > <span data-ttu-id="fb14c-144">Microsoft Edge ポリシーの構成は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="fb14c-144">It is not mandatory to configure the Microsoft Edge policy.</span></span> <span data-ttu-id="fb14c-145">多くの組織では、これをオーバーライドとして使用します。これにより、最新のサイト リストで IE ポリシーが有効なすべてのユーザーを対象とし、より簡単に更新バージョンを対象として Microsoft Edge ポリシーの使用をパイロットすることができます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-145">Many organizations use this as an override, allowing them to target the current Site List at all users with the IE policy, and more easily target an updated version to pilot uses with the Microsoft Edge policy.</span></span>

<span data-ttu-id="fb14c-146">エンタープライズ モード サイト一覧について詳しくは、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fb14c-146">For more information about Enterprise Mode Site lists, see:</span></span>

- [<span data-ttu-id="fb14c-147">Enterprise Mode Site List Manager の使用</span><span class="sxs-lookup"><span data-stu-id="fb14c-147">Use the Enterprise Mode Site List Manager</span></span>](/internet-explorer/ie11-deploy-guide/use-the-enterprise-mode-site-list-manager)
- <span data-ttu-id="fb14c-148">[ファイルと Enterprise Mode Site List Manager (スキーマ v.2) を使ってエンタープライズ モード サイト一覧に複数のサイトを追加する](/internet-explorer/ie11-deploy-guide/add-multiple-sites-to-enterprise-mode-site-list-using-the-version-2-schema-and-enterprise-mode-tool)</span><span class="sxs-lookup"><span data-stu-id="fb14c-148">[Add multiple sites to the Enterprise Mode site list using a file and the Enterprise Mode Site List Manager (schema v.2)](/internet-explorer/ie11-deploy-guide/add-multiple-sites-to-enterprise-mode-site-list-using-the-version-2-schema-and-enterprise-mode-tool).</span></span>

### <a name="configure-using-the-use-the-enterprise-mode-ie-website-list-policy"></a><span data-ttu-id="fb14c-149">[エンタープライズ モードの IE Web サイト一覧を使う] ポリシーの使用を構成する</span><span class="sxs-lookup"><span data-stu-id="fb14c-149">Configure using the Use the Enterprise Mode IE website list policy</span></span>

<span data-ttu-id="fb14c-150">IE モードでは、Internet Explorer のエンタープライズ サイト リストを構成する既存のポリシーを使用して、単一のリストを作成し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-150">IE mode can use the existing policy configuring the Enterprise Site List for Internet Explorer, allowing you to create and maintain a single list.</span></span>

1. <span data-ttu-id="fb14c-151">サイト リスト XML を作成または再利用します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-151">Create or reuse a Site List XML</span></span>
    1. <span data-ttu-id="fb14c-152">要素 _\<open-in\>IE11\</open-in\>_ が含まれているすべてのサイトが IE モードで開くようになります。</span><span class="sxs-lookup"><span data-stu-id="fb14c-152">All sites that have the element _\<open-in\>IE11\</open-in\>_ will now open in IE mode.</span></span>
2. <span data-ttu-id="fb14c-153">グループ ポリシー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-153">Open Group Policy Editor.</span></span>
3. <span data-ttu-id="fb14c-154">**[ユーザーの構成/コンピューターの構成]** > **[管理用テンプレート]** > **[Windows コンポーネント]** > **[Internet Explorer]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb14c-154">Click **User Configuration/Computer Configuration** > **Administrative Templates** > **Windows Components** > **Internet Explorer**.</span></span>
4. <span data-ttu-id="fb14c-155">**[エンタープライズ モードの IE Web サイト一覧を使う]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb14c-155">Double-click **Use the Enterprise Mode IE website list**.</span></span>
5. <span data-ttu-id="fb14c-156">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-156">Select **Enabled**.</span></span>
6. <span data-ttu-id="fb14c-157">**[オプション]** で、Web サイト一覧の場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-157">Under **Options**, type the location of website list.</span></span> <span data-ttu-id="fb14c-158">次のいずれかの場所を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-158">You can use one of the following locations:</span></span>
    - <span data-ttu-id="fb14c-159">(推奨) HTTPS の場所: **https**:**//iemode/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="fb14c-159">(Recommended) HTTPS location: **https**:**//iemode/sites.xml**</span></span>
    - <span data-ttu-id="fb14c-160">ローカル ネットワーク ファイル: **\\\network\shares\sites.xml**</span><span class="sxs-lookup"><span data-stu-id="fb14c-160">Local network file: **\\\network\shares\sites.xml**</span></span>
    - <span data-ttu-id="fb14c-161">ローカル ファイル: **file:///c:/Users/\<user\>/Documents/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="fb14c-161">Local file: **file:///c:/Users/\<user\>/Documents/sites.xml**</span></span>
7. <span data-ttu-id="fb14c-162">**[OK]** または **[適用]** をクリックして、これらの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-162">Click **OK** or **Apply** to save these settings.</span></span>

### <a name="configure-using-the-configure-the-enterprise-mode-site-list-policy"></a><span data-ttu-id="fb14c-163">[エンタープライズ モード サイト リストを構成する] ポリシーの使用を構成する</span><span class="sxs-lookup"><span data-stu-id="fb14c-163">Configure using the Configure the Enterprise Mode Site List policy</span></span>

<span data-ttu-id="fb14c-164">Microsoft Edge に対して別個のポリシーを使用して IE モードを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-164">You can also configure IE mode with a separate policy for Microsoft Edge.</span></span> <span data-ttu-id="fb14c-165">この追加のポリシーを使用すると、IE サイト リストをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-165">This additional policy allows you to override the IE site list.</span></span> <span data-ttu-id="fb14c-166">たとえば、一部の組織は、生産サイト リストの対象をすべてのユーザーにします。</span><span class="sxs-lookup"><span data-stu-id="fb14c-166">For example, some organizations will target the production site list to all users.</span></span> <span data-ttu-id="fb14c-167">その後、このポリシーを使用して、パイロット サイト リストを少数のユーザー グループに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-167">You can then deploy the pilot site list to a small group of users using this policy.</span></span>

1. <span data-ttu-id="fb14c-168">サイト リスト XML を作成または再利用します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-168">Create or reuse a Site List XML</span></span>
    1. <span data-ttu-id="fb14c-169">要素 _\<open-in\>IE11\</open-in\>_ が含まれているすべてのサイトが IE モードで開くようになります。</span><span class="sxs-lookup"><span data-stu-id="fb14c-169">All sites that have the element _\<open-in\>IE11\</open-in\>_ will now open in IE mode.</span></span>
2. <span data-ttu-id="fb14c-170">グループ ポリシー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-170">Open Group Policy Editor.</span></span>
3. <span data-ttu-id="fb14c-171">**[ユーザーの構成/コンピューターの構成]** > **[管理用テンプレート]** > **[Microsoft Edge]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb14c-171">Click **User Configuration/Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
4. <span data-ttu-id="fb14c-172">**[エンタープライズ モード サイト一覧を構成する]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb14c-172">Double-click **Configure the Enterprise Mode Site List**.</span></span>
5. <span data-ttu-id="fb14c-173">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-173">Select **Enabled**.</span></span>
6. <span data-ttu-id="fb14c-174">**[オプション]** で、Web サイト一覧の場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-174">Under **Options**, type the location of website list.</span></span> <span data-ttu-id="fb14c-175">次のいずれかの場所を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-175">You can use one of the following locations:</span></span>
    - <span data-ttu-id="fb14c-176">(推奨) HTTPS の場所: **https**:**//iemode/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="fb14c-176">(Recommended) HTTPS location: **https**:**//iemode/sites.xml**</span></span> <!--Trying to keep this from being an active link in MD -->
    - <span data-ttu-id="fb14c-177">ローカル ネットワーク ファイル: **\\\network\shares\sites.xml**</span><span class="sxs-lookup"><span data-stu-id="fb14c-177">Local network file: **\\\network\shares\sites.xml**</span></span>
    - <span data-ttu-id="fb14c-178">ローカル ファイル: **file:///c:/Users/\<user\>/Documents/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="fb14c-178">Local file: **file:///c:/Users/\<user\>/Documents/sites.xml**</span></span>
7. <span data-ttu-id="fb14c-179">**[OK]** または **[適用]** をクリックして、これらの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-179">Click **OK** or **Apply** to save these settings.</span></span>

### <a name="configure-all-intranet-sites"></a><span data-ttu-id="fb14c-180">すべてのイントラネット サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="fb14c-180">Configure all intranet sites</span></span>

<span data-ttu-id="fb14c-181">IE モードは、ローカル イントラネット ゾーンのすべてのサイトに対して構成できます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-181">IE mode can be configured as for all sites in the Local Intranet zone.</span></span> <span data-ttu-id="fb14c-182">エンタープライズ モード サイト リストを使用して、個々のサイトを IE モードから削除できます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-182">You can remove individual sites from IE mode using an Enterprise Mode Site List.</span></span>

>[!NOTE]
>
> <span data-ttu-id="fb14c-183">ローカル イントラネット ゾーンには明示的に追加されたサイトが含まれますが、ヒューリスティックを使用してサイトをこのゾーンに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-183">The Local Intranet zone contains explicitly added sites, but also assigns sites to this zone using heuristics.</span></span> <span data-ttu-id="fb14c-184">これには、ドットなしのホスト名 (**https**:**//payroll** など) や、プロキシ構成スクリプトでプロキシをバイパスするように構成されているサイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-184">This can include dotless host names (e.g. **https**:**//payroll**) and sites that the proxy configuration script configures to bypass the proxy.</span></span> <span data-ttu-id="fb14c-185">外部関係者が DNS またはプロキシを制御している場合、Web サイトを強制的に IE モードにする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fb14c-185">If an external party controls DNS or proxy, they could potentially force websites into IE mode.</span></span>

1. <span data-ttu-id="fb14c-186">ローカル グループ ポリシー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-186">Open Local Group Policy Editor.</span></span>
2. <span data-ttu-id="fb14c-187">**[ユーザーの構成/コンピューターの構成]** > **[管理用テンプレート]** > **[Microsoft Edge]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb14c-187">Click **User Configuration/Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
3. <span data-ttu-id="fb14c-188">**[すべてのイントラネット サイトを Internet Explorer に送る]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb14c-188">Double-click **Send all intranet sites to Internet Explorer**.</span></span>
4. <span data-ttu-id="fb14c-189">**[有効]** を選択し、**[OK]** または **[適用]** をクリックしてポリシー設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-189">Select **Enabled**, and then click **OK** or **Apply** to save the policy settings.</span></span>

## <a name="redirect-sites-from-ie-to-microsoft-edge"></a><span data-ttu-id="fb14c-190">サイトを IE から Microsoft Edge にリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="fb14c-190">Redirect sites from IE to Microsoft Edge</span></span>

<span data-ttu-id="fb14c-191">Internet Explorer を必要としないサイトで、ユーザーが Internet Explorer を使用できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-191">You can prevent your users from using Internet Explorer for sites that don't need it.</span></span> <span data-ttu-id="fb14c-192">サイト リストにないサイトの場合、Internet Explorer ではそのサイトを自動的に Microsoft Edge にリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-192">Internet Explorer can automatically redirect sites to Microsoft Edge if they aren't on your site list.</span></span>

1. <span data-ttu-id="fb14c-193">グループ ポリシー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="fb14c-193">Open Group Policy Editor.</span></span>
2. <span data-ttu-id="fb14c-194">**[ユーザーの構成/コンピューターの構成]** > **[管理用ツール]** > **[Windows コンポーネント]** > **[Internet Explorer]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb14c-194">Click **User Configuration/Computer Configuration** > **Administrative Tools** > **Windows Components** > **Internet Explorer**.</span></span>
3. <span data-ttu-id="fb14c-195">**[エンタープライズ モード サイト一覧に含まれていないすべてのサイトを Microsoft Edge に送信します]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb14c-195">Double-click **Send all sites not included in the Enterprise Mode Site List to Microsoft Edge.**</span></span>
4. <span data-ttu-id="fb14c-196">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-196">Select **Enabled**</span></span>
5. <span data-ttu-id="fb14c-197">**[OK]** または **[適用]** をクリックして、これらの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-197">Click **OK** or **Apply** to save these settings.</span></span>
6. <span data-ttu-id="fb14c-198">**[リダイレクトされたサイトを開くときに使用する Microsoft Edge のチャネルを構成する]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb14c-198">Double-click **Configure which channel of Microsoft Edge to use for opening redirected sites**.</span></span>
7. <span data-ttu-id="fb14c-199">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-199">Select **Enabled**.</span></span>
8. <span data-ttu-id="fb14c-200">**[オプション]** で、使用する上位 3 つのチャネルを選択します。Internet Explorer では、ユーザーがデバイスにインストールした、最も高くランク付けされたチャネルにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="fb14c-200">Under **Options**, select your top three choices for the channel to use - Internet Explorer will redirect to the highest ranked choice that the user has installed on that device:</span></span>
   - <span data-ttu-id="fb14c-201">Microsoft Edge Stable</span><span class="sxs-lookup"><span data-stu-id="fb14c-201">Microsoft Edge Stable</span></span>
   - <span data-ttu-id="fb14c-202">Microsoft Edge Beta バージョン 77 以降</span><span class="sxs-lookup"><span data-stu-id="fb14c-202">Microsoft Edge Beta version 77 or later</span></span>
   - <span data-ttu-id="fb14c-203">Microsoft Edge Dev バージョン 77 以降</span><span class="sxs-lookup"><span data-stu-id="fb14c-203">Microsoft Edge Dev version 77 or later</span></span>
   - <span data-ttu-id="fb14c-204">Microsoft Edge Canary バージョン 77 以降</span><span class="sxs-lookup"><span data-stu-id="fb14c-204">Microsoft Edge Canary version 77 or later</span></span>
   - <span data-ttu-id="fb14c-205">Microsoft Edge バージョン 45 以前</span><span class="sxs-lookup"><span data-stu-id="fb14c-205">Microsoft Edge version 45 or earlier</span></span>
9. <span data-ttu-id="fb14c-206">**[OK]** または **[適用]** をクリックして、これらの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb14c-206">Click **OK** or **Apply** to save these settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb14c-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb14c-207">See also</span></span>

- [<span data-ttu-id="fb14c-208">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="fb14c-208">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="fb14c-209">IE モードの概要</span><span class="sxs-lookup"><span data-stu-id="fb14c-209">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="fb14c-210">その他のエンタープライズ モード情報</span><span class="sxs-lookup"><span data-stu-id="fb14c-210">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)