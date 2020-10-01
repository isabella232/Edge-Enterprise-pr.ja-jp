---
title: Microsoft Edge エンタープライズの同期
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 09/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge エンタープライズの同期
ms.openlocfilehash: d5868fb496c036d750925bb5ae6dfa3de0293fd2
ms.sourcegitcommit: 8a4479a1b034c3c13ea03ee3a2374a1af332cb38
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "11091949"
---
# <span data-ttu-id="9d1b2-103">Microsoft Edge エンタープライズの同期</span><span class="sxs-lookup"><span data-stu-id="9d1b2-103">Microsoft Edge Enterprise Sync</span></span>

<span data-ttu-id="9d1b2-104">この記事では、Microsoft Edge を使用して、サインインしているすべてのデバイスでお気に入り、パスワード、その他のブラウザー データを同期する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-104">This article explains how to use Microsoft Edge to sync your favorites, passwords, and other browser data across all your signed-in devices.</span></span>

> [!NOTE]
> <span data-ttu-id="9d1b2-105">この記事は Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="9d1b2-106">概要</span><span class="sxs-lookup"><span data-stu-id="9d1b2-106">Overview</span></span>

<span data-ttu-id="9d1b2-107">Microsoft Edge の同期を使用すると、ユーザーは、サインインしているすべてのデバイスで閲覧データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-107">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="9d1b2-108">同期でサポートされるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-108">The data supported by sync includes:</span></span>

- <span data-ttu-id="9d1b2-109">お気に入り</span><span class="sxs-lookup"><span data-stu-id="9d1b2-109">Favorites</span></span>
- <span data-ttu-id="9d1b2-110">パスワード</span><span class="sxs-lookup"><span data-stu-id="9d1b2-110">Passwords</span></span>
- <span data-ttu-id="9d1b2-111">住所など (フォームの入力情報)</span><span class="sxs-lookup"><span data-stu-id="9d1b2-111">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="9d1b2-112">コレクション</span><span class="sxs-lookup"><span data-stu-id="9d1b2-112">Collections</span></span>
- <span data-ttu-id="9d1b2-113">設定</span><span class="sxs-lookup"><span data-stu-id="9d1b2-113">Settings</span></span>

<span data-ttu-id="9d1b2-114">同期機能はユーザーの同意によって有効になり、ユーザーは上記の各データ タイプについて同期をオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-114">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span>

> [!NOTE]
> <span data-ttu-id="9d1b2-115">同期機能をサポートするために、デバイスの接続および構成データ (デバイス名、製造元、モデルなど) がアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-115">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <span data-ttu-id="9d1b2-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="9d1b2-116">Prerequisites</span></span>

<span data-ttu-id="9d1b2-117">Azure Active Directory (Azure AD) アカウントでの Microsoft Edge の同期は、次のサブスクリプションのいずれかで使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-117">Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for any of the following subscriptions:</span></span>

- <span data-ttu-id="9d1b2-118">Azure AD Premium (P1 および P2)</span><span class="sxs-lookup"><span data-stu-id="9d1b2-118">Azure AD Premium (P1 and P2)</span></span>
- <span data-ttu-id="9d1b2-119">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="9d1b2-119">M365 Business Premium</span></span>
- <span data-ttu-id="9d1b2-120">Office 365 E3 以上</span><span class="sxs-lookup"><span data-stu-id="9d1b2-120">Office 365 E3 and above</span></span>
- <span data-ttu-id="9d1b2-121">Azure Information Protection (AIP) (P1& P2)</span><span class="sxs-lookup"><span data-stu-id="9d1b2-121">Azure Information Protection (AIP) (P1& P2)</span></span>
- <span data-ttu-id="9d1b2-122">すべての EDU サブスクリプション (学生または教職員向けの Microsoft Apps、学生または教職員向けの Exchange Online、O365 A1 以上、M365 A1 以上、学生または教職員向けの Azure Information Protection P1 または P2)</span><span class="sxs-lookup"><span data-stu-id="9d1b2-122">All EDU subscriptions (Microsoft Apps for Students or Faculty, Exchange Online for Students or Faculty, O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

## <span data-ttu-id="9d1b2-123">Microsoft Edge の同期の構成</span><span class="sxs-lookup"><span data-stu-id="9d1b2-123">Configuring Microsoft Edge sync</span></span>

<span data-ttu-id="9d1b2-124">Microsoft Edge の同期の構成オプションは、Azure Information Protection (AIP) サービスを介して利用できます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-124">Configuration options for Microsoft Edge sync are available through the Azure Information Protection (AIP) service.</span></span> <span data-ttu-id="9d1b2-125">テナントの AIP が有効になっている場合、ライセンスに関係なくすべてのユーザーが Microsoft Edge のデータを同期できます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-125">When AIP is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="9d1b2-126">AIP を有効にする方法は、[ここ](https://docs.microsoft.com/azure/information-protection/activate-office365)で説明されています。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-126">Instructions on how to enable AIP can be found [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="9d1b2-127">特定のユーザー セットに対して同期を制限するために、これらのユーザーに対して [AIP のオンボード制御ポリシー](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps) を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-127">To restrict sync to certain set of users, you can enable the [AIP onboarding control policy](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps) for those users.</span></span> <span data-ttu-id="9d1b2-128">必要なユーザーがすべてオンボードされた後でも同期ができない場合には、[Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps) PowerShell コマンドレット を使用して IPCv3Service が有効になっていることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-128">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps)  PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="9d1b2-129">Azure Information Protection を有効にすると、AIP を使用してコンテンツを保護するために Microsoft Word や Microsoft Outlook などの他のアプリケーションも許可されます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-129">Activating Azure Information Protection will also allow other applications, such as Microsoft Word or Microsoft Outlook, to protect content with AIP.</span></span> <span data-ttu-id="9d1b2-130">また、エッジ同期を制限するために使用されるオンボード制御ポリシーは、他のアプリケーションが AIP を使用してコンテンツを保護することも制限します。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-130">In addition, any onboarding control policy used to restrict Edge sync will also restrict other applications from protecting content using AIP.</span></span>

## <span data-ttu-id="9d1b2-131">Microsoft Edge と Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="9d1b2-131">Microsoft Edge and Enterprise State Roaming</span></span>

<span data-ttu-id="9d1b2-132">新しい Microsoft Edge は、ユーザー データの同期の範囲をすべてのデバイスに拡張したクロスプラットフォーム アプリケーションであり、Azure AD Enterprise State Roaming の一部ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-132">The new Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="9d1b2-133">ただし、新しい Microsoft Edge では、独自のキーを取り込む機能など、ESR のデータ保護の約束を満たしています。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-133">However, the new Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="9d1b2-134">詳細については、「[Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-134">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <span data-ttu-id="9d1b2-135">同期グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="9d1b2-135">Sync group policies</span></span>

<span data-ttu-id="9d1b2-136">次のグループ ポリシーは、Microsoft Edge の同期に影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-136">The following group policies impact Microsoft Edge sync:</span></span>

- <span data-ttu-id="9d1b2-137">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): 同期を完全に無効にします。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-137">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="9d1b2-138">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): 閲覧の履歴の保存と同期を無効にします。このポリシーにより、開いているタブの同期も無効になります。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-138">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="9d1b2-139">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): 同期から除外される種類の一覧を構成します。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-139">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>
- <span data-ttu-id="9d1b2-140">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Active Directory (AD) プロファイルがオンプレミスの記憶域を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-140">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Allow Active Directory (AD) profiles to use on-premises storage.</span></span> <span data-ttu-id="9d1b2-141">詳細については、「[Active Directory (AD) ユーザー用のオンプレミス同期](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-141">For more information, see [On-premises sync for Active Directory (AD) users](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).</span></span>
- <span data-ttu-id="9d1b2-142">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): 既定で同期をオンにします。同期にはユーザーの同意を必要としません。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-142">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): Turn sync on by default and do not require user consent to sync.</span></span>  

## <span data-ttu-id="9d1b2-143">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="9d1b2-143">Frequently Asked Questions</span></span>

### <span data-ttu-id="9d1b2-144">セキュリティとサーバー/データのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="9d1b2-144">SECURITY and SERVER/DATA COMPLIANCE</span></span>

#### <span data-ttu-id="9d1b2-145">同期したデータは暗号化されていますか?</span><span class="sxs-lookup"><span data-stu-id="9d1b2-145">Is the synced data encrypted?</span></span> 

<span data-ttu-id="9d1b2-146">データは TLS 1.2 以上を使用してトランスポートで暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-146">The data is encrypted in transport using TLS 1.2 or greater.</span></span> <span data-ttu-id="9d1b2-147">ほとんどのデータ型は、さらに AES256 を使用する Microsoft のサービスで保存時に暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-147">Most data types are additionally encrypted at rest in Microsoft's service using AES256.</span></span> 

#### <span data-ttu-id="9d1b2-148">Microsoft Edge の同期データはどこに保存されますか?</span><span class="sxs-lookup"><span data-stu-id="9d1b2-148">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="9d1b2-149">Azure AD アカウントの同期されたデータは、テナント ID に従って、セキュリティで保護されたサーバーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-149">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="9d1b2-150">たとえば、米国に登録されているテナントのデータは地理的にその地域にあるサーバーに保存され、Office アプリケーションで使用されるストレージ ソリューションと同じソリューションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-150">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

#### <span data-ttu-id="9d1b2-151">Microsoft Edge との同期以外に、データが Microsoft のクラウドから移動することはありますか?</span><span class="sxs-lookup"><span data-stu-id="9d1b2-151">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="9d1b2-152">いいえ、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-152">No.</span></span>

#### <span data-ttu-id="9d1b2-153">テナント管理者が独自のキーを使用することはできますか?</span><span class="sxs-lookup"><span data-stu-id="9d1b2-153">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="9d1b2-154">はい、[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) から使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-154">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

#### <span data-ttu-id="9d1b2-155">エンタープライズ向けの同期には、どのサービス使用条件が適用されますか?</span><span class="sxs-lookup"><span data-stu-id="9d1b2-155">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="9d1b2-156">サービス使用条件は、ご利用の Azure AD サブスクリプションの条件と同じです。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-156">The terms of service are the same terms as your Azure AD subscription.</span></span> <span data-ttu-id="9d1b2-157">すべての Azure AD のサービス使用条件には、最終的には Microsoft の[オンライン サービス条件](https://www.microsoft.com/licensing/product-licensing/products)が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-157">All the Azure AD terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

#### <span data-ttu-id="9d1b2-158">Microsoft Edge は、Government Community Cloud (GCC) High のコンプライアンスをサポートしていますか?</span><span class="sxs-lookup"><span data-stu-id="9d1b2-158">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="9d1b2-159">現時点ではサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-159">Not today.</span></span> <span data-ttu-id="9d1b2-160">GCC High は Tier D ですが、Microsoft Edge は Tier C までをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-160">GCC High is Tier D, while Microsoft Edge supports up to Tier C.</span></span>

### <span data-ttu-id="9d1b2-161">同期の適用</span><span class="sxs-lookup"><span data-stu-id="9d1b2-161">APPLYING SYNC</span></span>

#### <span data-ttu-id="9d1b2-162">企業や教育機関のお客様が、従来の Microsoft Edge を引き続き使用することを決定した場合、どうなりますか。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-162">What happens with enterprise and educational customers who decide to stay with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="9d1b2-163">現在のバージョンの Microsoft Edge ブラウザーは、引き続き ESR サービスの対象に含まれます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-163">The current version of Microsoft Edge browser will continue to participate in the ESR offering.</span></span>

#### <span data-ttu-id="9d1b2-164">同期するには Azure AD Premium サブスクリプションが必要なのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="9d1b2-164">Why do I need a premium Azure AD subscription to sync?</span></span>

<span data-ttu-id="9d1b2-165">エンタープライズ向け同期は Azure Information Protection に依存していますが、これは Azure AD のすべての階層で利用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-165">Enterprise sync depends on Azure Information Protection, which is not available in all Azure AD tiers.</span></span>

#### <span data-ttu-id="9d1b2-166">Microsoft Edge の同期は Enterprise State Roaming に依存していますか?</span><span class="sxs-lookup"><span data-stu-id="9d1b2-166">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="9d1b2-167">いいえ、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-167">No.</span></span> <span data-ttu-id="9d1b2-168">ESR を使用して同期を有効にすることはできますが、Microsoft Edge の同期は ESR の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-168">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="9d1b2-169">詳細については、「[Microsoft Edge の同期](microsoft-edge-enterprise-sync.md)」と「[Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-169">For more information, see [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md) and [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

#### <span data-ttu-id="9d1b2-170">Microsoft Edge では、将来 Microsoft Edge と IE との同期はサポートされますか?</span><span class="sxs-lookup"><span data-stu-id="9d1b2-170">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="9d1b2-171">その同期をサポートする計画はありません。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-171">There are no plans to support this syncing.</span></span> <span data-ttu-id="9d1b2-172">ご自分の環境で従来のアプリをサポートするために IE を使用する必要がある場合、[新しい IE モード](https://docs.microsoft.com/deployedge/edge-ie-mode)を検討してください。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-172">If you still need IE in your environment to support legacy apps, consider our [new IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>

#### <span data-ttu-id="9d1b2-173">新しい Microsoft Edge ブラウザーは、Microsoft Edge 従来版と同期しますか?</span><span class="sxs-lookup"><span data-stu-id="9d1b2-173">Will the new Microsoft Edge browser sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="9d1b2-174">いいえ、同期されません。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-174">No, it won't.</span></span> <span data-ttu-id="9d1b2-175">この 2 つのエコシステムを接続すると、新しい Microsoft Edge での同期の信頼性が低下します。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-175">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the new Microsoft Edge.</span></span> <span data-ttu-id="9d1b2-176">既存のデータが新しい Microsoft Edge に移行されるようにします。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-176">We will ensure that existing data is migrated to the new Microsoft Edge.</span></span> <span data-ttu-id="9d1b2-177">ユーザーは、選択したブラウザーからデータをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-177">Users will also be able to import data from browser of their choice.</span></span> <span data-ttu-id="9d1b2-178">これは、新しい Microsoft Edge ブラウザーが IE と同期する方法を備えていないことも意味します。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-178">This also means that new Microsoft Edge browser won't have a way to sync with IE.</span></span>

### <span data-ttu-id="9d1b2-179">同期の管理</span><span class="sxs-lookup"><span data-stu-id="9d1b2-179">MANAGING SYNC</span></span>

#### <span data-ttu-id="9d1b2-180">ユーザーに個人用テナントと同期させないようにすることはできますか?</span><span class="sxs-lookup"><span data-stu-id="9d1b2-180">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="9d1b2-181">直接はできませんが、[RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) ポリシーを使用して、Microsoft Edge にサインオンできるプロファイルを定義することはできます。</span><span class="sxs-lookup"><span data-stu-id="9d1b2-181">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

## <span data-ttu-id="9d1b2-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d1b2-182">See also</span></span>

- [<span data-ttu-id="9d1b2-183">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="9d1b2-183">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="9d1b2-184">Microsoft Edge と Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="9d1b2-184">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
