---
title: Active Directory (AD) ユーザー用のオンプレミス同期
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 02/12/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Active Directory (AD) ユーザー用のオンプレミス同期
ms.openlocfilehash: 820188db94f4ab2bc9b1ad659c22c324bcea145b
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11448051"
---
# <a name="on-premises-sync-for-active-directory-ad-users"></a><span data-ttu-id="520ef-103">Active Directory (AD) ユーザー用のオンプレミス同期</span><span class="sxs-lookup"><span data-stu-id="520ef-103">On-premises sync for Active Directory (AD) users</span></span>

<span data-ttu-id="520ef-104">この記事では、Active Directory (AD) ユーザーが Microsoft クラウド サービスに接続することなく、Microsoft Edge のお気に入りや設定をコンピュータ間でローミングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="520ef-104">This article explains how Active Directory (AD) users can roam Microsoft Edge favorites and settings between computers without connecting to Microsoft cloud services.</span></span>

> [!NOTE]
> <span data-ttu-id="520ef-105">この記事は Microsoft Edge version 85 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="520ef-105">This article applies to Microsoft Edge version 85 or later.</span></span>

## <a name="introduction"></a><span data-ttu-id="520ef-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="520ef-106">Introduction</span></span>

<span data-ttu-id="520ef-107">Microsoft Edge でユーザー データを同期するには、通常 Microsoft アカウントか Azure Active Directory (Azure AD) アカウントのいずれかと、Microsoft クラウド サービスへの接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="520ef-107">Syncing user data in Microsoft Edge normally requires either a Microsoft Account or an Azure Active Directory (Azure AD) account, and a connection to Microsoft cloud services.</span></span> <span data-ttu-id="520ef-108">オンプレミス同期を利用すれば、Microsoft Edge で Active Directory ユーザーのお気に入りや設定をファイルに保存し、異なるコンピューター間で移動させることができます。</span><span class="sxs-lookup"><span data-stu-id="520ef-108">With on-premises sync, Microsoft Edge saves an Active Directory user's favorites and settings to a file that can be moved between different computers.</span></span> <span data-ttu-id="520ef-109">オンプレミス同期は、使用を許可しているプロファイルについてはクラウド同期の妨げにはなりません。</span><span class="sxs-lookup"><span data-stu-id="520ef-109">On-premises sync doesn't interfere with cloud syncing for those profiles that allow it.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="520ef-110">動作のしくみ</span><span class="sxs-lookup"><span data-stu-id="520ef-110">How it works</span></span>

<span data-ttu-id="520ef-111">Microsoft Edge では、クラウド同期には使用できない Active Directory (AD) アカウントとプロファイルを関連付けることができます。オンプレミス同期を有効にすると、AD プロファイルのデータは profile.pb という名前のファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="520ef-111">Microsoft Edge allows profiles to be associated with Active Directory (AD) accounts, which can't be used with cloud sync. When on-premises sync is enabled, the data from the AD profile is saved to a file named profile.pb.</span></span> <span data-ttu-id="520ef-112">既定では、このファイルは *%APPDATA%/Microsoft/Edge* に保存されます。</span><span class="sxs-lookup"><span data-stu-id="520ef-112">By default, this file is stored in *%APPDATA%/Microsoft/Edge*.</span></span> <span data-ttu-id="520ef-113">このファイルが作成された後は、異なるコンピューター間で移動することができるようになり、ユーザー データはそれぞれのコンピューターで読み書きされます。</span><span class="sxs-lookup"><span data-stu-id="520ef-113">After this file is written, it can be moved between different computers, and user data will be read and written on each computer.</span></span> <span data-ttu-id="520ef-114">Microsoft Edge は、このファイルからの読み取りと書き込みのみを行います。必要に応じてファイルを移動させるのは管理者の責任となります。</span><span class="sxs-lookup"><span data-stu-id="520ef-114">Microsoft Edge only reads and writes from this file; it is the admin's responsibility to ensure that the file is moved as needed.</span></span>

## <a name="use-on-premises-sync"></a><span data-ttu-id="520ef-115">オンプレミス同期を使用する</span><span class="sxs-lookup"><span data-stu-id="520ef-115">Use on-premises sync</span></span>

<span data-ttu-id="520ef-116">オンプレミス同期を使用するには、オンプレミス同期を有効にし、プロファイルを AD アカウントに関連付ける必要があり、オプションでユーザー データの場所を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="520ef-116">To use on-premises sync, you have to enable it, associate a profile with an AD account, and optionally, change the location of the user data.</span></span>

### <a name="enable-on-premises-sync"></a><span data-ttu-id="520ef-117">オンプレミス同期を有効にする</span><span class="sxs-lookup"><span data-stu-id="520ef-117">Enable on-premises sync</span></span>

<span data-ttu-id="520ef-118">Microsoft Edge でオンプレミス同期を有効にするには、[RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled) ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="520ef-118">To enable on-premises sync in Microsoft Edge, configure the [RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled) policy.</span></span>

### <a name="ensure-that-a-profile-is-associated-with-an-active-directory-account"></a><span data-ttu-id="520ef-119">プロファイルが Active Directory アカウントに関連付けられていることを確認する</span><span class="sxs-lookup"><span data-stu-id="520ef-119">Ensure that a profile is associated with an Active Directory account</span></span>

<span data-ttu-id="520ef-120">オンプレミス同期は、Active Directory (AD) アカウントに関連付けられているプロファイルでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="520ef-120">On-premises sync only works with the profile associated with an Active Directory (AD) account.</span></span> <span data-ttu-id="520ef-121">そういったプロファイルが存在しない場合には、オンプレミス同期は機能しません。</span><span class="sxs-lookup"><span data-stu-id="520ef-121">If no such profile exists, on-premises sync will not function.</span></span> <span data-ttu-id="520ef-122">ユーザーが AD アカウントを使用してサインインできるようにするには、[ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin) ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="520ef-122">To ensure that users sign on with an AD account, configure the [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin) policy.</span></span> <span data-ttu-id="520ef-123">オンプレミスの同期の場合、Microsoft Edge はユーザー データの ID を確立するために AD にのみ依存します。Microsoft Edge がオンプレミスのデータの読み取りと書き込みを行う方法と、管理者が AD ユーザーのローミングを構成した方法との間に直接的な関係はありません。</span><span class="sxs-lookup"><span data-stu-id="520ef-123">For on-premises sync, Microsoft Edge only relies on AD to establish an identity for the user data, and there's no direct relationship between how Microsoft Edge reads and writes on-premises data to how the admin has configured roaming for an AD user.</span></span>

### <a name="change-the-location-of-the-user-data-optional"></a><span data-ttu-id="520ef-124">ユーザー データの場所を変更する (オプション)</span><span class="sxs-lookup"><span data-stu-id="520ef-124">Change the location of the user data (optional)</span></span>

<span data-ttu-id="520ef-125">既定では、ユーザー データは *%APPDATA%/Microsoft/Edge* の **profile.pb** という名前のファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="520ef-125">By default, the user data is stored in a filed named **profile.pb** in *%APPDATA%/Microsoft/Edge*.</span></span> <span data-ttu-id="520ef-126">このファイルの場所を変更するには、[RoamingProfileLocation](./microsoft-edge-policies.md#roamingprofilelocation) ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="520ef-126">To change the location of this file, configure the [RoamingProfileLocation](./microsoft-edge-policies.md#roamingprofilelocation) policy.</span></span>

## <a name="changes-in-the-user-experience-when-on-premises-sync-is-enabled"></a><span data-ttu-id="520ef-127">オンプレミス同期が有効になっている場合のユーザー エクスペリエンスの変更</span><span class="sxs-lookup"><span data-stu-id="520ef-127">Changes in the user experience when on-premises sync is enabled</span></span>

<span data-ttu-id="520ef-128">オンプレミス同期を有効にすると、ユーザーは同期を有効にするように要求されません。また、ユーザーは同期設定で同期をオフにすることができず、オンプレミス同期でサポートされていない同期の種類をオンにすることもできません。</span><span class="sxs-lookup"><span data-stu-id="520ef-128">When on-premises sync is enabled, users won't be asked to enable sync. In addition, users can't turn off sync in Sync settings, and they can't turn on sync types that aren't supported by on-premises sync.</span></span>

## <a name="on-premises-sync-usage-notes"></a><span data-ttu-id="520ef-129">オンプレミス同期の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="520ef-129">On-premises sync usage notes</span></span>

### <a name="running-cloud-sync-and-on-premises-sync-on-the-same-computer"></a><span data-ttu-id="520ef-130">クラウド同期とオンプレミス同期を同じコンピューター上で実行する</span><span class="sxs-lookup"><span data-stu-id="520ef-130">Running cloud sync and on-premises sync on the same computer</span></span>

<span data-ttu-id="520ef-131">オンプレミス同期がクラウド同期の妨げになることはありません。Microsoft Edge にクラウドと同期している複数の Microsoft アカウントまたは Azure Active Directory プロファイルがある場合、オンプレミス同期が有効になっている間は、これらのプロファイルは引き続き同期されます。</span><span class="sxs-lookup"><span data-stu-id="520ef-131">On-premises sync doesn't interfere with cloud sync. If Microsoft Edge has multiple Microsoft Account or Azure Active Directory profiles that sync to the cloud, these profiles will continue to sync while on-premises sync is enabled.</span></span>

### <a name="running-microsoft-edge-on-more-than-one-computer-at-a-time-isnt-recommended"></a><span data-ttu-id="520ef-132">複数のコンピューターで Microsoft Edge を同時に実行することはお勧めできません</span><span class="sxs-lookup"><span data-stu-id="520ef-132">Running Microsoft Edge on more than one computer at a time isn't recommended</span></span>

<span data-ttu-id="520ef-133">オンプレミス同期はユーザー データのファイルをコンピューター間で移動させることによって機能するため、オンプレミス同期では同時に実行される複数のセッションでの変更は同期されません。</span><span class="sxs-lookup"><span data-stu-id="520ef-133">Because on-premises sync works by moving a user data file between computers, on-premises sync doesn't sync changes between simultaneous sessions.</span></span> <span data-ttu-id="520ef-134">この理由から、オンプレミス同期は一度に 1 台のコンピューター上で使用する場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="520ef-134">For this reason, on-premises sync works best when used on one computer at a time.</span></span> <span data-ttu-id="520ef-135">オンプレミスのセッションが同時に実行される場合、次にブラウザー セッションを開始したときに、いずれかのコンピューター上のデータが他のコンピューター上のデータによって予期せず上書きされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="520ef-135">If there are simultaneous on-premises sessions running, data on any of the computers may be unexpectedly overwritten by data from another computer the next time you start a browser session.</span></span>

> [!NOTE]
> <span data-ttu-id="520ef-136">オンプレミス同期が有効になっている場合、Microsoft Edge では **profile.pb** ファイルがロックされます。</span><span class="sxs-lookup"><span data-stu-id="520ef-136">Microsoft Edge locks the **profile.pb** file when on-premises sync is enabled.</span></span> <span data-ttu-id="520ef-137">フォルダー リダイレクトを使用して 1 つの **profile.pb** ファイルを異なるコンピューター間で共有する場合には、そのファイルを使用する Microsoft Edge インスタンスは 1 つのみが起動可能です。</span><span class="sxs-lookup"><span data-stu-id="520ef-137">If folder redirection is used to share a single **profile.pb** file between different computers, then only one instance of Microsoft Edge using that file can be started.</span></span>

### <a name="using-other-sync-policies-with-on-premises-sync"></a><span data-ttu-id="520ef-138">オンプレミスの同期を使用したその他の同期ポリシーの使用</span><span class="sxs-lookup"><span data-stu-id="520ef-138">Using other sync policies with on-premises sync</span></span>

<span data-ttu-id="520ef-139">[SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) ポリシーを使用して、お気に入りや設定の同期を必要に応じて選択的に無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="520ef-139">The [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) policy can be used to selectively disable either favorites or settings sync if desired.</span></span> <span data-ttu-id="520ef-140">[SyncDisabled](./microsoft-edge-policies.md#syncdisabled) ポリシーはオンプレミスの同期には影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="520ef-140">The [SyncDisabled](./microsoft-edge-policies.md#syncdisabled) policy has no impact on on-premises sync.</span></span>

## <a name="see-also"></a><span data-ttu-id="520ef-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="520ef-141">See also</span></span>

- [<span data-ttu-id="520ef-142">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="520ef-142">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="520ef-143">Microsoft Edge と Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="520ef-143">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="520ef-144">Microsoft Edge エンタープライズの同期</span><span class="sxs-lookup"><span data-stu-id="520ef-144">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)