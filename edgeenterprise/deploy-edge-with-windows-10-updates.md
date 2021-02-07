---
title: Windows 10 更新プログラムを適用した Microsoft Edge の展開
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Windows 10 更新プログラムを適用した Microsoft Edge の展開
ms.openlocfilehash: a000e3426792df79d1450c838b7848be10d6b0ca
ms.sourcegitcommit: 16a92a51560fdba6f6480e4533453348f026c7ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "11313947"
---
# <span data-ttu-id="3792d-103">Windows 10 更新プログラムを適用した Microsoft Edge の展開</span><span class="sxs-lookup"><span data-stu-id="3792d-103">Deploy Microsoft Edge with Windows 10 updates</span></span>

<span data-ttu-id="3792d-104">この記事では、Windows 10 更新プログラムを使用して Microsoft Edge を展開しているユーザー向け情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="3792d-104">The article provides information for users who are deploying Microsoft Edge by using Windows 10 updates.</span></span>

## <span data-ttu-id="3792d-105">Windows 10 リリース 20H2 の場合</span><span class="sxs-lookup"><span data-stu-id="3792d-105">For Windows 10 release 20H2</span></span>

<span data-ttu-id="3792d-106">Windows 10 バージョン 20H2 には、Microsoft Edge が既定のブラウザーとして既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="3792d-106">Windows 10 version 20H2 already has Microsoft Edge installed as its default browser.</span></span>

## <span data-ttu-id="3792d-107">Windows 10 の場合、RS4 から 20H1 をリリースします</span><span class="sxs-lookup"><span data-stu-id="3792d-107">For Windows 10 releases RS4 through 20H1</span></span>

<span data-ttu-id="3792d-108">Windows Server Update Services (WSUS) には、Microsoft Edge レガシ デスクトップ アプリを削除して Microsoft Edge に置き換える、RS4 から 20H1 への Windows 10 の各バージョンの更新プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3792d-108">Windows Server Update Services (WSUS) has updates for each version of Windows 10 from RS4 through 20H1 that will remove the Microsoft Edge Legacy desktop app and replace it with Microsoft Edge.</span></span> <span data-ttu-id="3792d-109">詳しくは、[このサポート記事](https://support.microsoft.com/topic/update-in-wsus-for-the-new-microsoft-edge-for-windows-10-version-1809-1903-1909-and-2004-october-29-2020-b4980418-4ec4-dee7-3b17-1c6499bd127c)を参照して、Windows バージョンに最適な WSUS 更新プログラムを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3792d-109">For more information, see [this support article](https://support.microsoft.com/topic/update-in-wsus-for-the-new-microsoft-edge-for-windows-10-version-1809-1903-1909-and-2004-october-29-2020-b4980418-4ec4-dee7-3b17-1c6499bd127c) to find out which WSUS update is right for your Windows version.</span></span>

## <span data-ttu-id="3792d-110">RS4 より前の Windows 10 リリース (および Windows 7、8.1 以前) の場合</span><span class="sxs-lookup"><span data-stu-id="3792d-110">For Windows 10 releases prior to RS4 (and Windows 7, 8.1, and earlier)</span></span>

<span data-ttu-id="3792d-111">Microsoft Edge をインストールする Windows 更新プログラムは、これらのバージョンでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="3792d-111">Windows updates to install Microsoft Edge aren't available for these versions.</span></span> <span data-ttu-id="3792d-112">[Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json) や[ Intune](https://docs.microsoft.com/intune/apps/apps-windows-edge/?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json) など、これらのデバイスに Microsoft Edge を展開するためのその他のオプションを検討します。</span><span class="sxs-lookup"><span data-stu-id="3792d-112">Consider other options for deploying Microsoft Edge to these devices such as [Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json) or [Intune](https://docs.microsoft.com/intune/apps/apps-windows-edge/?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json).</span></span>

## <span data-ttu-id="3792d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3792d-113">See also</span></span>

- [<span data-ttu-id="3792d-114">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="3792d-114">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="3792d-115">Microsoft Edge の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="3792d-115">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)