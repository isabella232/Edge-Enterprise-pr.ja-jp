---
title: ユーザー環境内の Microsoft Edge
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: ユーザー環境内の Microsoft Edge
ms.openlocfilehash: e1418d21ff9e541d83d5b86baf5ff25c50d2299d
ms.sourcegitcommit: 16a92a51560fdba6f6480e4533453348f026c7ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "11313948"
---
# <span data-ttu-id="ed7da-103">ユーザー環境内の Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ed7da-103">Microsoft Edge in your environment</span></span>

<span data-ttu-id="ed7da-104">この記事では、Microsoft Edge レガシがサービスを終了したときに Microsoft Edge を展開する準備をする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed7da-104">This article describes how to prepare to deploy Microsoft Edge when Microsoft Edge Legacy reaches its end of service.</span></span>

<span data-ttu-id="ed7da-105">Microsoft Edge 製品チームの[ブログ投稿](https://aka.ms/EdgeLegacyEOS)に示す通り、Microsoft Edge レガシ デスクトップ アプリケーションのサポートは 2021 年 3 月 9 日に終了します。</span><span class="sxs-lookup"><span data-stu-id="ed7da-105">As per the Microsoft Edge Product Team’s [blog post](https://aka.ms/EdgeLegacyEOS), support for the Microsoft Edge Legacy desktop application will end on March 9, 2021.</span></span> <span data-ttu-id="ed7da-106">4 月に Update Tuesday (または "B") リリースを適用すると、Windows 10 RS4 ~ 20H1 を実行しているデバイスから Microsoft Edge レガシが削除され、Microsoft Edge に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="ed7da-106">When you apply the Update Tuesday (or "B") release in April, it will remove Microsoft Edge Legacy from devices running Windows 10 RS4 through 20H1 and replace it with Microsoft Edge.</span></span>

## <span data-ttu-id="ed7da-107">準備する方法</span><span class="sxs-lookup"><span data-stu-id="ed7da-107">How to Prepare</span></span>

<span data-ttu-id="ed7da-108">Microsoft Edge が 4 月の Update Tuesday リリースで Windows 10 RS4 ~ 20H1 デバイスにインストールされる準備を行う場合は、「[Microsoft Edgeの展開を計画する](deploy-edge-plan-deployment.md)」を参照することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ed7da-108">To prepare for Microsoft Edge being installed on Windows 10 RS4 through 20H1 devices with the Update Tuesday release in April, we recommend reading [Plan your deployment of Microsoft Edge](deploy-edge-plan-deployment.md).</span></span>

<span data-ttu-id="ed7da-109">展開を計画した後、次のいずれかの方法を使用して Microsoft Edge の展開を準備します。</span><span class="sxs-lookup"><span data-stu-id="ed7da-109">After you plan your deployment, use one of the following approaches to prepare to deploy Microsoft Edge.</span></span>

- <span data-ttu-id="ed7da-110">**グループ ポリシーをインストールして、Microsoft Edge の更新方法をカスタマイズします**。</span><span class="sxs-lookup"><span data-stu-id="ed7da-110">**Install group policies to customize your Microsoft Edge update approach**.</span></span> <span data-ttu-id="ed7da-111">詳しくは、「[Windows での Microsoft Edge ポリシー設定の構成](configure-microsoft-edge.md)」をご覧ください。また、[更新ポリシー リファレンス](microsoft-edge-update-policies.md)資料 に特に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ed7da-111">For more information, see [Configure Microsoft Edge policy settings on Windows](configure-microsoft-edge.md), and pay special attention to the [Update Policy reference](microsoft-edge-update-policies.md) material.</span></span> <span data-ttu-id="ed7da-112">4 月の Update Tuesday リリースをインストールする前に、更新を管理するためにグループ ポリシーをインストールすると、Microsoft Edge はtadatini ポリシーの順守を開始します。</span><span class="sxs-lookup"><span data-stu-id="ed7da-112">If you install group policies to manage your updates before installing April’s Update Tuesday release, Microsoft Edge will immediately start respecting your policy.</span></span> <span data-ttu-id="ed7da-113">インストールされているグループ ポリシーがインストールされていない場合、Microsoft Edge は自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="ed7da-113">If there isn't any installed group policy, Microsoft Edge will automatically update itself.</span></span>

- <span data-ttu-id="ed7da-114">**2021年 3 月 9 日のサービス終了日より前に Microsoft Edge レガシ デスクトップ アプリケーションを削除し、Microsoft Edge を展開します**。</span><span class="sxs-lookup"><span data-stu-id="ed7da-114">**Remove the Microsoft Edge Legacy desktop application before its end of service date of March 9, 2021 and deploy Microsoft Edge**.</span></span> <span data-ttu-id="ed7da-115">Windows 10 RS4 ~ 20H1 の場合は、Windows 更新プログラムを使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="ed7da-115">For Windows 10 RS4 through 20H1, you can do this by using Windows Updates.</span></span> <span data-ttu-id="ed7da-116">詳しくは、「[Windows 10 更新プログラムを適用した Microsoft Edge の展開](deploy-edge-with-windows-10-updates.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ed7da-116">For more information, see [Deploy Microsoft Edge with Windows 10 updates](deploy-edge-with-windows-10-updates.md).</span></span>

## <span data-ttu-id="ed7da-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed7da-117">See also</span></span>

- [<span data-ttu-id="ed7da-118">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="ed7da-118">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="ed7da-119">Microsoft Edge の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="ed7da-119">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)