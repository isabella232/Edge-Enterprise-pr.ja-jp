---
title: Jamf を使用して macOS の Microsoft Edge を構成する
ms.author: brianalt
author: dan-wesley
manager: laurawi
ms.date: 02/20/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Jamf を使用して Mac デバイスの Microsoft Edge ポリシー設定を構成する
ms.openlocfilehash: 336bdfed2c53811615b0183dc5ca7db916cd7428
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980358"
---
# <span data-ttu-id="1aea6-103">Jamf を使用して macOS の Microsoft Edge ポリシー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="1aea6-103">Configure Microsoft Edge policy settings on macOS with Jamf</span></span>

<span data-ttu-id="1aea6-104">この記事では、Jamf Pro 10.19 の Microsoft Edge ポリシー マニフェスト ファイルを使用して、macOS のポリシー設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-104">This article describes how to configure policy settings on macOS using a Microsoft Edge policy manifest file on Jamf Pro 10.19.</span></span>

<span data-ttu-id="1aea6-105">macOS の Microsoft Edge ポリシー設定は、プロパティ リスト (.plist) ファイルを使用して構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-105">You can also configure Microsoft Edge policy settings on macOS by using a property list (.plist) file.</span></span> <span data-ttu-id="1aea6-106">詳細については、「[.plist を使用して macOS 用に構成する](configure-microsoft-edge-on-mac.md)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="1aea6-106">For more information, see [Configure for macOS using a .plist](configure-microsoft-edge-on-mac.md)</span></span>


## <span data-ttu-id="1aea6-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="1aea6-107">Prerequisites</span></span>

<span data-ttu-id="1aea6-108">次のソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="1aea6-108">The following software is required:</span></span>

- <span data-ttu-id="1aea6-109">Microsoft Edge Stable チャネル 81</span><span class="sxs-lookup"><span data-stu-id="1aea6-109">Microsoft Edge Stable channel 81</span></span>
- <span data-ttu-id="1aea6-110">ポリシー テンプレート ファイル (バージョン 81.0.416.3)</span><span class="sxs-lookup"><span data-stu-id="1aea6-110">Policy Templates file, version 81.0.416.3</span></span>
- <span data-ttu-id="1aea6-111">Jamf Pro (バージョン 10.19)</span><span class="sxs-lookup"><span data-stu-id="1aea6-111">Jamf Pro, Version 10.19</span></span>

## <span data-ttu-id="1aea6-112">Jamf Pro の [Application & Custom Settings] メニューについて</span><span class="sxs-lookup"><span data-stu-id="1aea6-112">About the Jamf Pro Application & Custom Settings menu</span></span>

<span data-ttu-id="1aea6-113">Jamf Pro 10.18 以前では、Office 365 の管理には手動による .plist の作成が必要でした。</span><span class="sxs-lookup"><span data-stu-id="1aea6-113">Before Jamf Pro 10.18, managing Office 365 involved manually building a .plist file.</span></span> <span data-ttu-id="1aea6-114">この作業は、強力な技術的バックグラウンドが必要になる、時間のかかるワークフローでした。</span><span class="sxs-lookup"><span data-stu-id="1aea6-114">This was a time-consuming workflow that required a strong technical background.</span></span> <span data-ttu-id="1aea6-115">Jamf Pro 10.18 では、構成プロセスを合理化することで、このような障壁が排除されました。</span><span class="sxs-lookup"><span data-stu-id="1aea6-115">Jamf Pro 10.18 eliminated those barriers by streamlining the configuration process.</span></span> <span data-ttu-id="1aea6-116">ただし、この新しいユーザー インターフェイスは、IT 管理者のみが使用できるものであり、Jamf が指定した特定のアプリケーションと優先ドメインに対応していました。</span><span class="sxs-lookup"><span data-stu-id="1aea6-116">However, IT Admins could only use this new user interface for specific applications and preference domains specified by Jamf.</span></span>

<span data-ttu-id="1aea6-117">Jamf Pro 10.19 では、ユーザーが「カスタム スキーマ」として JSON マニフェストをアップロードすることで任意の優先ドメインをターゲットに設定できます。このマニフェストから、グラフィカル ユーザー インターフェイスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-117">In Jamf Pro 10.19, a user can upload a JSON manifest as a "custom schema" to target any preference domain, and the graphical user interface will be generated from this manifest.</span></span> <span data-ttu-id="1aea6-118">このカスタム スキーマは、JSON スキーマ仕様に従って作成します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-118">The custom schema that's created follows the JSON Schema specification.</span></span>

<span data-ttu-id="1aea6-119">詳細については、Jamf Pro 管理者ガイドの「[コンピューター構成プロファイル](https://jamf.it/computer-configuration-profiles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aea6-119">For more information, see [Computer Configuration Profiles](https://jamf.it/computer-configuration-profiles) in the Jamf Pro Administrator's Guide.</span></span>

## <span data-ttu-id="1aea6-120">Microsoft Edge の特定のバージョン用のポリシー マニフェストを取得する</span><span class="sxs-lookup"><span data-stu-id="1aea6-120">Get the policy manifest for a specific version of Microsoft Edge</span></span>

<span data-ttu-id="1aea6-121">ポリシー マニフェストを取得するには:</span><span class="sxs-lookup"><span data-stu-id="1aea6-121">To get the policy manifest:</span></span>

- <span data-ttu-id="1aea6-122">[Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)に移動します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-122">Go to the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise).</span></span>
- <span data-ttu-id="1aea6-123">[チャネル/バージョン] ドロップダウンリストで、\*\*バージョン 81 以降の任意のチャネル\*\*\*を選択します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-123">On the Channel/Version dropdown list, select \*\*any channel with version 81 or later.\*\*\*.</span></span>
- <span data-ttu-id="1aea6-124">[ビルド] ドロップダウンリストで、任意の \*\*81 ビルド以降\*\*\*を選択します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-124">On the Build dropdown list, select any \*\*81 build or later.\*\*\*.</span></span>
- <span data-ttu-id="1aea6-125">[ポリシー ファイルの取得] をクリックして、ポリシー テンプレートのバンドルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-125">Click GET POLICY FILES to download our policy templates bundle.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1aea6-126">現在、このポリシー テンプレートのバンドルは、CAB ファイルとして署名されています。</span><span class="sxs-lookup"><span data-stu-id="1aea6-126">Currently, the policy templates bundle is signed as a CAB file.</span></span> <span data-ttu-id="1aea6-127">このファイルを macOS で開くには、サード パーティ製ツール (The Unarchiver など) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1aea6-127">You'll need to use a 3rd party tool, such as The Unarchiver to open the file on macOS.</span></span>

<span data-ttu-id="1aea6-128">CAB ファイルを展開してから、ZIP ファイルを展開して、最上位ディレクトリの "mac" に移動します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-128">After you unpack the CAB file, unpack the ZIP file and navigate to the "mac" top level directory.</span></span> <span data-ttu-id="1aea6-129">このディレクトリに、"policy_manifest.json" という名前のマニフェスト ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="1aea6-129">The manifest, which is named "policy_manifest.json", is in this directory.</span></span>

<span data-ttu-id="1aea6-130">このマニフェスト ファイルは、ビルド 81.0.416.3 以降のポリシー バンドルごとに発行されます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-130">This manifest will be published in every policy bundle starting with build 81.0.416.3.</span></span> <span data-ttu-id="1aea6-131">開発用チャネルのポリシーをテストする場合は、それぞれの開発リリースに関連付けられたマニフェストを取得して、そのマニフェストを Jamf Pro でテストしてください。</span><span class="sxs-lookup"><span data-stu-id="1aea6-131">If you want to test policies in the Dev channel, you can take the manifest associated with each Dev release and test it in Jamf Pro.</span></span>  

## <span data-ttu-id="1aea6-132">Jamf Pro でポリシー マニフェストを使用する</span><span class="sxs-lookup"><span data-stu-id="1aea6-132">Use the policy manifest in Jamf Pro</span></span>

<span data-ttu-id="1aea6-133">次の手順を使用して、Jamf Pro にポリシー マニフェストをアップロードし、macOS 用のポリシー プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-133">Use the following steps to upload the policy manifest to Jamf Pro and then create a policy profile for macOS.</span></span>

1. <span data-ttu-id="1aea6-134">Jamf にサインインします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-134">Sign in to Jamf.</span></span>
2. <span data-ttu-id="1aea6-135">**[Computer]** (コンピューター) タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-135">Select the **Computer** tab.</span></span>
3. <span data-ttu-id="1aea6-136">**[Content Management]** (コンテンツ管理) にある **[Configuration Profiles]** (構成プロファイル) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-136">Under **Content Management**, select **Configuration Profiles**.</span></span>
4. <span data-ttu-id="1aea6-137">**[Configuration Profiles]** ページで、**[+ New]** (+ 新規) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-137">On the **Configuration Profiles** page, click **+ New**.</span></span>

   ![Jamf に新しいプロファイルを追加する](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles.png)

5. <span data-ttu-id="1aea6-139">**[New macOS Configuration Profile]** (新規 macOS 構成プロファイル) > **[Options]** (オプション) で、**[Application & Custom Settings]** (アプリケーションとカスタムの設定) を選択します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-139">On **New macOS Configuration Profile**>**Options**, select **Application & Custom Settings**.</span></span>
6. <span data-ttu-id="1aea6-140">**[Application & Custom Settings]** ポップアップ ウィンドウで、**[Configure]** (構成) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-140">On the **Application & Custom Settings** popup window, click **Configure**.</span></span>

   ![アプリケーションとカスタムの設定を構成する](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom.png)

7. <span data-ttu-id="1aea6-142">**[Application & Custom Settings]** セクションで、次のスクリーンショットに示した値を設定します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-142">In the **Application & Custom Settings** section, set the values shown in the following screen shot.</span></span>

   ![プロファイル ソースとカスタム スキーマ](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-schema.png)

   - <span data-ttu-id="1aea6-144">**[Creation Method]** (作成方法) には、**[Configure settings]** (設定を構成する) を選択します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-144">For **Creation Method**, pick **Configure settings**.</span></span>
   - <span data-ttu-id="1aea6-145">**[Source]** (ソース) には、**[Custom Schema]** (カスタム スキーマ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-145">For **Source**, pick **Custom Schema**.</span></span>
   - <span data-ttu-id="1aea6-146">**[Preference Domain]** (優先ドメイン) には、対象のドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-146">For **Preference Domain**, provide the name of your domain.</span></span> <span data-ttu-id="1aea6-147">この例では、そのドメインとして「*com.microsoft.Edge*」を使用します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-147">This example uses *com.microsoft.Edge* as the domain.</span></span>
   - <span data-ttu-id="1aea6-148">**[Custom Schema]** (カスタム スキーマ) には、"policy_manifest.json" マニフェスト ファイルの内容を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-148">For **Custom Schema**, paste the contents of the "policy_manifest.json" manifest file.</span></span>
   - <span data-ttu-id="1aea6-149">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-149">Click **Save**.</span></span>

8. <span data-ttu-id="1aea6-150">プロファイルを保存すると、Jamf により、次のスクリーン ショットに示す **[General]** (全般) セクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-150">After you save the profile, Jamf displays the **General** section shown in the next screen shot.</span></span>

   ![[General] セクションの構成](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-general-setting.png)

   - <span data-ttu-id="1aea6-152">プロファイルの **[Name]** (名前) と **[Description]** (説明) を入力します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-152">Provide a display **Name** for the profile and a **Description**.</span></span>
   - <span data-ttu-id="1aea6-153">**[Category]** (カテゴリ) の既定の設定 **[None]** (なし) は、そのままにします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-153">Keep the default setting for **Category**, which is **None**.</span></span>
   - <span data-ttu-id="1aea6-154">**[Distribution Method]** (配布方法) のオプションは、**[Install Automatically]** (自動的にインストールする) または **[Make Available in Self Service]** (セルフサービスで利用可能にする) にします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-154">For **Distribution Method**, the options are **Install Automatically** or **Make Available in Self Service**.</span></span>
   - <span data-ttu-id="1aea6-155">**[Level]** (レベル) のオプションは、**[User Level]** (ユーザー レベル) または **[Computer Level]** (コンピューター レベル) にします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-155">For **Level**, the options are **User Level** or **Computer Level**.</span></span>
   - <span data-ttu-id="1aea6-156">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-156">Click **Save**.</span></span>

9. <span data-ttu-id="1aea6-157">[General] セクションを保存すると、Jamf により、この記事の例に応じて設定された "Microsoft Edge Beta Channel" 構成プロファイルが示されます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-157">After you save the General section, Jamf shows the "Microsoft Edge Beta Channel" configuration profile set up for our example.</span></span> <span data-ttu-id="1aea6-158">次のスクリーン ショットでは、**[Edit]** (編集) をクリックすることでプロファイルの作業を続行できます。作業が完了している場合は、**[Done]** (完了) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-158">In the next screen shot, note that you can keep working the profile by clicking **Edit** or if you're finished, click **Done**.</span></span>

   ![オプションを設定した新しい構成プロファイル](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel.png)

   > [!NOTE]
   > <span data-ttu-id="1aea6-160">このプロファイルは保存後に、別の Jamf セッションで編集できます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-160">You can edit this profile after it's been saved and in another Jamf session.</span></span> <span data-ttu-id="1aea6-161">たとえば、[Distribution Method] を [Make Available in Self Service] に変更できます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-161">For example, you might decide to change the Distribution Method to Make Available in Self Service.</span></span>

   <span data-ttu-id="1aea6-162">Microsoft Edge Stable チャネルの追加編集や削除を実行する場合は、次のスクリーン ショットに示す [Configuration Profiles] でプロファイル名を選択します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-162">To do a follow up edit on the Microsoft Edge Stable Channel, or delete it, select the profile name, shown in the following Configuration Profiles screen shot.</span></span>

   ![[Configuration Profiles] リスト](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel-done.png)

<span data-ttu-id="1aea6-164">新しい構成プロファイルの作成後には、そのプロファイルの **[Scope]** (スコープ) も構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1aea6-164">After you create the new configuration profile you still have to configure the **Scope** for the profile.</span></span>

### <span data-ttu-id="1aea6-165">スコープを構成するには</span><span class="sxs-lookup"><span data-stu-id="1aea6-165">To configure the scope</span></span>

1. <span data-ttu-id="1aea6-166">**[Targets]** (ターゲット) で、次の最小限の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="1aea6-166">For **Targets**, provide the following minimum settings:</span></span>

   - <span data-ttu-id="1aea6-167">TARGET COMPUTERS (ターゲット コンピューター)。</span><span class="sxs-lookup"><span data-stu-id="1aea6-167">TARGET COMPUTERS.</span></span> <span data-ttu-id="1aea6-168">このオプションは、[Specific Computers] (特定のコンピューター) または [All Computers] (すべてのコンピューター) にします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-168">The options are Specific Computers or All Computers.</span></span>
   - <span data-ttu-id="1aea6-169">TARGET USERS (ターゲット ユーザー)。</span><span class="sxs-lookup"><span data-stu-id="1aea6-169">TARGET USERS.</span></span> <span data-ttu-id="1aea6-170">このオプションは、[Specific Users] (特定のユーザー) または [All Users] (すべてのユーザー) にします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-170">The options are Specific Users or All Users.</span></span>
   - <span data-ttu-id="1aea6-171">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-171">Click **Save**.</span></span>
2. <span data-ttu-id="1aea6-172">**[Limitations]** (制限) は、既定の設定 [None] のままにします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-172">For **Limitations**, keep the default setting: None.</span></span> <span data-ttu-id="1aea6-173">[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-173">Click **Cancel**.</span></span>
3. <span data-ttu-id="1aea6-174">**[Exclusions]** (除外) は、既定の設定 [None] のままにします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-174">For **Exclusions**, keep the default setting: None.</span></span> <span data-ttu-id="1aea6-175">[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1aea6-175">Click **Cancel**.</span></span>

## <span data-ttu-id="1aea6-176">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="1aea6-176">Frequently Asked Questions</span></span>

### <span data-ttu-id="1aea6-177">Microsoft Edge は、マスター基本設定が使用されるように構成できますか?</span><span class="sxs-lookup"><span data-stu-id="1aea6-177">Can Microsoft Edge be configured to use master preferences?</span></span>

<span data-ttu-id="1aea6-178">Microsoft Edge は、マスター基本設定ファイルが使用されるように構成できます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-178">Yes, you can configure Microsoft Edge to use a master preferences file.</span></span>

<span data-ttu-id="1aea6-179">マスター基本設定ファイルを使用すると、Microsoft Edge を展開する際に、ブラウザー ユーザー プロファイルの既定の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-179">A master preferences file lets you configure default settings for a browser user profile when Microsoft Edge is deployed.</span></span> <span data-ttu-id="1aea6-180">マスター基本設定ファイルを使用すると、デバイス管理システムで管理されていないコンピューターに設定を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-180">You can also use a master preferences file to apply settings on computers that aren't managed by a device management system.</span></span> <span data-ttu-id="1aea6-181">これらの設定は、ユーザーがブラウザーを初めて実行するときに、ユーザーのプロファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-181">These settings are applied to the user’s profile the first time the user runs the browser.</span></span> <span data-ttu-id="1aea6-182">ユーザーがブラウザーを実行した後で発生した、マスター基本設定ファイルへの変更は適用されません。</span><span class="sxs-lookup"><span data-stu-id="1aea6-182">After the user runs the browser, changes to the master preferences file aren’t applied.</span></span> <span data-ttu-id="1aea6-183">ユーザーは、ブラウザーでマスター基本設定の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-183">A user can change settings from the master preferences in the browser.</span></span> <span data-ttu-id="1aea6-184">ブラウザーを初めて実行した後に設定を必須にしたり、設定を変更したりする場合は、ポリシーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1aea6-184">If you want to make a setting mandatory or change a setting after the first run of the browser, you must use a policy.</span></span>

<span data-ttu-id="1aea6-185">マスター基本設定ファイルを使用すると、ブラウザーのさまざまな設定や基本設定をカスタマイズできます。これには、他の Chromium ベースのブラウザーと共有されるものや、Microsoft Edge に固有のものも含まれます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-185">A master preferences file lets you to customize many different settings and preferences for the browser, including those shared with other Chromium based browsers and specific to Microsoft Edge.</span></span>  <span data-ttu-id="1aea6-186">ポリシー関連の基本設定は、マスター基本設定ファイルを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-186">Policy related preferences can be configured using the master preferences file.</span></span> <span data-ttu-id="1aea6-187">ポリシーが設定され、対応するマスター基本設定が設定されている場合は、ポリシー設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="1aea6-187">In cases where a policy is set and there’s a corresponding master preference set, the policy setting takes precedence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1aea6-188">利用可能なすべての基本設定が Microsoft Edge の用語や命名規則と一致していないこともあります。</span><span class="sxs-lookup"><span data-stu-id="1aea6-188">All the available preferences might not be consistent with Microsoft Edge terminology and naming conventions.</span></span>  <span data-ttu-id="1aea6-189">これらの基本設定が今後のリリースでも引き続き期待どおりに動作することは保証されません。</span><span class="sxs-lookup"><span data-stu-id="1aea6-189">There’s no guarantee that these preferences will continue to work as expected in future releases.</span></span> <span data-ttu-id="1aea6-190">今後のバージョンでは、基本設定が変更または無視される可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="1aea6-190">Preferences might be changed or ignored in later versions.</span></span>

<span data-ttu-id="1aea6-191">マスター基本設定ファイルは、JSON マークアップを使用して書式設定されたテキスト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="1aea6-191">A master preferences file is a text file that’s formatted using JSON markup.</span></span> <span data-ttu-id="1aea6-192">このファイルは、msedge.exe 実行可能ファイルと同じディレクトリに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1aea6-192">This file needs to be added to the same directory as the msedge.exe executable.</span></span> <span data-ttu-id="1aea6-193">macOS でのシステム全体のエンタープライズ展開では通常、"*~/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*" または "*/Library/Microsoft/Microsoft Edge Master Preferences*" になります。</span><span class="sxs-lookup"><span data-stu-id="1aea6-193">For system wide enterprise deployments on macOS this is typically: “*~/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*" or "*/Library/Microsoft/Microsoft Edge Master Preferences*”.</span></span>

## <span data-ttu-id="1aea6-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="1aea6-194">See also</span></span>

- [<span data-ttu-id="1aea6-195">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="1aea6-195">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="1aea6-196">Intune で macOS 用に構成する</span><span class="sxs-lookup"><span data-stu-id="1aea6-196">Configure for macOS with Intune</span></span>](configure-microsoft-edge-on-mac.md)
- [<span data-ttu-id="1aea6-197">Windows 用に構成する</span><span class="sxs-lookup"><span data-stu-id="1aea6-197">Configure for Windows</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="1aea6-198">Intune で Windows 用に構成する</span><span class="sxs-lookup"><span data-stu-id="1aea6-198">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)
