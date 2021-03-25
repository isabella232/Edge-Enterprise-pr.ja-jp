---
title: Windows および macOS で Microsoft Edge を既定のブラウザーとして設定する
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 1/15/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge を既定のブラウザーとして設定する方法について説明します
ms.openlocfilehash: 9151294c34cb2252a7fb32e660c1e3d9e64b5f76
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447761"
---
# <a name="set-microsoft-edge-as-the-default-browser"></a><span data-ttu-id="6b3d7-103">Microsoft Edge を既定のブラウザーとして設定する</span><span class="sxs-lookup"><span data-stu-id="6b3d7-103">Set Microsoft Edge as the default browser</span></span>

<span data-ttu-id="6b3d7-104">この記事では、Windows および macOS で Microsoft Edge を既定のブラウザーとして設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-104">This article explains how you can set Microsoft Edge as the default browser on Windows and macOS.</span></span>

> [!NOTE]
> <span data-ttu-id="6b3d7-105">この記事は、Windows 8 および Windows 10 の Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-105">This article applies to Microsoft Edge version 77 or later on Windows 8 and Windows 10.</span></span> <span data-ttu-id="6b3d7-106">Windows 7 および macOS の場合は、「[Microsoft Edge を既定のブラウザーとして設定する](./microsoft-edge-policies.md#defaultbrowsersettingenabled)」のポリシーをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-106">For Windows 7 and macOS, see the [Set Microsoft Edge as default browser](./microsoft-edge-policies.md#defaultbrowsersettingenabled) policy.</span></span>

## <a name="introduction"></a><span data-ttu-id="6b3d7-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="6b3d7-107">Introduction</span></span>

<span data-ttu-id="6b3d7-108">Microsoft Edge を組織の既定ブラウザーとして設定するには、**[既定の関連付け構成ファイルの設定]** グループ ポリシーまたは [DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) モバイル デバイス管理設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-108">You can use the **Set a default associations configuration file** Group Policy or the [DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) Mobile Device Management setting to set Microsoft Edge as the default browser for your organization.</span></span>

<span data-ttu-id="6b3d7-109">html ファイル、http/https リンク、および PDF ファイル用の既定ブラウザーとして Microsoft Edge Stable を設定するには、次のアプリケーション関連付けファイルの例を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-109">To set Microsoft Edge Stable as the default browser for html files, http/https links, and PDF files use the following application association file example:</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations> 
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> <span data-ttu-id="6b3d7-110">Microsoft Edge Beta を既定ブラウザーとして設定するには、**ApplicationName** を "Microsoft Edge Beta"、**ProgId** を "MSEdgeBHTML" に設定します。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-110">To set Microsoft Edge Beta as the default browser, set **ApplicationName** to "Microsoft Edge Beta" and **ProgId** to "MSEdgeBHTML".</span></span> <span data-ttu-id="6b3d7-111">Microsoft Edge Dev を既定ブラウザーとして設定するには、**ApplicationName** を "Microsoft Edge Dev"、**ProgId** を "MSEdgeDHTML" に設定します。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-111">To set Microsoft Edge Dev as the default browser, set **ApplicationName** to "Microsoft Edge Dev" and **ProgId** to "MSEdgeDHTML".</span></span>


> [!NOTE]
> <span data-ttu-id="6b3d7-112">ターゲット デバイスに Microsoft Edge がインストールされていない場合、既定のファイル関連付けは適用されません。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-112">The default file associations aren't applied if Microsoft Edge isn't installed on the target device.</span></span> <span data-ttu-id="6b3d7-113">このシナリオでは、ユーザーがリンクまたは htm/html ファイルを開くときに、既定のアプリケーションを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-113">In this scenario, users are prompted to select their default application when they open a link or a htm/html file.</span></span>

## <a name="set-microsoft-edge-as-the-default-browser-on-domain-joined-devices"></a><span data-ttu-id="6b3d7-114">ドメインに参加しているデバイスで Microsoft Edge を既定のブラウザーとして設定する</span><span class="sxs-lookup"><span data-stu-id="6b3d7-114">Set Microsoft Edge as the default browser on domain-joined devices</span></span>

<span data-ttu-id="6b3d7-115">ドメインに参加しているデバイスで Microsoft Edge を既定のブラウザーとして設定するには、**[既定の関連付け構成ファイルの設定]** グループ ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-115">You can set Microsoft Edge as the default browser on domain-joined devices by configuring the **Set a default associations configuration file** group policy.</span></span> <span data-ttu-id="6b3d7-116">このグループ ポリシーを有効にした場合は、既定の関連付け構成ファイルを作成し、保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-116">Turning this group policy on requires you to create and store a default associations configuration file.</span></span> <span data-ttu-id="6b3d7-117">このファイルは、ローカルまたはネットワーク共有に保存されます。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-117">This file is stored locally or on a network share.</span></span> <span data-ttu-id="6b3d7-118">このファイルの作成方法について詳しくは、「[既定のアプリケーションの関連付けのエクスポートまたはインポート](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-118">For more information about creating this file, see [Export or Import Default Application Associations](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations).</span></span>

### <a name="to-configure-the-group-policy-for-a-default-file-type-and-protocol-associations-configuration-file"></a><span data-ttu-id="6b3d7-119">ファイルの種類とプロトコルの既定の関連付け構成ファイルに関するグループ ポリシーを構成するには:</span><span class="sxs-lookup"><span data-stu-id="6b3d7-119">To configure the group policy for a default file type and protocol associations configuration file:</span></span>

1. <span data-ttu-id="6b3d7-120">グループ ポリシー エディターを開き、**[コンピューターの構成]\[管理用テンプレート]\[Windows コンポーネント]\[エクスプローラー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-120">Open the Group Policy editor and go to the **Computer Configuration\Administrative Templates\Windows Components\File Explorer**.</span></span>
2. <span data-ttu-id="6b3d7-121">**[既定の関連付け構成ファイルの設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-121">Select **Set a default associations configuration file**.</span></span>
3. <span data-ttu-id="6b3d7-122">**[ポリシー設定]** をクリックしてから、**[有効]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-122">Click **policy setting**, and then click **Enabled**.</span></span>
4. <span data-ttu-id="6b3d7-123">**[オプション]** で、既定の関連付け構成ファイルの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-123">Under **Options:**, type the location to your default associations configuration file.</span></span>
5. <span data-ttu-id="6b3d7-124">**[OK]** をクリックして、ポリシー設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-124">Click **OK** to save the policy settings.</span></span>

<span data-ttu-id="6b3d7-125">次のスクリーンショットの例は、ターゲット デバイスからアクセス可能なネットワーク共有にある *appassoc.xml* という関連付けファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-125">The example in the next screenshot shows an associations file named *appassoc.xml* on a network share that is accessible from the target device.</span></span>

   ![グループ ポリシーでファイルの関連付けを有効にする](./media/edge-learnmore-make-edge-default-browser/edge-learnmore-app-associations.png)

   > [!NOTE]
   > <span data-ttu-id="6b3d7-127">この設定が有効で、ユーザーのデバイスがドメインに参加している場合は、次回ユーザーがサインオンすると関連付け構成ファイルが処理されます。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-127">If this setting is enabled and the user's device is domain-joined, the associations configuration file is processed the next time the user signs on.</span></span>

## <a name="set-microsoft-edge-as-the-default-browser-on-azure-active-directory-joined-devices"></a><span data-ttu-id="6b3d7-128">Azure Active Directory に参加しているデバイスで Microsoft Edge を既定のブラウザーとして設定する</span><span class="sxs-lookup"><span data-stu-id="6b3d7-128">Set Microsoft Edge as the default browser on Azure Active Directory joined devices</span></span>

<span data-ttu-id="6b3d7-129">Azure Active Directory に参加しているデバイスで Microsoft Edge を既定のブラウザーとして設定するには、例として次のアプリケーション関連付けファイルを使用して、[DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) モバイル デバイス管理設定の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-129">To set Microsoft Edge as the default browser on Azure Active Directory joined devices follow the steps in the [DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) Mobile Device Management setting using the following application association file as an example.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> <span data-ttu-id="6b3d7-130">Microsoft Edge Beta を既定ブラウザーとして設定するには、**ApplicationName** を "Microsoft Edge Beta"、**ProgId** を "MSEdgeBHTML" に設定します。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-130">To set Microsoft Edge Beta as the default browser, set **ApplicationName** to "Microsoft Edge Beta" and **ProgId** to "MSEdgeBHTML".</span></span> <span data-ttu-id="6b3d7-131">Microsoft Edge Dev を既定ブラウザーとして設定するには、**ApplicationName** を "Microsoft Edge Dev"、**ProgId** を "MSEdgeDHTML" に設定します。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-131">To set Microsoft Edge Dev as the default browser, set **ApplicationName** to "Microsoft Edge Dev" and **ProgId** to "MSEdgeDHTML".</span></span>

## <a name="set-microsoft-edge-as-the-default-browser-on-macos"></a><span data-ttu-id="6b3d7-132">macOS で Microsoft Edge を既定のブラウザーとして設定する</span><span class="sxs-lookup"><span data-stu-id="6b3d7-132">Set Microsoft Edge as the default browser on macOS</span></span>

<span data-ttu-id="6b3d7-133">macOS でプログラムによって既定のブラウザーを設定しようとすると、エンド ユーザーに対してプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-133">Attempting to programmatically set the default browser on macOS causes a prompt to appear for the end user.</span></span> <span data-ttu-id="6b3d7-134">このプロンプトは、AppleScript によってのみ自動化できる macOS のセキュリティ機能です。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-134">This prompt is a macOS security feature that can only be automated away by using an AppleScript.</span></span>

<span data-ttu-id="6b3d7-135">この制限により、macOS で Microsoft Edge を既定のブラウザーとして設定するための主要な方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-135">Because of this limitation, there are two main methods for setting Microsoft Edge as the default browser on a macOS.</span></span> <span data-ttu-id="6b3d7-136">最初の方法は、Microsoft Edge が既に既定のブラウザーとして設定されている macOS のイメージを使用してデバイスをフラッシュする方法です。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-136">The first option is to flash the device with an image of macOS where Microsoft Edge has already been set as the default browser.</span></span> <span data-ttu-id="6b3d7-137">もう 1 つの方法は、 [Microsoft Edge を既定のブラウザーとして設定する](./microsoft-edge-policies.md#defaultbrowsersettingenabled) ポリシーを使用する方法です。このポリシーでは、ユーザーに対して Microsoft Edge を既定のブラウザーとして設定するように求めます。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-137">The other option is to use the [Set Microsoft Edge as default browser](./microsoft-edge-policies.md#defaultbrowsersettingenabled) policy, which prompts the user to set Microsoft Edge as the default browser.</span></span>

<span data-ttu-id="6b3d7-138">どちらの方法を使用する場合でも、ユーザーは既定のブラウザーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-138">When using either of these methods, it is still possible for a user to change the default browser.</span></span> <span data-ttu-id="6b3d7-139">これは、既定のブラウザーの設定をプログラムではブロックできないというセキュリティ上の理由によります。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-139">This is because for security reasons, the default browser preference can’t be blocked programmatically.</span></span> <span data-ttu-id="6b3d7-140">このため、Microsoft Edge が既定のブラウザーとして設定されているイメージを作成する場合でも、**Microsoft Edge を既定のブラウザーとして設定する** ポリシー展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-140">For this reason, we recommend that you deploy the **Set Microsoft Edge as default browser** policy even if you create an image with Microsoft Edge as the default browser.</span></span> <span data-ttu-id="6b3d7-141">このポリシーが設定されている場合、次回 Microsoft Edge を開いたときに、ユーザーが Microsoft Edge から既定のブラウザーを変更すると、Microsoft Edge を既定として設定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="6b3d7-141">If the policy is set and a user changes the default browser from Microsoft Edge the next time they open Microsoft Edge, they will be prompted to set it as the default.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b3d7-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b3d7-142">See also</span></span>

- [<span data-ttu-id="6b3d7-143">Microsoft Edge の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="6b3d7-143">Plan your deployment of Microsoft Edge</span></span>](./deploy-edge-plan-deployment.md)
- [<span data-ttu-id="6b3d7-144">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="6b3d7-144">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="6b3d7-145">Microsoft Edge を既定のブラウザーとして設定する (Windows 7、macOS)</span><span class="sxs-lookup"><span data-stu-id="6b3d7-145">Set Microsoft Edge as default browser (Windows 7 and macOS)</span></span>](./microsoft-edge-policies.md#defaultbrowsersettingenabled)
- [<span data-ttu-id="6b3d7-146">Windows 10 – ファイルの関連付けを構成する方法 (IT 担当者向け)</span><span class="sxs-lookup"><span data-stu-id="6b3d7-146">Windows 10 – How to configure file associations for IT Pros?</span></span>](/archive/blogs/windowsinternals/windows-10-how-to-configure-file-associations-for-it-pros)
- [<span data-ttu-id="6b3d7-147">既定のアプリケーションの関連付けのエクスポートまたはインポート</span><span class="sxs-lookup"><span data-stu-id="6b3d7-147">Export or Import Default Application Associations</span></span>](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)
  - [<span data-ttu-id="6b3d7-148">DISM の概要</span><span class="sxs-lookup"><span data-stu-id="6b3d7-148">DISM Overview</span></span>](/windows-hardware/manufacture/desktop/what-is-dism)
  - [<span data-ttu-id="6b3d7-149">DISM - 展開イメージのサービスと管理</span><span class="sxs-lookup"><span data-stu-id="6b3d7-149">DISM - Deployment Image Servicing and Management</span></span>](/windows-hardware/manufacture/desktop/dism---deployment-image-servicing-and-management-technical-reference-for-windows)