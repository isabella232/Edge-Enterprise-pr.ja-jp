---
title: Microsoft Edge キオスク モードを構成する
ms.author: aguta
author: aguta
manager: srugh
ms.date: 01/21/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge キオスク モードを構成する
ms.openlocfilehash: be353a0e13e9234de40296a2e8dcc31b1b800f52
ms.sourcegitcommit: 8a88fd38bdb5e132e89bf17dd2b5fb72f5d1b4b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297473"
---
# <span data-ttu-id="2ffcb-103">Microsoft Edge キオスク モードを構成する</span><span class="sxs-lookup"><span data-stu-id="2ffcb-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="2ffcb-104">この記事では、パイロットを実行することができる Microsoft Edge キオスク モードのオプションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="2ffcb-105">また、対象としている機能のロードマップも含まれます。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-105">There's also a roadmap of features we're targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="2ffcb-106">この記事は Microsoft Edge version 87 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-106">This article applies to Microsoft Edge version 87 or later.</span></span>

## <span data-ttu-id="2ffcb-107">概要</span><span class="sxs-lookup"><span data-stu-id="2ffcb-107">Overview</span></span>

<span data-ttu-id="2ffcb-108">Microsoft Edge キオスク モードは、ブラウザーの 2 つのロックダウン エクスペリエンスを提供し、組織が顧客に最高のエクスペリエンスを作成し、管理し、提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-108">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="2ffcb-109">次のロックダウン エクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-109">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="2ffcb-110">**デジタル/対話型サイネージ** エクスペリエンスでは、全画面表示モードで特定のサイトを表示します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-110">**Digital/Interactive Signage** experience - Displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="2ffcb-111">**パブリック ブラウジング** エクスペリエンスでは、Microsoft Edge の限定的な複数タブのバージョンを実行します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-111">**Public-Browsing** experience - Runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="2ffcb-112">どちらのエクスペリエンスでも、ユーザー データを保護する Microsoft Edge InPrivate セッションを実行します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-112">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <span data-ttu-id="2ffcb-113">Microsoft Edge キオスク モードのセットアップ</span><span class="sxs-lookup"><span data-stu-id="2ffcb-113">Set up Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="2ffcb-114">キオスク モード機能の初期セットが Microsoft Edge Canary チャネルのバージョン 87 でテストに使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-114">An initial set of kiosk mode features is available to test with Microsoft Edge Stable Channel, version 87.</span></span> <span data-ttu-id="2ffcb-115">[Microsoft Edge (Official Stable チャネル)](https://www.microsoft.com/edge) から 最新バージョンをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-115">You can download the latest version from [Microsoft Edge (Official Stable Channel)](https://www.microsoft.com/edge).</span></span>

### <span data-ttu-id="2ffcb-116">キオスク モードでサポートされる機能</span><span class="sxs-lookup"><span data-stu-id="2ffcb-116">Kiosk mode supported features</span></span>

<span data-ttu-id="2ffcb-117">次の表に、キオスク モードでサポートされている機能を示します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-117">The following table lists the features supported by kiosk mode.</span></span>

|<span data-ttu-id="2ffcb-118">機能</span><span class="sxs-lookup"><span data-stu-id="2ffcb-118">Feature</span></span>|<span data-ttu-id="2ffcb-119">デジタル/対話型サイネージ</span><span class="sxs-lookup"><span data-stu-id="2ffcb-119">Digital\Interactive Signage</span></span>|<span data-ttu-id="2ffcb-120">パブリック ブラウジング</span><span class="sxs-lookup"><span data-stu-id="2ffcb-120">Public browsing</span></span>|<span data-ttu-id="2ffcb-121">Microsoft Edge のバージョン (以上) で利用可能</span><span class="sxs-lookup"><span data-stu-id="2ffcb-121">Available with Microsoft Edge version (and higher)</span></span>|
|-|-|-|-|
|<span data-ttu-id="2ffcb-122">InPrivate ナビゲーション。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-122">InPrivate Navigation</span></span>|<span data-ttu-id="2ffcb-123">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-123">Y</span></span>|<span data-ttu-id="2ffcb-124">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-124">Y</span></span>|<span data-ttu-id="2ffcb-125">87</span><span class="sxs-lookup"><span data-stu-id="2ffcb-125">87</span></span>|
|<span data-ttu-id="2ffcb-126">非アクティブ時のリセット</span><span class="sxs-lookup"><span data-stu-id="2ffcb-126">Reset on inactivity</span></span>|<span data-ttu-id="2ffcb-127">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-127">Y</span></span>|<span data-ttu-id="2ffcb-128">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-128">Y</span></span>|<span data-ttu-id="2ffcb-129">87</span><span class="sxs-lookup"><span data-stu-id="2ffcb-129">87</span></span>|
|<span data-ttu-id="2ffcb-130">[読み取り専用アドレス バー](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="2ffcb-130">[Read only address bar](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) (policy)</span></span> |<span data-ttu-id="2ffcb-131">N</span><span class="sxs-lookup"><span data-stu-id="2ffcb-131">N</span></span>|<span data-ttu-id="2ffcb-132">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-132">Y</span></span> |<span data-ttu-id="2ffcb-133">87</span><span class="sxs-lookup"><span data-stu-id="2ffcb-133">87</span></span>|
|<span data-ttu-id="2ffcb-134">[終了時にダウンロードを削除する](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) (ポリシー)</span><span class="sxs-lookup"><span data-stu-id="2ffcb-134">[Delete downloads on exit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) (policy)</span></span>  | <span data-ttu-id="2ffcb-135">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-135">Y</span></span>|<span data-ttu-id="2ffcb-136">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-136">Y</span></span> |<span data-ttu-id="2ffcb-137">87</span><span class="sxs-lookup"><span data-stu-id="2ffcb-137">87</span></span>|
|<span data-ttu-id="2ffcb-138">F11 がブロックされています (全画面に入る/終了する)</span><span class="sxs-lookup"><span data-stu-id="2ffcb-138">F11 blocked (enter/exit full-screen)</span></span> | <span data-ttu-id="2ffcb-139">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-139">Y</span></span> | <span data-ttu-id="2ffcb-140">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-140">Y</span></span> | <span data-ttu-id="2ffcb-141">87</span><span class="sxs-lookup"><span data-stu-id="2ffcb-141">87</span></span> |
|<span data-ttu-id="2ffcb-142">F12 がブロックされています (開発者ツールの起動)</span><span class="sxs-lookup"><span data-stu-id="2ffcb-142">F12 blocked (launch Developer Tools)</span></span> | <span data-ttu-id="2ffcb-143">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-143">Y</span></span> | <span data-ttu-id="2ffcb-144">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-144">Y</span></span> | <span data-ttu-id="2ffcb-145">87</span><span class="sxs-lookup"><span data-stu-id="2ffcb-145">87</span></span> |
| <span data-ttu-id="2ffcb-146">複数タブのサポート</span><span class="sxs-lookup"><span data-stu-id="2ffcb-146">Multi tab support</span></span> | <span data-ttu-id="2ffcb-147">N</span><span class="sxs-lookup"><span data-stu-id="2ffcb-147">N</span></span>| <span data-ttu-id="2ffcb-148">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-148">Y</span></span>| <span data-ttu-id="2ffcb-149">87</span><span class="sxs-lookup"><span data-stu-id="2ffcb-149">87</span></span>|
|<span data-ttu-id="2ffcb-150">[セッションの終了] ボタン</span><span class="sxs-lookup"><span data-stu-id="2ffcb-150">End session button</span></span> | <span data-ttu-id="2ffcb-151">N</span><span class="sxs-lookup"><span data-stu-id="2ffcb-151">N</span></span>| <span data-ttu-id="2ffcb-152">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-152">Y</span></span>| <span data-ttu-id="2ffcb-153">88</span><span class="sxs-lookup"><span data-stu-id="2ffcb-153">88</span></span>|
|<span data-ttu-id="2ffcb-154">すべての内部 Microsoft Edge URL はブロックされます (ただし、*edge://downloads* および *edge://print*以外)</span><span class="sxs-lookup"><span data-stu-id="2ffcb-154">All internal Microsoft Edge URLs are blocked, except for *edge://downloads* and *edge://print*</span></span> |<span data-ttu-id="2ffcb-155">N</span><span class="sxs-lookup"><span data-stu-id="2ffcb-155">N</span></span>|<span data-ttu-id="2ffcb-156">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-156">Y</span></span>|<span data-ttu-id="2ffcb-157">88</span><span class="sxs-lookup"><span data-stu-id="2ffcb-157">88</span></span>|
| <span data-ttu-id="2ffcb-158">Ctrl + N がブロックされています (新しいウィンドウを開く)</span><span class="sxs-lookup"><span data-stu-id="2ffcb-158">CTRL+N blocked (open a new window)</span></span> | <span data-ttu-id="2ffcb-159">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-159">Y</span></span> | <span data-ttu-id="2ffcb-160">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-160">Y</span></span> | <span data-ttu-id="2ffcb-161">89</span><span class="sxs-lookup"><span data-stu-id="2ffcb-161">89</span></span> |
| <span data-ttu-id="2ffcb-162">Ctrl + T ブロックされています (新しいタブを開く)</span><span class="sxs-lookup"><span data-stu-id="2ffcb-162">CTRL+T blocked (open new tab)</span></span> | <span data-ttu-id="2ffcb-163">N</span><span class="sxs-lookup"><span data-stu-id="2ffcb-163">N</span></span> | <span data-ttu-id="2ffcb-164">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-164">Y</span></span> | <span data-ttu-id="2ffcb-165">89</span><span class="sxs-lookup"><span data-stu-id="2ffcb-165">89</span></span> |
|<span data-ttu-id="2ffcb-166">設定と詳細 (...) では、必要なオプションだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-166">Settings and more (...) will display only the required options</span></span>  |<span data-ttu-id="2ffcb-167">N</span><span class="sxs-lookup"><span data-stu-id="2ffcb-167">N</span></span> |<span data-ttu-id="2ffcb-168">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-168">Y</span></span> |<span data-ttu-id="2ffcb-169">89</span><span class="sxs-lookup"><span data-stu-id="2ffcb-169">89</span></span> |

> [!NOTE]
> <span data-ttu-id="2ffcb-170">キオスク モードの進化に伴い、より多くの機能を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-170">As kiosk mode evolves, more features will be available.</span></span>

## <span data-ttu-id="2ffcb-171">キオスク モードの機能を使用する</span><span class="sxs-lookup"><span data-stu-id="2ffcb-171">Use kiosk mode features</span></span>

<span data-ttu-id="2ffcb-172">Microsoft Edge キオスク モードの機能は、Windows 10 の次のコマンド ライン オプションで起動できます。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-172">Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options:</span></span>

- <span data-ttu-id="2ffcb-173">キオスク モードのデジタル/対話型サイネージ:</span><span class="sxs-lookup"><span data-stu-id="2ffcb-173">Kiosk mode Digital/Interactive signage:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen`
- <span data-ttu-id="2ffcb-174">キオスク モードのパブリック ブラウジング:</span><span class="sxs-lookup"><span data-stu-id="2ffcb-174">Kiosk mode public browsing:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing`

### <span data-ttu-id="2ffcb-175">その他のコマンド ライン オプション</span><span class="sxs-lookup"><span data-stu-id="2ffcb-175">Additional command line options</span></span>

- `--no-first-run` <span data-ttu-id="2ffcb-176">: Microsoft Edge の最初の実行エクスペリエンスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-176">: Disable the first Microsoft Edge run experience.</span></span>
- `--kiosk-idle-timeout-minutes` <span data-ttu-id="2ffcb-177">: Microsoft Edge キオスク モードでユーザーのセッションがリセットされる前に、最後のユーザー アクティビティから時間 (分単位) を変更します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-177">: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="2ffcb-178">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-178">The following values are supported:</span></span>

  - <span data-ttu-id="2ffcb-179">既定値</span><span class="sxs-lookup"><span data-stu-id="2ffcb-179">Default values</span></span>
    - <span data-ttu-id="2ffcb-180">全画面表示 - オフ</span><span class="sxs-lookup"><span data-stu-id="2ffcb-180">Full screen - turned off</span></span>
    - <span data-ttu-id="2ffcb-181">パブリック ブラウジング - 5 分</span><span class="sxs-lookup"><span data-stu-id="2ffcb-181">Public browsing - 5 minutes</span></span>
  - <span data-ttu-id="2ffcb-182">指定可能な値</span><span class="sxs-lookup"><span data-stu-id="2ffcb-182">Allowed values</span></span>
    - <span data-ttu-id="2ffcb-183">0 - タイマーをオフにします</span><span class="sxs-lookup"><span data-stu-id="2ffcb-183">0 - turns off the timer</span></span>
    - <span data-ttu-id="2ffcb-184">1 - 1440 分 (アイドル タイマー時のリセット)</span><span class="sxs-lookup"><span data-stu-id="2ffcb-184">1-1440 minutes for reset on idle timer</span></span>

## <span data-ttu-id="2ffcb-185">キオスク モードでサポートされているポリシー</span><span class="sxs-lookup"><span data-stu-id="2ffcb-185">Support policies for kiosk mode</span></span>

<span data-ttu-id="2ffcb-186">以下の表にある Microsoft Edge ポリシーのいずれかを使用して、構成する Microsoft Edge キオスク モードの種類に応じてキオスク エクスペリエンスを強化します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-186">Use any of the Microsoft Edge policies listed in the following table to enhance the kiosk experience for the Microsoft Edge kiosk mode type you configure.</span></span> <span data-ttu-id="2ffcb-187">これらのポリシーの詳細については、「[Microsoft Edge - ブラウザー ポリシー リファレンス](https://docs.microsoft.com/deployedge/microsoft-edge-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-187">To learn more about these policies, see [Microsoft Edge – Browser policy reference](https://docs.microsoft.com/deployedge/microsoft-edge-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="2ffcb-188">ポリシーの構成は、次の表に示すポリシーに限定されませんが、キオスク モード機能に悪影響が及びないことを確認するために、追加のポリシーをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-188">Policy configuration isn't limited to the policies listed in the following table, however additional policies should be tested to ensure that kiosk mode functionality isn't negatively affected.</span></span>

|<span data-ttu-id="2ffcb-189">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="2ffcb-189">Group policy</span></span>|<span data-ttu-id="2ffcb-190">デジタル/対話型サイネージ</span><span class="sxs-lookup"><span data-stu-id="2ffcb-190">Digital\Interactive signage</span></span>|<span data-ttu-id="2ffcb-191">パブリック ブラウズの単一アプリ</span><span class="sxs-lookup"><span data-stu-id="2ffcb-191">Public browsing single-app</span></span>|
|--|--|--|
|[<span data-ttu-id="2ffcb-192">印刷</span><span class="sxs-lookup"><span data-stu-id="2ffcb-192">Printing</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printing-policies) | <span data-ttu-id="2ffcb-193">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-193">Y</span></span>|<span data-ttu-id="2ffcb-194">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-194">Y</span></span> |
|[<span data-ttu-id="2ffcb-195">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="2ffcb-195">HomePageLocation</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepagelocation) |<span data-ttu-id="2ffcb-196">N</span><span class="sxs-lookup"><span data-stu-id="2ffcb-196">N</span></span> | <span data-ttu-id="2ffcb-197">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-197">Y</span></span>|
|[<span data-ttu-id="2ffcb-198">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="2ffcb-198">ShowHomeButton</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#showhomebutton) |<span data-ttu-id="2ffcb-199">N</span><span class="sxs-lookup"><span data-stu-id="2ffcb-199">N</span></span> | <span data-ttu-id="2ffcb-200">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-200">Y</span></span>|
|[<span data-ttu-id="2ffcb-201">NewTabPageLocation</span><span class="sxs-lookup"><span data-stu-id="2ffcb-201">NewTabPageLocation</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation) |<span data-ttu-id="2ffcb-202">N</span><span class="sxs-lookup"><span data-stu-id="2ffcb-202">N</span></span> |<span data-ttu-id="2ffcb-203">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-203">Y</span></span> |
|[<span data-ttu-id="2ffcb-204">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="2ffcb-204">FavoritesBarEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#favoritesbarenabled) |<span data-ttu-id="2ffcb-205">N</span><span class="sxs-lookup"><span data-stu-id="2ffcb-205">N</span></span> |<span data-ttu-id="2ffcb-206">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-206">Y</span></span> |
|[<span data-ttu-id="2ffcb-207">URLAllowlist</span><span class="sxs-lookup"><span data-stu-id="2ffcb-207">URLAllowlist</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist) |<span data-ttu-id="2ffcb-208">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-208">Y</span></span> |<span data-ttu-id="2ffcb-209">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-209">Y</span></span> |
|[<span data-ttu-id="2ffcb-210">URLBlocklist</span><span class="sxs-lookup"><span data-stu-id="2ffcb-210">URLBlocklist</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist) |<span data-ttu-id="2ffcb-211">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-211">Y</span></span> | <span data-ttu-id="2ffcb-212">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-212">Y</span></span>|
|[<span data-ttu-id="2ffcb-213">ManagedSearchEngines</span><span class="sxs-lookup"><span data-stu-id="2ffcb-213">ManagedSearchEngines</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#managedsearchengines) |<span data-ttu-id="2ffcb-214">N</span><span class="sxs-lookup"><span data-stu-id="2ffcb-214">N</span></span> | <span data-ttu-id="2ffcb-215">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-215">Y</span></span>|
|[<span data-ttu-id="2ffcb-216">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="2ffcb-216">UserFeedbackAllowed</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed) |<span data-ttu-id="2ffcb-217">N</span><span class="sxs-lookup"><span data-stu-id="2ffcb-217">N</span></span> | <span data-ttu-id="2ffcb-218">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-218">Y</span></span>|
|[<span data-ttu-id="2ffcb-219">VerticalTabsAllowed</span><span class="sxs-lookup"><span data-stu-id="2ffcb-219">VerticalTabsAllowed</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#verticaltabsallowed) | <span data-ttu-id="2ffcb-220">N</span><span class="sxs-lookup"><span data-stu-id="2ffcb-220">N</span></span>|<span data-ttu-id="2ffcb-221">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-221">Y</span></span> |
|[<span data-ttu-id="2ffcb-222">SmartScreen の設定</span><span class="sxs-lookup"><span data-stu-id="2ffcb-222">SmartScreen settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#smartscreen-settings-policies) |<span data-ttu-id="2ffcb-223">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-223">Y</span></span> |<span data-ttu-id="2ffcb-224">Y</span><span class="sxs-lookup"><span data-stu-id="2ffcb-224">Y</span></span> |

## <span data-ttu-id="2ffcb-225">割り当てられたアクセスによる Microsoft Edge の使用</span><span class="sxs-lookup"><span data-stu-id="2ffcb-225">Microsoft Edge with assigned access</span></span>

### <span data-ttu-id="2ffcb-226">シングル アプリ キオスク</span><span class="sxs-lookup"><span data-stu-id="2ffcb-226">Single app kiosk</span></span>

<span data-ttu-id="2ffcb-227">Microsoft Edge は現在、次のロックダウン エクスペリエンス、つまりデジタル/対話型サイネージ、およびパブリックブラウジングを備えた、単一アプリに割り当てられたアクセス用の同じ Microsoft Edge レガシ キオスク モード タイプのサブセットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-227">Microsoft Edge currently supports a subset of the same Microsoft Edge Legacy kiosk mode types for single-app assigned access with the following lockdown experiences: Digital/Interactive signage, and Public-browsing.</span></span>  

<span data-ttu-id="2ffcb-228">現在、割り当てられたアクセスによるキオスク モードは、最新の  [Windows 10 Insider Preview ビルド](https://insider.windows.com/) (バージョン 20215 以降) と  [Microsoft Edge Dev チャネル](https://www.microsoftedgeinsider.com/download) (バージョン 87.0.644.4 以降) でテストに使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-228">Kiosk mode with assigned access is currently available for testing with the latest [Windows 10 Insider Preview Build](https://insider.windows.com/), version 20215 or higher, and with the [Microsoft Edge Dev Channel](https://www.microsoftedgeinsider.com/download), version 87.0.644.4 or higher.</span></span>

**<span data-ttu-id="2ffcb-229">Windows Insiders Preview を入手するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="2ffcb-229">How do I get the Windows Insiders preview?</span></span>**

<span data-ttu-id="2ffcb-230">PC に Windows 10 Insider Preview ビルドをインストールするには、「 [Windows 10 Insider Preview ビルドの概要](https://docs.microsoft.com/windows-insider/get-started)」の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-230">To install a Windows 10 Insider Preview Build on a PC, follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>

### <span data-ttu-id="2ffcb-231">複数アプリ キオスク</span><span class="sxs-lookup"><span data-stu-id="2ffcb-231">Multi-app kiosk</span></span>

<span data-ttu-id="2ffcb-232">Microsoft Edge は、Windows 10 で[複数アプリの割り当てられたアクセス](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) によって実行できます。これは Microsoft Edge レガシでの "通常の閲覧" タイプのキオスク モードに相当します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-232">Microsoft Edge can be run with [multi-app assigned access](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing" kiosk mode type.</span></span> <span data-ttu-id="2ffcb-233">複数アプリの割り当てられたアクセスで Microsoft Edge を構成するには、[複数アプリ キオスクの設定](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)方法の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-233">To configure Microsoft Edge with multi-app assigned access, follow the instructions on how to [Set up a multi-app kiosk](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="2ffcb-234">(Microsoft Edge Stable チャネルの AUMID は **MSEdge** です)。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-234">(The AUMID for the Microsoft Edge Stable channel is **MSEdge**).</span></span>

<span data-ttu-id="2ffcb-235">複数アプリが割り当てられたアクセスで Microsoft Edge を使用する場合は、Microsoft Edge キオスクを構成するには、[Microsoft Edge ブラウザー ポリシー](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) を使用して、固有の要件を満たすように閲覧エクスペリエンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-235">When using Microsoft Edge with multi-app assigned access, you can configure Microsoft Edge kiosk to use the[Microsoft Edge browser policies](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) to configure the browsing experience to meet your unique requirements.</span></span>

### <span data-ttu-id="2ffcb-236">Windows の設定を使用して構成する</span><span class="sxs-lookup"><span data-stu-id="2ffcb-236">Configure using Windows Settings</span></span>

<span data-ttu-id="2ffcb-237">Windows の設定は、1 つか 2 つのシングル アプリのキオスク デバイスを設定する最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-237">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="2ffcb-238">シングル アプリのキオスク コンピューターをセットアップするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-238">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="2ffcb-239">最新の Windows 10 Insider Preview (バージョン 20215 以降) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-239">Install the latest Windows 10 Insider Preview, version 20215 or higher.</span></span> <span data-ttu-id="2ffcb-240">「[Windows 10 Insider Preview ビルドの概要](https://docs.microsoft.com/windows-insider/get-started)」の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-240">Follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>
2. <span data-ttu-id="2ffcb-241">[Microsoft Edge Stableチャネル](https://www.microsoft.com/edge)、バージョン 87 以上の最新バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-241">Install the latest version of [Microsoft Edge Stable channel](https://www.microsoft.com/edge), version 87 or higher.</span></span>  <span data-ttu-id="2ffcb-242">最新の機能をテストするには、最新の [Microsoft Edge 開発チャネル](https://www.microsoftedgeinsider.com/download) (バージョン 89 以上) をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-242">To test the latest features, you can download the latest [Microsoft Edge Dev channel](https://www.microsoftedgeinsider.com/download), version 89 or higher.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="2ffcb-243">デバイス レベルのインストールが必要であるため、Canary 以外のチャネルのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-243">Because a device level installation is required, only a non-Canary channel is supported.</span></span>

3. <span data-ttu-id="2ffcb-244">キオスク コンピューターで、[Windows の設定] を開き、検索フィールドに "キオスク" と入力します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-244">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="2ffcb-245">次のスクリーンショットに表示されている  **[Set up a kiosk (assigned access)]** (キオスク モードを設定する (割り当てられたアクセス)) を選択し、キオスクを作成するダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-245">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

4. <span data-ttu-id="2ffcb-247">**[Set up a kiosk]**  (キオスク モードを設定する) ページで、 **[開始する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-247">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="キオスク ページ - 開始する":::

5. <span data-ttu-id="2ffcb-249">名前を入力して新しいキオスク アカウントを作成するか、または入力されているドロップダウン リストから既存のアカウントを選択して、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-249">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="キオスク モード - アカウントの作成":::

6. <span data-ttu-id="2ffcb-251">**[キオスク アプリを選ぶ]**  ページで、**[Microsoft Edge]** を選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-251">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2ffcb-252">これは、Microsoft Edge Dev、Beta、Stable チャネルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-252">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="キオスク モード - アプリを選ぶ":::

7. <span data-ttu-id="2ffcb-254">Microsoft Edge がキオスク モードで実行しているときの表示方法について、次のいずれかのオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-254">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="2ffcb-255">デジタル/対話型サイネージ - 全画面表示モードで特定のサイトを表示し、Microsoft Edge を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-255">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="2ffcb-256">パブリック ブラウザー - Microsoft Edge の限定的な複数タブのバージョンを実行します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-256">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="キオスク モードの表示 - 全画面表示デジタル署名":::

8. <span data-ttu-id="2ffcb-258"> *\*[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-258">Select **Next**.</span></span>
9. <span data-ttu-id="2ffcb-259">キオスクが起動したときに読み込む URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-259">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="キオスク モード - URL の入力":::

10. <span data-ttu-id="2ffcb-261">アイドル時間に、既定値の 5 分をそのまま使用するか、独自の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-261">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="キオスク モード - アイドル時間の入力":::

11. <span data-ttu-id="2ffcb-263"> *\*[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-263">Click **Next**.</span></span>
12. <span data-ttu-id="2ffcb-264"> *\*[設定]**  ウィンドウを閉じて、選択内容を保存して適用します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-264">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="キオスク モード - 設定の終了":::

13. <span data-ttu-id="2ffcb-266">キオスク デバイスからサインオフし、ローカル キオスク アカウントでサインインして、構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-266">Sign out from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <span data-ttu-id="2ffcb-267">機能上の制限事項</span><span class="sxs-lookup"><span data-stu-id="2ffcb-267">Functional limitations</span></span>

<span data-ttu-id="2ffcb-268">このキオスク モードのプレビュー版をリリースすることにより、Microsoft は商品の改善と新機能の追加に継続的に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-268">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="2ffcb-269">次の機能をオフにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-269">We recommend that you turn off:</span></span>

- [<span data-ttu-id="2ffcb-270">StartupBoostEnabled</span><span class="sxs-lookup"><span data-stu-id="2ffcb-270">StartupBoostEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startupboostenabled)
- [<span data-ttu-id="2ffcb-271">InternetExplorerIntegrationLevel</span><span class="sxs-lookup"><span data-stu-id="2ffcb-271">InternetExplorerIntegrationLevel</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationlevel)
- [<span data-ttu-id="2ffcb-272">拡張機能</span><span class="sxs-lookup"><span data-stu-id="2ffcb-272">Extensions</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions-policies)
- [<span data-ttu-id="2ffcb-273">BackgroundModeEnabled</span><span class="sxs-lookup"><span data-stu-id="2ffcb-273">BackgroundModeEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)

## <span data-ttu-id="2ffcb-274">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="2ffcb-274">Roadmap</span></span>

### <span data-ttu-id="2ffcb-275">2021 年初旬</span><span class="sxs-lookup"><span data-stu-id="2ffcb-275">In early 2021</span></span>

<span data-ttu-id="2ffcb-276">次のサポートと機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-276">We'll add the following support and features:</span></span>

- <span data-ttu-id="2ffcb-277">シングル アプリとして割り当てられたアクセスによる Microsoft Edge キオスク モードの Windows 10 1909 またはそれ以上での一般提供。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-277">General availability of Microsoft Edge kiosk mode with assigned access single app on Windows 10 1909 and higher.</span></span>
- <span data-ttu-id="2ffcb-278">Microsoft Edge 従来版とのパリティのための追加機能。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-278">Additional features for parity with Microsoft Edge Legacy.</span></span>
- <span data-ttu-id="2ffcb-279">キオスク モード プロファイル UX を使用してデバイスを構成するための Intune との統合。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-279">Integration with Intune to configure devices using kiosk mode profile UX.</span></span>
- <span data-ttu-id="2ffcb-280">追加のキーボード ショートカットはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-280">Additional keyboard shortcuts will be blocked.</span></span>
- <span data-ttu-id="2ffcb-281">ブラウザーからの他のアプリケーションの起動を制限します。</span><span class="sxs-lookup"><span data-stu-id="2ffcb-281">Restrict the launch of other applications from the browser.</span></span>

## <span data-ttu-id="2ffcb-282">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ffcb-282">See also</span></span>

- [<span data-ttu-id="2ffcb-283">Windows デスクトップ エディションでのキオスクおよびデジタル サイネージの構成</span><span class="sxs-lookup"><span data-stu-id="2ffcb-283">Configure kiosks and digital signs on Windows desktop editions</span></span>](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [<span data-ttu-id="2ffcb-284">Microsoft Edge レガシ キオスク モードの展開</span><span class="sxs-lookup"><span data-stu-id="2ffcb-284">Deploy Microsoft Edge Legacy kiosk mode</span></span>](https://aka.ms/edgekioskmode)
- [<span data-ttu-id="2ffcb-285">Microsoft Edge の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="2ffcb-285">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="2ffcb-286">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="2ffcb-286">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
