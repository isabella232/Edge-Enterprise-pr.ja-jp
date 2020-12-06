---
title: Jamf を使用して macOS の Microsoft Edge を構成する
ms.author: brianalt
author: dan-wesley
manager: laurawi
ms.date: 11/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Jamf を使用して Mac デバイスの Microsoft Edge ポリシー設定を構成する
ms.openlocfilehash: 1859d9fb1fd3ea8ff6908c41f75df21a8b338769
ms.sourcegitcommit: ed6a5afabf909df87bec48671c4c47bcdfaeb7bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "11194715"
---
# <span data-ttu-id="f157f-103">Jamf を使用して macOS の Microsoft Edge ポリシー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="f157f-103">Configure Microsoft Edge policy settings on macOS with Jamf</span></span>

<span data-ttu-id="f157f-104">この記事では、Jamf Pro 10.19 の Microsoft Edge ポリシー マニフェスト ファイルを使用して、macOS のポリシー設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f157f-104">This article describes how to configure policy settings on macOS using a Microsoft Edge policy manifest file on Jamf Pro 10.19.</span></span>

<span data-ttu-id="f157f-105">macOS の Microsoft Edge ポリシー設定は、プロパティ リスト (.plist) ファイルを使用して構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f157f-105">You can also configure Microsoft Edge policy settings on macOS by using a property list (.plist) file.</span></span> <span data-ttu-id="f157f-106">詳細については、「[.plist を使用して macOS 用に構成する](configure-microsoft-edge-on-mac.md)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="f157f-106">For more information, see [Configure for macOS using a .plist](configure-microsoft-edge-on-mac.md)</span></span>


## <span data-ttu-id="f157f-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="f157f-107">Prerequisites</span></span>

<span data-ttu-id="f157f-108">次のソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="f157f-108">The following software is required:</span></span>

- <span data-ttu-id="f157f-109">Microsoft Edge Stable チャネル 81</span><span class="sxs-lookup"><span data-stu-id="f157f-109">Microsoft Edge Stable channel 81</span></span>
- <span data-ttu-id="f157f-110">ポリシー テンプレート ファイル (バージョン 81.0.416.3)</span><span class="sxs-lookup"><span data-stu-id="f157f-110">Policy Templates file, version 81.0.416.3</span></span>
- <span data-ttu-id="f157f-111">Jamf Pro (バージョン 10.19)</span><span class="sxs-lookup"><span data-stu-id="f157f-111">Jamf Pro, Version 10.19</span></span>

## <span data-ttu-id="f157f-112">Jamf Pro の [Application & Custom Settings] メニューについて</span><span class="sxs-lookup"><span data-stu-id="f157f-112">About the Jamf Pro Application & Custom Settings menu</span></span>

<span data-ttu-id="f157f-113">Jamf Pro 10.18 以前では、Office 365 の管理には手動による .plist の作成が必要でした。</span><span class="sxs-lookup"><span data-stu-id="f157f-113">Before Jamf Pro 10.18, managing Office 365 involved manually building a .plist file.</span></span> <span data-ttu-id="f157f-114">この作業は、強力な技術的バックグラウンドが必要になる、時間のかかるワークフローでした。</span><span class="sxs-lookup"><span data-stu-id="f157f-114">This was a time-consuming workflow that required a strong technical background.</span></span> <span data-ttu-id="f157f-115">Jamf Pro 10.18 では、構成プロセスを合理化することで、このような障壁が排除されました。</span><span class="sxs-lookup"><span data-stu-id="f157f-115">Jamf Pro 10.18 eliminated those barriers by streamlining the configuration process.</span></span> <span data-ttu-id="f157f-116">ただし、この新しいユーザー インターフェイスは、IT 管理者のみが使用できるものであり、Jamf が指定した特定のアプリケーションと優先ドメインに対応していました。</span><span class="sxs-lookup"><span data-stu-id="f157f-116">However, IT Admins could only use this new user interface for specific applications and preference domains specified by Jamf.</span></span>

<span data-ttu-id="f157f-117">Jamf Pro 10.19 では、ユーザーが「カスタム スキーマ」として JSON マニフェストをアップロードすることで任意の優先ドメインをターゲットに設定できます。このマニフェストから、グラフィカル ユーザー インターフェイスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f157f-117">In Jamf Pro 10.19, a user can upload a JSON manifest as a "custom schema" to target any preference domain, and the graphical user interface will be generated from this manifest.</span></span> <span data-ttu-id="f157f-118">このカスタム スキーマは、JSON スキーマ仕様に従って作成します。</span><span class="sxs-lookup"><span data-stu-id="f157f-118">The custom schema that's created follows the JSON Schema specification.</span></span>

<span data-ttu-id="f157f-119">詳細については、Jamf Pro 管理者ガイドの「[コンピューター構成プロファイル](https://jamf.it/computer-configuration-profiles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f157f-119">For more information, see [Computer Configuration Profiles](https://jamf.it/computer-configuration-profiles) in the Jamf Pro Administrator's Guide.</span></span>

## <span data-ttu-id="f157f-120">Microsoft Edge の特定のバージョン用のポリシー マニフェストを取得する</span><span class="sxs-lookup"><span data-stu-id="f157f-120">Get the policy manifest for a specific version of Microsoft Edge</span></span>

<span data-ttu-id="f157f-121">ポリシー マニフェストを取得するには:</span><span class="sxs-lookup"><span data-stu-id="f157f-121">To get the policy manifest:</span></span>

- <span data-ttu-id="f157f-122">[Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)に移動します。</span><span class="sxs-lookup"><span data-stu-id="f157f-122">Go to the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise).</span></span>
- <span data-ttu-id="f157f-123">[チャネル/バージョン] ドロップダウン リストで、**バージョン 81 以降の任意のチャネルを選択します。**_。</span><span class="sxs-lookup"><span data-stu-id="f157f-123">On the Channel/Version dropdown list, select **any channel with version 81 or later.**_.</span></span>
- <span data-ttu-id="f157f-124">[ビルド] ドロップダウン リストで、_*81 以降の任意のビルドを選択します。*\*_。</span><span class="sxs-lookup"><span data-stu-id="f157f-124">On the Build dropdown list, select any _*81 build or later.*\*_.</span></span>
- <span data-ttu-id="f157f-125">[ポリシー ファイルの取得] をクリックして、ポリシー テンプレートのバンドルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f157f-125">Click GET POLICY FILES to download our policy templates bundle.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f157f-126">現在、このポリシー テンプレートのバンドルは、CAB ファイルとして署名されています。</span><span class="sxs-lookup"><span data-stu-id="f157f-126">Currently, the policy templates bundle is signed as a CAB file.</span></span> <span data-ttu-id="f157f-127">このファイルを macOS で開くには、サード パーティ製ツール (The Unarchiver など) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f157f-127">You'll need to use a 3rd party tool, such as The Unarchiver to open the file on macOS.</span></span>

<span data-ttu-id="f157f-128">CAB ファイルを展開してから、ZIP ファイルを展開して、最上位ディレクトリの "mac" に移動します。</span><span class="sxs-lookup"><span data-stu-id="f157f-128">After you unpack the CAB file, unpack the ZIP file and navigate to the "mac" top level directory.</span></span> <span data-ttu-id="f157f-129">このディレクトリに、"policy_manifest.json" という名前のマニフェスト ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="f157f-129">The manifest, which is named "policy_manifest.json", is in this directory.</span></span>

<span data-ttu-id="f157f-130">このマニフェスト ファイルは、ビルド 81.0.416.3 以降のポリシー バンドルごとに発行されます。</span><span class="sxs-lookup"><span data-stu-id="f157f-130">This manifest will be published in every policy bundle starting with build 81.0.416.3.</span></span> <span data-ttu-id="f157f-131">開発用チャネルのポリシーをテストする場合は、それぞれの開発リリースに関連付けられたマニフェストを取得して、そのマニフェストを Jamf Pro でテストしてください。</span><span class="sxs-lookup"><span data-stu-id="f157f-131">If you want to test policies in the Dev channel, you can take the manifest associated with each Dev release and test it in Jamf Pro.</span></span>  

## <span data-ttu-id="f157f-132">Jamf Pro でポリシー マニフェストを使用する</span><span class="sxs-lookup"><span data-stu-id="f157f-132">Use the policy manifest in Jamf Pro</span></span>

<span data-ttu-id="f157f-133">次の手順を使用して、Jamf Pro にポリシー マニフェストをアップロードし、macOS 用のポリシー プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f157f-133">Use the following steps to upload the policy manifest to Jamf Pro and then create a policy profile for macOS.</span></span>

1. <span data-ttu-id="f157f-134">Jamf にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f157f-134">Sign in to Jamf.</span></span>
2. <span data-ttu-id="f157f-135">[_\*Computer\*\*] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="f157f-135">Select the _*Computer*\* tab.</span></span>
3. <span data-ttu-id="f157f-136">**[Content Management]** (コンテンツ管理) にある **[Configuration Profiles]** (構成プロファイル) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f157f-136">Under **Content Management**, select **Configuration Profiles**.</span></span>
4. <span data-ttu-id="f157f-137">**[Configuration Profiles]** ページで、**[+ New]** (+ 新規) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f157f-137">On the **Configuration Profiles** page, click **+ New**.</span></span>

   ![Jamf に新しいプロファイルを追加する](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles.png)

5. <span data-ttu-id="f157f-139">**[New macOS Configuration Profile]** (新規 macOS 構成プロファイル) > **[Options]** (オプション) で、**[Application & Custom Settings]** (アプリケーションとカスタムの設定) を選択します。</span><span class="sxs-lookup"><span data-stu-id="f157f-139">On **New macOS Configuration Profile**>**Options**, select **Application & Custom Settings**.</span></span>
6. <span data-ttu-id="f157f-140">**[Application & Custom Settings]** ポップアップ ウィンドウで、**[Configure]** (構成) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f157f-140">On the **Application & Custom Settings** popup window, click **Configure**.</span></span>

   ![アプリケーションとカスタムの設定を構成する](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom.png)

7. <span data-ttu-id="f157f-142">**[Application & Custom Settings]** セクションで、次のスクリーンショットに示した値を設定します。</span><span class="sxs-lookup"><span data-stu-id="f157f-142">In the **Application & Custom Settings** section, set the values shown in the following screen shot.</span></span>

   ![プロファイル ソースとカスタム スキーマ](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-schema.png)

   - <span data-ttu-id="f157f-144">**[Creation Method]** (作成方法) には、**[Configure settings]** (設定を構成する) を選択します。</span><span class="sxs-lookup"><span data-stu-id="f157f-144">For **Creation Method**, pick **Configure settings**.</span></span>
   - <span data-ttu-id="f157f-145">**[Source]** (ソース) には、**[Custom Schema]** (カスタム スキーマ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="f157f-145">For **Source**, pick **Custom Schema**.</span></span>
   - <span data-ttu-id="f157f-146">**[Preference Domain]** (優先ドメイン) には、対象のドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f157f-146">For **Preference Domain**, provide the name of your domain.</span></span> <span data-ttu-id="f157f-147">この例では、そのドメインとして「*com.microsoft.Edge*」を使用します。</span><span class="sxs-lookup"><span data-stu-id="f157f-147">This example uses *com.microsoft.Edge* as the domain.</span></span>
   - <span data-ttu-id="f157f-148">**[Custom Schema]** (カスタム スキーマ) には、"policy_manifest.json" マニフェスト ファイルの内容を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f157f-148">For **Custom Schema**, paste the contents of the "policy_manifest.json" manifest file.</span></span>
   - <span data-ttu-id="f157f-149">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f157f-149">Click **Save**.</span></span>

8. <span data-ttu-id="f157f-150">プロファイルを保存すると、Jamf により、次のスクリーン ショットに示す **[General]** (全般) セクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f157f-150">After you save the profile, Jamf displays the **General** section shown in the next screen shot.</span></span>

   ![[General] セクションの構成](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-general-setting.png)

   - <span data-ttu-id="f157f-152">プロファイルの **[Name]** (名前) と **[Description]** (説明) を入力します。</span><span class="sxs-lookup"><span data-stu-id="f157f-152">Provide a display **Name** for the profile and a **Description**.</span></span>
   - <span data-ttu-id="f157f-153">**[Category]** (カテゴリ) の既定の設定 **[None]** (なし) は、そのままにします。</span><span class="sxs-lookup"><span data-stu-id="f157f-153">Keep the default setting for **Category**, which is **None**.</span></span>
   - <span data-ttu-id="f157f-154">**[Distribution Method]** (配布方法) のオプションは、**[Install Automatically]** (自動的にインストールする) または **[Make Available in Self Service]** (セルフサービスで利用可能にする) にします。</span><span class="sxs-lookup"><span data-stu-id="f157f-154">For **Distribution Method**, the options are **Install Automatically** or **Make Available in Self Service**.</span></span>
   - <span data-ttu-id="f157f-155">**[Level]** (レベル) のオプションは、**[User Level]** (ユーザー レベル) または **[Computer Level]** (コンピューター レベル) にします。</span><span class="sxs-lookup"><span data-stu-id="f157f-155">For **Level**, the options are **User Level** or **Computer Level**.</span></span>
   - <span data-ttu-id="f157f-156">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f157f-156">Click **Save**.</span></span>

9. <span data-ttu-id="f157f-157">[General] セクションを保存すると、Jamf により、この記事の例に応じて設定された "Microsoft Edge Beta Channel" 構成プロファイルが示されます。</span><span class="sxs-lookup"><span data-stu-id="f157f-157">After you save the General section, Jamf shows the "Microsoft Edge Beta Channel" configuration profile set up for our example.</span></span> <span data-ttu-id="f157f-158">次のスクリーン ショットでは、**[Edit]** (編集) をクリックすることでプロファイルの作業を続行できます。作業が完了している場合は、**[Done]** (完了) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f157f-158">In the next screen shot, note that you can keep working the profile by clicking **Edit** or if you're finished, click **Done**.</span></span>

   ![オプションを設定した新しい構成プロファイル](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel.png)

   > [!NOTE]
   > <span data-ttu-id="f157f-160">このプロファイルは保存後に、別の Jamf セッションで編集できます。</span><span class="sxs-lookup"><span data-stu-id="f157f-160">You can edit this profile after it's been saved and in another Jamf session.</span></span> <span data-ttu-id="f157f-161">たとえば、[Distribution Method] を [Make Available in Self Service] に変更できます。</span><span class="sxs-lookup"><span data-stu-id="f157f-161">For example, you might decide to change the Distribution Method to Make Available in Self Service.</span></span>

   <span data-ttu-id="f157f-162">Microsoft Edge Stable チャネルの追加編集や削除を実行する場合は、次のスクリーン ショットに示す [Configuration Profiles] でプロファイル名を選択します。</span><span class="sxs-lookup"><span data-stu-id="f157f-162">To do a follow up edit on the Microsoft Edge Stable Channel, or delete it, select the profile name, shown in the following Configuration Profiles screen shot.</span></span>

   ![[Configuration Profiles] リスト](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel-done.png)

<span data-ttu-id="f157f-164">新しい構成プロファイルの作成後には、そのプロファイルの **[Scope]** (スコープ) も構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f157f-164">After you create the new configuration profile you still have to configure the **Scope** for the profile.</span></span>

### <span data-ttu-id="f157f-165">スコープを構成するには</span><span class="sxs-lookup"><span data-stu-id="f157f-165">To configure the scope</span></span>

1. <span data-ttu-id="f157f-166">**[Targets]** (ターゲット) で、次の最小限の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f157f-166">For **Targets**, provide the following minimum settings:</span></span>

   - <span data-ttu-id="f157f-167">TARGET COMPUTERS (ターゲット コンピューター)。</span><span class="sxs-lookup"><span data-stu-id="f157f-167">TARGET COMPUTERS.</span></span> <span data-ttu-id="f157f-168">このオプションは、[Specific Computers] (特定のコンピューター) または [All Computers] (すべてのコンピューター) にします。</span><span class="sxs-lookup"><span data-stu-id="f157f-168">The options are Specific Computers or All Computers.</span></span>
   - <span data-ttu-id="f157f-169">TARGET USERS (ターゲット ユーザー)。</span><span class="sxs-lookup"><span data-stu-id="f157f-169">TARGET USERS.</span></span> <span data-ttu-id="f157f-170">このオプションは、[Specific Users] (特定のユーザー) または [All Users] (すべてのユーザー) にします。</span><span class="sxs-lookup"><span data-stu-id="f157f-170">The options are Specific Users or All Users.</span></span>
   - <span data-ttu-id="f157f-171">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f157f-171">Click **Save**.</span></span>
2. <span data-ttu-id="f157f-172">**[Limitations]** (制限) は、既定の設定 [None] のままにします。</span><span class="sxs-lookup"><span data-stu-id="f157f-172">For **Limitations**, keep the default setting: None.</span></span> <span data-ttu-id="f157f-173">[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f157f-173">Click **Cancel**.</span></span>
3. <span data-ttu-id="f157f-174">**[Exclusions]** (除外) は、既定の設定 [None] のままにします。</span><span class="sxs-lookup"><span data-stu-id="f157f-174">For **Exclusions**, keep the default setting: None.</span></span> <span data-ttu-id="f157f-175">[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f157f-175">Click **Cancel**.</span></span>

## <span data-ttu-id="f157f-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="f157f-176">See also</span></span>

- [<span data-ttu-id="f157f-177">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="f157f-177">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="f157f-178">Intune で macOS 用に構成する</span><span class="sxs-lookup"><span data-stu-id="f157f-178">Configure for macOS with Intune</span></span>](configure-microsoft-edge-on-mac.md)
- [<span data-ttu-id="f157f-179">Windows 用に構成する</span><span class="sxs-lookup"><span data-stu-id="f157f-179">Configure for Windows</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="f157f-180">Intune で Windows 用に構成する</span><span class="sxs-lookup"><span data-stu-id="f157f-180">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)
