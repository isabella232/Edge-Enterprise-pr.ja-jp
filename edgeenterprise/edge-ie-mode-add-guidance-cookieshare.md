---
title: Microsoft Edge から Internet Explorer への Cookie の共有
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 'Microsoft Edge から Internet Explorer へと Cookie を共有する方法 '
ms.openlocfilehash: 8f1a38106e49f71aa9d27f32cfecbd0df44eaf9f
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641843"
---
# <a name="cookie-sharing-from-microsoft-edge-to-internet-explorer"></a><span data-ttu-id="36c48-103">Microsoft Edge から Internet Explorer への Cookie の共有</span><span class="sxs-lookup"><span data-stu-id="36c48-103">Cookie sharing from Microsoft Edge to Internet Explorer</span></span>

>[!Note]
> <span data-ttu-id="36c48-104">Internet Explorer 11 デスクトップ アプリケーションは廃止され、2022 年 6 月 15 日にサポートが終了します (スコープ内の一覧については、[FAQ を参照してください](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549))。</span><span class="sxs-lookup"><span data-stu-id="36c48-104">The Internet Explorer 11 desktop application will be retired and go out of support on June 15, 2022 (for a list of what’s in scope, [see the FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span></span> <span data-ttu-id="36c48-105">現在使用しているものと同じ IE11 アプリとサイトを、Internet Explorer モードの Microsoft Edge で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="36c48-105">The same IE11 apps and sites you use today can open in Microsoft Edge with Internet Explorer mode.</span></span> <span data-ttu-id="36c48-106">[こちらをご覧ください](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。</span><span class="sxs-lookup"><span data-stu-id="36c48-106">[Learn more here](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span></span>

<span data-ttu-id="36c48-107">この記事では、Internet Explorer モードの使用中に、Microsoft Edge プロセスから Internet Explorer プロセスへのセッション Cookie の共有を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="36c48-107">This article explains explains how to configure session cookie sharing from a Microsoft Edge process to Internet Explorer process, while using Internet Explorer mode.</span></span>

> [!NOTE]
> <span data-ttu-id="36c48-108">この記事は Microsoft Edge version 87 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="36c48-108">This article applies to Microsoft Edge version 87 or later.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36c48-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="36c48-109">Prerequisites</span></span>

- <span data-ttu-id="36c48-110">Windows 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="36c48-110">Windows updates</span></span>

  - <span data-ttu-id="36c48-111">Windows 10 バージョン 2004、Windows Server バージョン 2004 - KB4571744 以上</span><span class="sxs-lookup"><span data-stu-id="36c48-111">Windows 10 version 2004, Windows Server version 2004 - KB4571744 or higher</span></span>
  - <span data-ttu-id="36c48-112">Windows 10 バージョン 1909、Windows Server バージョン 1909 – KB4566116 以上</span><span class="sxs-lookup"><span data-stu-id="36c48-112">Windows 10 version 1909, Windows Server version 1909 – KB4566116 or higher</span></span>
  - <span data-ttu-id="36c48-113">Windows 10 バージョン 1903、Windows Server バージョン 1903 – KB4566116 以上</span><span class="sxs-lookup"><span data-stu-id="36c48-113">Windows 10 version 1903, Windows Server version 1903 – KB4566116 or higher</span></span>
  - <span data-ttu-id="36c48-114">Windows 10 バージョン 1809、Windows Server バージョン 1809、および Windows Server 2019 - KB4571748 以降</span><span class="sxs-lookup"><span data-stu-id="36c48-114">Windows 10 version 1809, Windows Server version 1809, and Windows Server 2019 - KB4571748 or higher</span></span>
  - <span data-ttu-id="36c48-115">Windows 10 バージョン 1803 – KB4577032 以降</span><span class="sxs-lookup"><span data-stu-id="36c48-115">Windows 10 version 1803 – KB4577032 or higher</span></span>

- <span data-ttu-id="36c48-116">Microsoft Edge バージョン 87 以降</span><span class="sxs-lookup"><span data-stu-id="36c48-116">Microsoft Edge version 87 or later</span></span>
- <span data-ttu-id="36c48-117">エンタープライズ モード サイト一覧を使用して構成された [IE モード](./edge-ie-mode.md) </span><span class="sxs-lookup"><span data-stu-id="36c48-117">[IE mode](./edge-ie-mode.md) configured with Enterprise Mode Site List</span></span>

## <a name="overview"></a><span data-ttu-id="36c48-118">概要</span><span class="sxs-lookup"><span data-stu-id="36c48-118">Overview</span></span>

<span data-ttu-id="36c48-119">大規模な組織では、最新のブラウザー上で動作するアプリケーションを、ワークフローの一部としてシングル サインオン (SSO) を有効にした状態で Internet Explorer モードで開くように構成されている可能性のある別のアプリケーションにリンクさせることが一般的です。</span><span class="sxs-lookup"><span data-stu-id="36c48-119">A common configuration in large organizations is to have an application that works on a modern browser link to another application, which might be configured to open in Internet Explorer mode with Single Sign On (SSO) enabled as part of the workflow.</span></span>

<span data-ttu-id="36c48-120">既定では、Microsoft Edge や Internet Explorer のプロセスはセッション Cookie を共有しないため、場合によっては不便になってしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="36c48-120">By default, the Microsoft Edge and Internet Explorer processes don't share session cookies, and this can be inconvenient in some cases.</span></span> <span data-ttu-id="36c48-121">たとえば、Internet Explorer モードでユーザーの再認証が必要な場合や、Microsoft Edge のセッションからサインアウトしても、Internet Explorer モードのセッションからはサインアウトしない場合などです。</span><span class="sxs-lookup"><span data-stu-id="36c48-121">For example, when a user has to re-authenticate in Internet Explorer mode or when signing out of an Microsoft Edge session doesn’t sign out of the Internet Explorer mode session.</span></span> <span data-ttu-id="36c48-122">これらのシナリオでは、SSO によって設定された特定の Cookie が Microsoft Edge から Internet Explorer へと送信されるように構成することで、再認証の必要性を排除し、認証エクスペリエンスをよりシームレスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="36c48-122">In these scenarios, you can configure specific cookies set by SSO to be sent from Microsoft Edge to Internet Explorer so the authentication experience becomes more seamless by eliminating the need to re-authenticate.</span></span>

> [!NOTE]
> <span data-ttu-id="36c48-123">セッション Cookie は、Microsoft Edge から Internet Explorer にのみ共有することができます。</span><span class="sxs-lookup"><span data-stu-id="36c48-123">Session cookies can only be shared from Microsoft Edge to Internet Explorer.</span></span> <span data-ttu-id="36c48-124">セッション Cookie を逆方向へ (Internet Explorer から Microsoft Edge へと) 共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="36c48-124">Sharing session cookies in reverse (from Internet Explorer to Microsoft Edge) isn't possible.</span></span>

## <a name="how-cookie-sharing-works"></a><span data-ttu-id="36c48-125">Cookie の共有のしくみ</span><span class="sxs-lookup"><span data-stu-id="36c48-125">How cookie sharing works</span></span>

<span data-ttu-id="36c48-126">エンタープライズ モード サイト一覧の XML が拡張され、Microsoft Edge のセッションから Internet Explorer と共有する必要のある Cookie を指定する要素が追加できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="36c48-126">The Enterprise Mode site list XML has been extended to allow additional elements to specify cookies that need to be shared from a Microsoft Edge session with Internet Explorer.</span></span>  

<span data-ttu-id="36c48-127">Microsoft Edge のセッションで初めての Internet Explorer モードのタブが作成されると、一致するすべての Cookie が Internet Explorer のセッションへと共有されます。</span><span class="sxs-lookup"><span data-stu-id="36c48-127">The first time an Internet Explorer mode tab is created in a Microsoft Edge session, all matching cookies are shared to the Internet Explorer session.</span></span> <span data-ttu-id="36c48-128">その後は、ルールに一致する Cookie が追加、削除、修正されるたびに、Internet Explorer のセッションに対する更新として送信されます。</span><span class="sxs-lookup"><span data-stu-id="36c48-128">Subsequently, any time a cookie that matches a rule is added, deleted, or modified it is sent as an update to the Internet Explorer session.</span></span> <span data-ttu-id="36c48-129">また、サイト一覧が更新されると、共有 Cookie のセットも再評価されます。</span><span class="sxs-lookup"><span data-stu-id="36c48-129">The set of shared cookies is also re-evaluated when the site list is updated.</span></span>

### <a name="updated-schema-elements"></a><span data-ttu-id="36c48-130">更新されたスキーマ要素</span><span class="sxs-lookup"><span data-stu-id="36c48-130">Updated schema elements</span></span>

<span data-ttu-id="36c48-131">以下の表では、Cookie の共有機能をサポートするために追加された \<shared-cookie\> 要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="36c48-131">The following table describes the \<shared-cookie\> element added to support the cookie sharing feature.</span></span>

| <span data-ttu-id="36c48-132">要素</span><span class="sxs-lookup"><span data-stu-id="36c48-132">Element</span></span>| <span data-ttu-id="36c48-133">説明</span><span class="sxs-lookup"><span data-stu-id="36c48-133">Description</span></span> |
|-|-|
| \<shared-cookie **domain**=".contoso.com" **name**="cookie1"\>\</shared-cookie\><br><br><span data-ttu-id="36c48-134">または</span><span class="sxs-lookup"><span data-stu-id="36c48-134">OR</span></span><br><br>\<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2"\>\</shared-cookie\>   |<span data-ttu-id="36c48-135">**(必須)** \<shared-cookie\> 要素には、最低でも*ドメイン* (ドメイン Cookie の場合) または *host* (ホストオンリー Cookie の場合) 属性と *name* 属性が必要です。</span><span class="sxs-lookup"><span data-stu-id="36c48-135">**(Required)** A \<shared-cookie\> element requires, at minimum, a *domain* (for domain cookies) or a *host* (for host-only cookies) attribute and a *name* attribute.</span></span><br><span data-ttu-id="36c48-136">これらは、Cookie のドメインと名前のそれぞれに完全に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36c48-136">These must be exact matches to the cookie's domain and name respectively.</span></span> <span data-ttu-id="36c48-137">**注** サブドメインは一致しません。</span><span class="sxs-lookup"><span data-stu-id="36c48-137">**Note** that subdomains do not match.</span></span><br><br><span data-ttu-id="36c48-138">*domain* 属性はドメイン Cookie に使用されます (先頭のドットは許可されていますが、オプションです)。</span><span class="sxs-lookup"><span data-stu-id="36c48-138">The *domain* attribute is used for domain cookies (and a leading dot is allowed but optional).</span></span><br><span data-ttu-id="36c48-139">*host* 属性はホストオンリー Cookie に使用されます (先頭のドットはエラーとなります)。</span><span class="sxs-lookup"><span data-stu-id="36c48-139">The *host* attribute is used for host-only cookies (and a leading dot is an error).</span></span> <span data-ttu-id="36c48-140">どちらも指定しない、または両方を指定する場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="36c48-140">Specifying neither or both will result in an error.</span></span><br><span data-ttu-id="36c48-141">\* Cookie 文字列にドメインが指定されている場合 (HTTP Set-Cookie 応答ヘッダーまたは document.cookie JS API 経由)、Cookie はドメイン Cookie となります。</span><span class="sxs-lookup"><span data-stu-id="36c48-141">\* A cookie is a domain cookie if a domain was specified in the cookie string (via HTTP Set-Cookie response header or document.cookie JS API).</span></span> <span data-ttu-id="36c48-142">ドメイン Cookie は、指定されたドメインとすべてのサブドメインに適用されます。</span><span class="sxs-lookup"><span data-stu-id="36c48-142">A domain cookie applies to the specified domain and all subdomains.</span></span> <span data-ttu-id="36c48-143">Cookie 文字列にドメインが指定されていない場合、Cookie はホストオンリー Cookie となり、設定されている特定のホストにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="36c48-143">If a domain was not specified in the cookie string, the cookie is a host-only cookie and only applies to the specific host that it was set for.</span></span> <span data-ttu-id="36c48-144">1 単語によるホスト名 (例: http://intranetsite)) や IP アドレス (例: http://10.0.0.1)) などの URL のいくつかのクラスについては、ホストオンリー Cookie の設定ができることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="36c48-144">Note that some classes of URLs such as single-word hostnames (e.g. http://intranetsite) and IP addresses (e.g. http://10.0.0.1) can only set host-only cookies.</span></span>    |
| \<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2" **path**="/a/b/c"\>\</shared-cookie\>  | <span data-ttu-id="36c48-145">**(オプション)** *path* 属性は指定される場合があります。</span><span class="sxs-lookup"><span data-stu-id="36c48-145">**(Optional)** A *path* attribute may be specified.</span></span> <span data-ttu-id="36c48-146">path 属性が指定されていない場合 (または path 属性が空白の場合)、ドメイン/ホストと名前が一致する Cookie は、パスに関係なくポリシーに一致します (ワイルドカード ルール)。</span><span class="sxs-lookup"><span data-stu-id="36c48-146">If no path attribute is specified (or if the path attribute is empty), any cookies matching domain/host and name match the policy, regardless of path (wildcard rule).</span></span><br><br><span data-ttu-id="36c48-147">パスが指定される場合は、完全一致である必要があります。</span><span class="sxs-lookup"><span data-stu-id="36c48-147">If a path is specified, it must be an exact match.</span></span><br><span data-ttu-id="36c48-148">Cookie がパスが指定されているルールに一致する場合、パスが指定されていないルールよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="36c48-148">If a cookie matches a rule with a path, that takes precedence over a rule without a path.</span></span> |

#### <a name="sharing-example"></a><span data-ttu-id="36c48-149">共有の例</span><span class="sxs-lookup"><span data-stu-id="36c48-149">Sharing example</span></span>

```xml
<site-list version="1">
<shared-cookie domain=".contoso.com" name="cookie1"></shared-cookie> 
<shared-cookie host="subdomain.contoso.com" name="cookie2" path="/a/b/c">
</shared-cookie>
</site-list>
```

## <a name="see-also"></a><span data-ttu-id="36c48-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="36c48-150">See also</span></span>

- [<span data-ttu-id="36c48-151">IE モードの概要</span><span class="sxs-lookup"><span data-stu-id="36c48-151">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="36c48-152">構成可能なサイトの情報</span><span class="sxs-lookup"><span data-stu-id="36c48-152">Configurable sites information</span></span>](./edge-learnmore-configurable-sites-ie-mode.md)
- [<span data-ttu-id="36c48-153">その他のエンタープライズ モード情報</span><span class="sxs-lookup"><span data-stu-id="36c48-153">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="36c48-154">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="36c48-154">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)