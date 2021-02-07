---
title: Microsoft Edge の展開を計画する
ms.author: collw
author: appcompatguy
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge の展開を計画する
ms.openlocfilehash: 1b56d9874550c2002cec0577a53a3bf5766e2805
ms.sourcegitcommit: 16a92a51560fdba6f6480e4533453348f026c7ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "11313877"
---
# <span data-ttu-id="c3147-103">Microsoft Edge の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="c3147-103">Plan your deployment of Microsoft Edge</span></span>

<span data-ttu-id="c3147-104">この記事では、エンタープライズ環境で Microsoft Edge を展開する際に推奨される方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3147-104">This article describes the recommended practices for deploying Microsoft Edge in an enterprise environment.</span></span>

>[!NOTE]
><span data-ttu-id="c3147-105">この記事は Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c3147-105">This article applies to Microsoft Edge version 77 or later.</span></span>

<span data-ttu-id="c3147-106">以降のセクションでは、Microsoft Edge の展開を計画するための具体的なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c3147-106">The following sections provide specific guidance for planning your Microsoft Edge deployment.</span></span>

- [<span data-ttu-id="c3147-107">ブラウザーの環境と要件を評価する</span><span class="sxs-lookup"><span data-stu-id="c3147-107">Evaluate browser environment and requirements</span></span>](#evaluate-your-existing-browser-environment-and-browser-needs)
- [<span data-ttu-id="c3147-108">Windows 10 デバイスの準備ができていることを確認します</span><span class="sxs-lookup"><span data-stu-id="c3147-108">Make sure Windows 10 devices are ready</span></span>](#make-sure-your-windows-10-devices-are-ready)
- [<span data-ttu-id="c3147-109">展開方法の選択</span><span class="sxs-lookup"><span data-stu-id="c3147-109">Pick deployment methodology</span></span>](#determine-your-deployment-methodology)
- [<span data-ttu-id="c3147-110">サイト検出を実行する</span><span class="sxs-lookup"><span data-stu-id="c3147-110">Do site discovery</span></span>](#do-site-discovery)
- [<span data-ttu-id="c3147-111">チャネル戦略の選択</span><span class="sxs-lookup"><span data-stu-id="c3147-111">Pick channel strategy</span></span>](#determine-your-channel-strategy)
- [<span data-ttu-id="c3147-112">ポリシーを識別し構成する</span><span class="sxs-lookup"><span data-stu-id="c3147-112">Identify and configure policies</span></span>](#define-and-configure-policies)
- [<span data-ttu-id="c3147-113">アプリの互換性をテストする</span><span class="sxs-lookup"><span data-stu-id="c3147-113">Test App compatibility</span></span>](#do-app-compatibility-testing)
- [<span data-ttu-id="c3147-114">Microsoft Edge パイロット</span><span class="sxs-lookup"><span data-stu-id="c3147-114">Microsoft Edge pilot</span></span>](#deploy-microsoft-edge-to-a-pilot-group)
- [<span data-ttu-id="c3147-115">パイロットの評価</span><span class="sxs-lookup"><span data-stu-id="c3147-115">Evaluate pilot</span></span>](#validate-your-deployment)
- [<span data-ttu-id="c3147-116">Microsoft Edge をエンタープライズ全体に展開する</span><span class="sxs-lookup"><span data-stu-id="c3147-116">Deploy Microsoft Edge across the enterprise</span></span>](#broad-deployment-of-microsoft-edge)

## <span data-ttu-id="c3147-117">既存のブラウザー環境とブラウザーのニーズを評価する</span><span class="sxs-lookup"><span data-stu-id="c3147-117">Evaluate your existing browser environment and browser needs</span></span>

<span data-ttu-id="c3147-118">現在のブラウザーの状態とプロジェクトのビジョンを把握するための時間を取り、すべてのプロジェクトの利害関係者が同じ結果に向かって作業していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3147-118">Take time to understand your current browser state and project vision to ensure that all project stakeholders are aligned and working towards the same result.</span></span>

<span data-ttu-id="c3147-119">現在の状態を明確にすることから開始します。</span><span class="sxs-lookup"><span data-stu-id="c3147-119">Start by defining your current state:</span></span>

- <span data-ttu-id="c3147-120">現在どのブラウザーが環境に展開されていますか。</span><span class="sxs-lookup"><span data-stu-id="c3147-120">Which browsers are currently deployed in your environment?</span></span>
- <span data-ttu-id="c3147-121">どのブラウザーが既定のブラウザーとして設定されていますか。</span><span class="sxs-lookup"><span data-stu-id="c3147-121">Which browser is set as the default browser?</span></span>
- <span data-ttu-id="c3147-122">一部のアプリで Internet Explorer を使用する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="c3147-122">Do you need to use Internet Explorer for some of your apps?</span></span>
- <span data-ttu-id="c3147-123">現在、エンタープライズモードサイト一覧を使用して Internet Explorer を構成していますか。</span><span class="sxs-lookup"><span data-stu-id="c3147-123">Do you use an Enterprise Mode Site List to configure Internet Explorer today?</span></span>
- <span data-ttu-id="c3147-124">お客様の環境でどの OS プラットフォームがサポートされていますか </span><span class="sxs-lookup"><span data-stu-id="c3147-124">What OS platforms are supported in your environment?</span></span> <span data-ttu-id="c3147-125">(Windows 10、macOS、Windows 7、Windows Server など)。</span><span class="sxs-lookup"><span data-stu-id="c3147-125">(Windows 10, macOS, Windows 7, Windows Server, etc.)</span></span>
- <span data-ttu-id="c3147-126">ブラウザー管理にどのような管理ツールを使用していますか。</span><span class="sxs-lookup"><span data-stu-id="c3147-126">What management tools do you use for browser management?</span></span>
- <span data-ttu-id="c3147-127">ブラウザーの構成と管理を担当するのはだれですか。</span><span class="sxs-lookup"><span data-stu-id="c3147-127">Who is responsible for browser configuration and management?</span></span>
- <span data-ttu-id="c3147-128">ブラウザーの互換性を検証するプロセスはどのようなものですか。</span><span class="sxs-lookup"><span data-stu-id="c3147-128">What is your process for validating browser compatibility?</span></span>

<span data-ttu-id="c3147-129">現在の状態を把握したら、次のことを考慮して、適切なブラウザー展開の目標を決定できます。</span><span class="sxs-lookup"><span data-stu-id="c3147-129">After you understand the current state, you can determine the desired goals for your browser deployment, taking into account the following:</span></span>

- <span data-ttu-id="c3147-130">[Microsoft Edge を既定のブラウザーとして設定する](https://docs.microsoft.com/DeployEdge/edge-default-browser)必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="c3147-130">Do you want to [set Microsoft Edge as your default browser](https://docs.microsoft.com/DeployEdge/edge-default-browser)?</span></span>
- <span data-ttu-id="c3147-131">どのように [Microsoft Edge を構成](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge)しますか。</span><span class="sxs-lookup"><span data-stu-id="c3147-131">How will you [configure Microsoft Edge](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge)?</span></span>
- <span data-ttu-id="c3147-132">初期展開では、どのような機能を構成する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="c3147-132">What features are critical to configure as part of your initial deployment?</span></span>
- <span data-ttu-id="c3147-133">特定された互換性または構成の問題に対処するためのプロセスはどのようなものですか。</span><span class="sxs-lookup"><span data-stu-id="c3147-133">What is the process for addressing any identified compatibility or configuration issues?</span></span>

<span data-ttu-id="c3147-134">また、関心のある次のような機能の**前提条件**についても理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3147-134">You should also understand the **pre-requisites** for features you're interested in, such as:</span></span>

- [<span data-ttu-id="c3147-135">Windows Defender Application Guard</span><span class="sxs-lookup"><span data-stu-id="c3147-135">Windows Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-guard/reqs-wd-app-guard)
- [<span data-ttu-id="c3147-136">Internet Explorer モード</span><span class="sxs-lookup"><span data-stu-id="c3147-136">Internet Explorer mode</span></span>](https://docs.microsoft.com/DeployEdge/edge-ie-mode)
- [<span data-ttu-id="c3147-137">認証と同期</span><span class="sxs-lookup"><span data-stu-id="c3147-137">Authentication and sync</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-identity)

<span data-ttu-id="c3147-138">これらの回答を考慮することで、Microsoft Edge の展開を計画する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="c3147-138">With these answers in mind, you're ready to planning your Microsoft Edge deployment.</span></span>
<!--bookmark -->

## <span data-ttu-id="c3147-139">Windows 10 デバイスの準備ができていることを確認します</span><span class="sxs-lookup"><span data-stu-id="c3147-139">Make sure your Windows 10 devices are ready</span></span>

<span data-ttu-id="c3147-140">Edge Stableチャネルでは、2019年10月以降 (またはそれ以降) の最新の累積更新プログラム (LCU) を必要とします。</span><span class="sxs-lookup"><span data-stu-id="c3147-140">The Edge Stable channel requires the Latest Cumulative Update (LCU) from October 2019 (or later).</span></span> <span data-ttu-id="c3147-141">以前の LCU を含む Windows 10 デバイスに展開しようとすると、インストールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="c3147-141">If you attempt to deploy to a Windows 10 device that has an older LCU, then the installation will fail.</span></span> <span data-ttu-id="c3147-142">Edgeを展開する前に適用する必要がある最小限の LCU についての詳細は、[「Windows update を する」](https://docs.microsoft.com/DeployEdge/microsoft-edge-sysupdate-windows-updates)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3147-142">For more details about the minimum LCU that must be applied before deploying Edge, see [Windows updates to support the next version of Microsoft Edge](https://docs.microsoft.com/DeployEdge/microsoft-edge-sysupdate-windows-updates).</span></span>

## <span data-ttu-id="c3147-143">展開方法を決定する</span><span class="sxs-lookup"><span data-stu-id="c3147-143">Determine your deployment methodology</span></span>

<span data-ttu-id="c3147-144">目指している最終的な状態を把握できたら、そこに到達するための計画を開始します。</span><span class="sxs-lookup"><span data-stu-id="c3147-144">After you know your desired end state, you're ready to start planning how to get there.</span></span> <span data-ttu-id="c3147-145">Microsoft Edge を展開するための主な方法は、ロール別に展開する方法と、サイト別に展開する方法の 2 つです。</span><span class="sxs-lookup"><span data-stu-id="c3147-145">The two main ways to deploy Microsoft Edge are by role, and by site.</span></span>

### <span data-ttu-id="c3147-146">ロール別にエンド ユーザーに展開する</span><span class="sxs-lookup"><span data-stu-id="c3147-146">Deploy to end users by role</span></span>

<span data-ttu-id="c3147-147">アプリの互換性が主な問題であり、どのアプリをテストする必要があるかを把握していない場合は、ロール別にエンド ユーザーに展開することを検討します。</span><span class="sxs-lookup"><span data-stu-id="c3147-147">If app compatibility is your main concern, and you don't have a firm grasp on which apps to test, you might want to consider deploying to end users by role.</span></span> <span data-ttu-id="c3147-148">これにより、段階的な展開の各グループで、互換性の問題に対処するために構成を変更する必要があるアプリについてのフィードバックやインサイトを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="c3147-148">This enables each wave of a phased deployment to provide feedback and insights on apps that might need to have their configuration modified to address compatibility issues.</span></span>

### <span data-ttu-id="c3147-149">サイト別にエンド ユーザーに展開する</span><span class="sxs-lookup"><span data-stu-id="c3147-149">Deploy to end users by site</span></span>

<span data-ttu-id="c3147-150">帯域幅が主な問題である場合は、事前にアプリケーションの互換性テストを実施することを検討します。</span><span class="sxs-lookup"><span data-stu-id="c3147-150">If bandwidth is your primary concern, you might want to consider doing application compatibility testing up front.</span></span> <span data-ttu-id="c3147-151">テストが完了したら、サイト別にエンド ユーザーに展開して、他のソフトウェア配信の最適化のキャッシュを活用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c3147-151">After you finish testing, deploy to end users by site so you can leverage caching other software delivery optimizations.</span></span>

## <span data-ttu-id="c3147-152">サイト検出を実行する</span><span class="sxs-lookup"><span data-stu-id="c3147-152">Do site discovery</span></span>

<span data-ttu-id="c3147-153">レガシ Web アプリケーションに依存しており、Internet Explorer モードの使用を計画している場合 (ほとんどのお客様が該当)、追加のサイト検出の実行が必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3147-153">If you have a dependency on legacy web applications, and plan to use Internet Explorer mode (which most customers do), then you probably need to do some additional site discovery.</span></span>

### <span data-ttu-id="c3147-154">レガシ バージョンの Microsoft Edge を既に展開し、構成している場合</span><span class="sxs-lookup"><span data-stu-id="c3147-154">If you've already deployed and configured the legacy version of Microsoft Edge</span></span>

<span data-ttu-id="c3147-155">レガシ バージョンの Microsoft Edge で使用するようにエンタープライズ サイト一覧が既に構成されている場合、作業はほぼ完了です。</span><span class="sxs-lookup"><span data-stu-id="c3147-155">If you've already configured your Enterprise Site List to work for the legacy version of Microsoft Edge, then your work is almost done!</span></span> <span data-ttu-id="c3147-156">ニュートラル サイトの追加が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3147-156">The one thing you may need to add are neutral sites.</span></span>

<span data-ttu-id="c3147-157">ニュートラルサイトは、通常、シングル サインオン (SSO) を提供するサイトです。</span><span class="sxs-lookup"><span data-stu-id="c3147-157">Neutral sites are typically sites that provide Single Sign-On (SSO).</span></span> <span data-ttu-id="c3147-158">Microsoft Edge からニュートラル サイトに移動する場合は、Microsoft Edge で認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3147-158">If you navigate to a neutral site from Microsoft Edge, then you want to stay in Microsoft Edge to authenticate.</span></span> <span data-ttu-id="c3147-159">Internet Explorer モードでニュートラル サイトに移動する場合は、Internet Explorer モードで認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3147-159">If navigate to a neutral site in Internet Explorer mode, then you want to stay in Internet Explorer mode to authenticate.</span></span>

<span data-ttu-id="c3147-160">使用する SSO (またはその他のニュートラル) サイトを特定し、エンタープライズ サイト一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="c3147-160">Identify any SSO (or other neutral) sites that you use and add these to your Enterprise Site List.</span></span>

### <span data-ttu-id="c3147-161">既定のブラウザーとして Internet Explorer を構成していた場合</span><span class="sxs-lookup"><span data-stu-id="c3147-161">If you've configured Internet Explorer as your default browser</span></span>

<span data-ttu-id="c3147-162">現在、Internet Explorer のみを使用している場合は、どのサイトが最新の Web 標準にアップグレードされ、どのサイトでまだ Internet Explorer が必要であるかを把握していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3147-162">If you're currently only using Internet Explorer, you might not know which sites have upgraded to modern web standards and which still require Internet Explorer.</span></span> <span data-ttu-id="c3147-163">これらのサイトを検索して、エンタープライズ サイト一覧に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3147-163">You want to find these sites and add them to the Enterprise Site List.</span></span> <span data-ttu-id="c3147-164">これにより、必要なサイトでのみ Internet Explorer モードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c3147-164">This lets you use Internet Explorer mode only on the sites that need it.</span></span>

> [!TIP]
> <span data-ttu-id="c3147-165">[Enterprise Site Discovery](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery?redirectedfrom=MSDN) ツールを使用して、Internet Explorer モードを必要とする可能性があるサイトを検出します。</span><span class="sxs-lookup"><span data-stu-id="c3147-165">Use the [Enterprise Site Discovery](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery?redirectedfrom=MSDN) tools to discover the sites that might need Internet Explorer mode.</span></span> <span data-ttu-id="c3147-166">Windows 10、Windows 8.1、Windows 7 で、Windows Internet Explorer 8 から Internet Explorer 11 までを実行しているコンピューターでデータを収集できます。</span><span class="sxs-lookup"><span data-stu-id="c3147-166">You can collect collect data on computers running Windows Internet Explorer 8 through Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7.</span></span>

### <span data-ttu-id="c3147-167">サイト検出データを分析する</span><span class="sxs-lookup"><span data-stu-id="c3147-167">Analyze site discovery data</span></span>

<span data-ttu-id="c3147-168">サイト データを収集した後、次の 4 つの手順を実行してデータを分析することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3147-168">After you've collected site data, we recommend the following 4-step process to analyze the data:</span></span>

1. <span data-ttu-id="c3147-169">データをドメインごと、次に URL ごとに並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="c3147-169">Sort the data by domain, and then by URL.</span></span>
2. <span data-ttu-id="c3147-170">Internet Explorer モード用に構成する "アプリ" の境界を定義します。</span><span class="sxs-lookup"><span data-stu-id="c3147-170">Define the boundaries of an "app" to configure for Internet Explorer mode.</span></span> <span data-ttu-id="c3147-171">アプリを定義するすべてのサイトと Web コントロールを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3147-171">You want to include all the sites and web controls that define the app.</span></span> <span data-ttu-id="c3147-172">ただし、アプリの定義を広くしすぎるすることで、余分なサイトやコントロールを含めないようにします。</span><span class="sxs-lookup"><span data-stu-id="c3147-172">But you don't want to include any extra sites and controls by defining the app too broadly.</span></span> <span data-ttu-id="c3147-173">サイトによって、"http://contoso.com/app1" のように単純なものもあれば、複数のサイトやページを定義する必要があるものもあります。</span><span class="sxs-lookup"><span data-stu-id="c3147-173">Some sites may be as simple as "http://contoso.com/app1" while others may require you to define multiple sites and pages.</span></span>
3. <span data-ttu-id="c3147-174">アプリをテストして、ネイティブに機能していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3147-174">Test the app to verify that it doesn't work natively.</span></span> <span data-ttu-id="c3147-175">多くのサイトでは、最新のブラウザーが検出されると最新のコンテンツが提供され、Internet Explorer が検出された場合にのみレガシ コンテンツが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c3147-175">Many sites will offer modern content when they detect a modern browser, and only offer legacy content when they detect Internet Explorer.</span></span>
4. <span data-ttu-id="c3147-176">アプリがテストではねられた場合は、エンタープライズ サイト一覧にアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="c3147-176">Add the app to your Enterprise Site list if it fails testing.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c3147-177">ベスト プラクティスとして、アプリを構成するすべてのサイトをグループ化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3147-177">As a best practice, group all of the sites that comprise an app.</span></span> <span data-ttu-id="c3147-178">1 つのタスクを実行するためにすべてのサイトを使用する必要がある場合、およびそれらがまとめて更新される傾向がある場合は、そのサイトをグループ化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3147-178">If the sites all need to be used to accomplish one task, and if they tend to be updated together, that is a good indication that they should be grouped.</span></span> <span data-ttu-id="c3147-179">これにより、アプリをアップグレードするときに、サイト全体を Internet Explorer モードから削除し、そのアプリに最新のブラウザーを使用し始めるのが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="c3147-179">This way, when you upgrade an app, it's easier to remove the entire site from Internet Explorer mode and start using a modern browser for that app.</span></span>

## <span data-ttu-id="c3147-180">チャネル戦略を決定する</span><span class="sxs-lookup"><span data-stu-id="c3147-180">Determine your channel strategy</span></span>

<span data-ttu-id="c3147-181">Microsoft Edge は[複数のチャネル](https://docs.microsoft.com/DeployEdge/microsoft-edge-channels)でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="c3147-181">Microsoft Edge is released in [multiple channels](https://docs.microsoft.com/DeployEdge/microsoft-edge-channels).</span></span>

> [!NOTE]
> <span data-ttu-id="c3147-182">1 台のデバイスに複数のチャネルをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c3147-182">You can install more than one channel on a device</span></span>

<span data-ttu-id="c3147-183">Stable チャネルは、ほとんどのデバイスに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3147-183">The Stable Channel is what you will want to deploy to most devices.</span></span> <span data-ttu-id="c3147-184">ただし、複数のデバイスと複数のチャネルを含む展開戦略を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3147-184">However, you should consider a deployment strategy that includes multiple devices and multiple channels.</span></span>

### <span data-ttu-id="c3147-185">複数のデバイスとチャネル</span><span class="sxs-lookup"><span data-stu-id="c3147-185">Multiple devices and channels</span></span>

<span data-ttu-id="c3147-186">Beta チャネルを使用するように構成されたデバイスの代表的なサブセットを用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3147-186">We recommend having a representative subset of devices configured to use the Beta Channel.</span></span> <span data-ttu-id="c3147-187">これにより、ブラウザーに対する今後の変更点をプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="c3147-187">This lets you preview upcoming changes to the browser.</span></span> <span data-ttu-id="c3147-188">これらの変更点がエンド ユーザーまたはアプリに影響するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c3147-188">You can see if these changes are going to affect your end users or apps.</span></span>

<span data-ttu-id="c3147-189">また、Dev チャネル (または Canary チャネル) を Web 開発者などの一部のロールで使用できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c3147-189">You might also want to make the Dev Channel (or even the Canary Channel) available to some roles, such as web developers.</span></span> <span data-ttu-id="c3147-190">より流動的で急速に変化するチャネルで一部のデバイスをターゲットにするか、またはこれらのチャネルをユーザーがインストールすることを選択できるようにするかを検討します。</span><span class="sxs-lookup"><span data-stu-id="c3147-190">Consider whether you would like to target some devices with more fluid and rapidly changing channels, or simply make these channels available for users to opt to install.</span></span>

<span data-ttu-id="c3147-191">1 台のデバイスに複数のチャネルをインストールできるため、プレリリース版のチャネルをインストールすることを選択したユーザーについてテストのリスクを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="c3147-191">Because it's possible to install multiple channels on a device, you can mitigate the risk of testing for users who have opted to install a pre-release channel.</span></span> <span data-ttu-id="c3147-192">たとえば、Beta チャンネルを使用しているユーザーがいて、問題が発生した場合、ユーザーは Stable チャンネルに切り替えて作業を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="c3147-192">For example, if you have a user who's using the Beta Channel, and there's a problem, they can switch to the Stable Channel and continue working.</span></span> <span data-ttu-id="c3147-193">これにより、問題を解決できるようになるまでの間も、ユーザーはブロックされません。</span><span class="sxs-lookup"><span data-stu-id="c3147-193">This unblocks them until the issue can be fixed.</span></span>

> [!NOTE]
> <span data-ttu-id="c3147-194">ユーザーが同期を有効にした場合、その構成はチャネル間で同期されるため、チャネル間の移行がさらに容易になります。</span><span class="sxs-lookup"><span data-stu-id="c3147-194">If the user enabled Sync, then their configuration will sync across channels, making it even easier to transition between channels.</span></span>

## <span data-ttu-id="c3147-195">ポリシーを定義および構成する</span><span class="sxs-lookup"><span data-stu-id="c3147-195">Define and configure policies</span></span>

<span data-ttu-id="c3147-196">エンタープライズ サイト一覧を作成したら、Microsoft Edge を使用して展開する予定のポリシーを特定し、構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3147-196">After you've created your Enterprise Site List, we recommend identifying and configuring the policies that you intend to deploy with Microsoft Edge.</span></span> <span data-ttu-id="c3147-197">これにより、テストの実行時にこれらのポリシーが確実に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c3147-197">This ensures that these policies are applied when you perform your testing.</span></span>

<span data-ttu-id="c3147-198">最初に、ユーザーに提供する初回実行時のエクスペリエンスを検討します。</span><span class="sxs-lookup"><span data-stu-id="c3147-198">First, consider the first-run experience you want your users to have.</span></span> <span data-ttu-id="c3147-199">現在のブラウザーから自動的に設定をインポートする場合は、[AutoImportAtFirstRun](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoimportatfirstrun) のポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c3147-199">If you want to automatically import settings from the current browser, configure the policy for [AutoImportAtFirstRun](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoimportatfirstrun).</span></span>

<span data-ttu-id="c3147-200">セキュリティ ポリシーについては、Microsoft Edge セキュリティ ベースラインから始めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3147-200">For security policies, we recommend starting with the Microsoft Edge Security Baseline.</span></span> <span data-ttu-id="c3147-201">セキュリティベース ラインは、[推奨されるセキュリティ ベースラインの設定](https://techcommunity.microsoft.com/t5/Microsoft-Security-Baselines/Security-baseline-DRAFT-for-Chromium-based-Microsoft-Edge/ba-p/949991)または [Microsoft Intune](https://docs.microsoft.com/intune/protect/security-baseline-settings-edge) を使用して適用できます。</span><span class="sxs-lookup"><span data-stu-id="c3147-201">The Security Baseline can be applied using the [recommended security configuration baseline settings](https://techcommunity.microsoft.com/t5/Microsoft-Security-Baselines/Security-baseline-DRAFT-for-Chromium-based-Microsoft-Edge/ba-p/949991) or by using [Microsoft Intune](https://docs.microsoft.com/intune/protect/security-baseline-settings-edge).</span></span>

<span data-ttu-id="c3147-202">その他のポリシーについては、[Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policies) と [Microsoft Edge Update](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) のポリシー構成を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3147-202">For other policies, we recommend reviewing the policy configurations for [Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policies) and [Microsoft Edge Updates](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

### <span data-ttu-id="c3147-203">更新の戦略とポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="c3147-203">Define your update strategy and policies</span></span>

<span data-ttu-id="c3147-204">Microsoft Edge の展開後に更新プログラムを実行する方法を決定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c3147-204">You also want to determine how you want to do updates after you deploy Microsoft Edge:</span></span>

- <span data-ttu-id="c3147-205">**Microsoft Edge の自己更新を許可する** (既定)。</span><span class="sxs-lookup"><span data-stu-id="c3147-205">**Allow Microsoft Edge to update itself** (default).</span></span> <span data-ttu-id="c3147-206">Microsoft Edge の自動更新を許可するように選択した場合、展開したチャネルによって決定されているペースで Microsoft Edge が自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="c3147-206">If you choose to allow automatic updates of Microsoft Edge, then Microsoft Edge will automatically update itself at the pace determined by the channel(s) you deployed.</span></span>
- <span data-ttu-id="c3147-207">**ユーザーのペースで Microsoft Edge を更新する**</span><span class="sxs-lookup"><span data-stu-id="c3147-207">**Update Microsoft Edge at your own pace**.</span></span> <span data-ttu-id="c3147-208">更新プログラムを展開するタイミングを明示的に制御する場合は、自動更新を無効にして自分で展開することができます ([更新ポリシー リファレンス](https://docs.microsoft.com/DeployEdge/microsoft-edge-update-policies)を参照してください)。自動更新を無効にした後、次のいずれかのツールを使用して、各チャネルの更新プログラムを展開できます。</span><span class="sxs-lookup"><span data-stu-id="c3147-208">If you prefer to have explicit control over when updates are deployed, you can disable automatic updates and deploy it yourself (see the [Update Policy reference](https://docs.microsoft.com/DeployEdge/microsoft-edge-update-policies).) After you disable automatic updates you can deploy updates for each channel using one of the following tools:</span></span>

- [<span data-ttu-id="c3147-209">Intune</span><span class="sxs-lookup"><span data-stu-id="c3147-209">Intune</span></span>](https://docs.microsoft.com/intune/apps/apps-windows-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)
- [<span data-ttu-id="c3147-210">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c3147-210">Configuration Manager</span></span>](https://docs.microsoft.com/DeployEdge/deploy-edge-with-configuration-manager)
- <span data-ttu-id="c3147-211">選択した展開ツール</span><span class="sxs-lookup"><span data-stu-id="c3147-211">the deployment tool of your choice.</span></span>

<span data-ttu-id="c3147-212">更新戦略に関係なく、リングによる展開戦略を活用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3147-212">Regardless of your update strategy, we recommend leveraging a ringed deployment strategy.</span></span> <span data-ttu-id="c3147-213">自動更新では、Beta チャネルを実行しているユーザーの代表的なサンプルに、Stable チャネルになる候補に関する問題を特定してもらうことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c3147-213">With automatic updates, this means having a representative sample of users running the Beta Channel, to identify issues with what will become the Stable Channel.</span></span> <span data-ttu-id="c3147-214">手動更新では、新しい Stable チャネル ビルドがリリースされた後に、パイロット グループの追加の検証を含めるような場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c3147-214">With manual updates, this might also include additional validation of a pilot group after a new Stable Channel build is released.</span></span> <span data-ttu-id="c3147-215">この後に、広範な展開が行われます。</span><span class="sxs-lookup"><span data-stu-id="c3147-215">This is followed by broad deployment.</span></span>

>[!NOTE]
><span data-ttu-id="c3147-216">Microsoft Edge のサポートは、各チャネルの最新バージョンの Microsoft Edge にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c3147-216">Microsoft Edge support will only apply to the most recent version of Microsoft Edge in each channel</span></span>

## <span data-ttu-id="c3147-217">アプリの互換性テストを実行する</span><span class="sxs-lookup"><span data-stu-id="c3147-217">Do app compatibility testing</span></span>

<span data-ttu-id="c3147-218">Microsoft Edge のアプリケーションの互換性は非常に高いため、Microsoft は互換性に関する次のような約束をしています。</span><span class="sxs-lookup"><span data-stu-id="c3147-218">Application compatibility for Microsoft Edge is extremely high - so high that Microsoft provides the following compatibility promises:</span></span>

1. <span data-ttu-id="c3147-219">Microsoft Edge *version 45 以前*で動作している場合、Microsoft Edge *version 77 以降*でも動作します。</span><span class="sxs-lookup"><span data-stu-id="c3147-219">If it works on Microsoft Edge *version 45 and earlier*, it will work on Microsoft Edge *version 77 and later*.</span></span>
2. <span data-ttu-id="c3147-220">Internet Explorer で機能している場合、Internet Explorer モードの Microsoft Edge でも動作します。</span><span class="sxs-lookup"><span data-stu-id="c3147-220">If it works on Internet Explorer, it will work on Microsoft Edge in Internet Explorer mode.</span></span>
3. <span data-ttu-id="c3147-221">Google Chrome で機能している場合、Microsoft Edge でも動作します。</span><span class="sxs-lookup"><span data-stu-id="c3147-221">If it works on Google Chrome, it will work on Microsoft Edge.</span></span>

<span data-ttu-id="c3147-222">この互換性の約束が果たされていないアプリケーションがある場合、Microsoft は [Microsoft App Assure](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure) によってお約束通り、アプリの修正を行います。</span><span class="sxs-lookup"><span data-stu-id="c3147-222">If you have an application where we don't meet our compatibility promise, then we stand behind the promise to fix it with [Microsoft App Assure](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure).</span></span>

### <span data-ttu-id="c3147-223">内部機関業務アプリのテスト</span><span class="sxs-lookup"><span data-stu-id="c3147-223">Internal line of business app testing</span></span>

<span data-ttu-id="c3147-224">このように互換性の約束をしていますが、多くの組織では自社のコンプライアンスまたはリスク管理の理由から一部のアプリケーションを検証する必要があるということも理解しています。</span><span class="sxs-lookup"><span data-stu-id="c3147-224">Despite our compatibility promise, we know that many organizations must validate some applications for their compliance or risk management reasons.</span></span> <span data-ttu-id="c3147-225">これは非常に簡単であると予測されますが、アプリのテストは整理して厳格に実行することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c3147-225">Even though we expect this to be very straightforward, it's important to be organized and rigorous in app testing.</span></span>

<span data-ttu-id="c3147-226">アプリの互換性テストを行うには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="c3147-226">There are 2 ways to do app compatibility testing:</span></span>

1. <span data-ttu-id="c3147-227">ラボ テスト。</span><span class="sxs-lookup"><span data-stu-id="c3147-227">Lab testing.</span></span> <span data-ttu-id="c3147-228">アプリケーションは、特定の構成を持つ厳格に制御された環境で検証されます。</span><span class="sxs-lookup"><span data-stu-id="c3147-228">Applications are validated in a tightly controlled environment with specific configurations.</span></span>
2. <span data-ttu-id="c3147-229">パイロット テスト。</span><span class="sxs-lookup"><span data-stu-id="c3147-229">Pilot testing.</span></span> <span data-ttu-id="c3147-230">アプリケーションは、日常的な作業環境で、限られた数のユーザーが自分のデバイスを使用することによって検証されます。</span><span class="sxs-lookup"><span data-stu-id="c3147-230">Applications are validated by a limited number of users in their daily work environment using their own devices.</span></span>

<span data-ttu-id="c3147-231">互換性テストに過剰投資を行わずにリスクを管理するために、各アプリに最適な方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3147-231">Choose the method that is most appropriate for each app,  to manage risk without over-investing in compatibility testing.</span></span>

### <span data-ttu-id="c3147-232">サード パーティ製のアプリのサポート</span><span class="sxs-lookup"><span data-stu-id="c3147-232">Third party app support</span></span>

<span data-ttu-id="c3147-233">独自の基幹業務アプリに加えて、多くの組織は、外部ソースによって提供されるアプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="c3147-233">In addition to their own line of business apps, many organizations use apps provided by external sources.</span></span> <span data-ttu-id="c3147-234">[[Microsoft Edge 用 に準備されている](deploy-edge-ready-for-edge.md)] の記事には、組織内で使用されている可能性のある Web アプリケーションの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3147-234">The [Ready for Microsoft Edge](deploy-edge-ready-for-edge.md) article contains a list of web applications that may be in use within your organization.</span></span> <span data-ttu-id="c3147-235">このリストでは、Microsoft Edge と共に使用した際の製品のプロバイダー サポート ステートメントへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="c3147-235">This list provides links to provider support statements for their products when used with Microsoft Edge.</span></span>

## <span data-ttu-id="c3147-236">パイロット グループに Microsoft Edge を展開する</span><span class="sxs-lookup"><span data-stu-id="c3147-236">Deploy Microsoft Edge to a pilot group</span></span>

<span data-ttu-id="c3147-237">ポリシーを定義し、初期のアプリの互換性テストが完了したら、パイロット グループに展開できます。</span><span class="sxs-lookup"><span data-stu-id="c3147-237">After you've defined your policies and have finished your initial app compatibility testing, you're ready to deploy to your pilot group.</span></span> <span data-ttu-id="c3147-238">次のいずれかのツールを使用して、パイロット グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="c3147-238">Deploy to your pilot group using one of the following tools:</span></span>

- <span data-ttu-id="c3147-239">[Windows 用の Microsoft Intune](https://docs.microsoft.com/intune/apps/apps-windows-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json) または [macOS 用の Microsoft Intune](https://docs.microsoft.com/intune/apps/apps-edge-macos?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)</span><span class="sxs-lookup"><span data-stu-id="c3147-239">[Microsoft Intune for Windows](https://docs.microsoft.com/intune/apps/apps-windows-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json), or [Microsoft Intune for macOS](https://docs.microsoft.com/intune/apps/apps-edge-macos?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)</span></span>
- <span data-ttu-id="c3147-240">[Configuration Manager](https://docs.microsoft.com/DeployEdge/deploy-edge-with-configuration-manager)</span><span class="sxs-lookup"><span data-stu-id="c3147-240">[Configuration Manager](https://docs.microsoft.com/DeployEdge/deploy-edge-with-configuration-manager).</span></span>
- <span data-ttu-id="c3147-241">別の管理ツールで、[Microsoft Edge 用の MSI ファイル](https://www.microsoftedgeinsider.com/enterprise)をダウンロードして展開します。</span><span class="sxs-lookup"><span data-stu-id="c3147-241">Another management tool, download and deploy the [MSI file for Microsoft Edge](https://www.microsoftedgeinsider.com/enterprise).</span></span>

## <span data-ttu-id="c3147-242">展開を検証する</span><span class="sxs-lookup"><span data-stu-id="c3147-242">Validate your deployment</span></span>

<span data-ttu-id="c3147-243">パイロットを展開した後、ユーザーからのすべてのフィードバックを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3147-243">After you deploy your pilot, you want to capture all the feedback you get from your users.</span></span>

- <span data-ttu-id="c3147-244">互換性に関するフィードバックを取得します。</span><span class="sxs-lookup"><span data-stu-id="c3147-244">Capture feedback on compatibility.</span></span> <span data-ttu-id="c3147-245">エンタープライズ サイト一覧に含まれていて、サイト検出中に識別されなかったサイトを特定します。</span><span class="sxs-lookup"><span data-stu-id="c3147-245">Identify sites that belong on the Enterprise Site List that weren't identified during site discovery.</span></span>
- <span data-ttu-id="c3147-246">ポリシー構成に関するフィードバックを取得します。</span><span class="sxs-lookup"><span data-stu-id="c3147-246">Capture feedback on the policy configuration.</span></span> <span data-ttu-id="c3147-247">セキュリティ ガイドラインを遵守しながら、ユーザーが主要な機能を使用して、作業を確実に行うことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="c3147-247">Ensure that users can use key features and do their work while following security guidelines.</span></span>
- <span data-ttu-id="c3147-248">使いやすさと新機能に関するフィードバックを取得します。</span><span class="sxs-lookup"><span data-stu-id="c3147-248">Capture feedback on ease of use and new features.</span></span> <span data-ttu-id="c3147-249">ユーザーの疑問点に基づきトレーニングを開発して実施する必要がある領域を特定します。</span><span class="sxs-lookup"><span data-stu-id="c3147-249">Identify any areas where training should be developed and delivered based on user questions.</span></span>

## <span data-ttu-id="c3147-250">Microsoft Edge の広範な展開</span><span class="sxs-lookup"><span data-stu-id="c3147-250">Broad deployment of Microsoft Edge</span></span>

<span data-ttu-id="c3147-251">パイロットを完了し、パイロットから学んだ教訓を使用して展開計画を更新した後、すべてのユーザーに Microsoft Edge の完全な展開を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c3147-251">After a finishing the pilot and updating your deployment plan with lessons learned from the pilot, you're ready to do a full deployment of Microsoft Edge to all your users.</span></span>  <span data-ttu-id="c3147-252">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="c3147-252">Congratulations!</span></span>

## <span data-ttu-id="c3147-253">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3147-253">See also</span></span>

- [<span data-ttu-id="c3147-254">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="c3147-254">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="c3147-255">ビデオ - Microsoft Edge の展開</span><span class="sxs-lookup"><span data-stu-id="c3147-255">Video - Deploy Microsoft Edge</span></span>](microsoft-edge-video-deploy.md)
