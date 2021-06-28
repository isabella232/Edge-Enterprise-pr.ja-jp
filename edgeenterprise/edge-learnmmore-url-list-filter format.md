---
title: Microsoft Edge URL ポリシーのフィルター形式
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 05/01/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge の URLBlocklist ポリシーおよび URLAllowlist ポリシーで使用するフィルター形式について説明します。
ms.openlocfilehash: 94378a9193269c73a7439dd019d6cb2d6ac547df
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617267"
---
# <a name="filter-format-for-url-list-based-policies"></a><span data-ttu-id="40c1b-103">URL 一覧ベースのポリシーのフィルター形式</span><span class="sxs-lookup"><span data-stu-id="40c1b-103">Filter format for URL list-based policies</span></span>

<span data-ttu-id="40c1b-104">この記事では、Microsoft Edge の URL 一覧ベースのポリシー ([URLBlocklist](microsoft-edge-policies.md#urlblocklist)、[URLAllowList](microsoft-edge-policies.md#urlallowlist)、[CertificateTransparencyEnforcementDisabledForUrls](microsoft-edge-policies.md#certificatetransparencyenforcementdisabledforurls) などのポリシー) に使用するフィルター形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="40c1b-104">This article describes the filter format used for the Microsoft Edge URL list-based policies (For example, [URLBlocklist](microsoft-edge-policies.md#urlblocklist), [URLAllowList](microsoft-edge-policies.md#urlallowlist), and [CertificateTransparencyEnforcementDisabledForUrls](microsoft-edge-policies.md#certificatetransparencyenforcementdisabledforurls) policies.</span></span>

> [!NOTE]
> <span data-ttu-id="40c1b-105">この記事は、Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="the-filter-format"></a><span data-ttu-id="40c1b-106">フィルター形式</span><span class="sxs-lookup"><span data-stu-id="40c1b-106">The filter format</span></span>

<span data-ttu-id="40c1b-107">フィルター形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="40c1b-107">The filter format is:</span></span>

```
    [scheme://][.]host[:port][/path][@query]
```

<span data-ttu-id="40c1b-108">このフィルター形式には、以下のフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="40c1b-108">The fields in the filter format are:</span></span>

| <span data-ttu-id="40c1b-109">フィールド</span><span class="sxs-lookup"><span data-stu-id="40c1b-109">Field</span></span> | <span data-ttu-id="40c1b-110">説明</span><span class="sxs-lookup"><span data-stu-id="40c1b-110">Description</span></span> |
| --- | --- |
| <span data-ttu-id="40c1b-111">**scheme** (*オプション*)</span><span class="sxs-lookup"><span data-stu-id="40c1b-111">**scheme** (*optional*)</span></span> | <span data-ttu-id="40c1b-112"> http://、https://、ftp://、edge:// などを指定できます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-112">It can be http://, https://, ftp://, edge://, etc.</span></span> |
| <span data-ttu-id="40c1b-113">**host** (*必須*)</span><span class="sxs-lookup"><span data-stu-id="40c1b-113">**host** (*required*)</span></span> | <span data-ttu-id="40c1b-114">有効なホスト名である必要があります。ワイルドカード ("\*") を使用できます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-114">It must be a valid host name and you can use a wildcard ("\*").</span></span> <span data-ttu-id="40c1b-115">サブドメインの照合を無効にするには、**host** の前にオプションのドット (".") を含めます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-115">To disable subdomain matching, include an optional dot (".") before **host**.</span></span> <span data-ttu-id="40c1b-116">単一の IP アドレス リテラル ホスト名を指定できますが、IP アドレス リテラルホスト名に対してワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="40c1b-116">A single IP Address Literal hostname may be specified, but wildcarding is not supported for an IP Address Literal hostname.</span></span> |
| <span data-ttu-id="40c1b-117">**port** (*オプション*)</span><span class="sxs-lookup"><span data-stu-id="40c1b-117">**port** (*optional*)</span></span> | <span data-ttu-id="40c1b-118">有効な値は 1 ～ 65535 です。</span><span class="sxs-lookup"><span data-stu-id="40c1b-118">Valid values range from 1 to 65535.</span></span> |
| <span data-ttu-id="40c1b-119">**path** (*オプション*)</span><span class="sxs-lookup"><span data-stu-id="40c1b-119">**path** (*optional*)</span></span> | <span data-ttu-id="40c1b-120">パスには任意の文字列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-120">You can use any string in the path.</span></span> |
| <span data-ttu-id="40c1b-121">**query** (*オプション*)</span><span class="sxs-lookup"><span data-stu-id="40c1b-121">**query** (*optional*)</span></span> | <span data-ttu-id="40c1b-122">**query** には、キーと値またはキーのみのトークンをアンパサンド ("&") で区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="40c1b-122">The **query** is either key-value or key-only tokens separated by an ampersand ("&").</span></span> <span data-ttu-id="40c1b-123">キーと値のトークンは、等号 ("=") で区切ります。</span><span class="sxs-lookup"><span data-stu-id="40c1b-123">Separate key-value tokens with an equal sign ("=").</span></span> <span data-ttu-id="40c1b-124">プレフィックスの一致を指定するには、**query** の最後にアスタリスク ("\*") を使用できます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-124">To indicate a prefix match, you can use an asterisk ("\*") at the end of the **query**.</span></span> |

## <a name="comparing-the-filter-format-to-the-url-format"></a><span data-ttu-id="40c1b-125">フィルター形式と URL 形式の比較</span><span class="sxs-lookup"><span data-stu-id="40c1b-125">Comparing the filter format to the URL format</span></span>

<span data-ttu-id="40c1b-126">フィルター形式は URL 形式に似ていますが、次の点が異なります。</span><span class="sxs-lookup"><span data-stu-id="40c1b-126">The filter format resembles the URL format, except for the following differences:</span></span>

- <span data-ttu-id="40c1b-127">"user:pass" を含めても無視されます</span><span class="sxs-lookup"><span data-stu-id="40c1b-127">If you include "user:pass", it will be ignored.</span></span> <span data-ttu-id="40c1b-128">(http://user:pass@ftp.contoso.com/pub/example.iso など)。</span><span class="sxs-lookup"><span data-stu-id="40c1b-128">For example, http://user:pass@ftp.contoso.com/pub/example.iso.</span></span>
- <span data-ttu-id="40c1b-129">フラグメント識別子 ("#") を含めた場合、この識別子と、それ以降の文字列はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-129">If you include a fragment identifier ("#"), it and everything that follows the identifier is ignored.</span></span>
- <span data-ttu-id="40c1b-130">**host** としてワイルドカード ("\*") を使用できます。また、プレフィックスとしてドット (".") を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-130">You can use a wildcard ("\*") as the **host** and you can prefix it with a dot (".").</span></span>
- <span data-ttu-id="40c1b-131">**host** のサフィックスとして、スラッシュ ("/") またはドット (".") を使用できます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-131">You can use a forward slash ("/") or a dot (".") as a suffix for the **host**.</span></span> <span data-ttu-id="40c1b-132">この場合、サフィックスは無視されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-132">In this case, the suffix is ignored.</span></span>

## <a name="filter-selection-criteria"></a><span data-ttu-id="40c1b-133">フィルター選択条件</span><span class="sxs-lookup"><span data-stu-id="40c1b-133">Filter selection criteria</span></span>

<span data-ttu-id="40c1b-134">URL 用に選択されるフィルターは、次のフィルター選択規則を処理した後に検出される、最も明確な一致です。</span><span class="sxs-lookup"><span data-stu-id="40c1b-134">The filter selected for a URL is the most specific match found after processing the following filter selection rules:</span></span>

1. <span data-ttu-id="40c1b-135">**host** の一致部分が最も長いフィルターが最初に選択されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-135">Filters with the longest **host** match are selected first.</span></span>
2. <span data-ttu-id="40c1b-136">選択されたフィルターから、scheme または port が一致しないフィルターは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-136">From the selected filters, any filter with a non-matching scheme or port is discarded.</span></span>
3. <span data-ttu-id="40c1b-137">残りのフィルターから、一致する **path** が最も長いフィルターが選択されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-137">From the remaining filters, the filter with the longest matching **path** is selected.</span></span>
4. <span data-ttu-id="40c1b-138">残りのフィルターから、query トークンのセットが最も長いフィルターが選択されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-138">From the remaining filters, the filter with the longest set of query tokens is selected.</span></span> <span data-ttu-id="40c1b-139">この手順では、両方のフィルターで **path** の長さと **query** トーックンの数が同じであれば、許可一覧フィルターがブロック一覧フィルターより優先されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-139">At this step, the allow list filter takes precedence over the block list filter if both filters have the same **path** length and number of **query** tokens.</span></span>
5. <span data-ttu-id="40c1b-140">有効なフィルターが残っていない場合は、**host** から最上位のサブドメインが削除され、選択プロセスが手順 1. から再び開始されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-140">If there's no valid filter remaining, then the left-most subdomain is removed from **host** and the selection process starts over at step 1.</span></span> <span data-ttu-id="40c1b-141">特殊なアスタリスク ("\*") の **ホスト**が最後に検索され、すべてのホストに一致します。</span><span class="sxs-lookup"><span data-stu-id="40c1b-141">The special asterisk ("\*") **host** is the last searched and it matches all hosts.</span></span>
6. <span data-ttu-id="40c1b-142">フィルターが使用可能であれば、URL 要求がブロックまたは許可されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-142">If a filter's available, it blocks or allows the URL request.</span></span>

   >[!NOTE]
   ><span data-ttu-id="40c1b-143">フィルターの一致がない場合、既定の動作では、URL 要求が許可されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-143">The default behavior is to allow the URL request if no filter is matched.</span></span>

## <a name="example-filter-selection-criteria"></a><span data-ttu-id="40c1b-144">フィルター選択条件の例</span><span class="sxs-lookup"><span data-stu-id="40c1b-144">Example filter selection criteria</span></span>

<span data-ttu-id="40c1b-145">この例では、"https://sub.contoso.com/docs" との一致を検索するときに、フィルター選択で次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-145">In this example, when searching for a match to "https://sub.contoso.com/docs" the filter selection will:</span></span>

1. <span data-ttu-id="40c1b-146">"sub.contoso.com" のフィルターを検索します。</span><span class="sxs-lookup"><span data-stu-id="40c1b-146">Search for a filter for "sub.contoso.com".</span></span> <span data-ttu-id="40c1b-147">フィルターが見つかった場合、検索の処理は手順 2. に進みます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-147">If it finds a filter, the search moves to step 2.</span></span> <span data-ttu-id="40c1b-148">フィルターが見つからない場合は、"contoso.com"、"com"、最終的には "" を使用して検索が再試行されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-148">If a filter isn't found, then it tries again with "contoso.com", "com", and finally "".</span></span>
2. <span data-ttu-id="40c1b-149">選択されたフィルターから、**scheme** に "http" が含まれていないものはすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-149">From the selected filters, any that don't have "http" in the **scheme** are removed.</span></span>
3. <span data-ttu-id="40c1b-150">残りのフィルターから、正確なポート番号が "80" ではないものはすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-150">From the remaining filters, any that have an exact port number that isn't "80" are removed.</span></span>
4. <span data-ttu-id="40c1b-151">残りのフィルターから、**path** のプレフィックスが "/docs" でないものはすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-151">From the remaining filters, any that don't have "/docs" as a prefix of the **path** are removed.</span></span>
5. <span data-ttu-id="40c1b-152">残りのフィルターから、path のプレフィックスが最も長いフィルターが選択され、適用されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-152">From the remaining filters, the filter with the longest path prefix is selected and applied.</span></span> <span data-ttu-id="40c1b-153">フィルターが見つからない場合は、選択プロセスが手順 1. から再び開始されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-153">If a filter isn't found, the selection process starts over again at step 1.</span></span> <span data-ttu-id="40c1b-154">プロセスは、次のサブドメインで繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-154">The process is repeated with the next subdomain.</span></span>

### <a name="additional-filter-information"></a><span data-ttu-id="40c1b-155">フィルターに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="40c1b-155">Additional filter information</span></span>

<span data-ttu-id="40c1b-156">フィルターに、**host** のプレフィックスとしてドット (".") が含まれている場合は、**host** への正確な一致のみがフィルター選択されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-156">If a filter has a dot (".") prefixing the **host** then only exact **host** matches are filtered.</span></span> <span data-ttu-id="40c1b-157">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="40c1b-157">For example:</span></span>

- <span data-ttu-id="40c1b-158">"contoso.com" (ドットなし) は "contoso.com"、"www.contoso.com"、および "sub.www.contoso.com" と一致します。</span><span class="sxs-lookup"><span data-stu-id="40c1b-158">"contoso.com" (no dot) will match "contoso.com", "www.contoso.com", and "sub.www.contoso.com"</span></span>
- <span data-ttu-id="40c1b-159">".www.contoso.com" (ドットのプレフィックスあり) は、"www.contoso.com" にのみ一致します。</span><span class="sxs-lookup"><span data-stu-id="40c1b-159">".www.contoso.com" (with a dot prefix) will only match "www.contoso.com"</span></span>

<span data-ttu-id="40c1b-160">標準スキーマまたはカスタム **スキーマ**のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-160">You can use either a standard or custom **schema**.</span></span> <span data-ttu-id="40c1b-161">サポートされている標準スキーマは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="40c1b-161">Supported standard schemas include:</span></span>

- <span data-ttu-id="40c1b-162">_about_、_blob_、_content_、_edge_、_cid_、_data_、_file_、_filesystem_、_ftp_、_gopher_、_http_、_https_、_javascript_、_mailto_、_ws_、_wss_</span><span class="sxs-lookup"><span data-stu-id="40c1b-162">_about_, _blob_, _content_, _edge_, _cid_, _data_, _file_, _filesystem_, _ftp_, _gopher_, _http_, _https_, _javascript_, _mailto_, _ws_, and _wss_.</span></span>

<span data-ttu-id="40c1b-163">その他の **schema** はカスタムの **schema** として処理されますが、許可されるパターンは _schema:\*_ および _schema://\*_ のみです。</span><span class="sxs-lookup"><span data-stu-id="40c1b-163">Any other **schema** is treated as a custom **schema**, but only the _schema:\*_ and _schema://\*_ patterns are allowed.</span></span> <span data-ttu-id="40c1b-164">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="40c1b-164">For example:</span></span>

- <span data-ttu-id="40c1b-165">"custom:\*" または "custom://\*" は "custom:app" と一致します</span><span class="sxs-lookup"><span data-stu-id="40c1b-165">"custom:\*" or "custom://\*" will match "custom:app"</span></span>
- <span data-ttu-id="40c1b-166">"custom:app" と "custom://app" は無効です</span><span class="sxs-lookup"><span data-stu-id="40c1b-166">"custom:app" or "custom://app" are invalid</span></span>

<span data-ttu-id="40c1b-167">**schema** と **host** では、大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="40c1b-167">**schema** and **host** aren't case-sensitive.</span></span> <span data-ttu-id="40c1b-168">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="40c1b-168">For example:</span></span>

- <span data-ttu-id="40c1b-169">フィルター "http://contoso.com" は、"HTTP://contoso.com"、"http://contoso.COM"、"http://contoso.com" に一致します。</span><span class="sxs-lookup"><span data-stu-id="40c1b-169">"http://contoso.com" filter matches "HTTP://contoso.com", "http://contoso.COM", and "http://contoso.com"</span></span>

<span data-ttu-id="40c1b-170">**path** と **query** では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="40c1b-170">**path** and **query** are case-sensitive.</span></span> <span data-ttu-id="40c1b-171">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="40c1b-171">For example:</span></span>

- <span data-ttu-id="40c1b-172">フィルター "http://contoso.com/path?query=A" は、"http://contoso.com/Path?query=A" または "http://contoso.com/path?Query=A" に一致しません。</span><span class="sxs-lookup"><span data-stu-id="40c1b-172">"http://contoso.com/path?query=A" filter doesn't match "http://contoso.com/Path?query=A" or "http://contoso.com/path?Query=A".</span></span> <span data-ttu-id="40c1b-173">"http://contoso.COM/path?query=A" には一致します。</span><span class="sxs-lookup"><span data-stu-id="40c1b-173">It does match "http://contoso.COM/path?query=A".</span></span>

## <a name="content-license"></a><span data-ttu-id="40c1b-174">コンテンツ ライセンス</span><span class="sxs-lookup"><span data-stu-id="40c1b-174">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="40c1b-175">このページの一部の情報は、Chromium.org によって作成および共有されている著作物に基づいており、[Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/) に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="40c1b-175">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="40c1b-176">元の [Chromium のページはこちら](https://www.chromium.org/administrators/url-blacklist-filter-format)です。</span><span class="sxs-lookup"><span data-stu-id="40c1b-176">The original [Chromium page can be found here](https://www.chromium.org/administrators/url-blacklist-filter-format).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="40c1b-177">この著作物は、<a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a> に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="40c1b-177">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <a name="see-also"></a><span data-ttu-id="40c1b-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="40c1b-178">See also</span></span>

- [<span data-ttu-id="40c1b-179">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="40c1b-179">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
