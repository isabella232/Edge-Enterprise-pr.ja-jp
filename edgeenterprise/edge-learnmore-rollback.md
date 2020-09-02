---
title: 企業向け Microsoft Edge ロールバック
ms.author: v-danwes
author: dan-wesley
manager: srugh
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge を以前のバージョンにロールバックする方法
ms.openlocfilehash: 9af0881a079dd3059e567eaadb912b3d929924c4
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980437"
---
# <span data-ttu-id="beb15-103">Microsoft Edge を以前のバージョンにロールバックする方法</span><span class="sxs-lookup"><span data-stu-id="beb15-103">How to roll back Microsoft Edge to a previous version</span></span>

<span data-ttu-id="beb15-104">この記事では、ロールバック機能を使用して、Microsoft Edge の以前のバージョンにロールバックする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="beb15-104">This article describes how to roll back to a previous version of Microsoft Edge using the rollback feature.</span></span>

>[!NOTE]
><span data-ttu-id="beb15-105">この記事は Microsoft Edge version 86 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="beb15-105">This article applies to Microsoft Edge version 86 or later.</span></span>

## <span data-ttu-id="beb15-106">ロールバックの概要</span><span class="sxs-lookup"><span data-stu-id="beb15-106">Introduction to rollback</span></span>

<span data-ttu-id="beb15-107">ロールバックすると、Microsoft Edge ブラウザーのバージョンを以前のものに置換えることができます。</span><span class="sxs-lookup"><span data-stu-id="beb15-107">Rollback lets you replace your Microsoft Edge browser version with an earlier version.</span></span> <span data-ttu-id="beb15-108">この機能は、Microsoft Edge を展開する企業のためのセーフティネットとして設計されています。</span><span class="sxs-lookup"><span data-stu-id="beb15-108">This feature is designed to be a safety net for enterprises deploying Microsoft Edge.</span></span> <span data-ttu-id="beb15-109">Microsoft Edge の問題をトラブルシューティングする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="beb15-109">It provides a way to troubleshoot issues with Microsoft Edge.</span></span> <span data-ttu-id="beb15-110">ロールバックの利点は、簡単かつ迅速に以前のブラウザのバージョンに戻すことができることです。</span><span class="sxs-lookup"><span data-stu-id="beb15-110">The benefits of rollback are the ability to revert to previous browser version easily and quickly.</span></span> <span data-ttu-id="beb15-111">ロールバックすることで、Microsoft Edge の問題が業務に与える潜在的な影響を軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="beb15-111">Rollback reduces the potential impact that a Microsoft Edge issue has on business operations.</span></span>

## <span data-ttu-id="beb15-112">始める前に</span><span class="sxs-lookup"><span data-stu-id="beb15-112">Before you begin</span></span>

<span data-ttu-id="beb15-113">Microsoft Edge 環境にロールバック機能がインストールされているしくみを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="beb15-113">It's important to understand how the rollback feature is installed in a Microsoft Edge environment.</span></span> <span data-ttu-id="beb15-114">ロールバックの展開には、MSI を使って手動で行う方法と、Microsoft Edge 更新プログラムおよびグループ ポリシーを使って行う方法の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="beb15-114">You can deploy rollback using two different methods: manually with an MSI or by using Microsoft Edge update and Group Policy.</span></span> <span data-ttu-id="beb15-115">また、よりスムーズに展開するために、グループ ポリシーを選択して使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="beb15-115">We also  encourage using a selection of Group Policies for a smoother deployment.</span></span>

### <span data-ttu-id="beb15-116">推奨事項</span><span class="sxs-lookup"><span data-stu-id="beb15-116">Recommendations</span></span>

<span data-ttu-id="beb15-117">ロールバック機能は、Microsoft Edge ブラウザーの更新プログラムで発生する問題を一時的に修正するためのものです。</span><span class="sxs-lookup"><span data-stu-id="beb15-117">The rollback feature is meant to be a temporary fix for issues you might find in a Microsoft Edge browser update.</span></span> <span data-ttu-id="beb15-118">最新のセキュリティ更新プログラムによって提供される保護機能を使用するには、Microsoft Edge ブラウザーの最新バージョンをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="beb15-118">We recommend that users install the latest version of the Microsoft Edge browser to use the protection provided by the latest security updates.</span></span> <span data-ttu-id="beb15-119">以前のバージョンにロールバックすると、既知のセキュリティ問題にさらされるリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="beb15-119">Rollback to an earlier version risks exposure to known security issues.</span></span>

<span data-ttu-id="beb15-120">ブラウザーのバージョンを一時的にロールバックする前に、組織内のすべてのユーザーの同期を有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="beb15-120">Before temporarily rolling back your browser version, we also highly recommend that you enable Sync for all the users in your organization.</span></span> <span data-ttu-id="beb15-121">同期を有効にしない場合、閲覧データが永久に失われる危険性があります。</span><span class="sxs-lookup"><span data-stu-id="beb15-121">If you don't turn on Sync, there's a risk of permanent browsing data loss.</span></span> <span data-ttu-id="beb15-122">同期の詳細については、「[Microsoft Edge を同期する](microsoft-edge-enterprise-sync.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="beb15-122">For more information about Sync, see [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="beb15-123">常にデータ損失のリスクがあるため、ロールバックは必要な場合のみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="beb15-123">Only use rollback when necessary, there's always the risk of data loss.</span></span>

## <span data-ttu-id="beb15-124">MSI を使用して、手動でのロールバックを有効にする</span><span class="sxs-lookup"><span data-stu-id="beb15-124">Enable rollback manually with an MSI</span></span>

<span data-ttu-id="beb15-125">MSI を使用して手動でロールバックするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="beb15-125">Use the following steps to roll back manually with an MSI.</span></span>

1. <span data-ttu-id="beb15-126">Microsoft Edge 更新プログラムを無効にします。</span><span class="sxs-lookup"><span data-stu-id="beb15-126">Disable Microsoft Edge Updates.</span></span>

   > [!NOTE]
   > <span data-ttu-id="beb15-127">最新の管理用テンプレートをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="beb15-127">We recommend that you install the most current Administrative templates.</span></span> <span data-ttu-id="beb15-128">詳細については、「[Microsoft Edge 管理用テンプレートをダウンロードしてインストールする](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge#1-download-and-install-the-microsoft-edge-administrative-template)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="beb15-128">For more information, see [Download and install the Microsoft Edge administrative template](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge#1-download-and-install-the-microsoft-edge-administrative-template).</span></span>

   - <span data-ttu-id="beb15-129">ローカル グループ ポリシー エディターを開き、 *[コンピューターの構成]、[管理用テンプレート]、[Microsoft Edge 更新プログラム]、[アプリケーション]、[Microsoft Edge]* の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="beb15-129">Open the local Group Policy Editor and go to *Computer Configuration>Administrative Templates>Microsoft Edge Update>Applications>Microsoft Edge>*.</span></span>
   - <span data-ttu-id="beb15-130">[**更新ポリシーの上書き**] を選択し、[**有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="beb15-130">Select **Update policy override** and then select **Enabled**.</span></span>
   - <span data-ttu-id="beb15-131">[**オプション**] で、[ポリシー] ドロップダウンリストから [**無効にする**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="beb15-131">Under **Options**, pick **Update disabled** from the Policy dropdown list.</span></span>

2. <span data-ttu-id="beb15-132">MSI を入手します。</span><span class="sxs-lookup"><span data-stu-id="beb15-132">Get the MSI.</span></span>

   - <span data-ttu-id="beb15-133">ロールバックするバージョン用の MSI をダウンロードするのは [こちら](https://www.microsoft.com/edge/business/download)。</span><span class="sxs-lookup"><span data-stu-id="beb15-133">Download the MSI for the version you want to roll back to [from here](https://www.microsoft.com/edge/business/download).</span></span>
   - <span data-ttu-id="beb15-134">MSI をデスクトップに保存します。</span><span class="sxs-lookup"><span data-stu-id="beb15-134">Save the MSI to your desktop.</span></span>

3. <span data-ttu-id="beb15-135">ロールバック コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="beb15-135">Run the rollback command.</span></span>

   - <span data-ttu-id="beb15-136">**[管理者として実行]** を使用して Windows コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="beb15-136">Open the Windows command prompt with **Run as administrator**.</span></span>
   - <span data-ttu-id="beb15-137">次のコマンドを入力します。 *C:\Users\username\Desktop\test* は、ダウンロードした MSI のパスで、ファイル名は .msi ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="beb15-137">Type the following command, where: *C:\Users\username\Desktop\test* is the path to the MSI you downloaded, and FileName is the name of the .msi file:</span></span><br>
 `C:\Users\username\Desktop\test>msiexec /I FileName.msi /qn ALLOWDOWNGRADE=1`<br>
     > [!NOTE]
     > <span data-ttu-id="beb15-138">msiexec の詳細については、「[msiexec](https://docs.microsoft.com/windows-server/administration/windows-commands/msiexec)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="beb15-138">For more information about msiexec, see [msiexec](https://docs.microsoft.com/windows-server/administration/windows-commands/msiexec).</span></span>
   - <span data-ttu-id="beb15-139">Microsoft Edge を終了して再起動し、ロールバックが正常に機能したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="beb15-139">Close and reopen Microsoft Edge to verify that the rollback worked.</span></span> <span data-ttu-id="beb15-140">[**設定およびその他**] (ALT + F) から [**設定**] に移動し、[**Microsoft Edge について**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="beb15-140">Under **Settings and more** (ALT + F), go to **Settings** and select **About Microsoft Edge**.</span></span>

## <span data-ttu-id="beb15-141">Microsoft Edge 更新プログラムとグループポリシーを使用してロールバックを有効にする</span><span class="sxs-lookup"><span data-stu-id="beb15-141">Enable rollback with Microsoft Edge update and Group Policy</span></span>

<span data-ttu-id="beb15-142">Microsoft Edge 更新プログラムとグループポリシーでロールバックを有効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="beb15-142">Use the following steps to enable rollback with Microsoft Edge update and Group Policy.</span></span>

1. <span data-ttu-id="beb15-143">ローカル グループ ポリシー エディターを開き、 *[コンピューターの構成]、[管理用テンプレート]、[Microsoft Edge 更新プログラム]、[アプリケーション]、[Microsoft Edge]* の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="beb15-143">Open the local Group Policy Editor and go to *Computer Configuration>Administrative Templates>Microsoft Edge Update>Applications>Microsoft Edge>*.</span></span>
2. <span data-ttu-id="beb15-144">[**対象バージョンにロールバック**]、[**有効にする**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="beb15-144">Select **Rollback to target version** and then select **Enabled**.</span></span>
3. <span data-ttu-id="beb15-145">[**対象バージョンの上書き**] を選び、ロールバック先のブラウザー バージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="beb15-145">Select **Target version override** and pick the browser version you want to roll back to.</span></span>
4. <span data-ttu-id="beb15-146">[**更新ポリシーの上書き**] を選択し、[**有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="beb15-146">Select **Update policy override** and then select **Enabled**.</span></span> <span data-ttu-id="beb15-147">[**オプション**] 下の [ポリシー] ドロップダウンリストから次のオプションのいずれかを選択します ([**更新を無効にする**] の場合を除く）。</span><span class="sxs-lookup"><span data-stu-id="beb15-147">Under **Options**, pick one of the following options from the Policy dropdown list (except for **Update disabled**):</span></span>

   - <span data-ttu-id="beb15-148">常に更新プログラムを許可する</span><span class="sxs-lookup"><span data-stu-id="beb15-148">Always allow updates</span></span>
   - <span data-ttu-id="beb15-149">自動サイレント更新に限る</span><span class="sxs-lookup"><span data-stu-id="beb15-149">Automatic silent updates only</span></span>
   - <span data-ttu-id="beb15-150">手動更新に限る</span><span class="sxs-lookup"><span data-stu-id="beb15-150">Manual updates only</span></span>  

5. <span data-ttu-id="beb15-151">ロールバックは、次回 Microsoft Edge Update が更新プログラムをチェックするときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="beb15-151">Rollback will happen the next time Microsoft Edge Update checks for an update.</span></span>

   > [!NOTE]
   > <span data-ttu-id="beb15-152">すぐにロールバックしたい場合は、Microsoft Edge Update のポーリング間隔を変更するか、MSI を使用してロールバックを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="beb15-152">If you want rollback to happen right away you have to change the Microsoft Edge Update polling interval or enable rollback using an MSI.</span></span>

### <span data-ttu-id="beb15-153">一般的なロールバック エラー</span><span class="sxs-lookup"><span data-stu-id="beb15-153">Common rollback errors</span></span>

<span data-ttu-id="beb15-154">ロールバックできなくなるエラーには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="beb15-154">The following errors will prevent rollback:</span></span>

- <span data-ttu-id="beb15-155">入力がサポートされていない対象バージョンである</span><span class="sxs-lookup"><span data-stu-id="beb15-155">Input is an unsupported target version</span></span>
- <span data-ttu-id="beb15-156">入力が存在しない対象バージョンである</span><span class="sxs-lookup"><span data-stu-id="beb15-156">Input is a non-existent target version</span></span>
- <span data-ttu-id="beb15-157">入力のフォーマットが無効である</span><span class="sxs-lookup"><span data-stu-id="beb15-157">Input is incorrectly formatted</span></span>

### <span data-ttu-id="beb15-158">推奨されるグループポリシー</span><span class="sxs-lookup"><span data-stu-id="beb15-158">Recommended Group Policies</span></span>

<span data-ttu-id="beb15-159">ロールバックを使用するには、次のグループポリシーと設定が強く推奨されます。</span><span class="sxs-lookup"><span data-stu-id="beb15-159">The following group policies and settings are highly recommended for using rollback.</span></span>

#### <span data-ttu-id="beb15-160">グループ ポリシーを同期する</span><span class="sxs-lookup"><span data-stu-id="beb15-160">Sync Group Policies</span></span>

- <span data-ttu-id="beb15-161">ForceSync。</span><span class="sxs-lookup"><span data-stu-id="beb15-161">ForceSync.</span></span> <span data-ttu-id="beb15-162">ForceSync を有効にします。</span><span class="sxs-lookup"><span data-stu-id="beb15-162">Set ForceSync to enabled.</span></span> <span data-ttu-id="beb15-163">このポリシーによって、すべての Azure Active Directory (Azure AD) ユーザーの同期の有効化が強制されます。</span><span class="sxs-lookup"><span data-stu-id="beb15-163">This policy will force enable Sync on all Azure Active Directory (Azure AD) users.</span></span> <span data-ttu-id="beb15-164">このポリシーは、Microsoft Edge versions 86 以降でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="beb15-164">This policy is only effective for Microsoft Edge versions 86 and later.</span></span>
- <span data-ttu-id="beb15-165">*同期ポリシーから除外する種類のリストを構成する* により、管理者はユーザーが同期できるデータを制御できます。</span><span class="sxs-lookup"><span data-stu-id="beb15-165">The *Configure the list of the types that are excluded from synchronization policy* allows admins to control what data can be synced by users.</span></span>

#### <span data-ttu-id="beb15-166">ブラウザーの再起動グループポリシー</span><span class="sxs-lookup"><span data-stu-id="beb15-166">Browser restart Group Policies</span></span>

<span data-ttu-id="beb15-167">ロールバックを有効にした後、ユーザーに強制的に再起動させることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="beb15-167">We recommend forcing a restart on users after rollback is enabled.</span></span>

- <span data-ttu-id="beb15-168">[*保留中の更新についてブラウザーの再起動が推奨されている、または必要であることをユーザーに通知する*] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="beb15-168">Enable *Notify a user that a browser restart is recommended or required for pending updates*.</span></span> <span data-ttu-id="beb15-169">[オプション] で [**必須**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="beb15-169">Under Options, select **Required**.</span></span>
- <span data-ttu-id="beb15-170">[*更新通知の期間を設定する*] を有効にしてから、希望する時間をミリ秒単位で設定します。</span><span class="sxs-lookup"><span data-stu-id="beb15-170">Enable *Set the time period for update notifications* and then set the desired time in milliseconds.</span></span>

## <span data-ttu-id="beb15-171">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="beb15-171">Frequently asked questions</span></span>

### <span data-ttu-id="beb15-172">手動での MSI ロールバック</span><span class="sxs-lookup"><span data-stu-id="beb15-172">Manual MSI rollback</span></span>

#### <span data-ttu-id="beb15-173">起こりうる一般的な MSI の問題には何がありますか?</span><span class="sxs-lookup"><span data-stu-id="beb15-173">What generic MSI failures that can happen?</span></span>

1. <span data-ttu-id="beb15-174">[更新グループポリシーのインストール] が無効になっている場合、ロールバックは行われません。</span><span class="sxs-lookup"><span data-stu-id="beb15-174">If the Install update group policy is disabled, rollback won't occur.</span></span>

   - <span data-ttu-id="beb15-175">ロールバックを使用するには、インストールが [**有効**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="beb15-175">To use rollback, make sure Install is set to **Enabled**.</span></span> <span data-ttu-id="beb15-176">このポリシーを無効にすると、Microsoft Edge チャネルがインストールされなくなります。</span><span class="sxs-lookup"><span data-stu-id="beb15-176">When this policy is disabled, it prevents Microsoft Edge channels from being installed.</span></span> <span data-ttu-id="beb15-177">詳細については、「[インストール](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#install)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="beb15-177">For more information, see [Install](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#install).</span></span>

2. <span data-ttu-id="beb15-178">啓蒙更新プログラムが存在しない場合は、[*Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する*] が有効になっていない限り Microsoft Edge のインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="beb15-178">If Enlightenment Updates aren't present, Microsoft Edge installations will be blocked unless *Allow Microsoft Edge Side by Side browser experience* is enabled.</span></span>

   - <span data-ttu-id="beb15-179">Windows Version 1903、1909 では、最終更新が2019年10月以前の場合、この問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="beb15-179">For Windows versions 1903 and 1909: If your last update was before October 2019, you may have this issue.</span></span>
   - <span data-ttu-id="beb15-180">Windows Version 1709、1803、1809 では、最終更新が2019年11月以前の場合、この問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="beb15-180">For Windows versions 1709, 1803, and 1809: If your last update was before November 2019, you may have this issue.</span></span><br>
<span data-ttu-id="beb15-181">詳しくは、「[次のバージョンの Microsoft Edge をサポートする Windows 更新プログラム](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)」 をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="beb15-181">For more information, see [Windows updates to support the next version of Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)</span></span>

#### <span data-ttu-id="beb15-182">コマンド プロンプトを使用してもロールバックが発生せず、以下のようなエラーメッセージが表示されました。</span><span class="sxs-lookup"><span data-stu-id="beb15-182">The following error message was shown after using the Command Prompt and rollback didn't occur.</span></span> <span data-ttu-id="beb15-183">何が問題なのですか?</span><span class="sxs-lookup"><span data-stu-id="beb15-183">What's wrong?</span></span>

![ロールバック ステータス メッセージ](./media/edge-learnmore-rollback/edge-rollback-cmd-flag-error.png)

<span data-ttu-id="beb15-185">*ALLOWDOWNGRADE=1* は実行されませんでした。</span><span class="sxs-lookup"><span data-stu-id="beb15-185">*ALLOWDOWNGRADE=1* was not executed.</span></span>

### <span data-ttu-id="beb15-186">Microsoft Edge 更新プログラムとグループポリシーのロールバック</span><span class="sxs-lookup"><span data-stu-id="beb15-186">Microsoft Edge Update and Group Policy rollback</span></span>

#### <span data-ttu-id="beb15-187">*対象バージョンにロールバック* を設定し、*更新ポリシーの上書き* を有効にして *対象バージョンの上書き* 用に希望するブラウザーのバージョンを入力しましたが、ブラウザーのバージョンは期待したものではありませんでした。</span><span class="sxs-lookup"><span data-stu-id="beb15-187">I set *Rollback to target version*, enabled *Update policy override*, input my desired browser version for *Target version override*, but the browser version wasn't what I expected.</span></span> <span data-ttu-id="beb15-188">何が問題なのですか?</span><span class="sxs-lookup"><span data-stu-id="beb15-188">What's wrong?</span></span>

<span data-ttu-id="beb15-189">ロールバックを妨げる一般的なエラーは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="beb15-189">Some common errors that prevent rollback are:</span></span>

- <span data-ttu-id="beb15-190">対象バージョンへのロールバックが設定されていない場合、ロールバックは実行されません。</span><span class="sxs-lookup"><span data-stu-id="beb15-190">If Rollback to target version isn't set, rollback will not be executed.</span></span>
- <span data-ttu-id="beb15-191">対象バージョンの上書き設定には、次のいずれかの問題があります。</span><span class="sxs-lookup"><span data-stu-id="beb15-191">There are one of the following issues with the target version override setting:</span></span>

  - <span data-ttu-id="beb15-192">対象バージョンの上書きが、サポートされていない対象バージョンに設定されています。</span><span class="sxs-lookup"><span data-stu-id="beb15-192">Target version override is set to an unsupported target version.</span></span>
  - <span data-ttu-id="beb15-193">対象バージョンの上書きが、存在しない対象バージョンに設定されています。</span><span class="sxs-lookup"><span data-stu-id="beb15-193">Target version override is set to a non-existent target version.</span></span>
  - <span data-ttu-id="beb15-194">対象バージョンの上書きの入力形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="beb15-194">Target version override input is incorrectly formatted.</span></span>

- <span data-ttu-id="beb15-195">更新ポリシーの上書きが [更新を無効にする] に設定されている場合、Microsoft Edge Update は更新を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="beb15-195">If Update policy override is set to "Updates disabled", Microsoft Edge Update won't accept any updates.</span></span> <span data-ttu-id="beb15-196">この場合、ロールバックは実行されません。</span><span class="sxs-lookup"><span data-stu-id="beb15-196">This results in rollback not getting executed.</span></span>

### <span data-ttu-id="beb15-197">すべてのグループポリシーを正しく設定しましたが、ロールバックが実行されません。</span><span class="sxs-lookup"><span data-stu-id="beb15-197">I set all the group policies correctly, but rollback didn't execute.</span></span> <span data-ttu-id="beb15-198">何が問題なのですか?</span><span class="sxs-lookup"><span data-stu-id="beb15-198">What happened?</span></span>

<span data-ttu-id="beb15-199">Microsoft Edge Update では、更新プログラムの確認がまだ行われていません。</span><span class="sxs-lookup"><span data-stu-id="beb15-199">Microsoft Edge Update hasn't run a check for updates yet.</span></span> <span data-ttu-id="beb15-200">既定では、自動更新チェックにより 10 時間ごとに更新が確認されます。</span><span class="sxs-lookup"><span data-stu-id="beb15-200">By default, auto-update checks for updates every 10 hours.</span></span> <span data-ttu-id="beb15-201">この問題を解決するには、自動更新のチェック期間の上書きグループポリシーで Microsoft Edge 更新プログラムのポーリング間隔を変更します。</span><span class="sxs-lookup"><span data-stu-id="beb15-201">You can fix this by changing Microsoft Edge Update's polling interval with the Auto-update check period override group policy.</span></span> <span data-ttu-id="beb15-202">詳細については、[AutoUpdateCheckPeriodMinutes](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#autoupdatecheckperiodminutes) ポリシーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="beb15-202">For more information, see the [AutoUpdateCheckPeriodMinutes](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#autoupdatecheckperiodminutes) policy.</span></span>

### <span data-ttu-id="beb15-203">IT 管理者の場合、正常にロールバックするためのすべての手順に従います。</span><span class="sxs-lookup"><span data-stu-id="beb15-203">As an IT admin, I followed all the steps for rollback correctly.</span></span> <span data-ttu-id="beb15-204">ユーザーグループの一部しかロールバックされませんでした。</span><span class="sxs-lookup"><span data-stu-id="beb15-204">Only a portion of my user group was rolled back.</span></span> <span data-ttu-id="beb15-205">他のユーザーが、まだロールバックされていないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="beb15-205">Why haven't the other users been rolled back yet?</span></span>

<span data-ttu-id="beb15-206">グループポリシー設定が、まだすべてのクライアントに同期されていません。</span><span class="sxs-lookup"><span data-stu-id="beb15-206">The group policy setting hasn't synced to all the clients yet.</span></span> <span data-ttu-id="beb15-207">管理者がグループポリシーを設定した場合、クライアントがこれらの設定を即座に受け取ることはありません。</span><span class="sxs-lookup"><span data-stu-id="beb15-207">When admins set a group policy, clients don't receive these settings instantaneously.</span></span>

<!--
You can update all users' group policy with the  

When admins set all users don't get this setting instantaneously 

GP Update force group policy – link to this 

-->





## <span data-ttu-id="beb15-208">関連項目</span><span class="sxs-lookup"><span data-stu-id="beb15-208">See also</span></span>

- [<span data-ttu-id="beb15-209">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="beb15-209">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
