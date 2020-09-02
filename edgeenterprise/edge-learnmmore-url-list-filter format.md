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
ms.openlocfilehash: 5a0eff1ca7be17fccd1087716d426b13ea302847
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980445"
---
# <span data-ttu-id="b4e99-103">URL 一覧ベースのポリシーのフィルター形式</span><span class="sxs-lookup"><span data-stu-id="b4e99-103">Filter format for URL list-based policies</span></span>

<span data-ttu-id="b4e99-104">この記事では、Microsoft Edge の URL 一覧ベースのポリシー ([URLBlocklist](microsoft-edge-policies.md#urlblocklist)、[URLAllowList](microsoft-edge-policies.md#urlallowlist)、[CertificateTransparencyEnforcementDisabledForUrls](microsoft-edge-policies.md#certificatetransparencyenforcementdisabledforurls) などのポリシー) に使用するフィルター形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="b4e99-104">This article describes the filter format used for the Microsoft Edge URL list-based policies (For example, [URLBlocklist](microsoft-edge-policies.md#urlblocklist), [URLAllowList](microsoft-edge-policies.md#urlallowlist), and [CertificateTransparencyEnforcementDisabledForUrls](microsoft-edge-policies.md#certificatetransparencyenforcementdisabledforurls) policies.</span></span>

> [!NOTE]
> <span data-ttu-id="b4e99-105">この記事は、Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="b4e99-106">フィルター形式</span><span class="sxs-lookup"><span data-stu-id="b4e99-106">The filter format</span></span>

<span data-ttu-id="b4e99-107">フィルター形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b4e99-107">The filter format is:</span></span>

```
    [scheme://][.]host[:port][/path][@query]
```

<span data-ttu-id="b4e99-108">このフィルター形式には、以下のフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b4e99-108">The fields in the filter format are:</span></span>

| <span data-ttu-id="b4e99-109">フィールド</span><span class="sxs-lookup"><span data-stu-id="b4e99-109">Field</span></span> | <span data-ttu-id="b4e99-110">説明</span><span class="sxs-lookup"><span data-stu-id="b4e99-110">Description</span></span> |
| --- | --- |
| <span data-ttu-id="b4e99-111">**scheme** (*オプション*)</span><span class="sxs-lookup"><span data-stu-id="b4e99-111">**scheme** (*optional*)</span></span> | <span data-ttu-id="b4e99-112">http://、https://、ftp://、edge:// などを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-112">It can be http://, https://, ftp://, edge://, etc.</span></span> |
| <span data-ttu-id="b4e99-113">**host** (*必須*)</span><span class="sxs-lookup"><span data-stu-id="b4e99-113">**host** (*required*)</span></span> | <span data-ttu-id="b4e99-114">有効なホスト名または IP アドレスを指定します。ワイルドカード ("\*") を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-114">It must be a valid host name or IP address and you can use a wildcard ("\*").</span></span> <span data-ttu-id="b4e99-115">サブドメインの照合を無効にするには、**host** の前にオプションのドット (".") を含めます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-115">To disable subdomain matching, include an optional dot (".") before **host**.</span></span> |
| <span data-ttu-id="b4e99-116">**port** (*オプション*)</span><span class="sxs-lookup"><span data-stu-id="b4e99-116">**port** (*optional*)</span></span> | <span data-ttu-id="b4e99-117">有効な値は 1 ～ 65535 です。</span><span class="sxs-lookup"><span data-stu-id="b4e99-117">Valid values range from 1 to 65535.</span></span> |
| <span data-ttu-id="b4e99-118">**path** (*オプション*)</span><span class="sxs-lookup"><span data-stu-id="b4e99-118">**path** (*optional*)</span></span> | <span data-ttu-id="b4e99-119">パスには任意の文字列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-119">You can use any string in the path.</span></span> |
| <span data-ttu-id="b4e99-120">**query** (*オプション*)</span><span class="sxs-lookup"><span data-stu-id="b4e99-120">**query** (*optional*)</span></span> | <span data-ttu-id="b4e99-121">**query** には、キーと値またはキーのみのトークンをアンパサンド ("&") で区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="b4e99-121">The **query** is either key-value or key-only tokens separated by an ampersand ("&").</span></span> <span data-ttu-id="b4e99-122">キーと値のトークンは、等号 ("=") で区切ります。</span><span class="sxs-lookup"><span data-stu-id="b4e99-122">Separate key-value tokens with an equal sign ("=").</span></span> <span data-ttu-id="b4e99-123">プレフィックスの一致を指定するには、**query** の最後にアスタリスク ("\*") を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-123">To indicate a prefix match, you can use an asterisk ("\*") at the end of the **query**.</span></span> |

## <span data-ttu-id="b4e99-124">フィルター形式と URL 形式の比較</span><span class="sxs-lookup"><span data-stu-id="b4e99-124">Comparing the filter format to the URL format</span></span>

<span data-ttu-id="b4e99-125">フィルター形式は URL 形式に似ていますが、次の点が異なります。</span><span class="sxs-lookup"><span data-stu-id="b4e99-125">The filter format resembles the URL format, except for the following differences:</span></span>

- <span data-ttu-id="b4e99-126">"user:pass" を含めても無視されます</span><span class="sxs-lookup"><span data-stu-id="b4e99-126">If you include "user:pass", it will be ignored.</span></span> <span data-ttu-id="b4e99-127">(http://user:pass@ftp.contoso.com/pub/example.iso など)。</span><span class="sxs-lookup"><span data-stu-id="b4e99-127">For example, http://user:pass@ftp.contoso.com/pub/example.iso.</span></span>
- <span data-ttu-id="b4e99-128">フラグメント識別子 ("#") を含めた場合、この識別子と、それ以降の文字列はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-128">If you include a fragment identifier ("#"), it and everything that follows the identifier is ignored.</span></span>
- <span data-ttu-id="b4e99-129">**host** としてワイルドカード ("\*") を使用できます。また、プレフィックスとしてドット (".") を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-129">You can use a wildcard ("\*") as the **host** and you can prefix it with a dot (".").</span></span>
- <span data-ttu-id="b4e99-130">**host** のサフィックスとして、スラッシュ ("/") またはドット (".") を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-130">You can use a forward slash ("/") or a dot (".") as a suffix for the **host**.</span></span> <span data-ttu-id="b4e99-131">この場合、サフィックスは無視されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-131">In this case, the suffix is ignored.</span></span>

## <span data-ttu-id="b4e99-132">フィルター選択条件</span><span class="sxs-lookup"><span data-stu-id="b4e99-132">Filter selection criteria</span></span>

<span data-ttu-id="b4e99-133">URL 用に選択されるフィルターは、次のフィルター選択規則を処理した後に検出される、最も明確な一致です。</span><span class="sxs-lookup"><span data-stu-id="b4e99-133">The filter selected for a URL is the most specific match found after processing the following filter selection rules:</span></span>

1. <span data-ttu-id="b4e99-134">**host** の一致部分が最も長いフィルターが最初に選択されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-134">Filters with the longest **host** match are selected first.</span></span>
2. <span data-ttu-id="b4e99-135">選択されたフィルターから、scheme または port が一致しないフィルターは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-135">From the selected filters, any filter with a non-matching scheme or port is discarded.</span></span>
3. <span data-ttu-id="b4e99-136">残りのフィルターから、一致する **path** が最も長いフィルターが選択されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-136">From the remaining filters, the filter with the longest matching **path** is selected.</span></span>
4. <span data-ttu-id="b4e99-137">残りのフィルターから、query トークンのセットが最も長いフィルターが選択されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-137">From the remaining filters, the filter with the longest set of query tokens is selected.</span></span> <span data-ttu-id="b4e99-138">この手順では、両方のフィルターで **path** の長さと **query** トーックンの数が同じであれば、許可一覧フィルターがブロック一覧フィルターより優先されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-138">At this step, the allow list filter takes precedence over the block list filter if both filters have the same **path** length and number of **query** tokens.</span></span>
5. <span data-ttu-id="b4e99-139">有効なフィルターが残っていない場合は、**host** から最上位のサブドメインが削除され、選択プロセスが手順 1. から再び開始されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-139">If there's no valid filter remaining, then the left-most subdomain is removed from **host** and the selection process starts over at step 1.</span></span> <span data-ttu-id="b4e99-140">特殊なアスタリスク ("\*") の **ホスト**が最後に検索され、すべてのホストに一致します。</span><span class="sxs-lookup"><span data-stu-id="b4e99-140">The special asterisk ("\*") **host** is the last searched and it matches all hosts.</span></span>
6. <span data-ttu-id="b4e99-141">フィルターが使用可能であれば、URL 要求がブロックまたは許可されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-141">If a filter's available, it blocks or allows the URL request.</span></span>

   >[!NOTE]
   ><span data-ttu-id="b4e99-142">フィルターの一致がない場合、既定の動作では、URL 要求が許可されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-142">The default behavior is to allow the URL request if no filter is matched.</span></span>

## <span data-ttu-id="b4e99-143">フィルター選択条件の例</span><span class="sxs-lookup"><span data-stu-id="b4e99-143">Example filter selection criteria</span></span>

<span data-ttu-id="b4e99-144">この例では、"https://sub.contoso.com/docs" との一致を検索するときに、フィルター選択で次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-144">In this example, when searching for a match to "https://sub.contoso.com/docs" the filter selection will:</span></span>

1. <span data-ttu-id="b4e99-145">"sub.contoso.com" のフィルターを検索します。</span><span class="sxs-lookup"><span data-stu-id="b4e99-145">Search for a filter for "sub.contoso.com".</span></span> <span data-ttu-id="b4e99-146">フィルターが見つかった場合、検索の処理は手順 2. に進みます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-146">If it finds a filter, the search moves to step 2.</span></span> <span data-ttu-id="b4e99-147">フィルターが見つからない場合は、"contoso.com"、"com"、最終的には "" を使用して検索が再試行されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-147">If a filter isn't found, then it tries again with "contoso.com", "com", and finally "".</span></span>
2. <span data-ttu-id="b4e99-148">選択されたフィルターから、**scheme** に "http" が含まれていないものはすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-148">From the selected filters, any that don't have "http" in the **scheme** are removed.</span></span>
3. <span data-ttu-id="b4e99-149">残りのフィルターから、正確なポート番号が "80" ではないものはすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-149">From the remaining filters, any that have an exact port number that isn't "80" are removed.</span></span>
4. <span data-ttu-id="b4e99-150">残りのフィルターから、**path** のプレフィックスが "/docs" でないものはすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-150">From the remaining filters, any that don't have "/docs" as a prefix of the **path** are removed.</span></span>
5. <span data-ttu-id="b4e99-151">残りのフィルターから、path のプレフィックスが最も長いフィルターが選択され、適用されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-151">From the remaining filters, the filter with the longest path prefix is selected and applied.</span></span> <span data-ttu-id="b4e99-152">フィルターが見つからない場合は、選択プロセスが手順 1. から再び開始されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-152">If a filter isn't found, the selection process starts over again at step 1.</span></span> <span data-ttu-id="b4e99-153">プロセスは、次のサブドメインで繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-153">The process is repeated with the next subdomain.</span></span>

### <span data-ttu-id="b4e99-154">フィルターに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="b4e99-154">Additional filter information</span></span>

<span data-ttu-id="b4e99-155">フィルターに、**host** のプレフィックスとしてドット (".") が含まれている場合は、**host** への正確な一致のみがフィルター選択されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-155">If a filter has a dot (".") prefixing the **host** then only exact **host** matches are filtered.</span></span> <span data-ttu-id="b4e99-156">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="b4e99-156">For example:</span></span>

- <span data-ttu-id="b4e99-157">"contoso.com" (ドットなし) は "contoso.com"、"www.contoso.com"、および "sub.www.contoso.com" と一致します。</span><span class="sxs-lookup"><span data-stu-id="b4e99-157">"contoso.com" (no dot) will match "contoso.com", "www.contoso.com", and "sub.www.contoso.com"</span></span>
- <span data-ttu-id="b4e99-158">".www.contoso.com" (ドットのプレフィックスあり) は、"www.contoso.com" にのみ一致します。</span><span class="sxs-lookup"><span data-stu-id="b4e99-158">".www.contoso.com" (with a dot prefix) will only match "www.contoso.com"</span></span>

<span data-ttu-id="b4e99-159">標準またはカスタムの **schema** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-159">You can use either a standard or customer **schema**.</span></span> <span data-ttu-id="b4e99-160">サポートされている標準スキーマは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b4e99-160">Supported standard schemas include:</span></span>

- <span data-ttu-id="b4e99-161">_about_、_blob_、_content_、_edge_、_cid_、_data_、_file_、_filesystem_、_ftp_、_gopher_、_http_、_https_、_javascript_、_mailto_、_ws_、_wss_</span><span class="sxs-lookup"><span data-stu-id="b4e99-161">_about_, _blob_, _content_, _edge_, _cid_, _data_, _file_, _filesystem_, _ftp_, _gopher_, _http_, _https_, _javascript_, _mailto_, _ws_, and _wss_.</span></span>

<span data-ttu-id="b4e99-162">その他の **schema** はカスタムの **schema** として処理されますが、許可されるパターンは _schema:\*_ および _schema://\*_ のみです。</span><span class="sxs-lookup"><span data-stu-id="b4e99-162">Any other **schema** is treated as a custom **schema**, but only the _schema:\*_ and _schema://\*_ patterns are allowed.</span></span> <span data-ttu-id="b4e99-163">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="b4e99-163">For example:</span></span>

- <span data-ttu-id="b4e99-164">"custom:*" と "custom://*" は "custom:app" に一致します。</span><span class="sxs-lookup"><span data-stu-id="b4e99-164">"custom:*" or "custom://*" will match "custom:app"</span></span>
- <span data-ttu-id="b4e99-165">"custom:app" と "custom://app" は無効ですｌ</span><span class="sxs-lookup"><span data-stu-id="b4e99-165">"custom:app" or "custom://app" are invalid</span></span>

<span data-ttu-id="b4e99-166">**schema** と **host** では、大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="b4e99-166">**schema** and **host** aren't case-sensitive.</span></span> <span data-ttu-id="b4e99-167">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="b4e99-167">For example:</span></span>

- <span data-ttu-id="b4e99-168">フィルター "http://contoso.com" は、"HTTP://contoso.com"、"http://contoso.COM"、"http://contoso.com" に一致します。</span><span class="sxs-lookup"><span data-stu-id="b4e99-168">"http://contoso.com" filter matches "HTTP://contoso.com", "http://contoso.COM", and "http://contoso.com"</span></span>

<span data-ttu-id="b4e99-169">**path** と **query** では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="b4e99-169">**path** and **query** are case-sensitive.</span></span> <span data-ttu-id="b4e99-170">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="b4e99-170">For example:</span></span>

- <span data-ttu-id="b4e99-171">フィルター "http://contoso.com/path?query=A" は、"http://contoso.com/Path?query=A" または "http://contoso.com/path?Query=A" に一致しません。</span><span class="sxs-lookup"><span data-stu-id="b4e99-171">"http://contoso.com/path?query=A" filter doesn't match "http://contoso.com/Path?query=A" or "http://contoso.com/path?Query=A".</span></span> <span data-ttu-id="b4e99-172">"http://contoso.COM/path?query=A" には一致します。</span><span class="sxs-lookup"><span data-stu-id="b4e99-172">It does match "http://contoso.COM/path?query=A".</span></span>

## <span data-ttu-id="b4e99-173">コンテンツ ライセンス</span><span class="sxs-lookup"><span data-stu-id="b4e99-173">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="b4e99-174">このページの一部の情報は、Chromium.org によって作成および共有されている著作物に基づいており、[Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/) に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="b4e99-174">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="b4e99-175">元の [Chromium のページはこちら](https://www.chromium.org/administrators/url-blacklist-filter-format)です。</span><span class="sxs-lookup"><span data-stu-id="b4e99-175">The original [Chromium page can be found here](https://www.chromium.org/administrators/url-blacklist-filter-format).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="b4e99-176">この著作物は、<a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a> に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="b4e99-176">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <span data-ttu-id="b4e99-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4e99-177">See also</span></span>

- [<span data-ttu-id="b4e99-178">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="b4e99-178">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
