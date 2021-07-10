---
title: Microsoft Edge キオスク モードを構成する
ms.author: aguta
author: aguta
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: キオスク モード機能と Microsoft Edge キオスク モードのオプションを構成する方法について説明します。
ms.openlocfilehash: 38d94a5dfac15f810a463e43ad2fe44d51ee66c7
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642193"
---
# <a name="configure-microsoft-edge-kiosk-mode"></a><span data-ttu-id="8d1b1-103">Microsoft Edge キオスク モードを構成する</span><span class="sxs-lookup"><span data-stu-id="8d1b1-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="8d1b1-104">この記事では、パイロットを実行することができる Microsoft Edge キオスク モードのオプションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="8d1b1-105">また、対象としている機能のロードマップも含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-105">There's also a roadmap of features we're targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="8d1b1-106">この記事は Microsoft Edge version 87 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-106">This article applies to Microsoft Edge version 87 or later.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d1b1-107">[「キオスク モード機能の使用」](#use-kiosk-mode-features)で提供されているコマンド ライン引数を使用して、Windows 10 で Microsoft Edgeキオスク モード機能 を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-107">Invoke Microsoft Edge kiosk mode features on Windows 10 using the command line arguments provided in [Use kiosk mode features](#use-kiosk-mode-features).</span></span>

## <a name="overview"></a><span data-ttu-id="8d1b1-108">概要</span><span class="sxs-lookup"><span data-stu-id="8d1b1-108">Overview</span></span>

<span data-ttu-id="8d1b1-109">Microsoft Edge キオスク モードは、ブラウザーの 2 つのロックダウン エクスペリエンスを提供し、組織が顧客に最高のエクスペリエンスを作成し、管理し、提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-109">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="8d1b1-110">次のロックダウン エクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-110">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="8d1b1-111">**デジタル/対話型サイネージ** エクスペリエンスでは、全画面表示モードで特定のサイトを表示します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-111">**Digital/Interactive Signage** experience - Displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="8d1b1-112">**パブリック ブラウジング** エクスペリエンスでは、Microsoft Edge の限定的な複数タブのバージョンを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-112">**Public-Browsing** experience - Runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="8d1b1-113">どちらのエクスペリエンスでも、ユーザー データを保護する Microsoft Edge InPrivate セッションを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-113">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <a name="set-up-microsoft-edge-kiosk-mode"></a><span data-ttu-id="8d1b1-114">Microsoft Edge キオスク モードのセットアップ</span><span class="sxs-lookup"><span data-stu-id="8d1b1-114">Set up Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="8d1b1-115">キオスク モード機能の初期セットが Microsoft Edge Canary チャネルのバージョン 87 でテストに使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-115">An initial set of kiosk mode features is available to test with Microsoft Edge Stable Channel, version 87.</span></span> <span data-ttu-id="8d1b1-116">[Microsoft Edge (Official Stable チャネル)](https://www.microsoft.com/edge) から 最新バージョンをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-116">You can download the latest version from [Microsoft Edge (Official Stable Channel)](https://www.microsoft.com/edge).</span></span>

### <a name="kiosk-mode-supported-features"></a><span data-ttu-id="8d1b1-117">キオスク モードでサポートされる機能</span><span class="sxs-lookup"><span data-stu-id="8d1b1-117">Kiosk mode supported features</span></span>

<span data-ttu-id="8d1b1-118">次の表に、Microsoft Edge と Microsoft Edge レガシのキオスク モードでサポートされる機能を示します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-118">The following table lists the features supported by kiosk mode in Microsoft Edge and Microsoft Edge Legacy.</span></span> <span data-ttu-id="8d1b1-119">次の表を Microsoft Edge への移行のためのガイドとして使用し、Microsoft Edge の両方のバージョンでこれらの機能がどのようにサポートされているかを比較してください。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-119">Use this table as a guide to transitioning to Microsoft Edge by comparing how these features are supported in both versions of Microsoft Edge.</span></span>

|<span data-ttu-id="8d1b1-120">機能</span><span class="sxs-lookup"><span data-stu-id="8d1b1-120">Feature</span></span>|<span data-ttu-id="8d1b1-121">デジタル/対話型サイネージ</span><span class="sxs-lookup"><span data-stu-id="8d1b1-121">Digital\Interactive Signage</span></span>|<span data-ttu-id="8d1b1-122">パブリック ブラウジング</span><span class="sxs-lookup"><span data-stu-id="8d1b1-122">Public browsing</span></span>|<span data-ttu-id="8d1b1-123">Microsoft Edge のバージョン (以上) で利用可能</span><span class="sxs-lookup"><span data-stu-id="8d1b1-123">Available with Microsoft Edge version (and higher)</span></span>|<span data-ttu-id="8d1b1-124">Microsoft Edge レガシで使用可能</span><span class="sxs-lookup"><span data-stu-id="8d1b1-124">Available with Microsoft Edge Legacy</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="8d1b1-125">InPrivate ナビゲーション。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-125">InPrivate Navigation</span></span>|<span data-ttu-id="8d1b1-126">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-126">Y</span></span>|<span data-ttu-id="8d1b1-127">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-127">Y</span></span>|<span data-ttu-id="8d1b1-128">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-128">89</span></span>|<span data-ttu-id="8d1b1-129">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-129">Y</span></span>|
|<span data-ttu-id="8d1b1-130">非アクティブ時のリセット</span><span class="sxs-lookup"><span data-stu-id="8d1b1-130">Reset on inactivity</span></span>|<span data-ttu-id="8d1b1-131">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-131">Y</span></span>|<span data-ttu-id="8d1b1-132">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-132">Y</span></span>|<span data-ttu-id="8d1b1-133">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-133">89</span></span>|<span data-ttu-id="8d1b1-134">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-134">Y</span></span>|
|<span data-ttu-id="8d1b1-135">[読み取り専用アドレス バー](./microsoft-edge-policies.md#kioskaddressbareditingenabled) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-135">[Read only address bar](./microsoft-edge-policies.md#kioskaddressbareditingenabled) (policy)</span></span> |<span data-ttu-id="8d1b1-136">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-136">N</span></span>|<span data-ttu-id="8d1b1-137">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-137">Y</span></span> |<span data-ttu-id="8d1b1-138">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-138">89</span></span>|<span data-ttu-id="8d1b1-139">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-139">N</span></span>|
|<span data-ttu-id="8d1b1-140">[終了時にダウンロードを削除する](./microsoft-edge-policies.md#kioskdeletedownloadsonexit) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-140">[Delete downloads on exit](./microsoft-edge-policies.md#kioskdeletedownloadsonexit) (policy)</span></span>  | <span data-ttu-id="8d1b1-141">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-141">Y</span></span>|<span data-ttu-id="8d1b1-142">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-142">Y</span></span> |<span data-ttu-id="8d1b1-143">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-143">89</span></span>|<span data-ttu-id="8d1b1-144">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-144">N</span></span>|
|<span data-ttu-id="8d1b1-145">F11 がブロックされています (全画面に入る/終了する)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-145">F11 blocked (enter/exit full-screen)</span></span> | <span data-ttu-id="8d1b1-146">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-146">Y</span></span> | <span data-ttu-id="8d1b1-147">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-147">Y</span></span> |<span data-ttu-id="8d1b1-148">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-148">89</span></span>|<span data-ttu-id="8d1b1-149">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-149">Y</span></span>|
|<span data-ttu-id="8d1b1-150">F12 がブロックされています (開発者ツールの起動)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-150">F12 blocked (launch Developer Tools)</span></span> | <span data-ttu-id="8d1b1-151">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-151">Y</span></span> | <span data-ttu-id="8d1b1-152">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-152">Y</span></span> |<span data-ttu-id="8d1b1-153">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-153">89</span></span>|<span data-ttu-id="8d1b1-154">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-154">Y</span></span>|
| <span data-ttu-id="8d1b1-155">複数タブのサポート</span><span class="sxs-lookup"><span data-stu-id="8d1b1-155">Multi tab support</span></span> | <span data-ttu-id="8d1b1-156">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-156">N</span></span>| <span data-ttu-id="8d1b1-157">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-157">Y</span></span>|<span data-ttu-id="8d1b1-158">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-158">89</span></span>|<span data-ttu-id="8d1b1-159">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-159">Y</span></span>|
|<span data-ttu-id="8d1b1-160">[URL のサポートを許可する](./microsoft-edge-policies.md#urlallowlist) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-160">[Allow URL support](./microsoft-edge-policies.md#urlallowlist) (policy)</span></span>|<span data-ttu-id="8d1b1-161">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-161">Y</span></span>|<span data-ttu-id="8d1b1-162">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-162">Y</span></span>|<span data-ttu-id="8d1b1-163">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-163">89</span></span>|<span data-ttu-id="8d1b1-164">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-164">N</span></span>|
|<span data-ttu-id="8d1b1-165">[URL のサポートをブロックする](./microsoft-edge-policies.md#urlblocklist) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-165">[Block URL support](./microsoft-edge-policies.md#urlblocklist) (policy)</span></span>|<span data-ttu-id="8d1b1-166">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-166">Y</span></span>|<span data-ttu-id="8d1b1-167">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-167">Y</span></span>|<span data-ttu-id="8d1b1-168">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-168">89</span></span>|<span data-ttu-id="8d1b1-169">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-169">N</span></span>|
|<span data-ttu-id="8d1b1-170">[[ホーム] ボタンを表示する](./microsoft-edge-policies.md#showhomebutton) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-170">[Show home button](./microsoft-edge-policies.md#showhomebutton) (policy)</span></span>|<span data-ttu-id="8d1b1-171">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-171">N</span></span>|<span data-ttu-id="8d1b1-172">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-172">Y</span></span>|<span data-ttu-id="8d1b1-173">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-173">89</span></span>|<span data-ttu-id="8d1b1-174">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-174">Y</span></span>|
|<span data-ttu-id="8d1b1-175">[お気に入りを管理する](./microsoft-edge-policies.md#managedfavorites) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-175">[Manage favorites](./microsoft-edge-policies.md#managedfavorites) (policy)</span></span>|<span data-ttu-id="8d1b1-176">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-176">N</span></span>|<span data-ttu-id="8d1b1-177">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-177">Y</span></span>|<span data-ttu-id="8d1b1-178">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-178">89</span></span>|<span data-ttu-id="8d1b1-179">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-179">Y</span></span>|
|<span data-ttu-id="8d1b1-180">[プリンターを有効化](./microsoft-edge-policies.md#printingenabled) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-180">[Enable printer](./microsoft-edge-policies.md#printingenabled) (policy)</span></span>|<span data-ttu-id="8d1b1-181">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-181">Y</span></span>|<span data-ttu-id="8d1b1-182">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-182">Y</span></span>|<span data-ttu-id="8d1b1-183">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-183">89</span></span>|<span data-ttu-id="8d1b1-184">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-184">Y</span></span>|
|<span data-ttu-id="8d1b1-185">[新しいタブ ページの URLを構成する](./microsoft-edge-policies.md#newtabpagelocation) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-185">[Configure the new tab page URL](./microsoft-edge-policies.md#newtabpagelocation) (policy)</span></span>|<span data-ttu-id="8d1b1-186">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-186">N</span></span>|<span data-ttu-id="8d1b1-187">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-187">Y</span></span>|<span data-ttu-id="8d1b1-188">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-188">89</span></span>|<span data-ttu-id="8d1b1-189">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-189">Y</span></span>|
|<span data-ttu-id="8d1b1-190">[セッションの終了] ボタン \*</span><span class="sxs-lookup"><span data-stu-id="8d1b1-190">End session button \*</span></span> | <span data-ttu-id="8d1b1-191">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-191">N</span></span>| <span data-ttu-id="8d1b1-192">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-192">Y</span></span>|<span data-ttu-id="8d1b1-193">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-193">89</span></span>|<span data-ttu-id="8d1b1-194">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-194">Y</span></span>|
|<span data-ttu-id="8d1b1-195">すべての内部 Microsoft Edge URL はブロックされます (*edge://downloads* および *edge://print* を除く)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-195">All internal Microsoft Edge URLs are blocked, except for *edge://downloads* and *edge://print*</span></span> |<span data-ttu-id="8d1b1-196">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-196">N</span></span>|<span data-ttu-id="8d1b1-197">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-197">Y</span></span>|<span data-ttu-id="8d1b1-198">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-198">89</span></span>|<span data-ttu-id="8d1b1-199">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-199">Y</span></span>|
| <span data-ttu-id="8d1b1-200">Ctrl + N がブロックされています (新しいウィンドウを開く) \*</span><span class="sxs-lookup"><span data-stu-id="8d1b1-200">CTRL+N blocked (open a new window) \*</span></span> | <span data-ttu-id="8d1b1-201">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-201">Y</span></span> | <span data-ttu-id="8d1b1-202">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-202">Y</span></span> |<span data-ttu-id="8d1b1-203">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-203">89</span></span>|<span data-ttu-id="8d1b1-204">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-204">Y</span></span>|
| <span data-ttu-id="8d1b1-205">Ctrl + T がブロックされています (新しいタブを開く)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-205">CTRL+T blocked (open new tab)</span></span> |<span data-ttu-id="8d1b1-206">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-206">Y</span></span> | <span data-ttu-id="8d1b1-207">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-207">N</span></span> |<span data-ttu-id="8d1b1-208">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-208">89</span></span>|<span data-ttu-id="8d1b1-209">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-209">Y</span></span>|
|<span data-ttu-id="8d1b1-210">設定と詳細 (...) では、必要なオプションだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-210">Settings and more (...) will display only the required options</span></span>  |<span data-ttu-id="8d1b1-211">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-211">Y</span></span> |<span data-ttu-id="8d1b1-212">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-212">Y</span></span> |<span data-ttu-id="8d1b1-213">89</span><span class="sxs-lookup"><span data-stu-id="8d1b1-213">89</span></span>|<span data-ttu-id="8d1b1-214">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-214">Y</span></span>|
|<span data-ttu-id="8d1b1-215">ブラウザーからの他のアプリケーションの起動を制限する</span><span class="sxs-lookup"><span data-stu-id="8d1b1-215">Restrict the launch of other applications from the browser</span></span>|<span data-ttu-id="8d1b1-216">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-216">Y</span></span>|<span data-ttu-id="8d1b1-217">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-217">Y</span></span>|<span data-ttu-id="8d1b1-218">90</span><span class="sxs-lookup"><span data-stu-id="8d1b1-218">90</span></span>|<span data-ttu-id="8d1b1-219">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-219">Y</span></span>|
|<span data-ttu-id="8d1b1-220">UI 印刷設定のロックダウン</span><span class="sxs-lookup"><span data-stu-id="8d1b1-220">UI print settings lockdown</span></span>|<span data-ttu-id="8d1b1-221">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-221">Y</span></span>|<span data-ttu-id="8d1b1-222">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-222">Y</span></span>|<span data-ttu-id="8d1b1-223">90</span><span class="sxs-lookup"><span data-stu-id="8d1b1-223">90</span></span>|<span data-ttu-id="8d1b1-224">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-224">Y</span></span>|
|<span data-ttu-id="8d1b1-225">[新しいタブ ページをホーム ページとして設定する](./microsoft-edge-policies.md#homepageisnewtabpage) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-225">[Set the new tab page as the home page](./microsoft-edge-policies.md#homepageisnewtabpage) (policy)</span></span>|<span data-ttu-id="8d1b1-226">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-226">N</span></span>|<span data-ttu-id="8d1b1-227">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-227">Y</span></span>|<span data-ttu-id="8d1b1-228">90</span><span class="sxs-lookup"><span data-stu-id="8d1b1-228">90</span></span>|<span data-ttu-id="8d1b1-229">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-229">Y</span></span>|

> [!NOTE]
> <span data-ttu-id="8d1b1-230">"\*" に続く機能は、割り当てられたアクセス単一アプリのシナリオでのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-230">Features followed by "\*" are only enabled in an assigned access single app scenario.</span></span>

## <a name="use-kiosk-mode-features"></a><span data-ttu-id="8d1b1-231">キオスク モード機能を使用する</span><span class="sxs-lookup"><span data-stu-id="8d1b1-231">Use kiosk mode features</span></span>

<span data-ttu-id="8d1b1-232">Microsoft Edge キオスク モード機能は、デジタル/対話型サイネージおよびパブリック ブラウジング用の次の Windows 10 コマンドライン オプションで起動できます。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-232">Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options for Digital/Interactive signage and Public browsing.</span></span>

### <a name="kiosk-mode-digitalinteractive-signage"></a><span data-ttu-id="8d1b1-233">キオスク モード デジタル/対話型サイネージ</span><span class="sxs-lookup"><span data-stu-id="8d1b1-233">Kiosk mode Digital/Interactive signage</span></span>
 
```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen
```

### <a name="kiosk-mode-public-browsing"></a><span data-ttu-id="8d1b1-234">キオスク モードのパブリック ブラウジング</span><span class="sxs-lookup"><span data-stu-id="8d1b1-234">Kiosk mode Public browsing</span></span>

```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing
```

### <a name="additional-command-line-options"></a><span data-ttu-id="8d1b1-235">その他のコマンド ライン オプション</span><span class="sxs-lookup"><span data-stu-id="8d1b1-235">Additional command line options</span></span>

- <span data-ttu-id="8d1b1-236">**--no-first-run**: 最初の Microsoft Edge 実行エクスペリエンスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-236">**--no-first-run**: Disable the first Microsoft Edge run experience.</span></span>

   ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --no-first-run
  ```

  ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --no-first-run
  ```

- <span data-ttu-id="8d1b1-237">**--kiosk-idle-timeout-minutes=**: Microsoft Edge キオスク モードがユーザーのセッションをリセットする前に、最後のユーザー アクティビティからの時間 (分) を変更します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-237">**--kiosk-idle-timeout-minutes=**: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="8d1b1-238">次の例の "value" を分数に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-238">Replace "value" in the next example with the number of minutes.</span></span>

   ```
   --kiosk-idle-timeout-minutes=value
   ``` 
   <span data-ttu-id="8d1b1-239">次の "値" がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-239">The following "values" are supported:</span></span>

     - <span data-ttu-id="8d1b1-240">既定値 (分)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-240">Default values (in minutes)</span></span>
       - <span data-ttu-id="8d1b1-241">全画面 - 0 (オフ)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-241">Full screen - 0 (turned off)</span></span>
       - <span data-ttu-id="8d1b1-242">パブリック ブラウジング - 5 分</span><span class="sxs-lookup"><span data-stu-id="8d1b1-242">Public browsing - 5 minutes</span></span>
    - <span data-ttu-id="8d1b1-243">指定可能な値</span><span class="sxs-lookup"><span data-stu-id="8d1b1-243">Allowed values</span></span>
      - <span data-ttu-id="8d1b1-244">0 - タイマーをオフにします</span><span class="sxs-lookup"><span data-stu-id="8d1b1-244">0 - turns off the timer</span></span>
      - <span data-ttu-id="8d1b1-245">1 - 1440 分 (アイドル タイマー時のリセット)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-245">1-1440 minutes for reset on idle timer</span></span>


    ```
    msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --kiosk-idle-timeout-minutes=1
   ```

   ```
   msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --kiosk-idle-timeout-minutes=1
   ```

## <a name="support-policies-for-kiosk-mode"></a><span data-ttu-id="8d1b1-246">キオスク モードでサポートされているポリシー</span><span class="sxs-lookup"><span data-stu-id="8d1b1-246">Support policies for kiosk mode</span></span>

<span data-ttu-id="8d1b1-247">以下の表にある Microsoft Edge ポリシーのいずれかを使用して、構成する Microsoft Edge キオスク モードの種類に応じてキオスク エクスペリエンスを強化します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-247">Use any of the Microsoft Edge policies listed in the following table to enhance the kiosk experience for the Microsoft Edge kiosk mode type you configure.</span></span> <span data-ttu-id="8d1b1-248">これらのポリシーの詳細については、「[Microsoft Edge - ブラウザー ポリシー リファレンス](./microsoft-edge-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-248">To learn more about these policies, see [Microsoft Edge – Browser policy reference](./microsoft-edge-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8d1b1-249">ポリシーの構成は、次の表に示すポリシーに限定されませんが、キオスク モード機能に悪影響が及びないことを確認するために、追加のポリシーをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-249">Policy configuration isn't limited to the policies listed in the following table, however additional policies should be tested to ensure that kiosk mode functionality isn't negatively affected.</span></span>

|<span data-ttu-id="8d1b1-250">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="8d1b1-250">Group policy</span></span>|<span data-ttu-id="8d1b1-251">デジタル/対話型サイネージ</span><span class="sxs-lookup"><span data-stu-id="8d1b1-251">Digital\Interactive signage</span></span>|<span data-ttu-id="8d1b1-252">パブリック ブラウズの単一アプリ</span><span class="sxs-lookup"><span data-stu-id="8d1b1-252">Public browsing single-app</span></span>|
|--|--|--|
|[<span data-ttu-id="8d1b1-253">印刷</span><span class="sxs-lookup"><span data-stu-id="8d1b1-253">Printing</span></span>](./microsoft-edge-policies.md#printing-policies) | <span data-ttu-id="8d1b1-254">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-254">Y</span></span>|<span data-ttu-id="8d1b1-255">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-255">Y</span></span> |
|[<span data-ttu-id="8d1b1-256">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="8d1b1-256">HomePageLocation</span></span>](./microsoft-edge-policies.md#homepagelocation) |<span data-ttu-id="8d1b1-257">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-257">N</span></span> | <span data-ttu-id="8d1b1-258">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-258">Y</span></span>|
|[<span data-ttu-id="8d1b1-259">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="8d1b1-259">ShowHomeButton</span></span>](./microsoft-edge-policies.md#showhomebutton) |<span data-ttu-id="8d1b1-260">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-260">N</span></span> | <span data-ttu-id="8d1b1-261">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-261">Y</span></span>|
|[<span data-ttu-id="8d1b1-262">NewTabPageLocation</span><span class="sxs-lookup"><span data-stu-id="8d1b1-262">NewTabPageLocation</span></span>](./microsoft-edge-policies.md#newtabpagelocation) |<span data-ttu-id="8d1b1-263">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-263">N</span></span> |<span data-ttu-id="8d1b1-264">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-264">Y</span></span> |
|[<span data-ttu-id="8d1b1-265">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="8d1b1-265">FavoritesBarEnabled</span></span>](./microsoft-edge-policies.md#favoritesbarenabled) |<span data-ttu-id="8d1b1-266">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-266">N</span></span> |<span data-ttu-id="8d1b1-267">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-267">Y</span></span> |
|[<span data-ttu-id="8d1b1-268">URLAllowlist</span><span class="sxs-lookup"><span data-stu-id="8d1b1-268">URLAllowlist</span></span>](./microsoft-edge-policies.md#urlallowlist) |<span data-ttu-id="8d1b1-269">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-269">Y</span></span> |<span data-ttu-id="8d1b1-270">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-270">Y</span></span> |
|[<span data-ttu-id="8d1b1-271">URLBlocklist</span><span class="sxs-lookup"><span data-stu-id="8d1b1-271">URLBlocklist</span></span>](./microsoft-edge-policies.md#urlblocklist) |<span data-ttu-id="8d1b1-272">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-272">Y</span></span> | <span data-ttu-id="8d1b1-273">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-273">Y</span></span>|
|[<span data-ttu-id="8d1b1-274">ManagedSearchEngines</span><span class="sxs-lookup"><span data-stu-id="8d1b1-274">ManagedSearchEngines</span></span>](./microsoft-edge-policies.md#managedsearchengines) |<span data-ttu-id="8d1b1-275">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-275">N</span></span> | <span data-ttu-id="8d1b1-276">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-276">Y</span></span>|
|[<span data-ttu-id="8d1b1-277">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="8d1b1-277">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed) |<span data-ttu-id="8d1b1-278">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-278">N</span></span> | <span data-ttu-id="8d1b1-279">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-279">Y</span></span>|
|[<span data-ttu-id="8d1b1-280">VerticalTabsAllowed</span><span class="sxs-lookup"><span data-stu-id="8d1b1-280">VerticalTabsAllowed</span></span>](./microsoft-edge-policies.md#verticaltabsallowed) | <span data-ttu-id="8d1b1-281">N</span><span class="sxs-lookup"><span data-stu-id="8d1b1-281">N</span></span>|<span data-ttu-id="8d1b1-282">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-282">Y</span></span> |
|[<span data-ttu-id="8d1b1-283">SmartScreen の設定</span><span class="sxs-lookup"><span data-stu-id="8d1b1-283">SmartScreen settings</span></span>](./microsoft-edge-policies.md#smartscreen-settings-policies) |<span data-ttu-id="8d1b1-284">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-284">Y</span></span> |<span data-ttu-id="8d1b1-285">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-285">Y</span></span> |
|[<span data-ttu-id="8d1b1-286">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="8d1b1-286">EdgeCollectionsEnabled</span></span>](./microsoft-edge-policies.md#edgecollectionsenabled)|<span data-ttu-id="8d1b1-287">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-287">Y</span></span>|<span data-ttu-id="8d1b1-288">Y</span><span class="sxs-lookup"><span data-stu-id="8d1b1-288">Y</span></span>|

## <a name="microsoft-edge-with-assigned-access"></a><span data-ttu-id="8d1b1-289">割り当てられたアクセスによる Microsoft Edge の使用</span><span class="sxs-lookup"><span data-stu-id="8d1b1-289">Microsoft Edge with assigned access</span></span>

### <a name="single-app-kiosk"></a><span data-ttu-id="8d1b1-290">シングル アプリ キオスク</span><span class="sxs-lookup"><span data-stu-id="8d1b1-290">Single app kiosk</span></span>

<span data-ttu-id="8d1b1-291">Microsoft Edge バージョン 90 キオスク モードは、機能の広範なリストを提供します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-291">Microsoft Edge version 90 kiosk mode offers an extensive list of features.</span></span> <span data-ttu-id="8d1b1-292">キオスク モードでサポートされている機能のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-292">See the section of Kiosk mode supported features.</span></span>
<span data-ttu-id="8d1b1-293">次の Windows 更新プログラムを使用すると、割り当てられたアクセス シングル アプリを介して Microsoft Edge を構成できます。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-293">With the following Windows updates you can configure Microsoft Edge via assigned access single app.</span></span>

|<span data-ttu-id="8d1b1-294">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="8d1b1-294">Operating System</span></span>|<span data-ttu-id="8d1b1-295">バージョン</span><span class="sxs-lookup"><span data-stu-id="8d1b1-295">Version</span></span>|<span data-ttu-id="8d1b1-296">更新プログラム</span><span class="sxs-lookup"><span data-stu-id="8d1b1-296">Updates</span></span>|
|--|--|--|
|<span data-ttu-id="8d1b1-297">Windows 10</span><span class="sxs-lookup"><span data-stu-id="8d1b1-297">Windows 10</span></span> | <span data-ttu-id="8d1b1-298">2004 以降</span><span class="sxs-lookup"><span data-stu-id="8d1b1-298">2004 or later</span></span>|[<span data-ttu-id="8d1b1-299">KB4601382 以降</span><span class="sxs-lookup"><span data-stu-id="8d1b1-299">KB4601382 or later</span></span>](https://support.microsoft.com/topic/february-24-2021-kb4601382-os-builds-19041-844-and-19042-844-preview-1a7ed2b4-017d-2644-a1e8-dd6bf14cba76) |
|<span data-ttu-id="8d1b1-300">Windows 10</span><span class="sxs-lookup"><span data-stu-id="8d1b1-300">Windows 10</span></span>| <span data-ttu-id="8d1b1-301">1909</span><span class="sxs-lookup"><span data-stu-id="8d1b1-301">1909</span></span>| [<span data-ttu-id="8d1b1-302">KB4601380 以降</span><span class="sxs-lookup"><span data-stu-id="8d1b1-302">KB4601380 or later</span></span>](https://support.microsoft.com/topic/february-16-2021-kb4601380-os-build-18363-1411-preview-2e3c38e1-a947-1033-8006-a30f3806da18)|

<span data-ttu-id="8d1b1-303">[Windows の設定](/deployedge/microsoft-edge-configure-kiosk-mode#configure-using-windows-settings)と Intune を介して、Microsoft Edge キオスク モードの割り当てられたアクセス シングル アプリを管理できます。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-303">You can manage Microsoft Edge kiosk mode assigned access single app via [Windows Settings](/deployedge/microsoft-edge-configure-kiosk-mode#configure-using-windows-settings) and Intune.</span></span>

### <a name="multi-app-kiosk"></a><span data-ttu-id="8d1b1-304">複数アプリ キオスク</span><span class="sxs-lookup"><span data-stu-id="8d1b1-304">Multi-app kiosk</span></span>

<span data-ttu-id="8d1b1-305">Microsoft Edge は、Windows 10 で[複数アプリの割り当てられたアクセス](/windows/configuration/lock-down-windows-10-to-specific-apps) によって実行できます。これは Microsoft Edge レガシでの "通常の閲覧" タイプのキオスク モードに相当します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-305">Microsoft Edge can be run with [multi-app assigned access](/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing" kiosk mode type.</span></span> <span data-ttu-id="8d1b1-306">複数アプリの割り当てられたアクセスで Microsoft Edge を構成するには、[複数アプリ キオスクの設定](/windows/configuration/lock-down-windows-10-to-specific-apps)方法の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-306">To configure Microsoft Edge with multi-app assigned access, follow the instructions on how to [Set up a multi-app kiosk](/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="8d1b1-307">(Microsoft Edge Stable チャネルの AUMID は **MSEdge** です。)</span><span class="sxs-lookup"><span data-stu-id="8d1b1-307">(The AUMID for the Microsoft Edge Stable channel is **MSEdge**).</span></span>

### <a name="configure-using-windows-settings"></a><span data-ttu-id="8d1b1-308">Windows の設定を使用して構成する</span><span class="sxs-lookup"><span data-stu-id="8d1b1-308">Configure using Windows Settings</span></span>

<span data-ttu-id="8d1b1-309">Windows の設定は、1 つか 2 つのシングル アプリのキオスク デバイスを設定する最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-309">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="8d1b1-310">シングル アプリのキオスク コンピューターをセットアップするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-310">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="8d1b1-311">次の表に示すオペレーティング システムの最小システム更新プログラム。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-311">The minimum system updates for the operating systems listed in the next table.</span></span>

|<span data-ttu-id="8d1b1-312">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="8d1b1-312">Operating System</span></span>|<span data-ttu-id="8d1b1-313">バージョン</span><span class="sxs-lookup"><span data-stu-id="8d1b1-313">Version</span></span>|<span data-ttu-id="8d1b1-314">更新プログラム</span><span class="sxs-lookup"><span data-stu-id="8d1b1-314">Updates</span></span>|
|--|--|--|
|<span data-ttu-id="8d1b1-315">Windows 10</span><span class="sxs-lookup"><span data-stu-id="8d1b1-315">Windows 10</span></span> | <span data-ttu-id="8d1b1-316">2004 以降</span><span class="sxs-lookup"><span data-stu-id="8d1b1-316">2004 or later</span></span>|[<span data-ttu-id="8d1b1-317">KB4601382 以降</span><span class="sxs-lookup"><span data-stu-id="8d1b1-317">KB4601382 or later</span></span>](https://support.microsoft.com/topic/february-24-2021-kb4601382-os-builds-19041-844-and-19042-844-preview-1a7ed2b4-017d-2644-a1e8-dd6bf14cba76) |
|<span data-ttu-id="8d1b1-318">Windows 10</span><span class="sxs-lookup"><span data-stu-id="8d1b1-318">Windows 10</span></span>| <span data-ttu-id="8d1b1-319">1909</span><span class="sxs-lookup"><span data-stu-id="8d1b1-319">1909</span></span>| [<span data-ttu-id="8d1b1-320">KB4601380 以降</span><span class="sxs-lookup"><span data-stu-id="8d1b1-320">KB4601380 or later</span></span>](https://support.microsoft.com/topic/february-16-2021-kb4601380-os-build-18363-1411-preview-2e3c38e1-a947-1033-8006-a30f3806da18)|

2. <span data-ttu-id="8d1b1-321">最新の機能をテストするには、最新の [Microsoft Edge Stable チャネル](https://www.microsoft.com/edge/business/download) (バージョン 89 以上) をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-321">To test the latest features, you can download the latest [Microsoft Edge Stable channel](https://www.microsoft.com/edge/business/download), version 89 or higher.</span></span>

3. <span data-ttu-id="8d1b1-322">キオスク コンピューターで、[Windows の設定] を開き、検索フィールドに「キオスク」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-322">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="8d1b1-323">次のスクリーンショットに表示されている  **[Set up a kiosk (assigned access)]** (キオスク モードを設定する (割り当てられたアクセス)) を選択し、キオスクを作成するダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-323">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

4. <span data-ttu-id="8d1b1-325">**[Set up a kiosk]**  (キオスク モードを設定する) ページで、 **[開始する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-325">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="キオスク ページ - 開始する":::

5. <span data-ttu-id="8d1b1-327">名前を入力して新しいキオスク アカウントを作成するか、または入力されているドロップダウン リストから既存のアカウントを選択して、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-327">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="キオスク モード - アカウントの作成":::

6. <span data-ttu-id="8d1b1-329">**[キオスク アプリを選ぶ]**  ページで、**[Microsoft Edge]** を選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-329">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8d1b1-330">これは、Microsoft Edge Dev、Beta、Stable チャネルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-330">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

     :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5c-choose-a-kiosk-app.png" alt-text="キオスク モードの表示 - 全画面表示デジタル署名":::

7. <span data-ttu-id="8d1b1-332">Microsoft Edge がキオスク モードで実行しているときの表示方法について、次のいずれかのオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-332">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="8d1b1-333">デジタル/対話型サイネージ - 全画面表示モードで特定のサイトを表示し、Microsoft Edge を実行します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-333">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="8d1b1-334">パブリック ブラウザー - Microsoft Edge の限定的な複数タブのバージョンを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-334">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="キオスクの使い方 - 全画面表示デジタル署名":::

8. <span data-ttu-id="8d1b1-336"> *\*[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-336">Select **Next**.</span></span>
9. <span data-ttu-id="8d1b1-337">キオスクが起動したときに読み込む URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-337">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="キオスク モード - URL の入力":::

10. <span data-ttu-id="8d1b1-339">アイドル時間に、既定値の 5 分をそのまま使用するか、独自の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-339">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="キオスク モード - アイドル時間の入力":::

11. <span data-ttu-id="8d1b1-341"> *\*[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-341">Click **Next**.</span></span>
12. <span data-ttu-id="8d1b1-342"> *\*[設定]**  ウィンドウを閉じて、選択内容を保存して適用します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-342">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="キオスク モード - 設定の終了":::

13. <span data-ttu-id="8d1b1-344">キオスク デバイスからサインオフし、ローカル キオスク アカウントでサインインして、構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-344">Sign out from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <a name="functional-limitations"></a><span data-ttu-id="8d1b1-345">機能上の制限事項</span><span class="sxs-lookup"><span data-stu-id="8d1b1-345">Functional limitations</span></span>

<span data-ttu-id="8d1b1-346">このキオスク モードのプレビュー版をリリースすることにより、Microsoft は商品の改善と新機能の追加に継続的に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-346">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="8d1b1-347">現在、次の機能はサポートされていません。また、オフにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d1b1-347">We currently don't support the following features and recommend that you turn off:</span></span>

- [<span data-ttu-id="8d1b1-348">InPrivateModeAvailability</span><span class="sxs-lookup"><span data-stu-id="8d1b1-348">InPrivateModeAvailability</span></span>](./microsoft-edge-policies.md#inprivatemodeavailability)
- [<span data-ttu-id="8d1b1-349">IsolateOrigins</span><span class="sxs-lookup"><span data-stu-id="8d1b1-349">IsolateOrigins</span></span>](./microsoft-edge-policies.md#isolateorigins)
- [<span data-ttu-id="8d1b1-350">ManagedFavorites</span><span class="sxs-lookup"><span data-stu-id="8d1b1-350">ManagedFavorites</span></span>](./microsoft-edge-policies.md#managedfavorites)
- [<span data-ttu-id="8d1b1-351">EdgeShoppingAssistantEnabled</span><span class="sxs-lookup"><span data-stu-id="8d1b1-351">EdgeShoppingAssistantEnabled</span></span>](./microsoft-edge-policies.md#edgeshoppingassistantenabled)
- [<span data-ttu-id="8d1b1-352">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="8d1b1-352">EdgeCollectionsEnabled</span></span>](./microsoft-edge-policies.md#edgecollectionsenabled)
- [<span data-ttu-id="8d1b1-353">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="8d1b1-353">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed)
- [<span data-ttu-id="8d1b1-354">DefaultPopupsSetting</span><span class="sxs-lookup"><span data-stu-id="8d1b1-354">DefaultPopupsSetting</span></span>](./microsoft-edge-policies.md#defaultpopupssetting)
- [<span data-ttu-id="8d1b1-355">StartupBoostEnabled</span><span class="sxs-lookup"><span data-stu-id="8d1b1-355">StartupBoostEnabled</span></span>](./microsoft-edge-policies.md#startupboostenabled)
- [<span data-ttu-id="8d1b1-356">InternetExplorerIntegrationLevel</span><span class="sxs-lookup"><span data-stu-id="8d1b1-356">InternetExplorerIntegrationLevel</span></span>](./microsoft-edge-policies.md#internetexplorerintegrationlevel)
- [<span data-ttu-id="8d1b1-357">拡張機能</span><span class="sxs-lookup"><span data-stu-id="8d1b1-357">Extensions</span></span>](./microsoft-edge-policies.md#extensions-policies)
- [<span data-ttu-id="8d1b1-358">BackgroundModeEnabled</span><span class="sxs-lookup"><span data-stu-id="8d1b1-358">BackgroundModeEnabled</span></span>](./microsoft-edge-policies.md#backgroundmodeenabled)
- [<span data-ttu-id="8d1b1-359">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="8d1b1-359">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed)

## <a name="see-also"></a><span data-ttu-id="8d1b1-360">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d1b1-360">See also</span></span>

- [<span data-ttu-id="8d1b1-361">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="8d1b1-361">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="8d1b1-362">Microsoft Edge の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="8d1b1-362">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="8d1b1-363">Windows デスクトップ エディションでのキオスクおよびデジタル サイネージの構成</span><span class="sxs-lookup"><span data-stu-id="8d1b1-363">Configure kiosks and digital signs on Windows desktop editions</span></span>](/windows/configuration/kiosk-methods)
- [<span data-ttu-id="8d1b1-364">キオスク モードの移行を計画する</span><span class="sxs-lookup"><span data-stu-id="8d1b1-364">Plan your kiosk mode transition</span></span>](microsoft-edge-kiosk-mode-transition-plan.md)
