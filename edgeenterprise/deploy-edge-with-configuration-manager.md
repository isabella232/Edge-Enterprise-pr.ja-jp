---
title: System Center Configuration Manager を使用して Microsoft Edge を展開する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2019
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: System Center Configuration Manager (SCCM) を使用して Microsoft Edge を展開する方法について説明します。
ms.openlocfilehash: 64b26412c4596a9514227d41d1a4e753a66ed057
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447831"
---
# <a name="deploy-microsoft-edge-using-system-center-configuration-manager"></a><span data-ttu-id="dbcf3-103">System Center Configuration Manager を使用して Microsoft Edge を展開する</span><span class="sxs-lookup"><span data-stu-id="dbcf3-103">Deploy Microsoft Edge using System Center Configuration Manager</span></span>

<span data-ttu-id="dbcf3-104">この記事では、System Center Configuration Manager (SCCM) を使用して Microsoft Edge の展開を自動化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-104">This article shows you how to automate a Microsoft Edge deployment by using System Center Configuration Manager (SCCM).</span></span>

>[!NOTE]
><span data-ttu-id="dbcf3-105">この記事は、Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="dbcf3-106">開始する前に</span><span class="sxs-lookup"><span data-stu-id="dbcf3-106">Before you begin</span></span>

<span data-ttu-id="dbcf3-107">「[Configuration Manager でのアプリケーション管理の概要](/sccm/apps/understand/introduction-to-application-management)」の情報をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-107">Review the information in [Introduction to application management in Configuration Manager](/sccm/apps/understand/introduction-to-application-management).</span></span> <span data-ttu-id="dbcf3-108">アプリケーション管理に関する記事は、、サイトでアプリケーションのインストールを準備するためのガイドであり、この記事で使用する用語の理解に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-108">This application management article will help you understand the terminology used in this article and is a guide to preparing your site to install applications.</span></span>

<span data-ttu-id="dbcf3-109">[Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)から、Microsoft Edge Enterprise インストール ファイル (**MicrosoftEdgeDevEnterpriseX64.msi**、**MicrosoftEdgeDevEnterpriseX86.msi**) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-109">Download the Microsoft Edge Enterprise installation files (**MicrosoftEdgeDevEnterpriseX64.msi** and/or **MicrosoftEdgeDevEnterpriseX86.msi**) from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise).</span></span>

<span data-ttu-id="dbcf3-110">Microsoft Edge インストール ファイルは、ネットワーク上のアクセス可能な場所に保存してください。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-110">Make sure you store the Microsoft Edge installation files in an accessible network location.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="dbcf3-111">アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="dbcf3-111">Create the application</span></span>

<span data-ttu-id="dbcf3-112">Configuration Manager ウィザードを使用してアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-112">You'll create the application using a Configuration Manager wizard.</span></span>

### <a name="start-the-create-application-wizard-and-create-the-application"></a><span data-ttu-id="dbcf3-113">アプリケーションの作成ウィザードを起動してアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="dbcf3-113">Start the Create Application Wizard and create the application</span></span>  

1. <span data-ttu-id="dbcf3-114">Configuration Manager コンソールで、**[ソフトウェア ライブラリ]** > **[アプリケーション管理]** > **[アプリケーション]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-114">In the Configuration Manager console, click **Software Library** > **Application Management** > **Applications**.</span></span>  

2. <span data-ttu-id="dbcf3-115">**[ホーム]** タブの **[作成]** グループで、**[アプリケーションの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-115">On the **Home** tab, in the **Create** group, click **Create Application**.</span></span> <span data-ttu-id="dbcf3-116">または、ナビゲーション バーで **[アプリケーション]** を右クリックし、**[アプリケーションの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-116">Or, right-click on **Applications** in the navigation bar and then click **Create Application**.</span></span>

    ![アプリケーションの作成](./media/edge-ent-deployment-sccm/edge-ent-create-app-1.png)

3. <span data-ttu-id="dbcf3-118">**アプリケーションの作成ウィザード**の **[全般]** ページで、**[このアプリケーションの情報をインストール ファイルから自動的に検出する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-118">On the **General** page of the **Create Application Wizard**, choose **Automatically detect information about this application from installation files**.</span></span> <span data-ttu-id="dbcf3-119">これにより、インストール用 .msi ファイルから抽出された情報を使用して、ウィザードに情報の一部が事前入力されます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-119">This pre-populates some of the information in the wizard with information that's extracted from the installation .msi file.</span></span> <span data-ttu-id="dbcf3-120">次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-120">Provide the following information:</span></span>  

   - <span data-ttu-id="dbcf3-121">**種類**: **[Windows インストーラー (\*.msi ファイル)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-121">**Type**: Choose **Windows Installer (\*.msi file)**.</span></span>  

   - <span data-ttu-id="dbcf3-122">**場所**: インストール ファイル **MicrosoftEdgeDevEnterpriseX64.msi** または **MicrosoftEdgeDevEnterpriseX86.msi** の場所を入力 (または、**[参照]** をクリックして場所を選択) します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-122">**Location**: Type the location (or click **Browse** to select the location) of the installation file **MicrosoftEdgeDevEnterpriseX64.msi** or **MicrosoftEdgeDevEnterpriseX86.msi**.</span></span> <span data-ttu-id="dbcf3-123">Configuration Manager にインストール ファイルを指定するには、場所を *\\\Server\Share\File* の形式で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-123">Note that the location must be specified in the form *\\\Server\Share\File* for Configuration Manager to locate the installation files.</span></span>  

   <span data-ttu-id="dbcf3-124">**[このアプリケーションの設定の指定]** ページは、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-124">Your **Specify settings for this application** page will look like the following example:</span></span>  

    ![このアプリケーションの設定の指定](./media/edge-ent-deployment-sccm/edge-ent-create-app-2.png)

4. <span data-ttu-id="dbcf3-126">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-126">Click **Next**.</span></span> <span data-ttu-id="dbcf3-127">**[インポートした情報の表示]** ページの \*\*[詳細] \*\* に、アプリケーションおよびインポートされた関連ファイルに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-127">Under **Details** on the **Imported Information** page, you'll see information about the application and any associated files that were imported.</span></span> <span data-ttu-id="dbcf3-128">**[次へ]** をクリックして、ウィザードを続行します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-128">Click **Next** to continue with the wizard.</span></span>  

    ![インポートした情報の表示](./media/edge-ent-deployment-sccm/edge-ent-create-app-3.png)

5. <span data-ttu-id="dbcf3-130">**[一般情報]** ページでは、アプリケーションに関する詳細情報を追加できます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-130">On the **General Information** page, you can add more information about the application.</span></span> <span data-ttu-id="dbcf3-131">たとえば、ソフトウェアのバージョン、管理者のコメント、発行元などです。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-131">For example, Software version, Administrator comments, and Publisher.</span></span> <span data-ttu-id="dbcf3-132">この情報をに使用すると、Configuration Manager コンソールでアプリケーションを分類または検索する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-132">You can use this information to to help you sort and find the application in the Configuration Manager console.</span></span>

   <span data-ttu-id="dbcf3-133">**[インストール プログラム]** フィールドを使用して、PC にアプリケーションをインストールするために使用する完全なコマンド ラインを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-133">You can also use the **Installation program** field to specify the full command line that will be used to install the application on PCs.</span></span> <span data-ttu-id="dbcf3-134">これを編集して、独自のプロパティ (たとえば、無人インストール用の **/q** など) を追加できます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-134">You can edit this to add your own properties (for example, **/q** for an unattended installation).</span></span>

   <span data-ttu-id="dbcf3-135">次のスクリーンショットは、**[このアプリケーションの情報の指定]** フィールドの使用例を示しています。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-135">The following screenshot shows an example where the **Specify information about this application** fields are used.</span></span>

   ![アプリケーションのメタデータの指定](./media/edge-ent-deployment-sccm/edge-ent-create-app-5.png)

6. <span data-ttu-id="dbcf3-137">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-137">Click **Next**.</span></span>
7. <span data-ttu-id="dbcf3-138">**[概要]** ページの **[詳細]** でアプリケーションの設定を確認して、ウィザードの使用を終了できます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-138">On the **Summary** page, you can confirm your application settings under **Details** and then finish using the wizard.</span></span> <span data-ttu-id="dbcf3-139">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-139">Click **Next**.</span></span>  

    ![アプリケーション設定の詳細](./media/edge-ent-deployment-sccm/edge-ent-create-app-6.png)

8. <span data-ttu-id="dbcf3-141">**[完了]** ページで、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-141">On the **Completion** page, click **Close**.</span></span>

    ![成功ダイアログ](./media/edge-ent-deployment-sccm/edge-ent-create-app-7.png)

<span data-ttu-id="dbcf3-143">アプリケーションの作成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-143">You've finished creating the application.</span></span> <span data-ttu-id="dbcf3-144">Configuration Manager に表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-144">Use the following steps to see it in Configuration Manager:</span></span>

- <span data-ttu-id="dbcf3-145">**[ソフトウェア ライブラリ]** ワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-145">select the **Software Library** workspace</span></span>
- <span data-ttu-id="dbcf3-146">**[アプリケーション管理]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-146">expand **Application Management**</span></span>
- <span data-ttu-id="dbcf3-147">**[アプリケーション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-147">click **Applications**.</span></span>

<span data-ttu-id="dbcf3-148">次のスクリーンショットは、この記事で使用した例を示しています。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-148">The following screenshot shows the example used for this article.</span></span>  

![アプリケーション](./media/edge-ent-deployment-sccm/edge-ent-create-app-8.png)

## <a name="change-application-properties-and-deployment-settings"></a><span data-ttu-id="dbcf3-150">アプリケーションのプロパティと展開の設定を変更する</span><span class="sxs-lookup"><span data-stu-id="dbcf3-150">Change application properties and deployment settings</span></span>

<span data-ttu-id="dbcf3-151">アプリケーションを作成した後、必要に応じてアプリケーションの設定を調整できます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-151">After you create an application, you can refine the application settings if you need to.</span></span> <span data-ttu-id="dbcf3-152">アプリケーションのプロパティを確認するには:</span><span class="sxs-lookup"><span data-stu-id="dbcf3-152">To look at the application properties:</span></span>

- <span data-ttu-id="dbcf3-153">アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-153">select the application</span></span>
- <span data-ttu-id="dbcf3-154">**[ホーム]**>**[プロパティ]** の **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-154">in **Home**>**Properties**, click **Properties**.</span></span>  

   ![アプリケーションのプロパティを構成する](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-1.png)

 <span data-ttu-id="dbcf3-156">**[<アプリケーション名\> アプリケーションのプロパティ]** ダイアログ ページには、アプリケーションの動作を変更するために構成できる項目のタブ付きのビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-156">In the **<application name\> Application Properties** dialog page, you'll see a tabbed view of the items that you can configure to change the behavior of the application.</span></span> <span data-ttu-id="dbcf3-157">構成可能な設定について詳しくは、[アプリケーションの作成に関するページ](/sccm/apps/deploy-use/create-applications)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-157">For more information about the settings you can configure, see [Create applications](/sccm/apps/deploy-use/create-applications).</span></span>

<span data-ttu-id="dbcf3-158">この例では、アプリケーションの展開の種類のプロパティをいくつか変更します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-158">For this example, you'll change some properties of the application's deployment type.</span></span> <span data-ttu-id="dbcf3-159">展開のプロパティを変更するには:</span><span class="sxs-lookup"><span data-stu-id="dbcf3-159">To change the deployment properties:</span></span>

1. <span data-ttu-id="dbcf3-160">**[展開の種類]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-160">Click the **Deployment Types** tab.</span></span>
2. <span data-ttu-id="dbcf3-161">**[展開の種類]** で、アプリケーションの **[名前]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-161">Under **Deployment types:**, select the application **Name**</span></span>
3. <span data-ttu-id="dbcf3-162">**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-162">Click **Edit**.</span></span>

   ![展開の種類を編集する](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-2.png)

### <a name="add-a-requirement-to-the-deployment-type"></a><span data-ttu-id="dbcf3-164">展開の種類に要件を追加する</span><span class="sxs-lookup"><span data-stu-id="dbcf3-164">Add a requirement to the deployment type</span></span>

 <span data-ttu-id="dbcf3-165">要件には、デバイスにアプリケーションをインストールする前に満たす必要がある条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-165">Requirements specify conditions that must be met before an application is installed on a device.</span></span> <span data-ttu-id="dbcf3-166">組み込みの要件から選択することも、独自の要件を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-166">You can choose from built-in requirements or you can create your own.</span></span> <span data-ttu-id="dbcf3-167">たとえば、インストール ファイルのターゲット プロセッサ アーキテクチャに応じて、Windows 10 **x86** または **x64** を実行している PC にのみアプリケーションがインストールされるという要件を追加できます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-167">For example, you can add a requirement that the application will only be installed on PCs that are running Windows 10 **x86** or **x64**, depending on the installation file's target processor architecture.</span></span> <span data-ttu-id="dbcf3-168">この例では Windows 10 **x86** を指定します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-168">In this example, you'll specify Windows 10 **x86**.</span></span>

1. <span data-ttu-id="dbcf3-169">開いた展開の種類のプロパティ ページで、**[要件]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-169">From the deployment type properties page you just opened, click the **Requirements** tab.</span></span>

2. <span data-ttu-id="dbcf3-170">**[追加]** をクリックし、**[要件の作成]** ダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-170">Click **Add** to open the **Create Requirement** dialog.</span></span>

    ![要件の作成](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-3.png)

3. <span data-ttu-id="dbcf3-172">**[要件の作成]** ダイアログ ボックスで、次の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-172">In the **Create Requirement** dialog box, specify the following information:</span></span>

    - <span data-ttu-id="dbcf3-173">**カテゴリ**: **デバイス**</span><span class="sxs-lookup"><span data-stu-id="dbcf3-173">**Category**: **Device**</span></span>  

    - <span data-ttu-id="dbcf3-174">**条件**: **オペレーティング システム**</span><span class="sxs-lookup"><span data-stu-id="dbcf3-174">**Condition**: **Operating system**</span></span>  

    - <span data-ttu-id="dbcf3-175">**規則の種類**: **値**</span><span class="sxs-lookup"><span data-stu-id="dbcf3-175">**Rule type**: **Value**</span></span>  

    - <span data-ttu-id="dbcf3-176">**演算子**: **次のいずれか**</span><span class="sxs-lookup"><span data-stu-id="dbcf3-176">**Operator**: **One of**</span></span>  

    - <span data-ttu-id="dbcf3-177">オペレーティング システムの一覧から、**[Windows 10]** > **[すべての Windows 10 (32 ビット)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-177">From the operating systems list, select **Windows 10** > **All Windows 10 (32-bit)**.</span></span>  

    <span data-ttu-id="dbcf3-178">完了すると、ダイアログは次のスクリーンショット例のようになります。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-178">When you're finished, the dialog will look like the following screenshot example:</span></span>

    ![要件を追加する](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-4.png)

4. <span data-ttu-id="dbcf3-180">**[OK]** をクリックして、開いている各プロパティ ページを閉じ、Configuration Manager コンソールの **[アプリケーション]** 一覧に戻ります。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-180">Click **OK** to close each open property page and return to the **Applications** list in the Configuration Manager console.</span></span>  

## <a name="add-the-application-content-to-a-distribution-point"></a><span data-ttu-id="dbcf3-181">アプリケーション コンテンツを配布ポイントに追加する</span><span class="sxs-lookup"><span data-stu-id="dbcf3-181">Add the application content to a distribution point</span></span>  

<span data-ttu-id="dbcf3-182">更新されたアプリケーションを PC に展開するには、アプリケーションのコンテンツが配布ポイントにコピーされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-182">To deploy the updated application to PCs, make sure that the application content is copied to a distribution point.</span></span> <span data-ttu-id="dbcf3-183">PC は、配布ポイントにアクセスしてアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-183">PCs access the distribution point to install the application.</span></span>  

>[!TIP]
><span data-ttu-id="dbcf3-184">Configuration Manager の配布ポイントとコンテンツ管理について詳しくは、 「[System Center Configuration Manager でのコンテンツの展開および管理](/sccm/core/servers/deploy/configure/deploy-and-manage-content)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-184">To find out more about distribution points and content management in Configuration Manager, see [Deploy and manage content for System Center Configuration Manager](/sccm/core/servers/deploy/configure/deploy-and-manage-content).</span></span>  

1. <span data-ttu-id="dbcf3-185">Configuration Manager コンソールで、**[ソフトウェア ライブラリ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-185">In the Configuration Manager console, click **Software Library**.</span></span>  

2. <span data-ttu-id="dbcf3-186">**[ソフトウェア ライブラリ]** ワークスペースで **[アプリケーション]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-186">In the **Software Library** workspace, expand **Applications**.</span></span> <span data-ttu-id="dbcf3-187">アプリケーションの一覧から、作成したアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-187">Select the application you created in the list of applications.</span></span>

3. <span data-ttu-id="dbcf3-188">**[ホーム]** タブの **[展開]** グループで、**[コンテンツの配布]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-188">On the **Home** tab in the **Deployment** group, click **Distribute Content**.</span></span>  

4. <span data-ttu-id="dbcf3-189">**コンテンツの配布ウィザード**の **[全般]** ページで、アプリケーションの名前が正しいことを確認し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-189">On the **General** page of the **Distribute Content Wizard**, check that the application name is correct, and then click **Next**.</span></span>  

5. <span data-ttu-id="dbcf3-190">**[コンテンツ]** ページで、配布ポイントにコピーされる情報を確認し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-190">On the **Content** page, review the information that will be copied to the distribution point, and then click **Next**.</span></span>  

6. <span data-ttu-id="dbcf3-191">**[コンテンツの配布先]** ページで **[追加]** をクリックし、アプリケーション コンテンツのインストール先として 1 つ以上のコレクション、配布ポイント、または配布ポイント グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-191">On the **Content Destination** page, click **Add** to select one or more collections, distribution points, or distribution point groups on which to install the application content.</span></span>

7. <span data-ttu-id="dbcf3-192">ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-192">Complete the wizard.</span></span>

<span data-ttu-id="dbcf3-193">アプリケーション コンテンツが配布ポイントに正しくコピーされたかどうかを確認するには、**[監視]** ワークスペースの **[配布ステータス]** > **[コンテンツのステータス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-193">You can check that the application content was copied successfully to the distribution point from the **Monitoring** workspace, under **Distribution Status** > **Content Status**.</span></span>  

## <a name="deploy-the-application"></a><span data-ttu-id="dbcf3-194">アプリケーションを展開する</span><span class="sxs-lookup"><span data-stu-id="dbcf3-194">Deploy the application</span></span>  

<span data-ttu-id="dbcf3-195">次に、階層内のデバイス コレクションにアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-195">Next, deploy the application to a device collection in your hierarchy.</span></span> <span data-ttu-id="dbcf3-196">この例では、アプリケーションを **[すべてのシステム]** デバイス コレクションに展開します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-196">In this example, you deploy the application to the **All Systems** device collection.</span></span>  

>[!TIP]
><span data-ttu-id="dbcf3-197">前の手順で選択した要件により、指定されたプロセッサ アーキテクチャの Windows 10 コンピューターのみでアプリケーションがインストールされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-197">Remember that only Windows 10 computers of the specified processor architecture will install the application because of the requirements that you selected earlier.</span></span>  

1. <span data-ttu-id="dbcf3-198">Configuration Manager コンソールで、**[ソフトウェア ライブラリ]** > **[アプリケーション管理]** > **[アプリケーション]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-198">In the Configuration Manager console, click **Software Library** > **Application Management** > **Applications**.</span></span>

2. <span data-ttu-id="dbcf3-199">アプリケーションの一覧から、既に作成したアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-199">From the list of applications, select the application that you created earlier.</span></span> <span data-ttu-id="dbcf3-200">次に、**[ホーム]** タブの **[展開]** グループで **[展開]** をクリックするか、アプリケーションを右クリックして **[展開]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-200">Then, on the **Home** tab in the **Deployment** group, click **Deploy**, or right-click the application and select **Deploy**.</span></span>

    ![アプリケーションを展開する](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-1.png)

3. <span data-ttu-id="dbcf3-202">**ソフトウェアの展開ウィザード**の **[全般]** ページで **[参照]** をクリックし、アプリケーションの展開先としてデバイス コレクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-202">On the **General** page of the **Deploy Software Wizard**, click **Browse** to select the device collection to which you want to deploy the application.</span></span>

    ![インストール ファイルを参照する](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-2.png)

4. <span data-ttu-id="dbcf3-204">**[コンテンツ]** ページで、PC からアプリケーションをインストールする際に使用する配布ポイントが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-204">On the **Content** page, check that the distribution point from which you want PCs to install the application is selected.</span></span>

    ![配布ポイントを指定する](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-6.png)

5. <span data-ttu-id="dbcf3-206">**[展開設定]** ページで、展開アクションが **[インストール]** に設定され、展開の目的が **[必須]** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-206">On the **Deployment Settings** page, make sure that the deployment action is set to **Install**, and the deployment purpose is set to **Required**.</span></span>

    ![展開設定を構成する](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-8.png)

    >[!TIP]
    ><span data-ttu-id="dbcf3-208">展開の目的を **[必須]** に設定すると、設定した要件を満たす PC にアプリケーションがインストールされるようになります。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-208">By setting the deployment purpose to **Required**, you make sure that the application is installed on PCs that meet the requirements that you set.</span></span> <span data-ttu-id="dbcf3-209">この値を **[使用可能]** に設定した場合、ユーザーはソフトウェア センターから必要に応じてアプリケーションをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-209">If you set this value to **Available**, then users can install the application on demand from Software Center.</span></span>  

6. <span data-ttu-id="dbcf3-210">**[スケジュール]** ページでは、アプリケーションをいつインストールするかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-210">On the **Scheduling** page, you can configure when the application will be installed.</span></span> <span data-ttu-id="dbcf3-211">この例では、**[使用可能な時間後直ちに]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-211">For this example, select **As soon as possible after the available time**.</span></span>

    ![展開のスケジュール設定](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-9.png)

7. <span data-ttu-id="dbcf3-213">**[ユーザー エクスペリエンス]** ページで、ニーズに応じた値を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-213">On the **User Experience** page, select your desired values and click **Next**.</span></span>

    ![ユーザー エクスペリエンスを指定する](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-10.png)

8. <span data-ttu-id="dbcf3-215">ニーズに応じたアラート オプションを指定し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-215">Specify your desired alert options and click **Next**.</span></span>

    ![アラート設定を指定する](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-11.png)

9. <span data-ttu-id="dbcf3-217">ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-217">Complete the wizard.</span></span>

<span data-ttu-id="dbcf3-218">アプリケーションの展開の状態を確認するには、次の「**アプリケーションを監視する**」セクションの情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-218">Use the information in the following **Monitor the application** section to see the status of your application deployment.</span></span>  

## <a name="monitor-the-application"></a><span data-ttu-id="dbcf3-219">アプリケーションを監視する</span><span class="sxs-lookup"><span data-stu-id="dbcf3-219">Monitor the application</span></span>

 <span data-ttu-id="dbcf3-220">このセクションでは、展開したアプリケーションの展開状態を簡単に確認します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-220">In this section, you'll take a quick look at the deployment status of the application that you just deployed.</span></span>  

### <a name="to-review-the-deployment-status"></a><span data-ttu-id="dbcf3-221">展開状態を確認するには</span><span class="sxs-lookup"><span data-stu-id="dbcf3-221">To review the deployment status</span></span>  

1. <span data-ttu-id="dbcf3-222">Configuration Manager コンソールで、 **[監視]** > **[展開]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-222">In the Configuration Manager console, click **Monitoring** > **Deployments**.</span></span>  

2. <span data-ttu-id="dbcf3-223">展開の一覧から、アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-223">From the list of deployments, select the application.</span></span>

    ![展開を監視する](./media/edge-ent-deployment-sccm/edge-ent-monitor-deployment.png)

3. <span data-ttu-id="dbcf3-225">**[ホーム]** タブの **[展開]** グループで、**[ステータスの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-225">On the **Home** tab in the **Deployment** group, click **View Status**.</span></span>  

4. <span data-ttu-id="dbcf3-226">次のいずれかのタブを選択して、アプリケーションの展開に関する状態の最新情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-226">Select one of the following tabs to see more status updates about the application deployment:</span></span>  

    - <span data-ttu-id="dbcf3-227">**成功**: 指定された PC にアプリケーションが正常にインストールされました。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-227">**Success**: The application installed successfully on the indicated PCs.</span></span>  

    - <span data-ttu-id="dbcf3-228">**処理中**: アプリケーションのインストールはまだ完了していません。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-228">**In Progress**: The application has not yet finished installing.</span></span>  

    - <span data-ttu-id="dbcf3-229">**エラー**: 指定された PC にアプリケーションをインストール中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-229">**Error**: An error occurred installing the application on the indicated PCs.</span></span> <span data-ttu-id="dbcf3-230">エラーに関する詳細情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-230">Further information about the error is also displayed.</span></span>  

    - <span data-ttu-id="dbcf3-231">**要件が満たされていません**: 構成された要件を満たしていないため、指定のデバイスでインストールが行われませんでした (この例では、指定のデバイスで Windows 10 が実行されていないため)。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-231">**Requirements Not Met**: No installation attempt was made on the indicated devices because they did not meet the requirements you configured (in this example, because they do not run on Windows 10.)</span></span>

    - <span data-ttu-id="dbcf3-232">**不明**: Configuration Manager は、展開の状態を報告できませんでした。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-232">**Unknown**: Configuration Manager was unable to report the status of the deployment.</span></span> <span data-ttu-id="dbcf3-233">後でもう一度確認してしてください。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-233">Check back again later.</span></span>  

    >[!TIP]
    ><span data-ttu-id="dbcf3-234">アプリケーションの展開を監視するには、複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-234">There are several ways you can monitor application deployments.</span></span> <span data-ttu-id="dbcf3-235">詳しくは、「[System Center Configuration Manager コンソールからアプリケーションを監視する](/sccm/apps/deploy-use/monitor-applications-from-the-console)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-235">For more information, see [Monitor applications from the System Center Configuration Manager console](/sccm/apps/deploy-use/monitor-applications-from-the-console).</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="dbcf3-236">エンドユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="dbcf3-236">End-user experience</span></span>  

<span data-ttu-id="dbcf3-237">Configuration Manager によって管理され、指定されたプロセッサ アーキテクチャの Windows 10 を実行する PC を使用しているユーザーには、Microsoft Edge Dev アプリケーションをインストールする必要があることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-237">Users who have PCs that are managed by Configuration Manager and are running Windows 10 of the specified processor architecture, will see a message telling them that they must install the Microsoft Edge Dev application.</span></span> <span data-ttu-id="dbcf3-238">このインストール オプションを受け入れると、アプリケーションがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="dbcf3-238">When they accept this installation option, the application is installed.</span></span>  

## <a name="see-also"></a><span data-ttu-id="dbcf3-239">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbcf3-239">See also</span></span>

- [<span data-ttu-id="dbcf3-240">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="dbcf3-240">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="dbcf3-241">System Center Configuration Manager でアプリケーションを作成および展開する</span><span class="sxs-lookup"><span data-stu-id="dbcf3-241">Create and deploy an application with System Center Configuration Manager</span></span>](/sccm/apps/get-started/create-and-deploy-an-application)