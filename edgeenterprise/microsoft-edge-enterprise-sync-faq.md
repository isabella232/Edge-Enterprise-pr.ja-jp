---
title: Microsoft Edge のエンタープライズ向けの同期に関するよく寄せられる質問 (FAQ)
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge のエンタープライズ向けの同期に関してよく寄せられる質問。
ms.openlocfilehash: 4bb41c8d7ded64fcc0b4fd4843ef2b7ec0adec23
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617767"
---
# <a name="microsoft-edge-enterprise-sync-faq"></a><span data-ttu-id="6f08a-103">Microsoft Edge のエンタープライズ向けの同期に関するよく寄せられる質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="6f08a-103">Microsoft Edge enterprise sync FAQ</span></span>

<span data-ttu-id="6f08a-104">この記事では、Microsoft Edge バージョン 77 以降のエンタープライズ向けの同期に関するよく寄せられる質問に回答します。</span><span class="sxs-lookup"><span data-stu-id="6f08a-104">This article answers frequently asked questions about enterprise sync for Microsoft Edge version 77 or later.</span></span>

## <a name="security-and-serverdata-compliance"></a><span data-ttu-id="6f08a-105">セキュリティとサーバー/データのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="6f08a-105">Security and Server/Data Compliance</span></span>

### <a name="is-the-synced-data-encrypted"></a><span data-ttu-id="6f08a-106">同期したデータは暗号化されていますか?</span><span class="sxs-lookup"><span data-stu-id="6f08a-106">Is the synced data encrypted?</span></span>

<span data-ttu-id="6f08a-107">データは TLS 1.2 以上を使用してトランスポートで暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="6f08a-107">The data is encrypted in transport using TLS 1.2 or greater.</span></span> <span data-ttu-id="6f08a-108">すべてのデータ型は、AES128 を使用して Microsoft のサービスで保存中にさらに暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="6f08a-108">All data types are additionally encrypted at rest in Microsoft's service using AES128.</span></span> <span data-ttu-id="6f08a-109">オープン タブと履歴の同期に使用されるデータ型を除くすべてのデータ型は、[Azure Information Protection](./microsoft-edge-policies.md#restrictsignintopattern)ポリシーで管理されているキーを使ってユーザーのデバイスを離れる前に、さらに暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="6f08a-109">All data types except those used for open tab and history sync are additionally encrypted before leaving the user’s device with keys managed via the [Azure Information Protection](./microsoft-edge-policies.md#restrictsignintopattern) policy.</span></span>

### <a name="why-dont-open-tab-and-history-data-have-more-client-side-encryption"></a><span data-ttu-id="6f08a-110">オープンタブと履歴データにクライアント側の暗号化を追加しない理由はなぜでしょうか?</span><span class="sxs-lookup"><span data-stu-id="6f08a-110">Why don’t open tab and history data have more client-side encryption?</span></span>

<span data-ttu-id="6f08a-111">エンド ユーザー のデバイスでのリソース使用率を削減するために、オープン タブ ローミング データに基づいてサーバー側で履歴データが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6f08a-111">To reduce resource utilization on end-user devices, history data is generated server-side based on open tab roaming data.</span></span> <span data-ttu-id="6f08a-112">このプロセスは、このデータのクライアント側の暗号化では実行できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6f08a-112">This process would not be possible with client-side encryption of this data.</span></span> <span data-ttu-id="6f08a-113">オープン タブと履歴の同期を無効にするには [SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled) または [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="6f08a-113">To disable open tab and history sync, apply the [SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled) or [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) policies.</span></span>

### <a name="can-tenant-admins-bring-their-own-key"></a><span data-ttu-id="6f08a-114">テナント管理者が独自のキーを使用することはできますか?</span><span class="sxs-lookup"><span data-stu-id="6f08a-114">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="6f08a-115">はい [、Azure Information Protection を経由して可能です](https://azure.microsoft.com/services/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="6f08a-115">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

### <a name="where-is-microsoft-edge-sync-data-stored"></a><span data-ttu-id="6f08a-116">Microsoft Edge の同期データはどこに保存されますか?</span><span class="sxs-lookup"><span data-stu-id="6f08a-116">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="6f08a-117">Azure AD アカウントの同期されたデータは、テナント ID に従って、セキュリティで保護されたサーバーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="6f08a-117">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="6f08a-118">たとえば、米国に登録されているテナントのデータは地理的にその地域にあるサーバーに保存され、Office アプリケーションで使用されるストレージ ソリューションと同じソリューションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6f08a-118">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

### <a name="does-the-data-ever-leave-microsofts-cloud-aside-from-syncing-to-microsoft-edge"></a><span data-ttu-id="6f08a-119">Microsoft Edge との同期以外に、データが Microsoft のクラウドから移動することはありますか?</span><span class="sxs-lookup"><span data-stu-id="6f08a-119">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="6f08a-120">いいえ、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="6f08a-120">No.</span></span>

### <a name="what-terms-of-service-does-enterprise-sync-fall-under"></a><span data-ttu-id="6f08a-121">エンタープライズ向けの同期には、どのサービス使用条件が適用されますか?</span><span class="sxs-lookup"><span data-stu-id="6f08a-121">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="6f08a-122">Microsoft Edge 同期のサービス条件は、Microsoft ソフトウェア ライセンスに含まれており、 *edge://terms*の「Microsoft Edge」で確認が可能です。</span><span class="sxs-lookup"><span data-stu-id="6f08a-122">Terms of service for Microsoft Edge sync falls under the Microsoft software license viewable in Microsoft Edge at *edge://terms*.</span></span> <span data-ttu-id="6f08a-123">Azure ADサブスクリプションとサービス条件は、最終的には Microsoft の[オンライン サービス規約](https://www.microsoft.com/licensing/product-licensing/products)を適用します。 </span><span class="sxs-lookup"><span data-stu-id="6f08a-123">Your Azure AD subscription and terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

### <a name="does-microsoft-edge-support-government-community-cloud-gcc-high-compliance"></a><span data-ttu-id="6f08a-124">Microsoft Edge は、Government Community Cloud (GCC) の高コンプライアンスをサポートしていますか?</span><span class="sxs-lookup"><span data-stu-id="6f08a-124">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="6f08a-125">現時点ではサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6f08a-125">Not today.</span></span> <span data-ttu-id="6f08a-126">GCC High クラウドのユーザーの場合、Microsoft Edge の同期は無効になります。</span><span class="sxs-lookup"><span data-stu-id="6f08a-126">For customers in the GCC High cloud, Microsoft Edge sync is disabled.</span></span>

## <a name="applying-sync"></a><span data-ttu-id="6f08a-127">同期の適用</span><span class="sxs-lookup"><span data-stu-id="6f08a-127">Applying Sync</span></span>

### <a name="why-isnt-microsoft-edge-sync-supported-in-all-m365-subscriptions"></a><span data-ttu-id="6f08a-128">Microsoft Edge の同期がすべての M365 サブスクリプションでサポートされていないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="6f08a-128">Why isn’t Microsoft Edge sync supported in all M365 subscriptions?</span></span>

<span data-ttu-id="6f08a-129">エンタープライズ同期は、すべての M365 サブスクリプションで利用できない [Azure Information Protection](https://azure.microsoft.com/services/information-protection/) に依存しています。</span><span class="sxs-lookup"><span data-stu-id="6f08a-129">Enterprise sync depends on [Azure Information Protection](https://azure.microsoft.com/services/information-protection/), which is not available in all M365 subscriptions.</span></span>

### <a name="is-microsoft-edge-sync-based-on-enterprise-state-roaming"></a><span data-ttu-id="6f08a-130">Microsoft Edge の同期は Enterprise State Roaming に依存していますか?</span><span class="sxs-lookup"><span data-stu-id="6f08a-130">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="6f08a-131">いいえ、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="6f08a-131">No.</span></span> <span data-ttu-id="6f08a-132">ESR を使用して同期を有効にすることはできますが、Microsoft Edge の同期は ESR の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="6f08a-132">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="6f08a-133">詳細については、「[Microsoft Edge の同期](/DeployEdge/microsoft-edge-enterprise-sync)」と「[Microsoft Edge と Enterprise State Roaming](/DeployEdge/microsoft-edge-enterprise-state-roaming)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f08a-133">For more information, see [Microsoft Edge Sync](/DeployEdge/microsoft-edge-enterprise-sync) and [Microsoft Edge and Enterprise State Roaming](/DeployEdge/microsoft-edge-enterprise-state-roaming).</span></span>

### <a name="will-microsoft-edge-ever-support-syncing-between-microsoft-edge-and-ie"></a><span data-ttu-id="6f08a-134">Microsoft Edge では、将来 Microsoft Edge と IE との同期はサポートされますか?</span><span class="sxs-lookup"><span data-stu-id="6f08a-134">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="6f08a-135">その同期をサポートする計画はありません。</span><span class="sxs-lookup"><span data-stu-id="6f08a-135">There are no plans to support this syncing.</span></span> <span data-ttu-id="6f08a-136">ご自分の環境で従来のアプリをサポートするために IE を使用する必要がある場合、[新しい IE モード](./edge-ie-mode.md)を検討してください。</span><span class="sxs-lookup"><span data-stu-id="6f08a-136">If you still need IE in your environment to support legacy apps, consider our [new IE mode](./edge-ie-mode.md).</span></span>

### <a name="will-microsoft-edge-sync-with-microsoft-edge-legacy"></a><span data-ttu-id="6f08a-137">Microsoft Edge は Microsoft Edge レガシと同期しますか?</span><span class="sxs-lookup"><span data-stu-id="6f08a-137">Will Microsoft Edge sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="6f08a-138">いいえ、同期されません。</span><span class="sxs-lookup"><span data-stu-id="6f08a-138">No, it won't.</span></span> <span data-ttu-id="6f08a-139">これら 2 つのエコシステムを接続すると、Microsoft Edge の同期の信頼性が損なわれると考えています。</span><span class="sxs-lookup"><span data-stu-id="6f08a-139">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the Microsoft Edge.</span></span> <span data-ttu-id="6f08a-140">既存のデータが Microsoft Edge に移行されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f08a-140">We will ensure that existing data is migrated to the Microsoft Edge.</span></span> <span data-ttu-id="6f08a-141">ユーザーは選択したブラウザーからデータをインポートすることもできます。つまり、Microsoft Edge には IE と同期する方法が用意されていないということです。</span><span class="sxs-lookup"><span data-stu-id="6f08a-141">Users will also be able to import data from browser of their choice, which also means that Microsoft Edge won't have a way to sync with IE.</span></span>

## <a name="managing-sync"></a><span data-ttu-id="6f08a-142">同期の管理</span><span class="sxs-lookup"><span data-stu-id="6f08a-142">Managing Sync</span></span>

### <a name="is-it-possible-to-stop-my-users-from-syncing-with-a-personal-tenant"></a><span data-ttu-id="6f08a-143">ユーザーに個人用テナントと同期させないようにすることはできますか?</span><span class="sxs-lookup"><span data-stu-id="6f08a-143">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="6f08a-144">直接はできませんが、[RestrictSigninToPattern](./microsoft-edge-policies.md#restrictsignintopattern) ポリシーを使用して、Microsoft Edge にサインオンできるプロファイルを定義することはできます。</span><span class="sxs-lookup"><span data-stu-id="6f08a-144">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](./microsoft-edge-policies.md#restrictsignintopattern) policy.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f08a-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f08a-145">See also</span></span>

- [<span data-ttu-id="6f08a-146">Microsoft Edge エンタープライズの同期</span><span class="sxs-lookup"><span data-stu-id="6f08a-146">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="6f08a-147">Microsoft Edge と Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="6f08a-147">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="6f08a-148">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="6f08a-148">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)