---
title: Microsoft Edge エンドポイントの許可リスト
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 10/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge エンドポイントの許可リスト
ms.openlocfilehash: 48a3a72e5af3744516e3b72d02b5254ad2e0504a
ms.sourcegitcommit: b32d8d64ae65dc5a46e47b7c34b0211097a0cc65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "11133122"
---
# <span data-ttu-id="0b101-103">Microsoft Edge エンドポイントの許可リスト</span><span class="sxs-lookup"><span data-stu-id="0b101-103">Allow list for Microsoft Edge endpoints</span></span>

<span data-ttu-id="0b101-104">Microsoft Edge の機能を利用するには、インターネットに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b101-104">Microsoft Edge requires connectivity to the Internet to support its features.</span></span> <span data-ttu-id="0b101-105">この記事では、ファイアウォールやその他のセキュリティ メカニズムを介した通信を行うために、許可リストに追加する必要があるドメインの URL について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b101-105">This article identifies the domain URLs that you need to add to the Allow list to ensure communications through firewalls and other security mechanisms.</span></span>

> [!NOTE]
> <span data-ttu-id="0b101-106">これは、Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0b101-106">This applies  to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="0b101-107">許可するドメインの URL</span><span class="sxs-lookup"><span data-stu-id="0b101-107">Domain URLs to allow</span></span>

<span data-ttu-id="0b101-108">Microsoft Edge で次のドメインの URL を許可します。</span><span class="sxs-lookup"><span data-stu-id="0b101-108">Allow the following domain URLs for Microsoft Edge.</span></span>

### <span data-ttu-id="0b101-109">Update Service</span><span class="sxs-lookup"><span data-stu-id="0b101-109">Update Service</span></span>

<span data-ttu-id="0b101-110">Microsoft Edge が新しい更新プログラムを確認するために使用するサービス。</span><span class="sxs-lookup"><span data-stu-id="0b101-110">The service that Microsoft Edge uses to check for new updates.</span></span>

- `https://msedge.api.cdp.microsoft.com`

### <span data-ttu-id="0b101-111">Experimentation and Configuration Service</span><span class="sxs-lookup"><span data-stu-id="0b101-111">Experimentation and Configuration service</span></span>

- `https://config.edge.skype.com`

### <span data-ttu-id="0b101-112">Microsoft Edge のダウンロード場所</span><span class="sxs-lookup"><span data-stu-id="0b101-112">Download locations for Microsoft Edge</span></span>

<span data-ttu-id="0b101-113">初期インストール中、または更新プログラムが利用可能になった場合に、Microsoft Edge をダウンロードできる場所です。</span><span class="sxs-lookup"><span data-stu-id="0b101-113">Locations Microsoft Edge can be downloaded from during an initial install or when an update is available.</span></span> <span data-ttu-id="0b101-114">ダウンロード場所は、Update Service によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="0b101-114">The download location is determined by the Update Service.</span></span>

#### <span data-ttu-id="0b101-115">HTTP</span><span class="sxs-lookup"><span data-stu-id="0b101-115">HTTP</span></span>

- `http://msedge.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.f.dl.delivery.mp.microsoft.com`
- `http://msedge.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.b.dl.delivery.mp.microsoft.com`

#### <span data-ttu-id="0b101-116">HTTPS</span><span class="sxs-lookup"><span data-stu-id="0b101-116">HTTPS</span></span>

- `https://msedge.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sf.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > <span data-ttu-id="0b101-117">ダウンロード場所の許可リストを簡略化するには、次のようにワイルドカードを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b101-117">To simplify the allow list for download locations a wild card can be used:</span></span> `*.dl.delivery.mp.microsoft.com`

### <span data-ttu-id="0b101-118">Microsoft Edge 拡張機能のダウンロード場所</span><span class="sxs-lookup"><span data-stu-id="0b101-118">Download locations for Microsoft Edge Extensions</span></span>

<span data-ttu-id="0b101-119">初期インストール中、または更新プログラムが利用可能になった場合に、Microsoft Edge 拡張機能をダウンロードできる場所です。</span><span class="sxs-lookup"><span data-stu-id="0b101-119">Locations Microsoft Edge Extensions can be downloaded from during an initial install or when an update is available.</span></span> <span data-ttu-id="0b101-120">ダウンロード場所は、Update Service によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="0b101-120">The download location is determined by the Update Service.</span></span>

#### <span data-ttu-id="0b101-121">HTTP</span><span class="sxs-lookup"><span data-stu-id="0b101-121">HTTP</span></span>

- `http://msedgeextensions.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.f.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.dl.delivery.mp.microsoft.com`

#### <span data-ttu-id="0b101-122">HTTPS</span><span class="sxs-lookup"><span data-stu-id="0b101-122">HTTPS</span></span>

- `https://msedgeextensions.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sf.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > <span data-ttu-id="0b101-123">ダウンロード場所の許可リストを簡略化するには、次のようにワイルドカードを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b101-123">To simplify the allow list for download locations a wild card can be used:</span></span> `*.dl.delivery.mp.microsoft.com`

### <span data-ttu-id="0b101-124">ダウンロード配信の最適化 (オプション)</span><span class="sxs-lookup"><span data-stu-id="0b101-124">Optionally for Download Delivery Optimization</span></span>

<span data-ttu-id="0b101-125">配信の最適化については、「[Windows 10 更新プログラムの配信の最適化](https://aka.ms/waas-do)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b101-125">For information about delivery optimization, see [Delivery Optimization for Windows 10 updates](https://aka.ms/waas-do).</span></span>

- <span data-ttu-id="0b101-126">クライアントとサービスの通信の場合: `*.do.dsp.mp.microsoft.com` (HTTP ポート 80、HTTPS ポート 443)</span><span class="sxs-lookup"><span data-stu-id="0b101-126">Client to Service communication: `*.do.dsp.mp.microsoft.com` (HTTP Port 80, HTTPS Port 443)</span></span>
- <span data-ttu-id="0b101-127">クライアントとクライアントの通信の場合: TCP ポート7680を受信トラフィック用に開く必要がある</span><span class="sxs-lookup"><span data-stu-id="0b101-127">Client to Client communication: TCP port 7680 should be open for inbound traffic</span></span>

### <span data-ttu-id="0b101-128">同期</span><span class="sxs-lookup"><span data-stu-id="0b101-128">Sync</span></span>

<span data-ttu-id="0b101-129">これらのエンドポイントは、同期データの読み取りと書き込み、安全なデータの権利管理、新しい同期データが利用可能になったときのブラウザーへの通知を管理します。</span><span class="sxs-lookup"><span data-stu-id="0b101-129">These endpoints manage the reading and writing of synced data, rights management for secure data, and notifying the browser when new sync data is available.</span></span>

- <span data-ttu-id="0b101-130">Edge の同期サービス エンドポイント:</span><span class="sxs-lookup"><span data-stu-id="0b101-130">Edge sync service endpoints:</span></span>

  - `https://enterprise.edge.activity.windows.com`
  - `https://edge.activity.windows.com`

- <span data-ttu-id="0b101-131">Azure Information Protection エンドポイント:</span><span class="sxs-lookup"><span data-stu-id="0b101-131">Azure Information Protection endpoints:</span></span>

  - `https://api.aadrm.com` <span data-ttu-id="0b101-132">(ほとんどのテナントの場合)</span><span class="sxs-lookup"><span data-stu-id="0b101-132">(for most tenants)</span></span>
  - `https://api.aadrm.de` <span data-ttu-id="0b101-133">(ドイツのテナントの場合)</span><span class="sxs-lookup"><span data-stu-id="0b101-133">(for tenants in Germany)</span></span>
  - `https://api.aadrm.cn` <span data-ttu-id="0b101-134">(中国のテナントの場合)</span><span class="sxs-lookup"><span data-stu-id="0b101-134">(for tenants in China)</span></span>

- [<span data-ttu-id="0b101-135">Windows 通知サービス エンドポイント</span><span class="sxs-lookup"><span data-stu-id="0b101-135">Windows Notification Service endpoints</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)

## <span data-ttu-id="0b101-136">その他のブラウザー サポート サービス</span><span class="sxs-lookup"><span data-stu-id="0b101-136">Other browser support services</span></span>

<span data-ttu-id="0b101-137">追跡防止、証明書失効リスト、その他のブラウザー コンポーネントの更新プログラムなど、ブラウザー機能のメタデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="0b101-137">Provide metadata for browser features such as tracking protection, certificate revocation lists, and other browser component updates.</span></span> <span data-ttu-id="0b101-138">ダウンロード可能なスペルチェック辞書と広告ブロックの禁止リストを提供します。</span><span class="sxs-lookup"><span data-stu-id="0b101-138">Provide downloadable spellcheck dictionaries and ad-blocking block lists.</span></span> <span data-ttu-id="0b101-139">コレクション、オートフィル、拡張ストアなどのブラウザー機能をサポートするサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0b101-139">Provide services to support browser features such as collections, autofill, and extension store.</span></span>

- `http://edge.microsoft.com/`
- `https://edge.microsoft.com/`

## <span data-ttu-id="0b101-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b101-140">See also</span></span>

- [<span data-ttu-id="0b101-141">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="0b101-141">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="0b101-142">Microsoft Edge ドキュメント ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="0b101-142">Microsoft Edge documentation landing page</span></span>](https://docs.microsoft.com/DeployEdge/)
- [<span data-ttu-id="0b101-143">Windows 10 Enterprise Version 1903 の接続エンドポイントの管理</span><span class="sxs-lookup"><span data-stu-id="0b101-143">Manage connection endpoints for Windows 10 Enterprise, version 1903</span></span>](https://docs.microsoft.com/windows/privacy/manage-windows-1903-endpoints)
