---
title: Microsoft Edge の構成と試験
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 02/20/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge の構成と試験
ms.openlocfilehash: aef19fd9c119926a934a1ab00009a89ce2fe31fc
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447771"
---
# <a name="microsoft-edge-configurations-and-experimentation"></a><span data-ttu-id="a957b-103">Microsoft Edge の構成と試験</span><span class="sxs-lookup"><span data-stu-id="a957b-103">Microsoft Edge configurations and experimentation</span></span>

<span data-ttu-id="a957b-104">この記事では、Microsoft Edge と Experimentation and Configuration Service (ECS) の間でのやり取りについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a957b-104">This article describes the interaction between Microsoft Edge and the Experimentation and Configuration Service (ECS).</span></span> <span data-ttu-id="a957b-105">Microsoft Edge は、このサービスと通信して、さまざまな種類のペイロードを要求して受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a957b-105">Microsoft Edge communicates with this service to request and receive different kinds of payloads.</span></span> <span data-ttu-id="a957b-106">これらのペイロードには、構成、機能のロールアウト、試験が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a957b-106">These payloads include configurations, feature rollouts, and experiments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a957b-107">ペイロードを受信できるように、クライアントが `https://config.edge.skype.com` にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a957b-107">Make sure clients are able to access `https://config.edge.skype.com` so payloads can be received.</span></span>

> [!NOTE]
> <span data-ttu-id="a957b-108">これは、Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a957b-108">This applies to Microsoft Edge version 77 or later.</span></span>

## <a name="configurations"></a><span data-ttu-id="a957b-109">構成</span><span class="sxs-lookup"><span data-stu-id="a957b-109">Configurations</span></span>

<span data-ttu-id="a957b-110">構成は、製品の正常性、セキュリティ、プライバシーに関するコンプライアンスを保証するためのペイロードであり、(プラットフォームとチャネルに基づいて) すべてのユーザーに同じ値を使用することを目的としています。これにより、ドメイン アクションの機能フラグを有効にすることも、バグの発生時に機能フラグを無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a957b-110">Configurations are the payload meant to ensure product health, security, and privacy compliance, and are intended to have the same value for all the users (based on platforms and channels.) This could be to enable a feature flag for a domain action, and can also be used to disable a feature flag in the event of a bug.</span></span>

## <a name="controlled-feature-rollout"></a><span data-ttu-id="a957b-111">制御された機能ロールアウト</span><span class="sxs-lookup"><span data-stu-id="a957b-111">Controlled Feature Rollout</span></span>

<span data-ttu-id="a957b-112">制御された機能ロールアウト (Controlled Feature Rollout: CFR) は、機能を受け取るユーザー グループのサイズを徐々に拡大するための手順です。</span><span class="sxs-lookup"><span data-stu-id="a957b-112">Controlled Feature Rollout (CFR) is a procedure for slowly increasing the size of the user group that receives a feature.</span></span> <span data-ttu-id="a957b-113">ユーザー母集団からランダムに選択されたサブセットに新しい機能を配布することで、その機能が配布されていない同じサイズのコントロール グループとユーザー フィードバックを比較して、機能の影響を測定することができます。</span><span class="sxs-lookup"><span data-stu-id="a957b-113">By distributing a new feature to a randomly selected subset of the user population, it’s possible to compare user feedback to an equally sized control group without the feature to measure the impact of the feature.</span></span>

## <a name="experiments"></a><span data-ttu-id="a957b-114">テスト</span><span class="sxs-lookup"><span data-stu-id="a957b-114">Experiments</span></span>

<span data-ttu-id="a957b-115">Microsoft Edge のビルドには、まだ開発中の機能や、試験的な機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a957b-115">Microsoft Edge builds have features and functionality that are still in development or are experimental.</span></span> <span data-ttu-id="a957b-116">試験は CFR に似ていますが、新しい概念をテストするために、ユーザー グループのサイズはずっと小さくなります。</span><span class="sxs-lookup"><span data-stu-id="a957b-116">Experiments are like CFR, but the size of the user group is much smaller for testing the new concept.</span></span> <span data-ttu-id="a957b-117">これらの機能は、機能がロールアウトされるか試験が終了するまで、既定で非表示になります。</span><span class="sxs-lookup"><span data-stu-id="a957b-117">These features are hidden by default until the feature's rolled out or the experiment's finished.</span></span> <span data-ttu-id="a957b-118">これらの機能を有効または無効にするには、試験フラグを使用します。</span><span class="sxs-lookup"><span data-stu-id="a957b-118">Experiment flags are used to enable and disable these features.</span></span>

## <a name="about-the-ecs"></a><span data-ttu-id="a957b-119">ECS について</span><span class="sxs-lookup"><span data-stu-id="a957b-119">About the ECS</span></span>

<span data-ttu-id="a957b-120">上記のすべてのシナリオでは、ブラウザー クライアントに適用できるように、このサービスによって機能フラグの値が配布されます。</span><span class="sxs-lookup"><span data-stu-id="a957b-120">In all the preceding scenarios, the service delivers the feature flag values to the browser client so they can be applied.</span></span> <span data-ttu-id="a957b-121">更新プログラムによって、構成が直ちに適用される場合も、ユーザーがブラウザーを再起動したときに適用される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a957b-121">Depending on the update, configurations are applied immediately or when the user restarts the browser.</span></span>

<span data-ttu-id="a957b-122">このサービスと Microsoft Edge との間のやり取りは、[ExperimentationAndConfigurationServiceControl](./microsoft-edge-policies.md#experimentationandconfigurationservicecontrol) ポリシーの設定によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="a957b-122">Microsoft Edge's interaction with this service is controlled by settings in the [ExperimentationAndConfigurationServiceControl](./microsoft-edge-policies.md#experimentationandconfigurationservicecontrol) policy.</span></span> <span data-ttu-id="a957b-123">ポリシー設定は、次のように構成できます。</span><span class="sxs-lookup"><span data-stu-id="a957b-123">You can configure policy settings to:</span></span>

- <span data-ttu-id="a957b-124">構成のみを取得する</span><span class="sxs-lookup"><span data-stu-id="a957b-124">Retrieve configurations only</span></span>
- <span data-ttu-id="a957b-125">構成と試験を取得する</span><span class="sxs-lookup"><span data-stu-id="a957b-125">Retrieve configurations and experiments</span></span>
- <span data-ttu-id="a957b-126">サービスとの通信を無効にする</span><span class="sxs-lookup"><span data-stu-id="a957b-126">Disable communication with the service</span></span>

  > [!CAUTION]
  > <span data-ttu-id="a957b-127">サービスとの通信を無効にすると、Microsoft が深刻なバグに迅速に対応するための機能に影響します。</span><span class="sxs-lookup"><span data-stu-id="a957b-127">If you disable communications with the service, this will affect Microsoft’s ability to respond to a severe bug in a timely manner.</span></span>

## <a name="see-also"></a><span data-ttu-id="a957b-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="a957b-128">See also</span></span>

- [<span data-ttu-id="a957b-129">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="a957b-129">Microsoft Edge Enterprise landing page</span></span>](https://www.microsoftedgeinsider.com/enterprise)
- [<span data-ttu-id="a957b-130">Microsoft Edge ドキュメント ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="a957b-130">Microsoft Edge documentation landing page</span></span>](./index.yml)