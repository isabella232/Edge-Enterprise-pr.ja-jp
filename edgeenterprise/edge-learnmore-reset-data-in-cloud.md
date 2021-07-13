---
title: Microsoft Edge データをリセットする
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 07/09/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: クラウドで Microsoft Edge データをリセットする方法
ms.openlocfilehash: dc6c0ae1b1bc31228e9b9b1de315a19e99149134
ms.sourcegitcommit: 2a00571483e1d169b2b3b59f4fce43262f460a9a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643742"
---
# <a name="reset-microsoft-edge-data-in-the-cloud"></a><span data-ttu-id="537b3-103">クラウドで Microsoft Edge データをリセットする</span><span class="sxs-lookup"><span data-stu-id="537b3-103">Reset Microsoft Edge data in the cloud</span></span>

<span data-ttu-id="537b3-104">この記事では、クラウドで Microsoft Edge データをリセットする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="537b3-104">This article describes the steps for resetting your Microsoft Edge data in the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="537b3-105">この記事は、特に説明がない限り、Microsoft Edge バージョン 88 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="537b3-105">This article applies to Microsoft Edge version 88 or later unless otherwise noted.</span></span>

> [!NOTE]
> <span data-ttu-id="537b3-106">テナントが GCC Mod 環境にある場合、テナント管理者はデータをリセットするために Microsoft にサポート リクエストを提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="537b3-106">If your tenant is in a GCC Mod environment, your tenant admin will need to file a support request with Microsoft to reset your data.</span></span>

## <a name="overview"></a><span data-ttu-id="537b3-107">概要</span><span class="sxs-lookup"><span data-stu-id="537b3-107">Overview</span></span>

<span data-ttu-id="537b3-108">クラウドで Microsoft Edge データをリセットする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="537b3-108">There are situations in which you want to reset your Microsoft Edge data in the cloud.</span></span> <span data-ttu-id="537b3-109">たとえば、ユーザーがデータを同期したいと思っても、Microsoft Edge はデータを同期できないと報告することがあります。</span><span class="sxs-lookup"><span data-stu-id="537b3-109">For example,  you want to synchronize your data, but Microsoft Edge reports that it is unable to synchronize the data.</span></span> <span data-ttu-id="537b3-110">または、データが Microsoft のクラウドから削除されるのを確認したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="537b3-110">Or you might want to make sure that your data is removed from Microsoft’s cloud.</span></span> <span data-ttu-id="537b3-111">どちらの場合も、Microsoft Edge ではクラウド データのリセットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="537b3-111">In both cases, Microsoft Edge lets you perform a cloud data reset.</span></span>

## <a name="back-up-your-favorites"></a><span data-ttu-id="537b3-112">お気に入りをバックアップする</span><span class="sxs-lookup"><span data-stu-id="537b3-112">Back up your favorites</span></span>

<span data-ttu-id="537b3-113">リセットを実行する前に、お気に入りをバックアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="537b3-113">Before performing a reset, we recommend that you back up your favorites.</span></span> <span data-ttu-id="537b3-114">お気に入りをバックアップするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="537b3-114">Use the following steps to back up your favorites.</span></span>

1. <span data-ttu-id="537b3-115">Microsoft Edge の右上隅で、**[設定など] > [お気に入り] > [その他のオプション] > [お気に入りのエクスポート]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="537b3-115">In the upper-right corner of Microsoft Edge, select **Settings and more > Favorites > More options > Export favorites**.</span></span>
2. <span data-ttu-id="537b3-116">お気に入りを保存するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="537b3-116">Choose the file to where you want to save your favorites.</span></span> <span data-ttu-id="537b3-117">独自のファイル名を入力するか、Microsoft Edge が既定で提供する名前 "favorites_month_day_year.html" をファイル名として使用できます。</span><span class="sxs-lookup"><span data-stu-id="537b3-117">You can type your own filename or use the name that Microsoft Edge provides by default,  "favorites_month_day_year.html" as a filename.</span></span> <span data-ttu-id="537b3-118">たとえば、"favorites_12_17_20.html" とします。</span><span class="sxs-lookup"><span data-stu-id="537b3-118">For example, "favorites_12_17_20.html".</span></span> <span data-ttu-id="537b3-119">お気に入りを後で復元する必要がある場合は、そのファイルから復元できます。</span><span class="sxs-lookup"><span data-stu-id="537b3-119">If you need to restore your favorites later, you can do so from that file.</span></span>
3. <span data-ttu-id="537b3-120">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="537b3-120">Click **Save**.</span></span>

## <a name="perform-a-reset-to-fix-a-synchronization-problem"></a><span data-ttu-id="537b3-121">リセットを実行して同期の問題を修正する</span><span class="sxs-lookup"><span data-stu-id="537b3-121">Perform a reset to fix a synchronization problem</span></span>

<span data-ttu-id="537b3-122">Microsoft Edge がデータを同期できないと報告し、データのリセットを提案する場合は、リセットを実行して問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="537b3-122">If Microsoft Edge reports that it can't synchronize your data and suggests resetting your data, perform a reset to fix the problem.</span></span>

<span data-ttu-id="537b3-123">リセットを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="537b3-123">Use the following steps to do a reset.</span></span>

1. <span data-ttu-id="537b3-124">まず、リセットを実行しているデバイスを除き、モバイル デバイスを含むすべてのデバイスで Microsoft Edge からサインアウトしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="537b3-124">First, make sure that you’re signed out of Microsoft Edge on all your devices, including your mobile devices, except the device you are performing the reset on.</span></span> <span data-ttu-id="537b3-125">Microsoft Edge からサインアウトするには、Microsoft Edge の右上隅にある **[設定など] > [設定] > [サインアウト]** を選択します。サインアウトするときは、ローカル デバイスからお気に入りや設定などをクリアするオプションを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="537b3-125">To sign out of Microsoft Edge, in the upper-right corner of Microsoft Edge select **Settings and more > Settings > Sign out**. When signing out, do not select the option to clear favorites, settings, and etc. from your local device.</span></span>
2. <span data-ttu-id="537b3-126">他のすべてのデバイスからサインアウトした後、デスクトップで Microsoft Edge を開きます。Microsoft Edge の右上隅にある **[設定など] > [同期] > [同期のリセット] を選択します**。表示されるダイアログ ボックスで、データをリセットした後に同期を再開することを選択し、**[リセット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="537b3-126">After you sign out of all your other devices, open Microsoft Edge on your desktop.In the upper-right corner of Microsoft Edge **Select Settings and more > Sync > Reset sync**. In the resulting dialog box, choose to resume sync after resetting data, and then select **Reset**.</span></span>

## <a name="perform-a-reset-to-remove-your-data-from-microsofts-cloud"></a><span data-ttu-id="537b3-127">リセットを実行して Microsoft のクラウドからデータを削除する</span><span class="sxs-lookup"><span data-stu-id="537b3-127">Perform a reset to remove your data from Microsoft’s cloud</span></span>

<span data-ttu-id="537b3-128">Microsoft のクラウドからデータを削除する場合は、次の手順に従ってリセットします。</span><span class="sxs-lookup"><span data-stu-id="537b3-128">If you want to remove your data from Microsoft’s cloud, use the following steps to do a reset.</span></span>

1. <span data-ttu-id="537b3-129">リセットを実行しているデバイス以外のデバイスで同期を停止します。</span><span class="sxs-lookup"><span data-stu-id="537b3-129">Stop synchronization on devices except the device you are performing the reset on.</span></span>  <span data-ttu-id="537b3-130">Microsoft Edge の右上隅で、**[設定など] > [設定] > [同期] > [同期をオフ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="537b3-130">In the upper-right corner of Microsoft Edge, select **Settings and more > Settings > Sync > Turn off sync**.</span></span>  
2. <span data-ttu-id="537b3-131">同期を停止した後、Microsoft Edge の右上隅にある **[設定など] > [同期] > [同期のリセット]** を選択します。表示されるダイアログ ボックスで、データをリセットした後に同期を再開することを選択**しない**でください。</span><span class="sxs-lookup"><span data-stu-id="537b3-131">After you stop synchronization, in the upper-right corner of Microsoft Edge select **Settings and more > Sync > Reset sync**. In the resulting dialog box, **do not** choose to resume sync after resetting data.</span></span> <span data-ttu-id="537b3-132">**[リセット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="537b3-132">Select **Reset**.</span></span>

## <a name="what-to-expect-during-and-after-a-data-reset"></a><span data-ttu-id="537b3-133">データのリセット中およびリセット後に予想される処理</span><span class="sxs-lookup"><span data-stu-id="537b3-133">What to expect during and after a data reset</span></span>

<span data-ttu-id="537b3-134">Microsoft のクラウドに保存したデータの量によって、データのリセットに数秒から数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="537b3-134">A data reset can take from a few seconds to a few minutes, depending on how much data you have stored in Microsoft’s cloud.</span></span> <span data-ttu-id="537b3-135">場合によっては、リセットを完了できないというメッセージや、もう一度リセットを提案するメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="537b3-135">In some cases, you might see a message saying that a reset could not be completed and a suggestion to reset again.</span></span> <span data-ttu-id="537b3-136">この場合は、数時間待って、もう一度データのリセットを試みます。</span><span class="sxs-lookup"><span data-stu-id="537b3-136">In this case, wait a few hours and try to reset the data again.</span></span> <span data-ttu-id="537b3-137">それでもデータをリセットできない場合は、Microsoft Edge サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="537b3-137">If you are still unable to reset your data, contact Microsoft Edge Support.</span></span>

<span data-ttu-id="537b3-138">データのリセットが正常に完了すると、リセット後に同期を再開することを選択した場合、データはデバイスから再び同期されます。</span><span class="sxs-lookup"><span data-stu-id="537b3-138">After a data reset has been successfully completed, data will once again synchronize from your device if you chose to resume sync after the reset.</span></span> <span data-ttu-id="537b3-139">それらのデバイスから同期する場合は、他のデバイスにサインインし戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="537b3-139">You will need to sign back in on your other devices if you want to sync from those devices.</span></span> <span data-ttu-id="537b3-140">ただし、同期の再開を選択しなかった場合、Microsoft Edge データはクラウドから削除され、データは同期されません。</span><span class="sxs-lookup"><span data-stu-id="537b3-140">However, if you didn’t choose to resume sync, then your Microsoft Edge data is removed from the cloud and your data will no longer synchronize.</span></span>

## <a name="see-also"></a><span data-ttu-id="537b3-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="537b3-141">See also</span></span>

- [<span data-ttu-id="537b3-142">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="537b3-142">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="537b3-143">Microsoft Edge エンタープライズの同期</span><span class="sxs-lookup"><span data-stu-id="537b3-143">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)