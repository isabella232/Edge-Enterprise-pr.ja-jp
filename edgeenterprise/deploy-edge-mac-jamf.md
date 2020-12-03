---
title: Jamf を使用して macOS 用の Microsoft Edge 展開を自動化する
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 11/30/2019
audience: ITPro
ms.topic: technical
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Jamf を使用して macOS 用の Microsoft Edge 展開を自動化する方法。
ms.openlocfilehash: 8639c0b7bf78bb8e22370dba29b592af73d8cb40
ms.sourcegitcommit: ed6a5afabf909df87bec48671c4c47bcdfaeb7bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "11194725"
---
# <span data-ttu-id="19519-103">Jamf による macOS への展開</span><span class="sxs-lookup"><span data-stu-id="19519-103">Deploy to macOS with Jamf</span></span>

<span data-ttu-id="19519-104">この記事では、Jamf を使用して macOS 用に Microsoft Edge を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19519-104">This article describes how to deploy Microsoft Edge for macOS using Jamf.</span></span>

> [!NOTE]
> <span data-ttu-id="19519-105">この記事は、Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="19519-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="19519-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="19519-106">Prerequisites</span></span>

<span data-ttu-id="19519-107">Microsoft Edge を展開する前に、次の前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="19519-107">Before you deploy Microsoft Edge, make sure you meet the following prerequisites:</span></span>

- <span data-ttu-id="19519-108">Microsoft Edge インストール ファイル (**MicrosoftEdgeDev-\<version\>.pkg**) が、ネットワーク上のアクセス可能な場所にあること。</span><span class="sxs-lookup"><span data-stu-id="19519-108">The Microsoft Edge installation file,  **MicrosoftEdgeDev-\<version\>.pkg** is in an accessible location on your network.</span></span> <span data-ttu-id="19519-109">Microsoft Edge Enterprise のインストール ファイルは、[Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="19519-109">You can download the Microsoft Edge Enterprise installation files from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise).</span></span>
- <span data-ttu-id="19519-110">インストール ファイルを作成してコンピューターに展開するために必要なレベルのアクセスと権限のある Jamf Cloud アカウントを持っていること。</span><span class="sxs-lookup"><span data-stu-id="19519-110">You have a Jamf Cloud account with the level of access and privileges needed to create and deploy installation files to computers.</span></span>

## <span data-ttu-id="19519-111">Jamf を使用して Microsoft Edge を展開するには:</span><span class="sxs-lookup"><span data-stu-id="19519-111">To deploy Microsoft Edge using Jamf:</span></span>

1. <span data-ttu-id="19519-112">Jamf にサインオンし、**[All Settings]** (すべての設定) に移動します。</span><span class="sxs-lookup"><span data-stu-id="19519-112">Sign on to Jamf and go to **All Settings**.</span></span>

    ![すべての設定を開く](./media/mac-deploy/jamf-dash-main-open-settings.png)

2. <span data-ttu-id="19519-114">**[All Settings]** (すべての設定) の **[Computer Management]** (コンピューターの管理) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19519-114">Under **All Settings**, click **Computer Management**.</span></span>

    ![[Computer Management] (コンピュータの管理) の選択](./media/mac-deploy/jamf-all-settings-computer-mgmt.png)

3. <span data-ttu-id="19519-116">**[Computer Management]** (コンピュータの管理) で、**[Packages]** (パッケージ) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19519-116">Under **Computer Management**, click **Packages**.</span></span>

    ![[Packages] (パッケージ) の選択](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkgs.png)

4. <span data-ttu-id="19519-118">**[Packages]** (パッケージ) ページで、**[+ New]** (新規) をクリックして、新しいパッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="19519-118">On the **Packages** page, click **+ New** to add a new package.</span></span>

    ![[New] (新規) を選択して新しいパートナーシップを追加する](./media/mac-deploy/jamf-all-settings-computer-mgmt-new-pkg.png)

5. <span data-ttu-id="19519-120">**[New Package]** (新しいパッケージ) ページで、パッケージに関する詳細を入力し、**[Save]** (保存) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19519-120">On the **New Package** page, enter the details about the package and then click **Save**.</span></span> <span data-ttu-id="19519-121">(たとえば、表示名、情報、メモなど)。</span><span class="sxs-lookup"><span data-stu-id="19519-121">(For example, DISPLAY NAME, INFO, or NOTES.)</span></span>

    ![[Save] (保存) を選択してパッケージ情報を保存する](./media/mac-deploy/jamf-all-settings-computer-mgmt-save-pkg-info.png)

6. <span data-ttu-id="19519-123">メニュー バーの **[Computers]** (コンピューター) を選択し、ナビゲーション バーの **[Policies]** (ポリシー) を選択します。</span><span class="sxs-lookup"><span data-stu-id="19519-123">Select **Computers** on the menu bar, and then select **Policies** in the navigation bar.</span></span>

7. <span data-ttu-id="19519-124">**[+ New]** (新規) を選択して、**New Policy** (新しいポリシー) ウィンドウを表示します。</span><span class="sxs-lookup"><span data-stu-id="19519-124">Select **+ New** to display the **New Policy** pane.</span></span>

    ![[New] (新規) を選択して新しいポリシーを作成する](./media/mac-deploy/jamf-all-settings-computer-new-policy.png)

8. <span data-ttu-id="19519-126">**[Options]** (オプション) タブの **[General]** (全般) を選択します。</span><span class="sxs-lookup"><span data-stu-id="19519-126">On the **Options** tab, select **General**.</span></span>

    - <span data-ttu-id="19519-127">**[DISPLAY NAME]** (表示名) に、ポリシーの表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="19519-127">Under **DISPLAY NAME**, enter the display name for the policy.</span></span>
    - <span data-ttu-id="19519-128">**[Trigger]** (トリガー) で、ポリシーをトリガーするイベントを選択します。</span><span class="sxs-lookup"><span data-stu-id="19519-128">Under **Trigger**, select the event that will trigger the policy.</span></span> <span data-ttu-id="19519-129">(下の例では、イベントは [Startup] (スタートアップ) です。)</span><span class="sxs-lookup"><span data-stu-id="19519-129">(In the following example, the event is Startup.)</span></span>

    ![展開情報を入力する](./media/mac-deploy/jamf-all-settings-computer-cfg-policy.png)

9. <span data-ttu-id="19519-131">**[Options]** (オプション) タブで、**[Packages]** (パッケージ) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19519-131">On the **Options** tab, click **Packages**.</span></span>

10. <span data-ttu-id="19519-132">**[Configure Packages]** (パッケージの構成) ポップアップで、**[Configure]** (構成) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19519-132">On the **Configure Packages** popup, click **Configure**.</span></span>

    ![パッケージの構成](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-configure.png)

11. <span data-ttu-id="19519-134">追加したパッケージが **[Packages]** (パッケージ) ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="19519-134">The package that you added shows on the **Packages** pane.</span></span> <span data-ttu-id="19519-135">**[Add]** (追加) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19519-135">Click **Add**.</span></span> <span data-ttu-id="19519-136">次のスクリーンショットで、この例のパッケージは "MicrosoftEdgeBeta" です。</span><span class="sxs-lookup"><span data-stu-id="19519-136">For this example, the package is "MicrosoftEdgeBeta" in the following screenshot.</span></span>

    ![パッケージの追加](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-add-beta.png)

12. <span data-ttu-id="19519-138">**[New Policy]** (新しいポリシー) ページで、ドロップダウン リストを使用して、**[DISTRIBUTION POINT]** (配布ポイント) と、ポリシーについて実行する **[ACTION]** (アクション) を選択します。</span><span class="sxs-lookup"><span data-stu-id="19519-138">On the **New Policy** page, uUse the drop-down lists to select the **DISTRIBUTION POINT** and **ACTION** to take for the policy.</span></span> <span data-ttu-id="19519-139">**[Save]** (保存) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19519-139">Click **Save**.</span></span> <span data-ttu-id="19519-140">次のスクリーンショットでは、例として [Each computer's default distribution point] (各コンピューターの既定の配布ポイント) と [Install] (インストール) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="19519-140">The following screenshot uses "Each computer's default distribution point" and "Install" as an example.</span></span>

    ![配布ポイントとアクションの選択](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkg-cfg-distro.png)

13. <span data-ttu-id="19519-142">**[New Policy]** 新しいポリシーページで、**[Scope]** (スコープ) タブを選択します。コンピューターまたはユーザーに基づいて、展開の範囲を管理できます。</span><span class="sxs-lookup"><span data-stu-id="19519-142">On the **New Policy** page, select the **Scope** tab. You can manage the scope of the deployment based on computers or users.</span></span> <span data-ttu-id="19519-143">この例では、**[TARGET COMPUTERS]** (ターゲット コンピューター) ドロップダウン リストから **[All Computers]** (すべてのコンピューター) を選択し、**[Save]** (保存) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19519-143">For this example, select **All Computers** from the **TARGET COMPUTERS** drop-down list and then click **Save**.</span></span>

    ![展開の範囲を選択する](./media/mac-deploy/jamf-all-settings-computer-mgmt-add-target.png)

14. <span data-ttu-id="19519-145">この時点で、Microsoft Edge 展開ポリシーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="19519-145">At this point you can review the Microsoft Edge deployment policy.</span></span> <span data-ttu-id="19519-146">展開オプションが要件を満たしている場合は、**[Done]** (完了) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19519-146">If the deployment options meet your requirements, click **Done**.</span></span>

    ![完了をクリックする](./media/mac-deploy/jamf-all-settings-computer-mgmt-finish-add-deployment.png)

    > [!NOTE]
    > <span data-ttu-id="19519-148">いつでも展開ポリシーに戻って設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="19519-148">You can return to a deployment policy at any time to change settings.</span></span>

<span data-ttu-id="19519-149">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="19519-149">Congratulations!</span></span> <span data-ttu-id="19519-150">これで、Jamf を使用して macOS 用に Microsoft Edge を展開するための構成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="19519-150">You’ve just finished configuring Jamf to deploy Microsoft Edge for macOS.</span></span> <span data-ttu-id="19519-151">定義したトリガー条件に合致すると、指定したコンピューターにパッケージが展開されます。</span><span class="sxs-lookup"><span data-stu-id="19519-151">When the trigger condition you defined is true, the package will get deployed to the computers you specified.</span></span>

## <span data-ttu-id="19519-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="19519-152">See also</span></span>

- [<span data-ttu-id="19519-153">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="19519-153">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="19519-154">Jamf.com</span><span class="sxs-lookup"><span data-stu-id="19519-154">Jamf.com</span></span>](https://www.jamf.com/)
- [<span data-ttu-id="19519-155">Jamf を Microsoft Intune と統合する</span><span class="sxs-lookup"><span data-stu-id="19519-155">Integrate Jamf with Microsoft Intune</span></span>](https://docs.microsoft.com/intune/conditional-access-integrate-jamf)
