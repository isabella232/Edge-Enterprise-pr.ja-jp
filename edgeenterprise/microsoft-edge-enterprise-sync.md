---
title: Microsoft Edge エンタープライズの同期
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 08/03/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge エンタープライズの同期
ms.openlocfilehash: a6d01356db478871a7c6b386bbb731b32dc4739a
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980507"
---
# <span data-ttu-id="1f8cf-103">Microsoft Edge エンタープライズの同期</span><span class="sxs-lookup"><span data-stu-id="1f8cf-103">Microsoft Edge Enterprise Sync</span></span>

<span data-ttu-id="1f8cf-104">この記事では、Microsoft Edge を使用して、サインインしているすべてのデバイスでお気に入り、パスワード、その他のブラウザー データを同期する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-104">This article explains how to use Microsoft Edge to sync your favorites, passwords, and other browser data across all your signed-in devices.</span></span>

> [!NOTE]
> <span data-ttu-id="1f8cf-105">この記事は Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="1f8cf-106">概要</span><span class="sxs-lookup"><span data-stu-id="1f8cf-106">Overview</span></span>

<span data-ttu-id="1f8cf-107">Microsoft Edge の同期を使用すると、ユーザーは、サインインしているすべてのデバイスで閲覧データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-107">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="1f8cf-108">同期でサポートされるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-108">The data supported by sync includes:</span></span>

- <span data-ttu-id="1f8cf-109">お気に入り</span><span class="sxs-lookup"><span data-stu-id="1f8cf-109">Favorites</span></span>
- <span data-ttu-id="1f8cf-110">パスワード</span><span class="sxs-lookup"><span data-stu-id="1f8cf-110">Passwords</span></span>
- <span data-ttu-id="1f8cf-111">住所など (フォームの入力情報)</span><span class="sxs-lookup"><span data-stu-id="1f8cf-111">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="1f8cf-112">コレクション</span><span class="sxs-lookup"><span data-stu-id="1f8cf-112">Collections</span></span>
- <span data-ttu-id="1f8cf-113">設定</span><span class="sxs-lookup"><span data-stu-id="1f8cf-113">Settings</span></span>

<span data-ttu-id="1f8cf-114">同期機能はユーザーの同意によって有効になり、ユーザーは上記の各データ タイプについて同期をオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-114">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span>

> [!NOTE]
> <span data-ttu-id="1f8cf-115">同期機能をサポートするために、デバイスの接続および構成データ (デバイス名、製造元、モデルなど) がアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-115">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <span data-ttu-id="1f8cf-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="1f8cf-116">Prerequisites</span></span>

<span data-ttu-id="1f8cf-117">現時点では、Azure Active Directory (Azure AD) アカウントでの Microsoft Edge の同期は、次のサブスクリプションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-117">Currently Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for the following subscriptions:</span></span>

- <span data-ttu-id="1f8cf-118">Azure AD Premium (P1 および P2)</span><span class="sxs-lookup"><span data-stu-id="1f8cf-118">Azure AD Premium (P1 and P2)</span></span>
- <span data-ttu-id="1f8cf-119">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="1f8cf-119">M365 Business Premium</span></span>
- <span data-ttu-id="1f8cf-120">Office 365 E3 以上</span><span class="sxs-lookup"><span data-stu-id="1f8cf-120">Office 365 E3 and above</span></span>
- <span data-ttu-id="1f8cf-121">Azure Information Protection (AIP) (P1& P2)</span><span class="sxs-lookup"><span data-stu-id="1f8cf-121">Azure Information Protection (AIP) (P1& P2)</span></span>
- <span data-ttu-id="1f8cf-122">すべての EDU サブスクリプション (O365 A1 以上、M365 A1 以上、学生または教職員向けの Azure Information Protection P1 または P2)</span><span class="sxs-lookup"><span data-stu-id="1f8cf-122">All EDU subscriptions (O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

> [!NOTE]
> <span data-ttu-id="1f8cf-123">同期は、同期データを保護するために Azure Information Protection (AIP) によって提供される保護サービスに依存しています。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-123">Sync has a dependency on the protection service offered by Azure Information Protection (AIP) to protect sync data.</span></span> <span data-ttu-id="1f8cf-124">このサービスは、現在、前述のサブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-124">This service is currently available to the preceding subscriptions.</span></span> <span data-ttu-id="1f8cf-125">AIP で SKU の完全な一覧を表示するには、[Information Protection の価格に関するトピック](https://azure.microsoft.com/pricing/details/information-protection/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-125">To see the full list of SKUs with AIP, see [Information Protection Pricing](https://azure.microsoft.com/pricing/details/information-protection/).</span></span>

## <span data-ttu-id="1f8cf-126">Microsoft Edge の同期の構成オプション</span><span class="sxs-lookup"><span data-stu-id="1f8cf-126">Configuration options for Microsoft Edge sync</span></span>

<span data-ttu-id="1f8cf-127">Microsoft Edge の同期を有効にするには、次の構成オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-127">The following configuration options are available for enabling Microsoft Edge sync:</span></span>

- <span data-ttu-id="1f8cf-128">Azure Information Protection (AIP)</span><span class="sxs-lookup"><span data-stu-id="1f8cf-128">Azure Information Protection (AIP)</span></span>
- <span data-ttu-id="1f8cf-129">Azure AD Enterprise State Roaming (ESR)</span><span class="sxs-lookup"><span data-stu-id="1f8cf-129">Azure AD Enterprise State Roaming (ESR)</span></span>

<span data-ttu-id="1f8cf-130">AIP と ESR の両方が無効になっている場合、ユーザーのアカウントで同期が利用できないことを示すエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-130">If both AIP and ESR are disabled, users will see an error message indicating that sync is not available for their account.</span></span>

### <span data-ttu-id="1f8cf-131">Azure Information Protection (AIP)</span><span class="sxs-lookup"><span data-stu-id="1f8cf-131">Azure Information Protection (AIP)</span></span>

<span data-ttu-id="1f8cf-132">テナントの Azure Information Protection (AIP) サービスが有効になっている場合、ライセンスに関係なく、すべてのユーザーが Microsoft Edge データを同期できます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-132">If the Azure Information Protection (AIP) service is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="1f8cf-133">AIP を有効にする方法は、[ここ](https://docs.microsoft.com/azure/information-protection/activate-office365)で説明されています。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-133">Instructions on how to enable AIP can be found [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="1f8cf-134">特定のユーザー セットに対して同期を制限するために、これらのユーザーに対して [AADRM のオンボード制御ポリシー](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps)を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-134">To restrict sync to certain set of users, you can enable the [AADRM onboarding control policy](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) for those users.</span></span> <span data-ttu-id="1f8cf-135">必要なユーザーがすべてオンボードされた後でも同期ができない場合には、[Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/Get-AipServiceIPCv3?view=azureipps) PowerShell コマンドレット を使用して IPCv3Service が有効になっていることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-135">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/Get-AipServiceIPCv3?view=azureipps) PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="1f8cf-136">Azure Information Protection を有効にすると、Microsoft Word や Microsoft Outlook など、AIP を使用する他のアプリケーションのアクセスも制限されます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-136">Activating Azure Information Protection will also restrict access for other applications using AIP, such as Microsoft Word or Microsoft Outlook.</span></span>

### <span data-ttu-id="1f8cf-137">Azure AD Enterprise State Roaming (ESR)</span><span class="sxs-lookup"><span data-stu-id="1f8cf-137">Azure AD Enterprise State Roaming (ESR)</span></span>

<span data-ttu-id="1f8cf-138">任意のユーザーまたはテナントについて、Azure Active Directory [Enterprise State Roaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) (ESR) 機能が有効になっている場合、オンボード制御ポリシー設定に関係なく、Microsoft Edge の同期機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-138">If the Azure Active Directory [Enterprise State Roaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) (ESR) feature is enabled for any user or tenant, they can use the Microsoft Edge sync feature regardless of the onboarding control policy setting.</span></span>

## <span data-ttu-id="1f8cf-139">Microsoft Edge と Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="1f8cf-139">Microsoft Edge and Enterprise State Roaming</span></span>

<span data-ttu-id="1f8cf-140">新しい Microsoft Edge は、ユーザー データの同期の範囲をすべてのデバイスに拡張したクロスプラットフォーム アプリケーションであり、Azure AD Enterprise State Roaming の一部ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-140">The new Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="1f8cf-141">ただし、新しい Microsoft Edge では、独自のキーを取り込む機能など、ESR のデータ保護の約束を満たしています。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-141">However, the new Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="1f8cf-142">詳細については、「[Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-142">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <span data-ttu-id="1f8cf-143">同期グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="1f8cf-143">Sync group policies</span></span>

<span data-ttu-id="1f8cf-144">次のグループ ポリシーは、Microsoft Edge の同期に影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-144">The following group policies impact Microsoft Edge sync:</span></span>

- <span data-ttu-id="1f8cf-145">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): 同期を完全に無効にします。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-145">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="1f8cf-146">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): 閲覧の履歴の保存と同期を無効にします。このポリシーにより、開いているタブの同期も無効になります。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-146">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="1f8cf-147">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): 同期から除外される種類の一覧を構成します。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-147">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>

## <span data-ttu-id="1f8cf-148">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="1f8cf-148">Frequently Asked Questions</span></span>

### <span data-ttu-id="1f8cf-149">セキュリティとサーバー/データのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="1f8cf-149">SECURITY and SERVER/DATA COMPLIANCE</span></span>

#### <span data-ttu-id="1f8cf-150">同期したデータは暗号化されていますか?</span><span class="sxs-lookup"><span data-stu-id="1f8cf-150">Is the synced data encrypted?</span></span> 

<span data-ttu-id="1f8cf-151">転送中のデータは TLS 1.2 以降を使用して暗号化され、Microsoft のサービスでの保存時にはさらに AES256 を使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-151">The data is encrypted in transport using TLS 1.2 or greater, and additionally at rest in Microsoft's service using AES256.</span></span>

#### <span data-ttu-id="1f8cf-152">Microsoft Edge の同期データはどこに保存されますか?</span><span class="sxs-lookup"><span data-stu-id="1f8cf-152">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="1f8cf-153">Azure AD アカウントの同期されたデータは、テナント ID に従って、セキュリティで保護されたサーバーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-153">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="1f8cf-154">たとえば、米国に登録されているテナントのデータは地理的にその地域にあるサーバーに保存され、Office アプリケーションで使用されるストレージ ソリューションと同じソリューションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-154">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

#### <span data-ttu-id="1f8cf-155">Microsoft Edge との同期以外に、データが Microsoft のクラウドから移動することはありますか?</span><span class="sxs-lookup"><span data-stu-id="1f8cf-155">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="1f8cf-156">いいえ、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-156">No.</span></span>

#### <span data-ttu-id="1f8cf-157">テナント管理者が独自のキーを使用することはできますか?</span><span class="sxs-lookup"><span data-stu-id="1f8cf-157">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="1f8cf-158">はい、[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) から使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-158">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

#### <span data-ttu-id="1f8cf-159">エンタープライズ向けの同期には、どのサービス使用条件が適用されますか?</span><span class="sxs-lookup"><span data-stu-id="1f8cf-159">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="1f8cf-160">サービス使用条件は、ご利用の Azure AD サブスクリプションの条件と同じです。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-160">The terms of service are the same terms as your Azure AD subscription.</span></span> <span data-ttu-id="1f8cf-161">すべての Azure AD のサービス使用条件には、最終的には Microsoft の[オンライン サービス条件](https://www.microsoft.com/licensing/product-licensing/products)が適用されます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-161">All the Azure AD terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

#### <span data-ttu-id="1f8cf-162">Microsoft Edge は、Government Community Cloud (GCC) High のコンプライアンスをサポートしていますか?</span><span class="sxs-lookup"><span data-stu-id="1f8cf-162">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="1f8cf-163">現時点ではサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-163">Not today.</span></span> <span data-ttu-id="1f8cf-164">GCC High は Tier D ですが、Microsoft Edge は Tier C までをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-164">GCC High is Tier D, while Microsoft Edge supports up to Tier C.</span></span>

### <span data-ttu-id="1f8cf-165">同期の適用</span><span class="sxs-lookup"><span data-stu-id="1f8cf-165">APPLYING SYNC</span></span>

#### <span data-ttu-id="1f8cf-166">企業や教育機関のお客様が、従来の Microsoft Edge を引き続き使用することを決定した場合、どうなりますか。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-166">What happens with enterprise and educational customers who decide to stay with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="1f8cf-167">現在のバージョンの Microsoft Edge ブラウザーは、引き続き ESR サービスの対象に含まれます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-167">The current version of Microsoft Edge browser will continue to participate in the ESR offering.</span></span>

#### <span data-ttu-id="1f8cf-168">同期するには Azure AD Premium サブスクリプションが必要なのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="1f8cf-168">Why do I need a premium Azure AD subscription to sync?</span></span>

<span data-ttu-id="1f8cf-169">エンタープライズ向け同期は Azure Information Protection に依存していますが、これは Azure AD のすべての階層で利用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-169">Enterprise sync depends on Azure Information Protection, which is not available in all Azure AD tiers.</span></span>

#### <span data-ttu-id="1f8cf-170">Microsoft Edge の同期は Enterprise State Roaming に依存していますか?</span><span class="sxs-lookup"><span data-stu-id="1f8cf-170">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="1f8cf-171">いいえ、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-171">No.</span></span> <span data-ttu-id="1f8cf-172">ESR を使用して同期を有効にすることはできますが、Microsoft Edge の同期は ESR の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-172">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="1f8cf-173">詳細については、「[Microsoft Edge の同期](microsoft-edge-enterprise-sync.md)」と「[Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-173">For more information, see [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md) and [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

#### <span data-ttu-id="1f8cf-174">Microsoft Edge では、将来 Microsoft Edge と IE との同期はサポートされますか?</span><span class="sxs-lookup"><span data-stu-id="1f8cf-174">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="1f8cf-175">その同期をサポートする計画はありません。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-175">There are no plans to support this syncing.</span></span> <span data-ttu-id="1f8cf-176">ご自分の環境で従来のアプリをサポートするために IE を使用する必要がある場合、[新しい IE モード](https://docs.microsoft.com/deployedge/edge-ie-mode)を検討してください。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-176">If you still need IE in your environment to support legacy apps, consider our [new IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>

#### <span data-ttu-id="1f8cf-177">新しい Microsoft Edge ブラウザーは、Microsoft Edge 従来版と同期しますか?</span><span class="sxs-lookup"><span data-stu-id="1f8cf-177">Will the new Microsoft Edge browser sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="1f8cf-178">いいえ、同期されません。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-178">No, it won't.</span></span> <span data-ttu-id="1f8cf-179">この 2 つのエコシステムを接続すると、新しい Microsoft Edge での同期の信頼性が低下します。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-179">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the new Microsoft Edge.</span></span> <span data-ttu-id="1f8cf-180">既存のデータが新しい Microsoft Edge に移行されるようにします。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-180">We will ensure that existing data is migrated to the new Microsoft Edge.</span></span> <span data-ttu-id="1f8cf-181">ユーザーは、選択したブラウザーからデータをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-181">Users will also be able to import data from browser of their choice.</span></span> <span data-ttu-id="1f8cf-182">これは、新しい Microsoft Edge ブラウザーが IE と同期する方法を備えていないことも意味します。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-182">This also means that new Microsoft Edge browser won't have a way to sync with IE.</span></span>

### <span data-ttu-id="1f8cf-183">同期の管理</span><span class="sxs-lookup"><span data-stu-id="1f8cf-183">MANAGING SYNC</span></span>

#### <span data-ttu-id="1f8cf-184">ユーザーに個人用テナントと同期させないようにすることはできますか?</span><span class="sxs-lookup"><span data-stu-id="1f8cf-184">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="1f8cf-185">直接はできませんが、[RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) ポリシーを使用して、Microsoft Edge にサインオンできるプロファイルを定義することはできます。</span><span class="sxs-lookup"><span data-stu-id="1f8cf-185">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

## <span data-ttu-id="1f8cf-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f8cf-186">See also</span></span>

- [<span data-ttu-id="1f8cf-187">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="1f8cf-187">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="1f8cf-188">Microsoft Edge と Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="1f8cf-188">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
