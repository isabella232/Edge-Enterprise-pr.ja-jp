---
title: Microsoft Edge チャネル概要
ms.author: srugh
author: srugh
manager: seanlynd
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge チャネル概要
ms.openlocfilehash: 7d1fb72b458569cb4e4c6f44a6d89be7f65984df
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641993"
---
# <a name="overview-of-the-microsoft-edge-channels"></a><span data-ttu-id="40919-103">Microsoft Edge チャネルの概要</span><span class="sxs-lookup"><span data-stu-id="40919-103">Overview of the Microsoft Edge channels</span></span>

<span data-ttu-id="40919-104">次のバージョンの Microsoft Edge の利点の 1 つは、Microsoft が定期的に新機能を提供できることです。</span><span class="sxs-lookup"><span data-stu-id="40919-104">One of the benefits of the next version of Microsoft Edge is that Microsoft can provide new features on a regular basis.</span></span> <span data-ttu-id="40919-105">ただし、組織内のユーザーに Microsoft Edge を展開する管理者は、ユーザーがこれらの新機能を受け取る頻度を細かく制御できる方が良い場合があります。</span><span class="sxs-lookup"><span data-stu-id="40919-105">However, as the admin who deploys Microsoft Edge to the users in your organization, you might want to have more control over how often your users get these new features.</span></span> <span data-ttu-id="40919-106">Microsoft では、Microsoft Edge を新しい機能で更新する頻度を制御するために、チャネルと呼ばれる 4 つのオプションを提供しています。</span><span class="sxs-lookup"><span data-stu-id="40919-106">Microsoft provides you four options, called channels, to control how often Microsoft Edge is updated with new features.</span></span> <span data-ttu-id="40919-107">ここでは、これら 4 つのオプションの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="40919-107">Here's an overview of the four options.</span></span>

<span data-ttu-id="40919-108">各チャネルのサポートの詳細については、「[Microsoft Edge のライフサイクル](/deployedge/microsoft-edge-support-lifecycle)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40919-108">For more information on support for each channel read: [Microsoft Edge Lifecycle](/deployedge/microsoft-edge-support-lifecycle)</span></span>
  
> [!NOTE]
> <span data-ttu-id="40919-109">この記事は Microsoft Edge バージョン 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="40919-109">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="channel-overview"></a><span data-ttu-id="40919-110">チャネルの概要</span><span class="sxs-lookup"><span data-stu-id="40919-110">Channel overview</span></span>

|<span data-ttu-id="40919-111">チャネル</span><span class="sxs-lookup"><span data-stu-id="40919-111">Channel</span></span>|<span data-ttu-id="40919-112">主な目的</span><span class="sxs-lookup"><span data-stu-id="40919-112">Primary purpose</span></span>|<span data-ttu-id="40919-113">新機能に更新される頻度</span><span class="sxs-lookup"><span data-stu-id="40919-113">How often updated with new features</span></span>|<span data-ttu-id="40919-114">サポート</span><span class="sxs-lookup"><span data-stu-id="40919-114">Supported?</span></span>|
|:---:|---|:---:|:---:|
|[<span data-ttu-id="40919-115">Stable</span><span class="sxs-lookup"><span data-stu-id="40919-115">Stable</span></span>](#stable-channel)|<span data-ttu-id="40919-116">広範な展開</span><span class="sxs-lookup"><span data-stu-id="40919-116">Broad Deployment</span></span>|<span data-ttu-id="40919-117">6 週間に 1 回以上</span><span class="sxs-lookup"><span data-stu-id="40919-117">~6 weeks</span></span>|<span data-ttu-id="40919-118">あり</span><span class="sxs-lookup"><span data-stu-id="40919-118">Yes</span></span>|
|[<span data-ttu-id="40919-119">Beta</span><span class="sxs-lookup"><span data-stu-id="40919-119">Beta</span></span>](#beta-channel)|<span data-ttu-id="40919-120">組織内での代表的な対象での検証</span><span class="sxs-lookup"><span data-stu-id="40919-120">Representative validation in the organization</span></span>|<span data-ttu-id="40919-121">6 週間に 1 回以上</span><span class="sxs-lookup"><span data-stu-id="40919-121">~6 weeks</span></span>|<span data-ttu-id="40919-122">あり</span><span class="sxs-lookup"><span data-stu-id="40919-122">Yes</span></span>|
|[<span data-ttu-id="40919-123">Dev</span><span class="sxs-lookup"><span data-stu-id="40919-123">Dev</span></span>](#dev-channel)|<span data-ttu-id="40919-124">計画と開発</span><span class="sxs-lookup"><span data-stu-id="40919-124">Planning and developing</span></span>|<span data-ttu-id="40919-125">1 週間に 1 回</span><span class="sxs-lookup"><span data-stu-id="40919-125">Weekly</span></span>|<span data-ttu-id="40919-126">なし</span><span class="sxs-lookup"><span data-stu-id="40919-126">No</span></span>|
|[<span data-ttu-id="40919-127">Canary</span><span class="sxs-lookup"><span data-stu-id="40919-127">Canary</span></span>](#canary-channel)|<span data-ttu-id="40919-128">試験的な内容</span><span class="sxs-lookup"><span data-stu-id="40919-128">Bleeding edge content</span></span>|<span data-ttu-id="40919-129">毎日</span><span class="sxs-lookup"><span data-stu-id="40919-129">Daily</span></span>|<span data-ttu-id="40919-130">なし</span><span class="sxs-lookup"><span data-stu-id="40919-130">No</span></span>|

<span data-ttu-id="40919-131">どの更新チャネルをユーザーに展開するかについては、Microsoft Edge の更新されたバージョンでテストする必要がある、ユーザーが使用中の基幹業務アプリケーションの数など、いくつかの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="40919-131">Which update channel you decide to deploy to your users depends on several factors, such as how many line of business applications the user leverages and that you need to test any time they have an updated version of Microsoft Edge.</span></span> <span data-ttu-id="40919-132">この決定を行うには、Microsoft Edge で利用可能な 4 つの更新チャネルに関する次の情報をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="40919-132">To help you make this decision, review the following information about the four update channels that are available for Microsoft Edge.</span></span>

### <a name="stable-channel"></a><span data-ttu-id="40919-133">Stable チャネル</span><span class="sxs-lookup"><span data-stu-id="40919-133">Stable Channel</span></span>

<span data-ttu-id="40919-134">Stable チャネルは、組織での広範な展開を目的としており、ほとんどのユーザーに適したチャネルです。</span><span class="sxs-lookup"><span data-stu-id="40919-134">The Stable Channel is intended for broad deployment in your organization, and it is the channel that most users should be on.</span></span> <span data-ttu-id="40919-135">これはすべてのチャネルの中で最も安定しており、前の Beta チャネル リリースに含まれていた機能セットを安定させたものです。</span><span class="sxs-lookup"><span data-stu-id="40919-135">It is the most stable of the channels and is the a result of the stabilization of the feature set available in the prior Beta Channel release.</span></span> <span data-ttu-id="40919-136">約 6 週間ごとに新機能がリリースされます。</span><span class="sxs-lookup"><span data-stu-id="40919-136">New features ship about every 6 weeks.</span></span> <span data-ttu-id="40919-137">必要に応じて、セキュリティ更新プログラムと品質更新プログラムがリリースされます。</span><span class="sxs-lookup"><span data-stu-id="40919-137">Security and quality updates ship as needed.</span></span> <span data-ttu-id="40919-138">Stable チャネルからのリリースは、チャネルからの次のリリースが利用可能になるまでサービスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="40919-138">A release from the Stable Channel is serviced until the next release from the channel is available.</span></span>

### <a name="beta-channel"></a><span data-ttu-id="40919-139">Beta チャネル</span><span class="sxs-lookup"><span data-stu-id="40919-139">Beta Channel</span></span>

<span data-ttu-id="40919-140">Beta チャネルは、組織内の実稼働環境への展開を目的とし、代表的なユーザーのグループを対象としています。</span><span class="sxs-lookup"><span data-stu-id="40919-140">The Beta Channel is intended for production deployment in your organization to a representative sample set of users.</span></span> <span data-ttu-id="40919-141">これはサポートされているリリースであり、Beta からの各リリースは、このチャネルからの次のリリースが利用可能になるまでサービスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="40919-141">It is a supported release, and each release from Beta is serviced until the next release from this channel is available.</span></span> <span data-ttu-id="40919-142">ご利用環境で想定どおりに動作するかどうかを検証するための絶好の機会であり、問題が発生した場合は、リリースが Stable チャネルに公開される前に報告することができます。</span><span class="sxs-lookup"><span data-stu-id="40919-142">This is a great opportunity to validate that things work as expected in your environment, and if you encounter an issue have it remediated prior to the release going publishing to the Stable Channel.</span></span> <span data-ttu-id="40919-143">約 6 週間ごとに新機能がリリースされます。</span><span class="sxs-lookup"><span data-stu-id="40919-143">New features ship about every 6 weeks.</span></span> <span data-ttu-id="40919-144">必要に応じて、セキュリティ更新プログラムと品質更新プログラムがリリースされます。</span><span class="sxs-lookup"><span data-stu-id="40919-144">Security and quality updates ship as needed.</span></span>

### <a name="dev-channel"></a><span data-ttu-id="40919-145">Dev チャネル</span><span class="sxs-lookup"><span data-stu-id="40919-145">Dev Channel</span></span>

<span data-ttu-id="40919-146">Dev チャネルは、Canary チャネルよりも高い品質で、Microsoft Edge の最新機能を計画および開発することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="40919-146">The Dev Channel is intended to help you plan and develop with the latest capabilities of Microsoft Edge, but with higher quality than the Canary Channel.</span></span> <span data-ttu-id="40919-147">このチャネルでは、次の Beta リリースの前にいち早く新機能を確認し、準備できます。</span><span class="sxs-lookup"><span data-stu-id="40919-147">This is your opportunity to get an early look at what is coming next and prepare for the next Beta release.</span></span>

### <a name="canary-channel"></a><span data-ttu-id="40919-148">Canary チャネル</span><span class="sxs-lookup"><span data-stu-id="40919-148">Canary Channel</span></span>

<span data-ttu-id="40919-149">Canary チャネルは毎日リリースされ、すべてのチャネル内でも最先端で試験的な内容です。</span><span class="sxs-lookup"><span data-stu-id="40919-149">The Canary Channel ships daily and is the most bleeding edge of all the channels.</span></span> <span data-ttu-id="40919-150">ここには、最新の投資内容が反映されます。</span><span class="sxs-lookup"><span data-stu-id="40919-150">If you want access to the newest investments then they will appear here first.</span></span> <span data-ttu-id="40919-151">リリース頻度の性質上、長い目で見ると問題が発生することもあるため、Canary リリースを使用する場合は、別のチャネルを並行インストールすることもご検討ください。</span><span class="sxs-lookup"><span data-stu-id="40919-151">Because of the nature of this cadence problems will arise overtime, so you may want another channel installed side by side if you are leveraging the Canary releases.</span></span>

## <a name="see-also"></a><span data-ttu-id="40919-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="40919-152">See also</span></span>

- [<span data-ttu-id="40919-153">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="40919-153">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="40919-154">チャネル ダウンロード</span><span class="sxs-lookup"><span data-stu-id="40919-154">Channel downloads</span></span>](https://aka.ms/EdgeEnterprise)
