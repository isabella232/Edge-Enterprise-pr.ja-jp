---
title: Microsoft Edge キオスク モードを構成する
ms.author: aguta
author: aguta
manager: srugh
ms.date: 10/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge キオスク モードを構成する
ms.openlocfilehash: 799b3dd4b7fc96f0b8e5cb718bca98fd4f38ec15
ms.sourcegitcommit: 78905f66f4a6590a57c8f2bf808af92106b62996
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2020
ms.locfileid: "11094864"
---
# <span data-ttu-id="66060-103">Microsoft Edge キオスク モードを構成する</span><span class="sxs-lookup"><span data-stu-id="66060-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="66060-104">この記事では、パイロットを実行することができる Microsoft Edge キオスク モードのオプションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="66060-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="66060-105">また、予定されている機能のロードマップも含まれます。</span><span class="sxs-lookup"><span data-stu-id="66060-105">There's also a roadmap of features we are targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="66060-106">この記事は Microsoft Edge version 87 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="66060-106">This article applies to Microsoft Edge version 87 or later.</span></span>

## <span data-ttu-id="66060-107">概要</span><span class="sxs-lookup"><span data-stu-id="66060-107">Overview</span></span>

<span data-ttu-id="66060-108">Microsoft Edge キオスク モードは、ブラウザーの 2 つのロックダウン エクスペリエンスを提供し、組織が顧客に最高のエクスペリエンスを作成し、管理し、提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="66060-108">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="66060-109">次のロックダウン エクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="66060-109">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="66060-110">デジタル/対話型サイネージ エクスペリエンスでは、全画面表示モードで特定のサイトを表示します。</span><span class="sxs-lookup"><span data-stu-id="66060-110">The Digital/Interactive signage experience displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="66060-111">パブリック ブラウジング エクスペリエンスでは、Microsoft Edge の限定的な複数タブのバージョンを実行します。</span><span class="sxs-lookup"><span data-stu-id="66060-111">The public-browsing experience runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="66060-112">どちらのエクスペリエンスでも、ユーザー データを保護する Microsoft Edge InPrivate セッションを実行します。</span><span class="sxs-lookup"><span data-stu-id="66060-112">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <span data-ttu-id="66060-113">Microsoft Edge キオスク モードのセットアップ</span><span class="sxs-lookup"><span data-stu-id="66060-113">Set up Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="66060-114">キオスク モード機能の初期セットが Microsoft Edge Canary チャネルのバージョン 87 でテストに使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="66060-114">An initial set of kiosk mode features are now available to test with Microsoft Edge Canary Channel, version 87.</span></span> <span data-ttu-id="66060-115">Microsoft Edge Canary は、[Microsoft Edge Insider Channels](https://www.microsoftedgeinsider.com/download) ページからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="66060-115">You can download Microsoft Edge Canary from the [Microsoft Edge Insider Channels](https://www.microsoftedgeinsider.com/download) page.</span></span>

### <span data-ttu-id="66060-116">キオスク モードの機能</span><span class="sxs-lookup"><span data-stu-id="66060-116">Kiosk mode features</span></span>

<span data-ttu-id="66060-117">次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="66060-117">The following features are available:</span></span>

- <span data-ttu-id="66060-118">InPrivate ナビゲーションは、セッションの終了時にブラウザー データとダウンロードを削除することにより、ユーザー データを保護します。</span><span class="sxs-lookup"><span data-stu-id="66060-118">InPrivate navigation protects user data by deleting browser data and downloads when the session ends.</span></span>
- <span data-ttu-id="66060-119">終了時のダウンロード削除を構成するためのポリシー。</span><span class="sxs-lookup"><span data-stu-id="66060-119">A policy to configure Delete downloads on exit.</span></span>
- <span data-ttu-id="66060-120">非アクティブ状態が一定期間続いた後に、ユーザー セッションをリセットするオプション。</span><span class="sxs-lookup"><span data-stu-id="66060-120">The option to reset a user session after a certain period of inactivity.</span></span>
- <span data-ttu-id="66060-121">ロックダウン機能の初期セット。</span><span class="sxs-lookup"><span data-stu-id="66060-121">An initial set of lockdown functionality.</span></span> <span data-ttu-id="66060-122">次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="66060-122">The following functions are available:</span></span>

  - <span data-ttu-id="66060-123">マウスのコンテキスト メニュー</span><span class="sxs-lookup"><span data-stu-id="66060-123">Mouse context menu</span></span>
  - <span data-ttu-id="66060-124">F12 開発者ツール</span><span class="sxs-lookup"><span data-stu-id="66060-124">F12 Developer Tools</span></span>
  - <span data-ttu-id="66060-125">F11 全画面表示の終了 (全画面表示モードのとき)</span><span class="sxs-lookup"><span data-stu-id="66060-125">F11 Exit full screen (while in full screen mode)</span></span>
  - <span data-ttu-id="66060-126">*Edge://* ページの初期セットのブロック</span><span class="sxs-lookup"><span data-stu-id="66060-126">Blocking of the initial set of *Edge://* pages</span></span>

> [!NOTE]
> <span data-ttu-id="66060-127">キオスク モードの進化に伴い、より多くの機能を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="66060-127">As kiosk mode evolves, more features will be available.</span></span>

## <span data-ttu-id="66060-128">キオスク モードの機能を使用する</span><span class="sxs-lookup"><span data-stu-id="66060-128">Use kiosk mode features</span></span>

<span data-ttu-id="66060-129">Microsoft Edge キオスク モードの機能は、Windows 10 の次のコマンド ライン オプションで起動できます。</span><span class="sxs-lookup"><span data-stu-id="66060-129">You can invoke Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options:</span></span>

- <span data-ttu-id="66060-130">キオスク モードのデジタル/対話型サイネージ:</span><span class="sxs-lookup"><span data-stu-id="66060-130">Kiosk mode Digital/Interactive signage:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen`
- <span data-ttu-id="66060-131">キオスク モードのパブリック ブラウジング:</span><span class="sxs-lookup"><span data-stu-id="66060-131">Kiosk mode public browsing:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing`

### <span data-ttu-id="66060-132">その他のコマンド ライン オプション</span><span class="sxs-lookup"><span data-stu-id="66060-132">Additional command line options</span></span>

- `--no-first-run` <span data-ttu-id="66060-133">: Microsoft Edge の最初の実行エクスペリエンスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="66060-133">: Disable the first Microsoft Edge run experience.</span></span>
- `--kiosk-idle-timeout-minutes` <span data-ttu-id="66060-134">: Microsoft Edge キオスク モードでユーザーのセッションがリセットされる前に、最後のユーザー アクティビティから時間 (分単位) を変更します。</span><span class="sxs-lookup"><span data-stu-id="66060-134">: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="66060-135">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="66060-135">The following values are supported:</span></span>

  - <span data-ttu-id="66060-136">既定値</span><span class="sxs-lookup"><span data-stu-id="66060-136">Default values</span></span>
    - <span data-ttu-id="66060-137">全画面表示 - オフ</span><span class="sxs-lookup"><span data-stu-id="66060-137">Full screen - turned off</span></span>
    - <span data-ttu-id="66060-138">パブリック ブラウジング - 5 分</span><span class="sxs-lookup"><span data-stu-id="66060-138">Public browsing - 5 minutes</span></span>
  - <span data-ttu-id="66060-139">指定可能な値</span><span class="sxs-lookup"><span data-stu-id="66060-139">Allowed values</span></span>
    - <span data-ttu-id="66060-140">0 - タイマーをオフにします</span><span class="sxs-lookup"><span data-stu-id="66060-140">0 - turns off the timer</span></span>
    - <span data-ttu-id="66060-141">1 - 1440 分 (アイドル タイマー時のリセット)</span><span class="sxs-lookup"><span data-stu-id="66060-141">1-1440 minutes for reset on idle timer</span></span>

## <span data-ttu-id="66060-142">割り当てられたアクセスによる Microsoft Edge の使用</span><span class="sxs-lookup"><span data-stu-id="66060-142">Microsoft Edge with assigned access</span></span>

### <span data-ttu-id="66060-143">シングル アプリ キオスク</span><span class="sxs-lookup"><span data-stu-id="66060-143">Single app kiosk</span></span>

<span data-ttu-id="66060-144">Microsoft Edge は現在、次のロックダウン エクスペリエンス、デジタル/対話型サイネージ、およびパブリックブラウジングを備えた、単一アプリに割り当てられたアクセス用の同じ Microsoft Edge レガシ キオスク モード タイプのサブセットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="66060-144">Microsoft Edge currently supports a subset of the same Microsoft Edge Legacy kiosk mode types for single-app assigned access with the following lockdown experiences, Digital/Interactive signage and Public-browsing.</span></span>  

<span data-ttu-id="66060-145">現在、割り当てられたアクセスによるキオスク モードは、最新の  [Windows 10 Insider Preview ビルド](https://insider.windows.com/) (バージョン 20215 以降) と  [Microsoft Edge Dev チャネル](https://www.microsoftedgeinsider.com/download) (バージョン 87.0.644.4 以降) でテストに使用できます。</span><span class="sxs-lookup"><span data-stu-id="66060-145">Kiosk mode with assigned access is currently available for testing with the latest [Windows 10 Insider Preview Build](https://insider.windows.com/), version 20215 or higher, and with the [Microsoft Edge Dev Channel](https://www.microsoftedgeinsider.com/download), version 87.0.644.4 or higher.</span></span>

**<span data-ttu-id="66060-146">Windows Insiders Preview を入手するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="66060-146">How do I get the Windows Insiders preview?</span></span>**

<span data-ttu-id="66060-147">PC に Windows 10 Insider Preview ビルドをインストールするには、「 [Windows 10 Insider Preview ビルドの概要](https://docs.microsoft.com/windows-insider/get-started)」の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="66060-147">To install a Windows 10 Insider Preview Build on a PC, follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>

### <span data-ttu-id="66060-148">複数アプリ キオスク</span><span class="sxs-lookup"><span data-stu-id="66060-148">Multi-app kiosk</span></span>

<span data-ttu-id="66060-149">Microsoft Edge は、Windows 10 で[複数アプリの割り当てられたアクセス](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) によって実行できます。これは Microsoft Edge レガシでの "通常の閲覧" タイプのキオスク モードに相当します。</span><span class="sxs-lookup"><span data-stu-id="66060-149">Microsoft Edge can be run with [multi-app assigned access](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing" kiosk mode type.</span></span> <span data-ttu-id="66060-150">複数アプリの割り当てられたアクセスで Microsoft Edge を構成するには、[複数アプリ キオスクの設定](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)方法の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="66060-150">To configure Microsoft Edge with multi-app assigned access follow the instructions on how to [Set up a multi-app kiosk](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="66060-151">(Microsoft Edge Stable チャネルの AUMID は **MSEdge** です)。</span><span class="sxs-lookup"><span data-stu-id="66060-151">(The AUMID for the Microsoft Edge Stable channel is **MSEdge**).</span></span>

<span data-ttu-id="66060-152">Microsoft Edge キオスク モードを構成する複数アプリが割り当てられたアクセスで Microsoft Edge を使用する場合は、[Microsoft Edge ブラウザー ポリシー](https://review.docs.microsoft.com/en-us/DeployEdge/microsoft-edge-policies) を使用して、固有の要件を満たすように閲覧エクスペリエンスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="66060-152">Configure Microsoft Edge kiosk mode When using Microsoft Edge with multi-app assigned access you can use the [Microsoft Edge browser policies](https://review.docs.microsoft.com/en-us/DeployEdge/microsoft-edge-policies) to configure the browsing experience to meet your unique requirements.</span></span>

### <span data-ttu-id="66060-153">Windows の設定を使用して構成する</span><span class="sxs-lookup"><span data-stu-id="66060-153">Configure using Windows Settings</span></span>

<span data-ttu-id="66060-154">Windows の設定は、1 つか 2 つのシングル アプリのキオスク デバイスを設定する最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="66060-154">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="66060-155">シングル アプリのキオスク コンピューターをセットアップするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="66060-155">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="66060-156">最新の Windows 10 Insider Preview (バージョン 20215 以降) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="66060-156">Install the latest Windows 10 Insider Preview, version 20215 or higher.</span></span> <span data-ttu-id="66060-157">「[Windows 10 Insider Preview ビルドの概要](https://docs.microsoft.com/windows-insider/get-started)」の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="66060-157">Follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>
2. <span data-ttu-id="66060-158">最新の [Microsoft Edge Dev チャネル](https://www.microsoftedgeinsider.com/download) (87.0.644.4 以降) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="66060-158">Install the latest version of [Microsoft Edge Dev channel](https://www.microsoftedgeinsider.com/download), 87.0.644.4 or higher.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="66060-159">デバイス レベルのインストールが必要であるため、Canary 以外のチャネルのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="66060-159">Because a device level installation is required, only a non-Canary channel is supported.</span></span>

3. <span data-ttu-id="66060-160">キオスク コンピューターで、[Windows の設定] を開き、検索フィールドに "キオスク" と入力します。</span><span class="sxs-lookup"><span data-stu-id="66060-160">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="66060-161">次のスクリーンショットに表示されている  **[Set up a kiosk (assigned access)]** (キオスク モードを設定する (割り当てられたアクセス)) を選択し、キオスクを作成するダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="66060-161">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

4. <span data-ttu-id="66060-163">**[Set up a kiosk]**  (キオスク モードを設定する) ページで、 **[開始する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66060-163">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="キオスク ページ - 開始する":::

5. <span data-ttu-id="66060-165">名前を入力して新しいキオスク アカウントを作成するか、または入力されているドロップダウン リストから既存のアカウントを選択して、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66060-165">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="キオスク モード - アカウントの作成":::

6. <span data-ttu-id="66060-167">**[キオスク アプリを選ぶ]**  ページで、**[Microsoft Edge]** を選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66060-167">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="66060-168">これは、Microsoft Edge Dev、Beta、Stable チャネルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="66060-168">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="キオスク モード - アプリを選ぶ":::

7. <span data-ttu-id="66060-170">Microsoft Edge がキオスク モードで実行しているときの表示方法について、次のいずれかのオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="66060-170">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="66060-171">デジタル/対話型サイネージ - 全画面表示モードで特定のサイトを表示し、Microsoft Edge を実行します。</span><span class="sxs-lookup"><span data-stu-id="66060-171">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="66060-172">パブリック ブラウザー - Microsoft Edge の限定的な複数タブのバージョンを実行します。</span><span class="sxs-lookup"><span data-stu-id="66060-172">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="キオスク モードの表示 - 全画面表示デジタル署名":::

8. <span data-ttu-id="66060-174"> *\*[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="66060-174">Select **Next**.</span></span>
9. <span data-ttu-id="66060-175">キオスクが起動したときに読み込む URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="66060-175">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="キオスク モード - URL の入力":::

10. <span data-ttu-id="66060-177">アイドル時間に、既定値の 5 分をそのまま使用するか、独自の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="66060-177">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="キオスク モード - アイドル時間の入力":::

11. <span data-ttu-id="66060-179"> *\*[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66060-179">Click **Next**.</span></span>
12. <span data-ttu-id="66060-180"> *\*[設定]**  ウィンドウを閉じて、選択内容を保存して適用します。</span><span class="sxs-lookup"><span data-stu-id="66060-180">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="キオスク モード - 設定の終了":::

13. <span data-ttu-id="66060-182">キオスク デバイスからサインオフし、ローカル キオスク アカウントでサインインして、構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="66060-182">Sign off from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <span data-ttu-id="66060-183">機能上の制限事項</span><span class="sxs-lookup"><span data-stu-id="66060-183">Functional limitations</span></span>

<span data-ttu-id="66060-184">このキオスク モードのプレビュー版をリリースすることにより、Microsoft は商品の改善と新機能の追加に継続的に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="66060-184">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="66060-185">現在、キオスク モードで次の機能はサポートされていませんが、次の機能を導入するための作業が進行中です。</span><span class="sxs-lookup"><span data-stu-id="66060-185">Although kiosk mode doesn't currently support the following functionality, work is underway on the following features:</span></span>

- <span data-ttu-id="66060-186">コレクション</span><span class="sxs-lookup"><span data-stu-id="66060-186">Collections</span></span>
- <span data-ttu-id="66060-187">拡張機能</span><span class="sxs-lookup"><span data-stu-id="66060-187">Extensions</span></span>
- <span data-ttu-id="66060-188">Internet Explorer モード</span><span class="sxs-lookup"><span data-stu-id="66060-188">Internet Explorer mode</span></span>
- <span data-ttu-id="66060-189">Windows Defender Application Guard (WDAG)</span><span class="sxs-lookup"><span data-stu-id="66060-189">Windows Defender Application Guard (WDAG)</span></span>

## <span data-ttu-id="66060-190">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="66060-190">Roadmap</span></span>

### <span data-ttu-id="66060-191">今年の後半 (2020)</span><span class="sxs-lookup"><span data-stu-id="66060-191">Later this year (2020)</span></span>

<span data-ttu-id="66060-192">次の機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="66060-192">We'll add the following features:</span></span>

- <span data-ttu-id="66060-193">[セッションの終了] ボタン</span><span class="sxs-lookup"><span data-stu-id="66060-193">End session button</span></span>
- <span data-ttu-id="66060-194">読み取り専用アドレス バー</span><span class="sxs-lookup"><span data-stu-id="66060-194">Read only address bar</span></span>  
  - <span data-ttu-id="66060-195">グループ ポリシーで構成可能</span><span class="sxs-lookup"><span data-stu-id="66060-195">Configurable with group policy</span></span>
  - <span data-ttu-id="66060-196">有効にすると、ユーザーはアドレス バーを編集したり別のページに移動したりできなくなります。</span><span class="sxs-lookup"><span data-stu-id="66060-196">When enabled, users will be prevented from editing the address bar and navigating to another page.</span></span>

- <span data-ttu-id="66060-197">その他のロックダウン機能:</span><span class="sxs-lookup"><span data-stu-id="66060-197">More lockdown functions:</span></span>

  - <span data-ttu-id="66060-198">追加のアクセラレータがブロックされます (Ctrl+N など)</span><span class="sxs-lookup"><span data-stu-id="66060-198">Additional accelerators will be blocked (for example, CTRL+N)</span></span>
  - <span data-ttu-id="66060-199">[...] 設定メニューで必須オプション (印刷、ヘルプ、フィードバック、音声読み上げなど) のみが有効になります</span><span class="sxs-lookup"><span data-stu-id="66060-199">The "…" settings menu will enable only required options (for example, Print, Help,  Feedback, and Read aloud)</span></span>
  - <span data-ttu-id="66060-200">追加の *edge://* ページ ロックダウン (*edge://settings* など)</span><span class="sxs-lookup"><span data-stu-id="66060-200">Additional *edge://* pages lockdown (for example, *edge://settings*)</span></span>
  - <span data-ttu-id="66060-201">印刷オプション UI の構成</span><span class="sxs-lookup"><span data-stu-id="66060-201">Configure print options UI</span></span>
  - <span data-ttu-id="66060-202">エクスプローラーをダウンロード フォルダーのみに制限します。</span><span class="sxs-lookup"><span data-stu-id="66060-202">Limiting file explorer to the download folder only.</span></span>

### <span data-ttu-id="66060-203">2021 年初旬</span><span class="sxs-lookup"><span data-stu-id="66060-203">In early 2021</span></span>

<span data-ttu-id="66060-204">次のサポートと機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="66060-204">We'll add the following support and features:</span></span>

- <span data-ttu-id="66060-205">シングル アプリとして割り当てられたアクセスによる Microsoft Edge キオスク モードの Windows での一般提供。</span><span class="sxs-lookup"><span data-stu-id="66060-205">General availability of Microsoft Edge kiosk mode with assigned access single app on Windows.</span></span>
- <span data-ttu-id="66060-206">Microsoft Edge 従来版とのパリティのための追加機能。</span><span class="sxs-lookup"><span data-stu-id="66060-206">Additional features for parity with Microsoft Edge Legacy.</span></span>
- <span data-ttu-id="66060-207">キオスク モード プロファイル UX を使用してデバイスを構成するための Intune との統合。</span><span class="sxs-lookup"><span data-stu-id="66060-207">Integration with Intune to configure devices using kiosk mode profile UX.</span></span>

## <span data-ttu-id="66060-208">関連項目</span><span class="sxs-lookup"><span data-stu-id="66060-208">See also</span></span>

- [<span data-ttu-id="66060-209">Windows デスクトップ エディションでのキオスクおよびデジタル サイネージの構成</span><span class="sxs-lookup"><span data-stu-id="66060-209">Configure kiosks and digital signs on Windows desktop editions</span></span>](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [<span data-ttu-id="66060-210">Microsoft Edge レガシ キオスク モードの展開</span><span class="sxs-lookup"><span data-stu-id="66060-210">Deploy Microsoft Edge Legacy kiosk mode</span></span>](https://aka.ms/edgekioskmode)
- [<span data-ttu-id="66060-211">Microsoft Edge の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="66060-211">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="66060-212">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="66060-212">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
