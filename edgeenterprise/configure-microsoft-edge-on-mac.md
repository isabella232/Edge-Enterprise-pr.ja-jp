---
title: .plist を使用して macOS 用に Microsoft Edge を構成する
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 02/14/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: .plist を使用して macOS で Microsoft Edge ポリシー設定を構成する
ms.openlocfilehash: 84469a4f84deeee0e47b6d8899426fa36cf345aa
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980352"
---
# <span data-ttu-id="31202-103">.plist を使用して macOS 用に Microsoft Edge ポリシー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="31202-103">Configure Microsoft Edge policy settings for macOS using a .plist</span></span>

<span data-ttu-id="31202-104">この記事では、macOS でプロパティ リスト (.plist) ファイルを使用して Microsoft Edge を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31202-104">This article describes how to configure Microsoft Edge on macOS using a property list (.plist) file.</span></span> <span data-ttu-id="31202-105">このファイルを作成して、Microsoft Intune に展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31202-105">You'll learn how to create this file and then deploy it to Microsoft Intune.</span></span>

<span data-ttu-id="31202-106">詳しくは、[情報プロパティ リスト ファイルに関するページ](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (Apple の Web サイト) と「[カスタム ペイロードの設定](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="31202-106">For more information, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (Apple's website) and [Custom payload settings](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1).</span></span>

> [!NOTE]
> <span data-ttu-id="31202-107">この記事は Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="31202-107">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="31202-108">macOS で Microsoft Edge ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="31202-108">Configure Microsoft Edge policies on macOS</span></span>

<span data-ttu-id="31202-109">まず、plist を作成します。</span><span class="sxs-lookup"><span data-stu-id="31202-109">The first step is to create your plist.</span></span> <span data-ttu-id="31202-110">任意のテキスト エディターを使用して plist ファイルを作成することも、[ターミナルを使用して構成プロファイルを作成する](#create-a-configuration-profile-using-terminal)こともできます。</span><span class="sxs-lookup"><span data-stu-id="31202-110">You can create the plist file with any text editor or you can use [Terminal to create the configuration profile](#create-a-configuration-profile-using-terminal).</span></span> <span data-ttu-id="31202-111">ただし、XML コードの書式設定が行われるツールを使用する方が、plist ファイルの作成および編集が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="31202-111">However, it's easier to create and edit a plist file using a tool that formats the XML code for you.</span></span> <span data-ttu-id="31202-112">*Xcode* は、無料の統合開発環境です。次のいずれかの場所から入手できます。</span><span class="sxs-lookup"><span data-stu-id="31202-112">*Xcode* is a free integrated development environment that you can get from one of the following locations:</span></span>

- [<span data-ttu-id="31202-113">Apple Developer Web サイト</span><span class="sxs-lookup"><span data-stu-id="31202-113">Apple developer website</span></span>](https://developer.apple.com/xcode/)
- [<span data-ttu-id="31202-114">Mac App Store</span><span class="sxs-lookup"><span data-stu-id="31202-114">Mac App Store</span></span>](https://apps.apple.com/app/xcode/id497799835?mt=12)

<span data-ttu-id="31202-115">サポートされているポリシーと、対応する基本設定キー名については、[Microsoft Edge ブラウザー ポリシー リファレンス](microsoft-edge-policies.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="31202-115">For a list of supported policies and their preference key names, see [Microsoft Edge browser policies reference](microsoft-edge-policies.md).</span></span> <span data-ttu-id="31202-116">[Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードできるポリシー テンプレート ファイルの **examples** フォルダーには、plist の例 (*itadminexample.plist*) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="31202-116">In the policy templates file, which can be downloaded from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise), there's an example plist (*itadminexample.plist*) in the **examples** folder.</span></span> <span data-ttu-id="31202-117">このサンプル ファイルには、サポートされているすべてのデータ型が含まれており、これらはカスタマイズしてポリシー設定の定義に使用できます。</span><span class="sxs-lookup"><span data-stu-id="31202-117">The example file contains all supported data types that you can customize to define your policy settings.</span></span> 

<span data-ttu-id="31202-118">plist のコンテンツを作成できたら、次の手順は、Microsoft Edge の基本設定ドメイン *com.microsoft.Edge* を使用して名前を付けることです。</span><span class="sxs-lookup"><span data-stu-id="31202-118">The next step after you create the contents of your plist, is to name it using the Microsoft Edge preference domain, *com.microsoft.Edge*.</span></span> <span data-ttu-id="31202-119">この名前では、大文字と小文字が区別されます。また、すべての Microsoft Edge チャネルに適用されるため、ターゲットにするチャネルを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="31202-119">The name is case sensitive and should not include the channel you are targeting because it applies to all Microsoft Edge channels.</span></span> <span data-ttu-id="31202-120">plist ファイル名は、「**_com.microsoft.Edge.plist_**」とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31202-120">The plist file name must be **_com.microsoft.Edge.plist_**.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="31202-121">ビルド 78.0.249.2 以降、macOS 上のすべての Microsoft Edge チャネルは **com.microsoft.Edge** 基本設定ドメインから読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="31202-121">Starting with build 78.0.249.2, all Microsoft Edge channels on macOS read from the **com.microsoft.Edge** preference domain.</span></span> <span data-ttu-id="31202-122">それより前のリリースはすべて、チャネル固有のドメインから読み込まれます (例: Dev チャネルの場合は **com.microsoft.Edge.Dev**)。</span><span class="sxs-lookup"><span data-stu-id="31202-122">All prior releases read from a channel specific domain, such as **com.microsoft.Edge.Dev** for Dev channel.</span></span>

<span data-ttu-id="31202-123">最後に、Microsoft Intune など、好みの MDM プロバイダーを使用して、ユーザーの Mac デバイスに plist を展開します。</span><span class="sxs-lookup"><span data-stu-id="31202-123">The last step is to deploy your plist to your users' Mac devices using your preferred MDM provider, such as Microsoft Intune.</span></span> <span data-ttu-id="31202-124">手順については、「[plist を展開する](#deploy-your-plist)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="31202-124">For instructions see [Deploy your plist](#deploy-your-plist).</span></span>

### <span data-ttu-id="31202-125">ターミナルを使用して構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="31202-125">Create a configuration profile using Terminal</span></span>

1. <span data-ttu-id="31202-126">ターミナルで次のコマンドを使用して、好みの設定でデスクトップ上の Microsoft Edge の plist を作成します。</span><span class="sxs-lookup"><span data-stu-id="31202-126">In Terminal, use the following command to create a plist for Microsoft Edge on your desktop with your preferred settings:</span></span>

   ```cmd
   /usr/bin/defaults write ~/Desktop/com.microsoft.Edge.plist RestoreOnStartup -int 1
   ```

2. <span data-ttu-id="31202-127">plist をバイナリからプレーンテキスト形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="31202-127">Convert the plist from binary to plain text format:</span></span>

   ```cmd
   /usr/bin/plutil -convert xml1 ~/Desktop/com.microsoft.Edge.plist
   ```
<span data-ttu-id="31202-128">ファイルを変換した後、ポリシー データが正しく、構成プロファイルに必要な設定が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="31202-128">After converting the file verify that your policy data is correct and contains the settings you want for your configuration profile.</span></span>

> [!NOTE]
> <span data-ttu-id="31202-129">plist または xml ファイルは、内容としてキーと値のペアのみが含まれている状態にします。</span><span class="sxs-lookup"><span data-stu-id="31202-129">Only key value pairs should be in the contents of the plist or xml file.</span></span> <span data-ttu-id="31202-130">ファイルを Intune にアップロードする前に、すべての \<plist> と \<dict> の値と xml ヘッダーをファイルから削除します。</span><span class="sxs-lookup"><span data-stu-id="31202-130">Prior to uploading your file into Intune remove all the \<plist> and \<dict> values, and xml headers from your file.</span></span> <span data-ttu-id="31202-131">ファイルは、キーと値のペアのみが含まれている状態にします。</span><span class="sxs-lookup"><span data-stu-id="31202-131">The file should only contain key value pairs.</span></span>

## <span data-ttu-id="31202-132">plist を展開する</span><span class="sxs-lookup"><span data-stu-id="31202-132">Deploy your plist</span></span>

<span data-ttu-id="31202-133">Microsoft Intune の場合は、macOS プラットフォームをターゲットとした新しいデバイス構成プロファイルを作成し、プロファイルの種類として *[Preference file]* (基本設定ファイル) を選択します。</span><span class="sxs-lookup"><span data-stu-id="31202-133">For Microsoft Intune create a new device configuration profile targeting the macOS platform and select the *Preference file* profile type.</span></span> <span data-ttu-id="31202-134">基本設定ドメイン名として **com.microsoft.Edge** を指定し、plist をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="31202-134">Target **com.microsoft.Edge** as the preference domain name and upload your plist.</span></span> <span data-ttu-id="31202-135">詳しくは、「[Microsoft Intune を使用して macOS デバイスにプロパティ リスト ファイルを追加する](https://docs.microsoft.com/intune/configuration/preference-file-settings-macos)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="31202-135">For more information see [Add a property list file to macOS devices using Microsoft Intune](https://docs.microsoft.com/intune/configuration/preference-file-settings-macos).</span></span>

<span data-ttu-id="31202-136">Jamf の場合は、[*カスタム設定*] ペイロードとして .plist ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="31202-136">For Jamf upload the .plist file as a *Custom Settings* payload.</span></span>

## <span data-ttu-id="31202-137">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="31202-137">Frequently Asked Questions</span></span>

### <span data-ttu-id="31202-138">Microsoft Edge は、マスター基本設定が使用されるように構成できますか?</span><span class="sxs-lookup"><span data-stu-id="31202-138">Can Microsoft Edge be configured to use master preferences?</span></span>

<span data-ttu-id="31202-139">Microsoft Edge は、マスター基本設定ファイルが使用されるように構成できます。</span><span class="sxs-lookup"><span data-stu-id="31202-139">Yes, you can configure Microsoft Edge to use a master preferences file.</span></span>

<span data-ttu-id="31202-140">マスター基本設定ファイルを使用すると、Microsoft Edge を展開する際に、ブラウザー ユーザー プロファイルの既定の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="31202-140">A master preferences file lets you configure default settings for a browser user profile when Microsoft Edge is deployed.</span></span> <span data-ttu-id="31202-141">マスター基本設定ファイルを使用すると、デバイス管理システムで管理されていないコンピューターに設定を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="31202-141">You can also use a master preferences file to apply settings on computers that aren't managed by a device management system.</span></span> <span data-ttu-id="31202-142">これらの設定は、ユーザーがブラウザーを初めて実行するときに、ユーザーのプロファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="31202-142">These settings are applied to the user’s profile the first time the user runs the browser.</span></span> <span data-ttu-id="31202-143">ユーザーがブラウザーを実行した後で発生した、マスター基本設定ファイルへの変更は適用されません。</span><span class="sxs-lookup"><span data-stu-id="31202-143">After the user runs the browser, changes to the master preferences file aren’t applied.</span></span> <span data-ttu-id="31202-144">ユーザーは、ブラウザーでマスター基本設定の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="31202-144">A user can change settings from the master preferences in the browser.</span></span> <span data-ttu-id="31202-145">ブラウザーを初めて実行した後に設定を必須にしたり、設定を変更したりする場合は、ポリシーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31202-145">If you want to make a setting mandatory or change a setting after the first run of the browser, you must use a policy.</span></span>

<span data-ttu-id="31202-146">マスター基本設定ファイルを使用すると、ブラウザーのさまざまな設定や基本設定をカスタマイズできます。これには、他の Chromium ベースのブラウザーと共有されるものや、Microsoft Edge に固有のものも含まれます。</span><span class="sxs-lookup"><span data-stu-id="31202-146">A master preferences file lets you to customize many different settings and preferences for the browser, including those shared with other Chromium based browsers and specific to Microsoft Edge.</span></span>  <span data-ttu-id="31202-147">ポリシー関連の基本設定は、マスター基本設定ファイルを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="31202-147">Policy related preferences can be configured using the master preferences file.</span></span> <span data-ttu-id="31202-148">ポリシーが設定され、対応するマスター基本設定が設定されている場合は、ポリシー設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="31202-148">In cases where a policy is set and there’s a corresponding master preference set, the policy setting takes precedence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31202-149">利用可能なすべての基本設定が Microsoft Edge の用語や命名規則と一致していないこともあります。</span><span class="sxs-lookup"><span data-stu-id="31202-149">All the available preferences might not be consistent with Microsoft Edge terminology and naming conventions.</span></span>  <span data-ttu-id="31202-150">これらの基本設定が今後のリリースでも引き続き期待どおりに動作することは保証されません。</span><span class="sxs-lookup"><span data-stu-id="31202-150">There’s no guarantee that these preferences will continue to work as expected in future releases.</span></span> <span data-ttu-id="31202-151">今後のバージョンでは、基本設定が変更または無視される可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="31202-151">Preferences might be changed or ignored in later versions.</span></span>

<span data-ttu-id="31202-152">マスター基本設定ファイルは、JSON マークアップを使用して書式設定されたテキスト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="31202-152">A master preferences file is a text file that’s formatted using JSON markup.</span></span> <span data-ttu-id="31202-153">このファイルは、msedge.exe 実行可能ファイルと同じディレクトリに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31202-153">This file needs to be added to the same directory as the msedge.exe executable.</span></span> <span data-ttu-id="31202-154">macOS でのシステム全体のエンタープライズ展開では通常、"*~/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*" または "*/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*" になります。</span><span class="sxs-lookup"><span data-stu-id="31202-154">For system wide enterprise deployments on macOS this is typically: “*~/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*" or "*/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*”.</span></span>

## <span data-ttu-id="31202-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="31202-155">See also</span></span>

- [<span data-ttu-id="31202-156">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="31202-156">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="31202-157">Jamf を使用して macOS 用に構成する</span><span class="sxs-lookup"><span data-stu-id="31202-157">Configure for macOS with Jamf</span></span>](configure-microsoft-edge-on-mac-jamf.md)
- [<span data-ttu-id="31202-158">Windows 用に構成する</span><span class="sxs-lookup"><span data-stu-id="31202-158">Configure for Windows</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="31202-159">Intune で Windows 用に構成する</span><span class="sxs-lookup"><span data-stu-id="31202-159">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)
