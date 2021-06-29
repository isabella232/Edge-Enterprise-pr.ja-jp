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
ms.openlocfilehash: 921a95c0a5e80ba08fa745748ffa8b0da714ea7d
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617887"
---
# <a name="microsoft-edge---update-policies"></a><span data-ttu-id="64385-103">Microsoft Edge - 更新ポリシー</span><span class="sxs-lookup"><span data-stu-id="64385-103">Microsoft Edge - Update policies</span></span>

<span data-ttu-id="64385-104">最新バージョンの Microsoft Edge には、Microsoft Edge をいつどのように更新するかを制御するために使用できる以下のポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="64385-104">The latest version of Microsoft Edge includes the following policies that you can use to control how and when Microsoft Edge is updated.</span></span>

<span data-ttu-id="64385-105">Microsoft Edge で使用できるその他のポリシーについて詳しくは、[Microsoft Edge ブラウザー ポリシー リファレンス](microsoft-edge-policies.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64385-105">For information about other policies available in Microsoft Edge, check out [Microsoft Edge browser policy reference](microsoft-edge-policies.md)</span></span>
> [!NOTE]
> <span data-ttu-id="64385-106">この記事は、Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="64385-106">This article applies to Microsoft Edge version 77 or later.</span></span>
## <a name="available-policies"></a><span data-ttu-id="64385-107">使用可能なポリシー</span><span class="sxs-lookup"><span data-stu-id="64385-107">Available policies</span></span>
<span data-ttu-id="64385-108">次の表は、このリリースの Microsoft Edge で使用可能な、更新関連のすべてのグループ ポリシーの一覧を示しています。</span><span class="sxs-lookup"><span data-stu-id="64385-108">These tables lists all of the update-related group policies available in this release of Microsoft Edge.</span></span> <span data-ttu-id="64385-109">個々のポリシーに関する詳しい情報を取得するには、表内のリンクをお使いください。</span><span class="sxs-lookup"><span data-stu-id="64385-109">Use the links in the table to get more details about specific policies.</span></span>

<span data-ttu-id="64385-110">|&nbsp;|&nbsp;| |**-**|-| |**[アプリケーション](#applications)** |[基本設定](#preferences)| |**[プロキシ サーバー](#proxy-server)** |[Microsoft Edge WebView](#microsoft-edge-webview)|</span><span class="sxs-lookup"><span data-stu-id="64385-110">|&nbsp;|&nbsp;| |**-**|-| |**[Applications](#applications)**|[Preferences](#preferences)| |**[Proxy Server](#proxy-server)**|[Microsoft Edge WebView](#microsoft-edge-webview)|</span></span>
### [<a name="applications"></a><span data-ttu-id="64385-111">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="64385-111">Applications</span></span>](#applications-policies)
|<span data-ttu-id="64385-112">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="64385-112">Policy Name</span></span>|<span data-ttu-id="64385-113">キャプション</span><span class="sxs-lookup"><span data-stu-id="64385-113">Caption</span></span>|
|-|-|
|[<span data-ttu-id="64385-114">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="64385-114">InstallDefault</span></span>](#installdefault)|<span data-ttu-id="64385-115">インストールの既定の動作を許可する</span><span class="sxs-lookup"><span data-stu-id="64385-115">Allow installation default</span></span>|
|[<span data-ttu-id="64385-116">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="64385-116">UpdateDefault</span></span>](#updatedefault)|<span data-ttu-id="64385-117">更新ポリシーのオーバーライドの既定値</span><span class="sxs-lookup"><span data-stu-id="64385-117">Update policy override default</span></span>|
|[<span data-ttu-id="64385-118">Install</span><span class="sxs-lookup"><span data-stu-id="64385-118">Install</span></span>](#install)|<span data-ttu-id="64385-119">インストールを許可する (チャネルごと)</span><span class="sxs-lookup"><span data-stu-id="64385-119">Allow installation (per channel)</span></span>|
|[<span data-ttu-id="64385-120">Update</span><span class="sxs-lookup"><span data-stu-id="64385-120">Update</span></span>](#update)|<span data-ttu-id="64385-121">更新ポリシーのオーバーライド (チャネルごと)</span><span class="sxs-lookup"><span data-stu-id="64385-121">Update policy override (per channel)</span></span>|
|[<span data-ttu-id="64385-122">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="64385-122">Allowsxs</span></span>](#allowsxs)|<span data-ttu-id="64385-123">Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する</span><span class="sxs-lookup"><span data-stu-id="64385-123">Allow Microsoft Edge Side by Side browser experience</span></span>|
|[<span data-ttu-id="64385-124">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="64385-124">CreateDesktopShortcutDefault</span></span>](#createdesktopshortcutdefault)|<span data-ttu-id="64385-125">既定値のインストール時にデスクトップへのショートカットの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="64385-125">Prevent Desktop Shortcut creation upon install default</span></span>|
|[<span data-ttu-id="64385-126">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="64385-126">CreateDesktopShortcut</span></span>](#createdesktopshortcut)|<span data-ttu-id="64385-127">インストール時にデスクトップへのショートカットの作成を禁止する (チャネル単位)</span><span class="sxs-lookup"><span data-stu-id="64385-127">Prevent Desktop Shortcut creation upon install (per channel)</span></span>|
|[<span data-ttu-id="64385-128">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="64385-128">RollbackToTargetVersion</span></span>](#rollbacktotargetversion)|<span data-ttu-id="64385-129">ターゲットバージョンにロールバック (チャネル単位)</span><span class="sxs-lookup"><span data-stu-id="64385-129">Rollback to Target version (per channel)</span></span>|
|[<span data-ttu-id="64385-130">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="64385-130">TargetVersionPrefix</span></span>](#targetversionprefix)|<span data-ttu-id="64385-131">ターゲットバージョンの上書き (チャネルごと) </span><span class="sxs-lookup"><span data-stu-id="64385-131">Target version override (per channel)</span></span>|

### [<a name="preferences"></a><span data-ttu-id="64385-132">基本設定</span><span class="sxs-lookup"><span data-stu-id="64385-132">Preferences</span></span>](#preferences-policies)
|<span data-ttu-id="64385-133">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="64385-133">Policy Name</span></span>|<span data-ttu-id="64385-134">キャプション</span><span class="sxs-lookup"><span data-stu-id="64385-134">Caption</span></span>|
|-|-|
|[<span data-ttu-id="64385-135">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="64385-135">AutoUpdateCheckPeriodMinutes</span></span>](#autoupdatecheckperiodminutes)|<span data-ttu-id="64385-136">自動更新チェック期間のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="64385-136">Auto-update check period override</span></span>|
|[<span data-ttu-id="64385-137">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="64385-137">UpdatesSuppressed</span></span>](#updatessuppressed)|<span data-ttu-id="64385-138">自動更新チェックを停止する 1 日あたりの時間帯</span><span class="sxs-lookup"><span data-stu-id="64385-138">Time period in each day to suppress auto-update check</span></span>|

### [<a name="proxy-server"></a><span data-ttu-id="64385-139">プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="64385-139">Proxy Server</span></span>](#proxy-server-policies)
|<span data-ttu-id="64385-140">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="64385-140">Policy Name</span></span>|<span data-ttu-id="64385-141">キャプション</span><span class="sxs-lookup"><span data-stu-id="64385-141">Caption</span></span>|
|-|-|
|[<span data-ttu-id="64385-142">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="64385-142">ProxyMode</span></span>](#proxymode)|<span data-ttu-id="64385-143">プロキシ サーバーの設定をどのように指定するかを選択する</span><span class="sxs-lookup"><span data-stu-id="64385-143">Choose how to specify proxy server settings</span></span>|
|[<span data-ttu-id="64385-144">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="64385-144">ProxyPacUrl</span></span>](#proxypacurl)|<span data-ttu-id="64385-145">プロキシ .pac ファイルへの URL</span><span class="sxs-lookup"><span data-stu-id="64385-145">URL to a proxy .pac file</span></span>|
|[<span data-ttu-id="64385-146">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="64385-146">ProxyServer</span></span>](#proxyserver)|<span data-ttu-id="64385-147">プロキシ サーバーのアドレスまたは URL</span><span class="sxs-lookup"><span data-stu-id="64385-147">Address or URL of proxy server</span></span>|

### [<a name="microsoft-edge-webview"></a><span data-ttu-id="64385-148">Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="64385-148">Microsoft Edge WebView</span></span>](#microsoft-edge-webview-policies)
|<span data-ttu-id="64385-149">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="64385-149">Policy Name</span></span>|<span data-ttu-id="64385-150">キャプション</span><span class="sxs-lookup"><span data-stu-id="64385-150">Caption</span></span>|
|-|-|
|[<span data-ttu-id="64385-151">Install</span><span class="sxs-lookup"><span data-stu-id="64385-151">Install</span></span>](#install-webview)|<span data-ttu-id="64385-152">インストールを許可する</span><span class="sxs-lookup"><span data-stu-id="64385-152">Allow installation</span></span>|
|[<span data-ttu-id="64385-153">更新</span><span class="sxs-lookup"><span data-stu-id="64385-153">Update</span></span>](#update-webview)|<span data-ttu-id="64385-154">更新ポリシーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="64385-154">Update policy override</span></span>|

## <a name="applications-policies"></a><span data-ttu-id="64385-155">アプリケーションに関するポリシー</span><span class="sxs-lookup"><span data-stu-id="64385-155">Applications policies</span></span>

[<span data-ttu-id="64385-156">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-156">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="installdefault"></a><span data-ttu-id="64385-157">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="64385-157">InstallDefault</span></span>
#### <a name="allow-installation-default"></a><span data-ttu-id="64385-158">インストールの既定の動作を許可する</span><span class="sxs-lookup"><span data-stu-id="64385-158">Allow installation default</span></span>
><span data-ttu-id="64385-159">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="64385-159">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-160">説明</span><span class="sxs-lookup"><span data-stu-id="64385-160">Description</span></span>
<span data-ttu-id="64385-161">すべてのチャネルに既定の動作を指定して、ドメインに参加しているデバイスで Microsoft Edge を許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="64385-161">You can specify the default behavior of all channels to allow or block Microsoft Edge on domain-joined devices.</span></span>

<span data-ttu-id="64385-162">特定のチャネルの['インストールを許可する'](#install)ポリシーを有効にすることで、チャネルごとにポリシーを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="64385-162">You can override this policy for individual channels by enabling the '[Allow installation](#install)' policy for specific channels.</span></span>

<span data-ttu-id="64385-163">このポリシーを無効にすると、Microsoft Edge のインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="64385-163">If you disable this policy, the installation of Microsoft Edge is blocked.</span></span> <span data-ttu-id="64385-164">これは、[[インストールの許可](#install)] ポリシーが未構成に設定されている場合は、Microsoft Edge ソフトウェアのインストールにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="64385-164">This only affects the installation of Microsoft Edge software when the '[Allow installation](#install)' policy is set to Not Configured.</span></span>

<span data-ttu-id="64385-165">このポリシーによって、Microsoft Edge Update の実行は禁止されません。また、ユーザーが Microsoft Edge ソフトウェアを他の方法を使用してインストールすることも禁止されません。</span><span class="sxs-lookup"><span data-stu-id="64385-165">This policy doesn't prevent Microsoft Edge Update from running or prevent users from installing Microsoft Edge software using other methods.</span></span>

<span data-ttu-id="64385-166">このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="64385-166">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-167">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-167">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-168">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-168">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-169">GP 固有の名前: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="64385-169">GP unique name: InstallDefault</span></span>
- <span data-ttu-id="64385-170">GP の名前: インストールの既定の動作を許可する</span><span class="sxs-lookup"><span data-stu-id="64385-170">GP name: Allow installation default</span></span>
- <span data-ttu-id="64385-171">GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション</span><span class="sxs-lookup"><span data-stu-id="64385-171">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="64385-172">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-172">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-173">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-173">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-174">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-174">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-175">値の名前: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="64385-175">Value Name: InstallDefault</span></span>
- <span data-ttu-id="64385-176">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="64385-176">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-177">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-177">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="64385-178">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-178">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="updatedefault"></a><span data-ttu-id="64385-179">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="64385-179">UpdateDefault</span></span>
#### <a name="update-policy-override-default"></a><span data-ttu-id="64385-180">更新ポリシーのオーバーライドの既定値</span><span class="sxs-lookup"><span data-stu-id="64385-180">Update policy override default</span></span>
><span data-ttu-id="64385-181">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="64385-181">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-182">説明</span><span class="sxs-lookup"><span data-stu-id="64385-182">Description</span></span>
<span data-ttu-id="64385-183">Microsoft Edge で利用できる更新プログラムを Microsoft Edge Update で処理する方法について、すべてのチャネルを対象とした既定の動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="64385-183">Lets you specify the default behavior for all channels concerning the way Microsoft Edge Update handles available updates for Microsoft Edge.</span></span> <span data-ttu-id="64385-184">特定のチャネルに対して['更新ポリシーの上書き'](#update) ポリシーを指定することにより、個々のチャネルに対して上書きできます。</span><span class="sxs-lookup"><span data-stu-id="64385-184">Can be overridden for individual channels by specifying the '[Update policy override](#update)' policy for those specific channels.</span></span>

  <span data-ttu-id="64385-185">このポリシーを有効にした場合、Microsoft Edge Update では、以下のオプションの構成方法に従って Microsoft Edge の更新プログラムを処理します。</span><span class="sxs-lookup"><span data-stu-id="64385-185">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="64385-186">常に更新を許可する: 定期的な更新チェックまたは手動更新チェックで検出された場合に、更新プログラムを必ず適用します。</span><span class="sxs-lookup"><span data-stu-id="64385-186">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="64385-187">自動サイレント更新のみ: 更新プログラムは、定期的な更新チェックで検出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="64385-187">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="64385-188">手動更新のみ: 更新プログラムは、ユーザーが実行した手動更新チェックで検出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="64385-188">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span>
   - <span data-ttu-id="64385-189">更新を無効にする: 更新プログラムは適用されません。</span><span class="sxs-lookup"><span data-stu-id="64385-189">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="64385-190">手動更新を選択した場合は、アプリの手動更新メカニズムを使用して、必ず定期的に更新プログラムをチェックしてください (手動更新メカニズムが利用できる場合)。</span><span class="sxs-lookup"><span data-stu-id="64385-190">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="64385-191">更新を無効にした場合は、定期的に更新プログラムをチェックして、ユーザーに配布してください。</span><span class="sxs-lookup"><span data-stu-id="64385-191">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="64385-192">このポリシーを有効にして構成しない場合、Microsoft Edge Update は、['更新ポリシーの上書き'](#update) ポリシーで指定された使用可能な更新を処理します。</span><span class="sxs-lookup"><span data-stu-id="64385-192">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override](#update)' policy.</span></span>

  <span data-ttu-id="64385-193">このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="64385-193">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-194">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-194">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-195">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-195">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-196">GP 固有の名前: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="64385-196">GP unique name: UpdateDefault</span></span>
- <span data-ttu-id="64385-197">GP の名前: 更新ポリシーのオーバーライドの既定値</span><span class="sxs-lookup"><span data-stu-id="64385-197">GP name: Update policy override default</span></span>
- <span data-ttu-id="64385-198">GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション</span><span class="sxs-lookup"><span data-stu-id="64385-198">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="64385-199">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-199">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-200">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-200">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-201">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-201">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-202">値の名前: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="64385-202">Value Name: UpdateDefault</span></span>
- <span data-ttu-id="64385-203">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="64385-203">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-204">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-204">Example value:</span></span>
```
0x00000003
```
[<span data-ttu-id="64385-205">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-205">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="install"></a><span data-ttu-id="64385-206">Install</span><span class="sxs-lookup"><span data-stu-id="64385-206">Install</span></span>
#### <a name="allow-installation"></a><span data-ttu-id="64385-207">インストールを許可する</span><span class="sxs-lookup"><span data-stu-id="64385-207">Allow installation</span></span>
><span data-ttu-id="64385-208">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="64385-208">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-209">説明</span><span class="sxs-lookup"><span data-stu-id="64385-209">Description</span></span>
<span data-ttu-id="64385-210">ドメインに参加しているデバイスに Microsoft Edge チャネルをインストールできるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="64385-210">Specifies whether a Microsoft Edge channel can be installed on domain-joined devices.</span></span>

  <span data-ttu-id="64385-211">このポリシーをチャネルに対して有効にすると、Microsoft Edge はインストールのブロックをされなくなります。</span><span class="sxs-lookup"><span data-stu-id="64385-211">If you enable this policy for a channel, Microsoft Edge will not be blocked from installation.</span></span>

  <span data-ttu-id="64385-212">チャネルに対してこのポリシーを無効にすると、Microsoft Edge はインストールされなくなります。</span><span class="sxs-lookup"><span data-stu-id="64385-212">If you disable this policy for a channel, Microsoft Edge will be blocked from installation.</span></span>

  <span data-ttu-id="64385-213">チャネルにこのポリシーを構成しない場合、「[インストールの既定の動作を許可する](#installdefault)」 ポリシー構成により、ユーザーがMicrosoft Edge のそのチャネルをインストールできるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="64385-213">If you don't configure this policy for a channel, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install that channel of Microsoft Edge.</span></span>

  <span data-ttu-id="64385-214">このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="64385-214">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-215">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-215">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-216">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-216">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-217">GP 固有の名前: Install</span><span class="sxs-lookup"><span data-stu-id="64385-217">GP unique name: Install</span></span>
- <span data-ttu-id="64385-218">GP の名前: インストールを許可する</span><span class="sxs-lookup"><span data-stu-id="64385-218">GP name: Allow installation</span></span>
- <span data-ttu-id="64385-219">GP パス: </span><span class="sxs-lookup"><span data-stu-id="64385-219">GP path:</span></span> 
  - <span data-ttu-id="64385-220">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="64385-220">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="64385-221">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="64385-221">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="64385-222">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="64385-222">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="64385-223">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="64385-223">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="64385-224">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-224">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-225">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-225">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-226">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-226">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-227">キーの値: </span><span class="sxs-lookup"><span data-stu-id="64385-227">Value Name:</span></span> 
  - <span data-ttu-id="64385-228">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="64385-228">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="64385-229">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="64385-229">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="64385-230">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="64385-230">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="64385-231">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="64385-231">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="64385-232">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="64385-232">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-233">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-233">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="64385-234">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-234">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="update"></a><span data-ttu-id="64385-235">Update</span><span class="sxs-lookup"><span data-stu-id="64385-235">Update</span></span>
#### <a name="update-policy-override"></a><span data-ttu-id="64385-236">更新ポリシーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="64385-236">Update policy override</span></span>
><span data-ttu-id="64385-237">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="64385-237">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-238">説明</span><span class="sxs-lookup"><span data-stu-id="64385-238">Description</span></span>
<span data-ttu-id="64385-239">Microsoft Edge で利用できる更新プログラムを Microsoft Edge Update でどのように処理するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="64385-239">Specifies how Microsoft Edge Update handles available updates from Microsoft Edge.</span></span>

<span data-ttu-id="64385-240">このポリシーを有効にした場合、Microsoft Edge Update では、以下のオプションの構成方法に従って Microsoft Edge の更新プログラムを処理します。</span><span class="sxs-lookup"><span data-stu-id="64385-240">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="64385-241">常に更新を許可する: 定期的な更新チェックまたは手動更新チェックで検出された場合に、更新プログラムを必ず適用します。</span><span class="sxs-lookup"><span data-stu-id="64385-241">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
  - <span data-ttu-id="64385-242">自動サイレント更新のみ: 更新プログラムは、定期的な更新チェックで検出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="64385-242">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
  - <span data-ttu-id="64385-243">手動更新のみ: 更新プログラムは、ユーザーが実行した手動更新チェックで検出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="64385-243">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span> <span data-ttu-id="64385-244">(アプリによっては、このオプション用のインターフェイスがない場合もあります。)</span><span class="sxs-lookup"><span data-stu-id="64385-244">(Not all apps provide an interface for this option.)</span></span>
  - <span data-ttu-id="64385-245">更新を無効にする: 更新プログラムは適用されません。</span><span class="sxs-lookup"><span data-stu-id="64385-245">Updates disabled: Updates are never applied.</span></span>

<span data-ttu-id="64385-246">手動更新を選択した場合は、アプリの手動更新メカニズムを使用して、必ず定期的に更新プログラムをチェックしてください (手動更新メカニズムが利用できる場合)。</span><span class="sxs-lookup"><span data-stu-id="64385-246">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="64385-247">更新を無効にした場合は、定期的に更新プログラムをチェックして、ユーザーに配布してください。</span><span class="sxs-lookup"><span data-stu-id="64385-247">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

<span data-ttu-id="64385-248">このポリシーを有効にせず、構成しない場合、Microsoft Edge Update は、[「更新ポリシー上書きの既定値」](#updatedefault) ポリシーで指定された使用可能な更新プログラムを処理します。</span><span class="sxs-lookup"><span data-stu-id="64385-248">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override default](#updatedefault)' policy.</span></span>

<span data-ttu-id="64385-249">詳細については、「[https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64385-249">See [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406) for more information.</span></span>

<span data-ttu-id="64385-250">このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="64385-250">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-251">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-251">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-252">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-252">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-253">GP 固有の名前: Update</span><span class="sxs-lookup"><span data-stu-id="64385-253">GP unique name: Update</span></span>
- <span data-ttu-id="64385-254">GP の名前: 更新ポリシーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="64385-254">GP name: Update policy override</span></span>
- <span data-ttu-id="64385-255">GP パス: </span><span class="sxs-lookup"><span data-stu-id="64385-255">GP path:</span></span> 
  - <span data-ttu-id="64385-256">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="64385-256">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="64385-257">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="64385-257">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="64385-258">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="64385-258">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="64385-259">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="64385-259">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="64385-260">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-260">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-261">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-261">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-262">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-262">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-263">値の名前: </span><span class="sxs-lookup"><span data-stu-id="64385-263">Value Name:</span></span> 
  - <span data-ttu-id="64385-264">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="64385-264">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="64385-265">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="64385-265">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="64385-266">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="64385-266">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="64385-267">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="64385-267">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="64385-268">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="64385-268">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-269">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-269">Example value:</span></span>
```
always allow updates 0x00000001
Automatic silent updates only 0x00000003
manual updates only 0x00000002
updates disabled 0x00000000
```
[<span data-ttu-id="64385-270">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-270">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="allowsxs"></a><span data-ttu-id="64385-271">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="64385-271">Allowsxs</span></span>
#### <a name="allow-microsoft-edge-side-by-side-browser-experience"></a><span data-ttu-id="64385-272">Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する</span><span class="sxs-lookup"><span data-stu-id="64385-272">Allow Microsoft Edge Side by Side browser experience</span></span>
><span data-ttu-id="64385-273">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="64385-273">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-274">説明</span><span class="sxs-lookup"><span data-stu-id="64385-274">Description</span></span>
<span data-ttu-id="64385-275">このポリシーを使用すると、ユーザーは Microsoft Edge (Edge HTML) と Microsoft Edge (Chromium ベース) を同時に実行できます。</span><span class="sxs-lookup"><span data-stu-id="64385-275">This policy lets a user run Microsoft Edge (Edge HTML) and Microsoft Edge (Chromium-based) side-by-side.</span></span>

<span data-ttu-id="64385-276">このポリシーを "未構成" に設定した場合、Microsoft Edge (Chromium ベース) 安定チャネルと 2019 年 11 月のセキュリティ更新プログラムをインストールすると、Microsoft Edge (Edge HTML) が Microsoft Edge (Chromium ベース) に置き換わります。</span><span class="sxs-lookup"><span data-stu-id="64385-276">If this policy is set to “Not configured”, Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="64385-277">これは、"無効" に設定した場合と同じ動作です。</span><span class="sxs-lookup"><span data-stu-id="64385-277">This is the same behavior as the “Disabled” setting.</span></span>

<span data-ttu-id="64385-278">"無効" に設定した場合、同時実行エクスペリエンスがブロックされ、Microsoft Edge (Chromium ベース) 安定チャネルと 2019 年 11 月のセキュリティ更新プログラムをインストールすると、Microsoft Edge (Edge HTML) が Microsoft Edge (Chromium ベース) に置き換わります。</span><span class="sxs-lookup"><span data-stu-id="64385-278">The “Disabled” setting blocks a side-by-side experience and Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="64385-279">これは、"未構成" に設定した場合と同じ動作です。</span><span class="sxs-lookup"><span data-stu-id="64385-279">This is the same behavior as the “Not Configured” setting.</span></span>

<span data-ttu-id="64385-280">このポリシーを "有効" に設定した場合、Microsoft Edge (Chromium ベース) をインストールすると、Microsoft Edge (Chromium ベース) と Microsoft Edge (Edge HTML) を同時に実行できます。</span><span class="sxs-lookup"><span data-stu-id="64385-280">When this policy is “Enabled”, Microsoft Edge (Chromium-based) and Microsoft Edge (Edge HTML) can run side-by-side after Microsoft Edge (Chromium-based) is installed.</span></span>

<span data-ttu-id="64385-281">このグループ ポリシーを有効するには、Windows Update による Microsoft Edge (Chromium ベース) の自動インストールが行われる前に、ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64385-281">For this group policy to take affect, it must be configured before the automatic install of Microsoft Edge (Chromium-based) by Windows Update.</span></span> <span data-ttu-id="64385-282">注意: ユーザーは、Microsoft Edge (Chromium ベース) Blocker Toolkit を使用して、Microsoft Edge (Chromium ベース) の自動更新をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="64385-282">Note: A user can block the automatic update of Microsoft Edge (Chromium-based) by using the Microsoft Edge (Chromium-based) Blocker Toolkit.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-283">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-283">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-284">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-284">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-285">GP 固有の名前: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="64385-285">GP unique name: Allowsxs</span></span>
- <span data-ttu-id="64385-286">GP の名前: Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する</span><span class="sxs-lookup"><span data-stu-id="64385-286">GP name: Allow Microsoft Edge Side by Side browser experience</span></span>
- <span data-ttu-id="64385-287">GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション</span><span class="sxs-lookup"><span data-stu-id="64385-287">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="64385-288">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-288">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-289">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-289">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-290">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-290">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-291">値の名前: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="64385-291">Value Name: Allowsxs</span></span>
- <span data-ttu-id="64385-292">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="64385-292">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-293">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-293">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="64385-294">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-294">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="createdesktopshortcutdefault"></a><span data-ttu-id="64385-295">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="64385-295">CreateDesktopShortcutDefault</span></span>
#### <a name="prevent-desktop-shortcut-creation-upon-install-default"></a><span data-ttu-id="64385-296">既定値のインストール時にデスクトップへのショートカットの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="64385-296">Prevent Desktop Shortcut creation upon install default</span></span>
><span data-ttu-id="64385-297">Microsoft Edge Update 1.3.128.0 以降</span><span class="sxs-lookup"><span data-stu-id="64385-297">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-298">説明</span><span class="sxs-lookup"><span data-stu-id="64385-298">Description</span></span>
<span data-ttu-id="64385-299">Microsoft Edge がインストールされている場合に、デスクトップにショートカットを作成するすべてのチャネルに対する既定の動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="64385-299">Lets you specify the default behavior for all channels for creating a desktop shortcut when Microsoft Edge is installed.</span></span>

  <span data-ttu-id="64385-300">このポリシーを有効にすると、Microsoft Edge がインストールされている場合、デスクトップにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="64385-300">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="64385-301">このポリシーを無効にすると、Microsoft Edge インストールされていても、デスクトップにショートカットは作成されません。</span><span class="sxs-lookup"><span data-stu-id="64385-301">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="64385-302">このポリシーを構成していない場合は、インストール中に Microsoft Edge のデスクトップにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="64385-302">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="64385-303">Microsoft Edge が既にインストールされている場合、このポリシーの効果はありません。</span><span class="sxs-lookup"><span data-stu-id="64385-303">If Microsoft Edge is already installed, this policy will have no effect.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-304">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-304">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-305">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-305">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-306">GP 固有の名前: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="64385-306">GP unique name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="64385-307">GP の名前: 既定値のインストール時にデスクトップへのショートカットの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="64385-307">GP name: Prevent Desktop Shortcut creation upon install default</span></span>
- <span data-ttu-id="64385-308">GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション</span><span class="sxs-lookup"><span data-stu-id="64385-308">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="64385-309">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-309">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-310">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-310">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-311">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-311">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-312">値の名前: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="64385-312">Value Name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="64385-313">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="64385-313">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-314">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-314">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="64385-315">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-315">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="createdesktopshortcut"></a><span data-ttu-id="64385-316">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="64385-316">CreateDesktopShortcut</span></span>
#### <a name="prevent-desktop-shortcut-creation-upon-install"></a><span data-ttu-id="64385-317">インストール時にデスクトップへのショートカットの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="64385-317">Prevent Desktop Shortcut creation upon install</span></span>
><span data-ttu-id="64385-318">Microsoft Edge Update 1.3.128.0 以降</span><span class="sxs-lookup"><span data-stu-id="64385-318">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-319">説明</span><span class="sxs-lookup"><span data-stu-id="64385-319">Description</span></span>
<span data-ttu-id="64385-320">このポリシーを有効にすると、Microsoft Edge がインストールされている場合、デスクトップにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="64385-320">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="64385-321">このポリシーを無効にすると、Microsoft Edge インストールされていても、デスクトップにショートカットは作成されません。</span><span class="sxs-lookup"><span data-stu-id="64385-321">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="64385-322">このポリシーを構成していない場合は、インストール中に Microsoft Edge のデスクトップにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="64385-322">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="64385-323">Microsoft Edge が既にインストールされている場合、このポリシーの効果はありません。</span><span class="sxs-lookup"><span data-stu-id="64385-323">If Microsoft Edge is already installed, this policy will have no effect.</span></span>

  <span data-ttu-id="64385-324">チャネルにこのポリシーを構成しない場合、「[インストール時にデスクトップショートカットを作成しない](#createdesktopshortcutdefault)」ポリシー構成により、Microsoft Edge のインストール時にショートカットの作成が決まります。</span><span class="sxs-lookup"><span data-stu-id="64385-324">If you don't configure this policy for a channel, the '[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)' policy configuration determines shortcut creation when Microsoft Edge is installed.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-325">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-325">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-326">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-326">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-327">GP 固有の名前: CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="64385-327">GP unique name: CreateDesktopShortcut</span></span>
- <span data-ttu-id="64385-328">GP の名前: インストール時にデスクトップへのショートカットの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="64385-328">GP name: Prevent Desktop Shortcut creation upon install</span></span>
- <span data-ttu-id="64385-329">GP パス: </span><span class="sxs-lookup"><span data-stu-id="64385-329">GP path:</span></span> 
  - <span data-ttu-id="64385-330">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="64385-330">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="64385-331">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="64385-331">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="64385-332">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="64385-332">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="64385-333">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="64385-333">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="64385-334">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-334">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-335">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-335">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-336">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-336">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-337">キーの値: </span><span class="sxs-lookup"><span data-stu-id="64385-337">Value Name:</span></span> 
  - <span data-ttu-id="64385-338">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="64385-338">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="64385-339">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="64385-339">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="64385-340">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="64385-340">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="64385-341">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="64385-341">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="64385-342">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="64385-342">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-343">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-343">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="64385-344">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-344">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="rollbacktotargetversion"></a><span data-ttu-id="64385-345">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="64385-345">RollbackToTargetVersion</span></span>
#### <a name="rollback-to-target-version"></a><span data-ttu-id="64385-346">ターゲットバージョンにロールバックする</span><span class="sxs-lookup"><span data-stu-id="64385-346">Rollback to Target version</span></span>
><span data-ttu-id="64385-347">Microsoft Edge Update 1.3.133.3以降</span><span class="sxs-lookup"><span data-stu-id="64385-347">Microsoft Edge Update 1.3.133.3 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-348">説明</span><span class="sxs-lookup"><span data-stu-id="64385-348">Description</span></span>
<span data-ttu-id="64385-349">Microsoft Edge の更新プログラムで、Microsoft Edge のインストールを '[ターゲットバージョンの上書き](#targetversionprefix)' で指定されたバージョンにロールバックするように指定します。</span><span class="sxs-lookup"><span data-stu-id="64385-349">Specifies that Microsoft Edge Update should rollback installations of Microsoft Edge to the version indicated in '[Target version override](#targetversionprefix)'.</span></span>

<span data-ttu-id="64385-350">このポリシーは、[[ターゲットバージョンが上書きする]](#targetversionprefix)' が設定されていて、[[更新ポリシーの上書き]](#update)' がオン状態のいずれかに設定されている場合を除き (常に更新プログラム、自動サイレント更新のみ、手動更新のみを許可します)何も影響がありません。</span><span class="sxs-lookup"><span data-stu-id="64385-350">This policy has no effect unless '[Target version override](#targetversionprefix)' is set and '[Update policy override](#update)' is set to one of the ON states (Always allow updates, Automatic silent updates only, Manual updates only).</span></span>

<span data-ttu-id="64385-351">このポリシーを無効にした場合、または構成しなかった場合、'[ターゲットバージョンの上書き](#targetversionprefix)' で指定されているバージョンよりも高いバージョンにするようなインストールは変化せずそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="64385-351">If you disable this policy or don't configure it, installs that have a version higher than that specified by '[Target version override](#targetversionprefix)' will be left as-is.</span></span>

<span data-ttu-id="64385-352">このポリシーを有効にした場合、["ターゲットバージョンの上書き](#targetversionprefix)" によって指定されたよりも高いバージョンにするようなインストールは、ターゲットバージョンにダウングレードされます。</span><span class="sxs-lookup"><span data-stu-id="64385-352">If you enable this policy, installs that have a current version higher than specified by the '[Target version override](#targetversionprefix)' will be downgraded to the target version.</span></span>

<span data-ttu-id="64385-353">最新のセキュリティ更新プログラムによる保護機能を使用するには、Microsoft Edge ブラウザーの最新バージョンをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64385-353">We recommend that users install the latest version of the Microsoft Edge browser to ensure protection by the latest security updates.</span></span> <span data-ttu-id="64385-354">以前のバージョンにロールバックすると、既知のセキュリティ問題にさらされるリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="64385-354">Rollback to an earlier version risks exposure to known security issues.</span></span> <span data-ttu-id="64385-355">このポリシーは、Microsoft Edge ブラウザーの更新プログラムの問題に対処するための一時的な修正プログラムとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="64385-355">This policy is meant to be used as a temporary fix to address issues in a Microsoft Edge browser update.</span></span>

<span data-ttu-id="64385-356">ブラウザーのバージョンを一時的にロールバックする前に、組織内のすべてのユーザーの同期 ([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)) を有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64385-356">Before temporarily rolling back your browser version, we recommend that you turn on Sync ([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)) for all users in your organization.</span></span> <span data-ttu-id="64385-357">同期を有効にしない場合、閲覧データが永久に失われる危険性があります。</span><span class="sxs-lookup"><span data-stu-id="64385-357">If you don't turn on Sync, there is a risk of permanent browsing data loss.</span></span> <span data-ttu-id="64385-358">このポリシーは、自己の責任においてご使用ください。</span><span class="sxs-lookup"><span data-stu-id="64385-358">Use this policy at your own risk.</span></span>

<span data-ttu-id="64385-359">注: ロールバック可能なすべてのバージョンは、ここにあります [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise)。</span><span class="sxs-lookup"><span data-stu-id="64385-359">Note: All versions available for rollback can be viewed here [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise).</span></span>

<span data-ttu-id="64385-360">これは、Microsoft Edge バージョン 86以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="64385-360">This policy applies to Microsoft Edge version 86 or later.</span></span>

<span data-ttu-id="64385-361">詳細については、「[https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64385-361">See [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918) for more information.</span></span>

<span data-ttu-id="64385-362">このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="64385-362">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-363">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-363">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-364">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-364">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-365">GP 固有の名前: RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="64385-365">GP unique name: RollbackToTargetVersion</span></span>
- <span data-ttu-id="64385-366">GP 名: ターゲットバージョンにロールバックする</span><span class="sxs-lookup"><span data-stu-id="64385-366">GP name: Rollback to Target version</span></span>
- <span data-ttu-id="64385-367">GP パス: </span><span class="sxs-lookup"><span data-stu-id="64385-367">GP path:</span></span> 
  - <span data-ttu-id="64385-368">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="64385-368">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="64385-369">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="64385-369">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="64385-370">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="64385-370">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="64385-371">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="64385-371">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="64385-372">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-372">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-373">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-373">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-374">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-374">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-375">キーの値: </span><span class="sxs-lookup"><span data-stu-id="64385-375">Value Name:</span></span> 
  - <span data-ttu-id="64385-376">(Stable): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="64385-376">(Stable): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="64385-377">(ベータ): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="64385-377">(Beta): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="64385-378">(カナリア): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="64385-378">(Canary): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="64385-379">(Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="64385-379">(Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="64385-380">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="64385-380">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-381">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-381">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="64385-382">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-382">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="targetversionprefix"></a><span data-ttu-id="64385-383">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="64385-383">TargetVersionPrefix</span></span>
#### <a name="target-version-override"></a><span data-ttu-id="64385-384">ターゲット バージョンの上書き</span><span class="sxs-lookup"><span data-stu-id="64385-384">Target version override</span></span>
><span data-ttu-id="64385-385">Microsoft Edge Update 1.3.119.43 以降</span><span class="sxs-lookup"><span data-stu-id="64385-385">Microsoft Edge Update 1.3.119.43 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-386">説明</span><span class="sxs-lookup"><span data-stu-id="64385-386">Description</span></span>
<span data-ttu-id="64385-387">このポリシーを有効にして自動更新を有効にすると、Microsoft Edge がこのポリシー値で指定されたバージョンに更新されます。</span><span class="sxs-lookup"><span data-stu-id="64385-387">When this policy is enabled, and auto-update is enabled, Microsoft Edge will be updated to the version specified by this policy value.</span></span>

<span data-ttu-id="64385-388">ポリシー値は、83.0.499.12 のような特定の Microsoft Edge バージョンである必要があります。</span><span class="sxs-lookup"><span data-stu-id="64385-388">The policy value must be a specific Microsoft Edge version, e.g. 83.0.499.12.</span></span>

<span data-ttu-id="64385-389">指定した値より新しいバージョンの Microsoft Edge がデバイスにある場合、Microsoft Edge は新しいバージョンのままとなり、指定されたバージョンにダウングレードされません。</span><span class="sxs-lookup"><span data-stu-id="64385-389">If a device has newer version of Microsoft Edge than the value specified, Microsoft Edge will remain on the newer version and not downgrade to the specified version.</span></span>

<span data-ttu-id="64385-390">指定したバージョンが存在しない場合、または正しく書式設定されていない場合は、Microsoft Edge は現在のバージョンにとどまり、将来のバージョンに自動的に更新されません。</span><span class="sxs-lookup"><span data-stu-id="64385-390">If the specified version does not exist, or is improperly formatted, then Microsoft Edge will remain on its current version and not update to future versions automatically.</span></span>

<span data-ttu-id="64385-391">詳細については、「[https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64385-391">See [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707) for more information.</span></span>

<span data-ttu-id="64385-392">このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="64385-392">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-393">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-393">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-394">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-394">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-395">GP 固有の名前: TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="64385-395">GP unique name: TargetVersionPrefix</span></span>
- <span data-ttu-id="64385-396">GP の名前: ターゲット バージョンの上書き</span><span class="sxs-lookup"><span data-stu-id="64385-396">GP name: Target version override</span></span>
- <span data-ttu-id="64385-397">GP パス: </span><span class="sxs-lookup"><span data-stu-id="64385-397">GP path:</span></span> 
  - <span data-ttu-id="64385-398">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="64385-398">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="64385-399">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="64385-399">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="64385-400">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="64385-400">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="64385-401">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="64385-401">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="64385-402">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-402">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-403">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-403">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-404">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-404">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-405">キーの値: </span><span class="sxs-lookup"><span data-stu-id="64385-405">Value Name:</span></span> 
  - <span data-ttu-id="64385-406">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="64385-406">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="64385-407">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="64385-407">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="64385-408">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="64385-408">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="64385-409">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="64385-409">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="64385-410">値の種類: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="64385-410">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-411">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-411">Example value:</span></span>
```
83.0.499.12
```
[<span data-ttu-id="64385-412">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-412">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="preferences-policies"></a><span data-ttu-id="64385-413">基本設定に関するポリシー</span><span class="sxs-lookup"><span data-stu-id="64385-413">Preferences policies</span></span>

[<span data-ttu-id="64385-414">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-414">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="autoupdatecheckperiodminutes"></a><span data-ttu-id="64385-415">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="64385-415">AutoUpdateCheckPeriodMinutes</span></span>
#### <a name="auto-update-check-period-override"></a><span data-ttu-id="64385-416">自動更新チェック期間のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="64385-416">Auto-update check period override</span></span>
><span data-ttu-id="64385-417">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="64385-417">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-418">説明</span><span class="sxs-lookup"><span data-stu-id="64385-418">Description</span></span>
<span data-ttu-id="64385-419">有効にした場合、このポリシーによって、自動更新チェックの最小間隔の値 (分単位) を設定できます。</span><span class="sxs-lookup"><span data-stu-id="64385-419">If enabled, this policy lets you set a value for the minimum number of minutes between automatic update checks.</span></span> <span data-ttu-id="64385-420">有効にしなかった場合、自動更新チェックでは、既定で 10 時間ごとに更新が確認されます。</span><span class="sxs-lookup"><span data-stu-id="64385-420">Otherwise, by default, auto-update checks for updates every 10 hours.</span></span>

  <span data-ttu-id="64385-421">すべての自動更新チェックを無効にする場合は、値を 0 に設定します (推奨しません)。</span><span class="sxs-lookup"><span data-stu-id="64385-421">If you want to disable all auto-update checks, set the value to 0 (not recommended).</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-422">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-422">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-423">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-423">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-424">GP 固有の名前: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="64385-424">GP unique name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="64385-425">GP の名前: 自動更新チェック期間のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="64385-425">GP name: Auto-update check period override</span></span>
- <span data-ttu-id="64385-426">GP パス: 管理用テンプレート/Microsoft Edge Update/基本設定</span><span class="sxs-lookup"><span data-stu-id="64385-426">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="64385-427">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-427">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-428">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-428">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-429">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-429">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-430">値の名前: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="64385-430">Value Name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="64385-431">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="64385-431">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-432">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-432">Example value:</span></span>
```
0x00000578
```
[<span data-ttu-id="64385-433">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-433">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="updatessuppressed"></a><span data-ttu-id="64385-434">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="64385-434">UpdatesSuppressed</span></span>
#### <a name="time-period-in-each-day-to-suppress-auto-update-check"></a><span data-ttu-id="64385-435">自動更新チェックを停止する 1 日あたりの時間帯</span><span class="sxs-lookup"><span data-stu-id="64385-435">Time period in each day to suppress auto-update check</span></span>
><span data-ttu-id="64385-436">Microsoft Edge Update 1.3.33.5 以降</span><span class="sxs-lookup"><span data-stu-id="64385-436">Microsoft Edge Update 1.3.33.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-437">説明</span><span class="sxs-lookup"><span data-stu-id="64385-437">Description</span></span>
<span data-ttu-id="64385-438">このポリシーを有効にした場合、更新チェックは毎日指定の時刻 (時:分) に停止され、一定の期間、更新チェックが行われなくなります (分単位)。</span><span class="sxs-lookup"><span data-stu-id="64385-438">If you enable this policy, update checks are suppressed each day starting at Hour:Minute for a period of Duration (in minutes).</span></span> <span data-ttu-id="64385-439">この期間では夏時間が考慮されません。</span><span class="sxs-lookup"><span data-stu-id="64385-439">Duration isn't affected by daylight saving time.</span></span> <span data-ttu-id="64385-440">たとえば、開始時間が 22:00、期間が 480 分の場合、その期間内で夏時間の開始や終了が発生しても、更新は正確に 8 時間停止されます。</span><span class="sxs-lookup"><span data-stu-id="64385-440">For example, if the start time is 22:00 and the duration is 480 minutes, updates will be suppressed for exactly 8 hours, regardless of whether daylight saving time starts or ends during this period.</span></span>

  <span data-ttu-id="64385-441">このポリシーを無効にした場合または構成しなかった場合、更新チェックが一定期間停止されることはありません。</span><span class="sxs-lookup"><span data-stu-id="64385-441">If you disable or don't configure this policy, update checks aren't suppressed during any specific period.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-442">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-442">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-443">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-443">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-444">GP 固有の名前: UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="64385-444">GP unique name: UpdatesSuppressed</span></span>
- <span data-ttu-id="64385-445">GP の名前: 自動更新チェックを停止する 1 日あたりの時間帯</span><span class="sxs-lookup"><span data-stu-id="64385-445">GP name: Time period in each day to suppress auto-update check</span></span>
  - <span data-ttu-id="64385-446">オプション { Hour, Minute, Duration }</span><span class="sxs-lookup"><span data-stu-id="64385-446">Options { Hour, Minute, Duration }</span></span>
- <span data-ttu-id="64385-447">GP パス: 管理用テンプレート/Microsoft Edge Update/基本設定</span><span class="sxs-lookup"><span data-stu-id="64385-447">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="64385-448">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-448">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-449">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-449">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-450">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-450">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-451">値の名前: </span><span class="sxs-lookup"><span data-stu-id="64385-451">Value Name:</span></span> 
  - <span data-ttu-id="64385-452">UpdatesSuppressedDurationMin</span><span class="sxs-lookup"><span data-stu-id="64385-452">UpdatesSuppressedDurationMin</span></span>
  - <span data-ttu-id="64385-453">UpdatesSuppressedStartHour</span><span class="sxs-lookup"><span data-stu-id="64385-453">UpdatesSuppressedStartHour</span></span>
  - <span data-ttu-id="64385-454">UpdatesSuppressedStartMin</span><span class="sxs-lookup"><span data-stu-id="64385-454">UpdatesSuppressedStartMin</span></span>
- <span data-ttu-id="64385-455">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="64385-455">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-456">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-456">Example value:</span></span>
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[<span data-ttu-id="64385-457">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-457">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="proxy-server-policies"></a><span data-ttu-id="64385-458">プロキシ サーバーに関するポリシー</span><span class="sxs-lookup"><span data-stu-id="64385-458">Proxy Server policies</span></span>

[<span data-ttu-id="64385-459">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-459">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="proxymode"></a><span data-ttu-id="64385-460">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="64385-460">ProxyMode</span></span>
#### <a name="choose-how-to-specify-proxy-server-settings"></a><span data-ttu-id="64385-461">プロキシ サーバーの設定をどのように指定するかを選択する</span><span class="sxs-lookup"><span data-stu-id="64385-461">Choose how to specify proxy server settings</span></span>
><span data-ttu-id="64385-462">Microsoft Edge Update 1.3.21.81 以降</span><span class="sxs-lookup"><span data-stu-id="64385-462">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-463">説明</span><span class="sxs-lookup"><span data-stu-id="64385-463">Description</span></span>
<span data-ttu-id="64385-464">Microsoft Edge Update で使用されるプロキシ サーバーの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="64385-464">Allows you to specify the proxy server settings that are used by Microsoft Edge Update.</span></span>

  <span data-ttu-id="64385-465">このポリシーを有効にした場合、以下のプロキシ サーバーのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="64385-465">If you enable this policy, you can choose between the following proxy server options:</span></span>
   - <span data-ttu-id="64385-466">プロキシ サーバーを使用せず、常に直接接続することを選択した場合、他のオプションはすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="64385-466">If you choose to never use a proxy server and always connect directly, all other options are ignored.</span></span>
   - <span data-ttu-id="64385-467">システム プロキシ設定を使用するか、プロキシ サーバーの自動検出を選択した場合、他のオプションはすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="64385-467">If you choose to use system proxy settings or auto-detect the proxy server, all other options are ignored.</span></span>
   - <span data-ttu-id="64385-468">固定サーバー プロキシ モードを選択した場合、'[プロキシ サーバーのアドレスまたは URL](#proxyserver)' でさらにオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="64385-468">If you choose fixed server proxy mode, you can specify further options in '[Address or URL of proxy server](#proxyserver)' policy.</span></span>
   - <span data-ttu-id="64385-469">.pac プロキシスクリプトを使用する場合は、'[プロキシ .pac ファイルへの URL ](#proxypacurl)' ポリシーでスクリプトの URL を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64385-469">If you choose to use a .pac proxy script, you must specify the URL for the script in '[URL to a proxy .pac file](#proxypacurl)' policy.</span></span>

  <span data-ttu-id="64385-470">このポリシーを有効にした場合、組織内のユーザーは Microsoft Edge Update でプロキシ設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="64385-470">If you enable this policy, users in your organization can't change the proxy settings in Microsoft Edge Update.</span></span>

  <span data-ttu-id="64385-471">このポリシーを無効にした場合または構成しなかった場合、プロキシ サーバーの設定は構成されませんが、組織内のユーザーは Microsoft Edge Update で独自のプロキシ設定を選択できます。</span><span class="sxs-lookup"><span data-stu-id="64385-471">If you disable or don't configure this policy, no proxy server settings are configured, but users in your organization can choose their own proxy settings for Microsoft Edge Update.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-472">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-472">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-473">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-473">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-474">GP 固有の名前: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="64385-474">GP unique name: ProxyMode</span></span>
- <span data-ttu-id="64385-475">GP の名前: プロキシ サーバーの設定をどのように指定するかを選択する</span><span class="sxs-lookup"><span data-stu-id="64385-475">GP name: Choose how to specify proxy server settings</span></span>
- <span data-ttu-id="64385-476">GP パス: 管理用テンプレート/Microsoft Edge Update/プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="64385-476">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="64385-477">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-477">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-478">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-478">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-479">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-479">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-480">値の名前: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="64385-480">Value Name: ProxyMode</span></span>
- <span data-ttu-id="64385-481">値の種類: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="64385-481">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-482">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-482">Example value:</span></span>
```
fixed_servers
```
[<span data-ttu-id="64385-483">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-483">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="proxypacurl"></a><span data-ttu-id="64385-484">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="64385-484">ProxyPacUrl</span></span>
#### <a name="url-to-a-proxy-pac-file"></a><span data-ttu-id="64385-485">プロキシ .pac ファイルへの URL</span><span class="sxs-lookup"><span data-stu-id="64385-485">URL to a proxy .pac file</span></span>
><span data-ttu-id="64385-486">Microsoft Edge Update 1.3.21.81 以降</span><span class="sxs-lookup"><span data-stu-id="64385-486">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-487">説明</span><span class="sxs-lookup"><span data-stu-id="64385-487">Description</span></span>
<span data-ttu-id="64385-488">プロキシ自動構成 (PAC) ファイルの URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="64385-488">Allows you to specify a URL for a proxy auto-config (PAC) file.</span></span>

  <span data-ttu-id="64385-489">このポリシーを有効にした場合、PAC ファイルの URL を指定して、特定の Web サイトを取得するための適切なプロキシサーバーを Microsoft Edge Update で選択する方法を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="64385-489">If you enable this policy, you can specify a URL for a PAC file to automate how Microsoft Edge Update selects the appropriate proxy server for fetching a particular website.</span></span>

  <span data-ttu-id="64385-490">このポリシーは、 '[プロキシサーバー設定の指定方法を選択する](#proxymode)' ポリシーで手動プロキシ設定を指定した場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="64385-490">This policy is applied only if you have specified manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="64385-491">'[プロキシ サーバーの設定をどのように指定するかを選択する](#proxymode)'ポリシーで手動以外のプロキシ設定を選択した場合は、このポリシーを構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="64385-491">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-492">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-492">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-493">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-493">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-494">GP 固有の名前: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="64385-494">GP unique name: ProxyPacUrl</span></span>
- <span data-ttu-id="64385-495">GP の名前: プロキシ .pac ファイルへの URL</span><span class="sxs-lookup"><span data-stu-id="64385-495">GP name: URL to a proxy .pac file</span></span>
- <span data-ttu-id="64385-496">GP パス: 管理用テンプレート/Microsoft Edge Update/プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="64385-496">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="64385-497">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-497">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-498">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-498">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-499">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-499">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-500">値の名前: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="64385-500">Value Name: ProxyPacUrl</span></span>
- <span data-ttu-id="64385-501">値の種類: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="64385-501">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-502">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-502">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="64385-503">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-503">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="proxyserver"></a><span data-ttu-id="64385-504">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="64385-504">ProxyServer</span></span>
#### <a name="address-or-url-of-proxy-server"></a><span data-ttu-id="64385-505">プロキシ サーバーのアドレスまたは URL</span><span class="sxs-lookup"><span data-stu-id="64385-505">Address or URL of proxy server</span></span>
><span data-ttu-id="64385-506">Microsoft Edge Update 1.3.21.81 以降</span><span class="sxs-lookup"><span data-stu-id="64385-506">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-507">説明</span><span class="sxs-lookup"><span data-stu-id="64385-507">Description</span></span>
<span data-ttu-id="64385-508">Microsoft Edge Update で使用するプロキシ サーバーの URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="64385-508">Allows you to specify the URL of the proxy server for Microsoft Edge Update to use.</span></span>

  <span data-ttu-id="64385-509">このポリシーを有効にした場合、組織内の Microsoft Edge Update が使用するプロキシ サーバーの URL を設定できます。</span><span class="sxs-lookup"><span data-stu-id="64385-509">If you enable this policy, you can set the proxy server URL used by Microsoft Edge Update in your organization.</span></span>

  <span data-ttu-id="64385-510">このポリシーは、 '[プロキシサーバー設定の指定方法を選択する](#proxymode)' ポリシーで手動プロキシ設定を指定した場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="64385-510">This policy is applied only if you have selected manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="64385-511">'[プロキシ サーバーの設定をどのように指定するかを選択する](#proxymode)'ポリシーで手動以外のプロキシ設定を選択した場合は、このポリシーを構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="64385-511">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-512">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-512">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-513">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-513">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-514">GP 固有の名前: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="64385-514">GP unique name: ProxyServer</span></span>
- <span data-ttu-id="64385-515">GP の名前: プロキシ サーバーのアドレスまたは URL</span><span class="sxs-lookup"><span data-stu-id="64385-515">GP name: Address or URL of proxy server</span></span>
- <span data-ttu-id="64385-516">GP パス: 管理用テンプレート/Microsoft Edge Update/プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="64385-516">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="64385-517">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-517">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-518">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-518">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-519">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-519">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-520">値の名前: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="64385-520">Value Name: ProxyServer</span></span>
- <span data-ttu-id="64385-521">値の種類: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="64385-521">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-522">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-522">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="64385-523">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-523">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="microsoft-edge-webview-policies"></a><span data-ttu-id="64385-524">Microsoft Edge WebView に関するポリシー</span><span class="sxs-lookup"><span data-stu-id="64385-524">Microsoft Edge WebView policies</span></span>

[<span data-ttu-id="64385-525">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-525">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="install-webview"></a><span data-ttu-id="64385-526">インストール (WebView)</span><span class="sxs-lookup"><span data-stu-id="64385-526">Install (WebView)</span></span>
#### <a name="allow-installation"></a><span data-ttu-id="64385-527">インストールを許可する</span><span class="sxs-lookup"><span data-stu-id="64385-527">Allow installation</span></span>
><span data-ttu-id="64385-528">Microsoft Edge Update 1.3.127.1 以降</span><span class="sxs-lookup"><span data-stu-id="64385-528">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-529">説明</span><span class="sxs-lookup"><span data-stu-id="64385-529">Description</span></span>
<span data-ttu-id="64385-530">Microsoft Edge Update を使用して Microsoft Edge WebView をインストールできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="64385-530">Lets you specify whether Microsoft Edge WebView can be installed using Microsoft Edge Update.</span></span>

  - <span data-ttu-id="64385-531">このポリシーを有効にした場合、ユーザーは Microsoft Edge Update を使用して、Microsoft Edge WebView をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="64385-531">If you enable this policy, users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="64385-532">このポリシーを無効にした場合、ユーザーは Microsoft Edge Update を使用して Microsoft Edge WebView をインストールできません。</span><span class="sxs-lookup"><span data-stu-id="64385-532">If you disable this policy, users cannot install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="64385-533">このポリシーを構成しなかった場合、"[インストールの既定の動作を許可する](#installdefault)" ポリシーの構成に従って、ユーザーが Microsoft Edge Update を使用して Microsoft Edge WebView をインストールできるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="64385-533">If you don't configure this policy, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-534">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-534">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-535">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-535">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-536">GP 固有の名前: Install</span><span class="sxs-lookup"><span data-stu-id="64385-536">GP unique name: Install</span></span>
- <span data-ttu-id="64385-537">GP の名前: インストールを許可する</span><span class="sxs-lookup"><span data-stu-id="64385-537">GP name: Allow installation</span></span>
- <span data-ttu-id="64385-538">GP パス: 管理用テンプレート/Microsoft Edge Update/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="64385-538">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="64385-539">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-539">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-540">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-540">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-541">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-541">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-542">キーの値: </span><span class="sxs-lookup"><span data-stu-id="64385-542">Value Name:</span></span> 
  - <span data-ttu-id="64385-543">Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="64385-543">Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="64385-544">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="64385-544">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-545">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-545">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="64385-546">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-546">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="update-webview"></a><span data-ttu-id="64385-547">更新 (WebView)</span><span class="sxs-lookup"><span data-stu-id="64385-547">Update (WebView)</span></span>
#### <a name="update-policy-override"></a><span data-ttu-id="64385-548">更新ポリシーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="64385-548">Update policy override</span></span>
><span data-ttu-id="64385-549">Microsoft Edge Update 1.3.127.1 以降</span><span class="sxs-lookup"><span data-stu-id="64385-549">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <a name="description"></a><span data-ttu-id="64385-550">説明</span><span class="sxs-lookup"><span data-stu-id="64385-550">Description</span></span>
<span data-ttu-id="64385-551">Microsoft Edge WebView の自動更新を有効にするかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="64385-551">Lets you specify whether or not automatic updates are enabled for Microsoft Edge WebView.</span></span> <span data-ttu-id="64385-552">Microsoft Edge WebView は、アプリケーションが Web コンテンツを表示するために使用するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="64385-552">Microsoft Edge WebView is a component used by applications to display web content.</span></span>
<span data-ttu-id="64385-553">自動更新は、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="64385-553">Automatic updates are enabled by default.</span></span> <span data-ttu-id="64385-554">Microsoft Edge WebView の自動更新を無効にすると、このコンポーネントに依存するアプリケーションで互換性の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64385-554">Disabling automatic updates for Microsoft Edge WebView might cause compatibility issues with applications that depend on this component.</span></span>

  <span data-ttu-id="64385-555">このポリシーを有効にした場合、Microsoft Edge Update では、以下のオプションの構成方法に従って Microsoft Edge WebView の更新プログラムを処理します。</span><span class="sxs-lookup"><span data-stu-id="64385-555">If you enable this policy, Microsoft Edge Update handles Microsoft Edge WebView updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="64385-556">常に更新プログラムを許可する: 更新プログラムは自動的にダウンロードされ、適用されるます</span><span class="sxs-lookup"><span data-stu-id="64385-556">Always allow updates: Updates are automatically downloaded and applied</span></span>
  - <span data-ttu-id="64385-557">更新を無効にする: 更新プログラムはダウンロードまたは適用されません</span><span class="sxs-lookup"><span data-stu-id="64385-557">Updates disabled: Updates are never downloaded or applied</span></span>

  <span data-ttu-id="64385-558">このポリシーを有効にしないと、更新プログラムが自動的にダウンロードされ、適用されます。</span><span class="sxs-lookup"><span data-stu-id="64385-558">If you don't enable this policy, updates are automatically downloaded and applied.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="64385-559">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="64385-559">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="64385-560">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="64385-560">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="64385-561">GP 固有の名前: Update</span><span class="sxs-lookup"><span data-stu-id="64385-561">GP unique name: Update</span></span>
- <span data-ttu-id="64385-562">GP の名前: 更新ポリシーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="64385-562">GP name: Update policy override</span></span>
- <span data-ttu-id="64385-563">GP パス: 管理用テンプレート/Microsoft Edge Update/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="64385-563">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="64385-564">GP ADMX ファイル名:  msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="64385-564">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="64385-565">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="64385-565">Windows Registry Settings</span></span>
- <span data-ttu-id="64385-566">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="64385-566">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="64385-567">キーの値: </span><span class="sxs-lookup"><span data-stu-id="64385-567">Value Name:</span></span> 
  - <span data-ttu-id="64385-568">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="64385-568">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="64385-569">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="64385-569">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="64385-570">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="64385-570">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="64385-571">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="64385-571">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="see-also"></a><span data-ttu-id="64385-572">関連項目</span><span class="sxs-lookup"><span data-stu-id="64385-572">See also</span></span>
  - [<span data-ttu-id="64385-573">Microsoft Edge の構成</span><span class="sxs-lookup"><span data-stu-id="64385-573">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
  - [<span data-ttu-id="64385-574">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="64385-574">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
