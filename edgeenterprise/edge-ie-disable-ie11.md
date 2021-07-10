---
title: Internet Explorer 11 を無効にする
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge で Internet Explorer 11 を無効にし、Internet Explorer モードを使用する方法をご紹介します。
ms.openlocfilehash: 9ea99c794dc06a0eb5167e56e72b6e7b6ee70212
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641513"
---
# <a name="disable-internet-explorer-11"></a><span data-ttu-id="62670-103">Internet Explorer 11 を無効にする</span><span class="sxs-lookup"><span data-stu-id="62670-103">Disable Internet Explorer 11</span></span>

>[!Note]
> <span data-ttu-id="62670-104">Internet Explorer 11 デスクトップ アプリケーションは廃止され、2022 年 6 月 15 日にサポートが終了します (スコープ内の一覧については、[FAQ を参照してください](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549))。</span><span class="sxs-lookup"><span data-stu-id="62670-104">The Internet Explorer 11 desktop application will be retired and go out of support on June 15, 2022 (for a list of what’s in scope, [see the FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span></span> <span data-ttu-id="62670-105">現在使用しているものと同じ IE11 アプリとサイトを、Internet Explorer モードの Microsoft Edge で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="62670-105">The same IE11 apps and sites you use today can open in Microsoft Edge with Internet Explorer mode.</span></span> <span data-ttu-id="62670-106">[こちらをご覧ください](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。</span><span class="sxs-lookup"><span data-stu-id="62670-106">[Learn more here](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span></span>

<span data-ttu-id="62670-107">この記事では、お使いの環境でスタンドアロン ブラウザーとして Internet Explorer 11 を無効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="62670-107">This article describes how to disable Internet Explorer 11 as a standalone browser in your environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="62670-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="62670-108">Prerequisites</span></span>

<span data-ttu-id="62670-109">次の Windows 更新プログラムと Microsoft Edge ソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="62670-109">The following Windows updates and Microsoft Edge software are required:</span></span>

- <span data-ttu-id="62670-110">Windows 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="62670-110">Windows updates</span></span>

  - <span data-ttu-id="62670-111">Windows 10 バージョン 2004、Windows Server バージョン 2004、Windows 10 バージョン 20H2: [KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) 以降</span><span class="sxs-lookup"><span data-stu-id="62670-111">Windows 10, version 2004, Windows Server version 2004, Windows 10, version 20H2: [KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) or later</span></span>
  - <span data-ttu-id="62670-112">Windows 10 バージョン 1909、Windows Server バージョン 1909: [KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) 以降</span><span class="sxs-lookup"><span data-stu-id="62670-112">Windows 10 version 1909, Windows Server version 1909: [KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) or later</span></span>
  - <span data-ttu-id="62670-113">Windows 10 バージョン 1809、Windows Server バージョン 1809、および Windows Server 2019: [KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) 以降</span><span class="sxs-lookup"><span data-stu-id="62670-113">Windows 10 version 1809, Windows Server version 1809, and Windows Server 2019: [KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) or later</span></span>
  - <span data-ttu-id="62670-114">Windows 10 バージョン 1607、Windows Server 2016: [KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) 以降</span><span class="sxs-lookup"><span data-stu-id="62670-114">Windows 10, version 1607, Windows Server 2016: [KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) or later</span></span>
   - <span data-ttu-id="62670-115">Windows 10 初期バージョン (2015 年 7 月): [KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) 以降</span><span class="sxs-lookup"><span data-stu-id="62670-115">Windows 10 initial version (July 2015): [KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) or later</span></span>
  - <span data-ttu-id="62670-116">Windows 8.1: [KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) 以降</span><span class="sxs-lookup"><span data-stu-id="62670-116">Windows 8.1: [KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) or later</span></span>
  - <span data-ttu-id="62670-117">Windows Server 2012: [KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c) 以降</span><span class="sxs-lookup"><span data-stu-id="62670-117">Windows Server 2012: [KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c) or later</span></span>
  
- <span data-ttu-id="62670-118">Microsoft Edge 安定チャネル</span><span class="sxs-lookup"><span data-stu-id="62670-118">Microsoft Edge Stable Channel</span></span>


## <a name="overview"></a><span data-ttu-id="62670-119">概要</span><span class="sxs-lookup"><span data-stu-id="62670-119">Overview</span></span>

<span data-ttu-id="62670-120">従来の互換性のために Internet Explorer 11 (IE11) が必要な組織では、Microsoft Edge の Internet Explorer モード (IE モード) にシームレスで単一のブラウザー エクスペリエンスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="62670-120">For organizations that require Internet Explorer 11 (IE11) for legacy compatibility, Internet Explorer mode (IE mode) on Microsoft Edge provides a seamless, single browser experience.</span></span> <span data-ttu-id="62670-121">ユーザーは、IE11 に切り替えなくても、Microsoft Edge 内から従来のアプリケーションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="62670-121">Users can access legacy applications from within Microsoft Edge without having to switch back to IE11.</span></span>

<span data-ttu-id="62670-122">IE モードを構成した後、グループ ポリシーを使用して組織全体の **IE モード機能に影響を与えることなく**、スタンドアロン ブラウザーとして IE11 を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="62670-122">After you configure IE mode, you can disable IE11 as a standalone browser **without affecting IE mode functionality** across your organization using group policy.</span></span>

> [!NOTE]
> <span data-ttu-id="62670-123">特定のサイトにスタンドアロンの IE11 アプリが必要で、他のすべてのブラウザー トラフィックを Microsoft Edge にリダイレクトする場合は、[サイト リストに含まれていないすべてのサイトを Microsoft Edge に送信する](./edge-ie-mode-policies.md#redirect-sites-from-ie-to-microsoft-edge)ポリシーを構成して、サイトを IE から Microsoft Edge にリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="62670-123">If you need the standalone IE11 app for specific sites, and want to redirect all other browser traffic to Microsoft Edge, you can configure the [Send all sites not included in the site list to Microsoft Edge](./edge-ie-mode-policies.md#redirect-sites-from-ie-to-microsoft-edge) policy to redirect sites from IE to Microsoft Edge.</span></span>

## <a name="user-experience-after-redirecting-traffic-to-microsoft-edge"></a><span data-ttu-id="62670-124">Microsoft Edge にトラフィックをリダイレクトした後のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="62670-124">User experience after redirecting traffic to Microsoft Edge</span></span>

<span data-ttu-id="62670-125">**[スタンドアロン ブラウザーとして Internet Explorer 11 を無効にする]** ポリシーを有効にした場合は、すべての IE11 アクティビティが Microsoft Edge にリダイレクトされ、ユーザーは次のエクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="62670-125">When you enable the **Disable Internet Explorer 11 as a standalone browser** policy, all IE11 activity is redirected to Microsoft Edge and users have the following experience:</span></span>

- <span data-ttu-id="62670-126">スタート メニューの IE11 アイコンは削除されますが、タスク バー上の IE11 アイコンは残ります。</span><span class="sxs-lookup"><span data-stu-id="62670-126">The IE11 icon on the Start Menu will be removed, but the one on the taskbar will remain.</span></span>
- <span data-ttu-id="62670-127">ユーザーが IE11 を使用するショートカットまたはファイルの関連付けを起動しようとすると、Microsoft Edge で同じファイルまたはURL を開くようにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="62670-127">When users try to launch shortcuts or file associations that use IE11, they will be redirected to open the same file/URL in Microsoft Edge.</span></span>
- <span data-ttu-id="62670-128">ユーザーが IExplore.exe バイナリを直接呼び出して IE11 を起動しようとすると、代わりに Microsoft Edge が起動します。</span><span class="sxs-lookup"><span data-stu-id="62670-128">When users try to launch IE11 by directly invoking the iexplore.exe binary, Microsoft Edge will launch instead.</span></span>

<span data-ttu-id="62670-129">このエクスペリエンスのポリシー設定の一環として、オプションで IE11 を起動しようとするユーザーごとにダイレクト メッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="62670-129">As part of setting the policy for this experience, you can optionally show a redirect message for each user who tries to launch IE11.</span></span> <span data-ttu-id="62670-130">このメッセージは、"常に" または "ユーザーごとに 1 回" を表示するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="62670-130">This message can be set to display "Always" or "Once per user".</span></span> <span data-ttu-id="62670-131">既定では、次のスクリーンショットに表示されるリダイレクト メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="62670-131">By default, the redirect message shown in the next screenshot is never shown.</span></span>

:::image type="content" source="media/edge-ie-disable-ie11/disable-ie-redirect-msg.png" alt-text="Microsoft Edge へのリダイレクトがアクティブな場合は、IE を開こうとすると警告します。":::

<span data-ttu-id="62670-133">エンタープライズ モード サイト一覧に IE11 アプリで開くよう構成されたアプリケーションが含まれている場合、このポリシーを使用して IE11 を無効にすると、Microsoft Edge の IE モードで開きます。</span><span class="sxs-lookup"><span data-stu-id="62670-133">If your Enterprise Mode Site List contains applications that are configured to open in the IE11 app and you disable IE11 with this policy, they will open in IE mode on Microsoft Edge.</span></span>
> [!NOTE]
> <span data-ttu-id="62670-134">サイトが IE11 アプリケーションで開くように構成されていて、かつ IE11 を無効にするポリシーが構成されている場合、ユーザー フローに問題があることが知られています。</span><span class="sxs-lookup"><span data-stu-id="62670-134">There was a known issue with the user flow when a site is configured to open in the IE11 application and the disable IE11 policy is set.</span></span> <span data-ttu-id="62670-135">この問題は、Microsoft Edge バージョン 91.0.840.0 以降で修正されています。</span><span class="sxs-lookup"><span data-stu-id="62670-135">The issue has been fixed in Microsoft Edge versions 91.0.840.0 or later.</span></span>

## <a name="disable-internet-explorer-11-as-a-standalone-browser"></a><span data-ttu-id="62670-136">スタンドアロン ブラウザーとして Internet Explorer 11 を無効にする</span><span class="sxs-lookup"><span data-stu-id="62670-136">Disable Internet Explorer 11 as a standalone browser</span></span>

<span data-ttu-id="62670-137">グループ ポリシーを使用して Internet Explorer 11 を無効にするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="62670-137">To disable Internet Explorer 11 using group policy, follow these steps:</span></span>

1. <span data-ttu-id="62670-138">前提条件のオペレーティング システムの更新プログラムがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="62670-138">Ensure you have the pre-requisite operating system updates.</span></span> <span data-ttu-id="62670-139">この手順では、コンピューター上の ADMX ファイル (具体的には inetres.adml および inetres.admx) を直接更新します。</span><span class="sxs-lookup"><span data-stu-id="62670-139">This step will update the ADMX files on your machine directly (specifically inetres.adml and inetres.admx).</span></span> <span data-ttu-id="62670-140">セントラル ストアを更新する場合は、前提条件の更新プログラムがあるコンピューターから .adml ファイルと .admx ファイルをコピーする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="62670-140">Please note that if you want to update your Central Store, you will need to copy over the .adml and .admx files from a machine that has the pre-requisite updates.</span></span> <span data-ttu-id="62670-141">詳しくは、「[セントラル ストアの作成と管理](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="62670-141">For more information, see [Create and manage Central Store](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)</span></span>
2. <span data-ttu-id="62670-142">グループ ポリシー エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="62670-142">Open the Group Policy Editor.</span></span>
3. <span data-ttu-id="62670-143">[\**_Computer Configuration/Administrative Templates/Windows コンポーネント/Internet Explorer_] に移動_* します。</span><span class="sxs-lookup"><span data-stu-id="62670-143">Go to \**_Computer Configuration/Administrative Templates/Windows Components/Internet Explorer_*_.</span></span> 
4. <span data-ttu-id="62670-144">_\*Disable Internet Explorer 11 をスタンドアロン ブラウザー\*\*としてダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="62670-144">Double-click _\*Disable Internet Explorer 11 as a standalone browser\*\*.</span></span>
5. <span data-ttu-id="62670-145"> *\*[有効化]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="62670-145">Select **Enabled**.</span></span>
6. <span data-ttu-id="62670-146"> \*\*[オプション] \*\*で、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="62670-146">Under **Options**, pick one of the following values:</span></span>

   - <span data-ttu-id="62670-147">**[なし]**  IE11 が無効であることをユーザーに通知しない場合。</span><span class="sxs-lookup"><span data-stu-id="62670-147">**Never** if you don’t want to notify users that IE11 is disabled.</span></span>
   - <span data-ttu-id="62670-148">**[常に]**  IE11 からリダイレクトされるたびにユーザーに通知する場合。</span><span class="sxs-lookup"><span data-stu-id="62670-148">**Always** if you want to notify users every time they're redirected from IE11.</span></span>
   - <span data-ttu-id="62670-149">**[ユーザーごとに 1 回]**  リダイレクトされた初回のみユーザーに通知する場合。</span><span class="sxs-lookup"><span data-stu-id="62670-149">**Once per user** if you want to notify users only the first time they are redirected.</span></span>

7. <span data-ttu-id="62670-150"> *\*[OK]**  または  *\*[適用]**  をクリックして、このポリシー設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="62670-150">Click **OK** or **Apply** to save this policy setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="62670-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="62670-151">See also</span></span>

- [<span data-ttu-id="62670-152">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="62670-152">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="62670-153">IE モードの概要</span><span class="sxs-lookup"><span data-stu-id="62670-153">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="62670-154">その他のエンタープライズ モード情報</span><span class="sxs-lookup"><span data-stu-id="62670-154">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
