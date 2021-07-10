---
title: パスワード モニターがユーザーに対して自動的に有効にされます
ms.author: supalsul
author: dan-wesley
manager: tulasim
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: パスワード モニターがユーザーに対して自動的に有効にされます
ms.openlocfilehash: 76fc4f0c0ce4bb59ba6b2d4d8a82b61592585918
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11643093"
---
# <a name="password-monitor-auto-enabled-for-users"></a><span data-ttu-id="51efb-103">パスワード モニターがユーザーに対して自動的に有効にされます</span><span class="sxs-lookup"><span data-stu-id="51efb-103">Password Monitor auto-enabled for users</span></span>

<span data-ttu-id="51efb-104">この記事では、選択されたユーザーに対して Microsoft Edge のパスワード モニターがどのように有効になるかについて説明し、管理者が監視を有効にする方法を制御する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="51efb-104">This article describes how Password Monitor in Microsoft Edge will be turned on for select users and gives admins the steps to control how monitoring is enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="51efb-105">この記事は Microsoft Edge バージョン 88 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="51efb-105">This article applies to Microsoft Edge version 88 or later.</span></span>

## <a name="introduction-benefits-and-availability"></a><span data-ttu-id="51efb-106">概要、利点、可用性</span><span class="sxs-lookup"><span data-stu-id="51efb-106">Introduction, benefits, and availability</span></span>

<span data-ttu-id="51efb-107">パスワード モニターは、オンライン リークでパスワードが見つかった場合にユーザーに知らせることで、Microsoft Edge ユーザーがオンライン アカウントを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="51efb-107">Password Monitor helps Microsoft Edge users protect their online accounts by informing them if any of their passwords have been found in an online leak.</span></span> <span data-ttu-id="51efb-108">オンライン リークやデータ侵害は、攻撃者がサード パーティ製のアプリや Web サイトからデータを盗むと発生します。</span><span class="sxs-lookup"><span data-stu-id="51efb-108">Online leaks or data breaches happen when bad actors steal data from third-party apps or websites.</span></span> <span data-ttu-id="51efb-109">詳細については、Microsoft Research ブログの「[パスワード モニター: Microsoft Edge でのパスワードの保護](https://www.microsoft.com/research/blog/password-monitor-safeguarding-passwords-in-microsoft-edge/)」ペーパーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51efb-109">To learn more, see the [Password Monitor: Safeguarding passwords in Microsoft Edge](https://www.microsoft.com/research/blog/password-monitor-safeguarding-passwords-in-microsoft-edge/)  paper on the Microsoft Research Blog.</span></span>

### <a name="benefits"></a><span data-ttu-id="51efb-110">利点</span><span class="sxs-lookup"><span data-stu-id="51efb-110">Benefits</span></span>

<span data-ttu-id="51efb-111">これらのオンラインからの攻撃の頻度と範囲を考慮すると、このような保護をすべてのユーザーが入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51efb-111">Given the frequency and scope of these online attacks having this kind of protection has become necessary for everyone.</span></span> <span data-ttu-id="51efb-112">Microsoft Edge には、侵害されたことが判明しているパスワードに対して、保存されたユーザーのパスワードを安全に確認し、一致が見つかった場合にはユーザーに警告する組み込みの機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="51efb-112">Microsoft Edge has the built-in ability to securely check a user's saved passwords against passwords that are known to be compromised and alerts them if a match is found.</span></span>  

### <a name="availability"></a><span data-ttu-id="51efb-113">可用性</span><span class="sxs-lookup"><span data-stu-id="51efb-113">Availability</span></span>

<span data-ttu-id="51efb-114">パスワード モニターは、1/21 以降の安定チャネル バージョン 88 で使用できます。</span><span class="sxs-lookup"><span data-stu-id="51efb-114">Password Monitor is available in Stable Channel version 88 starting 1/21.</span></span> <span data-ttu-id="51efb-115">ロールアウトは段階的に行われるため、**[設定]** > **[プロファイル]** > **[パスワード]** ページに次のメッセージと制御が表示されるまでに数週間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="51efb-115">The rollout will be gradual and it could take a few weeks before you will see the following message and control in your **Settings** > **Profile** > **Password** page.</span></span>

:::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-enable-option.png" alt-text="パスワード モニターを有効にするオプション":::

## <a name="configure-group-policy-for-password-monitor"></a><span data-ttu-id="51efb-117">パスワード モニターのグループ ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="51efb-117">Configure group policy for Password Monitor</span></span>

<span data-ttu-id="51efb-118">この機能は [PasswordMonitorAllowed](./microsoft-edge-policies.md#passwordmonitorallowed) グループ ポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="51efb-118">This feature is controlled via the [PasswordMonitorAllowed](./microsoft-edge-policies.md#passwordmonitorallowed) group policy.</span></span>

<span data-ttu-id="51efb-119">ポリシーを有効にした後も、ユーザーは機能を有効にすることについて同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51efb-119">After the policy is enabled, users still need to provide consent to turn on the feature.</span></span> <span data-ttu-id="51efb-120">この機能にはユーザーの機密データと個人データ (パスワード) が含まれているため、同意が必要です。</span><span class="sxs-lookup"><span data-stu-id="51efb-120">Consent is required because the feature contains user's sensitive and personal data (passwords).</span></span> <span data-ttu-id="51efb-121">グループ ポリシーを使用して機能が無効になっている場合、ユーザーはこの設定を上書きできません。</span><span class="sxs-lookup"><span data-stu-id="51efb-121">If the feature is disabled using group policy, users can't override this setting.</span></span>  

## <a name="enabling-password-monitor-for-users"></a><span data-ttu-id="51efb-122">ユーザーに対してパスワード モニターを有効にする</span><span class="sxs-lookup"><span data-stu-id="51efb-122">Enabling Password Monitor for users</span></span>

<span data-ttu-id="51efb-123">パスワード モニター ポリシーが有効になると、さまざまな方法でこの機能をユーザーに利用可能にできます。</span><span class="sxs-lookup"><span data-stu-id="51efb-123">After the password monitor policy is enabled, there are different ways this feature is made available to users.</span></span>

- <span data-ttu-id="51efb-124">自動有効化。</span><span class="sxs-lookup"><span data-stu-id="51efb-124">Auto-enablement.</span></span> <span data-ttu-id="51efb-125">仕事用アカウント (Active Directory または Azure Active Directory) を使用してサインインし、パスワードを同期しているユーザーの場合、この機能が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="51efb-125">Users that are signed-in using their work account (Active Directory or Azure Active Directory) and syncing their passwords will be auto-enabled for this feature.</span></span> <span data-ttu-id="51efb-126">次のスクリーンショットに示されているように、ユーザーには機能が有効になっていることを知らせる通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51efb-126">They will  see the notification in the next screenshot informing them that the feature's turned on.</span></span>

  :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-enabled-notice.png" alt-text="パスワード モニターの有効化に関する通知":::

-  <span data-ttu-id="51efb-128">明示的な同意を得る。</span><span class="sxs-lookup"><span data-stu-id="51efb-128">Getting explicit consent.</span></span> <span data-ttu-id="51efb-129">パスワード同期が有効になっていないユーザーには、パスワード モニターを有効にするためのアクセス許可が要求されます。</span><span class="sxs-lookup"><span data-stu-id="51efb-129">Users that don’t have Password Sync turned on will be asked for permission to turn on Password Monitor.</span></span> <span data-ttu-id="51efb-130">次のアクションが発生すると、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51efb-130">They will be prompted when the following actions happen:</span></span>
   - <span data-ttu-id="51efb-131">ユーザーが新しいパスワードを保存した場合。</span><span class="sxs-lookup"><span data-stu-id="51efb-131">When a user is saving a new password.</span></span>
 
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-save-pw-prompt.png" alt-text="パスワードを保存するかどうかを尋ねるメッセージ":::

   - <span data-ttu-id="51efb-133">ユーザーが保存されたパスワードを使用してブラウザーにサインインした場合。</span><span class="sxs-lookup"><span data-stu-id="51efb-133">When a user has signed-in to the browser using a saved password.</span></span>
  
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-after-signin.png" alt-text="サインイン後の確認プロンプト":::
   
- <span data-ttu-id="51efb-135">直接のライセンス認証。</span><span class="sxs-lookup"><span data-stu-id="51efb-135">Direct activation.</span></span> <span data-ttu-id="51efb-136">ユーザーは、いつでも **[設定]** > **[パスワード]** に移動して、機能のオンとオフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="51efb-136">Users can go to **Settings** > **Passwords** anytime and turn the feature On or Off.</span></span>

## <a name="user-scenarios-with-password-monitor-auto-enabled"></a><span data-ttu-id="51efb-137">パスワード モニターが自動的に有効になっているユーザー シナリオ</span><span class="sxs-lookup"><span data-stu-id="51efb-137">User scenarios with Password Monitor auto-enabled</span></span>

<span data-ttu-id="51efb-138">次の表は、パスワード モニターが自動的に有効になっているシナリオと、ユーザーのデバイスでのパスワード モニターの動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="51efb-138">The following table shows scenarios where Password Monitor is auto-enabled and how it will work on user devices.</span></span>

| <span data-ttu-id="51efb-139">シナリオ</span><span class="sxs-lookup"><span data-stu-id="51efb-139">Scenario</span></span> | <span data-ttu-id="51efb-140">基本条件</span><span class="sxs-lookup"><span data-stu-id="51efb-140">Base conditions</span></span> | <span data-ttu-id="51efb-141">影響</span><span class="sxs-lookup"><span data-stu-id="51efb-141">Impact</span></span> |
|--|--|--|
| <span data-ttu-id="51efb-142">1. 同期がオン</span><span class="sxs-lookup"><span data-stu-id="51efb-142">1 with Sync on</span></span> | <span data-ttu-id="51efb-143">同期オン</span><span class="sxs-lookup"><span data-stu-id="51efb-143">Sync ON</span></span><br><span data-ttu-id="51efb-144">以前に機能が有効にされた: いいえ</span><span class="sxs-lookup"><span data-stu-id="51efb-144">Feature enabled previously: No</span></span><br><span data-ttu-id="51efb-145">同意の UI への応答: なし</span><span class="sxs-lookup"><span data-stu-id="51efb-145">Response to Consent UI: None</span></span> | <span data-ttu-id="51efb-146">機能は既定で有効になっており、ブラウザーが起動した 2 分後に通知バブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51efb-146">Feature enabled by default and a notice bubble is shown 2 min after browser starts.</span></span><br><span data-ttu-id="51efb-147">- その後に同期がオフになると、機能は無効になります。</span><span class="sxs-lookup"><span data-stu-id="51efb-147">- If sync is turned off after that, the feature is disabled.</span></span><br><span data-ttu-id="51efb-148">- 同期を変更する前に機能をオフにした場合、同期は機能に影響を与えなくなります。</span><span class="sxs-lookup"><span data-stu-id="51efb-148">-  Feature turned off before altering sync, sync will no longer affect the feature.</span></span>   |
| <span data-ttu-id="51efb-149">2. 同期がオン</span><span class="sxs-lookup"><span data-stu-id="51efb-149">2 with Sync on</span></span> | <span data-ttu-id="51efb-150">同期オン</span><span class="sxs-lookup"><span data-stu-id="51efb-150">Sync ON</span></span><br><span data-ttu-id="51efb-151">以前に機能が有効にされた: はい</span><span class="sxs-lookup"><span data-stu-id="51efb-151">Feature enabled previously: Yes</span></span><br><span data-ttu-id="51efb-152">同意の UI への応答: なし</span><span class="sxs-lookup"><span data-stu-id="51efb-152">Response to Consent UI: None</span></span> | <span data-ttu-id="51efb-153">機能はユーザーの選択と同じままになります。</span><span class="sxs-lookup"><span data-stu-id="51efb-153">Feature stays the same as user choice.</span></span>  <span data-ttu-id="51efb-154">通知バブルは表示されず、同期の変更が機能の値に影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="51efb-154">Notice bubble isn't shown and there's no affect of sync change on feature value.</span></span>|
| <span data-ttu-id="51efb-155">3. 同期がオフ</span><span class="sxs-lookup"><span data-stu-id="51efb-155">3 with Sync off</span></span> | <span data-ttu-id="51efb-156">同期オフ</span><span class="sxs-lookup"><span data-stu-id="51efb-156">Sync Off</span></span><br><span data-ttu-id="51efb-157">以前に機能が有効にされた: いいえ</span><span class="sxs-lookup"><span data-stu-id="51efb-157">Feature enabled previously: No</span></span><br><span data-ttu-id="51efb-158">同意の UI への応答: なし</span><span class="sxs-lookup"><span data-stu-id="51efb-158">Response to Consent UI: None</span></span> | <span data-ttu-id="51efb-159">同期がオフになり、機能は無効のままになります</span><span class="sxs-lookup"><span data-stu-id="51efb-159">Sync will be off and the feature will stay disabled</span></span><br><span data-ttu-id="51efb-160">- ユーザーが機能を変更せずに、その後の任意の時点で同期を有効にした場合: 機能が有効になり、同期が有効になった 2 分後に自動有効化の通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51efb-160">- At any point after that if user turns the sync on without altering the feature: the feature is enabled and auto-enablement notification is shown 2 minutes after Sync is turned on.</span></span> <br> <span data-ttu-id="51efb-161">- 同期が再びオフになった場合、機能は無効になります</span><span class="sxs-lookup"><span data-stu-id="51efb-161">- If sync is turned off again, the  feature is disabled</span></span> <br><span data-ttu-id="51efb-162">- 同期を有効にする前に機能を変更した場合、同期がパスワード モニターに影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="51efb-162">- If the feature is changed before turning on sync, sync will no longer affect Password Monitor.</span></span>  |  
| <span data-ttu-id="51efb-163">4. 同期がオフ</span><span class="sxs-lookup"><span data-stu-id="51efb-163">4 with Sync off</span></span> | <span data-ttu-id="51efb-164">同期オフ</span><span class="sxs-lookup"><span data-stu-id="51efb-164">Sync OFF</span></span><br><span data-ttu-id="51efb-165">以前に機能が有効にされた: はい</span><span class="sxs-lookup"><span data-stu-id="51efb-165">Feature enabled previously: Yes</span></span><br><span data-ttu-id="51efb-166">同意の UI への応答: なし</span><span class="sxs-lookup"><span data-stu-id="51efb-166">Response to Consent UI: None</span></span> | <span data-ttu-id="51efb-167">機能はユーザーの選択と同じままになり、通知バブルは表示されません。また、同期の変更が機能の値に影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="51efb-167">Feature stays the same as user choice, notice bubble isn't shown, and there's no effect of sync change on the feature value.</span></span>  |

<span data-ttu-id="51efb-168">さらに、ユーザーが次のいずれかに対するポリシーによって制限されている仕事用アカウントを使用してサインインしている場合、機能がユーザーに対して自動的に有効になることはありません。</span><span class="sxs-lookup"><span data-stu-id="51efb-168">In addition, if a user is signed-in using a work account that is restricted via policies for any of the following, the feature will NOT be auto-enabled for them:</span></span>

- <span data-ttu-id="51efb-169">パスワード モニターが無効になっている</span><span class="sxs-lookup"><span data-stu-id="51efb-169">Password Monitor is disabled</span></span>  
- <span data-ttu-id="51efb-170">パスワード同期が無効になっている</span><span class="sxs-lookup"><span data-stu-id="51efb-170">Password Sync is disabled</span></span>
- <span data-ttu-id="51efb-171">Microsoft サーバーとのデータ共有が無効になっている</span><span class="sxs-lookup"><span data-stu-id="51efb-171">Sharing of data with Microsoft servers is disabled</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="51efb-172">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="51efb-172">Frequently Asked Questions</span></span>

### <a name="how-can-password-monitor-be-disabled-for-my-organization"></a><span data-ttu-id="51efb-173">組織でパスワード モニターを無効にするにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="51efb-173">How can Password Monitor be disabled for my organization?</span></span>

<span data-ttu-id="51efb-174">組織のパスワード モニターは、次の方法で無効にできます。</span><span class="sxs-lookup"><span data-stu-id="51efb-174">You can disable Password Monitor for your organization by:</span></span>
- <span data-ttu-id="51efb-175">PasswordMonitorAllowed グループ ポリシーの使用。</span><span class="sxs-lookup"><span data-stu-id="51efb-175">Using the PasswordMonitorAllowed group policy.</span></span>
- <span data-ttu-id="51efb-176">データが同期され、Microsoft サーバーに送信されることを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="51efb-176">Stopping data from being synchronized and sent to Microsoft servers.</span></span>

  > [!NOTE]
  > <span data-ttu-id="51efb-177">パスワードの同期が無効になっている場合でも、ユーザーが機能をオンにすることに明示的に同意した場合や、自分で [設定] から有効にしている場合は、パスワード モニターが機能します。</span><span class="sxs-lookup"><span data-stu-id="51efb-177">Password Monitor can work even if Password Sync is disabled, as long as the user has given explicit consent to turn the feature On or have turned it on themselves via Settings.</span></span>

### <a name="what-happens-if-a-user-for-whom-the-feature-has-been-auto-enabled-turns-password-monitor-off-via-settings"></a><span data-ttu-id="51efb-178">機能が自動的に有効になっているユーザーが [設定] からパスワード モニターをオフにした場合、どうなりますか。</span><span class="sxs-lookup"><span data-stu-id="51efb-178">What happens if a user for whom the feature has been auto-enabled, turns Password Monitor off via Settings?</span></span>

<span data-ttu-id="51efb-179">ユーザー設定が優先され、そのユーザーに対しては機能が無効のままになります。</span><span class="sxs-lookup"><span data-stu-id="51efb-179">The user setting is honored and the feature will remain disabled for that user.</span></span> <span data-ttu-id="51efb-180">ただし、これまで同意プロンプトに一度も応答したことがない場合は、もう一度同意ダイアログが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="51efb-180">However, they might be shown a consent dialog again in case they've never previously responded to the consent prompt.</span></span>

## <a name="see-also"></a><span data-ttu-id="51efb-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="51efb-181">See also</span></span>

- [<span data-ttu-id="51efb-182">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="51efb-182">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)