---
title: Microsoft Edge セキュリティの概要
ms.author: srugh
author: srugh
manager: seanlyn
ms.date: 04/29/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge セキュリティの展開概要
ms.openlocfilehash: f22f2dcbace00cd535d201950c2af488c708525b
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980536"
---
# <span data-ttu-id="af0f1-103">Microsoft Edge セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="af0f1-103">Overview of Microsoft Edge security</span></span>
  
<span data-ttu-id="af0f1-104">企業の IT 管理者は、企業ネットワークやデバイスを悪意のある攻撃から保護し、企業データへの不正なアクセスや漏洩を防いでいます。同時に、セキュリティに関する多種多様な課題が常にあり、以前から存在する問題にも新たに出現した脅威に対しても対応を迫られています。</span><span class="sxs-lookup"><span data-stu-id="af0f1-104">IT admins in the enterprise are constantly facing a myriad of existing and emerging security challenges while protecting the corporate network and devices from malicious attacks and preventing unauthorized access and leaks of corporate data.</span></span> <span data-ttu-id="af0f1-105">Microsoft Edge には、このような課題に対処するために、ネイティブに構築された固有の機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="af0f1-105">Microsoft Edge provides several natively built, unique capabilities that help address these challenges.</span></span>

> [!NOTE]
> <span data-ttu-id="af0f1-106">この記事は Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="af0f1-106">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="af0f1-107">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="af0f1-107">Conditional Access</span></span>

<span data-ttu-id="af0f1-108">クラウド リソースを管理する場合、クラウドのセキュリティで重要になる要素は ID とアクセスです。</span><span class="sxs-lookup"><span data-stu-id="af0f1-108">A key aspect of cloud security is identity and access when it comes to managing your cloud resources.</span></span> <span data-ttu-id="af0f1-109">モバイル ファースト、クラウド ファーストの環境では、ユーザーはどこからでもさまざまなデバイスとアプリを使用して、組織のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="af0f1-109">In a mobile-first, cloud-first world, users can access your organization's resources using a variety of devices and apps from anywhere.</span></span> <span data-ttu-id="af0f1-110">このため、どのユーザーがリソースにアクセスできるかという点を考えるだけでは不十分です。</span><span class="sxs-lookup"><span data-stu-id="af0f1-110">As a result of this, just focusing on who can access a resource is not sufficient.</span></span> <span data-ttu-id="af0f1-111">リソースへのアクセス方法についても考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af0f1-111">You also need to factor in how a resource is accessed.</span></span> <span data-ttu-id="af0f1-112">Azure Active Directory (Azure AD) の条件付きアクセスは、セキュリティと生産性のバランスを制御するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="af0f1-112">Azure Active Directory (Azure AD) Conditional Access helps you master the balance between security and productivity.</span></span>

### <span data-ttu-id="af0f1-113">Microsoft Edge で条件付きアクセスによって保護されたリソースにアクセスする</span><span class="sxs-lookup"><span data-stu-id="af0f1-113">Accessing Conditional Access protected resources in Microsoft Edge</span></span>

<span data-ttu-id="af0f1-114">Microsoft Edge では、Azure AD 条件付きアクセスがネイティブにサポートされています。</span><span class="sxs-lookup"><span data-stu-id="af0f1-114">Microsoft Edge natively supports Azure AD Conditional Access.</span></span> <span data-ttu-id="af0f1-115">別の拡張機能をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="af0f1-115">There's no need to install a separate extension.</span></span> <span data-ttu-id="af0f1-116">エンタープライズ Azure AD 資格情報を使用して Microsoft Edge プロファイルにサインインすると、条件付きアクセスを使用して保護されたエンタープライズ クラウド リソースへのシームレスなアクセスが、Microsoft Edge によって許可されます。</span><span class="sxs-lookup"><span data-stu-id="af0f1-116">When you're signed into a Microsoft Edge profile with enterprise Azure AD credentials, Microsoft Edge allows seamless access to enterprise cloud resources protected using Conditional Access.</span></span>

<span data-ttu-id="af0f1-117">準拠デバイスで、リソースにアクセスする ID は、プロファイルの ID と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="af0f1-117">On a compliant device, the identity accessing the resource should match the identity on the profile.</span></span>  <span data-ttu-id="af0f1-118">一致していない場合は、次のスクリーンショットに示されているようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="af0f1-118">If it doesn't, you'll see a message like the one in the next screenshot.</span></span> <span data-ttu-id="af0f1-119">スクリーンショットの例で、"testadmin@evostsoneboxtest.com" は、リソースにアクセスするために必要なサインイン アカウントです。</span><span class="sxs-lookup"><span data-stu-id="af0f1-119">In the screenshot example, "testadmin@evostsoneboxtest.com" is the sign-in account needed to access the resource.</span></span>

![ブラウザーに表示された、条件付きアクセスのメッセージ](./media/edge-security/microsoft-edge-security-conditional-access.png)

<span data-ttu-id="af0f1-121">続行するには、必要なプロファイル (ある場合) に切り替えるか、ID が一致するプロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af0f1-121">To continue, you have to switch to the required profile (if you have one) or create a profile with matching identity.</span></span>

<span data-ttu-id="af0f1-122">サインインしてプロファイルを使用するには、ブラウザーの右上隅にあるアカウントの画像をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af0f1-122">To sign in and work with your profile, click the account picture in the top right corner of the browser.</span></span> <span data-ttu-id="af0f1-123">ドロップダウン メニューを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="af0f1-123">You can use the dropdown menu to:</span></span>

- <span data-ttu-id="af0f1-124">別のプロファイルを選択する。</span><span class="sxs-lookup"><span data-stu-id="af0f1-124">Select another profile.</span></span> <span data-ttu-id="af0f1-125">プロファイル名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af0f1-125">Click the profile name.</span></span>
- <span data-ttu-id="af0f1-126">プロファイルを作成する。</span><span class="sxs-lookup"><span data-stu-id="af0f1-126">Create a profile.</span></span> <span data-ttu-id="af0f1-127">**[プロファイルの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af0f1-127">Click **Add a profile**.</span></span>
- <span data-ttu-id="af0f1-128">プロファイルを管理する。</span><span class="sxs-lookup"><span data-stu-id="af0f1-128">Manage your profiles.</span></span> <span data-ttu-id="af0f1-129">**[プロファイルの設定を管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af0f1-129">Click **Manage profile settings**.</span></span>

<span data-ttu-id="af0f1-130">このサポートは、サポートされているすべてのバージョンの Windows および macOS を含めて、すべてのプラットフォームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="af0f1-130">This support is available across all platforms, including all supported versions of Windows and macOS.</span></span>

### <span data-ttu-id="af0f1-131">Azure Active Directory の条件付きアクセスを展開する方法</span><span class="sxs-lookup"><span data-stu-id="af0f1-131">How to deploy Conditional Access in Azure Active Directory</span></span>

<span data-ttu-id="af0f1-132">[条件付きアクセスの展開に関するページ](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)には、Azure Active Directory での条件付きアクセスの展開に役立つ詳細なガイドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="af0f1-132">[Deploy Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) provides a detailed guide to help deploy Conditional Access in Azure Active Directory.</span></span>

## <span data-ttu-id="af0f1-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="af0f1-133">See also</span></span>

- [<span data-ttu-id="af0f1-134">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="af0f1-134">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="af0f1-135">ビデオ - セキュリティ、互換性、管理の容易性</span><span class="sxs-lookup"><span data-stu-id="af0f1-135">Video: Security, compatibility, and manageability</span></span>](/microsoft-edge-video-security-compatibility-manageability.md)
