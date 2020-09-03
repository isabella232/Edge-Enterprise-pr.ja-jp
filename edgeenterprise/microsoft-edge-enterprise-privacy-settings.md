---
title: Microsoft Edge エンタープライズ プライバシー設定
ms.author: likravit
author: dan-wesley
manager: srugh
ms.date: 05/26/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge エンタープライズ プライバシー設定を構成する
ms.openlocfilehash: 2b7a33087ae5110c53d18b3192486d4ae62fa540
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980508"
---
# <span data-ttu-id="b835d-103">企業のプライバシーをサポートするように Microsoft Edge ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="b835d-103">Configure Microsoft Edge policies to support enterprise privacy</span></span>

<span data-ttu-id="b835d-104">Microsoft では、Microsoft Edge のデータ収集に関する選択を行うために必要な情報とコントロールを企業のお客様に提供できるよう取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="b835d-104">Microsoft is committed to providing enterprises with the information and controls needed to make choices about data collection in Microsoft Edge.</span></span>

## <span data-ttu-id="b835d-105">概要</span><span class="sxs-lookup"><span data-stu-id="b835d-105">Overview</span></span>

<span data-ttu-id="b835d-106">既定では、Windows 以外のプラットフォームに展開された Microsoft Edge では、診断データやサイト情報は Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="b835d-106">By default, Microsoft Edge deployed on non-Windows platforms doesn't send diagnostic data or site information to Microsoft.</span></span> <span data-ttu-id="b835d-107">Microsoft Edge が Windows 10 に導入されている場合、規定では、ユーザーの [Windows 診断データ設定](https://go.microsoft.com/fwlink/?linkid=2099569)に基づいて診断データが送信されます。</span><span class="sxs-lookup"><span data-stu-id="b835d-107">When Microsoft Edge is deployed on Windows 10, the default is to send diagnostic data based on the users' [Windows Diagnostic data setting](https://go.microsoft.com/fwlink/?linkid=2099569).</span></span>

<span data-ttu-id="b835d-108">次のグループポリシーを使用して、Microsoft Edge が組織のデータ収集を処理する方法を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b835d-108">You can also configure how Microsoft Edge handles data collection for your organization with the following group policies:</span></span>

- <span data-ttu-id="b835d-109">[MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - 使用状況とクラッシュ関連のデータレポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b835d-109">[MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - Enable usage and crash-related data reporting.</span></span>
- <span data-ttu-id="b835d-110">[SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Microsoft サービスを改善するためにサイト情報を送信します。</span><span class="sxs-lookup"><span data-stu-id="b835d-110">[SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Send site information to improve Microsoft services.</span></span>

## <span data-ttu-id="b835d-111">ポリシー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="b835d-111">Configure policy settings</span></span>

<span data-ttu-id="b835d-112">始める前に、最新の Microsoft Edge ポリシーテンプレートをダウンロードして使用してください (詳細については、「[Microsoft Edge を構成する](configure-microsoft-edge.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b835d-112">Before you begin, download and use the latest Microsoft Edge Policy Template (For more information, see [Configure Microsoft Edge](configure-microsoft-edge.md).)</span></span>

### <span data-ttu-id="b835d-113">使用状況とクラッシュ関連データのレポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="b835d-113">Enable usage and crash-related data reporting</span></span>

<span data-ttu-id="b835d-114">このポリシーによって、Microsoft Edge の使用状況およびクラッシュに関連するデータの Microsoft への送信が有効になります。</span><span class="sxs-lookup"><span data-stu-id="b835d-114">This policy enables reporting of usage and crash-related data about Microsoft Edge to Microsoft.</span></span>

<span data-ttu-id="b835d-115">Microsoft Edge では、製品を最新の状態に保ち、セキュリティで保護し、適切に実行するために必要な一連のデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="b835d-115">Microsoft Edge collects a set of required data that's necessary to keep the product up to date, secure, and performing properly.</span></span> <span data-ttu-id="b835d-116">このデータには、現在のデータ収集の同意、アプリのバージョン、Microsoft Edge のインストール状態に関する、Microsoft Edgeからの基本的なデバイス接続と構成情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b835d-116">This data includes basic device connectivity and configuration information from Microsoft Edge about the current data collection consent, app version, and installation state about your installation of Microsoft Edge.</span></span><span data-ttu-id="b835d-117">このデータ収集は、ポリシーを無効にすることでオフにできます。</span><span class="sxs-lookup"><span data-stu-id="b835d-117"> This data collection can be turned off by disabling the policy.</span></span>

<span data-ttu-id="b835d-118">使用状況およびクラッシュに関連するデータのレポートを Microsoft に送信するには、このポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b835d-118">Enable this policy to send reporting of usage and crash-related data to Microsoft.</span></span> <span data-ttu-id="b835d-119">このデータを Microsoft に送信しない場合は、このポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b835d-119">Disable this policy to not send the data to Microsoft.</span></span> <span data-ttu-id="b835d-120">いずれの場合でも、ユーザーがこの設定を変更または上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b835d-120">In both cases, users can't change or override the setting.</span></span>

<span data-ttu-id="b835d-121">Microsoft Edge が Windows 10 で実行されている場合: </span><span class="sxs-lookup"><span data-stu-id="b835d-121">When Microsoft Edge is running on Windows 10:</span></span>

- <span data-ttu-id="b835d-122">このポリシーが構成されていない場合、Microsoft Edge は既定で Windows 診断データの設定になります。</span><span class="sxs-lookup"><span data-stu-id="b835d-122">If this policy isn't configured, Microsoft Edge will default to the Windows diagnostic data setting.</span></span>
- <span data-ttu-id="b835d-123">このポリシーが有効になっている場合、Microsoft Edge は、Windows 診断データの設定が **[拡張]** または **[完全]** に設定されている場合にのみ使用状況データを送信します。</span><span class="sxs-lookup"><span data-stu-id="b835d-123">If this policy is enabled, Microsoft Edge will only send usage data if the Windows Diagnostic data setting is set to **Enhanced** or **Full**.</span></span>
- <span data-ttu-id="b835d-124">このポリシーが無効になっている場合、Microsoft Edge は使用状況データを送信しません。</span><span class="sxs-lookup"><span data-stu-id="b835d-124">If this policy is disabled, Microsoft Edge will not send usage data.</span></span> <span data-ttu-id="b835d-125">クラッシュに関連するデータは、Windows 診断データの設定に基づいて送信されます。</span><span class="sxs-lookup"><span data-stu-id="b835d-125">Crash-related data is sent based on the Windows Diagnostic data setting.</span></span> <span data-ttu-id="b835d-126">[Windows 診断データ設定の詳細を参照してください](https://go.microsoft.com/fwlink/?linkid=2099569)。</span><span class="sxs-lookup"><span data-stu-id="b835d-126">[Learn more about Windows Diagnostic data settings](https://go.microsoft.com/fwlink/?linkid=2099569).</span></span>

<span data-ttu-id="b835d-127">Microsoft Edge が Windows 7、8、または macOS で実行されている場合：</span><span class="sxs-lookup"><span data-stu-id="b835d-127">When Microsoft Edge is running on Windows 7, 8, and macOS:</span></span>

- <span data-ttu-id="b835d-128">このポリシーが構成されていない場合、Microsoft Edge は既定でユーザーの設定に従います。</span><span class="sxs-lookup"><span data-stu-id="b835d-128">If this policy isn't configured, Microsoft Edge will default to the user's preference.</span></span>

### <span data-ttu-id="b835d-129">Microsoft サービスの品質向上のためにサイト情報を送信する</span><span class="sxs-lookup"><span data-stu-id="b835d-129">Send site information to improve Microsoft services</span></span>

<span data-ttu-id="b835d-130">このポリシーでは、検索などの Microsoft 製品やサービスの品質を向上させるために Microsoft Edge で訪問した Web サイトに関する情報を Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="b835d-130">This policy enables sending information about websites visited in Microsoft Edge to Microsoft to improve Microsoft products and services such as search.</span></span>

<span data-ttu-id="b835d-131">Microsoft Edge でアクセスした Web サイトに関する情報を Microsoft に送信する場合は、このポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b835d-131">Enable this policy to send information about websites visited in Microsoft Edge to Microsoft.</span></span> <span data-ttu-id="b835d-132">Microsoft Edge でアクセスした Web サイトに関する情報を Microsoft に送信しない場合は、このポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b835d-132">Disable this policy to not send information about the websites that are visited in Microsoft Edge to Microsoft.</span></span> <span data-ttu-id="b835d-133">いずれの場合でも、ユーザーがこの設定を変更または上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b835d-133">In both cases, users can't change or override the setting.</span></span>

<span data-ttu-id="b835d-134">Microsoft Edge が Windows 10 で実行されている場合: </span><span class="sxs-lookup"><span data-stu-id="b835d-134">When Microsoft Edge is running on Windows 10:</span></span>

- <span data-ttu-id="b835d-135">このポリシーが構成されていない場合、Microsoft Edge は既定で Windows 診断データの設定になります。</span><span class="sxs-lookup"><span data-stu-id="b835d-135">If this policy isn't configured, Microsoft Edge will default to the Windows diagnostic data setting.</span></span>
- <span data-ttu-id="b835d-136">このポリシーが有効になっている場合、Microsoft Edge は、Windows 診断データの設定が **[完全]** に設定されている場合にのみ、アクセスした Web サイトに関する情報を送信します。</span><span class="sxs-lookup"><span data-stu-id="b835d-136">If this policy is enabled, Microsoft Edge will only send information about the websites that are visited if the Windows Diagnostic data setting is set to **Full**.</span></span>
- <span data-ttu-id="b835d-137">このポリシーが無効になっている場合、Microsoft Edge はアクセスした Web サイトに関する情報を送信しません。</span><span class="sxs-lookup"><span data-stu-id="b835d-137">If this policy is disabled, Microsoft Edge will not send info about websites visited.</span></span> <span data-ttu-id="b835d-138">詳細については、[Windows 診断データの設定に関するトピック](https://go.microsoft.com/fwlink/?linkid=2099569)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b835d-138">To [learn more about Windows Diagnostic data settings](https://go.microsoft.com/fwlink/?linkid=2099569).</span></span>

<span data-ttu-id="b835d-139">Microsoft Edge が Windows 7、8、または macOS で実行されている場合：</span><span class="sxs-lookup"><span data-stu-id="b835d-139">When Microsoft Edge is running on Windows 7, 8, and macOS:</span></span>

- <span data-ttu-id="b835d-140">このポリシーが構成されていない場合、Microsoft Edge は既定でユーザーの設定に従います。</span><span class="sxs-lookup"><span data-stu-id="b835d-140">If this policy isn't configured, Microsoft Edge will default to the user's preference.</span></span>

## <span data-ttu-id="b835d-141">実装の詳細</span><span class="sxs-lookup"><span data-stu-id="b835d-141">Implementation details</span></span>

<span data-ttu-id="b835d-142">Windows 10 で、実装が Windows 診断データの設定にどのように依存しているかを説明するために、**[使用状況とクラッシュ関連データのレポートを有効にする]** と **[Microsoft サービスの品質向上のためにサイト情報を送信する]** が構成されていない場合の構成を次の表に示します。。</span><span class="sxs-lookup"><span data-stu-id="b835d-142">For Windows 10 to understand our implementation with the dependency on the Windows Diagnostic data setting, the following table describes our configuration if **Enable usage and crash-related data reporting** and **Send site information to improve Microsoft services** were not configured.</span></span>

| <span data-ttu-id="b835d-143">Windows 診断データの設定</span><span class="sxs-lookup"><span data-stu-id="b835d-143">Windows Diagnostic data setting</span></span> | <span data-ttu-id="b835d-144">使用状況とクラッシュ関連データのレポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="b835d-144">Enable usage and crash-related data reporting</span></span> | <span data-ttu-id="b835d-145">Microsoft サービスの品質向上のためにサイト情報を送信する</span><span class="sxs-lookup"><span data-stu-id="b835d-145">Send site information to improve Microsoft services</span></span> |
|---------------------------------|-----------------------------------------------|-----------------------------------------------------|
| <span data-ttu-id="b835d-146">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="b835d-146">Security</span></span>                        | <span data-ttu-id="b835d-147">送信されない</span><span class="sxs-lookup"><span data-stu-id="b835d-147">Not sent</span></span>                                      | <span data-ttu-id="b835d-148">送信されない</span><span class="sxs-lookup"><span data-stu-id="b835d-148">Not sent</span></span>                                            |
| <span data-ttu-id="b835d-149">基本</span><span class="sxs-lookup"><span data-stu-id="b835d-149">Basic</span></span>                           | <span data-ttu-id="b835d-150">送信されない</span><span class="sxs-lookup"><span data-stu-id="b835d-150">Not sent</span></span>                                      | <span data-ttu-id="b835d-151">送信されない</span><span class="sxs-lookup"><span data-stu-id="b835d-151">Not sent</span></span>                                            |
| <span data-ttu-id="b835d-152">拡張</span><span class="sxs-lookup"><span data-stu-id="b835d-152">Enhanced</span></span>                        | <span data-ttu-id="b835d-153">送信される</span><span class="sxs-lookup"><span data-stu-id="b835d-153">Sent</span></span>                                          | <span data-ttu-id="b835d-154">送信されない</span><span class="sxs-lookup"><span data-stu-id="b835d-154">Not sent</span></span>                                            |
| <span data-ttu-id="b835d-155">完全</span><span class="sxs-lookup"><span data-stu-id="b835d-155">Full</span></span>                            | <span data-ttu-id="b835d-156">送信される</span><span class="sxs-lookup"><span data-stu-id="b835d-156">Sent</span></span>                                          | <span data-ttu-id="b835d-157">送信される</span><span class="sxs-lookup"><span data-stu-id="b835d-157">Sent</span></span>                                                |

<span data-ttu-id="b835d-158">Windows 10 の構成が上記の表に従って正しく構成されていない場合は、より少ないデータ収集設定に戻されます。</span><span class="sxs-lookup"><span data-stu-id="b835d-158">If your configurations for Windows 10 are misconfigured in accordance with the preceding table, we will fall back to the lesser data collection setting.</span></span>

<span data-ttu-id="b835d-159">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="b835d-159">For example:</span></span>

- <span data-ttu-id="b835d-160">[使用状況とクラッシュ関連データのレポートを有効にする] ポリシーは **[有効]** に設定されていますが、Windows 診断データの設定が **[基本]** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="b835d-160">You set the "Enable usage and crash-related data reporting" policy to **Enabled** but the Windows Diagnostic data setting is set to **Basic**.</span></span> <span data-ttu-id="b835d-161">この場合、使用状況やクラッシュに関連するデータは送信されません。</span><span class="sxs-lookup"><span data-stu-id="b835d-161">We won't send usage and crash-related data.</span></span>
- <span data-ttu-id="b835d-162">[Microsoft サービスの品質向上のためにサイト情報を送信する] ポリシーは **[無効]** に設定されていますが、Windows 診断データの設定が **[完全]** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="b835d-162">You set the "Send site information to improve Microsoft services" policy to **Disabled** but the Windows Diagnostic data setting is set to **Full**.</span></span> <span data-ttu-id="b835d-163">この場合、アクセスしたサイトに関する情報は送信されません。</span><span class="sxs-lookup"><span data-stu-id="b835d-163">We won't send information about the sites that are visited.</span></span>

<span data-ttu-id="b835d-164">以前の設定の正しい実装は、「使用状況とクラッシュ関連のデータレポートを有効にする」ポリシーを **[有効]** に設定し、Windows診断データ設定を **[拡張]** または **[完全]** に設定することです。</span><span class="sxs-lookup"><span data-stu-id="b835d-164">The correct implementation for the previous settings is to set the "Enable usage and crash-related data reporting" policy to **Enabled** and set the Windows Diagnostic data setting to **Enhanced** or **Full**.</span></span>

## <span data-ttu-id="b835d-165">その他のプライバシー ポリシー オプション</span><span class="sxs-lookup"><span data-stu-id="b835d-165">Additional privacy policy options</span></span>

<span data-ttu-id="b835d-166">データのプライバシーに関連する次のグループ ポリシーも検討することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b835d-166">You may want to consider the following group policies related to data privacy:</span></span>

- <span data-ttu-id="b835d-167">特定のサイトでの Cookie のブロック</span><span class="sxs-lookup"><span data-stu-id="b835d-167">Block cookies on specific sites</span></span>
- <span data-ttu-id="b835d-168">サード パーティの Cookie のブロック</span><span class="sxs-lookup"><span data-stu-id="b835d-168">Block third-party cookies</span></span>
- <span data-ttu-id="b835d-169">トラッキング拒否を構成する</span><span class="sxs-lookup"><span data-stu-id="b835d-169">Configure Do Not Track</span></span>
- <span data-ttu-id="b835d-170">InPrivate モードの無効化</span><span class="sxs-lookup"><span data-stu-id="b835d-170">Disable InPrivate mode</span></span>

## <span data-ttu-id="b835d-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="b835d-171">See also</span></span>

- [<span data-ttu-id="b835d-172">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="b835d-172">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="b835d-173">Microsoft Edge ポリシー</span><span class="sxs-lookup"><span data-stu-id="b835d-173">Microsoft Edge policies</span></span>](microsoft-edge-policies.md)
- [<span data-ttu-id="b835d-174">Microsoft Edge プライバシー ホワイトペーパー</span><span class="sxs-lookup"><span data-stu-id="b835d-174">Microsoft Edge Privacy Whitepaper</span></span>](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper)
