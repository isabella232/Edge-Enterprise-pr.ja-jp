---
title: Microsoft Edge Update のポリシーに関するドキュメント
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 11/12/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge アップデーターでサポートされているすべてのポリシーに関するドキュメント
ms.openlocfilehash: 0cdcda984efff8d10a84431e44c49ffbf28ddf07
ms.sourcegitcommit: c2ac4f889b625210b9365a60a447482fb5b4c9d4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "11167309"
---
# <span data-ttu-id="7d25d-103">Microsoft Edge - 更新ポリシー</span><span class="sxs-lookup"><span data-stu-id="7d25d-103">Microsoft Edge - Update policies</span></span>

<span data-ttu-id="7d25d-104">最新バージョンの Microsoft Edge には、Microsoft Edge をいつどのように更新するかを制御するために使用できる以下のポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d25d-104">The latest version of Microsoft Edge includes the following policies that you can use to control how and when Microsoft Edge is updated.</span></span>

<span data-ttu-id="7d25d-105">Microsoft Edge で使用できるその他のポリシーについて詳しくは、[Microsoft Edge ブラウザー ポリシー リファレンス](microsoft-edge-policies.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7d25d-105">For information about other policies available in Microsoft Edge, check out [Microsoft Edge browser policy reference](microsoft-edge-policies.md)</span></span>
> [!NOTE]
> <span data-ttu-id="7d25d-106">この記事は、Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-106">This article applies to Microsoft Edge version 77 or later.</span></span>
## <span data-ttu-id="7d25d-107">使用可能なポリシー</span><span class="sxs-lookup"><span data-stu-id="7d25d-107">Available policies</span></span>
<span data-ttu-id="7d25d-108">次の表は、このリリースの Microsoft Edge で使用可能な、更新関連のすべてのグループ ポリシーの一覧を示しています。</span><span class="sxs-lookup"><span data-stu-id="7d25d-108">These tables lists all of the update-related group policies available in this release of Microsoft Edge.</span></span> <span data-ttu-id="7d25d-109">個々のポリシーに関する詳しい情報を取得するには、表内のリンクをお使いください。</span><span class="sxs-lookup"><span data-stu-id="7d25d-109">Use the links in the table to get more details about specific policies.</span></span>

|||
|-|-|
|[<span data-ttu-id="7d25d-110">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7d25d-110">Applications</span></span>](#applications)|[<span data-ttu-id="7d25d-111">基本設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-111">Preferences</span></span>](#preferences)|
|[<span data-ttu-id="7d25d-112">プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="7d25d-112">Proxy Server</span></span>](#proxy-server)|[<span data-ttu-id="7d25d-113">Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="7d25d-113">Microsoft Edge WebView</span></span>](#microsoft-edge-webview)|

### [<span data-ttu-id="7d25d-114">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7d25d-114">Applications</span></span>](#applications-policies)
|<span data-ttu-id="7d25d-115">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="7d25d-115">Policy Name</span></span>|<span data-ttu-id="7d25d-116">キャプション</span><span class="sxs-lookup"><span data-stu-id="7d25d-116">Caption</span></span>|
|-|-|
|[<span data-ttu-id="7d25d-117">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="7d25d-117">InstallDefault</span></span>](#installdefault)|<span data-ttu-id="7d25d-118">インストールの既定の動作を許可する</span><span class="sxs-lookup"><span data-stu-id="7d25d-118">Allow installation default</span></span>|
|[<span data-ttu-id="7d25d-119">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="7d25d-119">UpdateDefault</span></span>](#updatedefault)|<span data-ttu-id="7d25d-120">更新ポリシーのオーバーライドの既定値</span><span class="sxs-lookup"><span data-stu-id="7d25d-120">Update policy override default</span></span>|
|[<span data-ttu-id="7d25d-121">Install</span><span class="sxs-lookup"><span data-stu-id="7d25d-121">Install</span></span>](#install)|<span data-ttu-id="7d25d-122">インストールを許可する (チャネルごと)</span><span class="sxs-lookup"><span data-stu-id="7d25d-122">Allow installation (per channel)</span></span>|
|[<span data-ttu-id="7d25d-123">Update</span><span class="sxs-lookup"><span data-stu-id="7d25d-123">Update</span></span>](#update)|<span data-ttu-id="7d25d-124">更新ポリシーのオーバーライド (チャネルごと)</span><span class="sxs-lookup"><span data-stu-id="7d25d-124">Update policy override (per channel)</span></span>|
|[<span data-ttu-id="7d25d-125">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="7d25d-125">Allowsxs</span></span>](#allowsxs)|<span data-ttu-id="7d25d-126">Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する</span><span class="sxs-lookup"><span data-stu-id="7d25d-126">Allow Microsoft Edge Side by Side browser experience</span></span>|
|[<span data-ttu-id="7d25d-127">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="7d25d-127">CreateDesktopShortcutDefault</span></span>](#createdesktopshortcutdefault)|<span data-ttu-id="7d25d-128">既定値のインストール時にデスクトップへのショートカットの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="7d25d-128">Prevent Desktop Shortcut creation upon install default</span></span>|
|[<span data-ttu-id="7d25d-129">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="7d25d-129">CreateDesktopShortcut</span></span>](#createdesktopshortcut)|<span data-ttu-id="7d25d-130">インストール時にデスクトップへのショートカットの作成を禁止する (チャネル単位)</span><span class="sxs-lookup"><span data-stu-id="7d25d-130">Prevent Desktop Shortcut creation upon install (per channel)</span></span>|
|[<span data-ttu-id="7d25d-131">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="7d25d-131">RollbackToTargetVersion</span></span>](#rollbacktotargetversion)|<span data-ttu-id="7d25d-132">ターゲットバージョンにロールバック (チャネル単位)</span><span class="sxs-lookup"><span data-stu-id="7d25d-132">Rollback to Target version (per channel)</span></span>|
|[<span data-ttu-id="7d25d-133">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="7d25d-133">TargetVersionPrefix</span></span>](#targetversionprefix)|<span data-ttu-id="7d25d-134">ターゲットバージョンの上書き (チャネルごと) </span><span class="sxs-lookup"><span data-stu-id="7d25d-134">Target version override (per channel)</span></span>|

### [<span data-ttu-id="7d25d-135">基本設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-135">Preferences</span></span>](#preferences-policies)
|<span data-ttu-id="7d25d-136">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="7d25d-136">Policy Name</span></span>|<span data-ttu-id="7d25d-137">キャプション</span><span class="sxs-lookup"><span data-stu-id="7d25d-137">Caption</span></span>|
|-|-|
|[<span data-ttu-id="7d25d-138">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="7d25d-138">AutoUpdateCheckPeriodMinutes</span></span>](#autoupdatecheckperiodminutes)|<span data-ttu-id="7d25d-139">自動更新チェック期間のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="7d25d-139">Auto-update check period override</span></span>|
|[<span data-ttu-id="7d25d-140">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="7d25d-140">UpdatesSuppressed</span></span>](#updatessuppressed)|<span data-ttu-id="7d25d-141">自動更新チェックを停止する 1 日あたりの時間帯</span><span class="sxs-lookup"><span data-stu-id="7d25d-141">Time period in each day to suppress auto-update check</span></span>|

### [<span data-ttu-id="7d25d-142">プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="7d25d-142">Proxy Server</span></span>](#proxy-server-policies)
|<span data-ttu-id="7d25d-143">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="7d25d-143">Policy Name</span></span>|<span data-ttu-id="7d25d-144">キャプション</span><span class="sxs-lookup"><span data-stu-id="7d25d-144">Caption</span></span>|
|-|-|
|[<span data-ttu-id="7d25d-145">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="7d25d-145">ProxyMode</span></span>](#proxymode)|<span data-ttu-id="7d25d-146">プロキシ サーバーの設定をどのように指定するかを選択する</span><span class="sxs-lookup"><span data-stu-id="7d25d-146">Choose how to specify proxy server settings</span></span>|
|[<span data-ttu-id="7d25d-147">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="7d25d-147">ProxyPacUrl</span></span>](#proxypacurl)|<span data-ttu-id="7d25d-148">プロキシ .pac ファイルへの URL</span><span class="sxs-lookup"><span data-stu-id="7d25d-148">URL to a proxy .pac file</span></span>|
|[<span data-ttu-id="7d25d-149">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="7d25d-149">ProxyServer</span></span>](#proxyserver)|<span data-ttu-id="7d25d-150">プロキシ サーバーのアドレスまたは URL</span><span class="sxs-lookup"><span data-stu-id="7d25d-150">Address or URL of proxy server</span></span>|

### [<span data-ttu-id="7d25d-151">Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="7d25d-151">Microsoft Edge WebView</span></span>](#microsoft-edge-webview-policies)
|<span data-ttu-id="7d25d-152">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="7d25d-152">Policy Name</span></span>|<span data-ttu-id="7d25d-153">キャプション</span><span class="sxs-lookup"><span data-stu-id="7d25d-153">Caption</span></span>|
|-|-|
|[<span data-ttu-id="7d25d-154">Install</span><span class="sxs-lookup"><span data-stu-id="7d25d-154">Install</span></span>](#install-webview)|<span data-ttu-id="7d25d-155">インストールを許可する</span><span class="sxs-lookup"><span data-stu-id="7d25d-155">Allow installation</span></span>|
|[<span data-ttu-id="7d25d-156">更新</span><span class="sxs-lookup"><span data-stu-id="7d25d-156">Update</span></span>](#update-webview)|<span data-ttu-id="7d25d-157">更新ポリシーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="7d25d-157">Update policy override</span></span>|

## <span data-ttu-id="7d25d-158">アプリケーションに関するポリシー</span><span class="sxs-lookup"><span data-stu-id="7d25d-158">Applications policies</span></span>

[<span data-ttu-id="7d25d-159">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-159">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="7d25d-160">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="7d25d-160">InstallDefault</span></span>
#### <span data-ttu-id="7d25d-161">インストールの既定の動作を許可する</span><span class="sxs-lookup"><span data-stu-id="7d25d-161">Allow installation default</span></span>
><span data-ttu-id="7d25d-162">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-162">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="7d25d-163">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-163">Description</span></span>
<span data-ttu-id="7d25d-164">すべてのチャネルに既定の動作を指定して、ドメインに参加しているデバイスで Microsoft Edge を許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-164">You can specify the default behavior of all channels to allow or block Microsoft Edge on domain-joined devices.</span></span>

<span data-ttu-id="7d25d-165">特定のチャネルの['インストールを許可する'](#install)ポリシーを有効にすることで、チャネルごとにポリシーを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-165">You can override this policy for individual channels by enabling the '[Allow installation](#install)' policy for specific channels.</span></span>

<span data-ttu-id="7d25d-166">このポリシーを無効にすると、Microsoft Edge のインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-166">If you disable this policy, the installation of Microsoft Edge is blocked.</span></span> <span data-ttu-id="7d25d-167">これは、[[インストールの許可](#install)] ポリシーが未構成に設定されている場合は、Microsoft Edge ソフトウェアのインストールにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="7d25d-167">This only affects the installation of Microsoft Edge software when the '[Allow installation](#install)' policy is set to Not Configured.</span></span>

<span data-ttu-id="7d25d-168">このポリシーによって、Microsoft Edge Update の実行は禁止されません。また、ユーザーが Microsoft Edge ソフトウェアを他の方法を使用してインストールすることも禁止されません。</span><span class="sxs-lookup"><span data-stu-id="7d25d-168">This policy doesn't prevent Microsoft Edge Update from running or prevent users from installing Microsoft Edge software using other methods.</span></span>

<span data-ttu-id="7d25d-169">このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-169">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="7d25d-170">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-170">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-171">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-171">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-172">GP 固有の名前: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="7d25d-172">GP unique name: InstallDefault</span></span>
- <span data-ttu-id="7d25d-173">GP の名前: インストールの既定の動作を許可する</span><span class="sxs-lookup"><span data-stu-id="7d25d-173">GP name: Allow installation default</span></span>
- <span data-ttu-id="7d25d-174">GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7d25d-174">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="7d25d-175">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-175">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-176">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-176">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-177">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-177">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-178">値の名前: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="7d25d-178">Value Name: InstallDefault</span></span>
- <span data-ttu-id="7d25d-179">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7d25d-179">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7d25d-180">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-180">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7d25d-181">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-181">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7d25d-182">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="7d25d-182">UpdateDefault</span></span>
#### <span data-ttu-id="7d25d-183">更新ポリシーのオーバーライドの既定値</span><span class="sxs-lookup"><span data-stu-id="7d25d-183">Update policy override default</span></span>
><span data-ttu-id="7d25d-184">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-184">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="7d25d-185">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-185">Description</span></span>
<span data-ttu-id="7d25d-186">Microsoft Edge で利用できる更新プログラムを Microsoft Edge Update で処理する方法について、すべてのチャネルを対象とした既定の動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-186">Lets you specify the default behavior for all channels concerning the way Microsoft Edge Update handles available updates for Microsoft Edge.</span></span> <span data-ttu-id="7d25d-187">特定のチャネルに対して['更新ポリシーの上書き'](#update) ポリシーを指定することにより、個々のチャネルに対して上書きできます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-187">Can be overridden for individual channels by specifying the '[Update policy override](#update)' policy for those specific channels.</span></span>

  <span data-ttu-id="7d25d-188">このポリシーを有効にした場合、Microsoft Edge Update では、以下のオプションの構成方法に従って Microsoft Edge の更新プログラムを処理します。</span><span class="sxs-lookup"><span data-stu-id="7d25d-188">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="7d25d-189">[常に更新を許可する]: 定期的な更新チェックまたは手動更新チェックで検出された場合に、更新プログラムを必ず適用します。</span><span class="sxs-lookup"><span data-stu-id="7d25d-189">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="7d25d-190">[自動サイレント更新のみ]: 更新プログラムは、定期的な更新チェックで検出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-190">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="7d25d-191">[手動更新のみ]: 更新プログラムは、ユーザーが実行した手動更新チェックで検出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-191">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span>
   - <span data-ttu-id="7d25d-192">[更新を無効にする]: 更新プログラムは適用されません。</span><span class="sxs-lookup"><span data-stu-id="7d25d-192">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="7d25d-193">手動更新を選択した場合は、アプリの手動更新メカニズムを使用して、必ず定期的に更新プログラムをチェックしてください (手動更新メカニズムが利用できる場合)。</span><span class="sxs-lookup"><span data-stu-id="7d25d-193">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="7d25d-194">更新を無効にした場合は、定期的に更新プログラムをチェックして、ユーザーに配布してください。</span><span class="sxs-lookup"><span data-stu-id="7d25d-194">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="7d25d-195">このポリシーを有効にして構成しない場合、Microsoft Edge Update は、['更新ポリシーの上書き'](#update) ポリシーで指定された使用可能な更新を処理します。</span><span class="sxs-lookup"><span data-stu-id="7d25d-195">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override](#update)' policy.</span></span>

  <span data-ttu-id="7d25d-196">このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-196">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="7d25d-197">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-197">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-198">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-198">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-199">GP 固有の名前: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="7d25d-199">GP unique name: UpdateDefault</span></span>
- <span data-ttu-id="7d25d-200">GP の名前: 更新ポリシーのオーバーライドの既定値</span><span class="sxs-lookup"><span data-stu-id="7d25d-200">GP name: Update policy override default</span></span>
- <span data-ttu-id="7d25d-201">GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7d25d-201">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="7d25d-202">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-202">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-203">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-203">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-204">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-204">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-205">値の名前: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="7d25d-205">Value Name: UpdateDefault</span></span>
- <span data-ttu-id="7d25d-206">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7d25d-206">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7d25d-207">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-207">Example value:</span></span>
```
0x00000003
```
[<span data-ttu-id="7d25d-208">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-208">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7d25d-209">Install</span><span class="sxs-lookup"><span data-stu-id="7d25d-209">Install</span></span>
#### <span data-ttu-id="7d25d-210">インストールを許可する</span><span class="sxs-lookup"><span data-stu-id="7d25d-210">Allow installation</span></span>
><span data-ttu-id="7d25d-211">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-211">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="7d25d-212">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-212">Description</span></span>
<span data-ttu-id="7d25d-213">ドメインに参加しているデバイスに Microsoft Edge チャネルをインストールできるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7d25d-213">Specifies whether a Microsoft Edge channel can be installed on domain-joined devices.</span></span>

  <span data-ttu-id="7d25d-214">このポリシーをチャネルに対して有効にすると、Microsoft Edge はインストールのブロックをされなくなります。</span><span class="sxs-lookup"><span data-stu-id="7d25d-214">If you enable this policy for a channel, Microsoft Edge will not be blocked from installation.</span></span>

  <span data-ttu-id="7d25d-215">チャネルに対してこのポリシーを無効にすると、Microsoft Edge はインストールされなくなります。</span><span class="sxs-lookup"><span data-stu-id="7d25d-215">If you disable this policy for a channel, Microsoft Edge will be blocked from installation.</span></span>

  <span data-ttu-id="7d25d-216">チャネルにこのポリシーを構成しない場合、「[インストールの既定の動作を許可する](#installdefault)」 ポリシー構成により、ユーザーがMicrosoft Edge のそのチャネルをインストールできるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="7d25d-216">If you don't configure this policy for a channel, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install that channel of Microsoft Edge.</span></span>

  <span data-ttu-id="7d25d-217">このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-217">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="7d25d-218">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-218">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-219">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-219">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-220">GP 固有の名前: Install</span><span class="sxs-lookup"><span data-stu-id="7d25d-220">GP unique name: Install</span></span>
- <span data-ttu-id="7d25d-221">GP の名前: インストールを許可する</span><span class="sxs-lookup"><span data-stu-id="7d25d-221">GP name: Allow installation</span></span>
- <span data-ttu-id="7d25d-222">GP パス: </span><span class="sxs-lookup"><span data-stu-id="7d25d-222">GP path:</span></span> 
  - <span data-ttu-id="7d25d-223">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7d25d-223">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="7d25d-224">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="7d25d-224">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="7d25d-225">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="7d25d-225">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="7d25d-226">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="7d25d-226">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="7d25d-227">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-227">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-228">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-228">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-229">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-229">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-230">値の名前: </span><span class="sxs-lookup"><span data-stu-id="7d25d-230">Value Name:</span></span> 
  - <span data-ttu-id="7d25d-231">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="7d25d-231">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="7d25d-232">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="7d25d-232">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="7d25d-233">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="7d25d-233">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="7d25d-234">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="7d25d-234">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="7d25d-235">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7d25d-235">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7d25d-236">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-236">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7d25d-237">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-237">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7d25d-238">Update</span><span class="sxs-lookup"><span data-stu-id="7d25d-238">Update</span></span>
#### <span data-ttu-id="7d25d-239">更新ポリシーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="7d25d-239">Update policy override</span></span>
><span data-ttu-id="7d25d-240">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-240">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="7d25d-241">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-241">Description</span></span>
<span data-ttu-id="7d25d-242">Microsoft Edge で利用できる更新プログラムを Microsoft Edge Update でどのように処理するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="7d25d-242">Specifies how Microsoft Edge Update handles available updates from Microsoft Edge.</span></span>

<span data-ttu-id="7d25d-243">このポリシーを有効にした場合、Microsoft Edge Update では、以下のオプションの構成方法に従って Microsoft Edge の更新プログラムを処理します。</span><span class="sxs-lookup"><span data-stu-id="7d25d-243">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="7d25d-244">[常に更新を許可する]: 定期的な更新チェックまたは手動更新チェックで検出された場合に、更新プログラムを必ず適用します。</span><span class="sxs-lookup"><span data-stu-id="7d25d-244">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
  - <span data-ttu-id="7d25d-245">[自動サイレント更新のみ]: 更新プログラムは、定期的な更新チェックで検出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-245">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
  - <span data-ttu-id="7d25d-246">[手動更新のみ]: 更新プログラムは、ユーザーが実行した手動更新チェックで検出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-246">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span> <span data-ttu-id="7d25d-247">(アプリによっては、このオプション用のインターフェイスがない場合もあります。)</span><span class="sxs-lookup"><span data-stu-id="7d25d-247">(Not all apps provide an interface for this option.)</span></span>
  - <span data-ttu-id="7d25d-248">[更新を無効にする]: 更新プログラムは適用されません。</span><span class="sxs-lookup"><span data-stu-id="7d25d-248">Updates disabled: Updates are never applied.</span></span>

<span data-ttu-id="7d25d-249">手動更新を選択した場合は、アプリの手動更新メカニズムを使用して、必ず定期的に更新プログラムをチェックしてください (手動更新メカニズムが利用できる場合)。</span><span class="sxs-lookup"><span data-stu-id="7d25d-249">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="7d25d-250">更新を無効にした場合は、定期的に更新プログラムをチェックして、ユーザーに配布してください。</span><span class="sxs-lookup"><span data-stu-id="7d25d-250">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

<span data-ttu-id="7d25d-251">このポリシーを有効にせず、構成しない場合、Microsoft Edge Update は、[「更新ポリシー上書きの既定値」](#updatedefault) ポリシーで指定された使用可能な更新プログラムを処理します。</span><span class="sxs-lookup"><span data-stu-id="7d25d-251">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override default](#updatedefault)' policy.</span></span>

<span data-ttu-id="7d25d-252">詳細については、「[https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d25d-252">See [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406) for more information.</span></span>

<span data-ttu-id="7d25d-253">このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-253">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="7d25d-254">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-254">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-255">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-255">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-256">GP 固有の名前: Update</span><span class="sxs-lookup"><span data-stu-id="7d25d-256">GP unique name: Update</span></span>
- <span data-ttu-id="7d25d-257">GP の名前: 更新ポリシーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="7d25d-257">GP name: Update policy override</span></span>
- <span data-ttu-id="7d25d-258">GP パス: </span><span class="sxs-lookup"><span data-stu-id="7d25d-258">GP path:</span></span> 
  - <span data-ttu-id="7d25d-259">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7d25d-259">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="7d25d-260">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="7d25d-260">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="7d25d-261">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="7d25d-261">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="7d25d-262">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="7d25d-262">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="7d25d-263">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-263">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-264">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-264">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-265">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-265">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-266">値の名前: </span><span class="sxs-lookup"><span data-stu-id="7d25d-266">Value Name:</span></span> 
  - <span data-ttu-id="7d25d-267">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="7d25d-267">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="7d25d-268">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="7d25d-268">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="7d25d-269">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="7d25d-269">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="7d25d-270">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="7d25d-270">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="7d25d-271">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7d25d-271">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7d25d-272">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-272">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7d25d-273">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-273">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7d25d-274">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="7d25d-274">Allowsxs</span></span>
#### <span data-ttu-id="7d25d-275">Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する</span><span class="sxs-lookup"><span data-stu-id="7d25d-275">Allow Microsoft Edge Side by Side browser experience</span></span>
><span data-ttu-id="7d25d-276">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-276">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="7d25d-277">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-277">Description</span></span>
<span data-ttu-id="7d25d-278">このポリシーを使用すると、ユーザーは Microsoft Edge (Edge HTML) と Microsoft Edge (Chromium ベース) を同時に実行できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-278">This policy lets a user run Microsoft Edge (Edge HTML) and Microsoft Edge (Chromium-based) side-by-side.</span></span>

<span data-ttu-id="7d25d-279">このポリシーを "未構成" に設定した場合、Microsoft Edge (Chromium ベース) 安定チャネルと 2019 年 11 月のセキュリティ更新プログラムをインストールすると、Microsoft Edge (Edge HTML) が Microsoft Edge (Chromium ベース) に置き換わります。</span><span class="sxs-lookup"><span data-stu-id="7d25d-279">If this policy is set to “Not configured”, Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="7d25d-280">これは、"無効" に設定した場合と同じ動作です。</span><span class="sxs-lookup"><span data-stu-id="7d25d-280">This is the same behavior as the “Disabled” setting.</span></span>

<span data-ttu-id="7d25d-281">"無効" に設定した場合、同時実行エクスペリエンスがブロックされ、Microsoft Edge (Chromium ベース) 安定チャネルと 2019 年 11 月のセキュリティ更新プログラムをインストールすると、Microsoft Edge (Edge HTML) が Microsoft Edge (Chromium ベース) に置き換わります。</span><span class="sxs-lookup"><span data-stu-id="7d25d-281">The “Disabled” setting blocks a side-by-side experience and Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="7d25d-282">これは、"未構成" に設定した場合と同じ動作です。</span><span class="sxs-lookup"><span data-stu-id="7d25d-282">This is the same behavior as the “Not Configured” setting.</span></span>

<span data-ttu-id="7d25d-283">このポリシーを "有効" に設定した場合、Microsoft Edge (Chromium ベース) をインストールすると、Microsoft Edge (Chromium ベース) と Microsoft Edge (Edge HTML) を同時に実行できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-283">When this policy is “Enabled”, Microsoft Edge (Chromium-based) and Microsoft Edge (Edge HTML) can run side-by-side after Microsoft Edge (Chromium-based) is installed.</span></span>

<span data-ttu-id="7d25d-284">このグループ ポリシーを有効するには、Windows Update による Microsoft Edge (Chromium ベース) の自動インストールが行われる前に、ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d25d-284">For this group policy to take affect, it must be configured before the automatic install of Microsoft Edge (Chromium-based) by Windows Update.</span></span> <span data-ttu-id="7d25d-285">注意: ユーザーは、Microsoft Edge (Chromium ベース) Blocker Toolkit を使用して、Microsoft Edge (Chromium ベース) の自動更新をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-285">Note: A user can block the automatic update of Microsoft Edge (Chromium-based) by using the Microsoft Edge (Chromium-based) Blocker Toolkit.</span></span>
#### <span data-ttu-id="7d25d-286">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-286">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-287">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-287">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-288">GP 固有の名前: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="7d25d-288">GP unique name: Allowsxs</span></span>
- <span data-ttu-id="7d25d-289">GP の名前: Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する</span><span class="sxs-lookup"><span data-stu-id="7d25d-289">GP name: Allow Microsoft Edge Side by Side browser experience</span></span>
- <span data-ttu-id="7d25d-290">GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7d25d-290">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="7d25d-291">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-291">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-292">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-292">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-293">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-293">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-294">値の名前: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="7d25d-294">Value Name: Allowsxs</span></span>
- <span data-ttu-id="7d25d-295">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7d25d-295">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7d25d-296">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-296">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7d25d-297">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-297">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7d25d-298">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="7d25d-298">CreateDesktopShortcutDefault</span></span>
#### <span data-ttu-id="7d25d-299">既定値のインストール時にデスクトップへのショートカットの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="7d25d-299">Prevent Desktop Shortcut creation upon install default</span></span>
><span data-ttu-id="7d25d-300">Microsoft Edge Update 1.3.128.0 以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-300">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="7d25d-301">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-301">Description</span></span>
<span data-ttu-id="7d25d-302">Microsoft Edge がインストールされている場合に、デスクトップにショートカットを作成するすべてのチャネルに対する既定の動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-302">Lets you specify the default behavior for all channels for creating a desktop shortcut when Microsoft Edge is installed.</span></span>

  <span data-ttu-id="7d25d-303">このポリシーを有効にすると、Microsoft Edge がインストールされている場合、デスクトップにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-303">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="7d25d-304">このポリシーを無効にすると、Microsoft Edge インストールされていても、デスクトップにショートカットは作成されません。</span><span class="sxs-lookup"><span data-stu-id="7d25d-304">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="7d25d-305">このポリシーを構成していない場合は、インストール中に Microsoft Edge のデスクトップにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-305">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="7d25d-306">Microsoft Edge が既にインストールされている場合、このポリシーの効果はありません。</span><span class="sxs-lookup"><span data-stu-id="7d25d-306">If Microsoft Edge is already installed, this policy will have no effect.</span></span>
#### <span data-ttu-id="7d25d-307">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-307">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-308">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-308">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-309">GP 固有の名前: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="7d25d-309">GP unique name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="7d25d-310">GP の名前: 既定値のインストール時にデスクトップへのショートカットの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="7d25d-310">GP name: Prevent Desktop Shortcut creation upon install default</span></span>
- <span data-ttu-id="7d25d-311">GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7d25d-311">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="7d25d-312">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-312">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-313">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-313">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-314">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-314">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-315">値の名前: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="7d25d-315">Value Name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="7d25d-316">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7d25d-316">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7d25d-317">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-317">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7d25d-318">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-318">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7d25d-319">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="7d25d-319">CreateDesktopShortcut</span></span>
#### <span data-ttu-id="7d25d-320">インストール時にデスクトップへのショートカットの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="7d25d-320">Prevent Desktop Shortcut creation upon install</span></span>
><span data-ttu-id="7d25d-321">Microsoft Edge Update 1.3.128.0 以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-321">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="7d25d-322">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-322">Description</span></span>
<span data-ttu-id="7d25d-323">このポリシーを有効にすると、Microsoft Edge がインストールされている場合、デスクトップにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-323">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="7d25d-324">このポリシーを無効にすると、Microsoft Edge インストールされていても、デスクトップにショートカットは作成されません。</span><span class="sxs-lookup"><span data-stu-id="7d25d-324">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="7d25d-325">このポリシーを構成していない場合は、インストール中に Microsoft Edge のデスクトップにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-325">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="7d25d-326">Microsoft Edge が既にインストールされている場合、このポリシーの効果はありません。</span><span class="sxs-lookup"><span data-stu-id="7d25d-326">If Microsoft Edge is already installed, this policy will have no effect.</span></span>

  <span data-ttu-id="7d25d-327">チャネルにこのポリシーを構成しない場合、「[インストール時にデスクトップショートカットを作成しない](#createdesktopshortcutdefault)」ポリシー構成により、Microsoft Edge のインストール時にショートカットの作成が決まります。</span><span class="sxs-lookup"><span data-stu-id="7d25d-327">If you don't configure this policy for a channel, the '[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)' policy configuration determines shortcut creation when Microsoft Edge is installed.</span></span>
#### <span data-ttu-id="7d25d-328">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-328">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-329">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-329">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-330">GP 固有の名前: CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="7d25d-330">GP unique name: CreateDesktopShortcut</span></span>
- <span data-ttu-id="7d25d-331">GP の名前: インストール時にデスクトップへのショートカットの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="7d25d-331">GP name: Prevent Desktop Shortcut creation upon install</span></span>
- <span data-ttu-id="7d25d-332">GP パス: </span><span class="sxs-lookup"><span data-stu-id="7d25d-332">GP path:</span></span> 
  - <span data-ttu-id="7d25d-333">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7d25d-333">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="7d25d-334">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="7d25d-334">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="7d25d-335">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="7d25d-335">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="7d25d-336">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="7d25d-336">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="7d25d-337">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-337">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-338">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-338">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-339">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-339">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-340">キーの値: </span><span class="sxs-lookup"><span data-stu-id="7d25d-340">Value Name:</span></span> 
  - <span data-ttu-id="7d25d-341">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="7d25d-341">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="7d25d-342">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="7d25d-342">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="7d25d-343">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="7d25d-343">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="7d25d-344">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="7d25d-344">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="7d25d-345">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7d25d-345">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7d25d-346">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-346">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7d25d-347">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-347">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7d25d-348">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="7d25d-348">RollbackToTargetVersion</span></span>
#### <span data-ttu-id="7d25d-349">ターゲットバージョンにロールバックする</span><span class="sxs-lookup"><span data-stu-id="7d25d-349">Rollback to Target version</span></span>
><span data-ttu-id="7d25d-350">Microsoft Edge Update 1.3.133.3以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-350">Microsoft Edge Update 1.3.133.3 and later</span></span>

#### <span data-ttu-id="7d25d-351">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-351">Description</span></span>
<span data-ttu-id="7d25d-352">Microsoft Edge の更新プログラムで、Microsoft Edge のインストールを '[ターゲットバージョンの上書き](#targetversionprefix)' で指定されたバージョンにロールバックするように指定します。</span><span class="sxs-lookup"><span data-stu-id="7d25d-352">Specifies that Microsoft Edge Update should rollback installations of Microsoft Edge to the version indicated in '[Target version override](#targetversionprefix)'.</span></span>

<span data-ttu-id="7d25d-353">このポリシーは、[[ターゲットバージョンが上書きする]](#targetversionprefix)' が設定されていて、[[更新ポリシーの上書き]](#update)' がオン状態のいずれかに設定されている場合を除き (常に更新プログラム、自動サイレント更新のみ、手動更新のみを許可します)何も影響がありません。</span><span class="sxs-lookup"><span data-stu-id="7d25d-353">This policy has no effect unless '[Target version override](#targetversionprefix)' is set and '[Update policy override](#update)' is set to one of the ON states (Always allow updates, Automatic silent updates only, Manual updates only).</span></span>

<span data-ttu-id="7d25d-354">このポリシーを無効にした場合、または構成しなかった場合、'[ターゲットバージョンの上書き](#targetversionprefix)' で指定されているバージョンよりも高いバージョンにするようなインストールは変化せずそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="7d25d-354">If you disable this policy or don't configure it, installs that have a version higher than that specified by '[Target version override](#targetversionprefix)' will be left as-is.</span></span>

<span data-ttu-id="7d25d-355">このポリシーを有効にした場合、["ターゲットバージョンの上書き](#targetversionprefix)" によって指定されたよりも高いバージョンにするようなインストールは、ターゲットバージョンにダウングレードされます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-355">If you enable this policy, installs that have a current version higher than specified by the '[Target version override](#targetversionprefix)' will be downgraded to the target version.</span></span>

<span data-ttu-id="7d25d-356">最新のセキュリティ更新プログラムによる保護機能を使用するには、Microsoft Edge ブラウザーの最新バージョンをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7d25d-356">We recommend that users install the latest version of the Microsoft Edge browser to ensure protection by the latest security updates.</span></span> <span data-ttu-id="7d25d-357">以前のバージョンにロールバックすると、既知のセキュリティ問題にさらされるリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="7d25d-357">Rollback to an earlier version risks exposure to known security issues.</span></span> <span data-ttu-id="7d25d-358">このポリシーは、Microsoft Edge ブラウザーの更新プログラムの問題に対処するための一時的な修正プログラムとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-358">This policy is meant to be used as a temporary fix to address issues in a Microsoft Edge browser update.</span></span>

<span data-ttu-id="7d25d-359">ブラウザーのバージョンを一時的にロールバックする前に、組織内のすべてのユーザーの同期 ([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)) を有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7d25d-359">Before temporarily rolling back your browser version, we recommend that you turn on Sync ([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)) for all users in your organization.</span></span> <span data-ttu-id="7d25d-360">同期を有効にしない場合、閲覧データが永久に失われる危険性があります。</span><span class="sxs-lookup"><span data-stu-id="7d25d-360">If you don't turn on Sync, there is a risk of permanent browsing data loss.</span></span> <span data-ttu-id="7d25d-361">このポリシーは、自己の責任においてご使用ください。</span><span class="sxs-lookup"><span data-stu-id="7d25d-361">Use this policy at your own risk.</span></span>

<span data-ttu-id="7d25d-362">注: ロールバック可能なすべてのバージョンは、ここにあります [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise)。</span><span class="sxs-lookup"><span data-stu-id="7d25d-362">Note: All versions available for rollback can be viewed here [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise).</span></span>

<span data-ttu-id="7d25d-363">これは、Microsoft Edge バージョン 86以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-363">This policy applies to Microsoft Edge version 86 or later.</span></span>

<span data-ttu-id="7d25d-364">詳細については、「[https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d25d-364">See [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918) for more information.</span></span>

<span data-ttu-id="7d25d-365">このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-365">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="7d25d-366">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-366">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-367">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-367">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-368">GP 固有の名前: RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="7d25d-368">GP unique name: RollbackToTargetVersion</span></span>
- <span data-ttu-id="7d25d-369">GP 名: ターゲットバージョンにロールバックする</span><span class="sxs-lookup"><span data-stu-id="7d25d-369">GP name: Rollback to Target version</span></span>
- <span data-ttu-id="7d25d-370">GP パス: </span><span class="sxs-lookup"><span data-stu-id="7d25d-370">GP path:</span></span> 
  - <span data-ttu-id="7d25d-371">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7d25d-371">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="7d25d-372">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="7d25d-372">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="7d25d-373">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="7d25d-373">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="7d25d-374">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="7d25d-374">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="7d25d-375">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-375">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-376">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-376">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-377">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-377">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-378">キーの値: </span><span class="sxs-lookup"><span data-stu-id="7d25d-378">Value Name:</span></span> 
  - <span data-ttu-id="7d25d-379">(Stable): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="7d25d-379">(Stable): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="7d25d-380">(ベータ): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="7d25d-380">(Beta): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="7d25d-381">(カナリア): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="7d25d-381">(Canary): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="7d25d-382">(Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="7d25d-382">(Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="7d25d-383">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7d25d-383">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7d25d-384">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-384">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7d25d-385">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-385">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7d25d-386">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="7d25d-386">TargetVersionPrefix</span></span>
#### <span data-ttu-id="7d25d-387">ターゲット バージョンの上書き</span><span class="sxs-lookup"><span data-stu-id="7d25d-387">Target version override</span></span>
><span data-ttu-id="7d25d-388">Microsoft Edge Update 1.3.119.43 以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-388">Microsoft Edge Update 1.3.119.43 and later</span></span>

#### <span data-ttu-id="7d25d-389">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-389">Description</span></span>
<span data-ttu-id="7d25d-390">このポリシーを有効にして自動更新を有効にすると、Microsoft Edge がこのポリシー値で指定されたバージョンに更新されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-390">When this policy is enabled, and auto-update is enabled, Microsoft Edge will be updated to the version specified by this policy value.</span></span>

<span data-ttu-id="7d25d-391">ポリシー値は、83.0.499.12 のような特定の Microsoft Edge バージョンである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d25d-391">The policy value must be a specific Microsoft Edge version, e.g. 83.0.499.12.</span></span>

<span data-ttu-id="7d25d-392">指定した値より新しいバージョンの Microsoft Edge がデバイスにある場合、Microsoft Edge は新しいバージョンのままとなり、指定されたバージョンにダウングレードされません。</span><span class="sxs-lookup"><span data-stu-id="7d25d-392">If a device has newer version of Microsoft Edge than the value specified, Microsoft Edge will remain on the newer version and not downgrade to the specified version.</span></span>

<span data-ttu-id="7d25d-393">指定したバージョンが存在しない場合、または正しく書式設定されていない場合は、Microsoft Edge は現在のバージョンにとどまり、将来のバージョンに自動的に更新されません。</span><span class="sxs-lookup"><span data-stu-id="7d25d-393">If the specified version does not exist, or is improperly formatted, then Microsoft Edge will remain on its current version and not update to future versions automatically.</span></span>

<span data-ttu-id="7d25d-394">詳細については、「[https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d25d-394">See [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707) for more information.</span></span>

<span data-ttu-id="7d25d-395">このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-395">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="7d25d-396">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-396">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-397">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-397">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-398">GP 固有の名前: TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="7d25d-398">GP unique name: TargetVersionPrefix</span></span>
- <span data-ttu-id="7d25d-399">GP の名前: ターゲット バージョンの上書き</span><span class="sxs-lookup"><span data-stu-id="7d25d-399">GP name: Target version override</span></span>
- <span data-ttu-id="7d25d-400">GP パス: </span><span class="sxs-lookup"><span data-stu-id="7d25d-400">GP path:</span></span> 
  - <span data-ttu-id="7d25d-401">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7d25d-401">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="7d25d-402">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="7d25d-402">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="7d25d-403">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="7d25d-403">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="7d25d-404">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="7d25d-404">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="7d25d-405">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-405">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-406">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-406">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-407">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-407">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-408">キーの値: </span><span class="sxs-lookup"><span data-stu-id="7d25d-408">Value Name:</span></span> 
  - <span data-ttu-id="7d25d-409">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="7d25d-409">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="7d25d-410">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="7d25d-410">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="7d25d-411">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="7d25d-411">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="7d25d-412">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="7d25d-412">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="7d25d-413">値の種類: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7d25d-413">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="7d25d-414">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-414">Example value:</span></span>
```
83.0.499.12
```
[<span data-ttu-id="7d25d-415">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-415">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="7d25d-416">基本設定に関するポリシー</span><span class="sxs-lookup"><span data-stu-id="7d25d-416">Preferences policies</span></span>

[<span data-ttu-id="7d25d-417">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-417">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="7d25d-418">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="7d25d-418">AutoUpdateCheckPeriodMinutes</span></span>
#### <span data-ttu-id="7d25d-419">自動更新チェック期間のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="7d25d-419">Auto-update check period override</span></span>
><span data-ttu-id="7d25d-420">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-420">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="7d25d-421">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-421">Description</span></span>
<span data-ttu-id="7d25d-422">有効にした場合、このポリシーによって、自動更新チェックの最小間隔の値 (分単位) を設定できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-422">If enabled, this policy lets you set a value for the minimum number of minutes between automatic update checks.</span></span> <span data-ttu-id="7d25d-423">有効にしなかった場合、自動更新チェックでは、既定で 10 時間ごとに更新が確認されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-423">Otherwise, by default, auto-update checks for updates every 10 hours.</span></span>

  <span data-ttu-id="7d25d-424">すべての自動更新チェックを無効にする場合は、値を 0 に設定します (推奨しません)。</span><span class="sxs-lookup"><span data-stu-id="7d25d-424">If you want to disable all auto-update checks, set the value to 0 (not recommended).</span></span>
#### <span data-ttu-id="7d25d-425">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-425">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-426">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-426">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-427">GP 固有の名前: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="7d25d-427">GP unique name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="7d25d-428">GP の名前: 自動更新チェック期間のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="7d25d-428">GP name: Auto-update check period override</span></span>
- <span data-ttu-id="7d25d-429">GP パス: 管理用テンプレート/Microsoft Edge Update/基本設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-429">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="7d25d-430">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-430">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-431">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-431">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-432">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-432">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-433">値の名前: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="7d25d-433">Value Name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="7d25d-434">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7d25d-434">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7d25d-435">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-435">Example value:</span></span>
```
0x00000578
```
[<span data-ttu-id="7d25d-436">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-436">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7d25d-437">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="7d25d-437">UpdatesSuppressed</span></span>
#### <span data-ttu-id="7d25d-438">自動更新チェックを停止する 1 日あたりの時間帯</span><span class="sxs-lookup"><span data-stu-id="7d25d-438">Time period in each day to suppress auto-update check</span></span>
><span data-ttu-id="7d25d-439">Microsoft Edge Update 1.3.33.5 以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-439">Microsoft Edge Update 1.3.33.5 and later</span></span>

#### <span data-ttu-id="7d25d-440">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-440">Description</span></span>
<span data-ttu-id="7d25d-441">このポリシーを有効にした場合、更新チェックは毎日指定の時刻 (時:分) に停止され、一定の期間、更新チェックが行われなくなります (分単位)。</span><span class="sxs-lookup"><span data-stu-id="7d25d-441">If you enable this policy, update checks are suppressed each day starting at Hour:Minute for a period of Duration (in minutes).</span></span> <span data-ttu-id="7d25d-442">この期間では夏時間が考慮されません。</span><span class="sxs-lookup"><span data-stu-id="7d25d-442">Duration isn't affected by daylight saving time.</span></span> <span data-ttu-id="7d25d-443">たとえば、開始時間が 22:00、期間が 480 分の場合、その期間内で夏時間の開始や終了が発生しても、更新は正確に 8 時間停止されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-443">For example, if the start time is 22:00 and the duration is 480 minutes, updates will be suppressed for exactly 8 hours, regardless of whether daylight saving time starts or ends during this period.</span></span>

  <span data-ttu-id="7d25d-444">このポリシーを無効にした場合または構成しなかった場合、更新チェックが一定期間停止されることはありません。</span><span class="sxs-lookup"><span data-stu-id="7d25d-444">If you disable or don't configure this policy, update checks aren't suppressed during any specific period.</span></span>
#### <span data-ttu-id="7d25d-445">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-445">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-446">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-446">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-447">GP 固有の名前: UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="7d25d-447">GP unique name: UpdatesSuppressed</span></span>
- <span data-ttu-id="7d25d-448">GP の名前: 自動更新チェックを停止する 1 日あたりの時間帯</span><span class="sxs-lookup"><span data-stu-id="7d25d-448">GP name: Time period in each day to suppress auto-update check</span></span>
  - <span data-ttu-id="7d25d-449">オプション { Hour, Minute, Duration }</span><span class="sxs-lookup"><span data-stu-id="7d25d-449">Options { Hour, Minute, Duration }</span></span>
- <span data-ttu-id="7d25d-450">GP パス: 管理用テンプレート/Microsoft Edge Update/基本設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-450">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="7d25d-451">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-451">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-452">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-452">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-453">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-453">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-454">値の名前: </span><span class="sxs-lookup"><span data-stu-id="7d25d-454">Value Name:</span></span> 
  - <span data-ttu-id="7d25d-455">UpdatesSuppressedDurationMin</span><span class="sxs-lookup"><span data-stu-id="7d25d-455">UpdatesSuppressedDurationMin</span></span>
  - <span data-ttu-id="7d25d-456">UpdatesSuppressedStartHour</span><span class="sxs-lookup"><span data-stu-id="7d25d-456">UpdatesSuppressedStartHour</span></span>
  - <span data-ttu-id="7d25d-457">UpdatesSuppressedStartMin</span><span class="sxs-lookup"><span data-stu-id="7d25d-457">UpdatesSuppressedStartMin</span></span>
- <span data-ttu-id="7d25d-458">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7d25d-458">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7d25d-459">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-459">Example value:</span></span>
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[<span data-ttu-id="7d25d-460">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-460">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="7d25d-461">プロキシ サーバーに関するポリシー</span><span class="sxs-lookup"><span data-stu-id="7d25d-461">Proxy Server policies</span></span>

[<span data-ttu-id="7d25d-462">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-462">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="7d25d-463">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="7d25d-463">ProxyMode</span></span>
#### <span data-ttu-id="7d25d-464">プロキシ サーバーの設定をどのように指定するかを選択する</span><span class="sxs-lookup"><span data-stu-id="7d25d-464">Choose how to specify proxy server settings</span></span>
><span data-ttu-id="7d25d-465">Microsoft Edge Update 1.3.21.81 以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-465">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="7d25d-466">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-466">Description</span></span>
<span data-ttu-id="7d25d-467">Microsoft Edge Update で使用されるプロキシ サーバーの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-467">Allows you to specify the proxy server settings that are used by Microsoft Edge Update.</span></span>

  <span data-ttu-id="7d25d-468">このポリシーを有効にした場合、以下のプロキシ サーバーのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-468">If you enable this policy, you can choose between the following proxy server options:</span></span>
   - <span data-ttu-id="7d25d-469">プロキシ サーバーを使用せず、常に直接接続することを選択した場合、他のオプションはすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-469">If you choose to never use a proxy server and always connect directly, all other options are ignored.</span></span>
   - <span data-ttu-id="7d25d-470">システム プロキシ設定を使用するか、プロキシ サーバーの自動検出を選択した場合、他のオプションはすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-470">If you choose to use system proxy settings or auto-detect the proxy server, all other options are ignored.</span></span>
   - <span data-ttu-id="7d25d-471">固定サーバー プロキシ モードを選択した場合、'[プロキシ サーバーのアドレスまたは URL](#proxyserver)' でさらにオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-471">If you choose fixed server proxy mode, you can specify further options in '[Address or URL of proxy server](#proxyserver)' policy.</span></span>
   - <span data-ttu-id="7d25d-472">.pac プロキシスクリプトを使用する場合は、'[プロキシ .pac ファイルへの URL ](#proxypacurl)' ポリシーでスクリプトの URL を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d25d-472">If you choose to use a .pac proxy script, you must specify the URL for the script in '[URL to a proxy .pac file](#proxypacurl)' policy.</span></span>

  <span data-ttu-id="7d25d-473">このポリシーを有効にした場合、組織内のユーザーは Microsoft Edge Update でプロキシ設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="7d25d-473">If you enable this policy, users in your organization can't change the proxy settings in Microsoft Edge Update.</span></span>

  <span data-ttu-id="7d25d-474">このポリシーを無効にした場合または構成しなかった場合、プロキシ サーバーの設定は構成されませんが、組織内のユーザーは Microsoft Edge Update で独自のプロキシ設定を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-474">If you disable or don't configure this policy, no proxy server settings are configured, but users in your organization can choose their own proxy settings for Microsoft Edge Update.</span></span>
#### <span data-ttu-id="7d25d-475">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-475">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-476">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-476">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-477">GP 固有の名前: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="7d25d-477">GP unique name: ProxyMode</span></span>
- <span data-ttu-id="7d25d-478">GP の名前: プロキシ サーバーの設定をどのように指定するかを選択する</span><span class="sxs-lookup"><span data-stu-id="7d25d-478">GP name: Choose how to specify proxy server settings</span></span>
- <span data-ttu-id="7d25d-479">GP パス: 管理用テンプレート/Microsoft Edge Update/プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="7d25d-479">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="7d25d-480">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-480">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-481">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-481">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-482">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-482">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-483">値の名前: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="7d25d-483">Value Name: ProxyMode</span></span>
- <span data-ttu-id="7d25d-484">値の種類: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7d25d-484">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="7d25d-485">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-485">Example value:</span></span>
```
fixed_servers
```
[<span data-ttu-id="7d25d-486">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-486">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7d25d-487">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="7d25d-487">ProxyPacUrl</span></span>
#### <span data-ttu-id="7d25d-488">プロキシ .pac ファイルへの URL</span><span class="sxs-lookup"><span data-stu-id="7d25d-488">URL to a proxy .pac file</span></span>
><span data-ttu-id="7d25d-489">Microsoft Edge Update 1.3.21.81 以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-489">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="7d25d-490">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-490">Description</span></span>
<span data-ttu-id="7d25d-491">プロキシ自動構成 (PAC) ファイルの URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-491">Allows you to specify a URL for a proxy auto-config (PAC) file.</span></span>

  <span data-ttu-id="7d25d-492">このポリシーを有効にした場合、PAC ファイルの URL を指定して、特定の Web サイトを取得するための適切なプロキシサーバーを Microsoft Edge Update で選択する方法を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-492">If you enable this policy, you can specify a URL for a PAC file to automate how Microsoft Edge Update selects the appropriate proxy server for fetching a particular website.</span></span>

  <span data-ttu-id="7d25d-493">このポリシーは、 '[プロキシサーバー設定の指定方法を選択する](#proxymode)' ポリシーで手動プロキシ設定を指定した場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-493">This policy is applied only if you have specified manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="7d25d-494">'[プロキシ サーバーの設定をどのように指定するかを選択する](#proxymode)'ポリシーで手動以外のプロキシ設定を選択した場合は、このポリシーを構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="7d25d-494">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="7d25d-495">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-495">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-496">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-496">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-497">GP 固有の名前: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="7d25d-497">GP unique name: ProxyPacUrl</span></span>
- <span data-ttu-id="7d25d-498">GP の名前: プロキシ .pac ファイルへの URL</span><span class="sxs-lookup"><span data-stu-id="7d25d-498">GP name: URL to a proxy .pac file</span></span>
- <span data-ttu-id="7d25d-499">GP パス: 管理用テンプレート/Microsoft Edge Update/プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="7d25d-499">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="7d25d-500">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-500">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-501">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-501">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-502">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-502">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-503">値の名前: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="7d25d-503">Value Name: ProxyPacUrl</span></span>
- <span data-ttu-id="7d25d-504">値の種類: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7d25d-504">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="7d25d-505">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-505">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="7d25d-506">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-506">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7d25d-507">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="7d25d-507">ProxyServer</span></span>
#### <span data-ttu-id="7d25d-508">プロキシ サーバーのアドレスまたは URL</span><span class="sxs-lookup"><span data-stu-id="7d25d-508">Address or URL of proxy server</span></span>
><span data-ttu-id="7d25d-509">Microsoft Edge Update 1.3.21.81 以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-509">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="7d25d-510">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-510">Description</span></span>
<span data-ttu-id="7d25d-511">Microsoft Edge Update で使用するプロキシ サーバーの URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-511">Allows you to specify the URL of the proxy server for Microsoft Edge Update to use.</span></span>

  <span data-ttu-id="7d25d-512">このポリシーを有効にした場合、組織内の Microsoft Edge Update が使用するプロキシ サーバーの URL を設定できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-512">If you enable this policy, you can set the proxy server URL used by Microsoft Edge Update in your organization.</span></span>

  <span data-ttu-id="7d25d-513">このポリシーは、 '[プロキシサーバー設定の指定方法を選択する](#proxymode)' ポリシーで手動プロキシ設定を指定した場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-513">This policy is applied only if you have selected manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="7d25d-514">'[プロキシ サーバーの設定をどのように指定するかを選択する](#proxymode)'ポリシーで手動以外のプロキシ設定を選択した場合は、このポリシーを構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="7d25d-514">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="7d25d-515">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-515">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-516">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-516">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-517">GP 固有の名前: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="7d25d-517">GP unique name: ProxyServer</span></span>
- <span data-ttu-id="7d25d-518">GP の名前: プロキシ サーバーのアドレスまたは URL</span><span class="sxs-lookup"><span data-stu-id="7d25d-518">GP name: Address or URL of proxy server</span></span>
- <span data-ttu-id="7d25d-519">GP パス: 管理用テンプレート/Microsoft Edge Update/プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="7d25d-519">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="7d25d-520">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-520">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-521">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-521">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-522">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-522">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-523">値の名前: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="7d25d-523">Value Name: ProxyServer</span></span>
- <span data-ttu-id="7d25d-524">値の種類: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7d25d-524">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="7d25d-525">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-525">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="7d25d-526">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-526">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="7d25d-527">Microsoft Edge WebView に関するポリシー</span><span class="sxs-lookup"><span data-stu-id="7d25d-527">Microsoft Edge WebView policies</span></span>

[<span data-ttu-id="7d25d-528">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-528">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="7d25d-529">インストール (WebView)</span><span class="sxs-lookup"><span data-stu-id="7d25d-529">Install (WebView)</span></span>
#### <span data-ttu-id="7d25d-530">インストールを許可する</span><span class="sxs-lookup"><span data-stu-id="7d25d-530">Allow installation</span></span>
><span data-ttu-id="7d25d-531">Microsoft Edge Update 1.3.127.1 以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-531">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <span data-ttu-id="7d25d-532">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-532">Description</span></span>
<span data-ttu-id="7d25d-533">Microsoft Edge Update を使用して Microsoft Edge WebView をインストールできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="7d25d-533">Lets you specify whether Microsoft Edge WebView can be installed using Microsoft Edge Update.</span></span>

  - <span data-ttu-id="7d25d-534">このポリシーを有効にした場合、ユーザーは Microsoft Edge Update を使用して、Microsoft Edge WebView をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-534">If you enable this policy, users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="7d25d-535">このポリシーを無効にした場合、ユーザーは Microsoft Edge Update を使用して Microsoft Edge WebView をインストールできません。</span><span class="sxs-lookup"><span data-stu-id="7d25d-535">If you disable this policy, users cannot install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="7d25d-536">このポリシーを構成しなかった場合、"[インストールの既定の動作を許可する](#installdefault)" ポリシーの構成に従って、ユーザーが Microsoft Edge Update を使用して Microsoft Edge WebView をインストールできるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="7d25d-536">If you don't configure this policy, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
#### <span data-ttu-id="7d25d-537">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-537">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-538">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-538">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-539">GP 固有の名前: Install</span><span class="sxs-lookup"><span data-stu-id="7d25d-539">GP unique name: Install</span></span>
- <span data-ttu-id="7d25d-540">GP の名前: インストールを許可する</span><span class="sxs-lookup"><span data-stu-id="7d25d-540">GP name: Allow installation</span></span>
- <span data-ttu-id="7d25d-541">GP パス: 管理用テンプレート/Microsoft Edge Update/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="7d25d-541">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="7d25d-542">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-542">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-543">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-543">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-544">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-544">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-545">キーの値: </span><span class="sxs-lookup"><span data-stu-id="7d25d-545">Value Name:</span></span> 
  - <span data-ttu-id="7d25d-546">Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="7d25d-546">Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="7d25d-547">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7d25d-547">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7d25d-548">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-548">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7d25d-549">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-549">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7d25d-550">更新 (WebView)</span><span class="sxs-lookup"><span data-stu-id="7d25d-550">Update (WebView)</span></span>
#### <span data-ttu-id="7d25d-551">更新ポリシーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="7d25d-551">Update policy override</span></span>
><span data-ttu-id="7d25d-552">Microsoft Edge Update 1.3.127.1 以降</span><span class="sxs-lookup"><span data-stu-id="7d25d-552">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <span data-ttu-id="7d25d-553">説明</span><span class="sxs-lookup"><span data-stu-id="7d25d-553">Description</span></span>
<span data-ttu-id="7d25d-554">Microsoft Edge WebView の自動更新を有効にするかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-554">Lets you specify whether or not automatic updates are enabled for Microsoft Edge WebView.</span></span> <span data-ttu-id="7d25d-555">Microsoft Edge WebView は、アプリケーションが Web コンテンツを表示するために使用するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="7d25d-555">Microsoft Edge WebView is a component used by applications to display web content.</span></span>
<span data-ttu-id="7d25d-556">自動更新は、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="7d25d-556">Automatic updates are enabled by default.</span></span> <span data-ttu-id="7d25d-557">Microsoft Edge WebView の自動更新を無効にすると、このコンポーネントに依存するアプリケーションで互換性の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d25d-557">Disabling automatic updates for Microsoft Edge WebView might cause compatibility issues with applications that depend on this component.</span></span>

  <span data-ttu-id="7d25d-558">このポリシーを有効にした場合、Microsoft Edge Update では、以下のオプションの構成方法に従って Microsoft Edge WebView の更新プログラムを処理します。</span><span class="sxs-lookup"><span data-stu-id="7d25d-558">If you enable this policy, Microsoft Edge Update handles Microsoft Edge WebView updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="7d25d-559">[常に更新プログラムを許可する]: 更新プログラムは自動的にダウンロードされ、適用されるます</span><span class="sxs-lookup"><span data-stu-id="7d25d-559">Always allow updates: Updates are automatically downloaded and applied</span></span>
  - <span data-ttu-id="7d25d-560">[更新を無効にする]: 更新プログラムはダウンロードまたは適用されません</span><span class="sxs-lookup"><span data-stu-id="7d25d-560">Updates disabled: Updates are never downloaded or applied</span></span>

  <span data-ttu-id="7d25d-561">このポリシーを有効にしないと、更新プログラムが自動的にダウンロードされ、適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d25d-561">If you don't enable this policy, updates are automatically downloaded and applied.</span></span>
#### <span data-ttu-id="7d25d-562">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-562">Windows information and settings</span></span>
##### <span data-ttu-id="7d25d-563">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="7d25d-563">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7d25d-564">GP 固有の名前: Update</span><span class="sxs-lookup"><span data-stu-id="7d25d-564">GP unique name: Update</span></span>
- <span data-ttu-id="7d25d-565">GP の名前: 更新ポリシーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="7d25d-565">GP name: Update policy override</span></span>
- <span data-ttu-id="7d25d-566">GP パス: 管理用テンプレート/Microsoft Edge Update/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="7d25d-566">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="7d25d-567">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7d25d-567">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7d25d-568">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="7d25d-568">Windows Registry Settings</span></span>
- <span data-ttu-id="7d25d-569">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7d25d-569">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7d25d-570">キーの値: </span><span class="sxs-lookup"><span data-stu-id="7d25d-570">Value Name:</span></span> 
  - <span data-ttu-id="7d25d-571">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="7d25d-571">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="7d25d-572">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7d25d-572">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7d25d-573">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="7d25d-573">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7d25d-574">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="7d25d-574">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="7d25d-575">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d25d-575">See also</span></span>
  - [<span data-ttu-id="7d25d-576">Microsoft Edge の構成</span><span class="sxs-lookup"><span data-stu-id="7d25d-576">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
  - [<span data-ttu-id="7d25d-577">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="7d25d-577">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)