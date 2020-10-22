---
title: 旧バージョンの Microsoft Edge にアクセスする
ms.author: jtkim
author: dan-wesley
manager: srugh
ms.date: 08/17/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: レガシ バージョンの Microsoft Edge にアクセスする方法について説明します。
ms.openlocfilehash: e4733d020f3a681ded50e5a087fe086d39362201
ms.sourcegitcommit: f7f7eb69d2298b0f9779a9fd28e3c4e297ef2e05
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125519"
---
# <span data-ttu-id="5837f-103">Microsoft Edge の新しいバージョンをインストールした後 Microsoft Edge レガシにアクセスする</span><span class="sxs-lookup"><span data-stu-id="5837f-103">Access Microsoft Edge Legacy after installing the new version of Microsoft Edge</span></span>

<span data-ttu-id="5837f-104">Microsoft Edge の新しいバージョンをインストールした後 Microsoft Edge レガシにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5837f-104">Learn how to access Microsoft Edge Legacy after installing the new version of Microsoft Edge.</span></span>

> [!NOTE]
> <span data-ttu-id="5837f-105">この記事は、Microsoft Edge [Stable チャネル](microsoft-edge-channels.md)に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5837f-105">This article applies to the Microsoft Edge [Stable channel](microsoft-edge-channels.md).</span></span>

<span data-ttu-id="5837f-106">ほとんどの組織では Microsoft Edge レガシを新しいバージョンに置き換えることが推奨されますが、ユーザーが両方のバージョンにアクセスする必要がある状況が考えられます。</span><span class="sxs-lookup"><span data-stu-id="5837f-106">While most organizations will want to replace Microsoft Edge Legacy with the new version, there are some situations where users will need access to both versions.</span></span> <span data-ttu-id="5837f-107">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="5837f-107">For example:</span></span>

- <span data-ttu-id="5837f-108">Microsoft Edge のいずれかまたは両方のバージョンを使用しているユーザーとやり取りするヘルプデスクとサポートのスタッフ。</span><span class="sxs-lookup"><span data-stu-id="5837f-108">Helpdesk and support staff who interact with users who are using either or both versions of Microsoft Edge.</span></span>
- <span data-ttu-id="5837f-109">Microsoft Edge のいずれかまたは両方のバージョンを使用している顧客をサポートする開発者。</span><span class="sxs-lookup"><span data-stu-id="5837f-109">Developers who support customers who are using either or both versions of Microsoft Edge.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5837f-110">運用環境で Microsoft Edge 従来版を Microsoft Edge の新しいバージョンと同時に実行することは推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="5837f-110">Running Microsoft Edge Legacy side-by-side with the new version of Microsoft Edge is not recommended for use in production.</span></span> <span data-ttu-id="5837f-111">この構成は、両方のバージョンのブラウザーのテストが必要な特別なケースでのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="5837f-111">This configuration should only be used in specific cases where testing with both browser versions is required.</span></span>
>
> <span data-ttu-id="5837f-112">Microsoft Edge 従来版のデスクトップ アプリのサポートは 2021 年 3 月 9 日に終了し、新しい Microsoft Edge に完全に移行します。</span><span class="sxs-lookup"><span data-stu-id="5837f-112">The Microsoft Edge Legacy desktop app will reach end of support on March 9, 2021 in favor of the new Microsoft Edge.</span></span> <span data-ttu-id="5837f-113">つまり、この日以降、Microsoft Edge 従来版にはセキュリティ更新プログラムが送信されなくなります。</span><span class="sxs-lookup"><span data-stu-id="5837f-113">This means that Microsoft Edge Legacy will not receive security updates after that date.</span></span> <span data-ttu-id="5837f-114">この変更は、Microsoft Edge 従来版のデスクトップ アプリで実行されるすべてのエクスペリエンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5837f-114">This change is applicable to all experiences that run in the Microsoft Edge Legacy desktop app.</span></span> <span data-ttu-id="5837f-115">[詳しくはこちらをご覧ください](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666)。</span><span class="sxs-lookup"><span data-stu-id="5837f-115">[Learn more](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666).</span></span>

## <span data-ttu-id="5837f-116">始める前に</span><span class="sxs-lookup"><span data-stu-id="5837f-116">Before you begin</span></span>
> [!NOTE]
> <span data-ttu-id="5837f-117">Windows 10 バージョン 20H2 から、Microsoft Edge 従来版は含まれなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5837f-117">Starting with Windows 10 version 20H2 Microsoft Edge Legacy is no longer included.</span></span> <span data-ttu-id="5837f-118">Windows 10 のこのバージョンから、並べて表示エクスペリエンスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5837f-118">Starting with this version of Windows 10 the side-by-side experience is not supported.</span></span>

<span data-ttu-id="5837f-119">この記事の手順は、最新のセキュリティ更新プログラムで更新されたシステムに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5837f-119">The procedures in this article apply to systems that have been updated with the latest security updates.</span></span> <span data-ttu-id="5837f-120">Microsoft Edge の新しいバージョンがインストールされると、古いバージョン (Microsoft Edge レガシ) が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="5837f-120">When the new version of Microsoft Edge is installed, the old version (Microsoft Edge Legacy) will be hidden.</span></span> <span data-ttu-id="5837f-121">既定では、ユーザーが古いバージョンを起動しようとすると常に、新しくインストールされたバージョンの Microsoft Edge にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="5837f-121">By default, all attempts to launch the old version will redirect the user to the newly installed version of Microsoft Edge.</span></span> <span data-ttu-id="5837f-122">この記事では、Microsoft Edge をインストールした後も Microsoft Edge レガシを引き続き使用できるようにする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5837f-122">This article describes how you can keep using Microsoft Edge Legacy after you install Microsoft Edge.</span></span>

## <span data-ttu-id="5837f-123">クイック スタート: Microsoft Edge Beta チャネルと Microsoft Edge 従来版の同時実行エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="5837f-123">Quickstart: Side-by-side experience with Microsoft Edge Beta Channel and Microsoft Edge Legacy</span></span>

<span data-ttu-id="5837f-124">この記事の詳細な手順を実行する前に、ユーザーが Microsoft Edge 従来版と Microsoft Edge [Beta チャネル](microsoft-edge-channels.md)を同時に実行できるようにするために、次の 2 つの手順を実行することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="5837f-124">Before using the detailed instructions in this article, consider the following two steps to let your users run Microsoft Edge Legacy and the Microsoft Edge [Beta channel](microsoft-edge-channels.md) side-by-side.</span></span>

1. <span data-ttu-id="5837f-125">Microsoft Edge の Stable チャネルが [Windows Update](https://support.microsoft.com/help/12373/windows-update-faq) で自動的にインストールされないように対策を講じます。</span><span class="sxs-lookup"><span data-stu-id="5837f-125">Prevent the automatic install of the Stable Channel of Microsoft Edge by [Windows Update](https://support.microsoft.com/help/12373/windows-update-faq).</span></span>

   > [!TIP]
   > <span data-ttu-id="5837f-126">[Blocker Toolkit](microsoft-edge-blocker-toolkit.md) を使用すると、Microsoft Edge の自動配布を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="5837f-126">Use the [Blocker Toolkit](microsoft-edge-blocker-toolkit.md) to disable automatic delivery of Microsoft Edge.</span></span>

2. <span data-ttu-id="5837f-127">新しいバージョンの Microsoft Edge の[Beta チャネル](https://www.microsoft.com/edge/business/download)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5837f-127">Install the [Beta channel](https://www.microsoft.com/edge/business/download) of the new version of Microsoft Edge.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5837f-128">レジストリ キー設定の詳細については、「[追加情報](#additional-information)」参照してください。</span><span class="sxs-lookup"><span data-stu-id="5837f-128">Read [Additional information](#additional-information) for information about Registry Key settings.</span></span>

<span data-ttu-id="5837f-129">この同時実行ソリューションは、この記事で説明する詳細な解決方法に比べてシンプルで、管理作業も少なくて済みます。</span><span class="sxs-lookup"><span data-stu-id="5837f-129">This side-by-side solution is less complex and requires less management than the detailed solution described in this article.</span></span> <span data-ttu-id="5837f-130">ただし、このソリューションは、Stable チャネルより Beta チャネルを実行する方が望ましいという意味ではありません。</span><span class="sxs-lookup"><span data-stu-id="5837f-130">However, this solution does mean that you'll be running the Beta Channel rather than the Stable Channel.</span></span>

## <span data-ttu-id="5837f-131">Microsoft Edge Stable チャネルと Microsoft Edge 従来版の同時実行エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="5837f-131">Side-by-side experience with Microsoft Edge Stable Channel and Microsoft Edge Legacy</span></span>

<span data-ttu-id="5837f-132">次のバージョンの Microsoft Edge の Stable チャネルをシステムレベルでインストールすると、現在のバージョン (Microsoft Edge レガシ) が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="5837f-132">Installing the Stable Channel of the next version of Microsoft Edge at the system-level will cause the current version (Microsoft Edge Legacy) to be hidden.</span></span> <span data-ttu-id="5837f-133">Windows で Microsoft Edge の両方のバージョンの同時実行をユーザーに許可する場合は、[**Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する**] グループ ポリシーを [**有効**] に設定すると、このエクスペリエンスを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="5837f-133">If you want to let your users see both versions of Microsoft Edge side by side in Windows, you can enable this experience by setting the **Allow Microsoft Edge Side by Side browser experience** group policy to **Enabled**.</span></span>

<span data-ttu-id="5837f-134">このグループポリシーについては、[こちら](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5837f-134">This group policy is documented [here](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs)</span></span>

### <span data-ttu-id="5837f-135">ブラウザーの同時実行エクスペリエンスをセットアップするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5837f-135">To set up the side-by-side browser experience policy:</span></span>

1. <span data-ttu-id="5837f-136">[Microsoft Edge For Business](https://www.microsoft.com/edge/business/download) からポリシー定義をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5837f-136">Install the Policy Definitions from [Microsoft Edge for Business](https://www.microsoft.com/edge/business/download).</span></span>

   - <span data-ttu-id="5837f-137">使用する CHANNEL/BUILD および PLATFORM を選択し、[GET POLICY FILES] (ポリシー ファイルの取得) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5837f-137">Pick the CHANNEL/BUILD and PLATFORM you want to use, and then click GET POLICY FILES.</span></span>
   - <span data-ttu-id="5837f-138">圧縮ファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="5837f-138">Extract the zipped files.</span></span>
   - <span data-ttu-id="5837f-139">msedge.admx と msedgeupdate.admx を `C:\Windows\PolicyDefinitions` ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5837f-139">Copy msedge.admx and msedgeupdate.admx to the `C:\Windows\PolicyDefinitions` directory.</span></span>
   - <span data-ttu-id="5837f-140">(適切な言語またはロケールのディレクトリから) msedge.adml と msedgeupdate.adml を `C:\Windows\PolicyDefinitions\[APPROPRIATE LANGUAGE/LOCALE]` ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5837f-140">Copy msedge.adml and msedgeupdate.adml (from the appropriate language/locale directory) to the `C:\Windows\PolicyDefinitions\[APPROPRIATE LANGUAGE/LOCALE]` directory.</span></span>

2. <span data-ttu-id="5837f-141">グループ ポリシー エディター (gpedit.msc) を開きます。</span><span class="sxs-lookup"><span data-stu-id="5837f-141">Open the Group Policy Editor (gpedit.msc).</span></span>
3. <span data-ttu-id="5837f-142">**[コンピューターの構成]** の *[管理用テンプレート] > [Microsoft Edge Update] > [アプリケーション]* に移動します。</span><span class="sxs-lookup"><span data-stu-id="5837f-142">Under **Computer Configuration**, go to *Administrative Templates>Microsoft Edge Update>Applications*.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5837f-143">*Microsoft Edge Update* フォルダーが表示されない場合は、手順 1 が正常に完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5837f-143">If you don't see the *Microsoft Edge Update* folder, verify that step 1 was completed correctly.</span></span>

4. <span data-ttu-id="5837f-144">**[アプリケーション]** で、[Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5837f-144">Under **Applications**, double-click "Allow Microsoft Edge Side by Side browser experience".</span></span> <span data-ttu-id="5837f-145">次の手順に進む前に、「[ベスト プラクティス ガイダンス](#best-practice-guidance)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5837f-145">See our [best practice guidance](#best-practice-guidance) before continuing to the next step.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5837f-146">既定では、このグループ ポリシーは [未構成] に設定されています。これにより、新しいバージョンの Microsoft Edge がインストールされている場合に Microsoft Edge レガシが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="5837f-146">By default, this group policy is set to "Not configured", which results in Microsoft Edge Legacy being hidden when the new version of Microsoft Edge is installed.</span></span>

5. <span data-ttu-id="5837f-147">**[有効]** を選択し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5837f-147">Select **Enabled** and then click **OK**.</span></span>  

<span data-ttu-id="5837f-148">このポリシーを設定すると、次のレジストリ キーが "00000001" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5837f-148">Setting this policy will set the following Registry Key  to '00000001':</span></span>

- <span data-ttu-id="5837f-149">キー: </span><span class="sxs-lookup"><span data-stu-id="5837f-149">Key:</span></span> `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate`
- <span data-ttu-id="5837f-150">キーの値: </span><span class="sxs-lookup"><span data-stu-id="5837f-150">Value Name:</span></span> `Allowsxs`
- <span data-ttu-id="5837f-151">値の種類: </span><span class="sxs-lookup"><span data-stu-id="5837f-151">Value Type:</span></span> `'REG_DWORD'`

#### <span data-ttu-id="5837f-152">ベスト プラクティス ガイダンス</span><span class="sxs-lookup"><span data-stu-id="5837f-152">Best practice guidance</span></span>

<span data-ttu-id="5837f-153">最良のエクスペリエンスを得るには、新しいバージョンの Microsoft Edge をユーザーのデバイスに展開する前に、**[Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する]** を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5837f-153">For the best experience, the **Allow Microsoft Edge Side by Side browser experience** should be enabled before the new version of Microsoft Edge is deployed to your users' devices.</span></span>

<span data-ttu-id="5837f-154">Microsoft Edge が展開された後でグループ ポリシーが有効になると、次のような影響があり、対処が必要になります。</span><span class="sxs-lookup"><span data-stu-id="5837f-154">If the group policy is enabled after Microsoft Edge is deployed, there are the following side effects and required actions:</span></span>

1. <span data-ttu-id="5837f-155">**[Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する]** は、新しいバージョンの Microsoft Edge 用のインストーラーが再度実行されるまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="5837f-155">**Allow Microsoft Edge Side by Side browser experience** won't take effect until after the installer for the new version of Microsoft Edge is run again.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5837f-156">インストーラーは、直接実行することも、新しいバージョンの Microsoft Edge 更新時に自動で実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="5837f-156">The installer can be run directly or automatically when the new version of Microsoft Edge updates.</span></span>

2. <span data-ttu-id="5837f-157">新しいバージョンの Microsoft Edge が展開されたときにピン留めが移行されるため、Microsoft Edge レガシはスタート画面またはタスク バーに再度ピン留めする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5837f-157">Microsoft Edge Legacy will need to be re-pinned to Start or the Taskbar because the pin is migrated when the new version of Microsoft Edge is deployed.</span></span>
3. <span data-ttu-id="5837f-158">Microsoft Edge レガシ用にスタート画面またはタスク バーにピン留めされたサイトは、新しいバージョンの Microsoft Edge に移行されます。</span><span class="sxs-lookup"><span data-stu-id="5837f-158">Sites that were pinned to Start or the Taskbar for Microsoft Edge Legacy will be migrated to the new version of Microsoft Edge.</span></span>

## <span data-ttu-id="5837f-159">追加情報</span><span class="sxs-lookup"><span data-stu-id="5837f-159">Additional information</span></span>

<span data-ttu-id="5837f-160">システムが完全に更新され、次のバージョンの Microsoft Edge の Stable チャネルがインストールされた後、次のレジストリ キーと値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="5837f-160">After the systems are fully updated and the Stable channel of the next version of Microsoft Edge is installed, the following registry key and value is set:</span></span>

- <span data-ttu-id="5837f-161">キー: </span><span class="sxs-lookup"><span data-stu-id="5837f-161">Key:</span></span> `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}`
- <span data-ttu-id="5837f-162">キーの値: </span><span class="sxs-lookup"><span data-stu-id="5837f-162">Key value:</span></span> `BrowserReplacement`

  > [!IMPORTANT]
  > <span data-ttu-id="5837f-163">このキーは、Microsoft Edge Stable チャネルが更新されるたびに上書きされます。</span><span class="sxs-lookup"><span data-stu-id="5837f-163">This key is over-written every time the Microsoft Edge Stable channel is updated.</span></span> <span data-ttu-id="5837f-164">ベスト プラクティスとしては、ユーザーが両方のバージョンの Microsoft Edge にアクセスできるように、このキーを削除しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5837f-164">As a best practice, we recommend that you DO NOT delete this key to allow users to access both versions of Microsoft Edge.</span></span>

## <span data-ttu-id="5837f-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="5837f-165">See also</span></span>

- [<span data-ttu-id="5837f-166">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="5837f-166">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="5837f-167">Microsoft Edge をサポートする Windows 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="5837f-167">Windows updates to support Microsoft Edge</span></span>](microsoft-edge-sysupdate-windows-updates.md)
