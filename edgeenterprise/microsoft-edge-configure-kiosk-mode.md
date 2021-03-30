---
title: Microsoft Edge キオスク モードを構成する
ms.author: aguta
author: aguta
manager: srugh
ms.date: 03/16/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: キオスク モード機能と Microsoft Edge キオスク モードのオプションを構成する方法について説明します。
ms.openlocfilehash: 9d76bfcaebeaf56e627a401cc4f0375bce9d17a3
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11448131"
---
# <a name="configure-microsoft-edge-kiosk-mode"></a><span data-ttu-id="ec865-103">Microsoft Edge キオスク モードを構成する</span><span class="sxs-lookup"><span data-stu-id="ec865-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="ec865-104">この記事では、パイロットを実行することができる Microsoft Edge キオスク モードのオプションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec865-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="ec865-105">また、対象としている機能のロードマップも含まれます。</span><span class="sxs-lookup"><span data-stu-id="ec865-105">There's also a roadmap of features we're targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="ec865-106">この記事は Microsoft Edge version 87 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ec865-106">This article applies to Microsoft Edge version 87 or later.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec865-107">[「キオスク モード機能の使用」](#use-kiosk-mode-features)で提供されているコマンド ライン引数を使用して、Windows 10 で Microsoft Edgeキオスク モード機能 を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ec865-107">Invoke Microsoft Edge kiosk mode features on Windows 10 using the command line arguments provided in [Use kiosk mode features](#use-kiosk-mode-features).</span></span>

## <a name="overview"></a><span data-ttu-id="ec865-108">概要</span><span class="sxs-lookup"><span data-stu-id="ec865-108">Overview</span></span>

<span data-ttu-id="ec865-109">Microsoft Edge キオスク モードは、ブラウザーの 2 つのロックダウン エクスペリエンスを提供し、組織が顧客に最高のエクスペリエンスを作成し、管理し、提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ec865-109">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="ec865-110">次のロックダウン エクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="ec865-110">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="ec865-111">**デジタル/対話型サイネージ** エクスペリエンスでは、全画面表示モードで特定のサイトを表示します。</span><span class="sxs-lookup"><span data-stu-id="ec865-111">**Digital/Interactive Signage** experience - Displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="ec865-112">**パブリック ブラウジング** エクスペリエンスでは、Microsoft Edge の限定的な複数タブのバージョンを実行します。</span><span class="sxs-lookup"><span data-stu-id="ec865-112">**Public-Browsing** experience - Runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="ec865-113">どちらのエクスペリエンスでも、ユーザー データを保護する Microsoft Edge InPrivate セッションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ec865-113">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <a name="set-up-microsoft-edge-kiosk-mode"></a><span data-ttu-id="ec865-114">Microsoft Edge キオスク モードのセットアップ</span><span class="sxs-lookup"><span data-stu-id="ec865-114">Set up Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="ec865-115">キオスク モード機能の初期セットが Microsoft Edge Canary チャネルのバージョン 87 でテストに使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ec865-115">An initial set of kiosk mode features is available to test with Microsoft Edge Stable Channel, version 87.</span></span> <span data-ttu-id="ec865-116">[Microsoft Edge (Official Stable チャネル)](https://www.microsoft.com/edge) から 最新バージョンをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="ec865-116">You can download the latest version from [Microsoft Edge (Official Stable Channel)](https://www.microsoft.com/edge).</span></span>

### <a name="kiosk-mode-supported-features"></a><span data-ttu-id="ec865-117">キオスク モードでサポートされる機能</span><span class="sxs-lookup"><span data-stu-id="ec865-117">Kiosk mode supported features</span></span>

<span data-ttu-id="ec865-118">次の表に、Microsoft Edge と Microsoft Edge レガシのキオスク モードでサポートされる機能を示します。</span><span class="sxs-lookup"><span data-stu-id="ec865-118">The following table lists the features supported by kiosk mode in Microsoft Edge and Microsoft Edge Legacy.</span></span> <span data-ttu-id="ec865-119">次の表を Microsoft Edge への移行のためのガイドとして使用し、Microsoft Edge の両方のバージョンでこれらの機能がどのようにサポートされているかを比較してください。</span><span class="sxs-lookup"><span data-stu-id="ec865-119">Use this table as a guide to transitioning to Microsoft Edge by comparing how these features are supported in both versions of Microsoft Edge.</span></span>

|<span data-ttu-id="ec865-120">機能</span><span class="sxs-lookup"><span data-stu-id="ec865-120">Feature</span></span>|<span data-ttu-id="ec865-121">デジタル/対話型サイネージ</span><span class="sxs-lookup"><span data-stu-id="ec865-121">Digital\Interactive Signage</span></span>|<span data-ttu-id="ec865-122">パブリック ブラウジング</span><span class="sxs-lookup"><span data-stu-id="ec865-122">Public browsing</span></span>|<span data-ttu-id="ec865-123">Microsoft Edge のバージョン (以上) で利用可能</span><span class="sxs-lookup"><span data-stu-id="ec865-123">Available with Microsoft Edge version (and higher)</span></span>|<span data-ttu-id="ec865-124">Microsoft Edge レガシで使用可能</span><span class="sxs-lookup"><span data-stu-id="ec865-124">Available with Microsoft Edge Legacy</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="ec865-125">InPrivate ナビゲーション。</span><span class="sxs-lookup"><span data-stu-id="ec865-125">InPrivate Navigation</span></span>|<span data-ttu-id="ec865-126">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-126">Y</span></span>|<span data-ttu-id="ec865-127">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-127">Y</span></span>|<span data-ttu-id="ec865-128">89</span><span class="sxs-lookup"><span data-stu-id="ec865-128">89</span></span>|<span data-ttu-id="ec865-129">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-129">Y</span></span>|
|<span data-ttu-id="ec865-130">非アクティブ時のリセット</span><span class="sxs-lookup"><span data-stu-id="ec865-130">Reset on inactivity</span></span>|<span data-ttu-id="ec865-131">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-131">Y</span></span>|<span data-ttu-id="ec865-132">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-132">Y</span></span>|<span data-ttu-id="ec865-133">89</span><span class="sxs-lookup"><span data-stu-id="ec865-133">89</span></span>|<span data-ttu-id="ec865-134">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-134">Y</span></span>|
|<span data-ttu-id="ec865-135">[読み取り専用アドレス バー](./microsoft-edge-policies.md#kioskaddressbareditingenabled) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="ec865-135">[Read only address bar](./microsoft-edge-policies.md#kioskaddressbareditingenabled) (policy)</span></span> |<span data-ttu-id="ec865-136">N</span><span class="sxs-lookup"><span data-stu-id="ec865-136">N</span></span>|<span data-ttu-id="ec865-137">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-137">Y</span></span> |<span data-ttu-id="ec865-138">89</span><span class="sxs-lookup"><span data-stu-id="ec865-138">89</span></span>|<span data-ttu-id="ec865-139">N</span><span class="sxs-lookup"><span data-stu-id="ec865-139">N</span></span>|
|<span data-ttu-id="ec865-140">[終了時にダウンロードを削除する](./microsoft-edge-policies.md#kioskdeletedownloadsonexit) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="ec865-140">[Delete downloads on exit](./microsoft-edge-policies.md#kioskdeletedownloadsonexit) (policy)</span></span>  | <span data-ttu-id="ec865-141">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-141">Y</span></span>|<span data-ttu-id="ec865-142">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-142">Y</span></span> |<span data-ttu-id="ec865-143">89</span><span class="sxs-lookup"><span data-stu-id="ec865-143">89</span></span>|<span data-ttu-id="ec865-144">N</span><span class="sxs-lookup"><span data-stu-id="ec865-144">N</span></span>|
|<span data-ttu-id="ec865-145">F11 がブロックされています (全画面に入る/終了する)</span><span class="sxs-lookup"><span data-stu-id="ec865-145">F11 blocked (enter/exit full-screen)</span></span> | <span data-ttu-id="ec865-146">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-146">Y</span></span> | <span data-ttu-id="ec865-147">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-147">Y</span></span> | <span data-ttu-id="ec865-148">89</span><span class="sxs-lookup"><span data-stu-id="ec865-148">89</span></span> |<span data-ttu-id="ec865-149">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-149">Y</span></span>|
|<span data-ttu-id="ec865-150">F12 がブロックされています (開発者ツールの起動)</span><span class="sxs-lookup"><span data-stu-id="ec865-150">F12 blocked (launch Developer Tools)</span></span> | <span data-ttu-id="ec865-151">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-151">Y</span></span> | <span data-ttu-id="ec865-152">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-152">Y</span></span> | <span data-ttu-id="ec865-153">89</span><span class="sxs-lookup"><span data-stu-id="ec865-153">89</span></span> |<span data-ttu-id="ec865-154">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-154">Y</span></span>|
| <span data-ttu-id="ec865-155">複数タブのサポート</span><span class="sxs-lookup"><span data-stu-id="ec865-155">Multi tab support</span></span> | <span data-ttu-id="ec865-156">N</span><span class="sxs-lookup"><span data-stu-id="ec865-156">N</span></span>| <span data-ttu-id="ec865-157">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-157">Y</span></span>| <span data-ttu-id="ec865-158">89</span><span class="sxs-lookup"><span data-stu-id="ec865-158">89</span></span>|<span data-ttu-id="ec865-159">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-159">Y</span></span>|
|<span data-ttu-id="ec865-160">[URL のサポートを許可する](./microsoft-edge-policies.md#urlallowlist) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="ec865-160">[Allow URL support](./microsoft-edge-policies.md#urlallowlist) (policy)</span></span>|<span data-ttu-id="ec865-161">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-161">Y</span></span>|<span data-ttu-id="ec865-162">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-162">Y</span></span>|<span data-ttu-id="ec865-163">89</span><span class="sxs-lookup"><span data-stu-id="ec865-163">89</span></span>|<span data-ttu-id="ec865-164">N</span><span class="sxs-lookup"><span data-stu-id="ec865-164">N</span></span>|
|<span data-ttu-id="ec865-165">[URL のサポートをブロックする](./microsoft-edge-policies.md#urlblocklist) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="ec865-165">[Block URL support](./microsoft-edge-policies.md#urlblocklist) (policy)</span></span>|<span data-ttu-id="ec865-166">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-166">Y</span></span>|<span data-ttu-id="ec865-167">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-167">Y</span></span>|<span data-ttu-id="ec865-168">89</span><span class="sxs-lookup"><span data-stu-id="ec865-168">89</span></span>|<span data-ttu-id="ec865-169">N</span><span class="sxs-lookup"><span data-stu-id="ec865-169">N</span></span>|
|<span data-ttu-id="ec865-170">[[ホーム] ボタンを表示する](./microsoft-edge-policies.md#showhomebutton) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="ec865-170">[Show home button](./microsoft-edge-policies.md#showhomebutton) (policy)</span></span>|<span data-ttu-id="ec865-171">N</span><span class="sxs-lookup"><span data-stu-id="ec865-171">N</span></span>|<span data-ttu-id="ec865-172">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-172">Y</span></span>|<span data-ttu-id="ec865-173">89</span><span class="sxs-lookup"><span data-stu-id="ec865-173">89</span></span>|<span data-ttu-id="ec865-174">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-174">Y</span></span>|
|<span data-ttu-id="ec865-175">[お気に入りを管理する](./microsoft-edge-policies.md#managedfavorites) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="ec865-175">[Manage favorites](./microsoft-edge-policies.md#managedfavorites) (policy)</span></span>|<span data-ttu-id="ec865-176">N</span><span class="sxs-lookup"><span data-stu-id="ec865-176">N</span></span>|<span data-ttu-id="ec865-177">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-177">Y</span></span>|<span data-ttu-id="ec865-178">89</span><span class="sxs-lookup"><span data-stu-id="ec865-178">89</span></span>|<span data-ttu-id="ec865-179">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-179">Y</span></span>|
|<span data-ttu-id="ec865-180">[プリンターを有効化](./microsoft-edge-policies.md#printingenabled) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="ec865-180">[Enable printer](./microsoft-edge-policies.md#printingenabled) (policy)</span></span>|<span data-ttu-id="ec865-181">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-181">Y</span></span>|<span data-ttu-id="ec865-182">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-182">Y</span></span>|<span data-ttu-id="ec865-183">89</span><span class="sxs-lookup"><span data-stu-id="ec865-183">89</span></span>|<span data-ttu-id="ec865-184">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-184">Y</span></span>|
|<span data-ttu-id="ec865-185">[新しいタブ ページの URLを構成する](./microsoft-edge-policies.md#newtabpagelocation) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="ec865-185">[Configure the new tab page URL](./microsoft-edge-policies.md#newtabpagelocation) (policy)</span></span>|<span data-ttu-id="ec865-186">N</span><span class="sxs-lookup"><span data-stu-id="ec865-186">N</span></span>|<span data-ttu-id="ec865-187">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-187">Y</span></span>||<span data-ttu-id="ec865-188">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-188">Y</span></span>|
|<span data-ttu-id="ec865-189">[セッションの終了] ボタン \*</span><span class="sxs-lookup"><span data-stu-id="ec865-189">End session button \*</span></span> | <span data-ttu-id="ec865-190">N</span><span class="sxs-lookup"><span data-stu-id="ec865-190">N</span></span>| <span data-ttu-id="ec865-191">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-191">Y</span></span>| <span data-ttu-id="ec865-192">89</span><span class="sxs-lookup"><span data-stu-id="ec865-192">89</span></span>|<span data-ttu-id="ec865-193">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-193">Y</span></span>|
|<span data-ttu-id="ec865-194">すべての内部 Microsoft Edge URL はブロックされます (*edge://downloads* および *edge://print* を除く)</span><span class="sxs-lookup"><span data-stu-id="ec865-194">All internal Microsoft Edge URLs are blocked, except for *edge://downloads* and *edge://print*</span></span> |<span data-ttu-id="ec865-195">N</span><span class="sxs-lookup"><span data-stu-id="ec865-195">N</span></span>|<span data-ttu-id="ec865-196">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-196">Y</span></span>|<span data-ttu-id="ec865-197">89</span><span class="sxs-lookup"><span data-stu-id="ec865-197">89</span></span>|<span data-ttu-id="ec865-198">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-198">Y</span></span>|
| <span data-ttu-id="ec865-199">Ctrl + N がブロックされています (新しいウィンドウを開く) \*</span><span class="sxs-lookup"><span data-stu-id="ec865-199">CTRL+N blocked (open a new window) \*</span></span> | <span data-ttu-id="ec865-200">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-200">Y</span></span> | <span data-ttu-id="ec865-201">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-201">Y</span></span> | <span data-ttu-id="ec865-202">89</span><span class="sxs-lookup"><span data-stu-id="ec865-202">89</span></span> |<span data-ttu-id="ec865-203">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-203">Y</span></span>|
| <span data-ttu-id="ec865-204">Ctrl + T がブロックされています (新しいタブを開く)</span><span class="sxs-lookup"><span data-stu-id="ec865-204">CTRL+T blocked (open new tab)</span></span> |<span data-ttu-id="ec865-205">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-205">Y</span></span> | <span data-ttu-id="ec865-206">N</span><span class="sxs-lookup"><span data-stu-id="ec865-206">N</span></span> | <span data-ttu-id="ec865-207">89</span><span class="sxs-lookup"><span data-stu-id="ec865-207">89</span></span> |<span data-ttu-id="ec865-208">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-208">Y</span></span>|
|<span data-ttu-id="ec865-209">設定と詳細 (...) では、必要なオプションだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec865-209">Settings and more (...) will display only the required options</span></span>  |<span data-ttu-id="ec865-210">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-210">Y</span></span> |<span data-ttu-id="ec865-211">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-211">Y</span></span> |<span data-ttu-id="ec865-212">89</span><span class="sxs-lookup"><span data-stu-id="ec865-212">89</span></span> |<span data-ttu-id="ec865-213">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-213">Y</span></span>|
|<span data-ttu-id="ec865-214">ブラウザーからの他のアプリケーションの起動を制限する</span><span class="sxs-lookup"><span data-stu-id="ec865-214">Restrict the launch of other applications from the browser</span></span>|<span data-ttu-id="ec865-215">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-215">Y</span></span>|<span data-ttu-id="ec865-216">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-216">Y</span></span>|<span data-ttu-id="ec865-217">90/91</span><span class="sxs-lookup"><span data-stu-id="ec865-217">90/91</span></span>|<span data-ttu-id="ec865-218">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-218">Y</span></span>|
|<span data-ttu-id="ec865-219">UI 印刷設定のロックダウン</span><span class="sxs-lookup"><span data-stu-id="ec865-219">UI print settings lockdown</span></span>|<span data-ttu-id="ec865-220">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-220">Y</span></span>|<span data-ttu-id="ec865-221">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-221">Y</span></span>|<span data-ttu-id="ec865-222">90/91</span><span class="sxs-lookup"><span data-stu-id="ec865-222">90/91</span></span>|<span data-ttu-id="ec865-223">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-223">Y</span></span>|
|<span data-ttu-id="ec865-224">[新しいタブ ページをホーム ページとして設定する](./microsoft-edge-policies.md#homepageisnewtabpage) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="ec865-224">[Set the new tab page as the home page](./microsoft-edge-policies.md#homepageisnewtabpage) (policy)</span></span>|-|-|<span data-ttu-id="ec865-225">TBD</span><span class="sxs-lookup"><span data-stu-id="ec865-225">TBD</span></span>|<span data-ttu-id="ec865-226">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-226">Y</span></span>|

> [!NOTE]
> <span data-ttu-id="ec865-227">"\*" に続く機能は、割り当てられたアクセス単一アプリのシナリオでのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="ec865-227">Features followed by "\*" are only enabled in an assigned access single app scenario.</span></span>

## <a name="use-kiosk-mode-features"></a><span data-ttu-id="ec865-228">キオスク モード機能を使用する</span><span class="sxs-lookup"><span data-stu-id="ec865-228">Use kiosk mode features</span></span>

<span data-ttu-id="ec865-229">Microsoft Edge キオスク モード機能は、デジタル/対話型サイネージおよびパブリック ブラウジング用の次の Windows 10 コマンドライン オプションで起動できます。</span><span class="sxs-lookup"><span data-stu-id="ec865-229">Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options for Digital/Interactive signage and Public browsing.</span></span>

### <a name="kiosk-mode-digitalinteractive-signage"></a><span data-ttu-id="ec865-230">キオスク モード デジタル/対話型サイネージ</span><span class="sxs-lookup"><span data-stu-id="ec865-230">Kiosk mode Digital/Interactive signage</span></span>
 
```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen
```

### <a name="kiosk-mode-public-browsing"></a><span data-ttu-id="ec865-231">キオスク モードのパブリック ブラウジング</span><span class="sxs-lookup"><span data-stu-id="ec865-231">Kiosk mode Public browsing</span></span>

```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing
```

### <a name="additional-command-line-options"></a><span data-ttu-id="ec865-232">その他のコマンド ライン オプション</span><span class="sxs-lookup"><span data-stu-id="ec865-232">Additional command line options</span></span>

- <span data-ttu-id="ec865-233">**--no-first-run**: 最初の Microsoft Edge 実行エクスペリエンスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ec865-233">**--no-first-run**: Disable the first Microsoft Edge run experience.</span></span>

   ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --no-first-run
  ```

  ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --no-first-run
  ```

- <span data-ttu-id="ec865-234">**--kiosk-idle-timeout-minutes=**: Microsoft Edge キオスク モードがユーザーのセッションをリセットする前に、最後のユーザー アクティビティからの時間 (分) を変更します。</span><span class="sxs-lookup"><span data-stu-id="ec865-234">**--kiosk-idle-timeout-minutes=**: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="ec865-235">次の例の "value" を分数に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ec865-235">Replace "value" in the next example with the number of minutes.</span></span>

   ```
   --kiosk-idle-timeout-minutes=value
   ``` 
   <span data-ttu-id="ec865-236">次の "値" がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ec865-236">The following "values" are supported:</span></span>

     - <span data-ttu-id="ec865-237">既定値 (分)</span><span class="sxs-lookup"><span data-stu-id="ec865-237">Default values (in minutes)</span></span>
       - <span data-ttu-id="ec865-238">全画面 - 0 (オフ)</span><span class="sxs-lookup"><span data-stu-id="ec865-238">Full screen - 0 (turned off)</span></span>
       - <span data-ttu-id="ec865-239">パブリック ブラウジング - 5 分</span><span class="sxs-lookup"><span data-stu-id="ec865-239">Public browsing - 5 minutes</span></span>
    - <span data-ttu-id="ec865-240">指定可能な値</span><span class="sxs-lookup"><span data-stu-id="ec865-240">Allowed values</span></span>
      - <span data-ttu-id="ec865-241">0 - タイマーをオフにします</span><span class="sxs-lookup"><span data-stu-id="ec865-241">0 - turns off the timer</span></span>
      - <span data-ttu-id="ec865-242">1 - 1440 分 (アイドル タイマー時のリセット)</span><span class="sxs-lookup"><span data-stu-id="ec865-242">1-1440 minutes for reset on idle timer</span></span>


    ```
    msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --kiosk-idle-timeout-minutes=1
   ```

   ```
   msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --kiosk-idle-timeout-minutes=1
   ```

## <a name="support-policies-for-kiosk-mode"></a><span data-ttu-id="ec865-243">キオスク モードでサポートされているポリシー</span><span class="sxs-lookup"><span data-stu-id="ec865-243">Support policies for kiosk mode</span></span>

<span data-ttu-id="ec865-244">以下の表にある Microsoft Edge ポリシーのいずれかを使用して、構成する Microsoft Edge キオスク モードの種類に応じてキオスク エクスペリエンスを強化します。</span><span class="sxs-lookup"><span data-stu-id="ec865-244">Use any of the Microsoft Edge policies listed in the following table to enhance the kiosk experience for the Microsoft Edge kiosk mode type you configure.</span></span> <span data-ttu-id="ec865-245">これらのポリシーの詳細については、「[Microsoft Edge - ブラウザー ポリシー リファレンス](./microsoft-edge-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec865-245">To learn more about these policies, see [Microsoft Edge – Browser policy reference](./microsoft-edge-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ec865-246">ポリシーの構成は、次の表に示すポリシーに限定されませんが、キオスク モード機能に悪影響が及びないことを確認するために、追加のポリシーをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec865-246">Policy configuration isn't limited to the policies listed in the following table, however additional policies should be tested to ensure that kiosk mode functionality isn't negatively affected.</span></span>

|<span data-ttu-id="ec865-247">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="ec865-247">Group policy</span></span>|<span data-ttu-id="ec865-248">デジタル/対話型サイネージ</span><span class="sxs-lookup"><span data-stu-id="ec865-248">Digital\Interactive signage</span></span>|<span data-ttu-id="ec865-249">パブリック ブラウズの単一アプリ</span><span class="sxs-lookup"><span data-stu-id="ec865-249">Public browsing single-app</span></span>|
|--|--|--|
|[<span data-ttu-id="ec865-250">印刷</span><span class="sxs-lookup"><span data-stu-id="ec865-250">Printing</span></span>](./microsoft-edge-policies.md#printing-policies) | <span data-ttu-id="ec865-251">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-251">Y</span></span>|<span data-ttu-id="ec865-252">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-252">Y</span></span> |
|[<span data-ttu-id="ec865-253">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="ec865-253">HomePageLocation</span></span>](./microsoft-edge-policies.md#homepagelocation) |<span data-ttu-id="ec865-254">N</span><span class="sxs-lookup"><span data-stu-id="ec865-254">N</span></span> | <span data-ttu-id="ec865-255">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-255">Y</span></span>|
|[<span data-ttu-id="ec865-256">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="ec865-256">ShowHomeButton</span></span>](./microsoft-edge-policies.md#showhomebutton) |<span data-ttu-id="ec865-257">N</span><span class="sxs-lookup"><span data-stu-id="ec865-257">N</span></span> | <span data-ttu-id="ec865-258">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-258">Y</span></span>|
|[<span data-ttu-id="ec865-259">NewTabPageLocation</span><span class="sxs-lookup"><span data-stu-id="ec865-259">NewTabPageLocation</span></span>](./microsoft-edge-policies.md#newtabpagelocation) |<span data-ttu-id="ec865-260">N</span><span class="sxs-lookup"><span data-stu-id="ec865-260">N</span></span> |<span data-ttu-id="ec865-261">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-261">Y</span></span> |
|[<span data-ttu-id="ec865-262">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="ec865-262">FavoritesBarEnabled</span></span>](./microsoft-edge-policies.md#favoritesbarenabled) |<span data-ttu-id="ec865-263">N</span><span class="sxs-lookup"><span data-stu-id="ec865-263">N</span></span> |<span data-ttu-id="ec865-264">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-264">Y</span></span> |
|[<span data-ttu-id="ec865-265">URLAllowlist</span><span class="sxs-lookup"><span data-stu-id="ec865-265">URLAllowlist</span></span>](./microsoft-edge-policies.md#urlallowlist) |<span data-ttu-id="ec865-266">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-266">Y</span></span> |<span data-ttu-id="ec865-267">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-267">Y</span></span> |
|[<span data-ttu-id="ec865-268">URLBlocklist</span><span class="sxs-lookup"><span data-stu-id="ec865-268">URLBlocklist</span></span>](./microsoft-edge-policies.md#urlblocklist) |<span data-ttu-id="ec865-269">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-269">Y</span></span> | <span data-ttu-id="ec865-270">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-270">Y</span></span>|
|[<span data-ttu-id="ec865-271">ManagedSearchEngines</span><span class="sxs-lookup"><span data-stu-id="ec865-271">ManagedSearchEngines</span></span>](./microsoft-edge-policies.md#managedsearchengines) |<span data-ttu-id="ec865-272">N</span><span class="sxs-lookup"><span data-stu-id="ec865-272">N</span></span> | <span data-ttu-id="ec865-273">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-273">Y</span></span>|
|[<span data-ttu-id="ec865-274">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="ec865-274">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed) |<span data-ttu-id="ec865-275">N</span><span class="sxs-lookup"><span data-stu-id="ec865-275">N</span></span> | <span data-ttu-id="ec865-276">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-276">Y</span></span>|
|[<span data-ttu-id="ec865-277">VerticalTabsAllowed</span><span class="sxs-lookup"><span data-stu-id="ec865-277">VerticalTabsAllowed</span></span>](./microsoft-edge-policies.md#verticaltabsallowed) | <span data-ttu-id="ec865-278">N</span><span class="sxs-lookup"><span data-stu-id="ec865-278">N</span></span>|<span data-ttu-id="ec865-279">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-279">Y</span></span> |
|[<span data-ttu-id="ec865-280">SmartScreen の設定</span><span class="sxs-lookup"><span data-stu-id="ec865-280">SmartScreen settings</span></span>](./microsoft-edge-policies.md#smartscreen-settings-policies) |<span data-ttu-id="ec865-281">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-281">Y</span></span> |<span data-ttu-id="ec865-282">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-282">Y</span></span> |
|[<span data-ttu-id="ec865-283">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="ec865-283">EdgeCollectionsEnabled</span></span>](./microsoft-edge-policies.md#edgecollectionsenabled)|<span data-ttu-id="ec865-284">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-284">Y</span></span>|<span data-ttu-id="ec865-285">Y</span><span class="sxs-lookup"><span data-stu-id="ec865-285">Y</span></span>|

## <a name="microsoft-edge-with-assigned-access"></a><span data-ttu-id="ec865-286">割り当てられたアクセスによる Microsoft Edge の使用</span><span class="sxs-lookup"><span data-stu-id="ec865-286">Microsoft Edge with assigned access</span></span>

### <a name="single-app-kiosk"></a><span data-ttu-id="ec865-287">シングル アプリ キオスク</span><span class="sxs-lookup"><span data-stu-id="ec865-287">Single app kiosk</span></span>

<span data-ttu-id="ec865-288">Microsoft Edge は現在、次のロックダウン エクスペリエンス、つまりデジタル/対話型サイネージ、およびパブリックブラウジングを備えた、単一アプリに割り当てられたアクセス用の同じ Microsoft Edge レガシ キオスク モード タイプのサブセットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ec865-288">Microsoft Edge currently supports a subset of the same Microsoft Edge Legacy kiosk mode types for single-app assigned access with the following lockdown experiences: Digital/Interactive signage, and Public-browsing.</span></span>  

<span data-ttu-id="ec865-289">割り当てられたアクセスを持つ Microsoft Edge キオスク モードは、現在、最新の [Windows 10 Insider Preview ビルド](https://insider.windows.com/)(バージョン 20215 以上)、 [および Microsoft Edge Beta チャネル](https://www.microsoftedgeinsider.com/download)(バージョン 89 以上) でテストできます。</span><span class="sxs-lookup"><span data-stu-id="ec865-289">Microsoft Edge kiosk mode with assigned access single app is currently available for testing with the latest [Windows 10 Insider Preview Build](https://insider.windows.com/), version 20215 or higher, and with the [Microsoft Edge Beta Channel](https://www.microsoftedgeinsider.com/download), version 89 or higher.</span></span>

**<span data-ttu-id="ec865-290">Windows Insiders Preview を入手するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="ec865-290">How do I get the Windows Insiders preview?</span></span>**

<span data-ttu-id="ec865-291">PC に Windows 10 Insider Preview ビルドをインストールするには、「 [Windows 10 Insider Preview ビルドの概要](/windows-insider/get-started)」の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="ec865-291">To install a Windows 10 Insider Preview Build on a PC, follow the instructions in [Getting started with Windows 10 Insider Preview Builds](/windows-insider/get-started).</span></span>

### <a name="multi-app-kiosk"></a><span data-ttu-id="ec865-292">複数アプリ キオスク</span><span class="sxs-lookup"><span data-stu-id="ec865-292">Multi-app kiosk</span></span>

<span data-ttu-id="ec865-293">Microsoft Edge は、Windows 10 で[複数アプリの割り当てられたアクセス](/windows/configuration/lock-down-windows-10-to-specific-apps) によって実行できます。これは Microsoft Edge レガシでの "通常の閲覧" タイプのキオスク モードに相当します。</span><span class="sxs-lookup"><span data-stu-id="ec865-293">Microsoft Edge can be run with [multi-app assigned access](/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing" kiosk mode type.</span></span> <span data-ttu-id="ec865-294">複数アプリの割り当てられたアクセスで Microsoft Edge を構成するには、[複数アプリ キオスクの設定](/windows/configuration/lock-down-windows-10-to-specific-apps)方法の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ec865-294">To configure Microsoft Edge with multi-app assigned access, follow the instructions on how to [Set up a multi-app kiosk](/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="ec865-295">(Microsoft Edge Stable チャネルの AUMID は **MSEdge** です)。</span><span class="sxs-lookup"><span data-stu-id="ec865-295">(The AUMID for the Microsoft Edge Stable channel is **MSEdge**).</span></span>

<span data-ttu-id="ec865-296">複数アプリが割り当てられたアクセスで Microsoft Edge を使用する場合は、Microsoft Edge キオスクを構成するには、[Microsoft Edge ブラウザー ポリシー](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) を使用して、固有の要件を満たすように閲覧エクスペリエンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="ec865-296">When using Microsoft Edge with multi-app assigned access, you can configure Microsoft Edge kiosk to use the[Microsoft Edge browser policies](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) to configure the browsing experience to meet your unique requirements.</span></span>

### <a name="configure-using-windows-settings"></a><span data-ttu-id="ec865-297">Windows の設定を使用して構成する</span><span class="sxs-lookup"><span data-stu-id="ec865-297">Configure using Windows Settings</span></span>

<span data-ttu-id="ec865-298">Windows の設定は、1 つか 2 つのシングル アプリのキオスク デバイスを設定する最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="ec865-298">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="ec865-299">シングル アプリのキオスク コンピューターをセットアップするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ec865-299">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="ec865-300">最新の Windows 10 Insider Preview (バージョン 20215 以降) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ec865-300">Install the latest Windows 10 Insider Preview, version 20215 or higher.</span></span> <span data-ttu-id="ec865-301">「[Windows 10 Insider Preview ビルドの概要](/windows-insider/get-started)」の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="ec865-301">Follow the instructions in [Getting started with Windows 10 Insider Preview Builds](/windows-insider/get-started).</span></span>
2. <span data-ttu-id="ec865-302">最新の機能をテストするには、最新の [Microsoft Edge Beta チャネル](https://www.microsoftedgeinsider.com/download)(バージョン 89 以上) をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="ec865-302">To test the latest features, you can download the latest [Microsoft Edge Beta channel](https://www.microsoftedgeinsider.com/download), version 89 or higher.</span></span>
3. <span data-ttu-id="ec865-303">キオスク コンピューターで、[Windows の設定] を開き、検索フィールドに "キオスク" と入力します。</span><span class="sxs-lookup"><span data-stu-id="ec865-303">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="ec865-304">次のスクリーンショットに表示されている  **[Set up a kiosk (assigned access)]** (キオスク モードを設定する (割り当てられたアクセス)) を選択し、キオスクを作成するダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="ec865-304">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

4. <span data-ttu-id="ec865-306">**[Set up a kiosk]**  (キオスク モードを設定する) ページで、 **[開始する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec865-306">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="キオスク ページ - 開始する":::

5. <span data-ttu-id="ec865-308">名前を入力して新しいキオスク アカウントを作成するか、または入力されているドロップダウン リストから既存のアカウントを選択して、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec865-308">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="キオスク モード - アカウントの作成":::

6. <span data-ttu-id="ec865-310">**[キオスク アプリを選ぶ]**  ページで、**[Microsoft Edge]** を選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec865-310">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ec865-311">これは、Microsoft Edge Dev、Beta、Stable チャネルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ec865-311">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="キオスク モード - アプリを選ぶ":::

7. <span data-ttu-id="ec865-313">Microsoft Edge がキオスク モードで実行しているときの表示方法について、次のいずれかのオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="ec865-313">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="ec865-314">デジタル/対話型サイネージ - 全画面表示モードで特定のサイトを表示し、Microsoft Edge を実行します。</span><span class="sxs-lookup"><span data-stu-id="ec865-314">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="ec865-315">パブリック ブラウザー - Microsoft Edge の限定的な複数タブのバージョンを実行します。</span><span class="sxs-lookup"><span data-stu-id="ec865-315">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="キオスク モードの表示 - 全画面表示デジタル署名":::

8. <span data-ttu-id="ec865-317"> *\*[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec865-317">Select **Next**.</span></span>
9. <span data-ttu-id="ec865-318">キオスクが起動したときに読み込む URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec865-318">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="キオスク モード - URL の入力":::

10. <span data-ttu-id="ec865-320">アイドル時間に、既定値の 5 分をそのまま使用するか、独自の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec865-320">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="キオスク モード - アイドル時間の入力":::

11. <span data-ttu-id="ec865-322"> *\*[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec865-322">Click **Next**.</span></span>
12. <span data-ttu-id="ec865-323"> *\*[設定]**  ウィンドウを閉じて、選択内容を保存して適用します。</span><span class="sxs-lookup"><span data-stu-id="ec865-323">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="キオスク モード - 設定の終了":::

13. <span data-ttu-id="ec865-325">キオスク デバイスからサインオフし、ローカル キオスク アカウントでサインインして、構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="ec865-325">Sign out from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <a name="functional-limitations"></a><span data-ttu-id="ec865-326">機能上の制限事項</span><span class="sxs-lookup"><span data-stu-id="ec865-326">Functional limitations</span></span>

<span data-ttu-id="ec865-327">このキオスク モードのプレビュー版をリリースすることにより、Microsoft は商品の改善と新機能の追加に継続的に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="ec865-327">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="ec865-328">現在、次の機能はサポートされていません。また、オフにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ec865-328">We currently don't support the following features and recommend that you turn off:</span></span>

- [<span data-ttu-id="ec865-329">InPrivateModeAvailability</span><span class="sxs-lookup"><span data-stu-id="ec865-329">InPrivateModeAvailability</span></span>](./microsoft-edge-policies.md#inprivatemodeavailability)
- [<span data-ttu-id="ec865-330">IsolateOrigins</span><span class="sxs-lookup"><span data-stu-id="ec865-330">IsolateOrigins</span></span>](./microsoft-edge-policies.md#isolateorigins)
- [<span data-ttu-id="ec865-331">ManagedFavorites</span><span class="sxs-lookup"><span data-stu-id="ec865-331">ManagedFavorites</span></span>](./microsoft-edge-policies.md#managedfavorites)
- [<span data-ttu-id="ec865-332">EdgeShoppingAssistantEnabled</span><span class="sxs-lookup"><span data-stu-id="ec865-332">EdgeShoppingAssistantEnabled</span></span>](./microsoft-edge-policies.md#edgeshoppingassistantenabled)
- [<span data-ttu-id="ec865-333">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="ec865-333">EdgeCollectionsEnabled</span></span>](./microsoft-edge-policies.md#edgecollectionsenabled)
- [<span data-ttu-id="ec865-334">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="ec865-334">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed)
- [<span data-ttu-id="ec865-335">DefaultPopupsSetting</span><span class="sxs-lookup"><span data-stu-id="ec865-335">DefaultPopupsSetting</span></span>](./microsoft-edge-policies.md#defaultpopupssetting)
- [<span data-ttu-id="ec865-336">StartupBoostEnabled</span><span class="sxs-lookup"><span data-stu-id="ec865-336">StartupBoostEnabled</span></span>](./microsoft-edge-policies.md#startupboostenabled)
- [<span data-ttu-id="ec865-337">InternetExplorerIntegrationLevel</span><span class="sxs-lookup"><span data-stu-id="ec865-337">InternetExplorerIntegrationLevel</span></span>](./microsoft-edge-policies.md#internetexplorerintegrationlevel)
- [<span data-ttu-id="ec865-338">拡張機能</span><span class="sxs-lookup"><span data-stu-id="ec865-338">Extensions</span></span>](./microsoft-edge-policies.md#extensions-policies)
- [<span data-ttu-id="ec865-339">BackgroundModeEnabled</span><span class="sxs-lookup"><span data-stu-id="ec865-339">BackgroundModeEnabled</span></span>](./microsoft-edge-policies.md#backgroundmodeenabled)
- [<span data-ttu-id="ec865-340">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="ec865-340">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed)

## <a name="roadmap"></a><span data-ttu-id="ec865-341">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="ec865-341">Roadmap</span></span>

### <a name="in-early-2021"></a><span data-ttu-id="ec865-342">2021 年初旬</span><span class="sxs-lookup"><span data-stu-id="ec865-342">In early 2021</span></span>

<span data-ttu-id="ec865-343">次のサポートと機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="ec865-343">We'll add the following support and features:</span></span>

- <span data-ttu-id="ec865-344">シングル アプリとして割り当てられたアクセスによる Microsoft Edge キオスク モードの Windows 10 1909 またはそれ以上での一般提供。</span><span class="sxs-lookup"><span data-stu-id="ec865-344">General availability of Microsoft Edge kiosk mode with assigned access single app on Windows 10 1909 and higher.</span></span>
- <span data-ttu-id="ec865-345">Microsoft Edge 従来版とのパリティのための追加機能。</span><span class="sxs-lookup"><span data-stu-id="ec865-345">Additional features for parity with Microsoft Edge Legacy.</span></span>
- <span data-ttu-id="ec865-346">キオスク モード プロファイル UX を使用してデバイスを構成するための Intune との統合。</span><span class="sxs-lookup"><span data-stu-id="ec865-346">Integration with Intune to configure devices using kiosk mode profile UX.</span></span>
- <span data-ttu-id="ec865-347">ブラウザーからの他のアプリケーションの起動を制限します。</span><span class="sxs-lookup"><span data-stu-id="ec865-347">Restrict the launch of other applications from the browser.</span></span>
- <span data-ttu-id="ec865-348">UI 印刷設定のロックダウン。</span><span class="sxs-lookup"><span data-stu-id="ec865-348">UI print settings lockdown.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec865-349">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec865-349">See also</span></span>

- [<span data-ttu-id="ec865-350">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="ec865-350">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="ec865-351">Microsoft Edge の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="ec865-351">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="ec865-352">Windows デスクトップ エディションでのキオスクおよびデジタル サイネージの構成</span><span class="sxs-lookup"><span data-stu-id="ec865-352">Configure kiosks and digital signs on Windows desktop editions</span></span>](/windows/configuration/kiosk-methods)
- [<span data-ttu-id="ec865-353">キオスク モードの移行を計画する</span><span class="sxs-lookup"><span data-stu-id="ec865-353">Plan your kiosk mode transition</span></span>](microsoft-edge-kiosk-mode-transition-plan.md)