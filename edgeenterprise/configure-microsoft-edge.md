---
title: Windows 用に Microsoft Edge を構成する
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 10/09/2019
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Windows デバイスで Microsoft Edge ポリシー設定を構成する
ms.openlocfilehash: 99aaf002f868ce29e81aa40024fa1de2e83d76e1
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980353"
---
# <span data-ttu-id="56871-103">Windows で Microsoft Edge ポリシー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="56871-103">Configure Microsoft Edge policy settings on Windows</span></span>

<span data-ttu-id="56871-104">Windows デバイスで Microsoft Edge ポリシー設定を構成するには、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56871-104">Use the following information to configure Microsoft Edge policy settings on your Windows devices.</span></span>

> [!NOTE]
> <span data-ttu-id="56871-105">この記事は、Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="56871-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="56871-106">Windows でポリシー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="56871-106">Configure policy settings on Windows</span></span>

<span data-ttu-id="56871-107">Windows のすべてのバージョンで Microsoft Edge および管理された Microsoft Edge 更新プログラムのポリシー設定を構成するには、_グループ ポリシー オブジェクト (GPO)_ を使用できます。</span><span class="sxs-lookup"><span data-stu-id="56871-107">You can use _group policy objects (GPO)_ to configure policy settings for Microsoft Edge and managed Microsoft Edge updates on all versions of Windows.</span></span> <span data-ttu-id="56871-108">また、Microsoft Active Directory ドメインに参加している Windows デバイスのレジストリか、Microsoft Intune でデバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンスを通じて、ポリシーをプロビジョニングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="56871-108">You can also provision policy through the registry for Windows devices that are joined to a Microsoft Active Directory domain, or Windows 10 Pro or Enterprise instances enrolled for device management in Microsoft Intune.</span></span> <span data-ttu-id="56871-109">グループ ポリシー オブジェクトを使用して Microsoft Edge を構成するには、Active Directory ドメイン内のグループ ポリシー中央ストアまたは各コンピューター上のポリシー定義テンプレート フォルダーに Microsoft Edge の規則と設定を追加するための_管理用テンプレート_をインストールし、設定する特定のポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="56871-109">To configure Microsoft Edge with group policy objects, you install _administrative templates_ that add rules and settings for Microsoft Edge to the group policy Central Store in your Active Directory domain or to the Policy Definition template folder on individual computers and then configure the specific policies you want to set.</span></span>

<span data-ttu-id="56871-110">ドメイン レベルでポリシーを管理する場合は、Active Directory グループ ポリシーを使用して Microsoft Edge ポリシー設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="56871-110">You can use Active Directory group policy to configure Microsoft Edge policy settings if you prefer to manage policy at the domain level.</span></span> <span data-ttu-id="56871-111">これにより、ポリシー設定をグローバルに管理することも、特定の OU に対して異なるポリシー設定を適用することもできます。また、WMI フィルターを使用して、特定のクエリによって返されたユーザーまたはコンピューターにのみ設定を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="56871-111">This enables you to manage policy settings globally, targeting different policy settings to specific OUs, or using WMI filters to apply settings only to users or computers returned by a particular query.</span></span> <span data-ttu-id="56871-112">個々のコンピューターでポリシーを構成する場合は、ターゲット コンピューターのローカル グループ ポリシー エディターを使用して、ローカル デバイスのみに影響するポリシー設定を適用できます。</span><span class="sxs-lookup"><span data-stu-id="56871-112">If you want to configure policy on individual computers, you can apply policy settings that only affect the local device using the Local Group Policy Editor on the target computer.</span></span>

<span data-ttu-id="56871-113">Microsoft Edge では、_必須_および_推奨_のポリシーがどちらもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="56871-113">Microsoft Edge supports both _mandatory_ and _recommended_ policies.</span></span> <span data-ttu-id="56871-114">必須ポリシーはユーザー基本設定を上書きし、ユーザーによる変更ができません。推奨ポリシーは既定の設定を提供し、ユーザーはこれを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="56871-114">Mandatory policies override user preferences and prevents the user from changing it, while recommended policy provide a default setting that may be overridden by the user.</span></span> <span data-ttu-id="56871-115">ほとんどのポリシーは必須のみです。サブセットは必須または推奨です。</span><span class="sxs-lookup"><span data-stu-id="56871-115">Most policies are mandatory only; a subset are mandatory and recommended.</span></span> <span data-ttu-id="56871-116">両方のバージョンのポリシーが設定されている場合は、必須の設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="56871-116">If both versions of a policy are set, the mandatory setting takes precedence.</span></span>

>[!TIP]
> <span data-ttu-id="56871-117">Microsoft Edge ポリシー設定は、Microsoft Intune を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="56871-117">You can use Microsoft Intune to configure Microsoft Edge policy settings.</span></span> <span data-ttu-id="56871-118">詳しくは、「[Microsoft Intune を使用して Microsoft Edge を構成する](configure-edge-with-intune.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="56871-118">For more information, see [Configure Microsoft Edge using Microsoft Intune](configure-edge-with-intune.md).</span></span>

<span data-ttu-id="56871-119">Microsoft Edge には 2 つの管理用テンプレートがあり、どちらもコンピューターまたは Active Directory ドメインのレベルで適用できます。</span><span class="sxs-lookup"><span data-stu-id="56871-119">There are two administrative templates for Microsoft Edge, both of which can be applied either at the computer or Active Directory domain level:</span></span>

- <span data-ttu-id="56871-120">*msedge.admx*: [Microsoft Edge 設定を構成する](microsoft-edge-policies.md)場合に使用。</span><span class="sxs-lookup"><span data-stu-id="56871-120">*msedge.admx* to [configure Microsoft Edge settings](microsoft-edge-policies.md)</span></span>
- <span data-ttu-id="56871-121">*msedgeupdate.admx*: [manage Microsoft Edge 更新プログラムを管理する](microsoft-edge-update-policies.md)場合に使用。</span><span class="sxs-lookup"><span data-stu-id="56871-121">*msedgeupdate.admx* to [manage Microsoft Edge updates](microsoft-edge-update-policies.md).</span></span>

<span data-ttu-id="56871-122">開始するには、Microsoft Edge 管理用テンプレートをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="56871-122">To get started, download and install the Microsoft Edge administrative template.</span></span>

### <span data-ttu-id="56871-123">1. Microsoft Edge 管理用テンプレートをダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="56871-123">1. Download and install the Microsoft Edge administrative template</span></span>

<span data-ttu-id="56871-124">Active Directory で Microsoft Edge ポリシー設定を構成する場合は、リモートサーバー管理ツール (RSAT) がインストールされているドメイン コントローラーまたはワークステーションからアクセスできるネットワーク上の場所にファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="56871-124">If you want to configure Microsoft Edge policy settings in Active Directory, download the files to a network location you can access from a domain controller or a workstation with the Remote Server Administration Tools (RSAT) installed.</span></span> <span data-ttu-id="56871-125">個々のコンピューターで構成を行う場合は、そのコンピューターにファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="56871-125">To configure on an individual computer, simply download the files to that computer.</span></span>

<span data-ttu-id="56871-126">管理用テンプレート ファイルを適切な場所に追加すると、グループ ポリシー エディターで Microsoft Edge ポリシー設定をすぐに使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="56871-126">When you add the administrative template files to the appropriate location, Microsoft Edge policy settings are immediately available in the Group Policy Editor.</span></span>

<span data-ttu-id="56871-127">[Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)に移動して、Microsoft Edge ポリシー テンプレートフ ァイル (*MicrosoftEdgePolicyTemplates.cab*) をダウンロードし、内容を展開します。</span><span class="sxs-lookup"><span data-stu-id="56871-127">Go to the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise) to download the Microsoft Edge policy templates file (*MicrosoftEdgePolicyTemplates.cab*) and extract the contents.</span></span>

#### <span data-ttu-id="56871-128">管理用テンプレートを Active Directory に追加する</span><span class="sxs-lookup"><span data-stu-id="56871-128">Add the administrative template to Active Directory</span></span>

1. <span data-ttu-id="56871-129">RSAT がインストールされているドメイン コントローラーまたはワークステーションで、ドメインの任意のドメイン コントローラー上 **PolicyDefinition** フォルダー (_中央ストア_とも呼ばれます) を参照します。</span><span class="sxs-lookup"><span data-stu-id="56871-129">On a domain controller or workstation with RSAT, browse to the **PolicyDefinition** folder (also known as the _Central Store_) on any domain controller for your domain.</span></span> <span data-ttu-id="56871-130">以前のバージョンの Windows Server では、PolicyDefinition フォルダーの作成が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="56871-130">For older versions of Windows Server, you may need to create the PolicyDefinition folder.</span></span> <span data-ttu-id="56871-131">詳しくは、「[Windows でグループ ポリシー管理用テンプレート用のセントラル ストアを作成および管理する方法](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="56871-131">For more information, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
1. <span data-ttu-id="56871-132">*MicrosoftEdgePolicyTemplates* を開き、**windows** > **admx** に移動します。</span><span class="sxs-lookup"><span data-stu-id="56871-132">Open *MicrosoftEdgePolicyTemplates* and go to **windows** > **admx**.</span></span>
1. <span data-ttu-id="56871-133">*msedge.admx* ファイルを PolicyDefinition フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="56871-133">Copy the *msedge.admx* file to the PolicyDefinition folder.</span></span> <span data-ttu-id="56871-134">(例: %systemroot%\sysvol\domain\policies\PolicyDefinitions)</span><span class="sxs-lookup"><span data-stu-id="56871-134">(Example: %systemroot%\sysvol\domain\policies\PolicyDefinitions)</span></span>
1. <span data-ttu-id="56871-135">*admx* フォルダーで、適切な言語フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="56871-135">In the *admx* folder, open the appropriate language folder.</span></span> <span data-ttu-id="56871-136">たとえば米国内にいる場合は、**en-US** フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="56871-136">For example, if you’re in the U.S., open the **en-US** folder.</span></span>
1. <span data-ttu-id="56871-137">PolicyDefinition フォルダー内にある、一致する言語のフォルダーに、*msedge.adml* ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="56871-137">Copy the *msedge.adml* file to the matching language folder in the PolicyDefinition folder.</span></span> <span data-ttu-id="56871-138">フォルダーが存在しない場合は作成します。</span><span class="sxs-lookup"><span data-stu-id="56871-138">Create the folder if it does not already exist.</span></span> <span data-ttu-id="56871-139">(例: %systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US)</span><span class="sxs-lookup"><span data-stu-id="56871-139">(Example: %systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US)</span></span>
1. <span data-ttu-id="56871-140">ドメインに複数のドメイン コントローラーがある場合、新しい ADMX ファイルは、次回のドメイン レプリケーション時にレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="56871-140">If your domain has more than one domain controller, the new ADMX files will be replicated to them at the next domain replication interval.</span></span>
1. <span data-ttu-id="56871-141">ファイルが正しく読み込まれたことを確認するには、Windows 管理ツールで**グループ ポリシー管理エディター**を開き、**[コンピューターの構成]** > **[ポリシー]** > **[管理用テンプレート]** > **[Microsoft Edge]** の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="56871-141">To confirm the files loaded correctly, open the **Group Policy Management Editor** from Windows Administrative Tools and expand **Computer Configuration** > **Policies** > **Administrative Templates** > **Microsoft Edge**.</span></span> <span data-ttu-id="56871-142">次の図のように、1 つ以上の Microsoft Edge ノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="56871-142">You should see one or more Microsoft Edge nodes as shown below.</span></span>

    ![Microsoft Edge ポリシー](./media/configure-microsoft-edge/edge-gpo-policies.png)

#### <span data-ttu-id="56871-144">管理用テンプレートを個々のコンピューターに追加する</span><span class="sxs-lookup"><span data-stu-id="56871-144">Add the administrative template to an individual computer</span></span>

1. <span data-ttu-id="56871-145">ターゲット コンピューターで、*MicrosoftEdgePolicyTemplates* を開き、**windows** > **admx** に移動します。</span><span class="sxs-lookup"><span data-stu-id="56871-145">On the target computer, open *MicrosoftEdgePolicyTemplates* and go to **windows** > **admx**.</span></span>
2. <span data-ttu-id="56871-146">*msedge.admx* ファイルをポリシー定義テンプレート フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="56871-146">Copy the *msedge.admx* file to your Policy Definition template folder.</span></span> <span data-ttu-id="56871-147">(例: C:\Windows\PolicyDefinitions)</span><span class="sxs-lookup"><span data-stu-id="56871-147">(Example: C:\Windows\PolicyDefinitions)</span></span>
3. <span data-ttu-id="56871-148">*admx* フォルダーで、適切な言語フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="56871-148">In the *admx* folder, open the appropriate language folder.</span></span> <span data-ttu-id="56871-149">たとえば米国内にいる場合は、**en-US** フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="56871-149">For example, if you’re in the U.S., open the **en-US** folder.</span></span>
4. <span data-ttu-id="56871-150">ポリシー定義フォルダー内にある、一致する言語のフォルダーに、*msedge.adml* ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="56871-150">Copy the *msedge.adml* file to the matching language folder in your Policy Definition folder.</span></span> <span data-ttu-id="56871-151">(例: C:\Windows\PolicyDefinitions\en-US)</span><span class="sxs-lookup"><span data-stu-id="56871-151">(Example: C:\Windows\PolicyDefinitions\en-US)</span></span>
5. <span data-ttu-id="56871-152">ファイルが正しく読み込まれたことを確認するには、直接ローカル グループ ポリシー エディターを開くか (Windows キー + R を押して「gpedit.msc」と入力します)、MMC を開いてローカル グループ ポリシー エディター スナップインを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="56871-152">To confirm the files loaded correctly either open Local Group Policy Editor directly (Windows key + R and enter gpedit.msc) or open MMC and load the Local Group Policy Editor snap-in.</span></span> <span data-ttu-id="56871-153">エラーが発生した場合は通常、ファイルの場所が正しくないことが原因です。</span><span class="sxs-lookup"><span data-stu-id="56871-153">If an error occurs, it’s usually because the files are in an incorrect location.</span></span>

<!--
To add the administrative template to manage Microsoft Edge updates:

1. Open the *MicrosoftEdgePolicyTemplates* file and go to **windows** > **admx**.
2. Copy the *msedgeupdate.admx* file to your Policy Definition template folder. (Example: C:\Windows\PolicyDefinitions)
3. In the *updatepolicies* folder, open the appropriate language folder. For example, if you’re in Germany, open the **de-DE** folder.
4. Copy the *msedgeupdate.adml* file to the matching language folder in your Policy Definition folder. (Example: C:\Windows\PolicyDefinitions\de-DE)
5. Open MMC and load the Local Group Policy Editor snap-in to confirm the files loaded correctly. If an error occurs, it’s usually because the files are in an incorrect location.

> [!NOTE]
> Currently the Microsoft Edge update policies are only localized in en-US. Additional language support will be added in a future release.
-->

### <span data-ttu-id="56871-154">2. 必須または推奨のポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="56871-154">2. Set mandatory or recommended policies</span></span>

<span data-ttu-id="56871-155">Active Directory の場合も個々のコンピューターの場合も、グループ ポリシー エディターを使用して、必須または推奨のポリシーを設定して Microsoft Edge を構成できます。</span><span class="sxs-lookup"><span data-stu-id="56871-155">You can set mandatory or recommended policies to configure Microsoft Edge with the Group Policy Editor for both Active Directory and individual computers.</span></span> <span data-ttu-id="56871-156">次の説明に従って適切なノードを選択することによって、ポリシー設定のスコープを **[コンピューターの構成]** または **[ユーザーの構成]** に指定できます。</span><span class="sxs-lookup"><span data-stu-id="56871-156">You can scope policy settings to either the **Computer Configuration** or **User Configuration** by selecting the appropriate node as described below.</span></span>

- <span data-ttu-id="56871-157">必須ポリシーを構成するには、グループ ポリシー エディターを開き、(**[コンピューターの構成]** または **[ユーザーの構成]**) > **[ポリシー]** > **[管理用テンプレート]** > **[Microsoft Edge]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="56871-157">To configure a mandatory policy, open the Group Policy Editor and go to (**Computer Configuration** or **User Configuration**) > **Policies** > **Administrative Templates** > **Microsoft Edge**.</span></span>
- <span data-ttu-id="56871-158">推奨ポリシーを構成するには、グループ ポリシー エディターを開き、(**[コンピューターの構成]** または **[ユーザーの構成]**) > **[ポリシー]** > **[管理用テンプレート]** > **[Microsoft Edge – 規定の設定 (ユーザーはオーバーライドできます)]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="56871-158">To configure a recommended policy, open the Group Policy Editor and go to (**Computer Configuration** or **User Configuration**) > **Policies** > **Administrative Templates** > **Microsoft Edge – Default Settings (users can override)**.</span></span>

  ![グループ ポリシー エディターを開きます。](./media/configure-microsoft-edge/edge-ad-policy.png)

### <span data-ttu-id="56871-160">3. ポリシーをテストする</span><span class="sxs-lookup"><span data-stu-id="56871-160">3. Test your policies</span></span>

<span data-ttu-id="56871-161">対象のクライアント デバイスで、Microsoft Edge を開き、**edge://policy** に移動して、適用されているすべてのポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="56871-161">On a target client device, open Microsoft Edge and navigate to **edge://policy** to see all policies that are applied.</span></span> <span data-ttu-id="56871-162">ポリシー設定をローカル コンピューターに適用した場合は、ポリシーがすぐに表示されます。</span><span class="sxs-lookup"><span data-stu-id="56871-162">If you applied policy settings on the local computer, policies should appear immediately.</span></span> <span data-ttu-id="56871-163">ポリシー設定の構成時に Microsoft Edge を開いていた場合は、一度閉じてから再度開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="56871-163">You may need to close and reopen Microsoft Edge if it was open while you were configuring policy settings.</span></span>

![ブラウザーで構成済みのポリシーの確認](./media/configure-microsoft-edge/edge-gpEdit.png)

<span data-ttu-id="56871-165">Active Directory グループ ポリシー設定では、ドメイン管理者によって定義された一定の間隔でポリシー設定がドメイン コンピューターに伝達され、ターゲット コンピューターには、すぐにポリシーの更新が届かない場合があります。</span><span class="sxs-lookup"><span data-stu-id="56871-165">For Active Directory group policy settings, policy settings are propagated to domain computers at a regular interval defined by your domain administrator, and target computers may not receive policy updates right away.</span></span> <span data-ttu-id="56871-166">ターゲット コンピューターの Active Directory グループ ポリシー設定を手動で更新するには、ターゲット コンピューターのコマンド プロンプトまたは PowerShell セッションから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="56871-166">To manually refresh Active Directory group policy settings on a target computer, execute the following command from a command prompt or PowerShell session on the target computer:</span></span>

``` powershell
gpupdate /force
```

<span data-ttu-id="56871-167">新しいポリシーを表示するには、Microsoft Edge を閉じてから再度開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="56871-167">You may need to close and reopen Microsoft Edge before the new policies appear.</span></span>

<span data-ttu-id="56871-168">ターゲット コンピューターで REGEDIT.exe を使用して、グループ ポリシー設定を保存するレジストリ設定を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="56871-168">You can also use REGEDIT.exe on a target computer to view the registry settings that store group policy settings.</span></span> <span data-ttu-id="56871-169">これらの設定は、レジストリ パス **HKLM\SOFTWARE\Policies\Microsoft\Edge** にあります。</span><span class="sxs-lookup"><span data-stu-id="56871-169">These settings are located at the registry path **HKLM\SOFTWARE\Policies\Microsoft\Edge**.</span></span>

## <span data-ttu-id="56871-170">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="56871-170">Frequently Asked Questions</span></span>

### <span data-ttu-id="56871-171">Microsoft Edge は、マスター基本設定が使用されるように構成できますか?</span><span class="sxs-lookup"><span data-stu-id="56871-171">Can Microsoft Edge be configured to use master preferences?</span></span>

<span data-ttu-id="56871-172">Microsoft Edge は、マスター基本設定ファイルが使用されるように構成できます。</span><span class="sxs-lookup"><span data-stu-id="56871-172">Yes, you can configure Microsoft Edge to use a master preferences file.</span></span>

 <span data-ttu-id="56871-173">マスター基本設定ファイルを使用すると、Microsoft Edge を展開する際に、既定の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="56871-173">A master preferences file lets you configure default settings when Microsoft Edge is deployed.</span></span> <span data-ttu-id="56871-174">マスター基本設定ファイルを使用すると、デバイス管理システムで管理されていないコンピューターに設定を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="56871-174">You can also use a master preferences file to apply settings on computers that aren't managed by a device management system.</span></span> <span data-ttu-id="56871-175">これらの設定は、ユーザーがブラウザーを初めて実行するときに、ユーザーのプロファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="56871-175">These settings are applied to the user’s profile the first time the user runs the browser.</span></span> <span data-ttu-id="56871-176">ユーザーがブラウザーを実行した後で発生した、マスター基本設定ファイルへの変更は適用されません。</span><span class="sxs-lookup"><span data-stu-id="56871-176">After the user runs the browser, changes to the master preferences file aren’t applied.</span></span> <span data-ttu-id="56871-177">ユーザーは、ブラウザーでマスター基本設定の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="56871-177">A user can change settings from the master preferences in the browser.</span></span> <span data-ttu-id="56871-178">ブラウザーを初めて実行した後に設定を必須にしたり、設定を変更したりする場合は、ポリシーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56871-178">If you want to make a setting mandatory or change a setting after the first run of the browser, you must use a policy.</span></span>

<span data-ttu-id="56871-179">マスター基本設定ファイルを使用すると、ブラウザーのさまざまな設定や基本設定をカスタマイズできます。これには、他の Chromium ベースのブラウザーと共有されるものや、Microsoft Edge に固有のものも含まれます。</span><span class="sxs-lookup"><span data-stu-id="56871-179">A master preferences file lets you to customize many different settings and preferences for the browser, including those shared with other Chromium based browsers and specific to Microsoft Edge.</span></span>  <span data-ttu-id="56871-180">ポリシー関連の基本設定は、マスター基本設定ファイルを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="56871-180">Policy related preferences can be configured using the master preferences file.</span></span> <span data-ttu-id="56871-181">ポリシーが設定され、対応するマスター基本設定が設定されている場合は、ポリシー設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="56871-181">In cases where a policy is set and there’s a corresponding master preference set, the policy setting takes precedence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56871-182">利用可能なすべての基本設定が Microsoft Edge の用語や命名規則と一致していないこともあります。</span><span class="sxs-lookup"><span data-stu-id="56871-182">All the available preferences might not be consistent with Microsoft Edge terminology and naming conventions.</span></span>  <span data-ttu-id="56871-183">これらの基本設定が今後のリリースでも引き続き期待どおりに動作することは保証されません。</span><span class="sxs-lookup"><span data-stu-id="56871-183">There’s no guarantee that these preferences will continue to work as expected in future releases.</span></span> <span data-ttu-id="56871-184">今後のバージョンでは、基本設定が変更または無視される可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="56871-184">Preferences might be changed or ignored in later versions.</span></span>

<span data-ttu-id="56871-185">マスター基本設定ファイルは、JSON マークアップを使用して書式設定されたテキスト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="56871-185">A master preferences file is a text file that’s formatted using JSON markup.</span></span> <span data-ttu-id="56871-186">このファイルは、msedge.exe 実行可能ファイルと同じディレクトリに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56871-186">This file needs to be added to the same directory as the msedge.exe executable.</span></span> <span data-ttu-id="56871-187">Windows でのシステム全体のエンタープライズ展開では通常、*Windows: C:\Program Files\Microsoft\Edge\Application\master_preferences* となります。</span><span class="sxs-lookup"><span data-stu-id="56871-187">For system wide enterprise deployments on Windows this is typically: *Windows: C:\Program Files\Microsoft\Edge\Application\master_preferences*.</span></span>

## <span data-ttu-id="56871-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="56871-188">See also</span></span>

- [<span data-ttu-id="56871-189">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="56871-189">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="56871-190">Intune で Windows 用に構成する</span><span class="sxs-lookup"><span data-stu-id="56871-190">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)
- [<span data-ttu-id="56871-191">macOS 用に構成する</span><span class="sxs-lookup"><span data-stu-id="56871-191">Configure for macOS</span></span>](configure-microsoft-edge-on-mac.md)
- [<span data-ttu-id="56871-192">Microsoft Edge エンタープライズ ポリシーを参照する</span><span class="sxs-lookup"><span data-stu-id="56871-192">Browse Microsoft Edge Enterprise Policies</span></span>](microsoft-edge-policies.md)


