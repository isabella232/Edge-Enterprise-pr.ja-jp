---
title: Microsoft Edge 同期を構成およびトラブルシューティングする
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 01/22/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 同期を構成およびトラブルシューティングする
ms.openlocfilehash: 36912d2fd1c33a227ce1d4b7c912f6ef1dfdcc00
ms.sourcegitcommit: 8a88fd38bdb5e132e89bf17dd2b5fb72f5d1b4b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297459"
---
# <span data-ttu-id="c2400-103">Microsoft Edge 同期を構成およびトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="c2400-103">Configure and troubleshoot Microsoft Edge sync</span></span>

<span data-ttu-id="c2400-104">この記事では、Microsoft Edge を使用して、サインインしているすべてのデバイスでお気に入り、パスワード、その他のブラウザー データを同期する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2400-104">This article explains how to configure and use Microsoft Edge to sync your favorites, passwords, and other browser data across all your signed-in devices.</span></span> <span data-ttu-id="c2400-105">この記事では、最も一般的に発生する同期の問題に対するトラブルシューティング手順も提供します。</span><span class="sxs-lookup"><span data-stu-id="c2400-105">This article also provides troubleshooting steps for the most commonly encountered sync issues.</span></span> <span data-ttu-id="c2400-106">また、トラブルシューティングに必要なログを収集するために推奨されるツールも含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2400-106">It also includes the recommended tools for gathering the logs needed for troubleshooting.</span></span>

> [!NOTE]
> <span data-ttu-id="c2400-107">この記事は、特に指定されない限り、Microsoft Edge バージョン 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c2400-107">Applies to Microsoft Edge version 77 or later unless otherwise noted.</span></span>

## <span data-ttu-id="c2400-108">概要</span><span class="sxs-lookup"><span data-stu-id="c2400-108">Overview</span></span>

<span data-ttu-id="c2400-109">Microsoft Edge の同期を使用すると、ユーザーは、サインインしているすべてのデバイスで閲覧データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c2400-109">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="c2400-110">同期でサポートされるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c2400-110">The data supported by sync includes:</span></span>

- <span data-ttu-id="c2400-111">お気に入り</span><span class="sxs-lookup"><span data-stu-id="c2400-111">Favorites</span></span>
- <span data-ttu-id="c2400-112">パスワード</span><span class="sxs-lookup"><span data-stu-id="c2400-112">Passwords</span></span>
- <span data-ttu-id="c2400-113">住所など (フォームの入力情報)</span><span class="sxs-lookup"><span data-stu-id="c2400-113">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="c2400-114">コレクション</span><span class="sxs-lookup"><span data-stu-id="c2400-114">Collections</span></span>
- <span data-ttu-id="c2400-115">設定</span><span class="sxs-lookup"><span data-stu-id="c2400-115">Settings</span></span>
- <span data-ttu-id="c2400-116">拡張機能</span><span class="sxs-lookup"><span data-stu-id="c2400-116">Extension</span></span>
- <span data-ttu-id="c2400-117">タブを開く (Microsoft Edge バージョン 88 で利用可能)</span><span class="sxs-lookup"><span data-stu-id="c2400-117">Open tabs (available in Microsoft Edge version 88)</span></span>
- <span data-ttu-id="c2400-118">履歴 (Microsoft Edge バージョン 88 で利用可能)</span><span class="sxs-lookup"><span data-stu-id="c2400-118">History (available in Microsoft Edge version 88)</span></span>

<span data-ttu-id="c2400-119">同期機能はユーザーの同意によって有効になり、ユーザーは上記の各データ タイプについて同期をオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c2400-119">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span>

> [!NOTE]
> <span data-ttu-id="c2400-120">同期機能をサポートするために、デバイスの接続および構成データ (デバイス名、製造元、モデルなど) がアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="c2400-120">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <span data-ttu-id="c2400-121">前提条件</span><span class="sxs-lookup"><span data-stu-id="c2400-121">Prerequisites</span></span>

<span data-ttu-id="c2400-122">Azure Active Directory (Azure AD) アカウントでの Microsoft Edge の同期は、次のサブスクリプションのいずれかで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2400-122">Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for any of the following subscriptions:</span></span>

- <span data-ttu-id="c2400-123">Azure AD Premium (P1 または P2)</span><span class="sxs-lookup"><span data-stu-id="c2400-123">Azure AD Premium (P1 or P2)</span></span>
- <span data-ttu-id="c2400-124">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="c2400-124">M365 Business Premium</span></span>
- <span data-ttu-id="c2400-125">Office 365 E1 以上</span><span class="sxs-lookup"><span data-stu-id="c2400-125">Office 365 E1 and above</span></span>
- <span data-ttu-id="c2400-126">Azure Information Protection (AIP) (P1 または P2)</span><span class="sxs-lookup"><span data-stu-id="c2400-126">Azure Information Protection (AIP) (P1 or P2)</span></span>
- <span data-ttu-id="c2400-127">すべての EDU サブスクリプション (学生または教職員向けの Microsoft Apps、学生または教職員向けの Exchange Online、O365 A1 以上、M365 A1 以上、学生または教職員向けの Azure Information Protection P1 または P2)</span><span class="sxs-lookup"><span data-stu-id="c2400-127">All EDU subscriptions (Microsoft Apps for Students or Faculty, Exchange Online for Students or Faculty, O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

## <span data-ttu-id="c2400-128">同期グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="c2400-128">Sync group policies</span></span>

<span data-ttu-id="c2400-129">Microsoft Edge の同期を構成および管理するには、次のグループ ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2400-129">You can use the following group policies to configure and manage Microsoft Edge sync:</span></span>

- <span data-ttu-id="c2400-130">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): 同期を完全に無効にします。</span><span class="sxs-lookup"><span data-stu-id="c2400-130">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="c2400-131">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): 閲覧の履歴と同期の保存を無効にします。このポリシーにより、オープン タブの同期も無効になります。</span><span class="sxs-lookup"><span data-stu-id="c2400-131">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="c2400-132">[AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory): このポリシーを無効に設定すると、履歴の同期も無効になります。</span><span class="sxs-lookup"><span data-stu-id="c2400-132">[AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory): When this policy is set to disabled, history sync will also be disabled.</span></span>
- <span data-ttu-id="c2400-133">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): 同期から除外されるタイプの一覧を構成します。</span><span class="sxs-lookup"><span data-stu-id="c2400-133">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>
- <span data-ttu-id="c2400-134">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Active Directory (AD) プロファイルがオンプレミスの記憶域を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c2400-134">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Allow Active Directory (AD) profiles to use on-premises storage.</span></span> <span data-ttu-id="c2400-135">詳細については、「[Active Directory (AD) ユーザー用のオンプレミス同期](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2400-135">For more information, see [On-premises sync for Active Directory (AD) users](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).</span></span>
- <span data-ttu-id="c2400-136">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): 既定で同期をオンにします。同期にはユーザーの同意を必要としません。</span><span class="sxs-lookup"><span data-stu-id="c2400-136">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): Turn on sync by default and do not require user consent to sync.</span></span>  

## <span data-ttu-id="c2400-137">Microsoft Edge を構成する</span><span class="sxs-lookup"><span data-stu-id="c2400-137">Configure Microsoft Edge sync</span></span>

<span data-ttu-id="c2400-138">Microsoft Edge の同期の構成オプションは、Azure Information Protection (AIP) サービスを介して利用できます。</span><span class="sxs-lookup"><span data-stu-id="c2400-138">Configuration options for Microsoft Edge sync are available through the Azure Information Protection (AIP) service.</span></span> <span data-ttu-id="c2400-139">テナントの AIP が有効になっている場合、ライセンスに関係なくすべてのユーザーが Microsoft Edge のデータを同期できます。</span><span class="sxs-lookup"><span data-stu-id="c2400-139">When AIP is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="c2400-140">AIP を有効にする方法は、[ここ](https://docs.microsoft.com/azure/information-protection/activate-office365)で説明されています。</span><span class="sxs-lookup"><span data-stu-id="c2400-140">Instructions on how to enable AIP can be found [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="c2400-141">特定のユーザー セットに対して同期を制限するために、これらのユーザーに対して [AIP のオンボード制御ポリシー](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c2400-141">To restrict sync to certain set of users, you can enable the [AIP onboarding control policy](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) for those users.</span></span> <span data-ttu-id="c2400-142">必要なユーザーがすべてオンボードされた後でも同期ができない場合には、[Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true) PowerShell コマンドレット を使用して IPCv3Service が有効になっていることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="c2400-142">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true)  PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="c2400-143">Azure Information Protection を有効にすると、AIP を使用してコンテンツを保護するために Microsoft Word や Microsoft Outlook などの他のアプリケーションも許可されます。</span><span class="sxs-lookup"><span data-stu-id="c2400-143">Activating Azure Information Protection will also allow other applications, such as Microsoft Word or Microsoft Outlook, to protect content with AIP.</span></span> <span data-ttu-id="c2400-144">また、Microsoft Edge 同期を制限するために使用されるオンボード制御ポリシーは、他のアプリケーションが AIP を使用してコンテンツを保護することも制限します。</span><span class="sxs-lookup"><span data-stu-id="c2400-144">In addition, any onboarding control policy used to restrict Edge sync will also restrict other applications from protecting content using AIP.</span></span>

## <span data-ttu-id="c2400-145">Microsoft Edge と Enterprise State Roaming (ESR)</span><span class="sxs-lookup"><span data-stu-id="c2400-145">Microsoft Edge and Enterprise State Roaming (ESR)</span></span>

<span data-ttu-id="c2400-146">新しい Microsoft Edge は、ユーザー データの同期の範囲をすべてのデバイスに拡張したクロスプラットフォーム アプリケーションであり、Azure AD Enterprise State Roaming の一部ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c2400-146">Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longaer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="c2400-147">ただし、Microsoft Edge では、独自のキーを取り込む機能など、ESR のデータ保護の約束を満たしています。</span><span class="sxs-lookup"><span data-stu-id="c2400-147">However, the Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="c2400-148">詳細については、「[Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2400-148">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <span data-ttu-id="c2400-149">同期に関する問題のトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="c2400-149">Troubleshoot sync issues</span></span>

<span data-ttu-id="c2400-150">このセクションでは、最も頻繁に発生した同期に関する問題のトラブルシューティング手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="c2400-150">This section provides troubleshooting steps for the most encountered sync issues.</span></span> <span data-ttu-id="c2400-151">また、トラブルシューティングに必要なログを収集するために推奨されるツールも含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2400-151">It also includes the recommended tools for gathering the logs needed for troubleshooting.</span></span>

### <span data-ttu-id="c2400-152">ID の問題と同期の問題</span><span class="sxs-lookup"><span data-stu-id="c2400-152">Identity issues versus sync issues</span></span>

<span data-ttu-id="c2400-153">ブラウザーでユーザー ID を維持するための一般的な使用例は、同期をサポートすることです。このため、ID の問題は、多くの場合、同期の問題と混同されます。</span><span class="sxs-lookup"><span data-stu-id="c2400-153">A popular use case for maintaining user identity in the browser is to support sync. For this reason, identity issues are frequently confused with sync issues.</span></span> <span data-ttu-id="c2400-154">同期のトラブルシューティングを開始する前に、ID と同期の問題の違いを理解してください。</span><span class="sxs-lookup"><span data-stu-id="c2400-154">Understand the difference between identity and sync issue before you start troubleshooting sync.</span></span>

<span data-ttu-id="c2400-155">問題を同期の問題として扱う前に、ユーザーが有効なアカウントでブラウザーにサインインしているかどうか確認します。</span><span class="sxs-lookup"><span data-stu-id="c2400-155">Before you treat an issue as a sync issue, check to see if the user is signed into the browser with a valid account.</span></span>

<span data-ttu-id="c2400-156">次のスクリーンショットは、ID エラーの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="c2400-156">The next screenshot shows an example of an identity error.</span></span> <span data-ttu-id="c2400-157">エラーは**資格情報**の下にある*edge://sync-internals*にある "**ラスト トークン エラー、 EDGE_AUTH_ERROR: 3, 54, 3ea**"です。</span><span class="sxs-lookup"><span data-stu-id="c2400-157">The error is "**Last Token Error, EDGE_AUTH_ERROR: 3, 54, 3ea**", which is found in *edge://sync-internals* under **Credentials**:</span></span>

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-identity-issue.png" alt-text="ラスト トークン エラー EDGE_AUTH_ERROR: 3,54、3ea":::

### <span data-ttu-id="c2400-159">同期に関する一般的な問題</span><span class="sxs-lookup"><span data-stu-id="c2400-159">Common sync issues</span></span>

#### <span data-ttu-id="c2400-160">問題 : M365 または Azure Information Protection サブスクリプションにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="c2400-160">Issue: Can't access M365 or Azure Information Protection subscription</span></span>

<span data-ttu-id="c2400-161">以前 M365 または Azure Information Protection (AIP) サブスクリプションの期限が切れて、新しいサブスクリプションに置き換えたということはありませんか?</span><span class="sxs-lookup"><span data-stu-id="c2400-161">Do you have a previous M365 or Azure Information Protection (AIP) subscription that expired and then replaced with a new subscription?</span></span> <span data-ttu-id="c2400-162">その場合は、テナント ID が変更されているので、サービス データをリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2400-162">If so, then the tenant ID has changed and the service data needs to be reset.</span></span> <span data-ttu-id="c2400-163">**「Cryptographer (暗号作成者) エラーが発生した** 問題」で、データ リセットの手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c2400-163">See the instructions for resetting data in the **Cryptographer error encountered** issue.</span></span>

#### <span data-ttu-id="c2400-164">問題 : "このアカウントでは同期できません。"</span><span class="sxs-lookup"><span data-stu-id="c2400-164">Issue: “Sync is not available for this account.”</span></span>

<span data-ttu-id="c2400-165">Azure Active Directory アカウントでこのエラーが発生した場合、または *edge://sync-internals*に DISABLED_BY_ADMIN が表示される場合は、問題が解決するまで、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c2400-165">If this error is encountered for an Azure Active Directory account, or if DISABLED_BY_ADMIN appears in *edge://sync-internals*, follow the steps in the next procedure sequentially until the problem is fixed.</span></span>

> [!NOTE]
> <span data-ttu-id="c2400-166">このエラーのソースは通常、Azure Active Directory テナントの構成変更を必要とするので、これらのトラブルシューティング手順はテナント管理者だけが実行できます。エンドユーザーは実行できません。</span><span class="sxs-lookup"><span data-stu-id="c2400-166">Because the source of this error is usually requires a configuration change in an Azure Active Directory tenant, these troubleshooting steps can only performed by a tenant admin and not by end users.</span></span>

1. <span data-ttu-id="c2400-167">エンタープライズ テナントにサポートされている M365 サブスクリプションがあるかどうか確認します。</span><span class="sxs-lookup"><span data-stu-id="c2400-167">Verify that the enterprise tenant has a supported M365 subscription.</span></span> <span data-ttu-id="c2400-168">利用可能なサブスクリプションの種類の最新の一覧は [ここに表示されています](https://docs.microsoft.com/azure/information-protection/activate-office365)。</span><span class="sxs-lookup"><span data-stu-id="c2400-168">The current list of available subscription types is [provided here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span> <span data-ttu-id="c2400-169">テナントにサポートされているサブスクリプションが存在しない場合は、Azure Information Protection を個別に購入するか、サポートされているサブスクリプションにアップグレードすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="c2400-169">If the tenant doesn't have a supported subscription, they can either purchase Azure Information Protection separately, or upgrade to one of the supported subscriptions.</span></span>
2. <span data-ttu-id="c2400-170">サポートされているサブスクリプションが利用可能な場合は、テナントが Azure Information Protection (AIP) を使用できる構成にしているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2400-170">If a supported subscription is available, verify that the tenant has Azure Information Protection (AIP) available.</span></span> <span data-ttu-id="c2400-171">AIP の状態を確認し、必要に応じて、AIP をアクティブ化するための手順については、 [ここ](https://docs.microsoft.com/azure/information-protection/activate-office365)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c2400-171">The instructions for checking the AIP status and, if necessary, activating AIP are [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>
3. <span data-ttu-id="c2400-172">手順 2 で AIP がアクティブであるのに同期が機能しない場合は、Enterprise State Roaming (ESR) をオンにします。</span><span class="sxs-lookup"><span data-stu-id="c2400-172">If step 2 shows that AIP is active but sync still doesn't work, turn on Enterprise State Roaming (ESR).</span></span> <span data-ttu-id="c2400-173">ESR を有効にする手順は [ここ](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c2400-173">The instructions for enabling ESR are [here](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span> <span data-ttu-id="c2400-174">ESR を使用し続ける必要はない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c2400-174">Note that ESR does not need to stay on.</span></span> <span data-ttu-id="c2400-175">この手順で問題が解決した場合は、ESR をオフにします。</span><span class="sxs-lookup"><span data-stu-id="c2400-175">You can turn off ESR if this step fixes the issue.</span></span>
4. <span data-ttu-id="c2400-176">Azure Information Protection が登録ポリシーによって範囲を設定されていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="c2400-176">Confirm that Azure Information Protection is not scoped via an onboarding policy.</span></span> <span data-ttu-id="c2400-177">[Get-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps)  PowerShell アプレットを使用して、範囲が設定されているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c2400-177">You can use the [Get-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps)  PowerShell applet to see if scoping is enabled.</span></span> <span data-ttu-id="c2400-178">次の 2 つの例では、範囲が設定されていない構成の例と、特定のセキュリティ グループを対象に範囲が設定されている構成の例を示します。</span><span class="sxs-lookup"><span data-stu-id="c2400-178">The next two examples show an unscoped configuration and a configuration scoped to a specific security group.</span></span>

   ```powershell
    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False 
   ```

   ```powershell

    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False f1488a05-8196-40a6-9483-524948b90282   All
   ```


   <span data-ttu-id="c2400-179">範囲指定が有効な場合、影響を受けるユーザーを、範囲のセキュリティ グループに追加するか、または範囲を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2400-179">If scoping is enabled, the affected user should either be added to the security group for the scope, or the scope should be removed.</span></span> <span data-ttu-id="c2400-180">次の例では、登録で AIP の範囲が指定されたセキュリティ グループに設定されています。[Set-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell アプレットを使用して範囲を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2400-180">In the example below, onboarding has scoped AIP to the indicated security group and the scoping should be removed with the [Set-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell applet.</span></span>

5. <span data-ttu-id="c2400-181">テナントで IIPCv3Service が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2400-181">Confirm that the IPCv3Service is turned on in the tenant.</span></span> <span data-ttu-id="c2400-182">[Get-AadrmConfiguration](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps)  PowerShell のアプレットがサービスの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="c2400-182">The [Get-AadrmConfiguration](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps)  PowerShell applet shows the status of the service.</span></span>

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-scoped-cfg-example.png" alt-text="IPCv3Service が有効になっているどうか確認します。":::

6. <span data-ttu-id="c2400-184">問題が解決しない場合は、[Microsoft Edge のサポート](https://www.microsoftedgeinsider.com/support)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="c2400-184">If the issue isn't fixed, contact [Microsoft Edge support](https://www.microsoftedgeinsider.com/support).</span></span>

#### <span data-ttu-id="c2400-185">問題 : "同期の設定..." でスタックする。または "同期サーバーに接続できません。</span><span class="sxs-lookup"><span data-stu-id="c2400-185">Issue: Stuck at "Setting up sync..." or “Couldn’t connect to the sync server.</span></span> <span data-ttu-id="c2400-186">再試行中…”</span><span class="sxs-lookup"><span data-stu-id="c2400-186">Retrying…”</span></span>

1. <span data-ttu-id="c2400-187">サインアウトし、もう一度サインインします。</span><span class="sxs-lookup"><span data-stu-id="c2400-187">Try to sign out and then sign in.</span></span>
2. <span data-ttu-id="c2400-188">「*edge://sync-internals*」へ移動します。</span><span class="sxs-lookup"><span data-stu-id="c2400-188">Go to *edge://sync-internals*.</span></span> <span data-ttu-id="c2400-189">次のエラーが "**情報入力**"セクションの下に表示される場合は、次の問題、**「発生した Cryptographer エラー」** に進みます。</span><span class="sxs-lookup"><span data-stu-id="c2400-189">If under the "**Type info**" section the following error is present, then  skip to the following issue, **Cryptographer error encountered**.</span></span>

   `"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered"`

3. <span data-ttu-id="c2400-190">サーバー エンドポイントに対して ping を実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="c2400-190">Try pinging the server endpoint.</span></span> <span data-ttu-id="c2400-191">クライアントのサーバー エンドポイントは、次の *「edge://sync-internals」* で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2400-191">The server endpoint for a client is available in *edge://sync-internals*.</span></span> <span data-ttu-id="c2400-192">次のスクリーンショットは、**環境情報**の下のエンドポイント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="c2400-192">The next screenshot shows endpoint information under **Environment Info**.</span></span>

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-endpoint-info.png" alt-text="エンドポイント情報":::

4. <span data-ttu-id="c2400-194">サーバーのエンドポイントが空の場合、またはサーバーに対して ping を実行できない場合、またはファイアウォールが環境に存在する場合は、クライアント コンピューターが必要とするサービス エンドポイントを使用できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2400-194">If the server endpoint is empty, or if server cannot be pinged and a firewall is present in the environment, confirm that the necessary service endpoints are available to the client computer.</span></span>

   - <span data-ttu-id="c2400-195">Microsoft Edge 同期サービス エンドポイント:</span><span class="sxs-lookup"><span data-stu-id="c2400-195">Microsoft Edge sync service endpoints:</span></span>
     - [https://edge-enterprise.activity.windows.com](https://edge-enterprise.activity.windows.com)
     - [https://edge.activity.windows.com](https://edge.activity.windows.com)
    - <span data-ttu-id="c2400-196">Azure Information Protection エンドポイント:</span><span class="sxs-lookup"><span data-stu-id="c2400-196">Azure Information Protection endpoints:</span></span>
      - <span data-ttu-id="c2400-197">[https://api.aadrm.com](https://api.aadrm.com)(ほとんどのテナントの場合)</span><span class="sxs-lookup"><span data-stu-id="c2400-197">[https://api.aadrm.com](https://api.aadrm.com) (for most tenants)</span></span>
      - <span data-ttu-id="c2400-198">[https://api.aadrm.de](https://api.aadrm.de)(ドイツのテナントの場合)</span><span class="sxs-lookup"><span data-stu-id="c2400-198">[https://api.aadrm.de](https://api.aadrm.de) (for tenants in Germany)</span></span>
      - <span data-ttu-id="c2400-199">[https://api.aadrm.cn](https://api.aadrm.cn)(中国のテナントの場合)</span><span class="sxs-lookup"><span data-stu-id="c2400-199">[https://api.aadrm.cn](https://api.aadrm.cn) (for tenants in China)</span></span>
   - <span data-ttu-id="c2400-200">[Windows 通知サービス エンドポイント](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)。</span><span class="sxs-lookup"><span data-stu-id="c2400-200">[Windows Notification Service endpoints](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config).</span></span>

5. <span data-ttu-id="c2400-201">それでも問題が解決しない場合は、[Microsoft Edge のサポート](https://www.microsoftedgeinsider.com/support)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="c2400-201">If the issue still isn't fixed, contact [Microsoft Edge support](https://www.microsoftedgeinsider.com/support).</span></span>

### <span data-ttu-id="c2400-202">問題: Cryptographer エラーが発生する</span><span class="sxs-lookup"><span data-stu-id="c2400-202">Issue: Cryptographer error encountered</span></span>

<span data-ttu-id="c2400-203">このエラーは、*edge://sync-internals* の**種類情報** に表示され、ユーザーのサービス側のデータをリセットする必要があることを意味している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c2400-203">This error is visible under **Type info** in *edge://sync-internals* and may mean that the user's service side data needs to be reset.</span></span> <span data-ttu-id="c2400-204">次の例は、暗号化のエラー メッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="c2400-204">The following example shows a cryptography error message:</span></span>
<br><span data-ttu-id="c2400-205">"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered"。</span><span class="sxs-lookup"><span data-stu-id="c2400-205">"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered".</span></span>

1. <span data-ttu-id="c2400-206">Microsoft Edge を再起動し、*「edge://sync-internals」* に移動し、**「AAD アカウントキーの状態」** セクションを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2400-206">Restart Microsoft Edge and navigate to *edge://sync-internals* and check the “**AAD Account Key Status**” section</span></span>
   - <span data-ttu-id="c2400-207">"最終 MIP 結果" での "成功": Cryptographer エラーは、サーバー データが失われたキーで暗号化されている可能性を意味します。</span><span class="sxs-lookup"><span data-stu-id="c2400-207">"Success" in "Last MIP Result": the cryptographer error means server data might be encrypted with a lost key.</span></span> <span data-ttu-id="c2400-208">同期を再開するには、データのリセットが必要です。</span><span class="sxs-lookup"><span data-stu-id="c2400-208">Data reset is needed to resume sync.</span></span>
   - <span data-ttu-id="c2400-209">"最後の MIP 結果" に "アクセス許可なし": Azure AD の変更またはテナントのサブスクリプションの変更が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c2400-209">"No permissions" in "Last MIP Result": It is possibly caused by an Azure AD change or tenant subscription changes.</span></span> <span data-ttu-id="c2400-210">同期を再開するには、データのリセットが必要です。</span><span class="sxs-lookup"><span data-stu-id="c2400-210">Data reset is needed to resume sync.</span></span>
   - <span data-ttu-id="c2400-211">その他のエラーは、サーバー構成の問題を意味する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c2400-211">Other errors may mean server configuration issues.</span></span>
2. <span data-ttu-id="c2400-212">データのリセットが必要な場合は、[「 クラウドのMicrosoft Edge データをリセットする」](edge-learnmore-reset-data-in-cloud.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2400-212">If data reset is needed, see [Reset Microsoft Edge data in the cloud](edge-learnmore-reset-data-in-cloud.md).</span></span>

#### <span data-ttu-id="c2400-213">問題: "同期は管理者によってオフにされています。"</span><span class="sxs-lookup"><span data-stu-id="c2400-213">Issue: “Sync has been turned off by your administrator.”</span></span>

<span data-ttu-id="c2400-214">[SyncDisabled ポリシー](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)が設定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2400-214">Make sure that the [SyncDisabled policy](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)  is not set.</span></span>

## <span data-ttu-id="c2400-215">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="c2400-215">Frequently Asked Questions</span></span>

### <span data-ttu-id="c2400-216">セキュリティとサーバー/データのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="c2400-216">SECURITY and SERVER/DATA COMPLIANCE</span></span>

#### <span data-ttu-id="c2400-217">同期したデータは暗号化されていますか?</span><span class="sxs-lookup"><span data-stu-id="c2400-217">Is the synced data encrypted?</span></span>

<span data-ttu-id="c2400-218">データは TLS 1.2 以上を使用してトランスポートで暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="c2400-218">The data is encrypted in transport using TLS 1.2 or greater.</span></span> <span data-ttu-id="c2400-219">すべてのデータ型は、AES128 を使用して Microsoft のサービスで保存中にさらに暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="c2400-219">All data types are additionally encrypted at rest in Microsoft's service using AES128.</span></span> <span data-ttu-id="c2400-220">オープン タブと履歴の同期に使用されるデータ型を除くすべてのデータ型は、[Azure Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern)ポリシーで管理されているキーを使ってユーザーのデバイスを離れる前に、さらに暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="c2400-220">All data types except those used for open tab and history sync are additionally encrypted before leaving the user’s device with keys managed via the [Azure Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

#### <span data-ttu-id="c2400-221">オープンタブと履歴データにクライアント側の暗号化を追加しない理由はなぜでしょうか?</span><span class="sxs-lookup"><span data-stu-id="c2400-221">Why don’t open tab and history data have more client-side encryption?</span></span>

<span data-ttu-id="c2400-222">エンド ユーザー のデバイスでのリソース使用率を削減するために、オープン タブ ローミング データに基づいてサーバー側で履歴データが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c2400-222">To reduce resource utilization on end-user devices, history data is generated server-side based on open tab roaming data.</span></span> <span data-ttu-id="c2400-223">このプロセスは、このデータのクライアント側の暗号化では実行できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c2400-223">This process would not be possible with client-side encryption of this data.</span></span> <span data-ttu-id="c2400-224">オープン タブと履歴の同期を無効にするには [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) または [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="c2400-224">To disable open tab and history sync, apply the [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) or [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) policies.</span></span>

#### <span data-ttu-id="c2400-225">テナント管理者が独自のキーを使用することはできますか?</span><span class="sxs-lookup"><span data-stu-id="c2400-225">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="c2400-226">はい [、Azure Information Protection を経由して可能です](https://azure.microsoft.com/services/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="c2400-226">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

#### <span data-ttu-id="c2400-227">Microsoft Edge の同期データはどこに保存されますか?</span><span class="sxs-lookup"><span data-stu-id="c2400-227">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="c2400-228">Azure AD アカウントの同期されたデータは、テナント ID に従って、セキュリティで保護されたサーバーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c2400-228">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="c2400-229">たとえば、米国に登録されているテナントのデータは地理的にその地域にあるサーバーに保存され、Office アプリケーションで使用されるストレージ ソリューションと同じソリューションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c2400-229">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

#### <span data-ttu-id="c2400-230">Microsoft Edge との同期以外に、データが Microsoft のクラウドから移動することはありますか?</span><span class="sxs-lookup"><span data-stu-id="c2400-230">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="c2400-231">いいえ、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="c2400-231">No.</span></span>

#### <span data-ttu-id="c2400-232">エンタープライズ向けの同期には、どのサービス使用条件が適用されますか?</span><span class="sxs-lookup"><span data-stu-id="c2400-232">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="c2400-233">Microsoft Edge 同期のサービス条件は、Microsoft ソフトウェア ライセンスに含まれており、 *edge://terms*の「Microsoft Edge」で確認が可能です。</span><span class="sxs-lookup"><span data-stu-id="c2400-233">Terms of service for Microsoft Edge sync falls under the Microsoft software license viewable in Microsoft Edge at *edge://terms*.</span></span> <span data-ttu-id="c2400-234">Azure ADサブスクリプションとサービス条件は、最終的には Microsoft の[オンライン サービス規約](https://www.microsoft.com/licensing/product-licensing/products)を適用します。 </span><span class="sxs-lookup"><span data-stu-id="c2400-234">Your Azure AD subscription and terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

#### <span data-ttu-id="c2400-235">Microsoft Edge は、Government Community Cloud (GCC) の高コンプライアンスをサポートしていますか?</span><span class="sxs-lookup"><span data-stu-id="c2400-235">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="c2400-236">現時点ではサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c2400-236">Not today.</span></span> <span data-ttu-id="c2400-237">GCC High クラウドのユーザーの場合、Microsoft Edge の同期は無効になります。</span><span class="sxs-lookup"><span data-stu-id="c2400-237">For customers in the GCC High cloud, Microsoft Edge sync is disabled.</span></span>

### <span data-ttu-id="c2400-238">同期の適用</span><span class="sxs-lookup"><span data-stu-id="c2400-238">APPLYING SYNC</span></span>

#### <span data-ttu-id="c2400-239">Microsoft Edge の同期がすべての M365 サブスクリプションでサポートされていないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="c2400-239">Why isn’t Microsoft Edge sync supported in all M365 subscriptions?</span></span>

<span data-ttu-id="c2400-240">エンタープライズ同期は、すべての M365 サブスクリプションで利用できない [Azure Information Protection](https://azure.microsoft.com/services/information-protection/) に依存しています。</span><span class="sxs-lookup"><span data-stu-id="c2400-240">Enterprise sync depends on [Azure Information Protection](https://azure.microsoft.com/services/information-protection/), which is not available in all M365 subscriptions.</span></span>

#### <span data-ttu-id="c2400-241">Microsoft Edge の同期は Enterprise State Roaming に依存していますか?</span><span class="sxs-lookup"><span data-stu-id="c2400-241">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="c2400-242">いいえ、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="c2400-242">No.</span></span> <span data-ttu-id="c2400-243">ESR を使用して同期を有効にすることはできますが、Microsoft Edge の同期は ESR の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="c2400-243">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="c2400-244">詳細については、「[Microsoft Edge の同期](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-sync)」と「[Microsoft Edge と Enterprise State Roaming](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-state-roaming)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2400-244">For more information, see [Microsoft Edge Sync](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-sync) and [Microsoft Edge and Enterprise State Roaming](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-state-roaming).</span></span>

#### <span data-ttu-id="c2400-245">Microsoft Edge では、将来 Microsoft Edge と IE との同期はサポートされますか?</span><span class="sxs-lookup"><span data-stu-id="c2400-245">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="c2400-246">その同期をサポートする計画はありません。</span><span class="sxs-lookup"><span data-stu-id="c2400-246">There are no plans to support this syncing.</span></span> <span data-ttu-id="c2400-247">ご自分の環境で従来のアプリをサポートするために IE を使用する必要がある場合、[新しい IE モード](https://docs.microsoft.com/deployedge/edge-ie-mode)を検討してください。</span><span class="sxs-lookup"><span data-stu-id="c2400-247">If you still need IE in your environment to support legacy apps, consider our [new IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>

#### <span data-ttu-id="c2400-248">Microsoft Edge は Microsoft Edge レガシと同期しますか?</span><span class="sxs-lookup"><span data-stu-id="c2400-248">Will Microsoft Edge sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="c2400-249">いいえ、同期されません。</span><span class="sxs-lookup"><span data-stu-id="c2400-249">No, it won't.</span></span> <span data-ttu-id="c2400-250">これら 2 つのエコシステムを接続すると、Microsoft Edge の同期の信頼性が損なわれると考えています。</span><span class="sxs-lookup"><span data-stu-id="c2400-250">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the Microsoft Edge.</span></span> <span data-ttu-id="c2400-251">既存のデータが Microsoft Edge に移行されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2400-251">We will ensure that existing data is migrated to the Microsoft Edge.</span></span> <span data-ttu-id="c2400-252">ユーザーは選択したブラウザーからデータをインポートすることもできます。つまり、Microsoft Edge には IE と同期する方法が用意されていないということです。</span><span class="sxs-lookup"><span data-stu-id="c2400-252">Users will also be able to import data from browser of their choice, which also means that Microsoft Edge won't have a way to sync with IE.</span></span>

### <span data-ttu-id="c2400-253">同期の管理</span><span class="sxs-lookup"><span data-stu-id="c2400-253">MANAGING SYNC</span></span>

#### <span data-ttu-id="c2400-254">ユーザーに個人用テナントと同期させないようにすることはできますか?</span><span class="sxs-lookup"><span data-stu-id="c2400-254">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="c2400-255">直接はできませんが、[RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) ポリシーを使用して、Microsoft Edge にサインオンできるプロファイルを定義することはできます。</span><span class="sxs-lookup"><span data-stu-id="c2400-255">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

## <span data-ttu-id="c2400-256">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2400-256">See also</span></span>

- [<span data-ttu-id="c2400-257">Microsoft Edge エンタープライズの同期</span><span class="sxs-lookup"><span data-stu-id="c2400-257">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="c2400-258">Microsoft Edge と Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="c2400-258">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="c2400-259">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="c2400-259">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
