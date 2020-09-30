---
title: Microsoft Edge キオスク モードを構成する
ms.author: aguta
author: aguta
manager: srugh
ms.date: 09/24/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge キオスク モードを構成する
ms.openlocfilehash: 17852cc7c7e4921a0fbef7d09a3f1c3d3cccf49f
ms.sourcegitcommit: b1285b7745eb41b241d706b401f8ce78fa33b227
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "11078667"
---
# <span data-ttu-id="c56cd-103">Microsoft Edge キオスク モードを構成する</span><span class="sxs-lookup"><span data-stu-id="c56cd-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="c56cd-104">この記事では、パイロットを実行することができる Microsoft Edge キオスク モードのオプションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="c56cd-105">また、予定されている機能のロードマップも含まれます。</span><span class="sxs-lookup"><span data-stu-id="c56cd-105">There's also a roadmap of features we are targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="c56cd-106">この記事は Microsoft Edge version 87 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c56cd-106">This article applies to Microsoft Edge version 87 or later.</span></span>

<span data-ttu-id="c56cd-107">Microsoft Edge レガシのキオスク モード (version 45 以前) については、「[Microsoft Edge キオスク モードの展開](https://aka.ms/edgekioskmode)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c56cd-107">For information about Microsoft Edge Legacy kiosk mode (version 45 and earlier) see [Deploy Microsoft Edge kiosk mode](https://aka.ms/edgekioskmode).</span></span>

## <span data-ttu-id="c56cd-108">概要</span><span class="sxs-lookup"><span data-stu-id="c56cd-108">Overview</span></span>

<span data-ttu-id="c56cd-109">Microsoft Edge キオスク モードは、ブラウザーの 2 つのロックダウン エクスペリエンスを提供し、組織が顧客に最高のエクスペリエンスを作成し、管理し、提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c56cd-109">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="c56cd-110">次のロックダウン エクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="c56cd-110">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="c56cd-111">デジタル/対話型サイネージ エクスペリエンスでは、全画面表示モードで特定のサイトを表示します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-111">The Digital/Interactive signage experience displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="c56cd-112">パブリック ブラウジング エクスペリエンスでは、Microsoft Edge の限定的な複数タブのバージョンを実行します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-112">The public-browsing experience runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="c56cd-113">どちらのエクスペリエンスでも、ユーザー データを保護する Microsoft Edge InPrivate セッションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-113">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <span data-ttu-id="c56cd-114">Microsoft Edge キオスク モードのセットアップ</span><span class="sxs-lookup"><span data-stu-id="c56cd-114">Set up Microsoft Edge kiosk mode</span></span>  

<span data-ttu-id="c56cd-115">キオスク モード機能の初期セットが Microsoft Edge Canary チャネルのバージョン 87 でテストに使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c56cd-115">An initial set of kiosk mode features are now available to test with Microsoft Edge Canary Channel, version 87.</span></span> <span data-ttu-id="c56cd-116">Microsoft Edge Canary は、[Microsoft Edge Insider Channels](https://www.microsoftedgeinsider.com/download) ページからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="c56cd-116">You can download Microsoft Edge Canary from the [Microsoft Edge Insider Channels](https://www.microsoftedgeinsider.com/download) page.</span></span>

### <span data-ttu-id="c56cd-117">キオスク モードの機能</span><span class="sxs-lookup"><span data-stu-id="c56cd-117">Kiosk mode features</span></span>

<span data-ttu-id="c56cd-118">次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c56cd-118">The following features are available:</span></span>

- <span data-ttu-id="c56cd-119">InPrivate ナビゲーション。</span><span class="sxs-lookup"><span data-stu-id="c56cd-119">InPrivate navigation.</span></span> <span data-ttu-id="c56cd-120">セッション終了時にブラウザー データとダウンロードを削除して、ユーザー データを保護します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-120">Protects user data by deleting browser data and downloads when the session ends.</span></span>
- <span data-ttu-id="c56cd-121">終了時のダウンロード削除を構成するためのポリシー。</span><span class="sxs-lookup"><span data-stu-id="c56cd-121">Policy to configure Delete downloads on exit.</span></span>
- <span data-ttu-id="c56cd-122">非アクティブ状態が特定期間続いた後に、ユーザー セッションをリセットする。</span><span class="sxs-lookup"><span data-stu-id="c56cd-122">Reset user session after a certain period of inactivity.</span></span>
- <span data-ttu-id="c56cd-123">ロックダウン機能の初期セット。</span><span class="sxs-lookup"><span data-stu-id="c56cd-123">Initial set of lockdown functionality.</span></span> <span data-ttu-id="c56cd-124">次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c56cd-124">The following functions are available:</span></span>

  - <span data-ttu-id="c56cd-125">マウスのコンテキスト メニュー</span><span class="sxs-lookup"><span data-stu-id="c56cd-125">Mouse context menu</span></span>
  - <span data-ttu-id="c56cd-126">F12 開発者ツール</span><span class="sxs-lookup"><span data-stu-id="c56cd-126">F12 Developer Tools</span></span>
  - <span data-ttu-id="c56cd-127">F11 全画面表示の終了 (全画面表示モードのとき)</span><span class="sxs-lookup"><span data-stu-id="c56cd-127">F11 Exit full screen (while in full screen mode)</span></span>
  - <span data-ttu-id="c56cd-128">*Edge://* ページの初期セットのブロック</span><span class="sxs-lookup"><span data-stu-id="c56cd-128">Blocking of the initial set of *Edge://* pages</span></span>

> [!NOTE]
> <span data-ttu-id="c56cd-129">キオスク モードの進化に伴い、より多くの機能を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c56cd-129">As kiosk mode evolves, more features will be available.</span></span>

### <span data-ttu-id="c56cd-130">キオスク モードの機能を使用する</span><span class="sxs-lookup"><span data-stu-id="c56cd-130">Use kiosk mode features</span></span>

<span data-ttu-id="c56cd-131">Microsoft Edge キオスク モードの機能は、Windows 10 の次のコマンド ライン オプションで起動できます。</span><span class="sxs-lookup"><span data-stu-id="c56cd-131">You can invoke Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options:</span></span>

- <span data-ttu-id="c56cd-132">キオスク モードのデジタル/対話型サイネージ:</span><span class="sxs-lookup"><span data-stu-id="c56cd-132">Kiosk mode Digital/Interactive signage:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen`
- <span data-ttu-id="c56cd-133">キオスク モードのパブリック ブラウジング:</span><span class="sxs-lookup"><span data-stu-id="c56cd-133">Kiosk mode public browsing:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing`

#### <span data-ttu-id="c56cd-134">その他のコマンド ライン オプション</span><span class="sxs-lookup"><span data-stu-id="c56cd-134">Additional command line options</span></span>

- `--no-first-run` <span data-ttu-id="c56cd-135">: Microsoft Edge の最初の実行エクスペリエンスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c56cd-135">: Disable the first Microsoft Edge run experience.</span></span>
- `--kiosk-idle-timeout-minutes` <span data-ttu-id="c56cd-136">: Microsoft Edge キオスク モードでユーザーのセッションがリセットされる前に、最後のユーザー アクティビティから時間 (分単位) を変更します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-136">: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="c56cd-137">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c56cd-137">The following values are supported:</span></span>

  - <span data-ttu-id="c56cd-138">既定値</span><span class="sxs-lookup"><span data-stu-id="c56cd-138">Default values</span></span>
    - <span data-ttu-id="c56cd-139">全画面表示 - オフ</span><span class="sxs-lookup"><span data-stu-id="c56cd-139">Full screen - turned off</span></span>
    - <span data-ttu-id="c56cd-140">パブリック ブラウジング - 5 分</span><span class="sxs-lookup"><span data-stu-id="c56cd-140">Public browsing - 5 minutes</span></span>
  - <span data-ttu-id="c56cd-141">指定可能な値</span><span class="sxs-lookup"><span data-stu-id="c56cd-141">Allowed values</span></span>
    - <span data-ttu-id="c56cd-142">0 - タイマーをオフにします</span><span class="sxs-lookup"><span data-stu-id="c56cd-142">0 - turns off the timer</span></span>
    - <span data-ttu-id="c56cd-143">1 - 1440 分 (アイドル タイマー時のリセット)</span><span class="sxs-lookup"><span data-stu-id="c56cd-143">1-1440 minutes for reset on idle timer</span></span>

## <span data-ttu-id="c56cd-144">割り当てられたアクセスによるキオスク モードをセットアップする</span><span class="sxs-lookup"><span data-stu-id="c56cd-144">Set up kiosk mode with assigned access</span></span>

<span data-ttu-id="c56cd-145">現在、割り当てられたアクセスによる Microsoft Edge のキオスク モードは、最新の [Windows 10 Insider Preview ビルド](https://insider.windows.com/) (バージョン 20215 以降) と [Microsoft Edge Dev チャネル](https://www.microsoftedgeinsider.com/download) (バージョン 87.0.644.4 以降) でテストに使用できます。</span><span class="sxs-lookup"><span data-stu-id="c56cd-145">Microsoft Edge kiosk mode with assigned access is currently available for testing with the latest [Windows 10 Insider Preview Build](https://insider.windows.com/), version 20215 or higher, and with the [Microsoft Edge Dev Channel](https://www.microsoftedgeinsider.com/download), version 87.0.644.4  or higher.</span></span>

**<span data-ttu-id="c56cd-146">Windows Insiders Preview を入手するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="c56cd-146">How do I get the Windows Insiders preview?</span></span>**

<span data-ttu-id="c56cd-147">PC に Windows 10 Insider Preview ビルドをインストールするには、「[Windows 10 Insider Preview ビルドの概要](https://docs.microsoft.com/windows-insider/get-started)」の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="c56cd-147">To install a Windows 10 Insider Preview Build on a PC, follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>

### <span data-ttu-id="c56cd-148">Windows の設定を使用して構成する</span><span class="sxs-lookup"><span data-stu-id="c56cd-148">Configure using Windows Settings</span></span>

<span data-ttu-id="c56cd-149">Windows の設定は、1 つか 2 つのシングル アプリのキオスク デバイスを設定する最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="c56cd-149">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="c56cd-150">シングル アプリのキオスク コンピューターをセットアップするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c56cd-150">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="c56cd-151">最新の Windows 10 Insider Preview (バージョン 20215 以降) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c56cd-151">Install the latest Windows 10 Insider Preview, version 20215 or higher.</span></span> <span data-ttu-id="c56cd-152">「[Windows 10 Insider Preview ビルドの概要](https://docs.microsoft.com/windows-insider/get-started)」の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="c56cd-152">Follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>
2. <span data-ttu-id="c56cd-153">最新の [Microsoft Edge Dev チャネル](https://www.microsoftedgeinsider.com/download) (87.0.644.4 以降) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c56cd-153">Install the latest version of [Microsoft Edge Dev channel](https://www.microsoftedgeinsider.com/download), 87.0.644.4 or higher.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="c56cd-154">デバイス レベルのインストールが必要であるため、Canary 以外のチャネルのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c56cd-154">Because a device level installation is required, only a non-Canary channel is supported.</span></span>

3. <span data-ttu-id="c56cd-155">キオスク コンピューターで、[Windows の設定] を開き、検索フィールドに "キオスク" と入力します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-155">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="c56cd-156">次のスクリーンショットに表示されている  **[Set up a kiosk (assigned access)]** (キオスク モードを設定する (割り当てられたアクセス)) を選択し、キオスクを作成するダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="c56cd-156">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

4. <span data-ttu-id="c56cd-158">**[Set up a kiosk]**  (キオスク モードを設定する) ページで、 **[開始する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c56cd-158">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

5. <span data-ttu-id="c56cd-160">名前を入力して新しいキオスク アカウントを作成するか、または入力されているドロップダウン リストから既存のアカウントを選択して、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c56cd-160">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

6. <span data-ttu-id="c56cd-162">**[キオスク アプリを選ぶ]**  ページで、**[Microsoft Edge]** を選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c56cd-162">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c56cd-163">これは、Microsoft Edge Dev、Beta、Stable チャネルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c56cd-163">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

7. <span data-ttu-id="c56cd-165">Microsoft Edge がキオスク モードで実行しているときの表示方法について、次のいずれかのオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="c56cd-165">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="c56cd-166">デジタル/対話型サイネージ - 全画面表示モードで特定のサイトを表示し、Microsoft Edge を実行します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-166">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="c56cd-167">パブリック ブラウザー - Microsoft Edge の限定的な複数タブのバージョンを実行します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-167">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

8. <span data-ttu-id="c56cd-169"> *\*[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-169">Select **Next**.</span></span>
9. <span data-ttu-id="c56cd-170">キオスクが起動したときに読み込む URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-170">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

10. <span data-ttu-id="c56cd-172">アイドル時間に、既定値の 5 分をそのまま使用するか、独自の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-172">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

11. <span data-ttu-id="c56cd-174"> *\*[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c56cd-174">Click **Next**.</span></span>
12. <span data-ttu-id="c56cd-175"> *\*[設定]**  ウィンドウを閉じて、選択内容を保存して適用します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-175">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

13. <span data-ttu-id="c56cd-177">キオスク デバイスからサインオフし、ローカル キオスク アカウントでサインインして、構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-177">Sign off from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <span data-ttu-id="c56cd-178">機能上の制限事項</span><span class="sxs-lookup"><span data-stu-id="c56cd-178">Functional limitations</span></span>

<span data-ttu-id="c56cd-179">このキオスク モードのプレビュー版をリリースすることにより、Microsoft は商品の改善と新機能の追加に継続的に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="c56cd-179">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="c56cd-180">現在、キオスク モードで次の機能はサポートされていませんが、次の機能を導入するための作業が進行中です。</span><span class="sxs-lookup"><span data-stu-id="c56cd-180">Although kiosk mode doesn't currently support the following functionality, work is underway on the following features:</span></span>

- <span data-ttu-id="c56cd-181">コレクション</span><span class="sxs-lookup"><span data-stu-id="c56cd-181">Collections</span></span>
- <span data-ttu-id="c56cd-182">拡張機能</span><span class="sxs-lookup"><span data-stu-id="c56cd-182">Extensions</span></span>
- <span data-ttu-id="c56cd-183">Internet Explorer モード</span><span class="sxs-lookup"><span data-stu-id="c56cd-183">Internet Explorer mode</span></span>
- <span data-ttu-id="c56cd-184">Windows Defender Application Guard (WDAG)</span><span class="sxs-lookup"><span data-stu-id="c56cd-184">Windows Defender Application Guard (WDAG)</span></span>

## <span data-ttu-id="c56cd-185">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="c56cd-185">Roadmap</span></span>

### <span data-ttu-id="c56cd-186">今年の後半 (2020)</span><span class="sxs-lookup"><span data-stu-id="c56cd-186">Later this year (2020)</span></span>

<span data-ttu-id="c56cd-187">次の機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-187">We'll add the following features:</span></span>

- <span data-ttu-id="c56cd-188">[セッションの終了] ボタン</span><span class="sxs-lookup"><span data-stu-id="c56cd-188">End session button</span></span>
- <span data-ttu-id="c56cd-189">読み取り専用 URL アドレス バー</span><span class="sxs-lookup"><span data-stu-id="c56cd-189">Read only URL address bar</span></span>  
  - <span data-ttu-id="c56cd-190">グループ ポリシーで構成可能</span><span class="sxs-lookup"><span data-stu-id="c56cd-190">Configurable with group policy</span></span>
  - <span data-ttu-id="c56cd-191">有効にすると、ユーザーはアドレス バーの URL を編集して別のページに移動することができません。</span><span class="sxs-lookup"><span data-stu-id="c56cd-191">When enabled, users will be prevented from editing the address bar URL to try navigating away to another page.</span></span>

- <span data-ttu-id="c56cd-192">その他のロックダウン機能:</span><span class="sxs-lookup"><span data-stu-id="c56cd-192">More lockdown functions:</span></span>

  - <span data-ttu-id="c56cd-193">追加のアクセラレータがブロックされます (Ctrl+N など)</span><span class="sxs-lookup"><span data-stu-id="c56cd-193">Additional accelerators will be blocked (for example, CTRL+N)</span></span>
  - <span data-ttu-id="c56cd-194">[...] 設定メニューで必須オプション (印刷、ヘルプ、フィードバック、音声読み上げなど) のみが有効になります</span><span class="sxs-lookup"><span data-stu-id="c56cd-194">The "…" settings menu will enable only required options (for example, Print, Help,  Feedback, and Read aloud)</span></span>
  - <span data-ttu-id="c56cd-195">追加の *edge://* ページ ロックダウン (*edge://settings* など)</span><span class="sxs-lookup"><span data-stu-id="c56cd-195">Additional *edge://* pages lockdown (for example, *edge://settings*)</span></span>
  - <span data-ttu-id="c56cd-196">印刷オプション UI の構成</span><span class="sxs-lookup"><span data-stu-id="c56cd-196">Configure print options UI</span></span>
  - <span data-ttu-id="c56cd-197">エクスプローラーをダウンロード フォルダーのみに制限します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-197">Limiting file explorer to the download folder only.</span></span>

### <span data-ttu-id="c56cd-198">2021 年初旬</span><span class="sxs-lookup"><span data-stu-id="c56cd-198">In early 2021</span></span>

<span data-ttu-id="c56cd-199">次のサポートと機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="c56cd-199">We'll add the following support and features:</span></span>

- <span data-ttu-id="c56cd-200">シングル アプリとして割り当てられたアクセスによる Microsoft Edge キオスク モードの Windows での一般提供。</span><span class="sxs-lookup"><span data-stu-id="c56cd-200">General availability of Microsoft Edge kiosk mode with assigned access single app on Windows.</span></span>
- <span data-ttu-id="c56cd-201">Microsoft Edge 従来版とのパリティのための追加機能。</span><span class="sxs-lookup"><span data-stu-id="c56cd-201">Additional features for parity with Microsoft Edge Legacy.</span></span>
- <span data-ttu-id="c56cd-202">キオスク モード プロファイル UX を使用してデバイスを構成するための Intune との統合。</span><span class="sxs-lookup"><span data-stu-id="c56cd-202">Integration with Intune to configure devices using kiosk mode profile UX.</span></span>

## <span data-ttu-id="c56cd-203">関連項目</span><span class="sxs-lookup"><span data-stu-id="c56cd-203">See also</span></span>

- [<span data-ttu-id="c56cd-204">Windows デスクトップ エディションでのキオスクおよびデジタル サイネージの構成</span><span class="sxs-lookup"><span data-stu-id="c56cd-204">Configure kiosks and digital signs on Windows desktop editions</span></span>](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [<span data-ttu-id="c56cd-205">Microsoft Edge レガシ キオスク モードの展開</span><span class="sxs-lookup"><span data-stu-id="c56cd-205">Deploy Microsoft Edge Legacy kiosk mode</span></span>](https://aka.ms/edgekioskmode)
- [<span data-ttu-id="c56cd-206">Microsoft Edge の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="c56cd-206">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="c56cd-207">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="c56cd-207">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)