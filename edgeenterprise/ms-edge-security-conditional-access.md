---
title: Microsoft Edge と条件付きアクセス
ms.author: srugh
author: srugh
manager: seanlyn
ms.date: 10/02/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge と条件付きアクセス
ms.openlocfilehash: 898a86c8c268a8c46e80dbd5ef3a435c300fb04e
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447141"
---
# <a name="microsoft-edge-and-conditional-access"></a><span data-ttu-id="3ace5-103">Microsoft Edge と条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="3ace5-103">Microsoft Edge and Conditional Access</span></span>
  
<span data-ttu-id="3ace5-104">この記事では、Microsoft Edge が条件付きアクセスをサポートする方法と、条件付きアクセスによって保護されているリソースにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ace5-104">This article describes how Microsoft Edge supports Conditional Access, and how to access resources protected by Conditional Access.</span></span>

> [!NOTE]
> <span data-ttu-id="3ace5-105">この記事は Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ace5-105">This article applies to Microsoft Edge version 77 or later.</span></span>

<span data-ttu-id="3ace5-106">クラウド リソースを管理する場合、クラウドのセキュリティで重要になる要素は ID とアクセスです。</span><span class="sxs-lookup"><span data-stu-id="3ace5-106">A key aspect of cloud security is identity and access when it comes to managing your cloud resources.</span></span> <span data-ttu-id="3ace5-107">モバイル ファースト、クラウド ファーストの環境では、ユーザーはどこからでもさまざまなデバイスとアプリを使用して、組織のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3ace5-107">In a mobile-first, cloud-first world, users can access your organization's resources using a variety of devices and apps from anywhere.</span></span> <span data-ttu-id="3ace5-108">このため、どのユーザーがリソースにアクセスできるかという点を考えるだけでは不十分です。</span><span class="sxs-lookup"><span data-stu-id="3ace5-108">As a result of this, just focusing on who can access a resource is not sufficient.</span></span> <span data-ttu-id="3ace5-109">リソースへのアクセス方法についても考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ace5-109">You also need to factor in how a resource is accessed.</span></span> <span data-ttu-id="3ace5-110">Azure Active Directory (Azure AD) の条件付きアクセスは、セキュリティと生産性のバランスを制御するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3ace5-110">Azure Active Directory (Azure AD) Conditional Access helps you master the balance between security and productivity.</span></span>

## <a name="accessing-conditional-access-protected-resources-in-microsoft-edge"></a><span data-ttu-id="3ace5-111">Microsoft Edge で条件付きアクセスによって保護されたリソースにアクセスする</span><span class="sxs-lookup"><span data-stu-id="3ace5-111">Accessing Conditional Access protected resources in Microsoft Edge</span></span>

<span data-ttu-id="3ace5-112">Microsoft Edge では、Azure AD 条件付きアクセスがネイティブにサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3ace5-112">Microsoft Edge natively supports Azure AD Conditional Access.</span></span> <span data-ttu-id="3ace5-113">別の拡張機能をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3ace5-113">There's no need to install a separate extension.</span></span> <span data-ttu-id="3ace5-114">エンタープライズ Azure AD 資格情報を使用して Microsoft Edge プロファイルにサインインすると、条件付きアクセスを使用して保護されたエンタープライズ クラウド リソースへのシームレスなアクセスが、Microsoft Edge によって許可されます。</span><span class="sxs-lookup"><span data-stu-id="3ace5-114">When you're signed into a Microsoft Edge profile with enterprise Azure AD credentials, Microsoft Edge allows seamless access to enterprise cloud resources protected using Conditional Access.</span></span>

<span data-ttu-id="3ace5-115">準拠デバイスで、リソースにアクセスする ID は、プロファイルの ID と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ace5-115">On a compliant device, the identity accessing the resource should match the identity on the profile.</span></span>  <span data-ttu-id="3ace5-116">一致していない場合は、次のスクリーンショットに示されているようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ace5-116">If it doesn't, you'll see a message like the one in the next screenshot.</span></span> <span data-ttu-id="3ace5-117">スクリーンショットの例で、"testadmin@evostsoneboxtest.com" は、リソースにアクセスするために必要なサインイン アカウントです。</span><span class="sxs-lookup"><span data-stu-id="3ace5-117">In the screenshot example, "testadmin@evostsoneboxtest.com" is the sign-in account needed to access the resource.</span></span>

![ブラウザーに表示された、条件付きアクセスのメッセージ](./media/edge-security/microsoft-edge-security-conditional-access.png)

<span data-ttu-id="3ace5-119">続行するには、必要なプロファイル (ある場合) に切り替えるか、ID が一致するプロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ace5-119">To continue, you have to switch to the required profile (if you have one) or create a profile with matching identity.</span></span>

<span data-ttu-id="3ace5-120">サインインしてプロファイルを使用するには、ブラウザーの右上隅にあるアカウントの画像をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ace5-120">To sign in and work with your profile, click the account picture in the top right corner of the browser.</span></span> <span data-ttu-id="3ace5-121">ドロップダウン メニューを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="3ace5-121">You can use the dropdown menu to:</span></span>

- <span data-ttu-id="3ace5-122">別のプロファイルを選択する。</span><span class="sxs-lookup"><span data-stu-id="3ace5-122">Select another profile.</span></span> <span data-ttu-id="3ace5-123">プロファイル名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ace5-123">Click the profile name.</span></span>
- <span data-ttu-id="3ace5-124">プロファイルを作成する。</span><span class="sxs-lookup"><span data-stu-id="3ace5-124">Create a profile.</span></span> <span data-ttu-id="3ace5-125">**[プロファイルの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ace5-125">Click **Add a profile**.</span></span>
- <span data-ttu-id="3ace5-126">プロファイルを管理する。</span><span class="sxs-lookup"><span data-stu-id="3ace5-126">Manage your profiles.</span></span> <span data-ttu-id="3ace5-127">**[プロファイルの設定を管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ace5-127">Click **Manage profile settings**.</span></span>

<span data-ttu-id="3ace5-128">このサポートは、サポートされているすべてのバージョンの Windows および macOS を含めて、すべてのプラットフォームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ace5-128">This support is available across all platforms, including all supported versions of Windows and macOS.</span></span>

### <a name="how-to-deploy-conditional-access-in-azure-active-directory"></a><span data-ttu-id="3ace5-129">Azure Active Directory の条件付きアクセスを展開する方法</span><span class="sxs-lookup"><span data-stu-id="3ace5-129">How to deploy Conditional Access in Azure Active Directory</span></span>

<span data-ttu-id="3ace5-130">[条件付きアクセスの展開に関するページ](/azure/active-directory/conditional-access/plan-conditional-access)には、Azure Active Directory での条件付きアクセスの展開に役立つ詳細なガイドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3ace5-130">[Deploy Conditional Access](/azure/active-directory/conditional-access/plan-conditional-access) provides a detailed guide to help deploy Conditional Access in Azure Active Directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ace5-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ace5-131">See also</span></span>

- [<span data-ttu-id="3ace5-132">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="3ace5-132">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="3ace5-133">ビデオ - セキュリティ、互換性、管理の容易性</span><span class="sxs-lookup"><span data-stu-id="3ace5-133">Video: Security, compatibility, and manageability</span></span>](/microsoft-edge-video-security-compatibility-manageability.md)