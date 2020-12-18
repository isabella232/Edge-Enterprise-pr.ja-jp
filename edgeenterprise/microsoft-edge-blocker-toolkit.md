---
title: Microsoft Edge の自動配布を無効にするための Blocker Toolkit
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 12/16/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge の自動配布を無効にするための Blocker Toolkit
ms.openlocfilehash: 9fb97d2dfec4822f8ce76dc3e37b85118c6572ad
ms.sourcegitcommit: 606282995b466a968bab40c16005a6653323c763
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "11229618"
---
# <span data-ttu-id="132ed-103">Microsoft Edge (Chromium ベース) の自動配布を無効にするための Blocker Toolkit</span><span class="sxs-lookup"><span data-stu-id="132ed-103">Blocker Toolkit to disable automatic delivery of Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="132ed-104">この記事では、Microsoft Edge の自動配布とインストールを無効にするための Blocker Toolkit について説明します。</span><span class="sxs-lookup"><span data-stu-id="132ed-104">This article describes the Blocker Toolkit for disabling automatic delivery and installation of Microsoft Edge.</span></span>

<span data-ttu-id="132ed-105">この記事では、次の更新が行われました。</span><span class="sxs-lookup"><span data-stu-id="132ed-105">The following updates have been made to this article:</span></span>

- <span data-ttu-id="132ed-106">**2020 年 1 月 9 日** Blocker Toolkit の使用が必要になる可能性のあるデバイスに関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="132ed-106">**01/09/2020** with more information about devices that might require you to use the Blocker Toolkit</span></span>
- <span data-ttu-id="132ed-107">**2020 年 2 月 28 日** この自動更新から除外するデバイスの基準から「MDM 管理対象」を削除しました</span><span class="sxs-lookup"><span data-stu-id="132ed-107">**2/28/2020** to remove "MDM managed" from the criteria of devices to be excluded from this automatic update</span></span>
- <span data-ttu-id="132ed-108">**2020 年 6 月 30** Windows Update に接続されているすべてのデバイスがこの更新プログラムを受信する範囲内にあることを反映しました（2020 年 7 月 30 日までに有効になります）</span><span class="sxs-lookup"><span data-stu-id="132ed-108">**6/30/2020** to reflect that all Windows Update connected devices are in scope to receive this update (effective no sooner than 7/30/2020)</span></span>
- <span data-ttu-id="132ed-109">**2020 年 12 月 10** Blocker Toolkit の設定が無視される 20H2 以前の状況を説明しました</span><span class="sxs-lookup"><span data-stu-id="132ed-109">**12/10/2020** to explain pre 20H2 situations in which the Blocker Toolkit settings will be ignored</span></span>

> [!NOTE]
> <span data-ttu-id="132ed-110">この記事は、Microsoft Edge Stable チャネルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="132ed-110">This applies to Microsoft Edge Stable channel.</span></span>

## <span data-ttu-id="132ed-111">概要</span><span class="sxs-lookup"><span data-stu-id="132ed-111">Overview</span></span>

<span data-ttu-id="132ed-112">お客様のセキュリティを強化し、最新の状態に保つために、Microsoft ではWindows 10 バージョン 1803 以降を実行しているすべての Windows Update で接続されたデバイスに Microsoft Edge (Chromium ベース) を配布します。</span><span class="sxs-lookup"><span data-stu-id="132ed-112">To help our customers become more secure and up-to-date, Microsoft will distribute Microsoft Edge (Chromium-based) to all Windows Update-connected devices running Windows 10 version 1803 and newer.</span></span> <span data-ttu-id="132ed-113">このプロセスは、2020 年 1 月 15 日以降に開始され、詳しい情報は当日提供されます。</span><span class="sxs-lookup"><span data-stu-id="132ed-113">This process will start after January 15, 2020 and more information will be available on that date.</span></span>

<span data-ttu-id="132ed-114">Blocker Toolkit は、Windows 10 バージョン 1803 以降を実行している Windows Update で接続されたデバイスへの Microsoft Edge (Chromium ベース) の自動配信をブロックする組織を対象としています。</span><span class="sxs-lookup"><span data-stu-id="132ed-114">The Blocker Toolkit is intended for organizations that would like to block automatic delivery of Microsoft Edge (Chromium-based) to Windows Updated-connected devices running Windows 10 version 1803 and newer.</span></span> <span data-ttu-id="132ed-115">Windows Server Update Services (WSUS) または Windows Update for Business (WUfB) が管理されているデバイスは、この自動 Windows Update から除外されますが、所属している組織を通じて新しい Microsoft Edge (Chromium ベース) を受け取る場合があります。</span><span class="sxs-lookup"><span data-stu-id="132ed-115">Devices that are Windows Server Update Services (WSUS) or Windows Update for Business (WUfB) managed will be excluded from this automatic Windows Update, but may receive the new Microsoft Edge (Chromium-based) through their organization.</span></span>

**<span data-ttu-id="132ed-116">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="132ed-116">It's important to note that:</span></span>**

- <span data-ttu-id="132ed-117">Blocker Toolkit を有効にしても、ユーザーはインターネットのダウンロードまたは外部メディアから Microsoft Edge (Chromium ベース) を手動でインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="132ed-117">The Blocker Toolkit will not prevent users from manually installing Microsoft Edge (Chromium-based) from Internet download, or from external media.</span></span>
- <span data-ttu-id="132ed-118">Windows Update for Business (WUfB) を通じて更新プログラムが管理されている組織では、この更新プログラムを自動的に受信することはありません。また、Blocker Toolkit を展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="132ed-118">Organizations with updates managed through Windows Update for Business (WUfB) will not automatically receive this update and do not need to deploy the blocker toolkit.</span></span>
- <span data-ttu-id="132ed-119">組織の環境が Windows Server Update Services (WSUS) や System Center Configuration Manager (SCCM) などの更新管理ソリューションで管理されている場合、Blocker Toolkit を展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="132ed-119">Organizations with environments managed with an update management solution such as Windows Server Update Services (WSUS) or System Center Configuration Manager (SCCM) do not have to deploy the Blocker Toolkit.</span></span> <span data-ttu-id="132ed-120">これらの製品を使用して、環境内で Windows Update と Microsoft Update を通じてリリースされた更新プログラム (新しい Microsoft Edge の [WSUS](https://support.microsoft.com/help/4584642/update-in-wsus-for-the-new-microsoft-edge)の更新プログラムを含む) の展開を完全に管理できます。</span><span class="sxs-lookup"><span data-stu-id="132ed-120">They can use those products to fully manage deployment of updates released through Windows Update and Microsoft Update, including the [Update in WSUS for the new Microsoft Edge](https://support.microsoft.com/help/4584642/update-in-wsus-for-the-new-microsoft-edge), within their environment.</span></span>
- <span data-ttu-id="132ed-121">この更新プログラムは、エンタープライズ ユーザーがこの更新プログラムの展開を柔軟かつ最大限に制御できるように、スタンドアロンの更新プログラムとして提供されます (月例の累積的な更新プログラムの一部ではありません)。</span><span class="sxs-lookup"><span data-stu-id="132ed-121">This update is a stand-alone update (not part of the monthly cumulative update) to give Enterprise customers flexibility and maximum control over deploying this update.</span></span>
- <span data-ttu-id="132ed-122">新しい Microsoft Edge (Chromium ベース) は、2020 年後半に Windows 10 バージョン 20H2 の機能更新プログラムの一部として含まれています。</span><span class="sxs-lookup"><span data-stu-id="132ed-122">The new Microsoft Edge (Chromium-based) is included as part of the Windows 10, version 20H2 feature update in the second half of 2020.</span></span> <span data-ttu-id="132ed-123">Blocker Toolkit は、20H2 の動作や展開に影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="132ed-123">The Blocker toolkit does not impact 20H2 behaviors or deployment.</span></span> <span data-ttu-id="132ed-124">Windows 10 バージョン 20H2 の詳細については、[こちら](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="132ed-124">See more information about Windows 10, version 20H2 [here](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/).</span></span>

<span data-ttu-id="132ed-125">Blocker Toolkit の実行可能ファイルは、[https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe) からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="132ed-125">You can download the Blocker Toolkit executable file from [https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe).</span></span>

### <span data-ttu-id="132ed-126">Toolkit のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="132ed-126">Toolkit components</span></span>

<span data-ttu-id="132ed-127">この Toolkit には、次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="132ed-127">This toolkit contains the following components:</span></span>

- <span data-ttu-id="132ed-128">実行可能な Blocker スクリプト (.CMD)</span><span class="sxs-lookup"><span data-stu-id="132ed-128">Executable blocker script (.CMD)</span></span>
- <span data-ttu-id="132ed-129">グループ ポリシー管理用テンプレート (.ADMX および .ADML)</span><span class="sxs-lookup"><span data-stu-id="132ed-129">Group Policy Administrative Template (.ADMX and .ADML)</span></span>

### <span data-ttu-id="132ed-130">サポートされるオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="132ed-130">Supported Operating Systems</span></span>

<span data-ttu-id="132ed-131">Windows 10 Version 1803 以降。</span><span class="sxs-lookup"><span data-stu-id="132ed-131">Windows 10 version 1803 and newer.</span></span>

## <span data-ttu-id="132ed-132">Blocker スクリプト</span><span class="sxs-lookup"><span data-stu-id="132ed-132">Blocker script</span></span>

<span data-ttu-id="132ed-133">このスクリプトは、レジストリキーを作成し、関連する値を設定することにより、ローカル コンピューターまたはリモート ターゲット コンピューターで、Microsoft Edge (Chromium ベース) の自動配信を (使用するコマンド ライン オプションに応じて) ブロックまたはブロック解除します。</span><span class="sxs-lookup"><span data-stu-id="132ed-133">The script creates a registry key and sets the associated value to block or unblock (depending on the command-line option used) automatic delivery of Microsoft Edge (Chromium-based) on either the local machine or a remote target machine.</span></span>

**<span data-ttu-id="132ed-134">レジストリ キー:</span><span class="sxs-lookup"><span data-stu-id="132ed-134">Registry key:</span></span>** `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate`<br>
**<span data-ttu-id="132ed-135">キーの値の名前:</span><span class="sxs-lookup"><span data-stu-id="132ed-135">Key value name:</span></span>** `DoNotUpdateToEdgeWithChromium`

| <span data-ttu-id="132ed-136">値</span><span class="sxs-lookup"><span data-stu-id="132ed-136">Value</span></span>                | <span data-ttu-id="132ed-137">結果</span><span class="sxs-lookup"><span data-stu-id="132ed-137">Result</span></span>                         |
|----------------------|--------------------------------|
| *<span data-ttu-id="132ed-138">キーが定義されていない</span><span class="sxs-lookup"><span data-stu-id="132ed-138">Key is not defined</span></span>* | <span data-ttu-id="132ed-139">配布はブロック*されません*。</span><span class="sxs-lookup"><span data-stu-id="132ed-139">Distribution is *not* blocked.</span></span> |
| <span data-ttu-id="132ed-140">0</span><span class="sxs-lookup"><span data-stu-id="132ed-140">0</span></span>                    | <span data-ttu-id="132ed-141">配布はブロック*されません*。</span><span class="sxs-lookup"><span data-stu-id="132ed-141">Distribution is *not* blocked.</span></span> |
| <span data-ttu-id="132ed-142">1</span><span class="sxs-lookup"><span data-stu-id="132ed-142">1</span></span>                    | <span data-ttu-id="132ed-143">配布はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="132ed-143">Distribution is blocked.</span></span>       |

<span data-ttu-id="132ed-144">このスクリプトのコマンド ライン構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="132ed-144">The script has the following command-line syntax:</span></span><br>
`EdgeChromium_Blocker.cmd [<machine name>] [/B] [/U] [/H]`

### <span data-ttu-id="132ed-145">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="132ed-145">Machine name</span></span>

<span data-ttu-id="132ed-146">`<machine name>` パラメーターはオプションです。</span><span class="sxs-lookup"><span data-stu-id="132ed-146">The `<machine name>` parameter is optional.</span></span> <span data-ttu-id="132ed-147">指定しない場合、アクションはローカル コンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="132ed-147">If not specified, the action is performed on the local machine.</span></span> <span data-ttu-id="132ed-148">それ以外の場合は、`REG` コマンドのリモート レジストリ機能を通じてリモート コンピューターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="132ed-148">Otherwise, the remote machine is accessed through the remote registry capabilities of the `REG` command.</span></span> <span data-ttu-id="132ed-149">セキュリティのアクセス許可が原因でリモート レジストリにアクセスできない場合、またはリモート コンピューターが見つからない場合は、`REG` コマンドからエラー メッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="132ed-149">If the remote registry can't be accessed due to security permissions or the remote machine can't be found, an error message is returned from the `REG` command.</span></span>

### <span data-ttu-id="132ed-150">スイッチ</span><span class="sxs-lookup"><span data-stu-id="132ed-150">Switches</span></span>

<span data-ttu-id="132ed-151">スクリプトで使用されるスイッチは相互に排他的であり、特定のコマンドからの最初の有効なスイッチのみが処理されます。</span><span class="sxs-lookup"><span data-stu-id="132ed-151">Switches used by the script are mutually exclusive and only the first valid switch from a given command is acted on.</span></span> <span data-ttu-id="132ed-152">同じコンピューターでスクリプトを複数回実行することができます。</span><span class="sxs-lookup"><span data-stu-id="132ed-152">The script can be run multiple times on the same machine.</span></span>

| <span data-ttu-id="132ed-153">スイッチ</span><span class="sxs-lookup"><span data-stu-id="132ed-153">Switch</span></span>       | <span data-ttu-id="132ed-154">説明</span><span class="sxs-lookup"><span data-stu-id="132ed-154">Description</span></span>                              |
|--------------|------------------------------------------|
| `/B`         | <span data-ttu-id="132ed-155">配布をブロックします。</span><span class="sxs-lookup"><span data-stu-id="132ed-155">Blocks distribution</span></span>                      |
| `/U`         | <span data-ttu-id="132ed-156">配布をブロック解除します。</span><span class="sxs-lookup"><span data-stu-id="132ed-156">Unblocks distribution</span></span>                    |
| `/H` <span data-ttu-id="132ed-157">または</span><span class="sxs-lookup"><span data-stu-id="132ed-157">or</span></span> `/?` | <span data-ttu-id="132ed-158">次の概要ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="132ed-158">Displays the following summary help:</span></span><br>`This tool can be used to remotely block or unblock the delivery of Microsoft Edge (Chromium-based) through Automatic Updates.`<br> `Usage:`<br>`EdgeChromium_Blocker.cmd [<machine name>] [/B][/U][/H]`<br>`B = Block Microsoft Edge (Chromium-based) deployment`<br>`U = Allow Microsoft Edge (Chromium-based) deployment`<br>`H = Help`<br>`Examples:`<br>`EdgeChromium_Blocker.cmd mymachine /B (blocks delivery on machine "mymachine")`<br>`EdgeChromium_Blocker.cmd /U (unblocks delivery on the local machine)`<br> |

## <span data-ttu-id="132ed-159">グループ ポリシー管理用テンプレート (.ADMX および .ADML ファイル)</span><span class="sxs-lookup"><span data-stu-id="132ed-159">Group Policy Administrative Template (.ADMX and .ADML files)</span></span>

<span data-ttu-id="132ed-160">管理者は、グループ ポリシー管理用テンプレート (.ADMX および .ADML ファイル) を使用することによって、新しいグループ ポリシー設定をインポートして、グループ ポリシー環境への Microsoft Edge (Chromium ベース) の自動配布をブロックまたはブロック解除することができます。また、グループ ポリシーを使用して、環境内のシステム全体に一元的にアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="132ed-160">The Group Policy Administrative Template (.ADMX  and .ADML files) allows administrators to import the new Group Policy settings to block or unblock automatic delivery of Microsoft Edge (Chromium-based) into their Group Policy environment, and use Group Policy to centrally execute the action across systems in their environment.</span></span>

<span data-ttu-id="132ed-161">ユーザーが Windows 10 RS3 Enterprise/EDU および RS4 以降を実行している場合、このポリシーは次のパスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="132ed-161">Users running Windows 10 RS3 Enterprise/EDU and RS4 and newer, will see the policy under the following path:</span></span>

```
/Computer Configuration  
  /Administrative Templates
    /Classic Administrative Templates
      /Windows Components
        /Windows Update  
          /Microsoft Edge (Chromium-based) Blockers  
```

<span data-ttu-id="132ed-162">この設定は、コンピューターの設定としてのみ使用できます。ユーザーごとの設定はありません。</span><span class="sxs-lookup"><span data-stu-id="132ed-162">This setting is available only as a Computer setting; there is no Per-User setting.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="132ed-163">このレジストリ設定は、ポリシー キーに格納されていないため、*優先設定*と見なされます。</span><span class="sxs-lookup"><span data-stu-id="132ed-163">This registry setting isn't stored in a policies key and is considered a *preference*.</span></span> <span data-ttu-id="132ed-164">したがって、設定を実装するグループ ポリシーオブジェクトが削除された場合や、ポリシーが **[未構成]** に設定されている場合、設定はそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="132ed-164">Therefore, if the Group Policy Object that implements the setting is ever removed or the policy is set to **Not Configured**, the setting will remain.</span></span> <span data-ttu-id="132ed-165">グループ ポリシーを使用して Microsoft Edge (Chromium ベース) の配布をブロック解除するには、ポリシーを **[無効]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="132ed-165">To unblock distribution of Microsoft Edge (Chromium-based) by using Group Policy, set the policy to **Disabled**.</span></span>

## <span data-ttu-id="132ed-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="132ed-166">See also</span></span>

- [<span data-ttu-id="132ed-167">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="132ed-167">Microsoft Edge Enterprise landing page</span></span>](https://www.microsoftedgeinsider.com/enterprise)
- [<span data-ttu-id="132ed-168">Microsoft Edge をサポートする Windows 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="132ed-168">Windows updates to support Microsoft Edge</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)
- [<span data-ttu-id="132ed-169">旧バージョンの Microsoft Edge にアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="132ed-169">How to access the old version of Microsoft Edge</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-access-old-edge)
