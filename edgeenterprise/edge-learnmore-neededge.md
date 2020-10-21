---
title: 最新の Web サイトに対応するための Internet Explorer から Microsoft Edge へのリダイレクト
ms.author: laannade
author: dan-wesley
manager: ratetali
ms.date: 10/19/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 最新の Web サイトに対応するための Internet Explorer から Microsoft Edge へのリダイレクト
ms.openlocfilehash: ce9e8dabdff25cc3ba375746ec82ddd78b6d7694
ms.sourcegitcommit: cf991cc4bd2e70169902cbda9ddc870d70e31ca2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2020
ms.locfileid: "11120522"
---
# <span data-ttu-id="c5848-103">最新の Web サイトに対応するための Internet Explorer から Microsoft Edge へのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="c5848-103">Redirection from Internet Explorer to Microsoft Edge for compatibility with modern web sites</span></span>

> [!NOTE]
> <span data-ttu-id="c5848-104">この記事は Microsoft Edge 安定バージョン 87 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c5848-104">This article applies to Microsoft Edge Stable version 87 or later.</span></span>

## <span data-ttu-id="c5848-105">概要</span><span class="sxs-lookup"><span data-stu-id="c5848-105">Overview</span></span>

<span data-ttu-id="c5848-106">最新の Web サイトの多くが、Internet Explorer と互換性のないデザインを採用しています。</span><span class="sxs-lookup"><span data-stu-id="c5848-106">Many modern websites have designs that are incompatible with Internet Explorer.</span></span> <span data-ttu-id="c5848-107">Internet Explorer のユーザーが互換性のないパブリック サイトにアクセスすると、そのサイトがブラウザーと互換性のないものであることを通知するメッセージが表示され、手動で別のブラウザーに切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5848-107">Whenever an Internet Explorer user visits an incompatible public site, they get a message that tells them the site is incompatible with their browser, and they need to manually switch to a different browser.</span></span>

<span data-ttu-id="c5848-108">Microsoft Edge 安定バージョン 87 から、手動で別のブラウザーに切り替える必要性について変更がありました。</span><span class="sxs-lookup"><span data-stu-id="c5848-108">The need to  manually switch to a different browser changes starting with Microsoft Edge Stable version 87.</span></span>

<span data-ttu-id="c5848-109">ユーザーが Internet Explorer と互換性のないサイトにアクセスすると、自動的に Microsoft Edge にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="c5848-109">When a user goes to a site that is incompatible with Internet Explorer, they will be automatically redirected to Microsoft Edge.</span></span> <span data-ttu-id="c5848-110">この記事では、リダイレクトのユーザー エクスペリエンスや、自動リダイレクトの構成や無効化に使用するグループ ポリシーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c5848-110">This article describes the user experience for redirection and the group policies that are used to configure or disable automatic redirection.</span></span>

> [!NOTE]
> <span data-ttu-id="c5848-111">Microsoft は、Internet Explorer との互換性がないことが知られているすべてのサイトの一覧を保持しています。</span><span class="sxs-lookup"><span data-stu-id="c5848-111">Microsoft maintains a list of all sites that are known to be incompatible with Internet Explorer.</span></span>

## <span data-ttu-id="c5848-112">リダイレクト エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="c5848-112">Redirection experience</span></span>

<span data-ttu-id="c5848-113">Microsoft Edge にリダイレクトすると、ユーザーには次のスクリーンショットにあるようなダイアログが 1 回のみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5848-113">On redirection to Microsoft Edge, users are shown the one-time dialog in the next screenshot.</span></span> <span data-ttu-id="c5848-114">このダイアログでは、リダイレクトされた理由を説明し、Internet Explorer から Microsoft Edge に閲覧データや設定をコピーすることに対する同意を求めています。</span><span class="sxs-lookup"><span data-stu-id="c5848-114">This dialog explains why they're getting redirected and prompts for consent to copy their browsing data and preferences from Internet Explorer to Microsoft Edge.</span></span> <span data-ttu-id="c5848-115">次の閲覧データがインポートされます: お気に入り、パスワード、検索エンジン、開いているタブ、履歴、設定、Cookie、ホーム ページ。</span><span class="sxs-lookup"><span data-stu-id="c5848-115">The following browsing data will be imported: Favorites, Passwords, Search engines, open tabs, History, settings, cookies, and the Home Page.</span></span>

![データや環境設定をインポートするためのブラウズ通知とプロンプト。](media/edge-learnmore-neededge/neededge-dialog1.png)

<span data-ttu-id="c5848-117">[Always bring over my browsing data and preferences from Internet Explorer] (常に Internet Explorer から閲覧データや環境設定を取り込む) のチェック ボックスをオンにして同意していなくても、 **[閲覧を続ける]**  をクリックしてセッションを継続することができます。</span><span class="sxs-lookup"><span data-stu-id="c5848-117">Even if they don't give their consent by checking "Always bring over my browsing data and preferences from Internet Explorer", they can click **Continue browsing** to continue their session.</span></span>

<span data-ttu-id="c5848-118">最後に、リダイレクトのたびにアドレス バーの下に次のスクリーンショットに示されているような Web サイトの非互換性バナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5848-118">Finally, a website incompatibility banner, shown in the next screenshot, appears below the address bar for every redirection.</span></span>

![最新のサイトに関する通知と、Microsoft Edge を既定のブラウザーに設定するか、Microsoft Edge を探すように促すプロンプトが表示されます。](media/edge-learnmore-neededge/neededge-banner.png)

<span data-ttu-id="c5848-120">Web サイトの非互換性バナー:</span><span class="sxs-lookup"><span data-stu-id="c5848-120">The website incompatibility banner:</span></span>

- <span data-ttu-id="c5848-121">ユーザーに Microsoft Edge への切り替えを促します</span><span class="sxs-lookup"><span data-stu-id="c5848-121">encourages the user to switch to Microsoft Edge</span></span>
- <span data-ttu-id="c5848-122">Microsoft Edge を既定のブラウザーとして設定するよう提案します</span><span class="sxs-lookup"><span data-stu-id="c5848-122">offers to make Microsoft Edge as the default browser</span></span>
- <span data-ttu-id="c5848-123">Microsoft Edge を探すためのオプションを提供します</span><span class="sxs-lookup"><span data-stu-id="c5848-123">gives the user the option to explore Microsoft Edge</span></span>

<span data-ttu-id="c5848-124">サイトが Internet Explorer から Microsoft Edge へとリダイレクトされた場合、サイトの読み込みを開始した Internet Explorer のタブは、それ以前にコンテンツがない場合には閉じられます。</span><span class="sxs-lookup"><span data-stu-id="c5848-124">When a site is redirected from Internet Explorer to Microsoft Edge, the Internet Explorer tab that started loading the site is closed if it had no prior content.</span></span> <span data-ttu-id="c5848-125">それ以外の場合は、アクティブなタブ ビューが、サイトが Microsoft Edge へとリダイレクトされた理由を説明する Microsoft の [サポート](https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554?ui=en-US&rs=en-US&ad=US)  ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="c5848-125">Otherwise, the active tab view goes to a  Microsoft [support](https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554?ui=en-US&rs=en-US&ad=US) page that explains why the site was redirected to Microsoft Edge.</span></span>

> [!NOTE]
> <span data-ttu-id="c5848-126">リダイレクト後は、ユーザーは Internet Explorer の非互換性リストにないサイトを閲覧するために Internet Explorer の使用に戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="c5848-126">After a redirection users can go back to using Internet Explorer for sites that are not on the Internet Explorer incompatibility list.</span></span>  

## <span data-ttu-id="c5848-127">Microsoft Edge へのリダイレクトを構成するポリシー</span><span class="sxs-lookup"><span data-stu-id="c5848-127">Policies to configure redirection to Microsoft Edge</span></span>

> [!NOTE]
> <span data-ttu-id="c5848-128">これらのポリシーは 2020 年 10 月 26 日までに ADMX ファイルの更新プログラムとして利用可能になり、2020 年 11 月 9 日までに Intune で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="c5848-128">These policies will be available as ADMX file updates by October 26, 2020 and will be available in Intune by November 9, 2020.</span></span>

<span data-ttu-id="c5848-129">Microsoft Edge への自動リダイレクトを有効にするには、3 つのグループ ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5848-129">Three group policies must be configured to enable automatic redirection to Microsoft Edge.</span></span> <span data-ttu-id="c5848-130">3 つのポリシーは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c5848-130">These policies are:</span></span>

- <span data-ttu-id="c5848-131">RedirectSitesFromInternetExplorerPreventBHOInstall</span><span class="sxs-lookup"><span data-stu-id="c5848-131">RedirectSitesFromInternetExplorerPreventBHOInstall</span></span>
- <span data-ttu-id="c5848-132">RedirectSitesFromInternetExplorerRedirectMode</span><span class="sxs-lookup"><span data-stu-id="c5848-132">RedirectSitesFromInternetExplorerRedirectMode</span></span>
- <span data-ttu-id="c5848-133">HideInternetExplorerRedirectUXForIncompatibleSitesEnabled</span><span class="sxs-lookup"><span data-stu-id="c5848-133">HideInternetExplorerRedirectUXForIncompatibleSitesEnabled</span></span>

### <span data-ttu-id="c5848-134">ポリシー: RedirectSitesFromInternetExplorerPreventBHOInstall</span><span class="sxs-lookup"><span data-stu-id="c5848-134">Policy: RedirectSitesFromInternetExplorerPreventBHOInstall</span></span>

<span data-ttu-id="c5848-135">Internet Explorer から Microsoft Edge へのリダイレクトには、"IEtoEdge BHO" という名前の Internet Explorer ブラウザー ヘルパー オブジェクト (BHO) が必要です。</span><span class="sxs-lookup"><span data-stu-id="c5848-135">Redirection from Internet Explorer to Microsoft Edge requires an Internet Explorer Browser Helper Object (BHO) named "IEtoEdge BHO".</span></span> <span data-ttu-id="c5848-136">**RedirectSitesFromInternetExplorerPreventBHOInstall** ポリシーは、この BHO がインストールされるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="c5848-136">The **RedirectSitesFromInternetExplorerPreventBHOInstall** policy controls whether or not this BHO is installed.</span></span>  

- <span data-ttu-id="c5848-137">このポリシーを有効にすると、リダイレクトに必要な BHO はインストールされず、Internet Explorer 上の特定の Web サイトではユーザーに対して非互換性メッセージが表示され続けます。</span><span class="sxs-lookup"><span data-stu-id="c5848-137">If you enable this policy, the BHO required for redirection will not be installed and your users will continue to see incompatibility messages for certain websites on Internet Explorer.</span></span> <span data-ttu-id="c5848-138">すでに BHO がインストールされている場合は、次回の Microsoft Edge 安定チャネルの更新時にアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c5848-138">If the BHO is already installed, it will be uninstalled the next time the Microsoft Edge Stable channel is updated.</span></span>
- <span data-ttu-id="c5848-139">このポリシーを無効にしているか、構成していない場合、BHO はインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c5848-139">If you disable or don't configure this policy, the BHO will be installed.</span></span> <span data-ttu-id="c5848-140">これは既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="c5848-140">This is the default behavior.</span></span>

<span data-ttu-id="c5848-141">BHO の必要性に加えて、"Sitelist" または "未構成" に設定する必要がある **RedirectSitesFromInternetExplorerRedirectMode** への依存関係があります。</span><span class="sxs-lookup"><span data-stu-id="c5848-141">In addition to needing the BHO, there is a dependency on the **RedirectSitesFromInternetExplorerRedirectMode**, which needs to be set to "Sitelist" or "Not Configured".</span></span>

### <span data-ttu-id="c5848-142">ポリシー: RedirectSitesFromInternetExplorerRedirectMode</span><span class="sxs-lookup"><span data-stu-id="c5848-142">Policy: RedirectSitesFromInternetExplorerRedirectMode</span></span>

 <span data-ttu-id="c5848-143">このポリシーは、Microsoft Edge の**既定のブラウザー**設定 "Internet Explorer に Microsoft Edge でサイトを開かせる" に対応しています。</span><span class="sxs-lookup"><span data-stu-id="c5848-143">This policy corresponds to the Microsoft Edge **Default browser** setting "Let Internet Explorer open sites in Microsoft Edge".</span></span> <span data-ttu-id="c5848-144">この設定にアクセスするには、*edge://settings/defaultbrowser* の URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c5848-144">You can access this setting by going to the *edge://settings/defaultbrowser* URL.</span></span>  

- <span data-ttu-id="c5848-145">このポリシーを設定していないか、"Sitelist" に設定している場合、Internet Explorer は互換性のないサイトを Microsoft Edge にリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="c5848-145">If you don't configure this policy or set it to "Sitelist", Internet Explorer will redirect incompatible sites to Microsoft Edge.</span></span> <span data-ttu-id="c5848-146">これは既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="c5848-146">This is the default behavior.</span></span>
- <span data-ttu-id="c5848-147">このポリシーを無効にしている場合、互換性のないサイトは Microsoft Edge にリダイレクトされません。</span><span class="sxs-lookup"><span data-stu-id="c5848-147">If you disable this policy, incompatible sites aren't redirected to Microsoft Edge.</span></span>

> [!NOTE]
> <span data-ttu-id="c5848-148">組織で管理されていない個人のデバイスを使用している場合は、**Internet Explorer の互換性**の下に "サイトの読み込みを Internet Explorer モードで許可する" という別の設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5848-148">If you're on a personal device that isn't  managed by your organization, you'll see another setting named "Allow sites to be loaded in Internet Explorer mode" under **Internet Explorer compatibility**.</span></span>
>
><span data-ttu-id="c5848-149">ドメインに参加しているか、モバイル デバイス管理 (MDM) に登録されているデバイスを使用している場合、このオプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="c5848-149">If you're on a domain joined or Mobile Device Management (MDM) enrolled device, you won't see this option.</span></span>
>
> <span data-ttu-id="c5848-150">代わりに、ユーザーに Internet Explorer モードでサイトを読み込ませる場合は、[Internet Explorer モード テストを許可する](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allow-internet-explorer-mode-testing)ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c5848-150">Instead, if you want to let your users load sites in Internet Explorer mode, you can do so by configuring the policy [Allow Internet Explorer mode testing](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allow-internet-explorer-mode-testing).</span></span>

### <span data-ttu-id="c5848-151">ポリシー: HideInternetExplorerRedirectUXForIncompatibleSitesEnabled</span><span class="sxs-lookup"><span data-stu-id="c5848-151">Policy: HideInternetExplorerRedirectUXForIncompatibleSitesEnabled</span></span>

<span data-ttu-id="c5848-152">このポリシーでは、互換性のないサイトを Microsoft Edge にリダイレクトするときのユーザー エクスペリエンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="c5848-152">This policy configures the user experience for incompatible site redirection to Microsoft Edge.</span></span>  

- <span data-ttu-id="c5848-153">このポリシーを有効にすると、ユーザーに対する 1 回限りのリダイレクト ダイアログとリダイレクト バナーが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="c5848-153">If you enable this policy, users never see the one-time redirection dialog and the redirection banner.</span></span> <span data-ttu-id="c5848-154">ブラウザーのデータやユーザー設定はインポートされません。</span><span class="sxs-lookup"><span data-stu-id="c5848-154">No browser data or user preferences are imported.</span></span>
- <span data-ttu-id="c5848-155">このポリシーを無効にしているか設定していない場合、最初のリダイレクトでリダイレクト ダイアログが表示され、リダイレクトとともに始まるセッションでは永続的なリダイレクト バナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5848-155">If you disable or don't configure this policy, the redirection dialog will be shown on the first redirection and the persistent redirection banner will be shown for sessions that start with a redirection.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c5848-156">ユーザーの閲覧データは、ユーザーに対して新しいリダイレクトが発生するたびにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="c5848-156">User browsing data will be imported every time a user encounters a new redirection.</span></span> <span data-ttu-id="c5848-157">ただし、これは 1 回限りのリダイレクト ダイアログでユーザーがインポートに同意した場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="c5848-157">However, this only happens if the user consented to the import on the one-time redirection dialog.</span></span>

## <span data-ttu-id="c5848-158">Microsoft Edge へのリダイレクトを無効にする</span><span class="sxs-lookup"><span data-stu-id="c5848-158">Disable redirection to Microsoft Edge</span></span>

<span data-ttu-id="c5848-159">Microsoft Edge 安定バージョン 87 にアップデートする前にリダイレクトを無効にする場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5848-159">If you want to disable redirection BEFORE updating to Microsoft Edge Stable version 87, use the following step:</span></span>

1. <span data-ttu-id="c5848-160">**RedirectSitesFromInternetExplorerRedirectMode** ポリシーを**有効**に設定します。</span><span class="sxs-lookup"><span data-stu-id="c5848-160">Set the **RedirectSitesFromInternetExplorerRedirectMode** policy to **Enabled**.</span></span> <span data-ttu-id="c5848-161">この設定は、ポリシーが有効になるとすぐにリダイレクトを停止します。</span><span class="sxs-lookup"><span data-stu-id="c5848-161">This setting will stop redirecting as soon as the policy takes effect.</span></span>

<span data-ttu-id="c5848-162">Microsoft Edge 安定バージョン 87 にアップデートした後にリダイレクトを無効にする場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5848-162">If you want to disable redirection AFTER updating to Microsoft Edge Stable version 87, use the following steps:</span></span>

1. <span data-ttu-id="c5848-163">**RedirectSitesFromInternetExplorerRedirectMode** ポリシーを**無効**に設定します。</span><span class="sxs-lookup"><span data-stu-id="c5848-163">Set the **RedirectSitesFromInternetExplorerRedirectMode** policy to **Disabled**.</span></span> <span data-ttu-id="c5848-164">この設定は、ポリシーが有効になるとすぐにリダイレクトを停止します。</span><span class="sxs-lookup"><span data-stu-id="c5848-164">This setting will stop redirecting as soon as the policy takes effect.</span></span>
2. <span data-ttu-id="c5848-165">**RedirectSitesFromInternetExplorerPreventBHOInstall** ポリシーを**有効**に設定します。</span><span class="sxs-lookup"><span data-stu-id="c5848-165">Set the **RedirectSitesFromInternetExplorerPreventBHOInstall** policy to **Enabled**.</span></span> <span data-ttu-id="c5848-166">これで次回の Microsoft Edge の更新後に BHO がアンインストールされるようになります。</span><span class="sxs-lookup"><span data-stu-id="c5848-166">This will uninstall the BHO after the next Microsoft Edge update.</span></span>

## <span data-ttu-id="c5848-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5848-167">See also</span></span>

- [<span data-ttu-id="c5848-168">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="c5848-168">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="c5848-169">Microsoft Edge ポリシー</span><span class="sxs-lookup"><span data-stu-id="c5848-169">Microsoft Edge Policies</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies)