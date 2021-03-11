---
title: Microsoft Edge の同期の問題を診断して修正する
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 管理者が一般的なエンタープライズ同期の問題のトラブルシューティングと修正に使用できるガイダンスとツール
ms.openlocfilehash: 767b26c74e91213b407e8264a8ed185f38dfc2e9
ms.sourcegitcommit: 86e0de9b27ad4297a6d5a57c866d7ef4fc7bb0cd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400199"
---
# <a name="diagnose-and-fix-microsoft-edge-sync-issues"></a><span data-ttu-id="8a805-103">Microsoft Edge の同期の問題を診断して修正する</span><span class="sxs-lookup"><span data-stu-id="8a805-103">Diagnose and fix Microsoft Edge sync issues</span></span>

<span data-ttu-id="8a805-104">この記事では、Azure Active Directory (Azure AD) 環境で最も一般的に発生する同期の問題のトラブルシューティング ガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="8a805-104">This article provides troubleshooting guidance for the most commonly encountered sync issues in an Azure Active Directory (Azure AD) environment.</span></span> <span data-ttu-id="8a805-105">また、同期の問題のトラブルシューティングに必要なログを収集するための推奨ツールも含まれています。</span><span class="sxs-lookup"><span data-stu-id="8a805-105">It also includes the recommended tools for gathering the logs needed for troubleshooting a sync issue.</span></span>

<span data-ttu-id="8a805-106">ユーザーがデバイス間でブラウザー データを同期する際に問題が発生した場合は、[同期のリセット](edge-learnmore-reset-data-in-cloud.md)を試すことができます。これが機能しない場合、管理者またはサポート スタッフは、次のガイダンスを使用して同期の問題を修正できます。</span><span class="sxs-lookup"><span data-stu-id="8a805-106">If a user is experiencing an issue syncing browser data across their devices they can try [resetting sync](edge-learnmore-reset-data-in-cloud.md). If this doesn't work, admins or support staff can use the following guidance to fix a sync issue.</span></span>

> [!NOTE]
> <span data-ttu-id="8a805-107">この記事は、特に指定されない限り、Microsoft Edge バージョン 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8a805-107">Applies to Microsoft Edge version 77 or later unless otherwise noted.</span></span>

## <a name="identity-issues-versus-sync-issues"></a><span data-ttu-id="8a805-108">ID の問題と同期の問題</span><span class="sxs-lookup"><span data-stu-id="8a805-108">Identity issues versus sync issues</span></span>

<span data-ttu-id="8a805-109">始める前に、ID の問題と同期の問題の違いを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="8a805-109">Before you begin it's important to understand the difference between identity issues and sync issues.</span></span> <span data-ttu-id="8a805-110">ブラウザーでユーザー ID を維持するための一般的な使用例は、同期をサポートすることです。このため、ID の問題は、多くの場合、同期の問題と混同されます。</span><span class="sxs-lookup"><span data-stu-id="8a805-110">A popular use case for maintaining user identity in the browser is to support sync. For this reason, identity issues are frequently confused with sync issues.</span></span> <span data-ttu-id="8a805-111">同期のトラブルシューティングを開始する前に、ID と同期の問題の違いを理解してください。</span><span class="sxs-lookup"><span data-stu-id="8a805-111">Understand the difference between identity and sync issue before you start troubleshooting sync.</span></span>

<span data-ttu-id="8a805-112">問題を同期の問題として扱う前に、ユーザーが有効なアカウントでブラウザーにサインインしているかどうか確認します。</span><span class="sxs-lookup"><span data-stu-id="8a805-112">Before you treat an issue as a sync issue, check to see if the user is signed into the browser with a valid account.</span></span>

<span data-ttu-id="8a805-113">次のスクリーンショットは、ID エラーの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="8a805-113">The next screenshot shows an example of an identity error.</span></span> <span data-ttu-id="8a805-114">エラーは**資格情報**の下にある*edge://sync-internals*にある "**ラスト トークン エラー、 EDGE_AUTH_ERROR: 3, 54, 3ea**"です。</span><span class="sxs-lookup"><span data-stu-id="8a805-114">The error is "**Last Token Error, EDGE_AUTH_ERROR: 3, 54, 3ea**", which is found in *edge://sync-internals* under **Credentials**:</span></span>

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-identity-issue.png" alt-text="ラスト トークン エラー EDGE_AUTH_ERROR: 3,54、3ea":::

## <a name="common-sync-issues"></a><span data-ttu-id="8a805-116">同期に関する一般的な問題</span><span class="sxs-lookup"><span data-stu-id="8a805-116">Common sync issues</span></span>

### <a name="issue-cant-access-m365-or-azure-information-protection-subscription"></a><span data-ttu-id="8a805-117">問題 : M365 または Azure Information Protection サブスクリプションにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="8a805-117">Issue: Can't access M365 or Azure Information Protection subscription</span></span>

<span data-ttu-id="8a805-118">以前 M365 または Azure Information Protection (AIP) サブスクリプションの期限が切れて、新しいサブスクリプションに置き換えたということはありませんか?</span><span class="sxs-lookup"><span data-stu-id="8a805-118">Do you have a previous M365 or Azure Information Protection (AIP) subscription that expired and then replaced with a new subscription?</span></span> <span data-ttu-id="8a805-119">その場合は、テナント ID が変更されているので、サービス データをリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a805-119">If so, then the tenant ID has changed and the service data needs to be reset.</span></span> <span data-ttu-id="8a805-120">**「Cryptographer (暗号作成者) エラーが発生した** 問題」で、データ リセットの手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8a805-120">See the instructions for resetting data in the **Cryptographer error encountered** issue.</span></span>

### <a name="issue-sync-is-not-available-for-this-account"></a><span data-ttu-id="8a805-121">問題 : "このアカウントでは同期できません。"</span><span class="sxs-lookup"><span data-stu-id="8a805-121">Issue: “Sync is not available for this account.”</span></span>

<span data-ttu-id="8a805-122">Azure Active Directory アカウントでこのエラーが発生した場合、または *edge://sync-internals*に DISABLED_BY_ADMIN が表示される場合は、問題が解決するまで、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8a805-122">If this error is encountered for an Azure Active Directory account, or if DISABLED_BY_ADMIN appears in *edge://sync-internals*, follow the steps in the next procedure sequentially until the problem is fixed.</span></span>

> [!NOTE]
> <span data-ttu-id="8a805-123">このエラーのソースは通常、Azure Active Directory テナントの構成変更を必要とするので、これらのトラブルシューティング手順はテナント管理者だけが実行できます。エンドユーザーは実行できません。</span><span class="sxs-lookup"><span data-stu-id="8a805-123">Because the source of this error is usually requires a configuration change in an Azure Active Directory tenant, these troubleshooting steps can only performed by a tenant admin and not by end users.</span></span>

1. <span data-ttu-id="8a805-124">エンタープライズ テナントにサポートされている M365 サブスクリプションがあるかどうか確認します。</span><span class="sxs-lookup"><span data-stu-id="8a805-124">Verify that the enterprise tenant has a supported M365 subscription.</span></span> <span data-ttu-id="8a805-125">利用可能なサブスクリプションの種類の最新の一覧は [ここに表示されています](https://docs.microsoft.com/azure/information-protection/activate-office365)。</span><span class="sxs-lookup"><span data-stu-id="8a805-125">The current list of available subscription types is [provided here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span> <span data-ttu-id="8a805-126">テナントにサポートされているサブスクリプションが存在しない場合は、Azure Information Protection を個別に購入するか、サポートされているサブスクリプションにアップグレードすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="8a805-126">If the tenant doesn't have a supported subscription, they can either purchase Azure Information Protection separately, or upgrade to one of the supported subscriptions.</span></span>
2. <span data-ttu-id="8a805-127">サポートされているサブスクリプションが利用可能な場合は、テナントが Azure Information Protection (AIP) を使用できる構成にしているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a805-127">If a supported subscription is available, verify that the tenant has Azure Information Protection (AIP) available.</span></span> <span data-ttu-id="8a805-128">AIP の状態を確認し、必要に応じて、AIP をアクティブ化するための手順については、 [ここ](https://docs.microsoft.com/azure/information-protection/activate-office365)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a805-128">The instructions for checking the AIP status and, if necessary, activating AIP are [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>
3. <span data-ttu-id="8a805-129">手順 2 で AIP がアクティブであるのに同期が機能しない場合は、Enterprise State Roaming (ESR) をオンにします。</span><span class="sxs-lookup"><span data-stu-id="8a805-129">If step 2 shows that AIP is active but sync still doesn't work, turn on Enterprise State Roaming (ESR).</span></span> <span data-ttu-id="8a805-130">ESR を有効にする手順は [ここ](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a805-130">The instructions for enabling ESR are [here](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span> <span data-ttu-id="8a805-131">ESR を使用し続ける必要はない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="8a805-131">Note that ESR does not need to stay on.</span></span> <span data-ttu-id="8a805-132">この手順で問題が解決した場合は、ESR をオフにします。</span><span class="sxs-lookup"><span data-stu-id="8a805-132">You can turn off ESR if this step fixes the issue.</span></span>
4. <span data-ttu-id="8a805-133">Azure Information Protection が登録ポリシーによって範囲を設定されていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="8a805-133">Confirm that Azure Information Protection is not scoped via an onboarding policy.</span></span> <span data-ttu-id="8a805-134">[Get-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell アプレットを使用して、範囲が設定されているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8a805-134">You can use the [Get-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell applet to see if scoping is enabled.</span></span> <span data-ttu-id="8a805-135">次の 2 つの例では、範囲が設定されていない構成の例と、特定のセキュリティ グループを対象に範囲が設定されている構成の例を示します。</span><span class="sxs-lookup"><span data-stu-id="8a805-135">The next two examples show an unscoped configuration and a configuration scoped to a specific security group.</span></span>

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

   <span data-ttu-id="8a805-136">範囲指定が有効な場合、影響を受けるユーザーを、範囲のセキュリティ グループに追加するか、または範囲を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a805-136">If scoping is enabled, the affected user should either be added to the security group for the scope, or the scope should be removed.</span></span> <span data-ttu-id="8a805-137">次の例では、登録で AIP の範囲が指定されたセキュリティ グループに設定されています。[Set-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell アプレットを使用して範囲を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a805-137">In the example below, onboarding has scoped AIP to the indicated security group and the scoping should be removed with the [Set-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell applet.</span></span>

5. <span data-ttu-id="8a805-138">テナントで IIPCv3Service が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a805-138">Confirm that the IPCv3Service is turned on in the tenant.</span></span> <span data-ttu-id="8a805-139">[Get-AadrmConfiguration](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps)  PowerShell のアプレットがサービスの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="8a805-139">The [Get-AadrmConfiguration](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps)  PowerShell applet shows the status of the service.</span></span>

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-scoped-cfg-example.png" alt-text="IPCv3Service が有効になっているどうか確認します。":::

6. <span data-ttu-id="8a805-141">問題が解決しない場合は、[Microsoft Edge のサポート](https://www.microsoftedgeinsider.com/support)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="8a805-141">If the issue isn't fixed, contact [Microsoft Edge support](https://www.microsoftedgeinsider.com/support).</span></span>

### <a name="issue-stuck-at-setting-up-sync-or-couldnt-connect-to-the-sync-server-retrying"></a><span data-ttu-id="8a805-142">問題 : "同期の設定..." でスタックする。または "同期サーバーに接続できません。</span><span class="sxs-lookup"><span data-stu-id="8a805-142">Issue: Stuck at "Setting up sync..." or “Couldn’t connect to the sync server.</span></span> <span data-ttu-id="8a805-143">再試行中…”</span><span class="sxs-lookup"><span data-stu-id="8a805-143">Retrying…”</span></span>

1. <span data-ttu-id="8a805-144">サインアウトし、もう一度サインインします。</span><span class="sxs-lookup"><span data-stu-id="8a805-144">Try to sign out and then sign in.</span></span>
2. <span data-ttu-id="8a805-145">「*edge://sync-internals*」へ移動します。</span><span class="sxs-lookup"><span data-stu-id="8a805-145">Go to *edge://sync-internals*.</span></span> <span data-ttu-id="8a805-146">次のエラーが "**情報入力**"セクションの下に表示される場合は、次の問題、**「発生した Cryptographer エラー」** に進みます。</span><span class="sxs-lookup"><span data-stu-id="8a805-146">If under the "**Type info**" section the following error is present, then  skip to the following issue, **Cryptographer error encountered**.</span></span>

   `"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered"`

3. <span data-ttu-id="8a805-147">サーバー エンドポイントに対して ping を実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="8a805-147">Try pinging the server endpoint.</span></span> <span data-ttu-id="8a805-148">クライアントのサーバー エンドポイントは、次の *「edge://sync-internals」* で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a805-148">The server endpoint for a client is available in *edge://sync-internals*.</span></span> <span data-ttu-id="8a805-149">次のスクリーンショットは、**環境情報**の下のエンドポイント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="8a805-149">The next screenshot shows endpoint information under **Environment Info**.</span></span>

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-endpoint-info.png" alt-text="エンドポイント情報":::

4. <span data-ttu-id="8a805-151">サーバーのエンドポイントが空の場合、またはサーバーに対して ping を実行できない場合、またはファイアウォールが環境に存在する場合は、クライアント コンピューターが必要とするサービス エンドポイントを使用できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a805-151">If the server endpoint is empty, or if server cannot be pinged and a firewall is present in the environment, confirm that the necessary service endpoints are available to the client computer.</span></span>

   - <span data-ttu-id="8a805-152">Microsoft Edge 同期サービス エンドポイント:</span><span class="sxs-lookup"><span data-stu-id="8a805-152">Microsoft Edge sync service endpoints:</span></span>
     - [https://edge-enterprise.activity.windows.com](https://edge-enterprise.activity.windows.com)
     - [https://edge.activity.windows.com](https://edge.activity.windows.com)
    - <span data-ttu-id="8a805-153">Azure Information Protection エンドポイント:</span><span class="sxs-lookup"><span data-stu-id="8a805-153">Azure Information Protection endpoints:</span></span>
      - <span data-ttu-id="8a805-154">[https://api.aadrm.com](https://api.aadrm.com)(ほとんどのテナントの場合)</span><span class="sxs-lookup"><span data-stu-id="8a805-154">[https://api.aadrm.com](https://api.aadrm.com) (for most tenants)</span></span>
      - <span data-ttu-id="8a805-155">[https://api.aadrm.de](https://api.aadrm.de)(ドイツのテナントの場合)</span><span class="sxs-lookup"><span data-stu-id="8a805-155">[https://api.aadrm.de](https://api.aadrm.de) (for tenants in Germany)</span></span>
      - <span data-ttu-id="8a805-156">[https://api.aadrm.cn](https://api.aadrm.cn)(中国のテナントの場合)</span><span class="sxs-lookup"><span data-stu-id="8a805-156">[https://api.aadrm.cn](https://api.aadrm.cn) (for tenants in China)</span></span>
   - <span data-ttu-id="8a805-157">[Windows 通知サービス エンドポイント](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)。</span><span class="sxs-lookup"><span data-stu-id="8a805-157">[Windows Notification Service endpoints](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config).</span></span>

5. <span data-ttu-id="8a805-158">それでも問題が解決しない場合は、[Microsoft Edge のサポート](https://www.microsoftedgeinsider.com/support)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="8a805-158">If the issue still isn't fixed, contact [Microsoft Edge support](https://www.microsoftedgeinsider.com/support).</span></span>

### <a name="issue-cryptographer-error-encountered"></a><span data-ttu-id="8a805-159">問題: Cryptographer エラーが発生する</span><span class="sxs-lookup"><span data-stu-id="8a805-159">Issue: Cryptographer error encountered</span></span>

<span data-ttu-id="8a805-160">このエラーは、*edge://sync-internals* の**種類情報** に表示され、ユーザーのサービス側のデータをリセットする必要があることを意味している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a805-160">This error is visible under **Type info** in *edge://sync-internals* and may mean that the user's service side data needs to be reset.</span></span> <span data-ttu-id="8a805-161">次の例は、暗号化のエラー メッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="8a805-161">The following example shows a cryptography error message:</span></span>
<br><span data-ttu-id="8a805-162">"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered"。</span><span class="sxs-lookup"><span data-stu-id="8a805-162">"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered".</span></span>

1. <span data-ttu-id="8a805-163">Microsoft Edge を再起動し、*「edge://sync-internals」* に移動し、**「AAD アカウントキーの状態」** セクションを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a805-163">Restart Microsoft Edge and navigate to *edge://sync-internals* and check the “**AAD Account Key Status**” section</span></span>
   - <span data-ttu-id="8a805-164">"最終 MIP 結果" での "成功": Cryptographer エラーは、サーバー データが失われたキーで暗号化されている可能性を意味します。</span><span class="sxs-lookup"><span data-stu-id="8a805-164">"Success" in "Last MIP Result": the cryptographer error means server data might be encrypted with a lost key.</span></span> <span data-ttu-id="8a805-165">同期を再開するには、データのリセットが必要です。</span><span class="sxs-lookup"><span data-stu-id="8a805-165">Data reset is needed to resume sync.</span></span>
   - <span data-ttu-id="8a805-166">"最後の MIP 結果" に "アクセス許可なし": Azure AD の変更またはテナントのサブスクリプションの変更が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a805-166">"No permissions" in "Last MIP Result": It is possibly caused by an Azure AD change or tenant subscription changes.</span></span> <span data-ttu-id="8a805-167">同期を再開するには、データのリセットが必要です。</span><span class="sxs-lookup"><span data-stu-id="8a805-167">Data reset is needed to resume sync.</span></span>
   - <span data-ttu-id="8a805-168">その他のエラーは、サーバー構成の問題を意味する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a805-168">Other errors may mean server configuration issues.</span></span>
2. <span data-ttu-id="8a805-169">データのリセットが必要な場合は、[「 クラウドのMicrosoft Edge データをリセットする」](edge-learnmore-reset-data-in-cloud.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a805-169">If data reset is needed, see [Reset Microsoft Edge data in the cloud](edge-learnmore-reset-data-in-cloud.md).</span></span>

### <a name="issue-sync-has-been-turned-off-by-your-administrator"></a><span data-ttu-id="8a805-170">問題: "同期は管理者によってオフにされています。"</span><span class="sxs-lookup"><span data-stu-id="8a805-170">Issue: “Sync has been turned off by your administrator.”</span></span>

<span data-ttu-id="8a805-171">[SyncDisabled ポリシー](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)が設定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a805-171">Make sure that the [SyncDisabled policy](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)  is not set.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a805-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a805-172">See also</span></span>

- [<span data-ttu-id="8a805-173">Microsoft Edge エンタープライズの同期</span><span class="sxs-lookup"><span data-stu-id="8a805-173">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="8a805-174">Microsoft Edge と Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="8a805-174">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="8a805-175">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="8a805-175">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
