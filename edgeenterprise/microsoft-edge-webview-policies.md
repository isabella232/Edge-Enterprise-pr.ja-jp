---
title: Microsoft Edge WebView2 ポリシードキュメント
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 10/16/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge ブラウザーでサポートされているすべてのポリシーに関する Windows と Mac のドキュメント
ms.openlocfilehash: 4298b25f7f158bc54f798442b4426494f046fa68
ms.sourcegitcommit: 7d160257010f75b86b89c8802d0dd27f1f8761ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2020
ms.locfileid: "11134446"
---
# <span data-ttu-id="c4fe8-103">Microsoft Edge WebView2 - ポリシー</span><span class="sxs-lookup"><span data-stu-id="c4fe8-103">Microsoft Edge WebView2 - Policies</span></span>

<span data-ttu-id="c4fe8-104">最新バージョンの Microsoft Edge WebView2には、次のポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-104">The latest version of Microsoft Edge WebView2 includes the following policies.</span></span> <span data-ttu-id="c4fe8-105">これらのポリシーを使用して、組織内での Microsoft Edge WebView2の動作方法を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-105">You can use these policies to configure how Microsoft Edge WebView2 runs in your organization.</span></span>

<span data-ttu-id="c4fe8-106">Microsoft Edge WebView2の更新方法とタイミングを制御するために使用される追加のポリシー セットについては、「[Microsoft Edge更新ポリシーの参照](microsoft-edge-update-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-106">For information about an additional set of policies used to control how and when Microsoft Edge WebView2 is updated, check out [Microsoft Edge update policy reference](microsoft-edge-update-policies.md).</span></span>


> [!NOTE]
> <span data-ttu-id="c4fe8-107">この記事は Microsoft Edge version 87 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-107">This article applies to Microsoft Edge version 87 or later.</span></span>

## <span data-ttu-id="c4fe8-108">使用可能なポリシー</span><span class="sxs-lookup"><span data-stu-id="c4fe8-108">Available policies</span></span>

<span data-ttu-id="c4fe8-109">次の表は、Microsoft Edge WebView2で使用可能な、このリリースのすべてのグループ ポリシーの一覧を示しています。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-109">These tables list all of the group policies available in this release of Microsoft Edge WebView2.</span></span> <span data-ttu-id="c4fe8-110">個々のポリシーに関する詳しい情報を取得するには、表内のリンクをお使いください。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-110">Use the links in the table to get more details about specific policies.</span></span>

|||
|-|-|
|[<span data-ttu-id="c4fe8-111">ローダーの上書き設定</span><span class="sxs-lookup"><span data-stu-id="c4fe8-111">Loader Override Settings</span></span>](#loader-override-settings)|

### [*<span data-ttu-id="c4fe8-112">ローダーの上書き設定</span><span class="sxs-lookup"><span data-stu-id="c4fe8-112">Loader Override Settings</span></span>*](#loader-override-settings-policies)

|<span data-ttu-id="c4fe8-113">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="c4fe8-113">Policy Name</span></span>|<span data-ttu-id="c4fe8-114">キャプション</span><span class="sxs-lookup"><span data-stu-id="c4fe8-114">Caption</span></span>|
|-|-|
|[<span data-ttu-id="c4fe8-115">browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="c4fe8-115">browserExecutableFolder</span></span>](#browserexecutablefolder)|<span data-ttu-id="c4fe8-116">ブラウザーの実行可能フォルダーの場所を構成する</span><span class="sxs-lookup"><span data-stu-id="c4fe8-116">Configure the location of the browser executable folder</span></span>|
|[<span data-ttu-id="c4fe8-117">releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="c4fe8-117">releaseChannelPreference</span></span>](#releasechannelpreference)|<span data-ttu-id="c4fe8-118">リリースチャネルの優先検索順序を設定する</span><span class="sxs-lookup"><span data-stu-id="c4fe8-118">Set the release channel search order preference</span></span>|




  ## <span data-ttu-id="c4fe8-119">ローダーの上書き設定ポリシー</span><span class="sxs-lookup"><span data-stu-id="c4fe8-119">Loader Override Settings policies</span></span>

  [<span data-ttu-id="c4fe8-120">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c4fe8-120">Back to top</span></span>](#microsoft-edge-webview2---policies)

  ### <span data-ttu-id="c4fe8-121">browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="c4fe8-121">browserExecutableFolder</span></span>

  #### <span data-ttu-id="c4fe8-122">ブラウザーの実行可能フォルダーの場所を構成する</span><span class="sxs-lookup"><span data-stu-id="c4fe8-122">Configure the location of the browser executable folder</span></span>

  
  
  #### <span data-ttu-id="c4fe8-123">サポートされているバージョン:</span><span class="sxs-lookup"><span data-stu-id="c4fe8-123">Supported versions:</span></span>

  - <span data-ttu-id="c4fe8-124">Windows での 87 以降</span><span class="sxs-lookup"><span data-stu-id="c4fe8-124">On Windows since 87 or later</span></span>

  #### <span data-ttu-id="c4fe8-125">説明</span><span class="sxs-lookup"><span data-stu-id="c4fe8-125">Description</span></span>

  <span data-ttu-id="c4fe8-126">このポリシーでは、指定したパスの WebView2 ランタイムを使用するように WebView2 アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-126">This policy configures WebView2 applications to use the WebView2 Runtime in the specified path.</span></span> <span data-ttu-id="c4fe8-127">フォルダーには、msedgewebview2.exe、 msedge.dll などのファイルが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-127">The folder should contain the following files: msedgewebview2.exe, msedge.dll, and so on.</span></span>

<span data-ttu-id="c4fe8-128">フォルダーパスの値を設定するには、値の名前と値のペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-128">To set the value for the folder path, provide a Value name and Value pair.</span></span> <span data-ttu-id="c4fe8-129">アプリケーションユーザーモデル ID または実行可能ファイル名に値の名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-129">Set value name to the Application User Model ID or the executable file name.</span></span> <span data-ttu-id="c4fe8-130">すべてのアプリケーションに適用するには、""\*" wildcardを値の名前として使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-130">You can use the "\*" wildcard as value name to apply to all applications.</span></span>

  #### <span data-ttu-id="c4fe8-131">サポートされている機能:</span><span class="sxs-lookup"><span data-stu-id="c4fe8-131">Supported features:</span></span>

  - <span data-ttu-id="c4fe8-132">必須にすることができるか: はい</span><span class="sxs-lookup"><span data-stu-id="c4fe8-132">Can be mandatory: Yes</span></span>
  - <span data-ttu-id="c4fe8-133">推奨にすることができるか: いいえ</span><span class="sxs-lookup"><span data-stu-id="c4fe8-133">Can be recommended: No</span></span>
  - <span data-ttu-id="c4fe8-134">動的なポリシーの更新: はい</span><span class="sxs-lookup"><span data-stu-id="c4fe8-134">Dynamic Policy Refresh: Yes</span></span>

  #### <span data-ttu-id="c4fe8-135">［データの種類］:</span><span class="sxs-lookup"><span data-stu-id="c4fe8-135">Data Type:</span></span>

  - <span data-ttu-id="c4fe8-136">文字列のリスト</span><span class="sxs-lookup"><span data-stu-id="c4fe8-136">List of strings</span></span>

  #### <span data-ttu-id="c4fe8-137">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="c4fe8-137">Windows information and settings</span></span>

  ##### <span data-ttu-id="c4fe8-138">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="c4fe8-138">Group Policy (ADMX) info</span></span>

  - <span data-ttu-id="c4fe8-139">GP 固有の名前: browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="c4fe8-139">GP unique name: browserExecutableFolder</span></span>
  - <span data-ttu-id="c4fe8-140">GP 名: ブラウザーの実行可能ファイルフォルダーの場所を構成する</span><span class="sxs-lookup"><span data-stu-id="c4fe8-140">GP name: Configure the location of the browser executable folder</span></span>
  - <span data-ttu-id="c4fe8-141">GP path (必須): 管理用テンプレート/Microsoft Edge WebView2/ローダーの上書き設定</span><span class="sxs-lookup"><span data-stu-id="c4fe8-141">GP path (Mandatory): Administrative Templates/Microsoft Edge WebView2/Loader Override Settings</span></span>
  - <span data-ttu-id="c4fe8-142">GP パス (推奨): なし</span><span class="sxs-lookup"><span data-stu-id="c4fe8-142">GP path (Recommended): N/A</span></span>
  - <span data-ttu-id="c4fe8-143">GP ADMX ファイル名: MSEdgeWebView2.admx</span><span class="sxs-lookup"><span data-stu-id="c4fe8-143">GP ADMX file name: MSEdgeWebView2.admx</span></span>

  ##### <span data-ttu-id="c4fe8-144">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="c4fe8-144">Windows Registry Settings</span></span>

  - <span data-ttu-id="c4fe8-145">Path (必須): SOFTWARE\Policies\Microsoft\Edge\WebView2\browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="c4fe8-145">Path (Mandatory): SOFTWARE\Policies\Microsoft\Edge\WebView2\browserExecutableFolder</span></span>
  - <span data-ttu-id="c4fe8-146">パス (推奨): なし</span><span class="sxs-lookup"><span data-stu-id="c4fe8-146">Path (Recommended): N/A</span></span>
  - <span data-ttu-id="c4fe8-147">値の名前: REG_SZ の一覧</span><span class="sxs-lookup"><span data-stu-id="c4fe8-147">Value Name: list of REG_SZ</span></span>
  - <span data-ttu-id="c4fe8-148">値の種類: REG_SZ の一覧</span><span class="sxs-lookup"><span data-stu-id="c4fe8-148">Value Type: list of REG_SZ</span></span>

  ##### <span data-ttu-id="c4fe8-149">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="c4fe8-149">Example value:</span></span>

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\browserExecutableFolder = "Name: *, Value: C:\\Program Files\\Microsoft Edge WebView2 Runtime Redistributable 85.0.541.0 x64"

```

  

  [<span data-ttu-id="c4fe8-150">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c4fe8-150">Back to top</span></span>](#microsoft-edge-webview2---policies)

  ### <span data-ttu-id="c4fe8-151">releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="c4fe8-151">releaseChannelPreference</span></span>

  #### <span data-ttu-id="c4fe8-152">リリースチャネルの優先検索順序を設定する</span><span class="sxs-lookup"><span data-stu-id="c4fe8-152">Set the release channel search order preference</span></span>

  
  
  #### <span data-ttu-id="c4fe8-153">サポートされているバージョン:</span><span class="sxs-lookup"><span data-stu-id="c4fe8-153">Supported versions:</span></span>

  - <span data-ttu-id="c4fe8-154">Windows での 87 以降</span><span class="sxs-lookup"><span data-stu-id="c4fe8-154">On Windows since 87 or later</span></span>

  #### <span data-ttu-id="c4fe8-155">説明</span><span class="sxs-lookup"><span data-stu-id="c4fe8-155">Description</span></span>

  <span data-ttu-id="c4fe8-156">既定のチャネル検索順序は、WebView2 ランタイム、ベータ、開発、およびカナリアです。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-156">The default channel search order is WebView2 Runtime, Beta, Dev, and Canary.</span></span>

<span data-ttu-id="c4fe8-157">既定の検索順序を反転するには、このポリシーを1に設定します。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-157">To reverse the default search order, set this policy to 1.</span></span>

<span data-ttu-id="c4fe8-158">リリースチャネルの基本設定の値を設定するには、値の名前と値のペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-158">To set the value for the release channel preference, provide a Value name and Value pair.</span></span> <span data-ttu-id="c4fe8-159">アプリケーションユーザーモデル ID または実行可能ファイル名に値の名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-159">Set value name to the Application User Model ID or the executable file name.</span></span> <span data-ttu-id="c4fe8-160">すべてのアプリケーションに適用するには、""\*" wildcardを値の名前として使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4fe8-160">You can use the "\*" wildcard as value name to apply to all applications.</span></span>

  #### <span data-ttu-id="c4fe8-161">サポートされている機能:</span><span class="sxs-lookup"><span data-stu-id="c4fe8-161">Supported features:</span></span>

  - <span data-ttu-id="c4fe8-162">必須にすることができるか: はい</span><span class="sxs-lookup"><span data-stu-id="c4fe8-162">Can be mandatory: Yes</span></span>
  - <span data-ttu-id="c4fe8-163">推奨にすることができるか: いいえ</span><span class="sxs-lookup"><span data-stu-id="c4fe8-163">Can be recommended: No</span></span>
  - <span data-ttu-id="c4fe8-164">動的なポリシーの更新: はい</span><span class="sxs-lookup"><span data-stu-id="c4fe8-164">Dynamic Policy Refresh: Yes</span></span>

  #### <span data-ttu-id="c4fe8-165">［データの種類］:</span><span class="sxs-lookup"><span data-stu-id="c4fe8-165">Data Type:</span></span>

  - <span data-ttu-id="c4fe8-166">文字列のリスト</span><span class="sxs-lookup"><span data-stu-id="c4fe8-166">List of strings</span></span>

  #### <span data-ttu-id="c4fe8-167">Windows の情報と設定</span><span class="sxs-lookup"><span data-stu-id="c4fe8-167">Windows information and settings</span></span>

  ##### <span data-ttu-id="c4fe8-168">グループ ポリシー (ADMX) 情報</span><span class="sxs-lookup"><span data-stu-id="c4fe8-168">Group Policy (ADMX) info</span></span>

  - <span data-ttu-id="c4fe8-169">GP 固有の名前: releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="c4fe8-169">GP unique name: releaseChannelPreference</span></span>
  - <span data-ttu-id="c4fe8-170">GP 名: リリースチャネルの優先検索順序を設定する</span><span class="sxs-lookup"><span data-stu-id="c4fe8-170">GP name: Set the release channel search order preference</span></span>
  - <span data-ttu-id="c4fe8-171">GP path (必須): 管理用テンプレート/Microsoft Edge WebView2/ローダーの上書き設定</span><span class="sxs-lookup"><span data-stu-id="c4fe8-171">GP path (Mandatory): Administrative Templates/Microsoft Edge WebView2/Loader Override Settings</span></span>
  - <span data-ttu-id="c4fe8-172">GP パス (推奨): なし</span><span class="sxs-lookup"><span data-stu-id="c4fe8-172">GP path (Recommended): N/A</span></span>
  - <span data-ttu-id="c4fe8-173">GP ADMX ファイル名: MSEdgeWebView2.admx</span><span class="sxs-lookup"><span data-stu-id="c4fe8-173">GP ADMX file name: MSEdgeWebView2.admx</span></span>

  ##### <span data-ttu-id="c4fe8-174">Windows レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="c4fe8-174">Windows Registry Settings</span></span>

  - <span data-ttu-id="c4fe8-175">Path (必須): SOFTWARE\Policies\Microsoft\Edge\WebView2\releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="c4fe8-175">Path (Mandatory): SOFTWARE\Policies\Microsoft\Edge\WebView2\releaseChannelPreference</span></span>
  - <span data-ttu-id="c4fe8-176">パス (推奨): なし</span><span class="sxs-lookup"><span data-stu-id="c4fe8-176">Path (Recommended): N/A</span></span>
  - <span data-ttu-id="c4fe8-177">値の名前: REG_SZ の一覧</span><span class="sxs-lookup"><span data-stu-id="c4fe8-177">Value Name: list of REG_SZ</span></span>
  - <span data-ttu-id="c4fe8-178">値の種類: REG_SZ の一覧</span><span class="sxs-lookup"><span data-stu-id="c4fe8-178">Value Type: list of REG_SZ</span></span>

  ##### <span data-ttu-id="c4fe8-179">サンプル値:</span><span class="sxs-lookup"><span data-stu-id="c4fe8-179">Example value:</span></span>

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\releaseChannelPreference = "Name: *, Value: 1"

```

  

  [<span data-ttu-id="c4fe8-180">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c4fe8-180">Back to top</span></span>](#microsoft-edge-webview2---policies)


## <span data-ttu-id="c4fe8-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4fe8-181">See also</span></span>

- [<span data-ttu-id="c4fe8-182">Microsoft Edge の構成</span><span class="sxs-lookup"><span data-stu-id="c4fe8-182">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="c4fe8-183">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="c4fe8-183">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="c4fe8-184">Microsoft Office セキュリティ ベースライン ブログ</span><span class="sxs-lookup"><span data-stu-id="c4fe8-184">Microsoft Security Baselines Blog</span></span>](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)