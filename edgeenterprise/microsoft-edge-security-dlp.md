---
title: Microsoft Edge でのデータ損失防止
ms.author: archandr
author: dan-wesley
manager: seanlynd
ms.date: 10/08/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge (DLP) でのデータ損失防止
ms.openlocfilehash: 59c1b68c0526a49a2ee30283893707852514828d
ms.sourcegitcommit: 2af303fc97e8493024e2359fa2e8be162ab95a59
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104620"
---
# <span data-ttu-id="0ef7e-103">Microsoft Edge (DLP) でのデータ損失防止</span><span class="sxs-lookup"><span data-stu-id="0ef7e-103">Data Loss Prevention (DLP) in Microsoft Edge</span></span>

<span data-ttu-id="0ef7e-104">データ損失防止 (DLP) は、企業の機密データを特定し、許可されていない公開から保護する技術のシステムです。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-104">Data loss prevention (DLP) is a system of technologies that identify and safeguard sensitive enterprise data from unauthorized disclosure.</span></span> <span data-ttu-id="0ef7e-105">業務標準や業界の規制を遵守するために、組織は機密情報を保護し、その許可されていない公開を防止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-105">To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its unauthorized disclosure.</span></span> <span data-ttu-id="0ef7e-106">機密情報には、財務データやクレジット カード番号、社会保障番号、医療記録などの個人を特定できる情報 (PII) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-106">Sensitive information includes financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records, among many other things.</span></span>

<span data-ttu-id="0ef7e-107">リモート ワークでは、DLP の使用が重視されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-107">Remote work has increased the emphasis on using DLP.</span></span> <span data-ttu-id="0ef7e-108">デバイス上での個人や業務アクティビティの利用が増加していることから、企業は職場外で企業データが許可なく共有されてしまうリスクに直面しています。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-108">With the growing use of personal and work activities on devices, enterprises are seeing an increased risk of unauthorized sharing of corporate data outside the workplace.</span></span>

<span data-ttu-id="0ef7e-109">このようなユーザー アクティビティの融合はデバイスにも広がっており、個人のデバイスや企業のデバイスの間を、さまざまなパブリック ネットワークやプライベート ネットワークを介してデータが移動しています。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-109">This blending of user activities has spread to devices as well, where data is moved between personal and corporate devices over a variety of public and private networks.</span></span> <span data-ttu-id="0ef7e-110">その結果として、機密データを公開してしまうリスクは飛躍的に高まりました。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-110">The net result is a dramatically increased risk of exposing sensitive data.</span></span>

<span data-ttu-id="0ef7e-111">Microsoft Edge は、Microsoft エンドポイント DLP と Windows 情報保護 (WIP) という 2 つの異なる DLP ソリューションをネイティブにサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-111">Microsoft Edge natively supports two different DLP solutions, Microsoft Endpoint DLP and Windows Information Protection (WIP).</span></span>

## <span data-ttu-id="0ef7e-112">Microsoft エンドポイント DLP</span><span class="sxs-lookup"><span data-stu-id="0ef7e-112">Microsoft Endpoint DLP</span></span>

<span data-ttu-id="0ef7e-113">Microsoft エンドポイント DLP は、データ中心の保護などの最新のコンセプトを用いた次世代の DLP です。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-113">Microsoft Endpoint DLP is the next generation of DLP using modern concepts such as data-centric protection.</span></span> <span data-ttu-id="0ef7e-114">これは Windows 10 と Microsoft Edge に組み込まれているので、デバイスに追加のエージェントやプラグインは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-114">It's  built-in to Windows 10 and Microsoft Edge so it doesn't need additional agents or plugins on the device.</span></span> <span data-ttu-id="0ef7e-115">エンドポイント DLP の詳細については、「[Learn about Microsoft 365 Endpoint data loss prevention (Microsoft 365 エンドポイント データ損失防止について)](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-115">To learn more about endpoint DLP, read [Learn about Microsoft 365 Endpoint data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide).</span></span>

> [!NOTE]
> <span data-ttu-id="0ef7e-116">これは、Microsoft Edge バージョン 85 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-116">This applies to Microsoft Edge version 85 or later.</span></span>

<span data-ttu-id="0ef7e-117">Microsoft Edge は、管理者が構成した機密ファイル用のポリシーを強制し、非準拠アクティビティの監査イベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-117">Microsoft Edge enforces admin configured policies for sensitive files and records audit events for non-compliant activities.</span></span>

<span data-ttu-id="0ef7e-118">Windows 10 を実行しているデバイスで監査および管理できるユーザー アクティビティには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-118">Some of the user activities that you can audit and manage on devices running Windows 10 include the following activities:</span></span>

- <span data-ttu-id="0ef7e-119">ファイルのアップロード: 許可されていないクラウド上の場所にアップロードされた機密ファイルを保護します。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-119">File Upload: Protect sensitive file upload to unauthorized cloud locations.</span></span> <span data-ttu-id="0ef7e-120">次の 3 つのスクリーンショットは、ユーザーがローカル ストレージに機密データ ファイルをドロップする順序を示しています。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-120">The next 3 screenshots show a sequence where a user tries to drop a sensitive data file on to their local storage.</span></span>
- <span data-ttu-id="0ef7e-121">クリップボードの保護: 機密データがファイルからコピーされないように保護します。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-121">Clipboard Protection: Protect sensitive data from being copied out of the file.</span></span>
- <span data-ttu-id="0ef7e-122">印刷の保護: 機密ファイルが印刷されないように保護します。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-122">Print Protection: Protect sensitive file from being printed.</span></span>
- <span data-ttu-id="0ef7e-123">USB/ネットワークへの保存: 機密ファイルがリムーバブル USB ストレージや許可されていないネットワークの場所に保存されないように保護します。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-123">Save to USB/Network: Protect sensitive file from being saved to removable USB storage or unauthorized network locations.</span></span>

<span data-ttu-id="0ef7e-124">監査や管理が可能なユーザー アクティビティの詳細については、「[Endpoint activities you can monitor and take action on (監視したり、アクションを実行したりできるエンドポイント アクティビティ)](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-124">For more detailed information about user activities you can audit and manage, see [Endpoint activities you can monitor and take action on](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on).</span></span>

## <span data-ttu-id="0ef7e-125">Windows 情報保護</span><span class="sxs-lookup"><span data-stu-id="0ef7e-125">Windows Information Protection</span></span>

<span data-ttu-id="0ef7e-126">Microsoft Edge が Windows 情報保護 (WIP) をどのようにサポートしているかについては、「[Windows Information Protection のサポート](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-126">Check out [Support for Windows Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection), which describes how Microsoft Edge supports Windows Information Protection (WIP).</span></span> <span data-ttu-id="0ef7e-127">システム要件、メリット、サポートされている機能については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ef7e-127">You can learn moe about system requirements, benefits, and supported features in the following sections:</span></span>

- [<span data-ttu-id="0ef7e-128">システム要件</span><span class="sxs-lookup"><span data-stu-id="0ef7e-128">System Requirements</span></span>](https://docs.microsoft.com/deployedge/:microsoft-edge-security-windows-information-protection#system-requirements)
- [<span data-ttu-id="0ef7e-129">Windows 情報保護のメリット</span><span class="sxs-lookup"><span data-stu-id="0ef7e-129">Windows Information Protection Benefits</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection#windows-information-protection-benefits)
- [<span data-ttu-id="0ef7e-130">Microsoft Edge でサポートされている WIP の機能</span><span class="sxs-lookup"><span data-stu-id="0ef7e-130">WIP features supported in Microsoft Edge</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-information-protection#wip-features-supported-in-microsoft-edge)

## <span data-ttu-id="0ef7e-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ef7e-131">See also</span></span>

- [<span data-ttu-id="0ef7e-132">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="0ef7e-132">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="0ef7e-133">ビデオ: Microsoft Edge でのデータ損失防止</span><span class="sxs-lookup"><span data-stu-id="0ef7e-133">Video: Data loss prevention - Microsoft Edge</span></span>](https://www.youtube.com/watch?v=dLD04U9eTqg)
- [<span data-ttu-id="0ef7e-134">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="0ef7e-134">Overview of data loss prevention</span></span>](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)
- [<span data-ttu-id="0ef7e-135">Windows 情報保護を使用して企業データを保護する</span><span class="sxs-lookup"><span data-stu-id="0ef7e-135">Protect your enterprise data using Windows Information Protection</span></span>](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)
