---
title: Microsoft Edge のプロキシ設定
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 05/01/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 'コマンド ライン オプションを使用してプロキシ設定を構成する '
ms.openlocfilehash: b5e2326e075ad89481560a6642944a8e88f4daa3
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980500"
---
# <span data-ttu-id="0a0e6-103">Microsoft Edge コマンド ライン オプションを使用してプロキシ設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="0a0e6-103">How to use Microsoft Edge command-line options to configure proxy settings</span></span>

<span data-ttu-id="0a0e6-104">この記事では、コマンド ライン オプションを使用して既定のシステム ネットワーク設定を上書きする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-104">This article describes how you can use command-line options to override the default system network settings.</span></span>

>[!NOTE]
><span data-ttu-id="0a0e6-105">この記事は、Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="0a0e6-106">システム ネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="0a0e6-106">System network settings</span></span>

<span data-ttu-id="0a0e6-107">Microsoft Edge ネットワーク スタックでは、既定でシステムのネットワーク設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-107">The Microsoft Edge network stack uses the system network settings by default.</span></span> <span data-ttu-id="0a0e6-108">この設定には、*プロキシ設定*と、*証明書ストアと秘密キー ストア*が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-108">These settings include *proxy settings*, and *certificate and private key stores*.</span></span>

<span data-ttu-id="0a0e6-109">シナリオによっては、システムの既定プロキシ設定を使用する以外の手段がユーザーから要求される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-109">There are scenarios where users request an alternative to using the system's default proxy settings.</span></span> <span data-ttu-id="0a0e6-110">Microsoft Edge では、そのようなシナリオをサポートするために、カスタムプロキシ設定の構成に使用できるコマンド ライン オプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-110">To support these scenarios, Microsoft Edge supports command-line options that you can use to configure custom proxy settings.</span></span>

<span data-ttu-id="0a0e6-111">これらのコマンド ライン オプションは、**プロキシ サーバー** グループの以下のポリシーに対応しています。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-111">These command-line options correspond to the following policies in the **Proxy server** group:</span></span>

- [<span data-ttu-id="0a0e6-112">ProxyBypassList</span><span class="sxs-lookup"><span data-stu-id="0a0e6-112">ProxyBypassList</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxybypasslist)
- [<span data-ttu-id="0a0e6-113">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="0a0e6-113">ProxyMode</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxymode)
- [<span data-ttu-id="0a0e6-114">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="0a0e6-114">ProxyPacUrl</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxypacurl)
- [<span data-ttu-id="0a0e6-115">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="0a0e6-115">ProxyServer</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxyserver)
- [<span data-ttu-id="0a0e6-116">ProxySettings</span><span class="sxs-lookup"><span data-stu-id="0a0e6-116">ProxySettings</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxysettings)

## <span data-ttu-id="0a0e6-117">プロキシ設定用のコマンド ライン オプション</span><span class="sxs-lookup"><span data-stu-id="0a0e6-117">Command-line options for proxy settings</span></span>

<span data-ttu-id="0a0e6-118">Microsoft Edge では、プロキシに関連する以下のコマンド ライン オプションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-118">Microsoft Edge supports the following proxy-related command-line options.</span></span>

 **`--no-proxy-server`**
 
<span data-ttu-id="0a0e6-119">システムでプロキシを使用するように別の手段で構成されていても、プロキシを使用しないように Microsoft Edge に指示します。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-119">Tells Microsoft Edge not to use a Proxy, even if the system is otherwise configured to use one.</span></span> <span data-ttu-id="0a0e6-120">指定されている他のプロキシ設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-120">It overrides any other proxy settings that are provided.</span></span>

**`--proxy-auto-detect`**

<span data-ttu-id="0a0e6-121">プロキシ構成を試行して自動的に検出するように、Mircrosoft Edge に指示します。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-121">Tells Microsoft Edge to try and automatically detect your proxy configuration.</span></span> <span data-ttu-id="0a0e6-122">`--proxy-server` が構成されていない場合、この引数は無視されます。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-122">This argument is ignored if `--proxy-server` is configured.</span></span>

**`--proxy-server=<scheme>=<uri>[:<port>][;...] | <uri>[:<port>] | "direct://"`**

<span data-ttu-id="0a0e6-123">カスタムのプロキシ構成を使用するように Microsoft Edge に指示します。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-123">Tells Microsoft Edge to use a custom proxy configuration.</span></span> <span data-ttu-id="0a0e6-124">カスタムのプロキシ構成は、次の 3 つの方法で指定できます。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-124">You can specify a custom proxy configuration in three ways.</span></span>

1. <span data-ttu-id="0a0e6-125">URL/ポートのペアのリストをセミコロン区切りで指定します。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-125">Provide a semicolon-separated mapping of list scheme to url/port pairs.</span></span> <span data-ttu-id="0a0e6-126">たとえば `--proxy-server="http=proxy1:8080;ftp=ftpproxy"` は、HTTP プロキシ "proxy1:8080" を http の URL に、HTTP プロキシ "ftpproxy:80" を ftp の URL に使用するよう Microsoft Edge に指示しています。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-126">For example, `--proxy-server="http=proxy1:8080;ftp=ftpproxy"` tells Microsoft Edge to use HTTP proxy "proxy1:8080" for http URLs and HTTP proxy "ftpproxy:80" for ftp URLs.</span></span>
2. <span data-ttu-id="0a0e6-127">すべての URL に使用するために、オプションのポートを指定した単一の URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-127">By providing a single uri with optional port to use for all URLs.</span></span> <span data-ttu-id="0a0e6-128">たとえば、`--proxy-server="proxy2:8080"` では、すべてのトラフィックに対して "proxy2:8080" のプロキシが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-128">For example, `--proxy-server="proxy2:8080"` will use the proxy at "proxy2:8080" for all traffic.</span></span>
3. <span data-ttu-id="0a0e6-129">特殊な "direct://" 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-129">By using the special "direct://" value.</span></span> <span data-ttu-id="0a0e6-130">たとえば `--proxy-server="direct://"` では、すべての接続でプロキシが使用されなくなります。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-130">For example, `--proxy-server="direct://"` will make all connections not use a proxy.</span></span> 

>[!NOTE]
><span data-ttu-id="0a0e6-131">プロキシの使用を試行し、プロキシを使用できない場合は直接接続にフォールバックするように Microsoft Edge を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-131">You can configure Microsoft Edge to try using a proxy and fallback to going direct if the proxy isn't available.</span></span> <span data-ttu-id="0a0e6-132">たとえば、`--proxy-server="http://proxy2:8080,direct://` と記述します。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-132">For example, `--proxy-server="http://proxy2:8080,direct://`.</span></span>

**`--proxy-bypass-list=(<trailing_domain>|<ip-address>)[:<port>][;...]`**

<span data-ttu-id="0a0e6-133">指定されたセミコロン区切りのホスト一覧については、指定されたプロキシをバイパスするように Microsoft Edge に指示します。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-133">Tells Microsoft Edge to bypass any specified proxy for the specified semicolon-separated list of hosts.</span></span> <span data-ttu-id="0a0e6-134">このフラグは、`--proxy-server` と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-134">This flag must be used with `--proxy-server`.</span></span>

>[!NOTE]
><span data-ttu-id="0a0e6-135">末尾ドメイン照合では、区切り文字 "." が要求されず、"\*microsoft.com" に "imicrosoft.com" が一致します。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-135">Trailing-domain matching doesn't require "." separators, "\*microsoft.com" will match "imicrosoft.com".</span></span> <span data-ttu-id="0a0e6-136">たとえば、`--proxy-server="proxy2:8080" --proxy-bypass-list="*.microsoft.com;*example.com;127.0.0.1:8080"` では、すべてのホストについて、ポート 8080 のプロキシ サーバー "proxy2" が使用されます。ただし、ポート 8080 の \*.microsoft.com、example.com、127.0.0.1 への要求は除外されます。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-136">For example, `--proxy-server="proxy2:8080" --proxy-bypass-list="*.microsoft.com;*example.com;127.0.0.1:8080"` will use the proxy server "proxy2" on port 8080 for all hosts except requests for \*.microsoft.com, example.com, and 127.0.0.1 on port 8080.</span></span> <span data-ttu-id="0a0e6-137">前の例で、imicrosoft.com への要求についてはプロキシが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-137">In the previous example, imicrosoft.com requests will still be proxied.</span></span> <span data-ttu-id="0a0e6-138">ただし、\*.example.com ではなく \*example.com が指定されているため、iexample.com への要求についてはプロキシがバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-138">However, iexample.com requests will bypass the proxy because \*example.com was specified instead of \*.example.com.</span></span>

**`--proxy-pac-url=<pac-file-url>`**

<span data-ttu-id="0a0e6-139">指定された URL の PAC ファイルを使用するように Microsoft Edge に指示します。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-139">Tells Microsoft Edge to use the PAC file at the specified URL.</span></span> <span data-ttu-id="0a0e6-140">たとえば `--proxy-pac-url="https://wpad/proxy.pac"` は、**proxy.pac** ファイルを使用して URL 要求のプロキシ情報を解決するように Microsoft Edge に指示します。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-140">For example, `--proxy-pac-url="https://wpad/proxy.pac"` tells Microsoft Edge to resolve proxy information for URL requests using the **proxy.pac** file.</span></span>

## <span data-ttu-id="0a0e6-141">コンテンツ ライセンス</span><span class="sxs-lookup"><span data-stu-id="0a0e6-141">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="0a0e6-142">このページの一部の情報は、Chromium.org によって作成および共有されている著作物に基づいており、[Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/) に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-142">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="0a0e6-143">元のページは[こちら](https://www.chromium.org/developers/design-documents/network-settings#TOC-Command-line-options-for-proxy-sett)です。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-143">The original page can be found [here](https://www.chromium.org/developers/design-documents/network-settings#TOC-Command-line-options-for-proxy-sett).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="0a0e6-144">この著作物は、<a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a> に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-144">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <span data-ttu-id="0a0e6-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a0e6-145">See also</span></span>

- <span data-ttu-id="0a0e6-146">高度な構成設定とその他のオプションについては、Chromium Open Source プロジェクトの[プロキシに関するドキュメント](https://chromium.googlesource.com/chromium/src/+/HEAD/net/docs/proxy.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0a0e6-146">To see advanced configuration settings and additional options, consult the [proxy documentation](https://chromium.googlesource.com/chromium/src/+/HEAD/net/docs/proxy.md) in the Chromium Open Source project.</span></span>
- [<span data-ttu-id="0a0e6-147">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="0a0e6-147">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
