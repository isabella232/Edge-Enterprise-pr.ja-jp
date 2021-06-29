---
title: Microsoft Edge データをリセットする
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 04/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: クラウドで Microsoft Edge データをリセットする方法
ms.openlocfilehash: 6dcbf2a80705aa87a35b50d41e0dbaa266ed4384
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617327"
---
# <a name="reset-microsoft-edge-data-in-the-cloud"></a><span data-ttu-id="a70ed-103">クラウドで Microsoft Edge データをリセットする</span><span class="sxs-lookup"><span data-stu-id="a70ed-103">Reset Microsoft Edge data in the cloud</span></span>

<span data-ttu-id="a70ed-104">この記事では、クラウドで Microsoft Edge データをリセットする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a70ed-104">This article describes the steps for resetting your Microsoft Edge data in the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="a70ed-105">この記事は、特に説明がない限り、Microsoft Edge バージョン 88 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a70ed-105">This article applies to Microsoft Edge version 88 or later unless otherwise noted.</span></span>

> [!NOTE]
> <span data-ttu-id="a70ed-106">テナントが GCC Mod 環境にある場合、テナント管理者はデータをリセットするために Microsoft にサポート リクエストを提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a70ed-106">If your tenant is in a GCC Mod environment, your tenant admin will need to file a support request with Microsoft to reset your data.</span></span>

## <a name="overview"></a><span data-ttu-id="a70ed-107">概要</span><span class="sxs-lookup"><span data-stu-id="a70ed-107">Overview</span></span>

<span data-ttu-id="a70ed-108">クラウドで Microsoft Edge データをリセットする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a70ed-108">There are situations in which you want to reset your Microsoft Edge data in the cloud.</span></span> <span data-ttu-id="a70ed-109">たとえば、ユーザーがデータを同期したいと思っても、Microsoft Edge はデータを同期できないと報告することがあります。</span><span class="sxs-lookup"><span data-stu-id="a70ed-109">For example,  you want to synchronize your data, but Microsoft Edge reports that it is unable to synchronize the data.</span></span> <span data-ttu-id="a70ed-110">または、データが Microsoft のクラウドから削除されるのを確認したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="a70ed-110">Or you might want to make sure that your data is removed from Microsoft’s cloud.</span></span> <span data-ttu-id="a70ed-111">どちらの場合も、Microsoft Edge ではクラウド データのリセットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a70ed-111">In both cases, Microsoft Edge lets you perform a cloud data reset.</span></span>

## <a name="back-up-your-favorites"></a><span data-ttu-id="a70ed-112">お気に入りをバックアップする</span><span class="sxs-lookup"><span data-stu-id="a70ed-112">Back up your favorites</span></span>

<span data-ttu-id="a70ed-113">リセットを実行する前に、お気に入りをバックアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a70ed-113">Before performing a reset, we recommend that you back up your favorites.</span></span> <span data-ttu-id="a70ed-114">お気に入りをバックアップするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a70ed-114">Use the following steps to back up your favorites.</span></span>

1. <span data-ttu-id="a70ed-115">Microsoft Edge で、 **[設定など]、[お気に入り]、 [その他のオプション]、[エクスポート]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a70ed-115">In Microsoft Edge, select **Settings and more > Favorites > More options > Export favorites**.</span></span>
2. <span data-ttu-id="a70ed-116">お気に入りを保存するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="a70ed-116">Choose the file to where you want to save your favorites.</span></span> <span data-ttu-id="a70ed-117">独自のファイル名を入力するか、Microsoft Edge が既定で提供する名前 "favorites_month_day_year.html" をファイル名として使用できます。</span><span class="sxs-lookup"><span data-stu-id="a70ed-117">You can type your own filename or use the name that Microsoft Edge provides by default,  "favorites_month_day_year.html" as a filename.</span></span> <span data-ttu-id="a70ed-118">たとえば、"favorites_12_17_20.html" とします。</span><span class="sxs-lookup"><span data-stu-id="a70ed-118">For example, "favorites_12_17_20.html".</span></span> <span data-ttu-id="a70ed-119">お気に入りを後で復元する必要がある場合は、そのファイルから復元できます。</span><span class="sxs-lookup"><span data-stu-id="a70ed-119">If you need to restore your favorites later, you can do so from that file.</span></span>
3. <span data-ttu-id="a70ed-120">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a70ed-120">Click **Save**.</span></span>

## <a name="perform-a-reset-to-fix-a-synchronization-problem"></a><span data-ttu-id="a70ed-121">リセットを実行して同期の問題を修正する</span><span class="sxs-lookup"><span data-stu-id="a70ed-121">Perform a reset to fix a synchronization problem</span></span>

<span data-ttu-id="a70ed-122">Microsoft Edge がデータを同期できないと報告し、データのリセットを提案する場合は、リセットを実行して問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="a70ed-122">If Microsoft Edge reports that it can't synchronize your data and suggests resetting your data, perform a reset to fix the problem.</span></span>

<span data-ttu-id="a70ed-123">リセットを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a70ed-123">Use the following steps to do a reset.</span></span>

1. <span data-ttu-id="a70ed-124">まず、リセットを実行しているデバイスを除き、モバイル デバイスを含むすべてのデバイスで Microsoft Edge からサインアウトしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a70ed-124">First, make sure that you’re signed out of Microsoft Edge on all your devices, including your mobile devices, except the device you are performing the reset on.</span></span> <span data-ttu-id="a70ed-125">Microsoft Edge からサインアウトするには、**[設定など]、[設定]、[サインアウト]** の順に選択します。サインアウトする場合は、ローカル デバイスからお気に入り、設定などをクリアするオプションを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="a70ed-125">To sign out of Microsoft Edge, select **Settings and more > Settings > Sign out**. When signing out, do not select the option to clear favorites, settings, and etc. from your local device.</span></span>
2. <span data-ttu-id="a70ed-126">他のすべてのデバイスからサインアウトした後、デスクトップで Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="a70ed-126">After you sign out of all your other devices, open Microsoft Edge on your desktop.</span></span> <span data-ttu-id="a70ed-127">**[設定など] > [同期] > [リセット同期]** の順に選択します。.結果のダイアログ ボックスで、データのリセット後に同期を再開し、\*\*[リセット] \*\* を選択 します。</span><span class="sxs-lookup"><span data-stu-id="a70ed-127">**Select Settings and more > Sync > Reset sync**. In the resulting dialog box, choose to resume sync after resetting data, and then select **Reset**.</span></span>

## <a name="perform-a-reset-to-remove-your-data-from-microsofts-cloud"></a><span data-ttu-id="a70ed-128">リセットを実行して Microsoft のクラウドからデータを削除する</span><span class="sxs-lookup"><span data-stu-id="a70ed-128">Perform a reset to remove your data from Microsoft’s cloud</span></span>

<span data-ttu-id="a70ed-129">Microsoft のクラウドからデータを削除する場合は、次の手順に従ってリセットします。</span><span class="sxs-lookup"><span data-stu-id="a70ed-129">If you want to remove your data from Microsoft’s cloud, use the following steps to do a reset.</span></span>

1. <span data-ttu-id="a70ed-130">リセットを実行しているデバイス以外のデバイスで同期を停止します。</span><span class="sxs-lookup"><span data-stu-id="a70ed-130">Stop synchronization on devices except the device you are performing the reset on.</span></span>  <span data-ttu-id="a70ed-131">Microsoft Edge で、**[設定など] > [設定] > [同期] > [同期をオフ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a70ed-131">In Microsoft Edge, select **Settings and more > Settings > Sync > Turn off sync**.</span></span>  
2. <span data-ttu-id="a70ed-132">同期を停止した後、**[設定など] > [同期] > [同期をリセット]** の順に選択します。結果のダイアログ ボックスでは、データのリセット後に同期を再開する選択は **行わない** でください。</span><span class="sxs-lookup"><span data-stu-id="a70ed-132">After you stop synchronization, select **Settings and more > Sync > Reset sync**. In the resulting dialog box, **do not** choose to resume sync after resetting data.</span></span> <span data-ttu-id="a70ed-133">**[リセット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a70ed-133">Select **Reset**.</span></span>

## <a name="what-to-expect-during-and-after-a-data-reset"></a><span data-ttu-id="a70ed-134">データのリセット中およびリセット後に予想される処理</span><span class="sxs-lookup"><span data-stu-id="a70ed-134">What to expect during and after a data reset</span></span>

<span data-ttu-id="a70ed-135">Microsoft のクラウドに保存したデータの量によって、データのリセットに数秒から数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a70ed-135">A data reset can take from a few seconds to a few minutes, depending on how much data you have stored in Microsoft’s cloud.</span></span> <span data-ttu-id="a70ed-136">場合によっては、リセットを完了できないというメッセージや、もう一度リセットを提案するメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="a70ed-136">In some cases, you might see a message saying that a reset could not be completed and a suggestion to reset again.</span></span> <span data-ttu-id="a70ed-137">この場合は、数時間待って、もう一度データのリセットを試みます。</span><span class="sxs-lookup"><span data-stu-id="a70ed-137">In this case, wait a few hours and try to reset the data again.</span></span> <span data-ttu-id="a70ed-138">それでもデータをリセットできない場合は、Microsoft Edge サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="a70ed-138">If you are still unable to reset your data, contact Microsoft Edge Support.</span></span>

<span data-ttu-id="a70ed-139">データのリセットが正常に完了すると、リセット後に同期を再開することを選択した場合、データはデバイスから再び同期されます。</span><span class="sxs-lookup"><span data-stu-id="a70ed-139">After a data reset has been successfully completed, data will once again synchronize from your device if you chose to resume sync after the reset.</span></span> <span data-ttu-id="a70ed-140">それらのデバイスから同期する場合は、他のデバイスにサインインし戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a70ed-140">You will need to sign back in on your other devices if you want to sync from those devices.</span></span> <span data-ttu-id="a70ed-141">ただし、同期の再開を選択しなかった場合、Microsoft Edge データはクラウドから削除され、データは同期されません。</span><span class="sxs-lookup"><span data-stu-id="a70ed-141">However, if you didn’t choose to resume sync, then your Microsoft Edge data is removed from the cloud and your data will no longer synchronize.</span></span>

## <a name="see-also"></a><span data-ttu-id="a70ed-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="a70ed-142">See also</span></span>

- [<span data-ttu-id="a70ed-143">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="a70ed-143">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="a70ed-144">Microsoft Edge エンタープライズの同期</span><span class="sxs-lookup"><span data-stu-id="a70ed-144">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)