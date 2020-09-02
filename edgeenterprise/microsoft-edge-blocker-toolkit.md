---
title: Microsoft Edge の自動配布を無効にするための Blocker Toolkit
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 06/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge の自動配布を無効にするための Blocker Toolkit
ms.openlocfilehash: 7563d2c94cf91a8434328699e46c75dbcfb77561
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980515"
---
# <span data-ttu-id="89104-103">Microsoft Edge (Chromium ベース) の自動配布を無効にするための Blocker Toolkit</span><span class="sxs-lookup"><span data-stu-id="89104-103">Blocker Toolkit to disable automatic delivery of Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="89104-104">この記事では、Microsoft Edge の自動配布とインストールを無効にするための Blocker Toolkit について説明します。</span><span class="sxs-lookup"><span data-stu-id="89104-104">This article describes the Blocker Toolkit for disabling automatic delivery and installation of Microsoft Edge.</span></span> <span data-ttu-id="89104-105">この記事は **2020/1/09** に無効化ツールキットの使用を必要とする可能性のあるデバイスに関する詳細情報が更新され、**2020/2/28** にこの自動更新から除外されるデバイスの基準から「MDM で管理」を削除しました。また、**2020/6/30** に、すべての Windows Update に接続されたデバイスがこの更新プログラムを受信する範囲にあることを反映しました (2020 年 7 月 30 日まで有効)。</span><span class="sxs-lookup"><span data-stu-id="89104-105">This article was updated on **01/09/2020** with more information about devices that might require you to use the Blocker Toolkit, on **2/28/2020** to remove "MDM managed" from the criteria of devices to be excluded from this automatic update, and on **6/30/2020** to reflect that all Windows Update connected devices are in scope to receive this update (effective no sooner than 7/30/2020).</span></span>

> [!NOTE]
> <span data-ttu-id="89104-106">この記事は、Microsoft Edge Stable チャネルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="89104-106">This applies to Microsoft Edge Stable channel.</span></span>

## <span data-ttu-id="89104-107">概要</span><span class="sxs-lookup"><span data-stu-id="89104-107">Overview</span></span>

<span data-ttu-id="89104-108">お客様のセキュリティを強化し、最新の状態に保つために、Microsoft ではWindows 10 バージョン 1803 以降を実行しているすべての Windows Update で接続されたデバイスに Microsoft Edge (Chromium ベース) を配布します。</span><span class="sxs-lookup"><span data-stu-id="89104-108">To help our customers become more secure and up-to-date, Microsoft will distribute Microsoft Edge (Chromium-based) to all Windows Update-connected devices running Windows 10 version 1803 and newer.</span></span> <span data-ttu-id="89104-109">このプロセスは、2020 年 1 月 15 日以降に開始され、詳しい情報は当日提供されます。</span><span class="sxs-lookup"><span data-stu-id="89104-109">This process will start after January 15, 2020 and more information will be available on that date.</span></span>

<span data-ttu-id="89104-110">Blocker Toolkit は、Windows 10 バージョン 1803 以降を実行している Windows Update で接続されたデバイスへの Microsoft Edge (Chromium ベース) の自動配信をブロックする組織を対象としています。</span><span class="sxs-lookup"><span data-stu-id="89104-110">The Blocker Toolkit is intended for organizations that would like to block automatic delivery of Microsoft Edge (Chromium-based) to Windows Updated-connected devices running Windows 10 version 1803 and newer.</span></span>
<span data-ttu-id="89104-111">Windows Server Update Services (WSUS) または Windows Update for Business (WUfB) で管理されているデバイスは、この自動更新から除外されます。</span><span class="sxs-lookup"><span data-stu-id="89104-111">Devices that are Windows Server Update Services (WSUS) or Windows Update for Business (WUfB) managed will be excluded from this automatic update.</span></span>

**<span data-ttu-id="89104-112">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="89104-112">It's important to note that:</span></span>**

- <span data-ttu-id="89104-113">Blocker Toolkit を有効にしても、ユーザーはインターネットのダウンロードまたは外部メディアから Microsoft Edge (Chromium ベース) を手動でインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="89104-113">The Blocker Toolkit will not prevent users from manually installing Microsoft Edge (Chromium-based) from Internet download, or from external media.</span></span>
- <span data-ttu-id="89104-114">Windows Update for Business (WUfB) を通じて更新プログラムが管理されている組織では、この更新プログラムを自動的に受信することはありません。また、Blocker Toolkit を展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="89104-114">Organizations with updates managed through Windows Update for Business (WUfB) will not automatically receive this update and do not need to deploy the blocker toolkit.</span></span>
- <span data-ttu-id="89104-115">組織の環境が Windows Server Update Services (WSUS) や System Center Configuration Manager (SCCM) などの更新管理ソリューションで管理されている場合、Blocker Toolkit を展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="89104-115">Organizations with environments managed with an update management solution such as Windows Server Update Services (WSUS) or System Center Configuration Manager (SCCM) do not have to deploy the Blocker Toolkit.</span></span> <span data-ttu-id="89104-116">組織では、これらの製品を使用することで、環境内で、Windows Update および Microsoft Update を介してリリースされた、Microsoft Edge (Chromium ベース) を含む更新プログラムの展開を完全に管理できます。</span><span class="sxs-lookup"><span data-stu-id="89104-116">They can use those products to fully manage deployment of updates released through Windows Update and Microsoft Update, including Microsoft Edge (Chromium-based), within their environment.</span></span>
- <span data-ttu-id="89104-117">この更新プログラムは、エンタープライズ ユーザーがこの更新プログラムの展開を柔軟かつ最大限に制御できるように、スタンドアロンの更新プログラムとして提供されます (月例の累積的な更新プログラムの一部ではありません)。</span><span class="sxs-lookup"><span data-stu-id="89104-117">This update is a stand-alone update (not part of the monthly cumulative update) to give Enterprise customers flexibility and maximum control over deploying this update.</span></span>
- <span data-ttu-id="89104-118">新しい Microsoft Edge (Chromium ベース) は、2020 年の後半に Windows 10 バージョン 20H2 機能更新の一部として含まれる予定です。</span><span class="sxs-lookup"><span data-stu-id="89104-118">The new Microsoft Edge (Chromium-based) will be included as part of the Windows 10, version 20H2 feature update in the second half of 2020.</span></span> <span data-ttu-id="89104-119">Blocker Toolkit は、20H2 の動作や展開に影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="89104-119">The Blocker toolkit does not impact 20H2 behaviors or deployment.</span></span> <span data-ttu-id="89104-120">Windows 10 バージョン 20H2 の詳細については、[こちら](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89104-120">See more information about Windows 10, version 20H2 [here](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/).</span></span>

<span data-ttu-id="89104-121">Blocker Toolkit の実行可能ファイルは、[https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe) からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="89104-121">You can download the Blocker Toolkit executable file from [https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe).</span></span>

### <span data-ttu-id="89104-122">Toolkit のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="89104-122">Toolkit components</span></span>

<span data-ttu-id="89104-123">この Toolkit には、次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="89104-123">This toolkit contains the following components:</span></span>

- <span data-ttu-id="89104-124">実行可能な Blocker スクリプト (.CMD)</span><span class="sxs-lookup"><span data-stu-id="89104-124">Executable blocker script (.CMD)</span></span>
- <span data-ttu-id="89104-125">グループ ポリシー管理用テンプレート (.ADMX および .ADML)</span><span class="sxs-lookup"><span data-stu-id="89104-125">Group Policy Administrative Template (.ADMX and .ADML)</span></span>

### <span data-ttu-id="89104-126">サポートされるオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="89104-126">Supported Operating Systems</span></span>

<span data-ttu-id="89104-127">Windows 10 Version 1803 以降。</span><span class="sxs-lookup"><span data-stu-id="89104-127">Windows 10 version 1803 and newer.</span></span>

## <span data-ttu-id="89104-128">Blocker スクリプト</span><span class="sxs-lookup"><span data-stu-id="89104-128">Blocker script</span></span>

<span data-ttu-id="89104-129">このスクリプトは、レジストリキーを作成し、関連する値を設定することにより、ローカル コンピューターまたはリモート ターゲット コンピューターで、Microsoft Edge (Chromium ベース) の自動配信を (使用するコマンド ライン オプションに応じて) ブロックまたはブロック解除します。</span><span class="sxs-lookup"><span data-stu-id="89104-129">The script creates a registry key and sets the associated value to block or unblock (depending on the command-line option used) automatic delivery of Microsoft Edge (Chromium-based) on either the local machine or a remote target machine.</span></span>

**<span data-ttu-id="89104-130">レジストリ キー:</span><span class="sxs-lookup"><span data-stu-id="89104-130">Registry key:</span></span>** `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate`<br>
**<span data-ttu-id="89104-131">キーの値の名前:</span><span class="sxs-lookup"><span data-stu-id="89104-131">Key value name:</span></span>** `DoNotUpdateToEdgeWithChromium`

| <span data-ttu-id="89104-132">値</span><span class="sxs-lookup"><span data-stu-id="89104-132">Value</span></span>                | <span data-ttu-id="89104-133">結果</span><span class="sxs-lookup"><span data-stu-id="89104-133">Result</span></span>                         |
|----------------------|--------------------------------|
| *<span data-ttu-id="89104-134">キーが定義されていない</span><span class="sxs-lookup"><span data-stu-id="89104-134">Key is not defined</span></span>* | <span data-ttu-id="89104-135">配布はブロック*されません*。</span><span class="sxs-lookup"><span data-stu-id="89104-135">Distribution is *not* blocked.</span></span> |
| <span data-ttu-id="89104-136">0</span><span class="sxs-lookup"><span data-stu-id="89104-136">0</span></span>                    | <span data-ttu-id="89104-137">配布はブロック*されません*。</span><span class="sxs-lookup"><span data-stu-id="89104-137">Distribution is *not* blocked.</span></span> |
| <span data-ttu-id="89104-138">1</span><span class="sxs-lookup"><span data-stu-id="89104-138">1</span></span>                    | <span data-ttu-id="89104-139">配布はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="89104-139">Distribution is blocked.</span></span>       |

<span data-ttu-id="89104-140">このスクリプトのコマンド ライン構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="89104-140">The script has the following command-line syntax:</span></span><br>
`EdgeChromium_Blocker.cmd [<machine name>] [/B] [/U] [/H]`

### <span data-ttu-id="89104-141">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="89104-141">Machine name</span></span>

<span data-ttu-id="89104-142">`<machine name>` パラメーターはオプションです。</span><span class="sxs-lookup"><span data-stu-id="89104-142">The `<machine name>` parameter is optional.</span></span> <span data-ttu-id="89104-143">指定しない場合、アクションはローカル コンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="89104-143">If not specified, the action is performed on the local machine.</span></span> <span data-ttu-id="89104-144">それ以外の場合は、`REG` コマンドのリモート レジストリ機能を通じてリモート コンピューターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="89104-144">Otherwise, the remote machine is accessed through the remote registry capabilities of the `REG` command.</span></span> <span data-ttu-id="89104-145">セキュリティのアクセス許可が原因でリモート レジストリにアクセスできない場合、またはリモート コンピューターが見つからない場合は、`REG` コマンドからエラー メッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="89104-145">If the remote registry can't be accessed due to security permissions or the remote machine can't be found, an error message is returned from the `REG` command.</span></span>

### <span data-ttu-id="89104-146">スイッチ</span><span class="sxs-lookup"><span data-stu-id="89104-146">Switches</span></span>

<span data-ttu-id="89104-147">スクリプトで使用されるスイッチは相互に排他的であり、特定のコマンドからの最初の有効なスイッチのみが処理されます。</span><span class="sxs-lookup"><span data-stu-id="89104-147">Switches used by the script are mutually exclusive and only the first valid switch from a given command is acted on.</span></span> <span data-ttu-id="89104-148">同じコンピューターでスクリプトを複数回実行することができます。</span><span class="sxs-lookup"><span data-stu-id="89104-148">The script can be run multiple times on the same machine.</span></span>

| <span data-ttu-id="89104-149">スイッチ</span><span class="sxs-lookup"><span data-stu-id="89104-149">Switch</span></span>       | <span data-ttu-id="89104-150">説明</span><span class="sxs-lookup"><span data-stu-id="89104-150">Description</span></span>                              |
|--------------|------------------------------------------|
| `/B`         | <span data-ttu-id="89104-151">配布をブロックします。</span><span class="sxs-lookup"><span data-stu-id="89104-151">Blocks distribution</span></span>                      |
| `/U`         | <span data-ttu-id="89104-152">配布をブロック解除します。</span><span class="sxs-lookup"><span data-stu-id="89104-152">Unblocks distribution</span></span>                    |
| `/H` <span data-ttu-id="89104-153">または</span><span class="sxs-lookup"><span data-stu-id="89104-153">or</span></span> `/?` | <span data-ttu-id="89104-154">次の概要ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="89104-154">Displays the following summary help:</span></span><br>`This tool can be used to remotely block or unblock the delivery of Microsoft Edge (Chromium-based) through Automatic Updates.`<br> `Usage:`<br>`EdgeChromium_Blocker.cmd [<machine name>] [/B][/U][/H]`<br>`B = Block Microsoft Edge (Chromium-based) deployment`<br>`U = Allow Microsoft Edge (Chromium-based) deployment`<br>`H = Help`<br>`Examples:`<br>`EdgeChromium_Blocker.cmd mymachine /B (blocks delivery on machine "mymachine")`<br>`EdgeChromium_Blocker.cmd /U (unblocks delivery on the local machine)`<br> |

## <span data-ttu-id="89104-155">グループ ポリシー管理用テンプレート (.ADMX および .ADML ファイル)</span><span class="sxs-lookup"><span data-stu-id="89104-155">Group Policy Administrative Template (.ADMX and .ADML files)</span></span>

<span data-ttu-id="89104-156">管理者は、グループ ポリシー管理用テンプレート (.ADMX および .ADML ファイル) を使用することによって、新しいグループ ポリシー設定をインポートして、グループ ポリシー環境への Microsoft Edge (Chromium ベース) の自動配布をブロックまたはブロック解除することができます。また、グループ ポリシーを使用して、環境内のシステム全体に一元的にアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="89104-156">The Group Policy Administrative Template (.ADMX  and .ADML files) allows administrators to import the new Group Policy settings to block or unblock automatic delivery of Microsoft Edge (Chromium-based) into their Group Policy environment, and use Group Policy to centrally execute the action across systems in their environment.</span></span>

<span data-ttu-id="89104-157">ユーザーが Windows 10 RS3 Enterprise/EDU および RS4 以降を実行している場合、このポリシーは次のパスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="89104-157">Users running Windows 10 RS3 Enterprise/EDU and RS4 and newer, will see the policy under the following path:</span></span>

```
/Computer Configuration  
  /Administrative Templates
    /Classic Administrative Templates
      /Windows Components
        /Windows Update  
          /Microsoft Edge (Chromium-based) Blockers  
```

<span data-ttu-id="89104-158">この設定は、コンピューターの設定としてのみ使用できます。ユーザーごとの設定はありません。</span><span class="sxs-lookup"><span data-stu-id="89104-158">This setting is available only as a Computer setting; there is no Per-User setting.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89104-159">このレジストリ設定は、ポリシー キーに格納されていないため、*優先設定*と見なされます。</span><span class="sxs-lookup"><span data-stu-id="89104-159">This registry setting isn't stored in a policies key and is considered a *preference*.</span></span> <span data-ttu-id="89104-160">したがって、設定を実装するグループ ポリシーオブジェクトが削除された場合や、ポリシーが **[未構成]** に設定されている場合、設定はそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="89104-160">Therefore, if the Group Policy Object that implements the setting is ever removed or the policy is set to **Not Configured**, the setting will remain.</span></span> <span data-ttu-id="89104-161">グループ ポリシーを使用して Microsoft Edge (Chromium ベース) の配布をブロック解除するには、ポリシーを **[無効]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="89104-161">To unblock distribution of Microsoft Edge (Chromium-based) by using Group Policy, set the policy to **Disabled**.</span></span>

## <span data-ttu-id="89104-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="89104-162">See also</span></span>

- [<span data-ttu-id="89104-163">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="89104-163">Microsoft Edge Enterprise landing page</span></span>](https://www.microsoftedgeinsider.com/enterprise)
- [<span data-ttu-id="89104-164">Microsoft Edge をサポートする Windows 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="89104-164">Windows updates to support Microsoft Edge</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)
- [<span data-ttu-id="89104-165">旧バージョンの Microsoft Edge にアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="89104-165">How to access the old version of Microsoft Edge</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-access-old-edge)
