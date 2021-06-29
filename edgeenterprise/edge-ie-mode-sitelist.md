---
title: エンタープライズ サイト構成戦略
ms.author: shisub
author: shisub
manager: srugh
ms.date: 05/19/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Internet Explorer モード用にエンタープライズ モードのサイト リストを構成する方法をステップごとに説明しているガイドです。
ms.openlocfilehash: 7369e4e14f33fc37c6ded0ebc7df57d64a34df50
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617397"
---
# <a name="enterprise-site-configuration-strategy"></a><span data-ttu-id="273aa-103">エンタープライズ サイト構成戦略</span><span class="sxs-lookup"><span data-stu-id="273aa-103">Enterprise site configuration strategy</span></span>

>[!Note]
> <span data-ttu-id="273aa-104">Internet Explorer 11 デスクトップ アプリケーションは廃止され、2022 年 6 月 15 日にサポートが終了します (スコープ内の一覧については、[FAQ を参照してください](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549))。</span><span class="sxs-lookup"><span data-stu-id="273aa-104">The Internet Explorer 11 desktop application will be retired and go out of support on June 15, 2022 (for a list of what’s in scope, [see the FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span></span> <span data-ttu-id="273aa-105">現在使用しているものと同じ IE11 アプリとサイトを、Internet Explorer モードの Microsoft Edge で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="273aa-105">The same IE11 apps and sites you use today can open in Microsoft Edge with Internet Explorer mode.</span></span> <span data-ttu-id="273aa-106">[こちらをご覧ください](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。</span><span class="sxs-lookup"><span data-stu-id="273aa-106">[Learn more here](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span></span>

<span data-ttu-id="273aa-107">この記事では、Microsoft Edge バージョン 77 以降の Internet Explorer モードをサポートするエンタープライズ モード サイト リストの変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="273aa-107">This article describes changes to the Enterprise Mode Site List to support Internet Explorer mode for Microsoft Edge version 77 and later.</span></span>

<span data-ttu-id="273aa-108">エンタープライズ モード サイト リスト XML ファイルのスキーマについて詳しくは、[エンタープライズ モード スキーマ v.2 ガイダンス](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="273aa-108">For more information on the schema for the Enterprise Mode Site List XML file, see [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

> [!NOTE]
> <span data-ttu-id="273aa-109">この記事は Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="273aa-109">This article applies to Microsoft Edge version 77 or later.</span></span>
<!--
## Updated schema elements

The following table describes the \<open-in app\> element added to the v.2 of the Enterprise Mode schema:

| **Element** | **Description** |
| --- | --- |
| \<open-in app="**true**"\> | A child element that controls what browser is used for sites. This element is required for sites that need to **open in IE11**.|

**Example:**

``` xml
<site url="contoso.com">

  <open-in app="true">IE11</open-in>

</site>
```

The following table shows the possible values of the \<open-in\> element:

| **Value** | **Description** |
| --- | --- |
| **\<open-in\>IE11\</open-in\>** | Opens the site in IE mode or a full IE11 window. To enable IE mode, see [Configure IE mode policies](./edge-ie-mode-policies.md)|
| **\<open-in app="**true**"\>IE11\</open-in\>** | Opens the site in a full IE11 window |
| **\<open-in\>MSEdge\</open-in\>** | Opens the site in Microsoft Edge |
| **\<open-in\>None or not specified\</open-in\>** | Opens the site in the default browser or in the browser where the user navigated to the site. |
|**\<open-in\>Configurable\</open-in\>** | Allows the site to participate in IE mode engine determination. To learn more, see [Learn about Configurable sites in IE mode](edge-learnmore-configurable-sites-ie-mode.md).  |

>[!NOTE]
> The attribute app=**"true"** is only recognized when associated to _'open-in' IE11_. Adding it to the other 'open-in' elements won't change browser behavior.   -->

## <a name="configuration-strategy"></a><span data-ttu-id="273aa-110">構成戦略</span><span class="sxs-lookup"><span data-stu-id="273aa-110">Configuration strategy</span></span>

<span data-ttu-id="273aa-111">次の手順は、IE モードのサイト構成戦略の一部です。</span><span class="sxs-lookup"><span data-stu-id="273aa-111">The following steps are part of a site configuration strategy for IE mode:</span></span>
1. <span data-ttu-id="273aa-112">サイトの一覧を準備する</span><span class="sxs-lookup"><span data-stu-id="273aa-112">Prepare your site list</span></span>
2. <span data-ttu-id="273aa-113">ニュートラル サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="273aa-113">Configure neutral sites</span></span>
3. <span data-ttu-id="273aa-114">(省略可能) 必要に応じて Cookie の共有を使用する</span><span class="sxs-lookup"><span data-stu-id="273aa-114">(Optional) Use cookie sharing if necessary</span></span>

<!--
Step 1.  – if you don’t have one use Site Discovery Step-by-Step
Step 2 – Neutral sites + sticky mode
        Use more examples and explain sticky mode better
Step 3 – If that doesn’t cover your needs, then use Cookie sharing -->

## <a name="prepare-your-site-list"></a><span data-ttu-id="273aa-115">サイトの一覧を準備する</span><span class="sxs-lookup"><span data-stu-id="273aa-115">Prepare your site list</span></span>

<span data-ttu-id="273aa-116">IE11 または Microsoft Edge 従来版のエンタープライズ モード サイトリストを既にお持ちの場合は、IE モードを構成するためにそれを再利用できます。</span><span class="sxs-lookup"><span data-stu-id="273aa-116">If you already have an Enterprise Mode site list for IE11 or Microsoft Edge Legacy, you can reuse it to configure IE mode.</span></span>

<span data-ttu-id="273aa-117">ただし、サイトの一覧をお持ちでない場合は、 「[エンタープライズ サイト発見ツール](/deployedge/edge-ie-mode-site-discovery)」を使用してリストを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="273aa-117">However, if you don't have a site list, you can use the [Enterprise Site Discovery tool](/deployedge/edge-ie-mode-site-discovery) to populate your site list.</span></span>

## <a name="configure-neutral-sites"></a><span data-ttu-id="273aa-118">ニュートラル サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="273aa-118">Configure neutral sites</span></span>

<span data-ttu-id="273aa-119">IE モードを正しく動作させるには、認証サーバーまたはシングル サインオン (SSO) サーバーをニュートラル サイトとして明示的に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="273aa-119">In order for IE mode to work properly, authentication / Single Sign-On (SSO) servers will need to be explicitly configured as neutral sites.</span></span> <span data-ttu-id="273aa-120">構成しないと、IE モードのページが Microsoft Edge にリダイレクトされ、認証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="273aa-120">Otherwise, IE mode pages will try to redirect to Microsoft Edge, and authentication will fail.</span></span>

<span data-ttu-id="273aa-121">ニュートラル サイトは、ナビゲーションが開始されたブラウザーを使用します。これは Microsoft Edge または IE モードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="273aa-121">A neutral site will use the browser where the navigation started - either Microsoft Edge or IE mode.</span></span> <span data-ttu-id="273aa-122">ニュートラル サイトを構成すると、これらの最新および従来の両方の認証サーバーを使用するすべてのアプリケーションが引き続き動作します。</span><span class="sxs-lookup"><span data-stu-id="273aa-122">Configuring neutral sites ensures that all applications using these authentication servers, both modern and legacy, continue to work.</span></span>

<span data-ttu-id="273aa-123">Enterprise Mode Site List Manager ツールで [*開く*] ドロップダウンを [なし] に設定するか、サイト リスト XML を直接更新することによって、トラル サイトを構成できます。</span><span class="sxs-lookup"><span data-stu-id="273aa-123">You can configure neutral sites by setting the *Open In* dropdown to 'None' in the Enterprise Mode Site List Manager tool or by directly updating the site list XML:</span></span>

``` xml
<site url="login.contoso.com">
   
    <open-in>None</open-in>

</site>
```

<span data-ttu-id="273aa-124">認証サーバーを識別するには、IE11 開発者ツールを使用して、アプリケーションからのネットワーク トラフィックを調べます。</span><span class="sxs-lookup"><span data-stu-id="273aa-124">To identify authentication servers, inspect the network traffic from an application using the IE11 Developer Tools.</span></span> <span data-ttu-id="273aa-125">認証サーバーを識別するために時間を割く時間が必要な場合は、ユーザーがワークフローを中断することなく継続できるよう、IE モードですべてのページ内ナビゲーションを維持するポリシーを構成し、ユーザーがワークフローを中断することなく続行できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="273aa-125">If you need more time to identify your authentication servers, you can configure a policy to keep all in-page navigations in IE mode to allow your users to continue their workflows uninterrupted.</span></span> <span data-ttu-id="273aa-126">不要な場合に IE モードの使用を最小限に抑えるには、認証サーバーを識別してサイト リストに追加したら、この設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="273aa-126">To minimize the use of IE mode when unnecessary, disable this setting once you've identified and added your authentication servers to the site list.</span></span> <span data-ttu-id="273aa-127">詳しくは、「[IE モードでページ内ナビゲーションを保持する](/deployedge/edge-learnmore-inpage-nav)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="273aa-127">For more information, see [Keep in-page navigation in IE mode](/deployedge/edge-learnmore-inpage-nav).</span></span>

>[!NOTE]
   ><span data-ttu-id="273aa-128">IE モード統合では、エンタープライズ モード スキーマ v.1 がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="273aa-128">Enterprise Mode schema v.1 isn't supported for IE mode integration.</span></span> <span data-ttu-id="273aa-129">現在、Internet Explorer 11 でスキーマ v.1 を使用している場合は、スキーマ v.2 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="273aa-129">If you are currently using schema v.1 with Internet Explorer 11, you must upgrade to schema v.2.</span></span> <span data-ttu-id="273aa-130">詳しくは、「[エンタープライズ モード スキーマ v.2 ガイダンス](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="273aa-130">For more information, see [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

## <a name="optional-use-cookie-sharing-if-necessary"></a><span data-ttu-id="273aa-131">(省略可能) 必要に応じて Cookie の共有を使用する</span><span class="sxs-lookup"><span data-stu-id="273aa-131">(Optional) Use cookie sharing if necessary</span></span>

<span data-ttu-id="273aa-132">既定では、Microsoft Edge や Internet Explorer のプロセスはセッション Cookie を共有しません。この共有の欠如は、IE モードの使用時に、場合によっては不便になってしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="273aa-132">By default, the Microsoft Edge and Internet Explorer processes don't share session cookies, and this lack of sharing can be inconvenient in some cases while using IE mode.</span></span> <span data-ttu-id="273aa-133">たとえば、ユーザーが以前に IE モードで再認証する必要がある場合、または Microsoft Edge セッションからサインアウトしても、重要なトランザクションのために Internet Explorer モード セッションからサイン アウトしない場合があります。</span><span class="sxs-lookup"><span data-stu-id="273aa-133">For example, when a user has to reauthenticate in IE mode when previously they are accustomed to doing so or when signing out of a Microsoft Edge session doesn’t sign out of the Internet Explorer mode session for critical transactions.</span></span> <span data-ttu-id="273aa-134">これらのシナリオでは、SSO によって設定された特定の Cookie が Microsoft Edge から Internet Explorer へと送信されるように構成することで、再認証の必要性を排除し、認証エクスペリエンスをよりシームレスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="273aa-134">In these scenarios, you can configure specific cookies set by SSO to be sent from Microsoft Edge to Internet Explorer so the authentication experience becomes more seamless by eliminating the need to reauthenticate.</span></span> <span data-ttu-id="273aa-135">詳しくは、「[Microsoft Edge から Internet Explorer に Cookie を共有する](/deployedge/edge-ie-mode-add-guidance-cookieshare)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="273aa-135">For more information, see [Cookie sharing from Microsoft Edge to Internet Explorer](/deployedge/edge-ie-mode-add-guidance-cookieshare).</span></span>

## <a name="see-also"></a><span data-ttu-id="273aa-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="273aa-136">See also</span></span>

- [<span data-ttu-id="273aa-137">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="273aa-137">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="273aa-138">IE モードの概要</span><span class="sxs-lookup"><span data-stu-id="273aa-138">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="273aa-139">その他のエンタープライズ モード情報</span><span class="sxs-lookup"><span data-stu-id="273aa-139">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
