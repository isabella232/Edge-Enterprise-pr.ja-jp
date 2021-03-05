---
title: Microsoft Edge キオスク モードを構成する
ms.author: aguta
author: aguta
manager: srugh
ms.date: 03/03/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: キオスク モード機能と Microsoft Edge キオスク モードのオプションを構成する方法について説明します。
ms.openlocfilehash: 9f2ce26f2c505ba3fc9e2e05b057e5d5df8257fe
ms.sourcegitcommit: 8da3a4de1a14514014b6d7b103ba79f2ace48044
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "11388543"
---
# <a name="configure-microsoft-edge-kiosk-mode"></a><span data-ttu-id="5d44a-103">Microsoft Edge キオスク モードを構成する</span><span class="sxs-lookup"><span data-stu-id="5d44a-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="5d44a-104">この記事では、パイロットを実行することができる Microsoft Edge キオスク モードのオプションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="5d44a-105">また、対象としている機能のロードマップも含まれます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-105">There's also a roadmap of features we're targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="5d44a-106">この記事は Microsoft Edge version 87 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-106">This article applies to Microsoft Edge version 87 or later.</span></span>

## <a name="overview"></a><span data-ttu-id="5d44a-107">概要</span><span class="sxs-lookup"><span data-stu-id="5d44a-107">Overview</span></span>

<span data-ttu-id="5d44a-108">Microsoft Edge キオスク モードは、ブラウザーの 2 つのロックダウン エクスペリエンスを提供し、組織が顧客に最高のエクスペリエンスを作成し、管理し、提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5d44a-108">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="5d44a-109">次のロックダウン エクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-109">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="5d44a-110">**デジタル/対話型サイネージ** エクスペリエンスでは、全画面表示モードで特定のサイトを表示します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-110">**Digital/Interactive Signage** experience - Displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="5d44a-111">**パブリック ブラウジング** エクスペリエンスでは、Microsoft Edge の限定的な複数タブのバージョンを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-111">**Public-Browsing** experience - Runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="5d44a-112">どちらのエクスペリエンスでも、ユーザー データを保護する Microsoft Edge InPrivate セッションを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-112">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <a name="set-up-microsoft-edge-kiosk-mode"></a><span data-ttu-id="5d44a-113">Microsoft Edge キオスク モードのセットアップ</span><span class="sxs-lookup"><span data-stu-id="5d44a-113">Set up Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="5d44a-114">キオスク モード機能の初期セットが Microsoft Edge Canary チャネルのバージョン 87 でテストに使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5d44a-114">An initial set of kiosk mode features is available to test with Microsoft Edge Stable Channel, version 87.</span></span> <span data-ttu-id="5d44a-115">[Microsoft Edge (Official Stable チャネル)](https://www.microsoft.com/edge) から 最新バージョンをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-115">You can download the latest version from [Microsoft Edge (Official Stable Channel)](https://www.microsoft.com/edge).</span></span>

### <a name="kiosk-mode-supported-features"></a><span data-ttu-id="5d44a-116">キオスク モードでサポートされる機能</span><span class="sxs-lookup"><span data-stu-id="5d44a-116">Kiosk mode supported features</span></span>

<span data-ttu-id="5d44a-117">次の表に、Microsoft Edge と Microsoft Edge レガシのキオスク モードでサポートされる機能を示します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-117">The following table lists the features supported by kiosk mode in Microsoft Edge and Microsoft Edge Legacy.</span></span> <span data-ttu-id="5d44a-118">次の表を Microsoft Edge への移行のためのガイドとして使用し、Microsoft Edge の両方のバージョンでこれらの機能がどのようにサポートされているかを比較してください。</span><span class="sxs-lookup"><span data-stu-id="5d44a-118">Use this table as a guide to transitioning to Microsoft Edge by comparing how these features are supported in both versions of Microsoft Edge.</span></span>

|<span data-ttu-id="5d44a-119">機能</span><span class="sxs-lookup"><span data-stu-id="5d44a-119">Feature</span></span>|<span data-ttu-id="5d44a-120">デジタル/対話型サイネージ</span><span class="sxs-lookup"><span data-stu-id="5d44a-120">Digital\Interactive Signage</span></span>|<span data-ttu-id="5d44a-121">パブリック ブラウジング</span><span class="sxs-lookup"><span data-stu-id="5d44a-121">Public browsing</span></span>|<span data-ttu-id="5d44a-122">Microsoft Edge のバージョン (以上) で利用可能</span><span class="sxs-lookup"><span data-stu-id="5d44a-122">Available with Microsoft Edge version (and higher)</span></span>|<span data-ttu-id="5d44a-123">Microsoft Edge レガシで使用可能</span><span class="sxs-lookup"><span data-stu-id="5d44a-123">Available with Microsoft Edge Legacy</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="5d44a-124">InPrivate ナビゲーション。</span><span class="sxs-lookup"><span data-stu-id="5d44a-124">InPrivate Navigation</span></span>|<span data-ttu-id="5d44a-125">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-125">Y</span></span>|<span data-ttu-id="5d44a-126">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-126">Y</span></span>|<span data-ttu-id="5d44a-127">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-127">89</span></span>|<span data-ttu-id="5d44a-128">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-128">Y</span></span>|
|<span data-ttu-id="5d44a-129">非アクティブ時のリセット</span><span class="sxs-lookup"><span data-stu-id="5d44a-129">Reset on inactivity</span></span>|<span data-ttu-id="5d44a-130">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-130">Y</span></span>|<span data-ttu-id="5d44a-131">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-131">Y</span></span>|<span data-ttu-id="5d44a-132">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-132">89</span></span>|<span data-ttu-id="5d44a-133">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-133">Y</span></span>|
|<span data-ttu-id="5d44a-134">[読み取り専用アドレス バー](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="5d44a-134">[Read only address bar](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) (policy)</span></span> |<span data-ttu-id="5d44a-135">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-135">N</span></span>|<span data-ttu-id="5d44a-136">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-136">Y</span></span> |<span data-ttu-id="5d44a-137">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-137">89</span></span>|<span data-ttu-id="5d44a-138">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-138">N</span></span>|
|<span data-ttu-id="5d44a-139">[終了時にダウンロードを削除する](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="5d44a-139">[Delete downloads on exit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) (policy)</span></span>  | <span data-ttu-id="5d44a-140">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-140">Y</span></span>|<span data-ttu-id="5d44a-141">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-141">Y</span></span> |<span data-ttu-id="5d44a-142">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-142">89</span></span>|<span data-ttu-id="5d44a-143">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-143">N</span></span>|
|<span data-ttu-id="5d44a-144">F11 がブロックされています (全画面に入る/終了する)</span><span class="sxs-lookup"><span data-stu-id="5d44a-144">F11 blocked (enter/exit full-screen)</span></span> | <span data-ttu-id="5d44a-145">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-145">Y</span></span> | <span data-ttu-id="5d44a-146">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-146">Y</span></span> | <span data-ttu-id="5d44a-147">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-147">89</span></span> |<span data-ttu-id="5d44a-148">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-148">Y</span></span>|
|<span data-ttu-id="5d44a-149">F12 がブロックされています (開発者ツールの起動)</span><span class="sxs-lookup"><span data-stu-id="5d44a-149">F12 blocked (launch Developer Tools)</span></span> | <span data-ttu-id="5d44a-150">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-150">Y</span></span> | <span data-ttu-id="5d44a-151">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-151">Y</span></span> | <span data-ttu-id="5d44a-152">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-152">89</span></span> |<span data-ttu-id="5d44a-153">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-153">Y</span></span>|
| <span data-ttu-id="5d44a-154">複数タブのサポート</span><span class="sxs-lookup"><span data-stu-id="5d44a-154">Multi tab support</span></span> | <span data-ttu-id="5d44a-155">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-155">N</span></span>| <span data-ttu-id="5d44a-156">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-156">Y</span></span>| <span data-ttu-id="5d44a-157">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-157">89</span></span>|<span data-ttu-id="5d44a-158">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-158">Y</span></span>|
|<span data-ttu-id="5d44a-159">[URL のサポートを許可する](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="5d44a-159">[Allow URL support](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist) (policy)</span></span>|<span data-ttu-id="5d44a-160">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-160">Y</span></span>|<span data-ttu-id="5d44a-161">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-161">Y</span></span>|<span data-ttu-id="5d44a-162">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-162">89</span></span>|<span data-ttu-id="5d44a-163">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-163">N</span></span>|
|<span data-ttu-id="5d44a-164">[URL のサポートをブロックする](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="5d44a-164">[Block URL support](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist) (policy)</span></span>|<span data-ttu-id="5d44a-165">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-165">Y</span></span>|<span data-ttu-id="5d44a-166">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-166">Y</span></span>|<span data-ttu-id="5d44a-167">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-167">89</span></span>|<span data-ttu-id="5d44a-168">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-168">N</span></span>|
|<span data-ttu-id="5d44a-169">[[ホーム] ボタンを表示する](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showhomebutton) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="5d44a-169">[Show home button](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showhomebutton) (policy)</span></span>|<span data-ttu-id="5d44a-170">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-170">N</span></span>|<span data-ttu-id="5d44a-171">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-171">Y</span></span>|<span data-ttu-id="5d44a-172">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-172">89</span></span>|<span data-ttu-id="5d44a-173">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-173">Y</span></span>|
|<span data-ttu-id="5d44a-174">[お気に入りを管理する](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#managedfavorites) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="5d44a-174">[Manage favorites](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#managedfavorites) (policy)</span></span>|<span data-ttu-id="5d44a-175">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-175">N</span></span>|<span data-ttu-id="5d44a-176">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-176">Y</span></span>|<span data-ttu-id="5d44a-177">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-177">89</span></span>|<span data-ttu-id="5d44a-178">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-178">Y</span></span>|
|<span data-ttu-id="5d44a-179">[プリンターを有効化](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="5d44a-179">[Enable printer](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled) (policy)</span></span>|<span data-ttu-id="5d44a-180">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-180">Y</span></span>|<span data-ttu-id="5d44a-181">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-181">Y</span></span>|<span data-ttu-id="5d44a-182">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-182">89</span></span>|<span data-ttu-id="5d44a-183">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-183">Y</span></span>|
|<span data-ttu-id="5d44a-184">[新しいタブ ページの URLを構成する](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagelocation) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="5d44a-184">[Configure the new tab page URL](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagelocation) (policy)</span></span>|<span data-ttu-id="5d44a-185">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-185">N</span></span>|<span data-ttu-id="5d44a-186">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-186">Y</span></span>||<span data-ttu-id="5d44a-187">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-187">Y</span></span>|
|<span data-ttu-id="5d44a-188">[セッションの終了] ボタン \*</span><span class="sxs-lookup"><span data-stu-id="5d44a-188">End session button \*</span></span> | <span data-ttu-id="5d44a-189">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-189">N</span></span>| <span data-ttu-id="5d44a-190">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-190">Y</span></span>| <span data-ttu-id="5d44a-191">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-191">89</span></span>|<span data-ttu-id="5d44a-192">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-192">Y</span></span>|
|<span data-ttu-id="5d44a-193">すべての内部 Microsoft Edge URL はブロックされます (*edge://downloads* および *edge://print* を除く)</span><span class="sxs-lookup"><span data-stu-id="5d44a-193">All internal Microsoft Edge URLs are blocked, except for *edge://downloads* and *edge://print*</span></span> |<span data-ttu-id="5d44a-194">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-194">N</span></span>|<span data-ttu-id="5d44a-195">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-195">Y</span></span>|<span data-ttu-id="5d44a-196">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-196">89</span></span>|<span data-ttu-id="5d44a-197">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-197">Y</span></span>|
| <span data-ttu-id="5d44a-198">Ctrl + N がブロックされています (新しいウィンドウを開く) \*</span><span class="sxs-lookup"><span data-stu-id="5d44a-198">CTRL+N blocked (open a new window) \*</span></span> | <span data-ttu-id="5d44a-199">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-199">Y</span></span> | <span data-ttu-id="5d44a-200">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-200">Y</span></span> | <span data-ttu-id="5d44a-201">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-201">89</span></span> |<span data-ttu-id="5d44a-202">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-202">Y</span></span>|
| <span data-ttu-id="5d44a-203">Ctrl + T がブロックされています (新しいタブを開く)</span><span class="sxs-lookup"><span data-stu-id="5d44a-203">CTRL+T blocked (open new tab)</span></span> |<span data-ttu-id="5d44a-204">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-204">Y</span></span> | <span data-ttu-id="5d44a-205">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-205">N</span></span> | <span data-ttu-id="5d44a-206">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-206">89</span></span> |<span data-ttu-id="5d44a-207">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-207">Y</span></span>|
|<span data-ttu-id="5d44a-208">設定と詳細 (...) では、必要なオプションだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-208">Settings and more (...) will display only the required options</span></span>  |<span data-ttu-id="5d44a-209">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-209">Y</span></span> |<span data-ttu-id="5d44a-210">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-210">Y</span></span> |<span data-ttu-id="5d44a-211">89</span><span class="sxs-lookup"><span data-stu-id="5d44a-211">89</span></span> |<span data-ttu-id="5d44a-212">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-212">Y</span></span>|
|<span data-ttu-id="5d44a-213">ブラウザーからの他のアプリケーションの起動を制限する</span><span class="sxs-lookup"><span data-stu-id="5d44a-213">Restrict the launch of other applications from the browser</span></span>|<span data-ttu-id="5d44a-214">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-214">Y</span></span>|<span data-ttu-id="5d44a-215">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-215">Y</span></span>|<span data-ttu-id="5d44a-216">90/91</span><span class="sxs-lookup"><span data-stu-id="5d44a-216">90/91</span></span>|<span data-ttu-id="5d44a-217">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-217">Y</span></span>|
|<span data-ttu-id="5d44a-218">UI 印刷設定のロックダウン</span><span class="sxs-lookup"><span data-stu-id="5d44a-218">UI print settings lockdown</span></span>|<span data-ttu-id="5d44a-219">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-219">Y</span></span>|<span data-ttu-id="5d44a-220">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-220">Y</span></span>|<span data-ttu-id="5d44a-221">90/91</span><span class="sxs-lookup"><span data-stu-id="5d44a-221">90/91</span></span>|<span data-ttu-id="5d44a-222">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-222">Y</span></span>|
|<span data-ttu-id="5d44a-223">[新しいタブ ページをホーム ページとして設定する](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepageisnewtabpage) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="5d44a-223">[Set the new tab page as the home page](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepageisnewtabpage) (policy)</span></span>|-|-|<span data-ttu-id="5d44a-224">TBD</span><span class="sxs-lookup"><span data-stu-id="5d44a-224">TBD</span></span>|<span data-ttu-id="5d44a-225">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-225">Y</span></span>|

> [!NOTE]
> <span data-ttu-id="5d44a-226">"\*" に続く機能は、割り当てられたアクセス単一アプリのシナリオでのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="5d44a-226">Features followed by "\*" are only enabled in an assigned access single app scenario.</span></span>

## <a name="use-kiosk-mode-features"></a><span data-ttu-id="5d44a-227">キオスク モード機能を使用する</span><span class="sxs-lookup"><span data-stu-id="5d44a-227">Use kiosk mode features</span></span>

<span data-ttu-id="5d44a-228">Microsoft Edge キオスク モード機能は、デジタル/対話型サイネージおよびパブリック ブラウジング用の次の Windows 10 コマンドライン オプションで起動できます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-228">Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options for Digital/Interactive signage and Public browsing.</span></span>

### <a name="kiosk-mode-digitalinteractive-signage"></a><span data-ttu-id="5d44a-229">キオスク モード デジタル/対話型サイネージ</span><span class="sxs-lookup"><span data-stu-id="5d44a-229">Kiosk mode Digital/Interactive signage</span></span>
 
```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen
```

### <a name="kiosk-mode-public-browsing"></a><span data-ttu-id="5d44a-230">キオスク モードのパブリック ブラウジング</span><span class="sxs-lookup"><span data-stu-id="5d44a-230">Kiosk mode Public browsing</span></span>

```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing
```

### <a name="additional-command-line-options"></a><span data-ttu-id="5d44a-231">その他のコマンド ライン オプション</span><span class="sxs-lookup"><span data-stu-id="5d44a-231">Additional command line options</span></span>

- <span data-ttu-id="5d44a-232">**--no-first-run**: 最初の Microsoft Edge 実行エクスペリエンスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="5d44a-232">**--no-first-run**: Disable the first Microsoft Edge run experience.</span></span>

   ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --no-first-run
  ```

  ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --no-first-run
  ```

- <span data-ttu-id="5d44a-233">**--kiosk-idle-timeout-minutes=**: Microsoft Edge キオスク モードがユーザーのセッションをリセットする前に、最後のユーザー アクティビティからの時間 (分) を変更します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-233">**--kiosk-idle-timeout-minutes=**: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="5d44a-234">次の例の "value" を分数に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-234">Replace "value" in the next example with the number of minutes.</span></span>

   ```
   --kiosk-idle-timeout-minutes=value
   ``` 
   <span data-ttu-id="5d44a-235">次の "値" がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5d44a-235">The following "values" are supported:</span></span>

     - <span data-ttu-id="5d44a-236">既定値 (分)</span><span class="sxs-lookup"><span data-stu-id="5d44a-236">Default values (in minutes)</span></span>
       - <span data-ttu-id="5d44a-237">全画面 - 0 (オフ)</span><span class="sxs-lookup"><span data-stu-id="5d44a-237">Full screen - 0 (turned off)</span></span>
       - <span data-ttu-id="5d44a-238">パブリック ブラウジング - 5 分</span><span class="sxs-lookup"><span data-stu-id="5d44a-238">Public browsing - 5 minutes</span></span>
    - <span data-ttu-id="5d44a-239">指定可能な値</span><span class="sxs-lookup"><span data-stu-id="5d44a-239">Allowed values</span></span>
      - <span data-ttu-id="5d44a-240">0 - タイマーをオフにします</span><span class="sxs-lookup"><span data-stu-id="5d44a-240">0 - turns off the timer</span></span>
      - <span data-ttu-id="5d44a-241">1 - 1440 分 (アイドル タイマー時のリセット)</span><span class="sxs-lookup"><span data-stu-id="5d44a-241">1-1440 minutes for reset on idle timer</span></span>


    ```
    msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --kiosk-idle-timeout-minutes=1
   ```

   ```
   msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --kiosk-idle-timeout-minutes=1
   ```

## <a name="support-policies-for-kiosk-mode"></a><span data-ttu-id="5d44a-242">キオスク モードでサポートされているポリシー</span><span class="sxs-lookup"><span data-stu-id="5d44a-242">Support policies for kiosk mode</span></span>

<span data-ttu-id="5d44a-243">以下の表にある Microsoft Edge ポリシーのいずれかを使用して、構成する Microsoft Edge キオスク モードの種類に応じてキオスク エクスペリエンスを強化します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-243">Use any of the Microsoft Edge policies listed in the following table to enhance the kiosk experience for the Microsoft Edge kiosk mode type you configure.</span></span> <span data-ttu-id="5d44a-244">これらのポリシーの詳細については、「[Microsoft Edge - ブラウザー ポリシー リファレンス](https://docs.microsoft.com/deployedge/microsoft-edge-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d44a-244">To learn more about these policies, see [Microsoft Edge – Browser policy reference](https://docs.microsoft.com/deployedge/microsoft-edge-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="5d44a-245">ポリシーの構成は、次の表に示すポリシーに限定されませんが、キオスク モード機能に悪影響が及びないことを確認するために、追加のポリシーをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d44a-245">Policy configuration isn't limited to the policies listed in the following table, however additional policies should be tested to ensure that kiosk mode functionality isn't negatively affected.</span></span>

|<span data-ttu-id="5d44a-246">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="5d44a-246">Group policy</span></span>|<span data-ttu-id="5d44a-247">デジタル/対話型サイネージ</span><span class="sxs-lookup"><span data-stu-id="5d44a-247">Digital\Interactive signage</span></span>|<span data-ttu-id="5d44a-248">パブリック ブラウズの単一アプリ</span><span class="sxs-lookup"><span data-stu-id="5d44a-248">Public browsing single-app</span></span>|
|--|--|--|
|[<span data-ttu-id="5d44a-249">印刷</span><span class="sxs-lookup"><span data-stu-id="5d44a-249">Printing</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printing-policies) | <span data-ttu-id="5d44a-250">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-250">Y</span></span>|<span data-ttu-id="5d44a-251">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-251">Y</span></span> |
|[<span data-ttu-id="5d44a-252">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="5d44a-252">HomePageLocation</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepagelocation) |<span data-ttu-id="5d44a-253">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-253">N</span></span> | <span data-ttu-id="5d44a-254">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-254">Y</span></span>|
|[<span data-ttu-id="5d44a-255">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="5d44a-255">ShowHomeButton</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#showhomebutton) |<span data-ttu-id="5d44a-256">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-256">N</span></span> | <span data-ttu-id="5d44a-257">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-257">Y</span></span>|
|[<span data-ttu-id="5d44a-258">NewTabPageLocation</span><span class="sxs-lookup"><span data-stu-id="5d44a-258">NewTabPageLocation</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation) |<span data-ttu-id="5d44a-259">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-259">N</span></span> |<span data-ttu-id="5d44a-260">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-260">Y</span></span> |
|[<span data-ttu-id="5d44a-261">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="5d44a-261">FavoritesBarEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#favoritesbarenabled) |<span data-ttu-id="5d44a-262">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-262">N</span></span> |<span data-ttu-id="5d44a-263">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-263">Y</span></span> |
|[<span data-ttu-id="5d44a-264">URLAllowlist</span><span class="sxs-lookup"><span data-stu-id="5d44a-264">URLAllowlist</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist) |<span data-ttu-id="5d44a-265">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-265">Y</span></span> |<span data-ttu-id="5d44a-266">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-266">Y</span></span> |
|[<span data-ttu-id="5d44a-267">URLBlocklist</span><span class="sxs-lookup"><span data-stu-id="5d44a-267">URLBlocklist</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist) |<span data-ttu-id="5d44a-268">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-268">Y</span></span> | <span data-ttu-id="5d44a-269">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-269">Y</span></span>|
|[<span data-ttu-id="5d44a-270">ManagedSearchEngines</span><span class="sxs-lookup"><span data-stu-id="5d44a-270">ManagedSearchEngines</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#managedsearchengines) |<span data-ttu-id="5d44a-271">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-271">N</span></span> | <span data-ttu-id="5d44a-272">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-272">Y</span></span>|
|[<span data-ttu-id="5d44a-273">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="5d44a-273">UserFeedbackAllowed</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed) |<span data-ttu-id="5d44a-274">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-274">N</span></span> | <span data-ttu-id="5d44a-275">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-275">Y</span></span>|
|[<span data-ttu-id="5d44a-276">VerticalTabsAllowed</span><span class="sxs-lookup"><span data-stu-id="5d44a-276">VerticalTabsAllowed</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#verticaltabsallowed) | <span data-ttu-id="5d44a-277">N</span><span class="sxs-lookup"><span data-stu-id="5d44a-277">N</span></span>|<span data-ttu-id="5d44a-278">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-278">Y</span></span> |
|[<span data-ttu-id="5d44a-279">SmartScreen の設定</span><span class="sxs-lookup"><span data-stu-id="5d44a-279">SmartScreen settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#smartscreen-settings-policies) |<span data-ttu-id="5d44a-280">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-280">Y</span></span> |<span data-ttu-id="5d44a-281">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-281">Y</span></span> |
|[<span data-ttu-id="5d44a-282">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="5d44a-282">EdgeCollectionsEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgecollectionsenabled)|<span data-ttu-id="5d44a-283">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-283">Y</span></span>|<span data-ttu-id="5d44a-284">Y</span><span class="sxs-lookup"><span data-stu-id="5d44a-284">Y</span></span>|

## <a name="microsoft-edge-with-assigned-access"></a><span data-ttu-id="5d44a-285">割り当てられたアクセスによる Microsoft Edge の使用</span><span class="sxs-lookup"><span data-stu-id="5d44a-285">Microsoft Edge with assigned access</span></span>

### <a name="single-app-kiosk"></a><span data-ttu-id="5d44a-286">シングル アプリ キオスク</span><span class="sxs-lookup"><span data-stu-id="5d44a-286">Single app kiosk</span></span>

<span data-ttu-id="5d44a-287">Microsoft Edge は現在、次のロックダウン エクスペリエンス、つまりデジタル/対話型サイネージ、およびパブリックブラウジングを備えた、単一アプリに割り当てられたアクセス用の同じ Microsoft Edge レガシ キオスク モード タイプのサブセットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5d44a-287">Microsoft Edge currently supports a subset of the same Microsoft Edge Legacy kiosk mode types for single-app assigned access with the following lockdown experiences: Digital/Interactive signage, and Public-browsing.</span></span>  

<span data-ttu-id="5d44a-288">割り当てられたアクセスを持つ Microsoft Edge キオスク モードは、現在、最新の [Windows 10 Insider Preview ビルド](https://insider.windows.com/)(バージョン 20215 以上)、 [および Microsoft Edge Beta チャネル](https://www.microsoftedgeinsider.com/download)(バージョン 89 以上) でテストできます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-288">Microsoft Edge kiosk mode with assigned access single app is currently available for testing with the latest [Windows 10 Insider Preview Build](https://insider.windows.com/), version 20215 or higher, and with the [Microsoft Edge Beta Channel](https://www.microsoftedgeinsider.com/download), version 89 or higher.</span></span>

**<span data-ttu-id="5d44a-289">Windows Insiders Preview を入手するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="5d44a-289">How do I get the Windows Insiders preview?</span></span>**

<span data-ttu-id="5d44a-290">PC に Windows 10 Insider Preview ビルドをインストールするには、「 [Windows 10 Insider Preview ビルドの概要](https://docs.microsoft.com/windows-insider/get-started)」の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="5d44a-290">To install a Windows 10 Insider Preview Build on a PC, follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>

### <a name="multi-app-kiosk"></a><span data-ttu-id="5d44a-291">複数アプリ キオスク</span><span class="sxs-lookup"><span data-stu-id="5d44a-291">Multi-app kiosk</span></span>

<span data-ttu-id="5d44a-292">Microsoft Edge は、Windows 10 で[複数アプリの割り当てられたアクセス](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) によって実行できます。これは Microsoft Edge レガシでの "通常の閲覧" タイプのキオスク モードに相当します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-292">Microsoft Edge can be run with [multi-app assigned access](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing" kiosk mode type.</span></span> <span data-ttu-id="5d44a-293">複数アプリの割り当てられたアクセスで Microsoft Edge を構成するには、[複数アプリ キオスクの設定](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)方法の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5d44a-293">To configure Microsoft Edge with multi-app assigned access, follow the instructions on how to [Set up a multi-app kiosk](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="5d44a-294">(Microsoft Edge Stable チャネルの AUMID は **MSEdge** です)。</span><span class="sxs-lookup"><span data-stu-id="5d44a-294">(The AUMID for the Microsoft Edge Stable channel is **MSEdge**).</span></span>

<span data-ttu-id="5d44a-295">複数アプリが割り当てられたアクセスで Microsoft Edge を使用する場合は、Microsoft Edge キオスクを構成するには、[Microsoft Edge ブラウザー ポリシー](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) を使用して、固有の要件を満たすように閲覧エクスペリエンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-295">When using Microsoft Edge with multi-app assigned access, you can configure Microsoft Edge kiosk to use the[Microsoft Edge browser policies](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) to configure the browsing experience to meet your unique requirements.</span></span>

### <a name="configure-using-windows-settings"></a><span data-ttu-id="5d44a-296">Windows の設定を使用して構成する</span><span class="sxs-lookup"><span data-stu-id="5d44a-296">Configure using Windows Settings</span></span>

<span data-ttu-id="5d44a-297">Windows の設定は、1 つか 2 つのシングル アプリのキオスク デバイスを設定する最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="5d44a-297">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="5d44a-298">シングル アプリのキオスク コンピューターをセットアップするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5d44a-298">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="5d44a-299">最新の Windows 10 Insider Preview (バージョン 20215 以降) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5d44a-299">Install the latest Windows 10 Insider Preview, version 20215 or higher.</span></span> <span data-ttu-id="5d44a-300">「[Windows 10 Insider Preview ビルドの概要](https://docs.microsoft.com/windows-insider/get-started)」の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="5d44a-300">Follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>
2. <span data-ttu-id="5d44a-301">最新の機能をテストするには、最新の [Microsoft Edge Beta チャネル](https://www.microsoftedgeinsider.com/download)(バージョン 89 以上) をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-301">To test the latest features, you can download the latest [Microsoft Edge Beta channel](https://www.microsoftedgeinsider.com/download), version 89 or higher.</span></span>
3. <span data-ttu-id="5d44a-302">キオスク コンピューターで、[Windows の設定] を開き、検索フィールドに "キオスク" と入力します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-302">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="5d44a-303">次のスクリーンショットに表示されている  **[Set up a kiosk (assigned access)]** (キオスク モードを設定する (割り当てられたアクセス)) を選択し、キオスクを作成するダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-303">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

4. <span data-ttu-id="5d44a-305">**[Set up a kiosk]**  (キオスク モードを設定する) ページで、 **[開始する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d44a-305">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="キオスク ページ - 開始する":::

5. <span data-ttu-id="5d44a-307">名前を入力して新しいキオスク アカウントを作成するか、または入力されているドロップダウン リストから既存のアカウントを選択して、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d44a-307">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="キオスク モード - アカウントの作成":::

6. <span data-ttu-id="5d44a-309">**[キオスク アプリを選ぶ]**  ページで、**[Microsoft Edge]** を選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d44a-309">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5d44a-310">これは、Microsoft Edge Dev、Beta、Stable チャネルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-310">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="キオスク モード - アプリを選ぶ":::

7. <span data-ttu-id="5d44a-312">Microsoft Edge がキオスク モードで実行しているときの表示方法について、次のいずれかのオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-312">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="5d44a-313">デジタル/対話型サイネージ - 全画面表示モードで特定のサイトを表示し、Microsoft Edge を実行します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-313">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="5d44a-314">パブリック ブラウザー - Microsoft Edge の限定的な複数タブのバージョンを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-314">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="キオスク モードの表示 - 全画面表示デジタル署名":::

8. <span data-ttu-id="5d44a-316"> *\*[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-316">Select **Next**.</span></span>
9. <span data-ttu-id="5d44a-317">キオスクが起動したときに読み込む URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-317">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="キオスク モード - URL の入力":::

10. <span data-ttu-id="5d44a-319">アイドル時間に、既定値の 5 分をそのまま使用するか、独自の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-319">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="キオスク モード - アイドル時間の入力":::

11. <span data-ttu-id="5d44a-321"> *\*[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d44a-321">Click **Next**.</span></span>
12. <span data-ttu-id="5d44a-322"> *\*[設定]**  ウィンドウを閉じて、選択内容を保存して適用します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-322">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="キオスク モード - 設定の終了":::

13. <span data-ttu-id="5d44a-324">キオスク デバイスからサインオフし、ローカル キオスク アカウントでサインインして、構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-324">Sign out from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <a name="functional-limitations"></a><span data-ttu-id="5d44a-325">機能上の制限事項</span><span class="sxs-lookup"><span data-stu-id="5d44a-325">Functional limitations</span></span>

<span data-ttu-id="5d44a-326">このキオスク モードのプレビュー版をリリースすることにより、Microsoft は商品の改善と新機能の追加に継続的に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-326">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="5d44a-327">次の機能をオフにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5d44a-327">We recommend that you turn off:</span></span>

- [<span data-ttu-id="5d44a-328">InPrivateModeAvailability</span><span class="sxs-lookup"><span data-stu-id="5d44a-328">InPrivateModeAvailability</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)
- [<span data-ttu-id="5d44a-329">IsolateOrigins</span><span class="sxs-lookup"><span data-stu-id="5d44a-329">IsolateOrigins</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#isolateorigins)
- [<span data-ttu-id="5d44a-330">ManagedFavorites</span><span class="sxs-lookup"><span data-stu-id="5d44a-330">ManagedFavorites</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#managedfavorites)
- [<span data-ttu-id="5d44a-331">EdgeShoppingAssistantEnabled</span><span class="sxs-lookup"><span data-stu-id="5d44a-331">EdgeShoppingAssistantEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgeshoppingassistantenabled)
- [<span data-ttu-id="5d44a-332">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="5d44a-332">EdgeCollectionsEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgecollectionsenabled)
- [<span data-ttu-id="5d44a-333">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="5d44a-333">UserFeedbackAllowed</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed)
- [<span data-ttu-id="5d44a-334">DefaultPopupsSetting</span><span class="sxs-lookup"><span data-stu-id="5d44a-334">DefaultPopupsSetting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#defaultpopupssetting)
- [<span data-ttu-id="5d44a-335">StartupBoostEnabled</span><span class="sxs-lookup"><span data-stu-id="5d44a-335">StartupBoostEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startupboostenabled)
- [<span data-ttu-id="5d44a-336">InternetExplorerIntegrationLevel</span><span class="sxs-lookup"><span data-stu-id="5d44a-336">InternetExplorerIntegrationLevel</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationlevel)
- [<span data-ttu-id="5d44a-337">拡張機能</span><span class="sxs-lookup"><span data-stu-id="5d44a-337">Extensions</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions-policies)
- [<span data-ttu-id="5d44a-338">BackgroundModeEnabled</span><span class="sxs-lookup"><span data-stu-id="5d44a-338">BackgroundModeEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)

## <a name="roadmap"></a><span data-ttu-id="5d44a-339">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="5d44a-339">Roadmap</span></span>

### <a name="in-early-2021"></a><span data-ttu-id="5d44a-340">2021 年初旬</span><span class="sxs-lookup"><span data-stu-id="5d44a-340">In early 2021</span></span>

<span data-ttu-id="5d44a-341">次のサポートと機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-341">We'll add the following support and features:</span></span>

- <span data-ttu-id="5d44a-342">シングル アプリとして割り当てられたアクセスによる Microsoft Edge キオスク モードの Windows 10 1909 またはそれ以上での一般提供。</span><span class="sxs-lookup"><span data-stu-id="5d44a-342">General availability of Microsoft Edge kiosk mode with assigned access single app on Windows 10 1909 and higher.</span></span>
- <span data-ttu-id="5d44a-343">Microsoft Edge 従来版とのパリティのための追加機能。</span><span class="sxs-lookup"><span data-stu-id="5d44a-343">Additional features for parity with Microsoft Edge Legacy.</span></span>
- <span data-ttu-id="5d44a-344">キオスク モード プロファイル UX を使用してデバイスを構成するための Intune との統合。</span><span class="sxs-lookup"><span data-stu-id="5d44a-344">Integration with Intune to configure devices using kiosk mode profile UX.</span></span>
- <span data-ttu-id="5d44a-345">ブラウザーからの他のアプリケーションの起動を制限します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-345">Restrict the launch of other applications from the browser.</span></span>
- <span data-ttu-id="5d44a-346">UI 印刷設定のロックダウン。</span><span class="sxs-lookup"><span data-stu-id="5d44a-346">UI print settings lockdown.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d44a-347">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d44a-347">See also</span></span>

- [<span data-ttu-id="5d44a-348">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="5d44a-348">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="5d44a-349">Microsoft Edge の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="5d44a-349">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="5d44a-350">Windows デスクトップ エディションでのキオスクおよびデジタル サイネージの構成</span><span class="sxs-lookup"><span data-stu-id="5d44a-350">Configure kiosks and digital signs on Windows desktop editions</span></span>](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [<span data-ttu-id="5d44a-351">キオスク モードの移行を計画する</span><span class="sxs-lookup"><span data-stu-id="5d44a-351">Plan your kiosk mode transition</span></span>](microsoft-edge-kiosk-mode-transition-plan.md)
