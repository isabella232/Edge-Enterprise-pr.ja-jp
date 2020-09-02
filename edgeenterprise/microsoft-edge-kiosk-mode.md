---
title: Microsoft Edge キオスク モード
ms.author: brianalt
author: brianalt
manager: seanlynd
ms.date: 01/16/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge キオスク モード
ms.openlocfilehash: 7a690820752b5361349bf394055a737bd8175215
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980520"
---
# <span data-ttu-id="e7511-103">Microsoft Edge キオスク モード</span><span class="sxs-lookup"><span data-stu-id="e7511-103">Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="e7511-104">この記事では、Microsoft Edge (version 77 以降) のキオスク モード オプションの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="e7511-104">This article provides an overview of the Microsoft Edge (version 77 or later) kiosk mode options.</span></span> <span data-ttu-id="e7511-105">また Microsoft Edge レガシのキオスク モード (version 45 以前) を使用するための要件についても説明します。</span><span class="sxs-lookup"><span data-stu-id="e7511-105">It also covers what's required to continue using Microsoft Edge Legacy kiosk mode (version 45 and earlier.)</span></span>

<span data-ttu-id="e7511-106">Microsoft Edge レガシのキオスク モード (version 45 以前) については、「[Microsoft Edge キオスク モードの展開](https://aka.ms/edgekioskmode)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e7511-106">For information about Microsoft Edge Legacy kiosk mode (version 45 and earlier) see [Deploy Microsoft Edge kiosk mode](https://aka.ms/edgekioskmode).</span></span>

## <span data-ttu-id="e7511-107">割り当てられたアクセスによる Microsoft Edge の使用</span><span class="sxs-lookup"><span data-stu-id="e7511-107">Microsoft Edge with assigned access</span></span>

<span data-ttu-id="e7511-108">Microsoft Edge は、Windows 10 で[複数アプリの割り当てられたアクセス](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)によって実行できます。これは Microsoft Edge レガシでの "通常の閲覧" タイプのキオスク モードに相当します。</span><span class="sxs-lookup"><span data-stu-id="e7511-108">Microsoft Edge can be run with [multi-app assigned access](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing” kiosk mode type.</span></span> <span data-ttu-id="e7511-109">複数アプリの割り当てられたアクセスで Microsoft Edge を構成するには、[複数アプリ キオスクの設定](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)方法の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e7511-109">To configure Microsoft Edge with multi-app assigned access follow the instructions on how to [Set up a multi-app kiosk](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="e7511-110">Microsoft Edge Stable チャネルの AUMID は **MSEdge** です。</span><span class="sxs-lookup"><span data-stu-id="e7511-110">The AUMID for the Microsoft Edge Stable channel is **MSEdge**.</span></span>

<span data-ttu-id="e7511-111">複数アプリの割り当てられたアクセスで Microsoft Edge を使用する場合は、[Microsoft Edge ブラウザーポリシー](microsoft-edge-policies.md)を使用して、固有の要件を満たすことができるように閲覧エクスペリエンスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e7511-111">When using Microsoft Edge with multi-app assigned access you can use the [Microsoft Edge browser policies](microsoft-edge-policies.md) to configure the browsing experience to meet your unique requirements.</span></span>

<span data-ttu-id="e7511-112">現在 Microsoft Edge では、シングル アプリの割り当てられたアクセス用の同じ Microsoft Edge レガシ キオスク モード タイプや、複数アプリの割り当てられたアクセスでの "公共閲覧" キオスク モード タイプがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e7511-112">Today Microsoft Edge does not support the same Microsoft Edge Legacy kiosk mode types for single-app assigned access and the "Public browsing" kiosk mode type in multi-app assigned access.</span></span> <span data-ttu-id="e7511-113">シングル アプリの割り当てられたアクセスのキオスク デバイス用にブラウザーが必要であれば、[Microsoft Edge レガシ キオスク モード](https://aka.ms/edgekioskmode)または [Microsoft キオスク ブラウザー アプリ](https://www.microsoft.com/p/kiosk-browser/9ngb5s5xg2kp?activetab=pivot:overviewtab)の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e7511-113">If you need a browser for your single-app assigned access kiosk device, we recommend using [Microsoft Edge Legacy kiosk mode](https://aka.ms/edgekioskmode) or the [Microsoft Kiosk Browser app](https://www.microsoft.com/p/kiosk-browser/9ngb5s5xg2kp?activetab=pivot:overviewtab).</span></span> 

## <span data-ttu-id="e7511-114">Microsoft Edge "--kiosk" コマンド ライン パラメーター</span><span class="sxs-lookup"><span data-stu-id="e7511-114">Microsoft Edge “--kiosk” command line parameter</span></span>

<span data-ttu-id="e7511-115">"`--kiosk`" コマンド ライン パラメーターを使用すると、キオスク モードで Microsoft Edge を起動できます。</span><span class="sxs-lookup"><span data-stu-id="e7511-115">You can launch Microsoft Edge in kiosk mode using the “`--kiosk`” command line parameter.</span></span> <span data-ttu-id="e7511-116">このとき、ブラウザーが全画面で開き、全画面のキーボード ショートカット (F11) が無効になります。</span><span class="sxs-lookup"><span data-stu-id="e7511-116">This opens the browser in full screen with the full screen keyboard shortcut disabled (F11).</span></span> <span data-ttu-id="e7511-117">これを行うには、ターゲットを次のように設定してショートカットを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7511-117">To accomplish this, create a shortcut with the target set to:</span></span><br>
*`"<local path>\msedge.exe" --kiosk http://bing.com`*

> [!NOTE]
> <span data-ttu-id="e7511-118">"`--kiosk`" パラメーターを指定しても、ユーザーによる Windows キーボード ショートカットへのアクセスは無効にならず、他のアプリケーションの実行も回避できません。</span><span class="sxs-lookup"><span data-stu-id="e7511-118">The "`--kiosk`" parameter will not prevent the user from accessing Windows keyboard shortcuts and will not prevent other applications from running.</span></span> <span data-ttu-id="e7511-119">このような種類の制御を実現するには、[AppLocker の使用による Windows 10 キオスクの作成](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-applocker)や[キーボード フィルターの使用](https://docs.microsoft.com/windows-hardware/customize/enterprise/keyboardfilter)を検討してください。</span><span class="sxs-lookup"><span data-stu-id="e7511-119">To accomplish this type of control, consider using [AppLocker to create a Windows 10 kiosk](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-applocker) and [Keyboard Filter](https://docs.microsoft.com/windows-hardware/customize/enterprise/keyboardfilter).</span></span>

<span data-ttu-id="e7511-120">キオスク モードを終了してブラウザーを閉じるには、Alt キーを押しながら F4 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e7511-120">To exit kiosk mode and close the browser use alt+F4.</span></span>

## <span data-ttu-id="e7511-121">Microsoft Edge レガシ キオスク モードのサポート</span><span class="sxs-lookup"><span data-stu-id="e7511-121">Support for Microsoft Edge Legacy kiosk mode</span></span>

<span data-ttu-id="e7511-122">新しいバージョンの Microsoft Edge Stable チャネルがインストールされると、Microsoft Edge レガシが非表示になり Microsoft Edge レガシを起動しようとすると、新しいバージョンにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="e7511-122">When the new version of Microsoft Edge Stable channel is installed, Microsoft Edge Legacy is hidden and all attempts to launch Microsoft Edge Legacy are redirected to the new version.</span></span> <span data-ttu-id="e7511-123">以下の情報も参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7511-123">For information about:</span></span>

- <span data-ttu-id="e7511-124">Windows 更新プログラムの要件については、「[次のバージョンの Microsoft Edge をサポートする Windows 更新プログラム](microsoft-edge-sysupdate-windows-updates.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e7511-124">Windows update requirements, see [Windows updates to support the next version of Microsoft Edge](microsoft-edge-sysupdate-windows-updates.md)</span></span> 
- <span data-ttu-id="e7511-125">Microsoft Edge のインストール後に Microsoft Edge レガシにアクセスする方法については、「[Microsoft Edge の新しいバージョンをインストールした後 Microsoft Edge レガシにアクセスする](microsoft-edge-sysupdate-access-old-edge.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e7511-125">Accessing Microsoft Edge Legacy after installing Microsoft Edge,  see [Access Microsoft Edge Legacy after installing the new version of Microsoft Edge](microsoft-edge-sysupdate-access-old-edge.md)</span></span>
 
<span data-ttu-id="e7511-126">キオスク デバイスで Microsoft Edge レガシ キオスク モードを引き続き使用するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7511-126">To continue using Microsoft Edge Legacy kiosk mode on your kiosk devices take one of the following actions:</span></span> 

- <span data-ttu-id="e7511-127">Microsoft Edge Stable チャネルをインストールする場合や、インストールを許可する場合、またはキオスク デバイスに既にインストールされている場合は、Microsoft Edge の [[Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する]](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs) ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="e7511-127">If you plan to install Microsoft Edge Stable channel, want to allow it to be installed, or if it's already installed on your kiosk device deploy the Microsoft Edge [Allow Microsoft Edge Side by Side browser experience](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs) policy.</span></span>
- <span data-ttu-id="e7511-128">キオスク デバイスへの Microsoft Edge Stable チャネルのインストールを回避するには、Stable チャネルに Microsoft Edge の [[インストールの既定の動作を許可する]](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allow-installation-default) ポリシーを展開するか、[Blocker Toolkit を使用して Microsoft Edge の自動配布を無効にする](microsoft-edge-blocker-toolkit.md)ことを検討します。</span><span class="sxs-lookup"><span data-stu-id="e7511-128">To prevent Microsoft Edge Stable channel from being installed on your kiosk devices deploy the Microsoft Edge [Allow installation default](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allow-installation-default) policy for Stable channel or consider using the [Blocker toolkit to disable automatic delivery of Microsoft Edge](microsoft-edge-blocker-toolkit.md).</span></span> 

## <span data-ttu-id="e7511-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7511-129">See also</span></span>

- [<span data-ttu-id="e7511-130">Windows デスクトップ エディションでのキオスクおよびデジタル サイネージの構成</span><span class="sxs-lookup"><span data-stu-id="e7511-130">Configure kiosks and digital signs on Windows desktop editions</span></span>](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [<span data-ttu-id="e7511-131">Microsoft Edge レガシ キオスク モードの展開</span><span class="sxs-lookup"><span data-stu-id="e7511-131">Deploy Microsoft Edge Legacy kiosk mode</span></span>](https://aka.ms/edgekioskmode) 
- [<span data-ttu-id="e7511-132">Microsoft Edge の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="e7511-132">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="e7511-133">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="e7511-133">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
