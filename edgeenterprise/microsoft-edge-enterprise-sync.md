---
title: Microsoft Edge エンタープライズの同期
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 12/09/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge エンタープライズの同期
ms.openlocfilehash: 791188b5d28c867d6409a4d5373ea6c1ec7e49c7
ms.sourcegitcommit: 482b2e440a62cbf974dc45ac817f9d9d187ba1b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "11205466"
---
# <span data-ttu-id="e5115-103">Microsoft Edge エンタープライズの同期</span><span class="sxs-lookup"><span data-stu-id="e5115-103">Microsoft Edge Enterprise Sync</span></span>

<span data-ttu-id="e5115-104">この記事では、Microsoft Edge を使用して、サインインしているすべてのデバイスでお気に入り、パスワード、その他のブラウザー データを同期する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5115-104">This article explains how to use Microsoft Edge to sync your favorites, passwords, and other browser data across all your signed-in devices.</span></span>

> [!NOTE]
> <span data-ttu-id="e5115-105">この記事は、特に説明がない限り、Microsoft Edge バージョン 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e5115-105">This article applies to Microsoft Edge version 77 or later unless otherwise noted.</span></span>

## <span data-ttu-id="e5115-106">概要</span><span class="sxs-lookup"><span data-stu-id="e5115-106">Overview</span></span>

<span data-ttu-id="e5115-107">Microsoft Edge の同期を使用すると、ユーザーは、サインインしているすべてのデバイスで閲覧データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e5115-107">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="e5115-108">同期でサポートされるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5115-108">The data supported by sync includes:</span></span>

- <span data-ttu-id="e5115-109">お気に入り</span><span class="sxs-lookup"><span data-stu-id="e5115-109">Favorites</span></span>
- <span data-ttu-id="e5115-110">パスワード</span><span class="sxs-lookup"><span data-stu-id="e5115-110">Passwords</span></span>
- <span data-ttu-id="e5115-111">住所など (フォームの入力情報)</span><span class="sxs-lookup"><span data-stu-id="e5115-111">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="e5115-112">コレクション</span><span class="sxs-lookup"><span data-stu-id="e5115-112">Collections</span></span>
- <span data-ttu-id="e5115-113">設定</span><span class="sxs-lookup"><span data-stu-id="e5115-113">Settings</span></span>
- <span data-ttu-id="e5115-114">拡張機能</span><span class="sxs-lookup"><span data-stu-id="e5115-114">Extension</span></span>
- <span data-ttu-id="e5115-115">タブを開く (Microsoft Edge バージョン 88 で利用可能)</span><span class="sxs-lookup"><span data-stu-id="e5115-115">Open tabs (available in Microsoft Edge version 88)</span></span>
- <span data-ttu-id="e5115-116">履歴 (Microsoft Edge バージョン 88 で利用可能)</span><span class="sxs-lookup"><span data-stu-id="e5115-116">History (available in Microsoft Edge version 88)</span></span>

<span data-ttu-id="e5115-117">同期機能はユーザーの同意によって有効になり、ユーザーは上記の各データ タイプについて同期をオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5115-117">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span>

> [!NOTE]
> <span data-ttu-id="e5115-118">同期機能をサポートするために、デバイスの接続および構成データ (デバイス名、製造元、モデルなど) がアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="e5115-118">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <span data-ttu-id="e5115-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="e5115-119">Prerequisites</span></span>

<span data-ttu-id="e5115-120">Azure Active Directory (Azure AD) アカウントでの Microsoft Edge の同期は、次のサブスクリプションのいずれかで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5115-120">Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for any of the following subscriptions:</span></span>

- <span data-ttu-id="e5115-121">Azure AD Premium (P1 または P2)</span><span class="sxs-lookup"><span data-stu-id="e5115-121">Azure AD Premium (P1 or P2)</span></span>
- <span data-ttu-id="e5115-122">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="e5115-122">M365 Business Premium</span></span>
- <span data-ttu-id="e5115-123">Office 365 E1 以上</span><span class="sxs-lookup"><span data-stu-id="e5115-123">Office 365 E1 and above</span></span>
- <span data-ttu-id="e5115-124">Azure Information Protection (AIP) (P1 または P2)</span><span class="sxs-lookup"><span data-stu-id="e5115-124">Azure Information Protection (AIP) (P1 or P2)</span></span>
- <span data-ttu-id="e5115-125">すべての EDU サブスクリプション (学生または教職員向けの Microsoft Apps、学生または教職員向けの Exchange Online、O365 A1 以上、M365 A1 以上、学生または教職員向けの Azure Information Protection P1 または P2)</span><span class="sxs-lookup"><span data-stu-id="e5115-125">All EDU subscriptions (Microsoft Apps for Students or Faculty, Exchange Online for Students or Faculty, O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

## <span data-ttu-id="e5115-126">Microsoft Edge の同期の構成</span><span class="sxs-lookup"><span data-stu-id="e5115-126">Configuring Microsoft Edge sync</span></span>

<span data-ttu-id="e5115-127">Microsoft Edge の同期の構成オプションは、Azure Information Protection (AIP) サービスを介して利用できます。</span><span class="sxs-lookup"><span data-stu-id="e5115-127">Configuration options for Microsoft Edge sync are available through the Azure Information Protection (AIP) service.</span></span> <span data-ttu-id="e5115-128">テナントの AIP が有効になっている場合、ライセンスに関係なくすべてのユーザーが Microsoft Edge のデータを同期できます。</span><span class="sxs-lookup"><span data-stu-id="e5115-128">When AIP is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="e5115-129">AIP を有効にする方法は、[ここ](https://docs.microsoft.com/azure/information-protection/activate-office365)で説明されています。</span><span class="sxs-lookup"><span data-stu-id="e5115-129">Instructions on how to enable AIP can be found [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="e5115-130">特定のユーザー セットに対して同期を制限するために、これらのユーザーに対して [AIP のオンボード制御ポリシー](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5115-130">To restrict sync to certain set of users, you can enable the [AIP onboarding control policy](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) for those users.</span></span> <span data-ttu-id="e5115-131">必要なユーザーがすべてオンボードされた後でも同期ができない場合には、[Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true) PowerShell コマンドレット を使用して IPCv3Service が有効になっていることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="e5115-131">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true)  PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="e5115-132">Azure Information Protection を有効にすると、AIP を使用してコンテンツを保護するために Microsoft Word や Microsoft Outlook などの他のアプリケーションも許可されます。</span><span class="sxs-lookup"><span data-stu-id="e5115-132">Activating Azure Information Protection will also allow other applications, such as Microsoft Word or Microsoft Outlook, to protect content with AIP.</span></span> <span data-ttu-id="e5115-133">また、エッジ同期を制限するために使用されるオンボード制御ポリシーは、他のアプリケーションが AIP を使用してコンテンツを保護することも制限します。</span><span class="sxs-lookup"><span data-stu-id="e5115-133">In addition, any onboarding control policy used to restrict Edge sync will also restrict other applications from protecting content using AIP.</span></span>

## <span data-ttu-id="e5115-134">Microsoft Edge と Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="e5115-134">Microsoft Edge and Enterprise State Roaming</span></span>

<span data-ttu-id="e5115-135">新しい Microsoft Edge は、ユーザー データの同期の範囲をすべてのデバイスに拡張したクロスプラットフォーム アプリケーションであり、Azure AD Enterprise State Roaming の一部ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e5115-135">The new Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="e5115-136">ただし、新しい Microsoft Edge では、独自のキーを取り込む機能など、ESR のデータ保護の約束を満たしています。</span><span class="sxs-lookup"><span data-stu-id="e5115-136">However, the new Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="e5115-137">詳細については、「[Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5115-137">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <span data-ttu-id="e5115-138">同期グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="e5115-138">Sync group policies</span></span>

<span data-ttu-id="e5115-139">次のグループ ポリシーは、Microsoft Edge の同期に影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="e5115-139">The following group policies impact Microsoft Edge sync:</span></span>

- <span data-ttu-id="e5115-140">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): 同期を完全に無効にします。</span><span class="sxs-lookup"><span data-stu-id="e5115-140">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="e5115-141">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): 閲覧の履歴と同期の保存を無効にします。このポリシーにより、オープン タブの同期も無効になります。</span><span class="sxs-lookup"><span data-stu-id="e5115-141">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="e5115-142">[AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory): このポリシーを無効に設定すると、履歴の同期も無効になります。</span><span class="sxs-lookup"><span data-stu-id="e5115-142">[AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory): When this policy is set to disabled, history sync will also be disabled.</span></span>
- <span data-ttu-id="e5115-143">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): 同期から除外されるタイプの一覧を構成します。</span><span class="sxs-lookup"><span data-stu-id="e5115-143">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>
- <span data-ttu-id="e5115-144">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Active Directory (AD) プロファイルがオンプレミスの記憶域を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e5115-144">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Allow Active Directory (AD) profiles to use on-premises storage.</span></span> <span data-ttu-id="e5115-145">詳細については、「[Active Directory (AD) ユーザー用のオンプレミス同期](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5115-145">For more information, see [On-premises sync for Active Directory (AD) users](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).</span></span>
- <span data-ttu-id="e5115-146">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): 既定で同期をオンにします。同期にはユーザーの同意を必要としません。</span><span class="sxs-lookup"><span data-stu-id="e5115-146">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): Turn sync on by default and do not require user consent to sync.</span></span>  

## <span data-ttu-id="e5115-147">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="e5115-147">Frequently Asked Questions</span></span>

### <span data-ttu-id="e5115-148">セキュリティとサーバー/データのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="e5115-148">SECURITY and SERVER/DATA COMPLIANCE</span></span>

#### <span data-ttu-id="e5115-149">同期したデータは暗号化されていますか?</span><span class="sxs-lookup"><span data-stu-id="e5115-149">Is the synced data encrypted?</span></span>

<span data-ttu-id="e5115-150">データは TLS 1.2 以上を使用してトランスポートで暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="e5115-150">The data is encrypted in transport using TLS 1.2 or greater.</span></span> <span data-ttu-id="e5115-151">すべてのデータ型は、AES128 を使用して Microsoft のサービスで保存中にさらに暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="e5115-151">All data types are additionally encrypted at rest in Microsoft's service using AES128.</span></span> <span data-ttu-id="e5115-152">オープン タブと履歴の同期に使用されるデータ型を除くすべてのデータ型は、[Azure Information Protection](https://docs.microsoft.com/azure/information-protection/) で管理されているキーを使ってユーザーのデバイスを離れる前に、 さらに暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="e5115-152">All data types except those used for open tab and history sync are additionally encrypted before leaving the user’s device with keys managed via [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/).</span></span>

#### <span data-ttu-id="e5115-153">オープンタブと履歴データにクライアント側の暗号化を追加しない理由はなぜでしょうか?</span><span class="sxs-lookup"><span data-stu-id="e5115-153">Why don’t open tab and history data have additional client-side encryption?</span></span>  

<span data-ttu-id="e5115-154">エンド ユーザー のデバイスでのリソース使用率を削減するために、オープン タブ ローミング データに基づいてサーバー側で履歴データが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e5115-154">In order to reduce resource utilization on end user devices, history data is generated server-side based on open tab roaming data.</span></span> <span data-ttu-id="e5115-155">このプロセスは、このデータのクライアント側の暗号化では実行できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e5115-155">This process would not be possible with client-side encryption of this data.</span></span> <span data-ttu-id="e5115-156">オープン タブと履歴の同期を無効にするには [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) または [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="e5115-156">To disable open tab and history sync, apply the [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) or [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) policies.</span></span>

#### <span data-ttu-id="e5115-157">テナント管理者が独自のキーを使用することはできますか?</span><span class="sxs-lookup"><span data-stu-id="e5115-157">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="e5115-158">はい [、Azure Information Protection を経由して可能です](https://azure.microsoft.com/services/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="e5115-158">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

#### <span data-ttu-id="e5115-159">Microsoft Edge の同期データはどこに保存されますか?</span><span class="sxs-lookup"><span data-stu-id="e5115-159">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="e5115-160">Azure AD アカウントの同期されたデータは、テナント ID に従って、セキュリティで保護されたサーバーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="e5115-160">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="e5115-161">たとえば、米国に登録されているテナントのデータは地理的にその地域にあるサーバーに保存され、Office アプリケーションで使用されるストレージ ソリューションと同じソリューションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5115-161">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

#### <span data-ttu-id="e5115-162">Microsoft Edge との同期以外に、データが Microsoft のクラウドから移動することはありますか?</span><span class="sxs-lookup"><span data-stu-id="e5115-162">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="e5115-163">いいえ、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="e5115-163">No.</span></span>

#### <span data-ttu-id="e5115-164">エンタープライズ向けの同期には、どのサービス使用条件が適用されますか?</span><span class="sxs-lookup"><span data-stu-id="e5115-164">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="e5115-165">Microsoft Edge 同期のサービス条件は、Microsoft ソフトウェア ライセンスに含まれており、 *edge://terms*の「Microsoft Edge」で確認が可能です。</span><span class="sxs-lookup"><span data-stu-id="e5115-165">Terms of service for Microsoft Edge sync falls under the Microsoft software license viewable in Microsoft Edge at *edge://terms*.</span></span> <span data-ttu-id="e5115-166">Azure ADサブスクリプションとサービス条件は、最終的には Microsoft の[オンライン サービス規約](https://www.microsoft.com/licensing/product-licensing/products)を適用します。 </span><span class="sxs-lookup"><span data-stu-id="e5115-166">Your Azure AD subscription and terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

#### <span data-ttu-id="e5115-167">Microsoft Edge は、Government Community Cloud (GCC) の高コンプライアンスをサポートしていますか?</span><span class="sxs-lookup"><span data-stu-id="e5115-167">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="e5115-168">現時点ではサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e5115-168">Not today.</span></span> <span data-ttu-id="e5115-169">GCC High クラウドのユーザーの場合、Microsoft Edge の同期は無効になります。</span><span class="sxs-lookup"><span data-stu-id="e5115-169">For customers in the GCC High cloud, Microsoft Edge sync is disabled.</span></span>

### <span data-ttu-id="e5115-170">同期の適用</span><span class="sxs-lookup"><span data-stu-id="e5115-170">APPLYING SYNC</span></span>

#### <span data-ttu-id="e5115-171">Microsoft Edge 同期がすべての M365 サブスクリプションでサポートされていないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="e5115-171">Why isn’t Microsoft Edge sync supported in all M365 subscriptions?</span></span>

<span data-ttu-id="e5115-172">エンタープライズ同期は、すべての M365 サブスクリプションで利用できる Azure Information Protection に依存しています。</span><span class="sxs-lookup"><span data-stu-id="e5115-172">Enterprise sync depends on Azure Information Protection, which is not available in all M365 subscriptions.</span></span>

#### <span data-ttu-id="e5115-173">Microsoft Edge の同期は Enterprise State Roaming に依存していますか?</span><span class="sxs-lookup"><span data-stu-id="e5115-173">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="e5115-174">いいえ、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="e5115-174">No.</span></span> <span data-ttu-id="e5115-175">ESR を使用して同期を有効にすることはできますが、Microsoft Edge の同期は ESR の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="e5115-175">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="e5115-176">詳細については、「[Microsoft Edge の同期](microsoft-edge-enterprise-sync.md)」と「[Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5115-176">For more information, see [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md) and [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

#### <span data-ttu-id="e5115-177">Microsoft Edge では、将来 Microsoft Edge と IE との同期はサポートされますか?</span><span class="sxs-lookup"><span data-stu-id="e5115-177">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="e5115-178">その同期をサポートする計画はありません。</span><span class="sxs-lookup"><span data-stu-id="e5115-178">There are no plans to support this syncing.</span></span> <span data-ttu-id="e5115-179">ご自分の環境で従来のアプリをサポートするために IE を使用する必要がある場合、[新しい IE モード](https://docs.microsoft.com/deployedge/edge-ie-mode)を検討してください。</span><span class="sxs-lookup"><span data-stu-id="e5115-179">If you still need IE in your environment to support legacy apps, consider our [new IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>

#### <span data-ttu-id="e5115-180">Microsoft Edge は Microsoft Edge レガシと同期しますか?</span><span class="sxs-lookup"><span data-stu-id="e5115-180">Will Microsoft Edge sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="e5115-181">いいえ、同期されません。</span><span class="sxs-lookup"><span data-stu-id="e5115-181">No, it won't.</span></span> <span data-ttu-id="e5115-182">これら 2 つのエコシステムを接続すると、Microsoft Edge の同期の信頼性が損なわれると考えています。</span><span class="sxs-lookup"><span data-stu-id="e5115-182">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the Microsoft Edge.</span></span> <span data-ttu-id="e5115-183">既存のデータが Microsoft Edge に移行されますことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5115-183">We will ensure that existing data is migrated to the Microsoft Edge.</span></span> <span data-ttu-id="e5115-184">ユーザーは、選択したブラウザーからデータをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e5115-184">Users will also be able to import data from browser of their choice.</span></span> <span data-ttu-id="e5115-185">これは、新しい Microsoft Edge ブラウザーが IE と同期する方法を備えていないことも意味します。</span><span class="sxs-lookup"><span data-stu-id="e5115-185">This also means that new Microsoft Edge browser won't have a way to sync with IE.</span></span>

### <span data-ttu-id="e5115-186">同期の管理</span><span class="sxs-lookup"><span data-stu-id="e5115-186">MANAGING SYNC</span></span>

#### <span data-ttu-id="e5115-187">ユーザーに個人用テナントと同期させないようにすることはできますか?</span><span class="sxs-lookup"><span data-stu-id="e5115-187">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="e5115-188">直接はできませんが、[RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) ポリシーを使用して、Microsoft Edge にサインオンできるプロファイルを定義することはできます。</span><span class="sxs-lookup"><span data-stu-id="e5115-188">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

## <span data-ttu-id="e5115-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5115-189">See also</span></span>

- [<span data-ttu-id="e5115-190">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="e5115-190">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="e5115-191">Microsoft Edge と Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="e5115-191">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
