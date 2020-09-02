---
title: Microsoft Edge チャネル概要
ms.author: srugh
author: srugh
manager: seanlynd
ms.date: 01/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge チャネル概要
ms.openlocfilehash: 4de456909df3cb5140abfb20ddb884ad9cc84c32
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980519"
---
# <span data-ttu-id="00f31-103">Microsoft Edge チャネルの概要</span><span class="sxs-lookup"><span data-stu-id="00f31-103">Overview of the Microsoft Edge channels</span></span>

<span data-ttu-id="00f31-104">次のバージョンの Microsoft Edge の利点の 1 つは、Microsoft が定期的に新機能を提供できることです。</span><span class="sxs-lookup"><span data-stu-id="00f31-104">One of the benefits of the next version of Microsoft Edge is that Microsoft can provide new features on a regular basis.</span></span> <span data-ttu-id="00f31-105">ただし、組織内のユーザーに Microsoft Edge を展開する管理者は、ユーザーがこれらの新機能を受け取る頻度を細かく制御できる方が良い場合があります。</span><span class="sxs-lookup"><span data-stu-id="00f31-105">However, as the admin who deploys Microsoft Edge to the users in your organization, you might want to have more control over how often your users get these new features.</span></span> <span data-ttu-id="00f31-106">Microsoft では、Microsoft Edge を新しい機能で更新する頻度を制御するために、チャネルと呼ばれる 4 つのオプションを提供しています。</span><span class="sxs-lookup"><span data-stu-id="00f31-106">Microsoft provides you four options, called channels, to control how often Microsoft Edge is updated with new features.</span></span> <span data-ttu-id="00f31-107">ここでは、これら 4 つのオプションの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="00f31-107">Here's an overview of the four options.</span></span>
  
> [!NOTE]
> <span data-ttu-id="00f31-108">この記事は Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="00f31-108">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="00f31-109">チャネルの概要</span><span class="sxs-lookup"><span data-stu-id="00f31-109">Channel overview</span></span>

|<span data-ttu-id="00f31-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="00f31-110">Channel</span></span>|<span data-ttu-id="00f31-111">主な目的</span><span class="sxs-lookup"><span data-stu-id="00f31-111">Primary purpose</span></span>|<span data-ttu-id="00f31-112">新機能に更新される頻度</span><span class="sxs-lookup"><span data-stu-id="00f31-112">How often updated with new features</span></span>|<span data-ttu-id="00f31-113">サポート</span><span class="sxs-lookup"><span data-stu-id="00f31-113">Supported?</span></span>|
|:---:|---|:---:|:---:|
|[<span data-ttu-id="00f31-114">Stable</span><span class="sxs-lookup"><span data-stu-id="00f31-114">Stable</span></span>](#stable-channel)|<span data-ttu-id="00f31-115">広範な展開</span><span class="sxs-lookup"><span data-stu-id="00f31-115">Broad Deployment</span></span>|<span data-ttu-id="00f31-116">6 週間に 1 回以上</span><span class="sxs-lookup"><span data-stu-id="00f31-116">~6 weeks</span></span>|<span data-ttu-id="00f31-117">あり</span><span class="sxs-lookup"><span data-stu-id="00f31-117">Yes</span></span>|
|[<span data-ttu-id="00f31-118">Beta</span><span class="sxs-lookup"><span data-stu-id="00f31-118">Beta</span></span>](#beta-channel)|<span data-ttu-id="00f31-119">組織内での代表的な対象での検証</span><span class="sxs-lookup"><span data-stu-id="00f31-119">Representative validation in the organization</span></span>|<span data-ttu-id="00f31-120">6 週間に 1 回以上</span><span class="sxs-lookup"><span data-stu-id="00f31-120">~6 weeks</span></span>|<span data-ttu-id="00f31-121">あり</span><span class="sxs-lookup"><span data-stu-id="00f31-121">Yes</span></span>|
|[<span data-ttu-id="00f31-122">Dev</span><span class="sxs-lookup"><span data-stu-id="00f31-122">Dev</span></span>](#dev-channel)|<span data-ttu-id="00f31-123">計画と開発</span><span class="sxs-lookup"><span data-stu-id="00f31-123">Planning and developing</span></span>|<span data-ttu-id="00f31-124">1 週間に 1 回</span><span class="sxs-lookup"><span data-stu-id="00f31-124">Weekly</span></span>|<span data-ttu-id="00f31-125">なし</span><span class="sxs-lookup"><span data-stu-id="00f31-125">No</span></span>|
|[<span data-ttu-id="00f31-126">Canary</span><span class="sxs-lookup"><span data-stu-id="00f31-126">Canary</span></span>](#canary-channel)|<span data-ttu-id="00f31-127">試験的な内容</span><span class="sxs-lookup"><span data-stu-id="00f31-127">Bleeding edge content</span></span>|<span data-ttu-id="00f31-128">毎日</span><span class="sxs-lookup"><span data-stu-id="00f31-128">Daily</span></span>|<span data-ttu-id="00f31-129">なし</span><span class="sxs-lookup"><span data-stu-id="00f31-129">No</span></span>|

<span data-ttu-id="00f31-130">どの更新チャネルをユーザーに展開するかについては、Microsoft Edge の更新されたバージョンでテストする必要がある、ユーザーが使用中の基幹業務アプリケーションの数など、いくつかの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="00f31-130">Which update channel you decide to deploy to your users depends on several factors, such as how many line of business applications the user leverages and that you need to test any time they have an updated version of Microsoft Edge.</span></span> <span data-ttu-id="00f31-131">この決定を行うには、Microsoft Edge で利用可能な 4 つの更新チャネルに関する次の情報をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="00f31-131">To help you make this decision, review the following information about the four update channels that are available for Microsoft Edge.</span></span>

### <span data-ttu-id="00f31-132">Stable チャネル</span><span class="sxs-lookup"><span data-stu-id="00f31-132">Stable Channel</span></span>

<span data-ttu-id="00f31-133">Stable チャネルは、組織での広範な展開を目的としており、ほとんどのユーザーに適したチャネルです。</span><span class="sxs-lookup"><span data-stu-id="00f31-133">The Stable Channel is intended for broad deployment in your organization, and it is the channel that most users should be on.</span></span> <span data-ttu-id="00f31-134">これはすべてのチャネルの中で最も安定しており、前の Beta チャネル リリースに含まれていた機能セットを安定させたものです。</span><span class="sxs-lookup"><span data-stu-id="00f31-134">It is the most stable of the channels and is the a result of the stabilization of the feature set available in the prior Beta Channel release.</span></span> <span data-ttu-id="00f31-135">約 6 週間ごとに新機能がリリースされます。</span><span class="sxs-lookup"><span data-stu-id="00f31-135">New features ship about every 6 weeks.</span></span> <span data-ttu-id="00f31-136">必要に応じて、セキュリティ更新プログラムと品質更新プログラムがリリースされます。</span><span class="sxs-lookup"><span data-stu-id="00f31-136">Security and quality updates ship as needed.</span></span> <span data-ttu-id="00f31-137">Stable チャネルからのリリースは、このチャネルからの次のリリースが利用可能になるまで、サポート対象と見なされます。</span><span class="sxs-lookup"><span data-stu-id="00f31-137">A release from the Stable Channel is considered supported until the next release from the channel is available.</span></span>

### <span data-ttu-id="00f31-138">Beta チャネル</span><span class="sxs-lookup"><span data-stu-id="00f31-138">Beta Channel</span></span>

<span data-ttu-id="00f31-139">Beta チャネルは、組織内の実稼働環境への展開を目的とし、代表的なユーザーのグループを対象としています。</span><span class="sxs-lookup"><span data-stu-id="00f31-139">The Beta Channel is intended for production deployment in your organization to a representative sample set of users.</span></span> <span data-ttu-id="00f31-140">サポートされているリリースであり、Beta からの各リリースは、このチャネルからの次のリリースが利用可能になるまでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="00f31-140">It is a supported release, and each release from Beta is supported until the next release from this channel is available.</span></span> <span data-ttu-id="00f31-141">ご利用環境で想定どおりに動作するかどうかを検証するための絶好の機会であり、問題が発生した場合は、リリースが Stable チャネルに公開される前に報告することができます。</span><span class="sxs-lookup"><span data-stu-id="00f31-141">This is a great opportunity to validate that things work as expected in your environment, and if you encounter an issue have it remediated prior to the release going publishing to the Stable Channel.</span></span> <span data-ttu-id="00f31-142">約 6 週間ごとに新機能がリリースされます。</span><span class="sxs-lookup"><span data-stu-id="00f31-142">New features ship about every 6 weeks.</span></span> <span data-ttu-id="00f31-143">必要に応じて、セキュリティ更新プログラムと品質更新プログラムがリリースされます。</span><span class="sxs-lookup"><span data-stu-id="00f31-143">Security and quality updates ship as needed.</span></span>

### <span data-ttu-id="00f31-144">Dev チャネル</span><span class="sxs-lookup"><span data-stu-id="00f31-144">Dev Channel</span></span>

<span data-ttu-id="00f31-145">Dev チャネルは、Canary チャネルよりも高い品質で、Microsoft Edge の最新機能を計画および開発することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="00f31-145">The Dev Channel is intended to help you plan and develop with the latest capabilities of Microsoft Edge, but with higher quality than the Canary Channel.</span></span> <span data-ttu-id="00f31-146">このチャネルでは、次の Beta リリースの前にいち早く新機能を確認し、準備できます。</span><span class="sxs-lookup"><span data-stu-id="00f31-146">This is your opportunity to get an early look at what is coming next and prepare for the next Beta release.</span></span>

### <span data-ttu-id="00f31-147">Canary チャネル</span><span class="sxs-lookup"><span data-stu-id="00f31-147">Canary Channel</span></span>

<span data-ttu-id="00f31-148">Canary チャネルは毎日リリースされ、すべてのチャネル内でも最先端で試験的な内容です。</span><span class="sxs-lookup"><span data-stu-id="00f31-148">The Canary Channel ships daily and is the most bleeding edge of all the channels.</span></span> <span data-ttu-id="00f31-149">ここには、最新の投資内容が反映されます。</span><span class="sxs-lookup"><span data-stu-id="00f31-149">If you want access to the newest investments then they will appear here first.</span></span> <span data-ttu-id="00f31-150">リリース頻度の性質上、長い目で見ると問題が発生することもあるため、Canary リリースを使用する場合は、別のチャネルを並行インストールすることもご検討ください。</span><span class="sxs-lookup"><span data-stu-id="00f31-150">Because of the nature of this cadence problems will arise overtime, so you may want another channel installed side by side if you are leveraging the Canary releases.</span></span>

## <span data-ttu-id="00f31-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="00f31-151">See also</span></span>

- [<span data-ttu-id="00f31-152">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="00f31-152">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="00f31-153">チャネル ダウンロード</span><span class="sxs-lookup"><span data-stu-id="00f31-153">Channel downloads</span></span>](https://aka.ms/EdgeEnterprise)
