---
title: エンタープライズ モード サイト リストでのサイトの構成
ms.author: cjacks
author: cjacks
manager: saudm
ms.date: 05/28/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: エンタープライズ サイト リストの構成
ms.openlocfilehash: 9b1943e4d50dcc770b4a634b99ecbd001d1ffbcc
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447651"
---
# <a name="configure-sites-on-the-enterprise-mode-site-list"></a><span data-ttu-id="1dd24-103">エンタープライズ モード サイト リストでのサイトの構成</span><span class="sxs-lookup"><span data-stu-id="1dd24-103">Configure Sites on the Enterprise Mode Site List</span></span>

<span data-ttu-id="1dd24-104">この記事では、Microsoft Edge バージョン 77 以降の IE モードの構成をサポートするエンタープライズ モード サイト リストの変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="1dd24-104">This article describes changes to the Enterprise Mode Site List that support configuring IE mode for Microsoft Edge version 77 and later.</span></span>

<span data-ttu-id="1dd24-105">エンタープライズ モード サイト リスト XML ファイルのスキーマについて詳しくは、[エンタープライズ モード スキーマ v.2 ガイダンス](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1dd24-105">For more information on the schema for the Enterprise Mode Site List XML file, see [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

> [!NOTE]
> <span data-ttu-id="1dd24-106">この記事は、Microsoft Edge version 77 (**Stable**、**Beta**、および **Dev** チャネル) 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1dd24-106">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>

## <a name="updated-schema-elements"></a><span data-ttu-id="1dd24-107">更新されたスキーマ要素</span><span class="sxs-lookup"><span data-stu-id="1dd24-107">Updated schema elements</span></span>

<span data-ttu-id="1dd24-108">次の表は、エンタープライズ モード スキーマ v.2 に追加された \<open-in app\> 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="1dd24-108">The following table describes the \<open-in app\> element added to the v.2 of the Enterprise Mode schema:</span></span>

| **<span data-ttu-id="1dd24-109">要素</span><span class="sxs-lookup"><span data-stu-id="1dd24-109">Element</span></span>** | **<span data-ttu-id="1dd24-110">説明</span><span class="sxs-lookup"><span data-stu-id="1dd24-110">Description</span></span>** |
| --- | --- |
| \<open-in app="**true**"\> | <span data-ttu-id="1dd24-111">サイトに使われるブラウザーの種類を制御する子要素。</span><span class="sxs-lookup"><span data-stu-id="1dd24-111">A child element that controls what browser is used for sites.</span></span> <span data-ttu-id="1dd24-112">**IE11 で開く**必要があるサイトには、この要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="1dd24-112">This element is required for sites that need to **open in IE11**.</span></span>|

**<span data-ttu-id="1dd24-113">例:</span><span class="sxs-lookup"><span data-stu-id="1dd24-113">Example:</span></span>**

``` xml
<site url="contoso.com">

  <open-in app="true">IE11</open-in>

</site>
```

<span data-ttu-id="1dd24-114">次の表は、\<open-in\> 要素の有効値を示しています。</span><span class="sxs-lookup"><span data-stu-id="1dd24-114">The following table shows the possible values of the \<open-in\> element:</span></span>

| **<span data-ttu-id="1dd24-115">値</span><span class="sxs-lookup"><span data-stu-id="1dd24-115">Value</span></span>** | **<span data-ttu-id="1dd24-116">説明</span><span class="sxs-lookup"><span data-stu-id="1dd24-116">Description</span></span>** |
| --- | --- |
| **\<open-in\><span data-ttu-id="1dd24-117">IE11</span><span class="sxs-lookup"><span data-stu-id="1dd24-117">IE11</span></span>\</open-in\>** | <span data-ttu-id="1dd24-118">IE モードまたはフル IE11 ウィンドウでサイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="1dd24-118">Opens the site in IE mode or a full IE11 window.</span></span> <span data-ttu-id="1dd24-119">IE モードを有効にするには、「[IE モード ポリシーの構成](./edge-ie-mode-policies.md)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="1dd24-119">To enable IE mode, see [Configure IE mode policies](./edge-ie-mode-policies.md)</span></span>|
| **\<open-in app="**true**"\><span data-ttu-id="1dd24-120">IE11</span><span class="sxs-lookup"><span data-stu-id="1dd24-120">IE11</span></span>\</open-in\>** | <span data-ttu-id="1dd24-121">フル IE11 ウィンドウでサイトを開きます</span><span class="sxs-lookup"><span data-stu-id="1dd24-121">Opens the site in a full IE11 window</span></span> |
| **\<open-in\><span data-ttu-id="1dd24-122">MSEdge</span><span class="sxs-lookup"><span data-stu-id="1dd24-122">MSEdge</span></span>\</open-in\>** | <span data-ttu-id="1dd24-123">Microsoft Edge でサイトを開きます</span><span class="sxs-lookup"><span data-stu-id="1dd24-123">Opens the site in Microsoft Edge</span></span> |
| **\<open-in\><span data-ttu-id="1dd24-124">none または未指定</span><span class="sxs-lookup"><span data-stu-id="1dd24-124">None or not specified</span></span>\</open-in\>** | <span data-ttu-id="1dd24-125">既定のブラウザー、またはサイトに移動したブラウザーでサイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="1dd24-125">Opens the site in the default browser or in the browser where the user navigated to the site.</span></span> |
|**\<open-in\><span data-ttu-id="1dd24-126">構成可能</span><span class="sxs-lookup"><span data-stu-id="1dd24-126">Configurable</span></span>\</open-in\>** | <span data-ttu-id="1dd24-127">サイトが IE モード エンジンの決定に参加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1dd24-127">Allows the site to participate in IE mode engine determination.</span></span> <span data-ttu-id="1dd24-128">詳細については、「[IE モードで構成可能なサイトの詳細](edge-learnmore-configurable-sites-ie-mode.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dd24-128">To learn more, see [Learn about Configurable sites in IE mode](edge-learnmore-configurable-sites-ie-mode.md).</span></span>  |

>[!NOTE]
> <span data-ttu-id="1dd24-129">属性 app=**"true"** が認識されるのは、_'open-in' IE11_ に関連付けられている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="1dd24-129">The attribute app=**"true"** is only recognized when associated to _'open-in' IE11_.</span></span> <span data-ttu-id="1dd24-130">他の 'open-in' 要素に追加しても、ブラウザーの動作は変わりません。</span><span class="sxs-lookup"><span data-stu-id="1dd24-130">Adding it to the other 'open-in' elements won't change browser behavior.</span></span>   

## <a name="configure-neutral-sites"></a><span data-ttu-id="1dd24-131">ニュートラル サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="1dd24-131">Configure neutral sites</span></span>

<span data-ttu-id="1dd24-132">IE モードを正しく動作させるには、認証サーバーまたはシングル サインオン サーバーをニュートラル サイトとして明示的に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dd24-132">In order for IE mode to work properly, authentication / Single Sign-On servers will need to be explicitly configured as neutral sites.</span></span> <span data-ttu-id="1dd24-133">構成しないと、IE モードのページが Microsoft Edge にリダイレクトされ、認証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="1dd24-133">Otherwise, IE mode pages will try to redirect to Microsoft Edge, and authentication will fail.</span></span>

<span data-ttu-id="1dd24-134">ニュートラル サイトは、ナビゲーションが開始されたブラウザーを使用します。これは Microsoft Edge または IE モードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="1dd24-134">A neutral site will use the browser where the navigation started - either Microsoft Edge or IE mode.</span></span> <span data-ttu-id="1dd24-135">ニュートラル サイトを構成すると、これらの最新および従来の両方の認証サーバーを使用するすべてのアプリケーションが引き続き動作します。</span><span class="sxs-lookup"><span data-stu-id="1dd24-135">Configuring neutral sites ensures that all applications using these authentication servers, both modern and legacy, continue to work.</span></span>

<span data-ttu-id="1dd24-136">Enterprise Mode Site List Manager ツールで [*開く*] ドロップダウンを [なし] に設定するか、サイト リスト XML を直接更新することによって、トラル サイトを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1dd24-136">You can configure neutral sites by setting the *Open In* dropdown to 'None' in the Enterprise Mode Site List Manager tool or by directly updating the site list XML:</span></span>

``` xml
<site url="login.contoso.com">
   
    <open-in>None</open-in>

</site>
```

<span data-ttu-id="1dd24-137">認証サーバーを識別するには、IE11 開発者ツールを使用して、アプリケーションからのネットワーク トラフィックを調べます。</span><span class="sxs-lookup"><span data-stu-id="1dd24-137">To identify authentication servers, inspect the network traffic from an application using the IE11 Developer Tools.</span></span> <span data-ttu-id="1dd24-138">認証サーバーの識別にさらに時間が必要な場合は、ページ内ナビゲーションがすべて IE モードのままになるようにポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1dd24-138">If you need more time to identify your authentication servers, you can configure a policy to keep all in-page navigation in IE mode.</span></span> <span data-ttu-id="1dd24-139">IE モードの使用を最小限に抑えるには、認証サーバーを識別してサイト リストに追加したら、この設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="1dd24-139">To minimize the use of IE mode, disable this setting once you've identified and added your authentication servers to the site list.</span></span> <span data-ttu-id="1dd24-140">詳細については、[ページ内ナビゲーションがすべて IE モードのままになるように構成する方法](./microsoft-edge-policies.md#internetexplorerintegrationsiteredirect)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1dd24-140">For more information, see [Configure in-page navigation to remain in IE mode](./microsoft-edge-policies.md#internetexplorerintegrationsiteredirect).</span></span>

>[!NOTE]
   ><span data-ttu-id="1dd24-141">IE モード統合では、エンタープライズ モード スキーマ v.1 がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1dd24-141">Enterprise Mode schema v.1 isn't supported for IE mode integration.</span></span> <span data-ttu-id="1dd24-142">現在、Internet Explorer 11 でスキーマ v.1 を使用している場合は、スキーマ v.2 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dd24-142">If you are currently using schema v.1 with Internet Explorer 11, you must upgrade to schema v.2.</span></span> <span data-ttu-id="1dd24-143">詳しくは、「[エンタープライズ モード スキーマ v.2 ガイダンス](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1dd24-143">For more information, see [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

## <a name="see-also"></a><span data-ttu-id="1dd24-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dd24-144">See also</span></span>

- [<span data-ttu-id="1dd24-145">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="1dd24-145">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="1dd24-146">IE モードの概要</span><span class="sxs-lookup"><span data-stu-id="1dd24-146">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="1dd24-147">その他のエンタープライズ モード情報</span><span class="sxs-lookup"><span data-stu-id="1dd24-147">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)