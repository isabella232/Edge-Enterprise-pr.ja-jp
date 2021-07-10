---
title: Microsoft Edge Stable チャネル更新プログラムのプログレッシブ ロールアウト
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Stable チャネル更新プログラムのプログレッシブ ロールアウト
ms.openlocfilehash: bdcefdc118125d67057fa77513bd732cff6882e3
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642293"
---
# <a name="progressive-rollouts-for-microsoft-edge-stable-channel-updates"></a><span data-ttu-id="ef461-103">Microsoft Edge Stable チャネル更新プログラムのプログレッシブ ロールアウト</span><span class="sxs-lookup"><span data-stu-id="ef461-103">Progressive rollouts for Microsoft Edge Stable channel updates</span></span>

<span data-ttu-id="ef461-104">Microsoft Edge 83 リリース以降、Microsoft Edge Stable チャネルへのメジャーアップデートのプログレッシブ ロールアウトを数日間にわたって実行します。</span><span class="sxs-lookup"><span data-stu-id="ef461-104">Starting with Microsoft Edge 83 release, we will perform gradual rollouts of major updates to Microsoft Edge Stable channel over the span of a few days.</span></span> <span data-ttu-id="ef461-105">このプログレッシブ ロールアウトにより、アップグレードを監視し、組織全体でブラウザーを安全に更新できます。</span><span class="sxs-lookup"><span data-stu-id="ef461-105">This progressive rollout allows us to monitor upgrades and safely update the browser across the organization.</span></span>

> [!NOTE]
> <span data-ttu-id="ef461-106">これは、Microsoft Edge Stable チャネルバージョン 83 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ef461-106">This applies to Microsoft Edge Stable channel version 83 or later.</span></span>

## <a name="why-do-we-need-progressive-rollout"></a><span data-ttu-id="ef461-107">なぜプログレッシブ ロールアウトが必要なのですか。</span><span class="sxs-lookup"><span data-stu-id="ef461-107">Why do we need progressive rollout?</span></span>

<span data-ttu-id="ef461-108">更新プログラムの状態を注意深く監視し、数日間にわたって更新プログラムを展開することにより、新しい更新プログラムで発生する可能性がある問題の影響を抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="ef461-108">By monitoring the health of our updates closely and rolling out the updates over the course of several days, we can limit the impact of issues that might occur with the new update.</span></span> <span data-ttu-id="ef461-109">Microsoft Edgeリリース83では、Windows 7、Windows 8 と 8.1、および Windows 10 バージョンのすべての Microsoft Edge でプログレッシブロールアウトが有効になります。</span><span class="sxs-lookup"><span data-stu-id="ef461-109">With Microsoft Edge release 83, Progressive Rollouts will be enabled for all Windows 7, Windows 8 & 8.1, and Windows 10 versions of Microsoft Edge.</span></span> <span data-ttu-id="ef461-110">準備ができ次第、Mac 上の Microsoft Edge もサポートします。</span><span class="sxs-lookup"><span data-stu-id="ef461-110">We will support Microsoft Edge on Mac as soon as it is ready.</span></span>

## <a name="how-will-the-updates-work"></a><span data-ttu-id="ef461-111">更新プログラムはどのように機能しますか。</span><span class="sxs-lookup"><span data-stu-id="ef461-111">How will the updates work?</span></span>

<span data-ttu-id="ef461-112">Microsoft Edge の各インストールには、アップグレード値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ef461-112">Each installation of Microsoft Edge is assigned an upgrade value.</span></span> <span data-ttu-id="ef461-113">段階的なロールアウトを開始すると、デバイスの値がアップグレード値の範囲内にある場合は、更新プログラムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef461-113">When we start rolling out incrementally, you'll see the update when the value on your device falls within the upgrade value range.</span></span> <span data-ttu-id="ef461-114">ロールアウトが (数日以内に) 進行して、最終的にすべてのユーザーが更新を取得します。</span><span class="sxs-lookup"><span data-stu-id="ef461-114">As the rollout progresses (within a few days), all users will eventually get the update.</span></span> <span data-ttu-id="ef461-115">重要なセキュリティ修正が含まれているブラウザの更新は、重要なセキュリティ修正が含まれていない更新よりも展開の頻度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="ef461-115">Browser updates with critical security fixes will have a faster rollout cadence than updates that don't have critical security fixes.</span></span> <span data-ttu-id="ef461-116">これは、脆弱性からの保護を迅速にするために行われます。</span><span class="sxs-lookup"><span data-stu-id="ef461-116">This is done to ensure prompt protection from vulnerabilities.</span></span>

## <a name="how-does-this-affect-enterprises"></a><span data-ttu-id="ef461-117">これは企業にどのように影響しますか。</span><span class="sxs-lookup"><span data-stu-id="ef461-117">How does this affect enterprises?</span></span>

<span data-ttu-id="ef461-118">Microsoft Edge アーティファクト は、Microsoft Intune、Windows Server Update Service (WSUS)、Configuration Manager などの複数のメカニズムを使用して企業に配布されます。</span><span class="sxs-lookup"><span data-stu-id="ef461-118">Microsoft Edge artifacts are distributed to enterprises using multiple mechanisms such as Microsoft Intune, Windows Server Update Service (WSUS), and Configuration Manager.</span></span> <span data-ttu-id="ef461-119">これらの展開ツールは、プログレッシブロールアウトによって動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="ef461-119">These deployment tools behave differently with respect to Progressive Rollout:</span></span>

- <span data-ttu-id="ef461-120">Microsoft Intune を介して配布を管理する企業は、自動更新に登録されています。</span><span class="sxs-lookup"><span data-stu-id="ef461-120">Enterprises that manage distribution via Microsoft Intune are registered for auto-updates.</span></span> <span data-ttu-id="ef461-121">プログレッシブロールアウトが使用され、すべてのユーザーに数日で更新が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef461-121">Progressive Rollout is used, and all the users will see an update in a few days.</span></span>
- <span data-ttu-id="ef461-122">WSUS (Windows Server Update Services) または構成マネージャーを介して配布を管理する企業は、自動更新に登録されていません。</span><span class="sxs-lookup"><span data-stu-id="ef461-122">Enterprises that manage distribution through WSUS (Windows Server Update Services) or Configuration Manager are not registered for auto-updates.</span></span> <span data-ttu-id="ef461-123">管理者は、最初から利用可能なアップデートを管理し、適用します。</span><span class="sxs-lookup"><span data-stu-id="ef461-123">Administrators manage and apply the updates that will be available from the start.</span></span> <span data-ttu-id="ef461-124">プログレッシブロールアウトはこのプロセスには影響しません。</span><span class="sxs-lookup"><span data-stu-id="ef461-124">Progressive Rollout does not affect this process.</span></span>

<span data-ttu-id="ef461-125">懸念や質問がある場合は、ユーザーの声、アプリケーション内のフィードバックボタン、またはコメントの下部を利用して、貴重なフィードバックを共有してください。</span><span class="sxs-lookup"><span data-stu-id="ef461-125">Please share your valuable feedback through user voice, the in-application feedback button, or below in the comments if you have any concerns or questions.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef461-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef461-126">See also</span></span>

- [<span data-ttu-id="ef461-127">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="ef461-127">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
