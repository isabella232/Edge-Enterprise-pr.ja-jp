---
title: Microsoft Edge と IE モードで構成可能なサイト
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 05/28/2020
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge と IE モードで構成可能なサイト
ms.openlocfilehash: 1bffdef8c88b7a83d999b29763fcca258102ed51
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447331"
---
# <a name="learn-about-configurable-sites-in-ie-mode"></a><span data-ttu-id="ee6e6-103">IE モードで構成可能なサイトについて学ぶ</span><span class="sxs-lookup"><span data-stu-id="ee6e6-103">Learn about Configurable sites in IE mode</span></span>

<span data-ttu-id="ee6e6-104">この記事では、Microsoft Edge で IE モードを使用する場合のエンタープライズモードサイトリストの構成可能サイト機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-104">This article explains the Configurable sites feature of the Enterprise Mode Site List when using IE mode in Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ee6e6-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="ee6e6-105">Prerequisites</span></span>

- <span data-ttu-id="ee6e6-106">Windows 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="ee6e6-106">Windows updates</span></span>

  - <span data-ttu-id="ee6e6-107">Windows 10 バージョン 1909, Windows server バージョン 1909 – KB4550945 以降</span><span class="sxs-lookup"><span data-stu-id="ee6e6-107">Windows 10 version 1909, Windows server version 1909 – KB4550945  or higher</span></span>
  - <span data-ttu-id="ee6e6-108">Windows 10 バージョン 1903, Windows server バージョン 1903 – KB4550945 以降</span><span class="sxs-lookup"><span data-stu-id="ee6e6-108">Windows 10 version 1903, Windows server version 1903 – KB4550945  or higher</span></span>
  - <span data-ttu-id="ee6e6-109">Windows 10 version 1809, Windows Server version 1809, Windows Server 2019 - KB4550969 以降</span><span class="sxs-lookup"><span data-stu-id="ee6e6-109">Windows 10 version 1809, Windows Server version 1809, and Windows Server 2019 - KB4550969 or higher</span></span>
  - <span data-ttu-id="ee6e6-110">Windows 10 version 1803 – KB4550944 以降</span><span class="sxs-lookup"><span data-stu-id="ee6e6-110">Windows 10 version 1803 – KB4550944 or higher</span></span>
  - <span data-ttu-id="ee6e6-111">Windows 10 version 1607, Windows Server 2016 - KB4556826 以降</span><span class="sxs-lookup"><span data-stu-id="ee6e6-111">Windows 10 version 1607, Windows Server 2016 - KB4556826 or higher</span></span>
  - <span data-ttu-id="ee6e6-112">Windows 10 初期バージョン, July 2015 - KB4550947 以降</span><span class="sxs-lookup"><span data-stu-id="ee6e6-112">Windows 10 initial version, July 2015 - KB4550947 or higher</span></span>
  - <span data-ttu-id="ee6e6-113">Windows 8.1 – KB4556798 以降</span><span class="sxs-lookup"><span data-stu-id="ee6e6-113">Windows 8.1 – KB4556798 or higher</span></span>

- <span data-ttu-id="ee6e6-114">Microsoft Edge version 83 以降</span><span class="sxs-lookup"><span data-stu-id="ee6e6-114">Microsoft Edge version 83 or later</span></span>
- <span data-ttu-id="ee6e6-115">エンタープライズモードサイトリストで構成された [IEモード](./edge-ie-mode.md)</span><span class="sxs-lookup"><span data-stu-id="ee6e6-115">[IE mode](./edge-ie-mode.md) configured with Enterprise Mode Site List</span></span>

## <a name="overview"></a><span data-ttu-id="ee6e6-116">概要</span><span class="sxs-lookup"><span data-stu-id="ee6e6-116">Overview</span></span>

<span data-ttu-id="ee6e6-117">エンタープライズモードサイトリストで IE モードを必要とするサイトを構成すると、レガシーアプリケーションを使用するほとんどの環境で問題なく機能します。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-117">Configuring sites needing IE mode in the Enterprise Mode Site List will work well for most environments with legacy applications.</span></span> <span data-ttu-id="ee6e6-118">ただし、このアプローチが、IEモードでドメイン全体をレンダリングせずに、IEモードで開くようにサイトのサブセットを構成するのに最適ではない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-118">However, in some cases this approach isn't the best to configure a subset of sites to open in IE mode without rendering an entire domain in IE mode.</span></span> <span data-ttu-id="ee6e6-119">例えば、ご自分の環境に単一のサーバーで実行されている最新のアプリケーションとレガシーアプリケーションの両方が含まれている場合や、IE モードでレガシーアプリケーションのみをレンダリングし、残りのアプリケーションを Microsoft Edge モードでレンダリングする柔軟性がご希望の場合です。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-119">For example, when your environment contains both modern and legacy applications running on a single server and you would like the flexibility to render only the legacy applications in IE mode and the remaining applications to render in Microsoft Edge mode.</span></span>

<span data-ttu-id="ee6e6-120">解決策は、[エンタープライズモードサイトリスト] の [構成可能なサイト] 機能を使用することです。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-120">The solution is to use the Configurable sites feature of the Enterprise Mode Site List.</span></span> <span data-ttu-id="ee6e6-121">この機能が有効になっている場合、Microsoft Edge は、「構成可能」タグが付いたサイトがIEモードエンジンの決定に参加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-121">When the feature is enabled, Microsoft Edge will allow sites with the "configurable" tag to participate in IE mode engine determination.</span></span>

## <a name="how-configurable-sites-works"></a><span data-ttu-id="ee6e6-122">構成可能なサイトの仕組み</span><span class="sxs-lookup"><span data-stu-id="ee6e6-122">How Configurable sites works</span></span>

### <a name="automatic-switching-from-the-microsoft-edge-engine-to-the-ie-mode-engine"></a><span data-ttu-id="ee6e6-123">Microsoft Edge エンジンから IE モードエンジンへの自動切り替え</span><span class="sxs-lookup"><span data-stu-id="ee6e6-123">Automatic switching from the Microsoft Edge engine to the IE mode engine</span></span>

<span data-ttu-id="ee6e6-124">[構成可能なサイト] 機能を使用するには、エンタープライズオプションサイトリストで 1 つ以上のサイトが `<open-in>Configurable</open-in>` オプションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-124">To use the Configurable sites feature, you'll need one or more sites in the Enterprise Mode Site List to have the `<open-in>Configurable</open-in>` option.</span></span>

<span data-ttu-id="ee6e6-125">例:</span><span class="sxs-lookup"><span data-stu-id="ee6e6-125">Example:</span></span>

```
<site-list version="1">
  <site url="app.com">
    <open-in>Configurable</open-in>
  </site>
</site-list>
```

<span data-ttu-id="ee6e6-126">構成可能なサイト機能を有効にすると、次の動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-126">When the Configurable sites feature is enabled, the following behavior occurs:</span></span>

1. <span data-ttu-id="ee6e6-127">設定可能なサイトにリクエストを送信するとき、Microsoft Edge は HTTP 要求ヘッダー"`X-InternetExplorerModeConfigurable: 1`"を送信します。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-127">When making a request to a Configurable site, Microsoft Edge will send the HTTP request header "`X-InternetExplorerModeConfigurable: 1`".</span></span>
2. <span data-ttu-id="ee6e6-128">構成可能なサイトは、Microsoft Edge がサイトを IE モードでロードすることを要求するために、HTTP 応答ヘッダー "`X-InternetExplorerMode: 1`"を含むリダイレクト応答（HTTP 302 など）を送信する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-128">A Configurable site may send a redirect response (for example, HTTP 302) with the HTTP response header "`X-InternetExplorerMode: 1`" to request that Microsoft Edge loads the site in IE mode.</span></span>
3. <span data-ttu-id="ee6e6-129">リダイレクトのターゲット（つまり、**ロケーション**応答ヘッダーの値）も**構成可能**サイトまたは**中立**サイトである必要があります。そうでない場合、IEモード応答ヘッダーは無視されます。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-129">The target of the redirect (that is, the value of the **Location** response header) must also be a **Configurable** or **Neutral** site, otherwise the IE mode response header will be ignored.</span></span> <span data-ttu-id="ee6e6-130">リダイレクトのターゲットは通常、元のURLと同じであると予想されます。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-130">It's expected that the target of the redirect will usually be the same as the original URL.</span></span> <span data-ttu-id="ee6e6-131">ただし、必ずしもそうである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-131">However, it doesn't have to be.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ee6e6-132">リダイレクト応答は、リダイレクトに対する Microsoft Edge の通常の HTTP キャッシング動作に従ってキャッシングされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-132">The redirect response is subject to caching according to Microsoft Edge's normal HTTP caching behavior for redirects.</span></span>

### <a name="switching-back-from-ie-mode-engine-to-microsoft-edge-engine"></a><span data-ttu-id="ee6e6-133">IE モードエンジンから Microsoft Edge エンジンに戻す</span><span class="sxs-lookup"><span data-stu-id="ee6e6-133">Switching back from IE mode engine to Microsoft Edge engine</span></span>

<span data-ttu-id="ee6e6-134">Microsoft Edge で構成可能なサイトを有効にすると、IE モードのタブで次の動作が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-134">Enabling Configurable sites in Microsoft Edge automatically enables the following behaviors in IE mode tabs:</span></span>

1. <span data-ttu-id="ee6e6-135">設定可能なサイトへのリクエストを行う場合、IE モードのタブは、Microsoft Edge のタブと同じように、HTTP 要求ヘッダー "`X-InternetExplorerModeConfigurable: 1`" を送信します。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-135">When making a request to a Configurable site, IE mode tabs will send the HTTP request header "`X-InternetExplorerModeConfigurable: 1`", the same as Microsoft Edge tabs.</span></span>
2. <span data-ttu-id="ee6e6-136">構成可能なサイトは、HTTP 応答ヘッダー "`X-InternetExplorerMode: 0`"を含むリダイレクト応答（HTTP 302など）を送信して、ナビゲーションが Microsoft Edge モードに戻るよう要求する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-136">A Configurable site might send a redirect response (for example, HTTP 302) with the HTTP response header "`X-InternetExplorerMode: 0`" to request that the navigation switch back to Microsoft Edge mode.</span></span>
3. <span data-ttu-id="ee6e6-137">リダイレクトのターゲット（つまり、**ロケーション**応答ヘッダーの値）も**構成可能**サイトまたは**中立**サイトである必要があります。そうでない場合、IEモード応答ヘッダーは無視されます。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-137">The target of the redirect (that is, the value of the **Location** response header) must also be a **Configurable** or **Neutral** site, otherwise the IE mode response header will be ignored.</span></span> <span data-ttu-id="ee6e6-138">リダイレクトのターゲットは通常、元のURLと同じであると予想されます。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-138">It's expected that the target of the redirect will usually be the same as the original URL.</span></span> <span data-ttu-id="ee6e6-139">ただし、必ずしもそうである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-139">However, it doesn't have to be.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ee6e6-140">リダイレクト応答は、リダイレクトに対する Microsoft Edge の通常の HTTP キャッシング動作に従ってキャッシングされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-140">The redirect response is subject to caching according to Microsoft Edge's normal HTTP caching behavior for redirects.</span></span>

> [!TIP]
> <span data-ttu-id="ee6e6-141">どちらのブラウザーエンジンも、構成可能なサイトに同じ "`X-InternetExplorerModeConfigurable: 1`" 要求ヘッダーを送信します。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-141">Both browser engines send the same "`X-InternetExplorerModeConfigurable: 1`" request header to Configurable sites.</span></span> <span data-ttu-id="ee6e6-142">ユーザーエージェント要求ヘッダーを使用して、Microsoft Edge モードからのリクエストと IE モードからのリクエストを区別し、サイトがすでに正しいエンジンに読み込まれているときにリダイレクトされないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee6e6-142">You should use the User-Agent request header to distinguish between requests from Microsoft Edge mode vs. IE mode to avoid redirecting when the site is already loading in the correct engine.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee6e6-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee6e6-143">See also</span></span>

- [<span data-ttu-id="ee6e6-144">IE モードの概要</span><span class="sxs-lookup"><span data-stu-id="ee6e6-144">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="ee6e6-145">その他のエンタープライズ モード情報</span><span class="sxs-lookup"><span data-stu-id="ee6e6-145">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="ee6e6-146">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="ee6e6-146">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)