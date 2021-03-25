---
title: .plist を使用して macOS 用に Microsoft Edge を構成する
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 11/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: .plist を使用して macOS で Microsoft Edge ポリシー設定を構成する
ms.openlocfilehash: 3f297c11d8009c85a1bc5e17447681ee2b9ef1e2
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447451"
---
# <a name="configure-microsoft-edge-policy-settings-for-macos-using-a-plist"></a><span data-ttu-id="e8960-103">.plist を使用して macOS 用に Microsoft Edge ポリシー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="e8960-103">Configure Microsoft Edge policy settings for macOS using a .plist</span></span>

<span data-ttu-id="e8960-104">この記事では、macOS でプロパティ リスト (.plist) ファイルを使用して Microsoft Edge を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8960-104">This article describes how to configure Microsoft Edge on macOS using a property list (.plist) file.</span></span> <span data-ttu-id="e8960-105">このファイルを作成して、Microsoft Intune に展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8960-105">You'll learn how to create this file and then deploy it to Microsoft Intune.</span></span>

<span data-ttu-id="e8960-106">詳しくは、[情報プロパティ リスト ファイルに関するページ](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (Apple の Web サイト) と「[カスタム ペイロードの設定](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8960-106">For more information, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (Apple's website) and [Custom payload settings](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1).</span></span>

> [!NOTE]
> <span data-ttu-id="e8960-107">この記事は Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e8960-107">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="configure-microsoft-edge-policies-on-macos"></a><span data-ttu-id="e8960-108">macOS で Microsoft Edge ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="e8960-108">Configure Microsoft Edge policies on macOS</span></span>

<span data-ttu-id="e8960-109">まず、plist を作成します。</span><span class="sxs-lookup"><span data-stu-id="e8960-109">The first step is to create your plist.</span></span> <span data-ttu-id="e8960-110">任意のテキスト エディターを使用して plist ファイルを作成することも、[ターミナルを使用して構成プロファイルを作成する](#create-a-configuration-profile-using-terminal)こともできます。</span><span class="sxs-lookup"><span data-stu-id="e8960-110">You can create the plist file with any text editor or you can use [Terminal to create the configuration profile](#create-a-configuration-profile-using-terminal).</span></span> <span data-ttu-id="e8960-111">ただし、XML コードの書式設定が行われるツールを使用する方が、plist ファイルの作成および編集が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="e8960-111">However, it's easier to create and edit a plist file using a tool that formats the XML code for you.</span></span> <span data-ttu-id="e8960-112">*Xcode* は、無料の統合開発環境です。次のいずれかの場所から入手できます。</span><span class="sxs-lookup"><span data-stu-id="e8960-112">*Xcode* is a free integrated development environment that you can get from one of the following locations:</span></span>

- [<span data-ttu-id="e8960-113">Apple Developer Web サイト</span><span class="sxs-lookup"><span data-stu-id="e8960-113">Apple developer website</span></span>](https://developer.apple.com/xcode/)
- [<span data-ttu-id="e8960-114">Mac App Store</span><span class="sxs-lookup"><span data-stu-id="e8960-114">Mac App Store</span></span>](https://apps.apple.com/app/xcode/id497799835?mt=12)

<span data-ttu-id="e8960-115">サポートされているポリシーと、対応する基本設定キー名については、[Microsoft Edge ブラウザー ポリシー リファレンス](microsoft-edge-policies.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8960-115">For a list of supported policies and their preference key names, see [Microsoft Edge browser policies reference](microsoft-edge-policies.md).</span></span> <span data-ttu-id="e8960-116">[Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードできるポリシー テンプレート ファイルの **examples** フォルダーには、plist の例 (*itadminexample.plist*) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8960-116">In the policy templates file, which can be downloaded from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise), there's an example plist (*itadminexample.plist*) in the **examples** folder.</span></span> <span data-ttu-id="e8960-117">このサンプル ファイルには、サポートされているすべてのデータ型が含まれており、これらはカスタマイズしてポリシー設定の定義に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8960-117">The example file contains all supported data types that you can customize to define your policy settings.</span></span> 

<span data-ttu-id="e8960-118">plist のコンテンツを作成できたら、次の手順は、Microsoft Edge の基本設定ドメイン *com.microsoft.Edge* を使用して名前を付けることです。</span><span class="sxs-lookup"><span data-stu-id="e8960-118">The next step after you create the contents of your plist, is to name it using the Microsoft Edge preference domain, *com.microsoft.Edge*.</span></span> <span data-ttu-id="e8960-119">この名前では、大文字と小文字が区別されます。また、すべての Microsoft Edge チャネルに適用されるため、ターゲットにするチャネルを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="e8960-119">The name is case sensitive and should not include the channel you are targeting because it applies to all Microsoft Edge channels.</span></span> <span data-ttu-id="e8960-120">plist ファイル名は、「**_com.microsoft.Edge.plist_**」とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8960-120">The plist file name must be **_com.microsoft.Edge.plist_**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8960-121">ビルド 78.0.249.2 以降、macOS 上のすべての Microsoft Edge チャネルは **com.microsoft.Edge** 基本設定ドメインから読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="e8960-121">Starting with build 78.0.249.2, all Microsoft Edge channels on macOS read from the **com.microsoft.Edge** preference domain.</span></span> <span data-ttu-id="e8960-122">それより前のリリースはすべて、チャネル固有のドメインから読み込まれます (例: Dev チャネルの場合は **com.microsoft.Edge.Dev**)。</span><span class="sxs-lookup"><span data-stu-id="e8960-122">All prior releases read from a channel specific domain, such as **com.microsoft.Edge.Dev** for Dev channel.</span></span>

<span data-ttu-id="e8960-123">最後に、Microsoft Intune など、好みの MDM プロバイダーを使用して、ユーザーの Mac デバイスに plist を展開します。</span><span class="sxs-lookup"><span data-stu-id="e8960-123">The last step is to deploy your plist to your users' Mac devices using your preferred MDM provider, such as Microsoft Intune.</span></span> <span data-ttu-id="e8960-124">手順については、「[plist を展開する](#deploy-your-plist)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8960-124">For instructions see [Deploy your plist](#deploy-your-plist).</span></span>

### <a name="create-a-configuration-profile-using-terminal"></a><span data-ttu-id="e8960-125">ターミナルを使用して構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="e8960-125">Create a configuration profile using Terminal</span></span>

1. <span data-ttu-id="e8960-126">ターミナルで次のコマンドを使用して、好みの設定でデスクトップ上の Microsoft Edge の plist を作成します。</span><span class="sxs-lookup"><span data-stu-id="e8960-126">In Terminal, use the following command to create a plist for Microsoft Edge on your desktop with your preferred settings:</span></span>

   ```cmd
   /usr/bin/defaults write ~/Desktop/com.microsoft.Edge.plist RestoreOnStartup -int 1
   ```

2. <span data-ttu-id="e8960-127">plist をバイナリからプレーンテキスト形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="e8960-127">Convert the plist from binary to plain text format:</span></span>

   ```cmd
   /usr/bin/plutil -convert xml1 ~/Desktop/com.microsoft.Edge.plist
   ```

<span data-ttu-id="e8960-128">ファイルを変換した後、ポリシー データが正しく、構成プロファイルに必要な設定が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8960-128">After converting the file verify that your policy data is correct and contains the settings you want for your configuration profile.</span></span>

> [!NOTE]
> <span data-ttu-id="e8960-129">plist または xml ファイルは、内容としてキーと値のペアのみが含まれている状態にします。</span><span class="sxs-lookup"><span data-stu-id="e8960-129">Only key value pairs should be in the contents of the plist or xml file.</span></span> <span data-ttu-id="e8960-130">ファイルを Intune にアップロードする前に、すべての \<plist> と \<dict> の値と xml ヘッダーをファイルから削除します。</span><span class="sxs-lookup"><span data-stu-id="e8960-130">Prior to uploading your file into Intune remove all the \<plist> and \<dict> values, and xml headers from your file.</span></span> <span data-ttu-id="e8960-131">ファイルは、キーと値のペアのみが含まれている状態にします。</span><span class="sxs-lookup"><span data-stu-id="e8960-131">The file should only contain key value pairs.</span></span>

## <a name="deploy-your-plist"></a><span data-ttu-id="e8960-132">plist を展開する</span><span class="sxs-lookup"><span data-stu-id="e8960-132">Deploy your plist</span></span>

<span data-ttu-id="e8960-133">Microsoft Intune の場合は、macOS プラットフォームをターゲットとした新しいデバイス構成プロファイルを作成し、プロファイルの種類として *[Preference file]* (基本設定ファイル) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8960-133">For Microsoft Intune create a new device configuration profile targeting the macOS platform and select the *Preference file* profile type.</span></span> <span data-ttu-id="e8960-134">基本設定ドメイン名として **com.microsoft.Edge** を指定し、plist をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="e8960-134">Target **com.microsoft.Edge** as the preference domain name and upload your plist.</span></span> <span data-ttu-id="e8960-135">詳しくは、「[Microsoft Intune を使用して macOS デバイスにプロパティ リスト ファイルを追加する](/intune/configuration/preference-file-settings-macos)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8960-135">For more information see [Add a property list file to macOS devices using Microsoft Intune](/intune/configuration/preference-file-settings-macos).</span></span>

<span data-ttu-id="e8960-136">Jamf の場合は、[*カスタム設定*] ペイロードとして .plist ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="e8960-136">For Jamf upload the .plist file as a *Custom Settings* payload.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8960-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8960-137">See also</span></span>

- [<span data-ttu-id="e8960-138">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="e8960-138">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="e8960-139">Jamf を使用して macOS 用に構成する</span><span class="sxs-lookup"><span data-stu-id="e8960-139">Configure for macOS with Jamf</span></span>](configure-microsoft-edge-on-mac-jamf.md)
- [<span data-ttu-id="e8960-140">Windows 用に構成する</span><span class="sxs-lookup"><span data-stu-id="e8960-140">Configure for Windows</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="e8960-141">Intune で Windows 用に構成する</span><span class="sxs-lookup"><span data-stu-id="e8960-141">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)