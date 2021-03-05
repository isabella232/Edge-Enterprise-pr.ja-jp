---
title: Internet Explorer 11 を無効にする
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/04/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge で Internet Explorer 11 を無効にし、Internet Explorer モードを使用する方法をご紹介します。
ms.openlocfilehash: be52f33b091977aff0ca29a4e10d4fc6ea4be957
ms.sourcegitcommit: f63a30c3e64e9e57fd76b6675ddff1fc2bbbeac8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393611"
---
# <a name="disable-internet-explorer-11"></a><span data-ttu-id="566b8-103">Internet Explorer 11 を無効にする</span><span class="sxs-lookup"><span data-stu-id="566b8-103">Disable Internet Explorer 11</span></span>

<span data-ttu-id="566b8-104">この記事では、お使いの環境でスタンドアロン ブラウザー Internet Explorer 11 を無効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="566b8-104">This article describes how to disable Internet Explorer 11 as a standalone browser in your environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="566b8-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="566b8-105">Prerequisites</span></span>

<span data-ttu-id="566b8-106">次の Windows 更新プログラムと Microsoft Edge ソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="566b8-106">The following Windows updates and Microsoft Edge software are required:</span></span>

- <span data-ttu-id="566b8-107">Windows 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="566b8-107">Windows updates</span></span>

  - <span data-ttu-id="566b8-108">Windows 10 バージョン 2004、Windows Server バージョン 2004、Windows 10 バージョン 20H2: [KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) 以降</span><span class="sxs-lookup"><span data-stu-id="566b8-108">Windows 10, version 2004, Windows Server version 2004, Windows 10, version 20H2: [KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) or later</span></span>
  - <span data-ttu-id="566b8-109">Windows 10 バージョン 1909、Windows Server バージョン 1909: [KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) 以降</span><span class="sxs-lookup"><span data-stu-id="566b8-109">Windows 10 version 1909, Windows Server version 1909: [KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) or later</span></span>
  - <span data-ttu-id="566b8-110">Windows 10 バージョン 1809、Windows Server バージョン 1809、および Windows Server 2019: [KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) 以降</span><span class="sxs-lookup"><span data-stu-id="566b8-110">Windows 10 version 1809, Windows Server version 1809, and Windows Server 2019: [KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) or later</span></span>
  - <span data-ttu-id="566b8-111">Windows 10 バージョン 1607、Windows Server 2016: [KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) 以降</span><span class="sxs-lookup"><span data-stu-id="566b8-111">Windows 10, version 1607, Windows Server 2016: [KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) or later</span></span>
   - <span data-ttu-id="566b8-112">Windows 10 初期バージョン (2015 年 7 月): [KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) 以降</span><span class="sxs-lookup"><span data-stu-id="566b8-112">Windows 10 initial version (July 2015): [KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) or later</span></span>
  - <span data-ttu-id="566b8-113">Windows 8.1: [KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) 以降</span><span class="sxs-lookup"><span data-stu-id="566b8-113">Windows 8.1: [KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) or later</span></span>
  - <span data-ttu-id="566b8-114">Windows Server 2012: [KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c) 以降</span><span class="sxs-lookup"><span data-stu-id="566b8-114">Windows Server 2012: [KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c) or later</span></span>
  
- <span data-ttu-id="566b8-115">Microsoft Edge 安定チャネル</span><span class="sxs-lookup"><span data-stu-id="566b8-115">Microsoft Edge Stable Channel</span></span>


## <a name="overview"></a><span data-ttu-id="566b8-116">概要</span><span class="sxs-lookup"><span data-stu-id="566b8-116">Overview</span></span>

<span data-ttu-id="566b8-117">従来の互換性のために Internet Explorer 11 (IE11) が必要な組織では、Microsoft Edge の Internet Explorer モード (IE モード) にシームレスで単一のブラウザー エクスペリエンスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="566b8-117">For organizations that require Internet Explorer 11 (IE11) for legacy compatibility, Internet Explorer mode (IE mode) on Microsoft Edge provides a seamless, single browser experience.</span></span> <span data-ttu-id="566b8-118">ユーザーは、IE11 に切り替えなくても、Microsoft Edge 内から従来のアプリケーションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="566b8-118">Users can access legacy applications from within Microsoft Edge without having to switch back to IE11.</span></span>

<span data-ttu-id="566b8-119">IE モードを構成した後、グループ ポリシーを使用して組織全体の **IE モード機能に影響を与えることなく**、スタンドアロン ブラウザーとして IE11 を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="566b8-119">After you configure IE mode, you can disable IE11 as a standalone browser **without affecting IE mode functionality** across your organization using group policy.</span></span>

> [!NOTE]
> <span data-ttu-id="566b8-120">特定のサイトにスタンドアロンの IE11 アプリが必要で、他のすべてのブラウザー トラフィックを Microsoft Edge にリダイレクトする場合は、[サイト リストに含まれていないすべてのサイトを Microsoft Edge に送信する](https://docs.microsoft.com/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge)ポリシーを構成して、サイトを IE から Microsoft Edge にリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="566b8-120">If you need the standalone IE11 app for specific sites, and want to redirect all other browser traffic to Microsoft Edge, you can configure the [Send all sites not included in the site list to Microsoft Edge](https://docs.microsoft.com/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge) policy to redirect sites from IE to Microsoft Edge.</span></span>

## <a name="user-experience-after-redirecting-traffic-to-microsoft-edge"></a><span data-ttu-id="566b8-121">Microsoft Edge にトラフィックをリダイレクトした後のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="566b8-121">User experience after redirecting traffic to Microsoft Edge</span></span>

<span data-ttu-id="566b8-122">**[スタンドアロン ブラウザーとして Internet Explorer 11 を無効にする]** ポリシーを有効にした場合は、すべての IE11 アクティビティが Microsoft Edge にリダイレクトされ、ユーザーは次のエクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="566b8-122">When you enable the **Disable Internet Explorer 11 as a standalone browser** policy, all IE11 activity is redirected to Microsoft Edge and users have the following experience:</span></span>

- <span data-ttu-id="566b8-123">スタート メニューの IE11 アイコンは削除されますが、タスク バー上の IE11 アイコンは残ります。</span><span class="sxs-lookup"><span data-stu-id="566b8-123">The IE11 icon on the Start Menu will be removed, but the one on the taskbar will remain.</span></span>
- <span data-ttu-id="566b8-124">ユーザーが IE11 を使用するショートカットまたはファイルの関連付けを起動しようとすると、Microsoft Edge で同じファイルまたはURL を開くようにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="566b8-124">When users try to launch shortcuts or file associations that use IE11, they will be redirected to open the same file/URL in Microsoft Edge.</span></span>
- <span data-ttu-id="566b8-125">ユーザーが IExplore.exe バイナリを直接呼び出して IE11 を起動しようとすると、代わりに Microsoft Edge が起動します。</span><span class="sxs-lookup"><span data-stu-id="566b8-125">When users try to launch IE11 by directly invoking the iexplore.exe binary, Microsoft Edge will launch instead.</span></span>

<span data-ttu-id="566b8-126">このエクスペリエンスのポリシー設定の一環として、オプションで IE11 を起動しようとするユーザーごとにダイレクト メッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="566b8-126">As part of setting the policy for this experience, you can optionally show a redirect message for each user who tries to launch IE11.</span></span> <span data-ttu-id="566b8-127">このメッセージは、"常に" または "ユーザーごとに 1 回" を表示するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="566b8-127">This message can be set to display "Always" or "Once per user".</span></span> <span data-ttu-id="566b8-128">既定では、次のスクリーンショットに表示されるリダイレクト メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="566b8-128">By default, the redirect message shown in the next screenshot is never shown.</span></span>

:::image type="content" source="media/edge-ie-disable-ie11/disable-ie-redirect-msg.png" alt-text="Microsoft Edge へのリダイレクトがアクティブな場合は、IE を開こうとすると警告します。":::

<span data-ttu-id="566b8-130">エンタープライズ モード サイト一覧に IE11 アプリで開くよう構成されたアプリケーションが含まれている場合、このポリシーを使用して IE11 を無効にすると、Microsoft Edge の IE モードで開きます。</span><span class="sxs-lookup"><span data-stu-id="566b8-130">If your Enterprise Mode Site List contains applications that are configured to open in the IE11 app and you disable IE11 with this policy, they will open in IE mode on Microsoft Edge.</span></span>
> [!NOTE]
> <span data-ttu-id="566b8-131">サイトが IE11 で開くように構成されていて、かつ IE11 を無効にするポリシーが構成されている場合、ユーザー フローに問題があることが知られています。</span><span class="sxs-lookup"><span data-stu-id="566b8-131">There is a known issue with the user flow when a site is configured to open in IE11 and the disable IE11 policy is set.</span></span> <span data-ttu-id="566b8-132">積極的に調査している問題。</span><span class="sxs-lookup"><span data-stu-id="566b8-132">The issue being actively investigated.</span></span>

## <a name="disable-internet-explorer-11-as-a-standalone-browser"></a><span data-ttu-id="566b8-133">スタンドアロン ブラウザーとして Internet Explorer 11 を無効にする</span><span class="sxs-lookup"><span data-stu-id="566b8-133">Disable Internet Explorer 11 as a standalone browser</span></span>

<span data-ttu-id="566b8-134">グループ ポリシーを使用して Internet Explorer 11 を無効にするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="566b8-134">To disable Internet Explorer 11 using group policy, follow these steps:</span></span>

1. <span data-ttu-id="566b8-135">最新の  [Microsoft Edge ポリシー テンプレート](https://www.microsoft.com/edge/business/download)をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="566b8-135">Download and install the latest [Microsoft Edge Policy Template](https://www.microsoft.com/edge/business/download).</span></span>
2. <span data-ttu-id="566b8-136">グループ ポリシー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="566b8-136">Open the Group Policy Editor.</span></span>
3. <span data-ttu-id="566b8-137">\*\*\*[コンピューターの構成]、[管理用テンプレート]、[Windows コンポーネント/Internet Explorer] \*\*\*の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="566b8-137">Go to ***Computer Configuration/Administrative Templates/Windows Components/Internet Explorer***.</span></span> 
4. <span data-ttu-id="566b8-138"> \*\*[スタンドアロン ブラウザーとして Internet Explorer 11 を無効にする] \*\*をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="566b8-138">Double-click **Disable Internet Explorer 11 as a standalone browser**.</span></span>
5. <span data-ttu-id="566b8-139"> *\*[有効化]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="566b8-139">Select **Enabled**.</span></span>
6. <span data-ttu-id="566b8-140"> \*\*[オプション] \*\*で、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="566b8-140">Under **Options**, pick one of the following values:</span></span>

   - <span data-ttu-id="566b8-141">**[なし]**  IE11 が無効であることをユーザーに通知しない場合。</span><span class="sxs-lookup"><span data-stu-id="566b8-141">**Never** if you don’t want to notify users that IE11 is disabled.</span></span>
   - <span data-ttu-id="566b8-142">**[常に]**  IE11 からリダイレクトされるたびにユーザーに通知する場合。</span><span class="sxs-lookup"><span data-stu-id="566b8-142">**Always** if you want to notify users every time they're redirected from IE11.</span></span>
   - <span data-ttu-id="566b8-143">**[ユーザーごとに 1 回]**  リダイレクトされた初回のみユーザーに通知する場合。</span><span class="sxs-lookup"><span data-stu-id="566b8-143">**Once per user** if you want to notify users only the first time they are redirected.</span></span>

7. <span data-ttu-id="566b8-144"> *\*[OK]**  または  *\*[適用]**  をクリックして、このポリシー設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="566b8-144">Click **OK** or **Apply** to save this policy setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="566b8-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="566b8-145">See also</span></span>

- [<span data-ttu-id="566b8-146">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="566b8-146">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="566b8-147">IE モードの概要</span><span class="sxs-lookup"><span data-stu-id="566b8-147">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="566b8-148">その他のエンタープライズ モード情報</span><span class="sxs-lookup"><span data-stu-id="566b8-148">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
