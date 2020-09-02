---
title: Microsoft Intune を使って Windows 用の Microsoft Edge ポリシー設定を構成する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/18/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Intune を使って Windows 用の Microsoft Edge ポリシー設定を構成します。
ms.openlocfilehash: 6200b52e9061f37f85fe0bfe7cf59a2172db97df
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980388"
---
# <span data-ttu-id="d6230-103">Microsoft Intune を使って Microsoft Edge ポリシー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="d6230-103">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>

<span data-ttu-id="d6230-104">この記事では、Microsoft Intune を使って Windows 10 用の Microsoft Edge ポリシー設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6230-104">This article explains how to configure Microsoft Edge policy settings for Windows 10 using Microsoft Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="d6230-105">この記事は Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d6230-105">This article applies to Microsoft Edge version 77 or later.</span></span>

<span data-ttu-id="d6230-106">デバイス構成プロファイルを Microsoft Intune に追加することで、Microsoft Edge のポリシーと設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d6230-106">You can configure Microsoft Edge policies and settings by adding a device configuration profile to Microsoft Intune.</span></span> <span data-ttu-id="d6230-107">Intune を使用してポリシーを管理および適用することは、Active Directory グループ ポリシーを使用するか、ユーザー デバイスでローカルのグループ ポリシー オブジェクト (GPO) 設定を構成することと同じです。</span><span class="sxs-lookup"><span data-stu-id="d6230-107">Using Intune to manage and enforce policies is equivalent to using Active Directory Group Policy or configuring local Group Policy Object (GPO) settings on user devices.</span></span>

<span data-ttu-id="d6230-108">Microsoft Intune を使用して Microsoft Edge ポリシーを管理する方法について詳しくは、「[Microsoft Edge と Microsoft Intune を使用して Web アクセスを管理する](https://docs.microsoft.com/intune/manage-microsoft-edge)」をご覧ください。ただし、この記事は Microsoft Edge version 45 以前を対象とした内容であるため、Microsoft Edge Enterprise version 77 以降に適用されない情報や参照が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="d6230-108">For more information about managing Microsoft Edge policies with Microsoft Intune, you can read [Manage web access by using Microsoft Edge with Microsoft Intune](https://docs.microsoft.com/intune/manage-microsoft-edge), but keep in mind that the linked article is specific to Microsoft Edge version 45 and earlier and therefore may contain information and references that don't apply to Microsoft Edge Enterprise version 77 and later.</span></span>

> [!TIP]
> <span data-ttu-id="d6230-109">Microsoft Intune を使用して macOS で Microsoft Edge を構成する方法については、[macOS 用の構成](configure-microsoft-edge-on-mac.md)に関する情報をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d6230-109">For information on how to configure Microsoft Edge on macOS using Microsoft Intune, see [Configure for macOS](configure-microsoft-edge-on-mac.md).</span></span>

## <span data-ttu-id="d6230-110">プロファイルを作成して Microsoft Edge for Windows 10 の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="d6230-110">Create a profile to manage settings in Microsoft Edge for Windows 10</span></span>

<span data-ttu-id="d6230-111">Microsoft Intune の管理用テンプレートを使用すると、クラウドを使用して Windows 10 デバイス上の Microsoft Edge グループ ポリシーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="d6230-111">Using Administrative Templates in Microsoft Intune, you can manage Microsoft Edge group policies on your Windows 10 devices using the cloud.</span></span> <span data-ttu-id="d6230-112">このセクションでは、Microsoft Edge 固有のアプリケーション設定を構成するためのテンプレートを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6230-112">This section will help you create a template to configure Microsoft Edge-specific application settings.</span></span> <span data-ttu-id="d6230-113">テンプレートを作成すると、デバイス構成プロファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d6230-113">When you create the template, it creates a device configuration profile.</span></span> <span data-ttu-id="d6230-114">このプロファイルは、組織内の Windows 10 デバイスに割り当てることも、展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="d6230-114">You can then assign or deploy this profile to Windows 10 devices in your organization.</span></span>

### <span data-ttu-id="d6230-115">前提条件</span><span class="sxs-lookup"><span data-stu-id="d6230-115">Prerequisites</span></span>

- <span data-ttu-id="d6230-116">以下の最小システム要件を満たす Windows 10:</span><span class="sxs-lookup"><span data-stu-id="d6230-116">Windows 10 with the following minimum system requirements:</span></span>
  - <span data-ttu-id="d6230-117">Windows 10 Version 1909</span><span class="sxs-lookup"><span data-stu-id="d6230-117">Windows 10, version 1909</span></span>
  - <span data-ttu-id="d6230-118">[KB4512941](https://support.microsoft.com/kb/4512941) をインストール済みの Windows 10 Version 1903</span><span class="sxs-lookup"><span data-stu-id="d6230-118">Windows 10, version 1903 with [KB4512941](https://support.microsoft.com/kb/4512941) installed</span></span>
  - <span data-ttu-id="d6230-119">[KB4512534](https://support.microsoft.com/kb/4512534) をインストール済みの Windows 10 Version 1809</span><span class="sxs-lookup"><span data-stu-id="d6230-119">Windows 10, version 1809 with [KB4512534](https://support.microsoft.com/kb/4512534) installed</span></span>
  - <span data-ttu-id="d6230-120">[KB4512509](https://support.microsoft.com/kb/4512509) をインストール済みの Windows 10 Version 1803</span><span class="sxs-lookup"><span data-stu-id="d6230-120">Windows 10, version 1803 with [KB4512509](https://support.microsoft.com/kb/4512509) installed</span></span>
  - <span data-ttu-id="d6230-121">[KB4516071](https://support.microsoft.com/kb/4516071) をインストール済みの Windows 10 Version 1709</span><span class="sxs-lookup"><span data-stu-id="d6230-121">Windows 10, version 1709 with [KB4516071](https://support.microsoft.com/kb/4516071) installed</span></span>

### <span data-ttu-id="d6230-122">管理用テンプレートを使用して Microsoft Edge のポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d6230-122">Use Administrative Templates to create a policy for Microsoft Edge</span></span>

<span data-ttu-id="d6230-123">この手順では、Intune に組み込まれた管理用テンプレート (グループポリシーで使い慣れているもの) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d6230-123">This procedure leverages Administrative templates (which you might be familiar with from Group Policy) that are built into Intune.</span></span> <span data-ttu-id="d6230-124">これらのテンプレートを使用して、事前に構成されたリストから設定を選択することによって、Microsoft Edge のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d6230-124">You can use these templates to create a policy for Microsoft Edge by selecting settings from a pre-configured list.</span></span>

1. <span data-ttu-id="d6230-125">[Microsoft エンドポイント マネージャー](https://endpoint.microsoft.com/) ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="d6230-125">Sign in to the [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) portal.</span></span>
2. <span data-ttu-id="d6230-126">ナビゲーション ウィンドウの左側にある [**デバイス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d6230-126">Select **Devices** in the left-hand navigation pane.</span></span>
3. <span data-ttu-id="d6230-127">[**Devices**] | [**概要**] で [**構成プロファイル**] を選択します (ポリシーの見出しの下)。</span><span class="sxs-lookup"><span data-stu-id="d6230-127">From **Devices** | **Overview**, select **Configuration Profiles** (under Policy heading).</span></span>
4. <span data-ttu-id="d6230-128">上部のコマンド バーで、**[プロファイルの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d6230-128">On the top command bar, select **Create profile**.</span></span>
5. <span data-ttu-id="d6230-129">[**プラットフォーム**] の下にあるドロップダウン リストで、[**Windows 10 以降**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d6230-129">In the drop-down list below **Platform**, select **Windows 10 and later**.</span></span>
6. <span data-ttu-id="d6230-130">[**プロファイル**] の下にあるドロップダウン リストで、[**管理用テンプレート**] を選択して、[**作成**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6230-130">In the drop-down list below **Profile**, select **Administrative Templates** and then click the **Create** button.</span></span> <span data-ttu-id="d6230-131">次のスクリーンショットは、プラットフォームとプロファイルの種類を選択できるドロップダウン リストを示しています。</span><span class="sxs-lookup"><span data-stu-id="d6230-131">The next screenshot shows the drop-down lists to select the platform and type of profile.</span></span>

    ![プラットフォームとプロファイルの種類を選択する](./media/configure-edge-with-intune/create-profile-platform.png)

7. <span data-ttu-id="d6230-133">[**基本**] タブで、「Microsoft Edge ポリシー」 などのわかりやすい [**名前**] を入力します。</span><span class="sxs-lookup"><span data-stu-id="d6230-133">On the **Basics** tab, enter a descriptive **Name**, such as Microsoft Edge Policy.</span></span> <span data-ttu-id="d6230-134">必要に応じて、ポリシーの **説明** を入力します。</span><span class="sxs-lookup"><span data-stu-id="d6230-134">Optionally, enter a  **Description** for the policy.</span></span>
<span data-ttu-id="d6230-135">次のスクリーンショットでは、[**基本**] タブのフォームを示しています。また、メニューバーにはプロファイルを作成するための次の手順 (灰色表示されているタブ) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6230-135">The next screenshot shows the form for the **Basics** tab and the menu bar shows the next steps (as grayed out tabs) to create the profile.</span></span>

   ![名前と説明を入力する](./media/configure-edge-with-intune/create-profile-basics-tab.png)

8. <span data-ttu-id="d6230-137">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d6230-137">Select **Next**.</span></span>
9. <span data-ttu-id="d6230-138">[**構成の設定**] タブで、次のいずれかの場所にある Microsoft Edge フォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d6230-138">On the **Configuration settings** tab, select the Microsoft Edge folder in one of the following locations:</span></span>

   - <span data-ttu-id="d6230-139">[コンピューターの構成] フォルダーの下</span><span class="sxs-lookup"><span data-stu-id="d6230-139">below the Computer Configuration folder</span></span>
   - <span data-ttu-id="d6230-140">[ユーザーの構成] フォルダーの下にあります。</span><span class="sxs-lookup"><span data-stu-id="d6230-140">below the User Configuration folder.</span></span>

   <span data-ttu-id="d6230-141">Microsoft Edge の使用可能な設定が右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6230-141">The available settings for Microsoft Edge will be shown on the right pane.</span></span> <span data-ttu-id="d6230-142">たとえば、次のスクリーンショットに示されているように、*[コンピューターの構成]、[Microsoft Edge]、[ダウンロードの制限を許可する]* などがあります。</span><span class="sxs-lookup"><span data-stu-id="d6230-142">For example, *Computer Configuration/Microsoft Edge/Allow download restrictions* shown in the following screenshot.</span></span>

   ![[構成設定] タブ](./media/configure-edge-with-intune/create-profile-configuration-settings-tab.png)

   > [!NOTE]
   > <span data-ttu-id="d6230-144">Microsoft Edge の使用可能なすべての設定の完全かつ最新のリストについては、「[Microsoft Edge のポリシー](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies)」 と 「[Microsoft Edge の更新ポリシー](https://docs.microsoft.com/DeployEdge/microsoft-edge-update-policies)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6230-144">See [Microsoft Edge – Policies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies) and [Microsoft Edge – Update policies](https://docs.microsoft.com/DeployEdge/microsoft-edge-update-policies) for the most complete and up to date list of all the available settings for Microsoft Edge.</span></span>

10. <span data-ttu-id="d6230-145">[検索] フィールドを使用して ("検索してアイテムをフィルター処理します...")、構成する特定の設定を検索します。</span><span class="sxs-lookup"><span data-stu-id="d6230-145">Use the search field ("Search to filter items ...") to find a specific setting you want to configure.</span></span> <span data-ttu-id="d6230-146">この例では、検索文字列は "ホームページ" です。</span><span class="sxs-lookup"><span data-stu-id="d6230-146">In this example, the search string is "home page".</span></span> <span data-ttu-id="d6230-147">次のスクリーンショットは、検索結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="d6230-147">The next screenshot shows the search results.</span></span>

    ![検索結果](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-search.png)

11. <span data-ttu-id="d6230-149">構成する設定を見つけたら、それを選択して設定できる値を公開します。</span><span class="sxs-lookup"><span data-stu-id="d6230-149">After you find the setting you intend to configure, select it to expose the values you can set.</span></span> <span data-ttu-id="d6230-150">次のスクリーンショットでは、例として [ホームページの URL を構成する] を選択しました。</span><span class="sxs-lookup"><span data-stu-id="d6230-150">In the next screenshot, we selected "Configure the home page URL" as an example.</span></span>

    ![ホーム ページの URL ポリシーを構成する](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-edit-pol.png)

12. <span data-ttu-id="d6230-152">前のスクリーンショットで示すように、ポリシーを有効にして、ホームページの URL に値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d6230-152">Enable the policy and enter a value for the Home page URL, as shown in the previous screenshot.</span></span>

13. <span data-ttu-id="d6230-153">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6230-153">Click **OK**.</span></span> <span data-ttu-id="d6230-154">[状態] 列の設定は、次のスクリーンショットの例のように "有効" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6230-154">The settings "State" column should appear as "Enabled", as shown in the following screenshot example.</span></span>

    ![設定の状態が有効になります](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-set-enabled.png)

14. <span data-ttu-id="d6230-156">**[次へ]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6230-156">Click the **Next** button.</span></span>

15. <span data-ttu-id="d6230-157">[**範囲タグ**] タブで、必要に応じて範囲タグを追加します。それ以外の場合は、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6230-157">On the **Scope tags** tab, add a Scope tag if wanted, otherwise click the **Next** button.</span></span>

16. <span data-ttu-id="d6230-158">[**割り当て**] タブで、[**含めるグループを選択**] をクリックしてこのポリシーをデバイスを含む Azure Active Directory (Azure AD) グループ、またはこのポリシー設定を受信するユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d6230-158">On the **Assignments** tab, click **+ Select groups to include** to assign this policy to the Azure Active Directory (Azure AD) group that contains the devices or the users that you want to receive this policy setting.</span></span> <span data-ttu-id="d6230-159">Azure AD のユーザーまたはデバイス グループにプロファイルを割り当てる方法については、「[Microsoft Intune でユーザーおよびデバイス プロファイルを割り当てる](https://docs.microsoft.com/intune/device-profile-assign)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d6230-159">See [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/device-profile-assign) for information about how to assign the profile to your Azure AD user or device groups.</span></span>

    ![含めるグループを選択する](./media/configure-edge-with-intune/create-profile-assignments-tab.png)

17. <span data-ttu-id="d6230-161">**[次へ]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6230-161">Click the **Next** button.</span></span>

18. <span data-ttu-id="d6230-162">[**確認および作成**] タブで、変更の概要をレビューして、正しいことを確認してから [**作成**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6230-162">On the **Review + create** tab, review the summary of your changes to ensure it's correct and then click the **Create** button.</span></span>

19. <span data-ttu-id="d6230-163">新しく作成されたポリシー (Microsoft Edge ポリシー) は、次のスクリーンショットに示されています。</span><span class="sxs-lookup"><span data-stu-id="d6230-163">The newly created policy (Microsoft Edge Policy) is shown in the following screenshot.</span></span>

    ![含めるグループを選択する](./media/configure-edge-with-intune/create-profile-new-policy-finished.png)

<span data-ttu-id="d6230-165">Windows 10 プロファイルについて詳しくは[、「Windows 10 テンプレートを使用して Microsoft Intune](https://docs.microsoft.com/intune/administrative-templates-windows)でグループポリシー設定を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6230-165">For more information about Windows 10 profiles, see [Use Windows 10 templates to configure group policy settings in Microsoft Intune](https://docs.microsoft.com/intune/administrative-templates-windows).</span></span>

## <span data-ttu-id="d6230-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6230-166">See also</span></span>

- [<span data-ttu-id="d6230-167">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="d6230-167">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="d6230-168">Microsoft Edge と Microsoft Intune を使用して Web アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="d6230-168">Manage web access by using Microsoft Edge with Microsoft Intune</span></span>](https://docs.microsoft.com/intune/manage-microsoft-edge)
- [<span data-ttu-id="d6230-169">Windows 10 テンプレートを使用し、Microsoft Intune でグループ ポリシー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="d6230-169">Use Windows 10 templates to configure group policy settings in Microsoft Intune</span></span>](https://docs.microsoft.com/intune/administrative-templates-windows)
- [<span data-ttu-id="d6230-170">Microsoft Intune を使用して Microsoft Edge を展開する</span><span class="sxs-lookup"><span data-stu-id="d6230-170">Deploy Microsoft Edge using Microsoft Intune</span></span>](https://docs.microsoft.com/intune/apps/apps-windows-edge/?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)
