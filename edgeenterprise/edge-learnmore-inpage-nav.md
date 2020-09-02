---
title: Internet Explorer モードでページ内ナビゲーションを保持する
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 05/01/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Internet Explorer モードでページ内ナビゲーションを保持する
ms.openlocfilehash: 0acca9e05a0d09b02fa61d5ddd7de3f7c6cabb92
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980452"
---
# <span data-ttu-id="6e80b-103">Internet Explorer モードでページ内ナビゲーションを保持する</span><span class="sxs-lookup"><span data-stu-id="6e80b-103">Keep in-page navigation in Internet Explorer mode</span></span>

<span data-ttu-id="6e80b-104">このポリシーは、Internet Explorer モード (IE モード) サイトからのすべてのページ内ナビゲーションを強制的に IE モードにするための一時的なソリューションとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e80b-104">You can use this policy as a temporary solution to force all in-page navigation from Internet Explorer mode (IE mode) sites to stay in IE mode.</span></span>

<span data-ttu-id="6e80b-105">ページ内ナビゲーションは、現在のページのリンク、スクリプト、またはフォームから開始されます。</span><span class="sxs-lookup"><span data-stu-id="6e80b-105">An in-page navigation is started from a link, a script, or a form on the current page.</span></span> <span data-ttu-id="6e80b-106">また、前回のページ内ナビゲーションの試行のサーバー側リダイレクトにもなります。</span><span class="sxs-lookup"><span data-stu-id="6e80b-106">It can also be a server-side redirect of a previous in-page navigation attempt.</span></span> <span data-ttu-id="6e80b-107">逆に、ユーザーはブラウザーの制御で、現在のページから独立したページ内ではないナビゲーションを開始することができます。</span><span class="sxs-lookup"><span data-stu-id="6e80b-107">Conversely, a user can start a navigation that isn't in-page that's independent of the current page in several ways by using the browser controls.</span></span> <span data-ttu-id="6e80b-108">たとえば、アドレス バー、[戻る] ボタン、またはお気に入りリンクを使用する場合です。</span><span class="sxs-lookup"><span data-stu-id="6e80b-108">For example, using the address bar, the back button, or a favorite link.</span></span>

>[!NOTE]
><span data-ttu-id="6e80b-109">この記事は、Microsoft Edge version 81 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6e80b-109">This article applies to Microsoft Edge version 81 or later.</span></span>

## <span data-ttu-id="6e80b-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="6e80b-110">Prerequisites</span></span>

<span data-ttu-id="6e80b-111">このポリシーには、次の Windows 更新プログラムが必要です。</span><span class="sxs-lookup"><span data-stu-id="6e80b-111">The following Windows updates are required for this policy:</span></span>

- <span data-ttu-id="6e80b-112">Windows 10 Version 1909 と 1903、Windows Server Version 1909 と 1903 ([KB4532695](https://support.microsoft.com/help/4532695))</span><span class="sxs-lookup"><span data-stu-id="6e80b-112">Windows 10 version 1909 & 1903, Windows Server version 1909 & 1903  ([KB4532695](https://support.microsoft.com/help/4532695))</span></span>
- <span data-ttu-id="6e80b-113">Windows 10 Version 1809、Windows Server Version 1809、Windows Server 2019 ([KB4534321](https://support.microsoft.com/help/4534321))</span><span class="sxs-lookup"><span data-stu-id="6e80b-113">Windows 10 version 1809, Windows Server version 1809, Windows Server 2019 ([KB4534321](https://support.microsoft.com/help/4534321))</span></span>
- <span data-ttu-id="6e80b-114">Windows 10 Version 1803 ([KB4534308](https://support.microsoft.com/help/4534308))</span><span class="sxs-lookup"><span data-stu-id="6e80b-114">Windows 10 version 1803 ([KB4534308](https://support.microsoft.com/help/4534308))</span></span>
- <span data-ttu-id="6e80b-115">Windows 10 Version 1709 ([KB4534318](https://support.microsoft.com/help/4534318))</span><span class="sxs-lookup"><span data-stu-id="6e80b-115">Windows 10 version 1709 ([KB4534318](https://support.microsoft.com/help/4534318))</span></span>


## <span data-ttu-id="6e80b-116">このポリシーの詳細</span><span class="sxs-lookup"><span data-stu-id="6e80b-116">About this policy</span></span>

<span data-ttu-id="6e80b-117">このポリシーにより、IE モード サイトで使用されるすべての認証サーバーを識別して構成する時間が与えられます。</span><span class="sxs-lookup"><span data-stu-id="6e80b-117">This policy gives you time to identify and configure all of the authentication servers used by your IE mode sites.</span></span> <span data-ttu-id="6e80b-118">ただし、このポリシーを使用すると、一部のサイトが IE モードで表示されたり、Microsoft Edge モードで表示されたりする、一貫性のない閲覧エクスペリエンスが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e80b-118">However, this policy can result in an inconsistent browsing experience, where some sites are rendered in IE mode and at other times rendered in Microsoft Edge mode.</span></span> <span data-ttu-id="6e80b-119">このエクスペリエンスは、サイトへのナビゲーションが IE モード ページから開始されたかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6e80b-119">This experience depends on whether the navigation to the site began from an IE mode page.</span></span> <span data-ttu-id="6e80b-120">特定のレンダリング エンジンで開くように明示的に構成されていないサイトはすべて、この矛盾の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="6e80b-120">Any site that isn't explicitly configured to open in a specific rendering engine will be subject to this inconsistency.</span></span>

<span data-ttu-id="6e80b-121">このポリシーを有効にする場合は、すべての認証サーバーを識別し、それらをニュートラルとしてサイト リストに追加した後で、このポリシーを無効にすることを推奨します。</span><span class="sxs-lookup"><span data-stu-id="6e80b-121">If you enable this policy, we recommend that you disable it after you've identified all the authentication servers and added them to the site list as neutral.</span></span> <span data-ttu-id="6e80b-122">このアクションにより、最新のサイトが不注意に IE モードで表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="6e80b-122">This action ensures that your modern sites never inadvertently render in IE mode.</span></span>

## <span data-ttu-id="6e80b-123">IE モードでページ内ナビゲーションを保持する</span><span class="sxs-lookup"><span data-stu-id="6e80b-123">Keep in-page navigation in IE mode</span></span>

<span data-ttu-id="6e80b-124">Internet Explorer モードで、自動またはすべてのページ内ナビゲーションを保持するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6e80b-124">To keep automatic or all in-page navigation in Internet Explorer mode, follow these steps:</span></span>

1. <span data-ttu-id="6e80b-125">ローカル グループ ポリシー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e80b-125">Open Local Group Policy Editor.</span></span>
2. <span data-ttu-id="6e80b-126">**[コンピューターの構成]** > **[管理用テンプレート]** > **[Microsoft Edge]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e80b-126">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
3. <span data-ttu-id="6e80b-127">[**設定**] で、[**Internet Explorer モード ページから起動したときに未構成サイトへの「ページ内」ナビゲーションの動作を指定する**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e80b-127">Under **Setting**, double-click **Specify how "in-page" navigations to unconfigured sites behave when started from Internet Explorer mode pages**.</span></span>

   ![ページ内ポリシーの設定](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-settings.png)

4. <span data-ttu-id="6e80b-129">[**有効**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e80b-129">Select **Enabled**</span></span> 

   ![ページ内ポリシーを有効にする](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-enable.png)

5. <span data-ttu-id="6e80b-131">ドロップダウン リストから、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e80b-131">Choose one of the following options from the dropdown list:</span></span>

   - <span data-ttu-id="6e80b-132">**既定** - Internet Explorer モードで開くように構成されたサイトのみが、そのモードで開きます。</span><span class="sxs-lookup"><span data-stu-id="6e80b-132">**Default** - Only sites configured to open in Internet Explorer mode will open in that mode.</span></span> <span data-ttu-id="6e80b-133">Internet Explorer モードで開くように構成されていないサイトは、Microsoft Edge にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="6e80b-133">Any site not configured to open in Internet Explorer mode will be redirected back to Microsoft Edge.</span></span>
   - <span data-ttu-id="6e80b-134">**Internet Explorer モードで自動ナビゲーションのみを保持する** - 未構成サイトへのすべての自動ナビゲーション （302 リダイレクトなど） が Internet Explorer モードで保持されることを除いて、既定のエクスペリエンスが必要な場合は、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e80b-134">**Keep only automatic navigations in Internet Explorer mode** - Use this option if you want the default experience except that all automatic navigations (such as 302 redirects) to unconfigured sites will be kept in Internet Explorer mode.</span></span>
   - <span data-ttu-id="6e80b-135">**すべてのページ内ナビゲーションを Internet Explorer モードで保持する** ***(推奨しない)*** - IE モードで読み込まれたページから未構成サイトへのすべてのナビゲーションは、Internet Explorer モードで保持されます。</span><span class="sxs-lookup"><span data-stu-id="6e80b-135">**Keep all in-page navigation in Internet Explorer mode** ***(Least Recommended)*** - All navigations from pages loaded in IE mode to unconfigured sites are kept in Internet Explorer mode.</span></span>

6. <span data-ttu-id="6e80b-136">[**OK**] または [**適用**] をクリックして、このポリシー設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="6e80b-136">Click **OK** or **Apply** to save the policy settings.</span></span>

## <span data-ttu-id="6e80b-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e80b-137">See also</span></span>

- [<span data-ttu-id="6e80b-138">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="6e80b-138">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
