---
title: Microsoft Edge Update のポリシーに関するドキュメント
ms.author: stmoody
author: brianalt-msft
manager: tahills
ms.date: 06/10/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge アップデーターでサポートされているすべてのポリシーに関するドキュメント
ms.openlocfilehash: d772d8dd6f60b89e9bd12a77b740e5fad699756a
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980472"
---
# <span data-ttu-id="c80ce-103">Microsoft Edge - 更新ポリシー</span><span class="sxs-lookup"><span data-stu-id="c80ce-103">Microsoft Edge - Update policies</span></span>
<span data-ttu-id="c80ce-104">最新バージョンの Microsoft Edge には、Microsoft Edge をいつどのように更新するかを制御するために使用できる以下のポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c80ce-104">The latest version of Microsoft Edge includes the following policies that you can use to control how and when Microsoft Edge is updated.</span></span>

           
<span data-ttu-id="c80ce-105">Microsoft Edge で使用できるその他のポリシーについて詳しくは、[Microsoft Edge ブラウザー ポリシー リファレンス](microsoft-edge-policies.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c80ce-105">For information about other policies available in Microsoft Edge, check out [Microsoft Edge browser policy reference](microsoft-edge-policies.md)</span></span>
> [!NOTE]
> <span data-ttu-id="c80ce-106">この記事は、Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-106">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="c80ce-107">使用可能なポリシー</span><span class="sxs-lookup"><span data-stu-id="c80ce-107">Available policies</span></span>
<span data-ttu-id="c80ce-108">次の表は、このリリースの Microsoft Edge で使用可能な、更新関連のすべてのグループ ポリシーの一覧を示しています。</span><span class="sxs-lookup"><span data-stu-id="c80ce-108">These tables lists all of the update-related group policies available in this release of Microsoft Edge.</span></span> <span data-ttu-id="c80ce-109">個々のポリシーに関する詳しい情報を取得するには、表内のリンクをお使いください。</span><span class="sxs-lookup"><span data-stu-id="c80ce-109">Use the links in the table to get more details about specific policies.</span></span>

|||
|-|-|
|[<span data-ttu-id="c80ce-110">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c80ce-110">Applications</span></span>](#applications)|[<span data-ttu-id="c80ce-111">基本設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-111">Preferences</span></span>](#preferences)|
|[<span data-ttu-id="c80ce-112">プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="c80ce-112">Proxy Server</span></span>](#proxy-server)||

### [<span data-ttu-id="c80ce-113">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c80ce-113">Applications</span></span>](#applications-policies)
|<span data-ttu-id="c80ce-114">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="c80ce-114">Policy Name</span></span>|<span data-ttu-id="c80ce-115">キャプション</span><span class="sxs-lookup"><span data-stu-id="c80ce-115">Caption</span></span>|
|-|-|
|[<span data-ttu-id="c80ce-116">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="c80ce-116">InstallDefault</span></span>](#installdefault)|<span data-ttu-id="c80ce-117">インストールの既定の動作を許可する</span><span class="sxs-lookup"><span data-stu-id="c80ce-117">Allow installation default</span></span>|
|[<span data-ttu-id="c80ce-118">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="c80ce-118">UpdateDefault</span></span>](#updatedefault)|<span data-ttu-id="c80ce-119">更新ポリシーのオーバーライドの既定値</span><span class="sxs-lookup"><span data-stu-id="c80ce-119">Update policy override default</span></span>|
|[<span data-ttu-id="c80ce-120">Install</span><span class="sxs-lookup"><span data-stu-id="c80ce-120">Install</span></span>](#install)|<span data-ttu-id="c80ce-121">インストールを許可する (チャネルごと)</span><span class="sxs-lookup"><span data-stu-id="c80ce-121">Allow installation (per channel)</span></span>|
|[<span data-ttu-id="c80ce-122">Update</span><span class="sxs-lookup"><span data-stu-id="c80ce-122">Update</span></span>](#update)|<span data-ttu-id="c80ce-123">更新ポリシーのオーバーライド (チャネルごと)</span><span class="sxs-lookup"><span data-stu-id="c80ce-123">Update policy override (per channel)</span></span>|
|[<span data-ttu-id="c80ce-124">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="c80ce-124">Allowsxs</span></span>](#allowsxs)|<span data-ttu-id="c80ce-125">Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する</span><span class="sxs-lookup"><span data-stu-id="c80ce-125">Allow Microsoft Edge Side by Side browser experience</span></span>|
|[<span data-ttu-id="c80ce-126">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="c80ce-126">CreateDesktopShortcutDefault</span></span>](#createdesktopshortcutdefault)|<span data-ttu-id="c80ce-127">既定値のインストール時にデスクトップへのショートカットの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="c80ce-127">Prevent Desktop Shortcut creation upon install default</span></span>|
|[<span data-ttu-id="c80ce-128">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="c80ce-128">CreateDesktopShortcut</span></span>](#createdesktopshortcut)|<span data-ttu-id="c80ce-129">インストール時にデスクトップへのショートカットの作成を禁止する (チャネル単位)</span><span class="sxs-lookup"><span data-stu-id="c80ce-129">Prevent Desktop Shortcut creation upon install (per channel)</span></span>|
|[<span data-ttu-id="c80ce-130">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="c80ce-130">TargetVersionPrefix</span></span>](#targetversionprefix)|<span data-ttu-id="c80ce-131">ターゲットバージョンの上書き (チャネルごと) </span><span class="sxs-lookup"><span data-stu-id="c80ce-131">Target version override (per channel)</span></span>|

### [<span data-ttu-id="c80ce-132">基本設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-132">Preferences</span></span>](#preferences-policies)
|<span data-ttu-id="c80ce-133">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="c80ce-133">Policy Name</span></span>|<span data-ttu-id="c80ce-134">キャプション</span><span class="sxs-lookup"><span data-stu-id="c80ce-134">Caption</span></span>|
|-|-|
|[<span data-ttu-id="c80ce-135">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="c80ce-135">AutoUpdateCheckPeriodMinutes</span></span>](#autoupdatecheckperiodminutes)|<span data-ttu-id="c80ce-136">自動更新チェック期間のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="c80ce-136">Auto-update check period override</span></span>|
|[<span data-ttu-id="c80ce-137">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="c80ce-137">UpdatesSuppressed</span></span>](#updatessuppressed)|<span data-ttu-id="c80ce-138">自動更新チェックを停止する 1 日あたりの時間帯</span><span class="sxs-lookup"><span data-stu-id="c80ce-138">Time period in each day to suppress auto-update check</span></span>|

### [<span data-ttu-id="c80ce-139">プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="c80ce-139">Proxy Server</span></span>](#proxy-server-policies)
|<span data-ttu-id="c80ce-140">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="c80ce-140">Policy Name</span></span>|<span data-ttu-id="c80ce-141">キャプション</span><span class="sxs-lookup"><span data-stu-id="c80ce-141">Caption</span></span>|
|-|-|
|[<span data-ttu-id="c80ce-142">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="c80ce-142">ProxyMode</span></span>](#proxymode)|<span data-ttu-id="c80ce-143">プロキシ サーバーの設定をどのように指定するかを選択する</span><span class="sxs-lookup"><span data-stu-id="c80ce-143">Choose how to specify proxy server settings</span></span>|
|[<span data-ttu-id="c80ce-144">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="c80ce-144">ProxyPacUrl</span></span>](#proxypacurl)|<span data-ttu-id="c80ce-145">プロキシ .pac ファイルへの URL</span><span class="sxs-lookup"><span data-stu-id="c80ce-145">URL to a proxy .pac file</span></span>|
|[<span data-ttu-id="c80ce-146">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="c80ce-146">ProxyServer</span></span>](#proxyserver)|<span data-ttu-id="c80ce-147">プロキシ サーバーのアドレスまたは URL</span><span class="sxs-lookup"><span data-stu-id="c80ce-147">Address or URL of proxy server</span></span>|

                 
      
  
             
            
                  

## <span data-ttu-id="c80ce-148">アプリケーションに関するポリシー</span><span class="sxs-lookup"><span data-stu-id="c80ce-148">Applications policies</span></span>

[<span data-ttu-id="c80ce-149">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-149">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="c80ce-150">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="c80ce-150">InstallDefault</span></span>
#### <span data-ttu-id="c80ce-151">インストールの既定の動作を許可する</span><span class="sxs-lookup"><span data-stu-id="c80ce-151">Allow installation default</span></span>
><span data-ttu-id="c80ce-152">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="c80ce-152">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="c80ce-153">説明</span><span class="sxs-lookup"><span data-stu-id="c80ce-153">Description</span></span>
<span data-ttu-id="c80ce-154">Microsoft Edge の更新プログラムを使用するときに、すべてのチャネルの既定の動作を指定して、Microsoft Edge の更新を許可または禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-154">You can specify the default behavior of all channels to allow or block Microsoft Edge updates when Microsoft Edge Update is used.</span></span>

<span data-ttu-id="c80ce-155">特定のチャネルの['インストールを許可する'](#install)ポリシーを有効にすることで、チャネルごとにポリシーを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-155">You can override this policy for individual channels by enabling the '[Allow installation](#install)' policy for specific channels.</span></span>

<span data-ttu-id="c80ce-156">このポリシーを無効にした場合、Microsoft Edge Update を使用した Microsoft Edge のインストールは禁止されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-156">If you disable this policy, the installation of Microsoft Edge through Microsoft Edge Update is blocked.</span></span> <span data-ttu-id="c80ce-157">これは、ユーザーが Microsoft Edge Update を実行していて、['インストールを許可する'](#install) ポリシーを設定していない場合にのみ、Microsoft Edgeソフトウェアのインストールに影響します。</span><span class="sxs-lookup"><span data-stu-id="c80ce-157">This only affects the installation of Microsoft Edge software only when users are running Microsoft Edge Update and when they haven't configured the '[Allow installation](#install)' policy.</span></span>

<span data-ttu-id="c80ce-158">このポリシーによって、Microsoft Edge Update の実行は禁止されません。また、ユーザーが Microsoft Edge ソフトウェアを他の方法を使用してインストールすることも禁止されません。</span><span class="sxs-lookup"><span data-stu-id="c80ce-158">This policy doesn't prevent Microsoft Edge Update from running or prevent users from installing Microsoft Edge software using other methods.</span></span>
#### <span data-ttu-id="c80ce-159">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-159">Windows information and settings</span></span>
##### <span data-ttu-id="c80ce-160">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="c80ce-160">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c80ce-161">GP 固有の名前: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="c80ce-161">GP unique name: InstallDefault</span></span>
- <span data-ttu-id="c80ce-162">GP の名前: インストールの既定の動作を許可する</span><span class="sxs-lookup"><span data-stu-id="c80ce-162">GP name: Allow installation default</span></span>
- <span data-ttu-id="c80ce-163">GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c80ce-163">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="c80ce-164">GP ADMX ファイル名: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c80ce-164">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c80ce-165">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-165">Windows Registry Settings</span></span>
- <span data-ttu-id="c80ce-166">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c80ce-166">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c80ce-167">値の名前: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="c80ce-167">Value Name: InstallDefault</span></span>
- <span data-ttu-id="c80ce-168">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c80ce-168">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c80ce-169">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="c80ce-169">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="c80ce-170">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-170">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c80ce-171">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="c80ce-171">UpdateDefault</span></span>
#### <span data-ttu-id="c80ce-172">更新ポリシーのオーバーライドの既定値</span><span class="sxs-lookup"><span data-stu-id="c80ce-172">Update policy override default</span></span>
><span data-ttu-id="c80ce-173">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="c80ce-173">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="c80ce-174">説明</span><span class="sxs-lookup"><span data-stu-id="c80ce-174">Description</span></span>
<span data-ttu-id="c80ce-175">Microsoft Edge で利用できる更新プログラムを Microsoft Edge Update で処理する方法について、すべてのチャネルを対象とした既定の動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-175">Lets you specify the default behavior for all channels concerning the way Microsoft Edge Update handles available updates for Microsoft Edge.</span></span> <span data-ttu-id="c80ce-176">特定のチャネルに対して['更新ポリシーの上書き'](#update) ポリシーを指定することにより、個々のチャネルに対して上書きできます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-176">Can be overridden for individual channels by specifying the '[Update policy override](#update)' policy for those specific channels.</span></span>

  <span data-ttu-id="c80ce-177">このポリシーを有効にした場合、Microsoft Edge Update では、以下のオプションの構成方法に従って Microsoft Edge の更新プログラムを処理します。</span><span class="sxs-lookup"><span data-stu-id="c80ce-177">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="c80ce-178">[常に更新を許可する]: 定期的な更新チェックまたは手動更新チェックで検出された場合に、更新プログラムを必ず適用します。</span><span class="sxs-lookup"><span data-stu-id="c80ce-178">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="c80ce-179">[自動サイレント更新のみ]: 更新プログラムは、定期的な更新チェックで検出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-179">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="c80ce-180">[手動更新のみ]: 更新プログラムは、ユーザーが実行した手動更新チェックで検出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-180">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span>
   - <span data-ttu-id="c80ce-181">[更新を無効にする]: 更新プログラムは適用されません。</span><span class="sxs-lookup"><span data-stu-id="c80ce-181">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="c80ce-182">手動更新を選択した場合は、アプリの手動更新メカニズムを使用して、必ず定期的に更新プログラムをチェックしてください (手動更新メカニズムが利用できる場合)。</span><span class="sxs-lookup"><span data-stu-id="c80ce-182">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="c80ce-183">更新を無効にした場合は、定期的に更新プログラムをチェックして、ユーザーに配布してください。</span><span class="sxs-lookup"><span data-stu-id="c80ce-183">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="c80ce-184">このポリシーを有効にして構成しない場合、Microsoft Edge Update は、['更新ポリシーの上書き'](#update) ポリシーで指定された使用可能な更新を処理します。</span><span class="sxs-lookup"><span data-stu-id="c80ce-184">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override](#update)' policy.</span></span>
#### <span data-ttu-id="c80ce-185">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-185">Windows information and settings</span></span>
##### <span data-ttu-id="c80ce-186">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="c80ce-186">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c80ce-187">GP 固有の名前: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="c80ce-187">GP unique name: UpdateDefault</span></span>
- <span data-ttu-id="c80ce-188">GP の名前: 更新ポリシーのオーバーライドの既定値</span><span class="sxs-lookup"><span data-stu-id="c80ce-188">GP name: Update policy override default</span></span>
- <span data-ttu-id="c80ce-189">GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c80ce-189">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="c80ce-190">GP ADMX ファイル名: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c80ce-190">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c80ce-191">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-191">Windows Registry Settings</span></span>
- <span data-ttu-id="c80ce-192">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c80ce-192">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c80ce-193">値の名前: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="c80ce-193">Value Name: UpdateDefault</span></span>
- <span data-ttu-id="c80ce-194">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c80ce-194">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c80ce-195">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="c80ce-195">Example value:</span></span>
```
0x00000003
```
[<span data-ttu-id="c80ce-196">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-196">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c80ce-197">Install</span><span class="sxs-lookup"><span data-stu-id="c80ce-197">Install</span></span>
#### <span data-ttu-id="c80ce-198">インストールを許可する</span><span class="sxs-lookup"><span data-stu-id="c80ce-198">Allow installation</span></span>
><span data-ttu-id="c80ce-199">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="c80ce-199">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="c80ce-200">説明</span><span class="sxs-lookup"><span data-stu-id="c80ce-200">Description</span></span>
<span data-ttu-id="c80ce-201">Microsoft Edge Update を使用して Microsoft Edge チャネルをインストールできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c80ce-201">Specifies whether a Microsoft Edge channel can be installed using Microsoft Edge Update.</span></span>

  <span data-ttu-id="c80ce-202">チャネルに対してこのポリシーを有効にした場合、ユーザーは Microsoft Edge Update を使用して、Microsoft Edge の該当するチャネルをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-202">If you enable this policy for a channel, users can install that channel of Microsoft Edge through Microsoft Edge Update.</span></span>

  <span data-ttu-id="c80ce-203">チャネルに対してこのポリシーを無効にした場合、ユーザーは Microsoft Edge Update を使用して、Microsoft Edge の該当するチャネルをインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c80ce-203">If you disable this policy for a channel, users cannot install that channel of Microsoft Edge through Microsoft Edge Update.</span></span>

  <span data-ttu-id="c80ce-204">チャネルにこのポリシーを構成しない場合、「[インストールの既定の動作を許可する](#installdefault)」 ポリシー構成により、ユーザーがMicrosoft Edge Update を通じて Microsoft Edge のそのチャネルをインストールできるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="c80ce-204">If you don't configure this policy for a channel, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install that channel of Microsoft Edge through Microsoft Edge Update.</span></span>
#### <span data-ttu-id="c80ce-205">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-205">Windows information and settings</span></span>
##### <span data-ttu-id="c80ce-206">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="c80ce-206">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c80ce-207">GP 固有の名前: Install</span><span class="sxs-lookup"><span data-stu-id="c80ce-207">GP unique name: Install</span></span>
- <span data-ttu-id="c80ce-208">GP の名前: インストールを許可する</span><span class="sxs-lookup"><span data-stu-id="c80ce-208">GP name: Allow installation</span></span>
- <span data-ttu-id="c80ce-209">GP パス: </span><span class="sxs-lookup"><span data-stu-id="c80ce-209">GP path:</span></span> 
  - <span data-ttu-id="c80ce-210">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c80ce-210">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="c80ce-211">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="c80ce-211">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="c80ce-212">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="c80ce-212">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="c80ce-213">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="c80ce-213">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="c80ce-214">GP ADMX ファイル名: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c80ce-214">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c80ce-215">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-215">Windows Registry Settings</span></span>
- <span data-ttu-id="c80ce-216">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c80ce-216">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c80ce-217">キーの値: </span><span class="sxs-lookup"><span data-stu-id="c80ce-217">Value Name:</span></span> 
  - <span data-ttu-id="c80ce-218">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="c80ce-218">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="c80ce-219">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="c80ce-219">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="c80ce-220">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="c80ce-220">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="c80ce-221">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="c80ce-221">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="c80ce-222">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c80ce-222">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c80ce-223">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="c80ce-223">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="c80ce-224">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-224">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c80ce-225">Update</span><span class="sxs-lookup"><span data-stu-id="c80ce-225">Update</span></span>
#### <span data-ttu-id="c80ce-226">更新ポリシーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="c80ce-226">Update policy override</span></span>
><span data-ttu-id="c80ce-227">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="c80ce-227">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="c80ce-228">説明</span><span class="sxs-lookup"><span data-stu-id="c80ce-228">Description</span></span>
<span data-ttu-id="c80ce-229">Microsoft Edge で利用できる更新プログラムを Microsoft Edge Update でどのように処理するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c80ce-229">Specifies how Microsoft Edge Update handles available updates from Microsoft Edge.</span></span>

  <span data-ttu-id="c80ce-230">このポリシーを有効にした場合、Microsoft Edge Update では、以下のオプションの構成方法に従って Microsoft Edge の更新プログラムを処理します。</span><span class="sxs-lookup"><span data-stu-id="c80ce-230">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="c80ce-231">[常に更新を許可する]: 定期的な更新チェックまたは手動更新チェックで検出された場合に、更新プログラムを必ず適用します。</span><span class="sxs-lookup"><span data-stu-id="c80ce-231">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="c80ce-232">[自動サイレント更新のみ]: 更新プログラムは、定期的な更新チェックで検出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-232">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="c80ce-233">[手動更新のみ]: 更新プログラムは、ユーザーが実行した手動更新チェックで検出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-233">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span> <span data-ttu-id="c80ce-234">(アプリによっては、このオプション用のインターフェイスがない場合もあります。)</span><span class="sxs-lookup"><span data-stu-id="c80ce-234">(Not all apps provide an interface for this option.)</span></span>
   - <span data-ttu-id="c80ce-235">[更新を無効にする]: 更新プログラムは適用されません。</span><span class="sxs-lookup"><span data-stu-id="c80ce-235">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="c80ce-236">手動更新を選択した場合は、アプリの手動更新メカニズムを使用して、必ず定期的に更新プログラムをチェックしてください (手動更新メカニズムが利用できる場合)。</span><span class="sxs-lookup"><span data-stu-id="c80ce-236">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="c80ce-237">更新を無効にした場合は、定期的に更新プログラムをチェックして、ユーザーに配布してください。</span><span class="sxs-lookup"><span data-stu-id="c80ce-237">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="c80ce-238">このポリシーを有効にせず、構成しない場合、Microsoft Edge Update は、[「更新ポリシー上書きの既定値」](#updatedefault) ポリシーで指定された使用可能な更新プログラムを処理します。</span><span class="sxs-lookup"><span data-stu-id="c80ce-238">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override default](#updatedefault)' policy.</span></span>
#### <span data-ttu-id="c80ce-239">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-239">Windows information and settings</span></span>
##### <span data-ttu-id="c80ce-240">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="c80ce-240">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c80ce-241">GP 固有の名前: Update</span><span class="sxs-lookup"><span data-stu-id="c80ce-241">GP unique name: Update</span></span>
- <span data-ttu-id="c80ce-242">GP の名前: 更新ポリシーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="c80ce-242">GP name: Update policy override</span></span>
- <span data-ttu-id="c80ce-243">GP パス: </span><span class="sxs-lookup"><span data-stu-id="c80ce-243">GP path:</span></span> 
  - <span data-ttu-id="c80ce-244">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c80ce-244">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="c80ce-245">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="c80ce-245">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="c80ce-246">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="c80ce-246">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="c80ce-247">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="c80ce-247">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="c80ce-248">GP ADMX ファイル名: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c80ce-248">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c80ce-249">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-249">Windows Registry Settings</span></span>
- <span data-ttu-id="c80ce-250">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c80ce-250">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c80ce-251">値の名前: </span><span class="sxs-lookup"><span data-stu-id="c80ce-251">Value Name:</span></span> 
  - <span data-ttu-id="c80ce-252">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="c80ce-252">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="c80ce-253">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="c80ce-253">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="c80ce-254">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="c80ce-254">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="c80ce-255">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="c80ce-255">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="c80ce-256">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c80ce-256">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c80ce-257">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="c80ce-257">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="c80ce-258">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-258">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c80ce-259">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="c80ce-259">Allowsxs</span></span>
#### <span data-ttu-id="c80ce-260">Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する</span><span class="sxs-lookup"><span data-stu-id="c80ce-260">Allow Microsoft Edge Side by Side browser experience</span></span>
><span data-ttu-id="c80ce-261">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="c80ce-261">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="c80ce-262">説明</span><span class="sxs-lookup"><span data-stu-id="c80ce-262">Description</span></span>
<span data-ttu-id="c80ce-263">このポリシーを使用すると、ユーザーは Microsoft Edge (Edge HTML) と Microsoft Edge (Chromium ベース) を同時に実行できます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-263">This policy lets a user run Microsoft Edge (Edge HTML) and Microsoft Edge (Chromium-based) side-by-side.</span></span>

<span data-ttu-id="c80ce-264">このポリシーを "未構成" に設定した場合、Microsoft Edge (Chromium ベース) 安定チャネルと 2019 年 11 月のセキュリティ更新プログラムをインストールすると、Microsoft Edge (Edge HTML) が Microsoft Edge (Chromium ベース) に置き換わります。</span><span class="sxs-lookup"><span data-stu-id="c80ce-264">If this policy is set to “Not configured”, Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="c80ce-265">これは、"無効" に設定した場合と同じ動作です。</span><span class="sxs-lookup"><span data-stu-id="c80ce-265">This is the same behavior as the “Disabled” setting.</span></span>

<span data-ttu-id="c80ce-266">"無効" に設定した場合、同時実行エクスペリエンスがブロックされ、Microsoft Edge (Chromium ベース) 安定チャネルと 2019 年 11 月のセキュリティ更新プログラムをインストールすると、Microsoft Edge (Edge HTML) が Microsoft Edge (Chromium ベース) に置き換わります。</span><span class="sxs-lookup"><span data-stu-id="c80ce-266">The “Disabled” setting blocks a side-by-side experience and Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="c80ce-267">これは、"未構成" に設定した場合と同じ動作です。</span><span class="sxs-lookup"><span data-stu-id="c80ce-267">This is the same behavior as the “Not Configured” setting.</span></span>

<span data-ttu-id="c80ce-268">このポリシーを "有効" に設定した場合、Microsoft Edge (Chromium ベース) をインストールすると、Microsoft Edge (Chromium ベース) と Microsoft Edge (Edge HTML) を同時に実行できます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-268">When this policy is “Enabled”, Microsoft Edge (Chromium-based) and Microsoft Edge (Edge HTML) can run side-by-side after Microsoft Edge (Chromium-based) is installed.</span></span>

<span data-ttu-id="c80ce-269">このグループ ポリシーを有効するには、Windows Update による Microsoft Edge (Chromium ベース) の自動インストールが行われる前に、ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c80ce-269">For this group policy to take affect, it must be configured before the automatic install of Microsoft Edge (Chromium-based) by Windows Update.</span></span> <span data-ttu-id="c80ce-270">注意: ユーザーは、Microsoft Edge (Chromium ベース) Blocker Toolkit を使用して、Microsoft Edge (Chromium ベース) の自動更新をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-270">Note: A user can block the automatic update of Microsoft Edge (Chromium-based) by using the Microsoft Edge (Chromium-based) Blocker Toolkit.</span></span>
#### <span data-ttu-id="c80ce-271">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-271">Windows information and settings</span></span>
##### <span data-ttu-id="c80ce-272">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="c80ce-272">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c80ce-273">GP 固有の名前: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="c80ce-273">GP unique name: Allowsxs</span></span>
- <span data-ttu-id="c80ce-274">GP の名前: Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する</span><span class="sxs-lookup"><span data-stu-id="c80ce-274">GP name: Allow Microsoft Edge Side by Side browser experience</span></span>
- <span data-ttu-id="c80ce-275">GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c80ce-275">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="c80ce-276">GP ADMX ファイル名: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c80ce-276">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c80ce-277">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-277">Windows Registry Settings</span></span>
- <span data-ttu-id="c80ce-278">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c80ce-278">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c80ce-279">値の名前: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="c80ce-279">Value Name: Allowsxs</span></span>
- <span data-ttu-id="c80ce-280">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c80ce-280">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c80ce-281">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="c80ce-281">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="c80ce-282">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-282">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c80ce-283">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="c80ce-283">CreateDesktopShortcutDefault</span></span>
#### <span data-ttu-id="c80ce-284">既定値のインストール時にデスクトップへのショートカットの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="c80ce-284">Prevent Desktop Shortcut creation upon install default</span></span>
><span data-ttu-id="c80ce-285">Microsoft Edge Update 1.3.128.0 以降</span><span class="sxs-lookup"><span data-stu-id="c80ce-285">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="c80ce-286">説明</span><span class="sxs-lookup"><span data-stu-id="c80ce-286">Description</span></span>
<span data-ttu-id="c80ce-287">Microsoft Edge がインストールされている場合に、デスクトップにショートカットを作成するすべてのチャネルに対する既定の動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-287">Lets you specify the default behavior for all channels for creating a desktop shortcut when Microsoft Edge is installed.</span></span>

  <span data-ttu-id="c80ce-288">このポリシーを有効にすると、Microsoft Edge がインストールされている場合、デスクトップにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-288">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="c80ce-289">このポリシーを無効にすると、Microsoft Edge インストールされていても、デスクトップにショートカットは作成されません。</span><span class="sxs-lookup"><span data-stu-id="c80ce-289">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="c80ce-290">このポリシーを構成していない場合は、インストール中に Microsoft Edge のデスクトップにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-290">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="c80ce-291">Microsoft Edge が既にインストールされている場合、このポリシーの効果はありません。</span><span class="sxs-lookup"><span data-stu-id="c80ce-291">If Microsoft Edge is already installed, this policy will have no effect.</span></span>
#### <span data-ttu-id="c80ce-292">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-292">Windows information and settings</span></span>
##### <span data-ttu-id="c80ce-293">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="c80ce-293">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c80ce-294">GP 固有の名前: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="c80ce-294">GP unique name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="c80ce-295">GP の名前: 既定値のインストール時にデスクトップへのショートカットの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="c80ce-295">GP name: Prevent Desktop Shortcut creation upon install default</span></span>
- <span data-ttu-id="c80ce-296">GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c80ce-296">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="c80ce-297">GP ADMX ファイル名: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c80ce-297">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c80ce-298">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-298">Windows Registry Settings</span></span>
- <span data-ttu-id="c80ce-299">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c80ce-299">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c80ce-300">値の名前: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="c80ce-300">Value Name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="c80ce-301">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c80ce-301">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c80ce-302">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="c80ce-302">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="c80ce-303">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-303">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c80ce-304">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="c80ce-304">CreateDesktopShortcut</span></span>
#### <span data-ttu-id="c80ce-305">インストール時にデスクトップへのショートカットの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="c80ce-305">Prevent Desktop Shortcut creation upon install</span></span>
><span data-ttu-id="c80ce-306">Microsoft Edge Update 1.3.128.0 以降</span><span class="sxs-lookup"><span data-stu-id="c80ce-306">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="c80ce-307">説明</span><span class="sxs-lookup"><span data-stu-id="c80ce-307">Description</span></span>
<span data-ttu-id="c80ce-308">このポリシーを有効にすると、Microsoft Edge がインストールされている場合、デスクトップにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-308">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="c80ce-309">このポリシーを無効にすると、Microsoft Edge インストールされていても、デスクトップにショートカットは作成されません。</span><span class="sxs-lookup"><span data-stu-id="c80ce-309">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="c80ce-310">このポリシーを構成していない場合は、インストール中に Microsoft Edge のデスクトップにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-310">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="c80ce-311">Microsoft Edge が既にインストールされている場合、このポリシーの効果はありません。</span><span class="sxs-lookup"><span data-stu-id="c80ce-311">If Microsoft Edge is already installed, this policy will have no effect.</span></span>

  <span data-ttu-id="c80ce-312">チャネルにこのポリシーを構成しない場合、「[インストール時にデスクトップショートカットを作成しない](#createdesktopshortcutdefault)」ポリシー構成により、Microsoft Edge のインストール時にショートカットの作成が決まります。</span><span class="sxs-lookup"><span data-stu-id="c80ce-312">If you don't configure this policy for a channel, the '[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)' policy configuration determines shortcut creation when Microsoft Edge is installed.</span></span>
#### <span data-ttu-id="c80ce-313">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-313">Windows information and settings</span></span>
##### <span data-ttu-id="c80ce-314">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="c80ce-314">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c80ce-315">GP 固有の名前: CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="c80ce-315">GP unique name: CreateDesktopShortcut</span></span>
- <span data-ttu-id="c80ce-316">GP の名前: インストール時にデスクトップへのショートカットの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="c80ce-316">GP name: Prevent Desktop Shortcut creation upon install</span></span>
- <span data-ttu-id="c80ce-317">GP パス: </span><span class="sxs-lookup"><span data-stu-id="c80ce-317">GP path:</span></span> 
  - <span data-ttu-id="c80ce-318">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c80ce-318">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="c80ce-319">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="c80ce-319">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="c80ce-320">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="c80ce-320">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="c80ce-321">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="c80ce-321">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="c80ce-322">GP ADMX ファイル名: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c80ce-322">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c80ce-323">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-323">Windows Registry Settings</span></span>
- <span data-ttu-id="c80ce-324">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c80ce-324">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c80ce-325">キーの値: </span><span class="sxs-lookup"><span data-stu-id="c80ce-325">Value Name:</span></span> 
  - <span data-ttu-id="c80ce-326">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="c80ce-326">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="c80ce-327">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="c80ce-327">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="c80ce-328">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="c80ce-328">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="c80ce-329">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="c80ce-329">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="c80ce-330">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c80ce-330">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c80ce-331">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="c80ce-331">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="c80ce-332">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-332">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c80ce-333">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="c80ce-333">TargetVersionPrefix</span></span>
#### <span data-ttu-id="c80ce-334">ターゲット バージョンの上書き</span><span class="sxs-lookup"><span data-stu-id="c80ce-334">Target version override</span></span>
><span data-ttu-id="c80ce-335">Microsoft Edge Update 1.3.119.43 以降</span><span class="sxs-lookup"><span data-stu-id="c80ce-335">Microsoft Edge Update 1.3.119.43 and later</span></span>

#### <span data-ttu-id="c80ce-336">説明</span><span class="sxs-lookup"><span data-stu-id="c80ce-336">Description</span></span>
<span data-ttu-id="c80ce-337">このポリシーを有効にして自動更新を有効にすると、Microsoft Edge がこのポリシー値で指定されたバージョンに更新されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-337">When this policy is enabled, and auto-update is enabled, Microsoft Edge will be updated to the version specified by this policy value.</span></span>

<span data-ttu-id="c80ce-338">ポリシー値は、83.0.499.12 のような特定の Microsoft Edge バージョンである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c80ce-338">The policy value must be a specific Microsoft Edge version, e.g. 83.0.499.12.</span></span>

<span data-ttu-id="c80ce-339">指定した値より新しいバージョンの Microsoft Edge がデバイスにある場合、Microsoft Edge は新しいバージョンのままとなり、指定されたバージョンにダウングレードされません。</span><span class="sxs-lookup"><span data-stu-id="c80ce-339">If a device has newer version of Microsoft Edge than the value specified, Microsoft Edge will remain on the newer version and not downgrade to the specified version.</span></span>

<span data-ttu-id="c80ce-340">指定したバージョンが存在しない場合、または正しく書式設定されていない場合は、Microsoft Edge は現在のバージョンにとどまり、将来のバージョンに自動的に更新されません。</span><span class="sxs-lookup"><span data-stu-id="c80ce-340">If the specified version does not exist, or is improperly formatted, then Microsoft Edge will remain on its current version and not update to future versions automatically.</span></span>
#### <span data-ttu-id="c80ce-341">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-341">Windows information and settings</span></span>
##### <span data-ttu-id="c80ce-342">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="c80ce-342">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c80ce-343">GP 固有の名前: TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="c80ce-343">GP unique name: TargetVersionPrefix</span></span>
- <span data-ttu-id="c80ce-344">GP の名前: ターゲット バージョンの上書き</span><span class="sxs-lookup"><span data-stu-id="c80ce-344">GP name: Target version override</span></span>
- <span data-ttu-id="c80ce-345">GP パス: </span><span class="sxs-lookup"><span data-stu-id="c80ce-345">GP path:</span></span> 
  - <span data-ttu-id="c80ce-346">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c80ce-346">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="c80ce-347">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="c80ce-347">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="c80ce-348">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="c80ce-348">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="c80ce-349">管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="c80ce-349">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="c80ce-350">GP ADMX ファイル名: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c80ce-350">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c80ce-351">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-351">Windows Registry Settings</span></span>
- <span data-ttu-id="c80ce-352">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c80ce-352">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c80ce-353">キーの値: </span><span class="sxs-lookup"><span data-stu-id="c80ce-353">Value Name:</span></span> 
  - <span data-ttu-id="c80ce-354">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="c80ce-354">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="c80ce-355">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="c80ce-355">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="c80ce-356">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="c80ce-356">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="c80ce-357">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="c80ce-357">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="c80ce-358">値の種類: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c80ce-358">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="c80ce-359">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="c80ce-359">Example value:</span></span>
```
83.0.499.12
```
[<span data-ttu-id="c80ce-360">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-360">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="c80ce-361">基本設定に関するポリシー</span><span class="sxs-lookup"><span data-stu-id="c80ce-361">Preferences policies</span></span>

[<span data-ttu-id="c80ce-362">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-362">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="c80ce-363">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="c80ce-363">AutoUpdateCheckPeriodMinutes</span></span>
#### <span data-ttu-id="c80ce-364">自動更新チェック期間のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="c80ce-364">Auto-update check period override</span></span>
><span data-ttu-id="c80ce-365">Microsoft Edge Update 1.2.145.5 以降</span><span class="sxs-lookup"><span data-stu-id="c80ce-365">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="c80ce-366">説明</span><span class="sxs-lookup"><span data-stu-id="c80ce-366">Description</span></span>
<span data-ttu-id="c80ce-367">有効にした場合、このポリシーによって、自動更新チェックの最小間隔の値 (分単位) を設定できます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-367">If enabled, this policy lets you set a value for the minimum number of minutes between automatic update checks.</span></span> <span data-ttu-id="c80ce-368">有効にしなかった場合、自動更新チェックでは、既定で 10 時間ごとに更新が確認されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-368">Otherwise, by default, auto-update checks for updates every 10 hours.</span></span>

  <span data-ttu-id="c80ce-369">すべての自動更新チェックを無効にする場合は、値を 0 に設定します (推奨しません)。</span><span class="sxs-lookup"><span data-stu-id="c80ce-369">If you want to disable all auto-update checks, set the value to 0 (not recommended).</span></span>
#### <span data-ttu-id="c80ce-370">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-370">Windows information and settings</span></span>
##### <span data-ttu-id="c80ce-371">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="c80ce-371">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c80ce-372">GP 固有の名前: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="c80ce-372">GP unique name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="c80ce-373">GP の名前: 自動更新チェック期間のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="c80ce-373">GP name: Auto-update check period override</span></span>
- <span data-ttu-id="c80ce-374">GP パス: 管理用テンプレート/Microsoft Edge Update/基本設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-374">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="c80ce-375">GP ADMX ファイル名: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c80ce-375">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c80ce-376">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-376">Windows Registry Settings</span></span>
- <span data-ttu-id="c80ce-377">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c80ce-377">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c80ce-378">値の名前: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="c80ce-378">Value Name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="c80ce-379">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c80ce-379">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c80ce-380">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="c80ce-380">Example value:</span></span>
```
0x00000578
```
[<span data-ttu-id="c80ce-381">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-381">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c80ce-382">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="c80ce-382">UpdatesSuppressed</span></span>
#### <span data-ttu-id="c80ce-383">自動更新チェックを停止する 1 日あたりの時間帯</span><span class="sxs-lookup"><span data-stu-id="c80ce-383">Time period in each day to suppress auto-update check</span></span>
><span data-ttu-id="c80ce-384">Microsoft Edge Update 1.3.33.5 以降</span><span class="sxs-lookup"><span data-stu-id="c80ce-384">Microsoft Edge Update 1.3.33.5 and later</span></span>

#### <span data-ttu-id="c80ce-385">説明</span><span class="sxs-lookup"><span data-stu-id="c80ce-385">Description</span></span>
<span data-ttu-id="c80ce-386">このポリシーを有効にした場合、更新チェックは毎日指定の時刻 (時:分) に停止され、一定の期間、更新チェックが行われなくなります (分単位)。</span><span class="sxs-lookup"><span data-stu-id="c80ce-386">If you enable this policy, update checks are suppressed each day starting at Hour:Minute for a period of Duration (in minutes).</span></span> <span data-ttu-id="c80ce-387">この期間では夏時間が考慮されません。</span><span class="sxs-lookup"><span data-stu-id="c80ce-387">Duration isn't affected by daylight saving time.</span></span> <span data-ttu-id="c80ce-388">たとえば、開始時間が 22:00、期間が 480 分の場合、その期間内で夏時間の開始や終了が発生しても、更新は正確に 8 時間停止されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-388">For example, if the start time is 22:00 and the duration is 480 minutes, updates will be suppressed for exactly 8 hours, regardless of whether daylight saving time starts or ends during this period.</span></span>

  <span data-ttu-id="c80ce-389">このポリシーを無効にした場合または構成しなかった場合、更新チェックが一定期間停止されることはありません。</span><span class="sxs-lookup"><span data-stu-id="c80ce-389">If you disable or don't configure this policy, update checks aren't suppressed during any specific period.</span></span>
#### <span data-ttu-id="c80ce-390">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-390">Windows information and settings</span></span>
##### <span data-ttu-id="c80ce-391">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="c80ce-391">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c80ce-392">GP 固有の名前: UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="c80ce-392">GP unique name: UpdatesSuppressed</span></span>
- <span data-ttu-id="c80ce-393">GP の名前: 自動更新チェックを停止する 1 日あたりの時間帯</span><span class="sxs-lookup"><span data-stu-id="c80ce-393">GP name: Time period in each day to suppress auto-update check</span></span>
  - <span data-ttu-id="c80ce-394">オプション { Hour, Minute, Duration }</span><span class="sxs-lookup"><span data-stu-id="c80ce-394">Options { Hour, Minute, Duration }</span></span>
- <span data-ttu-id="c80ce-395">GP パス: 管理用テンプレート/Microsoft Edge Update/基本設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-395">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="c80ce-396">GP ADMX ファイル名: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c80ce-396">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c80ce-397">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-397">Windows Registry Settings</span></span>
- <span data-ttu-id="c80ce-398">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c80ce-398">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c80ce-399">値の名前: </span><span class="sxs-lookup"><span data-stu-id="c80ce-399">Value Name:</span></span> 
  - <span data-ttu-id="c80ce-400">UpdatesSuppressedDurationMin</span><span class="sxs-lookup"><span data-stu-id="c80ce-400">UpdatesSuppressedDurationMin</span></span>
  - <span data-ttu-id="c80ce-401">UpdatesSuppressedStartHour</span><span class="sxs-lookup"><span data-stu-id="c80ce-401">UpdatesSuppressedStartHour</span></span>
  - <span data-ttu-id="c80ce-402">UpdatesSuppressedStartMin</span><span class="sxs-lookup"><span data-stu-id="c80ce-402">UpdatesSuppressedStartMin</span></span>
- <span data-ttu-id="c80ce-403">値の種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c80ce-403">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c80ce-404">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="c80ce-404">Example value:</span></span>
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[<span data-ttu-id="c80ce-405">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-405">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="c80ce-406">プロキシ サーバーに関するポリシー</span><span class="sxs-lookup"><span data-stu-id="c80ce-406">Proxy Server policies</span></span>
  
  

[<span data-ttu-id="c80ce-407">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-407">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="c80ce-408">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="c80ce-408">ProxyMode</span></span>
#### <span data-ttu-id="c80ce-409">プロキシ サーバーの設定をどのように指定するかを選択する</span><span class="sxs-lookup"><span data-stu-id="c80ce-409">Choose how to specify proxy server settings</span></span>
><span data-ttu-id="c80ce-410">Microsoft Edge Update 1.3.21.81 以降</span><span class="sxs-lookup"><span data-stu-id="c80ce-410">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="c80ce-411">説明</span><span class="sxs-lookup"><span data-stu-id="c80ce-411">Description</span></span>
<span data-ttu-id="c80ce-412">Microsoft Edge Update で使用されるプロキシ サーバーの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-412">Allows you to specify the proxy server settings that are used by Microsoft Edge Update.</span></span>

  <span data-ttu-id="c80ce-413">このポリシーを有効にした場合、以下のプロキシ サーバーのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-413">If you enable this policy, you can choose between the following proxy server options:</span></span>
   - <span data-ttu-id="c80ce-414">プロキシ サーバーを使用せず、常に直接接続することを選択した場合、他のオプションはすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-414">If you choose to never use a proxy server and always connect directly, all other options are ignored.</span></span>
   - <span data-ttu-id="c80ce-415">システム プロキシ設定を使用するか、プロキシ サーバーの自動検出を選択した場合、他のオプションはすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-415">If you choose to use system proxy settings or auto-detect the proxy server, all other options are ignored.</span></span>
   - <span data-ttu-id="c80ce-416">固定サーバー プロキシ モードを選択した場合、'[プロキシ サーバーのアドレスまたは URL](#proxyserver)' でさらにオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-416">If you choose fixed server proxy mode, you can specify further options in '[Address or URL of proxy server](#proxyserver)' policy.</span></span>
   - <span data-ttu-id="c80ce-417">.pac プロキシスクリプトを使用する場合は、'[プロキシ .pac ファイルへの URL ](#proxypacurl)' ポリシーでスクリプトの URL を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c80ce-417">If you choose to use a .pac proxy script, you must specify the URL for the script in '[URL to a proxy .pac file](#proxypacurl)' policy.</span></span>

  <span data-ttu-id="c80ce-418">このポリシーを有効にした場合、組織内のユーザーは Microsoft Edge Update でプロキシ設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="c80ce-418">If you enable this policy, users in your organization can't change the proxy settings in Microsoft Edge Update.</span></span>

  <span data-ttu-id="c80ce-419">このポリシーを無効にした場合または構成しなかった場合、プロキシ サーバーの設定は構成されませんが、組織内のユーザーは Microsoft Edge Update で独自のプロキシ設定を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-419">If you disable or don't configure this policy, no proxy server settings are configured, but users in your organization can choose their own proxy settings for Microsoft Edge Update.</span></span>
#### <span data-ttu-id="c80ce-420">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-420">Windows information and settings</span></span>
##### <span data-ttu-id="c80ce-421">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="c80ce-421">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c80ce-422">GP 固有の名前: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="c80ce-422">GP unique name: ProxyMode</span></span>
- <span data-ttu-id="c80ce-423">GP の名前: プロキシ サーバーの設定をどのように指定するかを選択する</span><span class="sxs-lookup"><span data-stu-id="c80ce-423">GP name: Choose how to specify proxy server settings</span></span>
- <span data-ttu-id="c80ce-424">GP パス: 管理用テンプレート/Microsoft Edge Update/プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="c80ce-424">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="c80ce-425">GP ADMX ファイル名: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c80ce-425">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c80ce-426">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-426">Windows Registry Settings</span></span>
- <span data-ttu-id="c80ce-427">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c80ce-427">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c80ce-428">値の名前: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="c80ce-428">Value Name: ProxyMode</span></span>
- <span data-ttu-id="c80ce-429">値の種類: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c80ce-429">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="c80ce-430">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="c80ce-430">Example value:</span></span>
```
fixed_servers
```
[<span data-ttu-id="c80ce-431">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-431">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c80ce-432">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="c80ce-432">ProxyPacUrl</span></span>
#### <span data-ttu-id="c80ce-433">プロキシ .pac ファイルへの URL</span><span class="sxs-lookup"><span data-stu-id="c80ce-433">URL to a proxy .pac file</span></span>
><span data-ttu-id="c80ce-434">Microsoft Edge Update 1.3.21.81 以降</span><span class="sxs-lookup"><span data-stu-id="c80ce-434">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="c80ce-435">説明</span><span class="sxs-lookup"><span data-stu-id="c80ce-435">Description</span></span>
<span data-ttu-id="c80ce-436">プロキシ自動構成 (PAC) ファイルの URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-436">Allows you to specify a URL for a proxy auto-config (PAC) file.</span></span>

  <span data-ttu-id="c80ce-437">このポリシーを有効にした場合、PAC ファイルの URL を指定して、特定の Web サイトを取得するための適切なプロキシサーバーを Microsoft Edge Update で選択する方法を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-437">If you enable this policy, you can specify a URL for a PAC file to automate how Microsoft Edge Update selects the appropriate proxy server for fetching a particular website.</span></span>

  <span data-ttu-id="c80ce-438">このポリシーは、 '[プロキシサーバー設定の指定方法を選択する](#proxymode)' ポリシーで手動プロキシ設定を指定した場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-438">This policy is applied only if you have specified manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="c80ce-439">'[プロキシ サーバーの設定をどのように指定するかを選択する](#proxymode)'ポリシーで手動以外のプロキシ設定を選択した場合は、このポリシーを構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="c80ce-439">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="c80ce-440">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-440">Windows information and settings</span></span>
##### <span data-ttu-id="c80ce-441">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="c80ce-441">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c80ce-442">GP 固有の名前: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="c80ce-442">GP unique name: ProxyPacUrl</span></span>
- <span data-ttu-id="c80ce-443">GP の名前: プロキシ .pac ファイルへの URL</span><span class="sxs-lookup"><span data-stu-id="c80ce-443">GP name: URL to a proxy .pac file</span></span>
- <span data-ttu-id="c80ce-444">GP パス: 管理用テンプレート/Microsoft Edge Update/プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="c80ce-444">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="c80ce-445">GP ADMX ファイル名: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c80ce-445">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c80ce-446">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-446">Windows Registry Settings</span></span>
- <span data-ttu-id="c80ce-447">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c80ce-447">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c80ce-448">値の名前: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="c80ce-448">Value Name: ProxyPacUrl</span></span>
- <span data-ttu-id="c80ce-449">値の種類: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c80ce-449">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="c80ce-450">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="c80ce-450">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="c80ce-451">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-451">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c80ce-452">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="c80ce-452">ProxyServer</span></span>
#### <span data-ttu-id="c80ce-453">プロキシ サーバーのアドレスまたは URL</span><span class="sxs-lookup"><span data-stu-id="c80ce-453">Address or URL of proxy server</span></span>
><span data-ttu-id="c80ce-454">Microsoft Edge Update 1.3.21.81 以降</span><span class="sxs-lookup"><span data-stu-id="c80ce-454">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="c80ce-455">説明</span><span class="sxs-lookup"><span data-stu-id="c80ce-455">Description</span></span>
<span data-ttu-id="c80ce-456">Microsoft Edge Update で使用するプロキシ サーバーの URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-456">Allows you to specify the URL of the proxy server for Microsoft Edge Update to use.</span></span>

  <span data-ttu-id="c80ce-457">このポリシーを有効にした場合、組織内の Microsoft Edge Update が使用するプロキシ サーバーの URL を設定できます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-457">If you enable this policy, you can set the proxy server URL used by Microsoft Edge Update in your organization.</span></span>

  <span data-ttu-id="c80ce-458">このポリシーは、 '[プロキシサーバー設定の指定方法を選択する](#proxymode)' ポリシーで手動プロキシ設定を指定した場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c80ce-458">This policy is applied only if you have selected manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="c80ce-459">'[プロキシ サーバーの設定をどのように指定するかを選択する](#proxymode)'ポリシーで手動以外のプロキシ設定を選択した場合は、このポリシーを構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="c80ce-459">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="c80ce-460">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-460">Windows information and settings</span></span>
##### <span data-ttu-id="c80ce-461">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="c80ce-461">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c80ce-462">GP 固有の名前: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="c80ce-462">GP unique name: ProxyServer</span></span>
- <span data-ttu-id="c80ce-463">GP の名前: プロキシ サーバーのアドレスまたは URL</span><span class="sxs-lookup"><span data-stu-id="c80ce-463">GP name: Address or URL of proxy server</span></span>
- <span data-ttu-id="c80ce-464">GP パス: 管理用テンプレート/Microsoft Edge Update/プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="c80ce-464">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="c80ce-465">GP ADMX ファイル名: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c80ce-465">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c80ce-466">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="c80ce-466">Windows Registry Settings</span></span>
- <span data-ttu-id="c80ce-467">パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c80ce-467">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c80ce-468">値の名前: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="c80ce-468">Value Name: ProxyServer</span></span>
- <span data-ttu-id="c80ce-469">値の種類: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c80ce-469">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="c80ce-470">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="c80ce-470">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="c80ce-471">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c80ce-471">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="c80ce-472">関連項目</span><span class="sxs-lookup"><span data-stu-id="c80ce-472">See also</span></span>
  - [<span data-ttu-id="c80ce-473">Microsoft Edge の構成</span><span class="sxs-lookup"><span data-stu-id="c80ce-473">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
  - [<span data-ttu-id="c80ce-474">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="c80ce-474">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
