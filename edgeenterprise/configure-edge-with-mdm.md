---
title: モバイル デバイス管理を使用して Microsoft Edge を構成する
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 10/25/2019
audience: ITPro
ms.topic: technical
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: モバイル デバイス管理を使用して Microsoft Edge を構成します。
ms.openlocfilehash: c9a725b5d0e820fb907150a8f83eeb17291b9f6a
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447551"
---
# <a name="configure-microsoft-edge-using-mobile-device-management"></a><span data-ttu-id="41d3e-103">モバイル デバイス管理を使用して Microsoft Edge を構成する</span><span class="sxs-lookup"><span data-stu-id="41d3e-103">Configure Microsoft Edge using Mobile Device Management</span></span>

<span data-ttu-id="41d3e-104">この記事では、[ADMX インジェスト](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)を通じ、[モバイル デバイス管理 (MDM)](/windows/client-management/mdm/) を使用して、Windows 10 で Microsoft Edge を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-104">This article explains how to configure Microsoft Edge on Windows 10 using [Mobile Device Management (MDM)](/windows/client-management/mdm/) by means of [ADMX Ingestion](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration).</span></span> <span data-ttu-id="41d3e-105">以下についても説明します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-105">This article also describes:</span></span>

- <span data-ttu-id="41d3e-106">[Microsoft Edge ポリシー用に Open Mobile Alliance Uniform Resource Identifier (OMA-URI) を作成する](#create-an-oma-uri-for-microsoft-edge-policies)方法。</span><span class="sxs-lookup"><span data-stu-id="41d3e-106">How to [create Open Mobile Alliance Uniform Resource Identifier (OMA-URI) for Microsoft Edge policies](#create-an-oma-uri-for-microsoft-edge-policies).</span></span>
- <span data-ttu-id="41d3e-107">[ADMX インジェストとカスタムの OMA-URI を使用して Intune で Microsoft Edge を構成する](#configure-microsoft-edge-in-intune-using-admx-ingestion)方法。</span><span class="sxs-lookup"><span data-stu-id="41d3e-107">How to [configure Microsoft Edge in Intune using ADMX ingestion and custom OMA-URI](#configure-microsoft-edge-in-intune-using-admx-ingestion).</span></span>

> [!NOTE]
> <span data-ttu-id="41d3e-108">この記事は、Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="41d3e-108">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="41d3e-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="41d3e-109">Prerequisites</span></span>

<span data-ttu-id="41d3e-110">以下の最小システム要件を満たす Windows 10:</span><span class="sxs-lookup"><span data-stu-id="41d3e-110">Windows 10, with the following minimum system requirements:</span></span>

- <span data-ttu-id="41d3e-111">[KB4512941](https://support.microsoft.com/help/4512941/) および [KB4517211](https://support.microsoft.com/help/4517211/) をインストール済みの Windows 10 Version 1903</span><span class="sxs-lookup"><span data-stu-id="41d3e-111">Windows 10, version 1903 with [KB4512941](https://support.microsoft.com/help/4512941/) and [KB4517211](https://support.microsoft.com/help/4517211/) installed</span></span>
- <span data-ttu-id="41d3e-112">[KB4512534](https://support.microsoft.com/help/4512534/) および [KB4520062](https://support.microsoft.com/help/4520062/) をインストール済みの Windows 10 Version 1809</span><span class="sxs-lookup"><span data-stu-id="41d3e-112">Windows 10, version 1809 with [KB4512534](https://support.microsoft.com/help/4512534/) and [KB4520062](https://support.microsoft.com/help/4520062/) installed</span></span>
- <span data-ttu-id="41d3e-113">[KB4512509](https://support.microsoft.com/help/4512509/) および [KB4519978](https://support.microsoft.com/help/4519978) をインストール済みの Windows 10 Version 1803</span><span class="sxs-lookup"><span data-stu-id="41d3e-113">Windows 10, version 1803 with [KB4512509](https://support.microsoft.com/help/4512509/) and [KB4519978](https://support.microsoft.com/help/4519978) installed</span></span>
- <span data-ttu-id="41d3e-114">[KB4516071](https://support.microsoft.com/help/4516071/) および [KB4520006](https://support.microsoft.com/help/4520006) をインストール済みの Windows 10 Version 1709</span><span class="sxs-lookup"><span data-stu-id="41d3e-114">Windows 10, version 1709 with [KB4516071](https://support.microsoft.com/help/4516071/) and [KB4520006](https://support.microsoft.com/help/4520006) installed</span></span>

## <a name="overview"></a><span data-ttu-id="41d3e-115">概要</span><span class="sxs-lookup"><span data-stu-id="41d3e-115">Overview</span></span>

<span data-ttu-id="41d3e-116">[ADMX インジェスト](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)をサポートする Enterprise Mobility Management (EMM) または MDM プロバイダーで、MDM を使用して Windows 10 の Microsoft Edge を構成できます。</span><span class="sxs-lookup"><span data-stu-id="41d3e-116">You can configure Microsoft Edge on Windows 10 using MDM with your preferred Enterprise Mobility Management (EMM) or MDM provider that supports [ADMX Ingestion](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration).</span></span>

<span data-ttu-id="41d3e-117">MDM を使用した Microsoft Edge の構成は、次の 2 つのプロセスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="41d3e-117">Configuring Microsoft Edge with MDM is a two part process:</span></span>

1. <span data-ttu-id="41d3e-118">Microsoft Edge ADMX ファイルを EMM または MDM プロバイダーに取り込む。</span><span class="sxs-lookup"><span data-stu-id="41d3e-118">Ingesting the Microsoft Edge ADMX file into your EMM or MDM provider.</span></span> <span data-ttu-id="41d3e-119">ADMX ファイルの取り込み方法については、プロバイダーの説明をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="41d3e-119">See your provider for instructions on how to ingest an ADMX file.</span></span>

   > [!NOTE]
   > <span data-ttu-id="41d3e-120">Microsoft Intune の場合は、「[ADMX インジェストを使用して Intune で Microsoft Edge を構成する](#configure-microsoft-edge-in-intune-using-admx-ingestion)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="41d3e-120">For Microsoft Intune, see [Configure Microsoft Edge in Intune using ADMX ingestion](#configure-microsoft-edge-in-intune-using-admx-ingestion).</span></span>

2. <span data-ttu-id="41d3e-121">[Microsoft Edge ポリシー用の OMA-URI を作成](#create-an-oma-uri-for-microsoft-edge-policies)する。</span><span class="sxs-lookup"><span data-stu-id="41d3e-121">[Creating an OMA-URI for a Microsoft Edge policy](#create-an-oma-uri-for-microsoft-edge-policies).</span></span>

## <a name="create-an-oma-uri-for-microsoft-edge-policies"></a><span data-ttu-id="41d3e-122">Microsoft Edge ポリシー用の OMA-URI を作成する</span><span class="sxs-lookup"><span data-stu-id="41d3e-122">Create an OMA-URI for Microsoft Edge policies</span></span>

<span data-ttu-id="41d3e-123">以下のセクションでは、OMA-URI パスを作成し、必須および推奨のブラウザー ポリシー用に XML 形式で値を検索および定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-123">The following sections describe how to create the OMA-URI path and look up and define the value in XML format for mandatory and recommended browser polices.</span></span>

<span data-ttu-id="41d3e-124">開始する前に、[Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)から Microsoft Edge ポリシー テンプレートフ ァイル (MicrosoftEdgePolicyTemplates.cab) をダウンロードし、内容を展開します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-124">Before you get started download the Microsoft Edge policy templates file (MicrosoftEdgePolicyTemplates.cab) from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise) and extract the contents.</span></span>

<span data-ttu-id="41d3e-125">OMA-URI を定義するには、次の 3 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-125">There are three steps for defining the OMA-URI:</span></span>

1. [<span data-ttu-id="41d3e-126">OMA-URI パスを作成する</span><span class="sxs-lookup"><span data-stu-id="41d3e-126">Create the OMA-URI path</span></span>](#create-the-oma-uri-path)
2. [<span data-ttu-id="41d3e-127">OMA-URI データ型を指定する</span><span class="sxs-lookup"><span data-stu-id="41d3e-127">Specify the OMA-URI data type</span></span>](#specify-the-data-type)
3. [<span data-ttu-id="41d3e-128">OMA-URI 値を設定する</span><span class="sxs-lookup"><span data-stu-id="41d3e-128">Set the OMA-URI value</span></span>](#set-the-value-for-a-browser-policy)

### <a name="create-the-oma-uri-path"></a><span data-ttu-id="41d3e-129">OMA-URI パスを作成する</span><span class="sxs-lookup"><span data-stu-id="41d3e-129">Create the OMA-URI path</span></span>

<span data-ttu-id="41d3e-130">OMA-URI パスを作成するためのガイドとして、次の式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="41d3e-130">Use the following formula as a guide for creating the OMA-URI paths.</span></span> <br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`* <br/><br/>

| <span data-ttu-id="41d3e-131">パラメーター</span><span class="sxs-lookup"><span data-stu-id="41d3e-131">Parameter</span></span>         | <span data-ttu-id="41d3e-132">説明</span><span class="sxs-lookup"><span data-stu-id="41d3e-132">Description</span></span>                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| \<ADMXIngestName> | <span data-ttu-id="41d3e-133">"Edge" を使用するか、管理用テンプレートの取り込み時に定義した名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-133">Use "Edge" or what you defined when ingesting the administrative template.</span></span> <span data-ttu-id="41d3e-134">たとえば、"./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/MicrosoftEdge/Policy/EdgeAdmx" を使用した場合は、"MicrosoftEdge" を使用します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-134">For example, if you used "./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/MicrosoftEdge/Policy/EdgeAdmx", then use "MicrosoftEdge".</span></span><br/><br/> <span data-ttu-id="41d3e-135">`<ADMXIngestionName>` は、ADMX ファイルの取り込み時に使用した名前と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41d3e-135">The `<ADMXIngestionName>` must match what was used when you ingested the ADMX file.</span></span> |
| \<ADMXNamespace>  | <span data-ttu-id="41d3e-136">必須のポリシーと推奨のポリシーのどちらを設定しているかによって、"microsoft_edge" または "microsoft_edge_recommended" を指定します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-136">Either "microsoft_edge" or "microsoft_edge_recommended" depending on whether you're setting a mandatory or recommended policy.</span></span> |
| \<ADMXCategory>   | <span data-ttu-id="41d3e-137">ポリシーの "parentCategory" は、ADMX ファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="41d3e-137">The "parentCategory" of the policy is defined in the ADMX file.</span></span> <span data-ttu-id="41d3e-138">ポリシーがグループ化されていない ("parentCategory" が定義されていない) 場合は、`<ADMXCategory>` を省略します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-138">Omit the `<ADMXCategory>` if the policy isn't grouped (No "parentCategory" defined).</span></span> |
| \<PolicyName>     | <span data-ttu-id="41d3e-139">ポリシー名については、[「ブラウザー ポリシー リファレンス](./microsoft-edge-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="41d3e-139">The policy name can be found in the [Browser policy reference](./microsoft-edge-policies.md) article.</span></span> |

#### <a name="uri-path-example"></a><span data-ttu-id="41d3e-140">URI パスの例:</span><span class="sxs-lookup"><span data-stu-id="41d3e-140">URI path example:</span></span>

<span data-ttu-id="41d3e-141">この例は、`<ADMXIngestName>` ノードの名前が "Edge" で、必須ポリシーを設定する場合を想定しています。</span><span class="sxs-lookup"><span data-stu-id="41d3e-141">For this example, assume the `<ADMXIngestName>` node was named “Edge" and you're setting a mandatory policy.</span></span> <span data-ttu-id="41d3e-142">URI パスは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="41d3e-142">The URI path would be:</span></span><br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~<ADMXCategory>/<PolicyName>`*

<span data-ttu-id="41d3e-143">ポリシーがグループに含まれていない場合 (DiskCacheSize など)、`~<ADMXCategory>` を削除します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-143">If the policy isn't in a group (for example, DiskCacheSize) remove "`~<ADMXCategory>`".</span></span> <span data-ttu-id="41d3e-144">`<PolicyName>` をポリシーの名前「DiskCacheSize」に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="41d3e-144">Replace `<PolicyName>` with the name of the policy, DiskCacheSize.</span></span> <span data-ttu-id="41d3e-145">URI パスは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="41d3e-145">The URI path would be:</span></span><br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`*

<span data-ttu-id="41d3e-146">ポリシーがグループ内にある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-146">If the policy is in a group, follow these steps:</span></span>

1. <span data-ttu-id="41d3e-147">任意の xml エディターを使用して **msedge.admx** を開きます。</span><span class="sxs-lookup"><span data-stu-id="41d3e-147">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="41d3e-148">設定するポリシー名を検索します </span><span class="sxs-lookup"><span data-stu-id="41d3e-148">Search for the policy name you want to set.</span></span> <span data-ttu-id="41d3e-149">("ExtensionInstallForceList" など)。</span><span class="sxs-lookup"><span data-stu-id="41d3e-149">For example, "ExtensionInstallForceList".</span></span>
3. <span data-ttu-id="41d3e-150">*parentCategory* 要素の *ref* 属性の値を使用します </span><span class="sxs-lookup"><span data-stu-id="41d3e-150">Use the value of the *ref* attribute from the *parentCategory* element.</span></span> <span data-ttu-id="41d3e-151">たとえば、\<parentCategory ref=" Extensions"/> の「拡張機能」です。</span><span class="sxs-lookup"><span data-stu-id="41d3e-151">For example, "Extensions" from \<parentCategory ref=" Extensions"/>.</span></span>
4. <span data-ttu-id="41d3e-152">`<ADMXCategory>` を *ref* 属性値に置き換えて、URI パスを作成します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-152">Replace `<ADMXCategory>` with the *ref* attribute value to construct the URI path.</span></span> <span data-ttu-id="41d3e-153">URI パスは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="41d3e-153">The URI path would be:</span></span><br/><br/>
*`/Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`*

### <a name="specify-the-data-type"></a><span data-ttu-id="41d3e-154">データ型を指定する</span><span class="sxs-lookup"><span data-stu-id="41d3e-154">Specify the data type</span></span>

<span data-ttu-id="41d3e-155">OMA URI のデータ型は常に "String" です。</span><span class="sxs-lookup"><span data-stu-id="41d3e-155">The OMA-URI data type is always “String”.</span></span>

### <a name="set-the-value-for-a-browser-policy"></a><span data-ttu-id="41d3e-156">ブラウザー ポリシーの値を設定する</span><span class="sxs-lookup"><span data-stu-id="41d3e-156">Set the value for a browser policy</span></span>

<span data-ttu-id="41d3e-157">このセクションでは、データ型ごとに XML 形式で値を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-157">This section describes how to set the value, in XML format, for each data type.</span></span> <span data-ttu-id="41d3e-158">ポリシーのデータ型については、「[ブラウザー ポリシー リファレンス](./microsoft-edge-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="41d3e-158">Go to [Browser policy reference](./microsoft-edge-policies.md) to look up the data type of the policy.</span></span>

> [!NOTE]
> <span data-ttu-id="41d3e-159">Boolean でないデータ型の場合、値は常に `<enabled/>` で始まります。</span><span class="sxs-lookup"><span data-stu-id="41d3e-159">For non-Boolean data types, the value always starts with `<enabled/>`.</span></span>

#### <a name="boolean-data-type"></a><span data-ttu-id="41d3e-160">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="41d3e-160">Boolean data type</span></span>

<span data-ttu-id="41d3e-161">Boolean 型のポリシーの場合は、`<enabled/>` また `<disabled/>` を使用します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-161">For policies that are Boolean types use `<enabled/>` or `<disabled/>`.</span></span>

#### <a name="integer-data-type"></a><span data-ttu-id="41d3e-162">Integer データ型</span><span class="sxs-lookup"><span data-stu-id="41d3e-162">Integer data type</span></span>

<span data-ttu-id="41d3e-163">値は常に`<enabled/>` 要素から始まり、その後に `<data id="[valueName]" value="[decimal value]"/>` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41d3e-163">The value always needs to start with the `<enabled/>` element followed by `<data id="[valueName]" value="[decimal value]"/>`.</span></span>

<span data-ttu-id="41d3e-164">新しいタブ ページの値の名前と 10 進値を検出するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-164">To find the value name and decimal value for a new tab page, use the following steps:</span></span>

1. <span data-ttu-id="41d3e-165">任意の xml エディターを使用して **msedge.admx** を開きます。</span><span class="sxs-lookup"><span data-stu-id="41d3e-165">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="41d3e-166">設定したポリシー名と一致する name 属性の `<policy>`要素を探します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-166">Search for the `<policy>` element where the name attribute matches the policy name you want to set.</span></span> <span data-ttu-id="41d3e-167">"RestoreOnStartup" の場合は、`name="RestoreOnStartup"` を探します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-167">For "RestoreOnStartup", search for `name="RestoreOnStartup"`.</span></span>
3. <span data-ttu-id="41d3e-168">`<elements>` ノードで、設定する値を探します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-168">In the `<elements>` node, find the value you want to set.</span></span>
4. <span data-ttu-id="41d3e-169">`<elements>` ノード内の "valueName" 属性に含まれる値を使用します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-169">Use the value in the "valueName" attribute in the `<elements>` node.</span></span> <span data-ttu-id="41d3e-170">"RestoreOnStartup" の場合、"valueName" は "RestoreOnStartup" です。</span><span class="sxs-lookup"><span data-stu-id="41d3e-170">For "RestoreOnStartup" the "valueName" is "RestoreOnStartup".</span></span>
5. <span data-ttu-id="41d3e-171">`<decimal>` ノード内の "value" 属性に含まれる値を使用します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-171">Use the value in the "value" attribute in the `<decimal>` node.</span></span> <span data-ttu-id="41d3e-172">"RestoreOnStartup" で新しいタブ ページを開く場合、値は "5" になります。</span><span class="sxs-lookup"><span data-stu-id="41d3e-172">For "RestoreOnStartup" to open the new tab page the value is "5".</span></span>

<span data-ttu-id="41d3e-173">起動時に新しいタブ ページを開くには、以下を使用します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-173">To open the new tab page on startup use:</span></span><br>
`<enabled/> <data id="RestoreOnStartup" value="5"/>`

#### <a name="list-of-strings-data-type"></a><span data-ttu-id="41d3e-174">文字列データ型のリスト</span><span class="sxs-lookup"><span data-stu-id="41d3e-174">List of strings data type</span></span>

<span data-ttu-id="41d3e-175">値は常に`<enabled/>` 要素から始まり、その後に `<data id="[listID]" value="[string 1];[string 2];[string 3]"/>` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41d3e-175">The value always needs to start with the `<enabled/>` element followed by `<data id="[listID]" value="[string 1];[string 2];[string 3]"/>`.</span></span>

> [!NOTE]
> <span data-ttu-id="41d3e-176">"id=" 属性名はポリシー名ではありません (ほとんどの場合はポリシー名と一致します)。</span><span class="sxs-lookup"><span data-stu-id="41d3e-176">The "id=" attribute name isn't the policy name, even though in most cases it matches the policy name.</span></span> <span data-ttu-id="41d3e-177">これは、ADMX ファイルに含まれている、\<list> ノードの ID 属性値です。</span><span class="sxs-lookup"><span data-stu-id="41d3e-177">It's the \<list> node id attribute value, which is found in the ADMX file.</span></span>

<span data-ttu-id="41d3e-178">listID を見つけて URL をブロックするための値を定義するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="41d3e-178">To find the listID and define the value to block a URL, follow these steps:</span></span>

1. <span data-ttu-id="41d3e-179">任意の xml エディターを使用して **msedge.admx** を開きます。</span><span class="sxs-lookup"><span data-stu-id="41d3e-179">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="41d3e-180">設定したポリシー名と一致する name 属性の `<policy>`要素を探します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-180">Search for the `<policy>` element where the name attribute matches the policy name you want to set.</span></span> <span data-ttu-id="41d3e-181">"URLBlocklist" の場合は、`name="URLBlocklist"` を探します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-181">For "URLBlocklist", search for `name="URLBlocklist"`.</span></span>
3. <span data-ttu-id="41d3e-182">`<list> node for [listID]` の "id" 属性に含まれる値を使用します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-182">Use the value in the "id" attribute of the `<list> node for [listID]`.</span></span>
4. <span data-ttu-id="41d3e-183">"value" は、セミコロン (;) で区切られた URL のリストです。</span><span class="sxs-lookup"><span data-stu-id="41d3e-183">The "value" is a list of URLs separated by a semicolon (;)</span></span>

<span data-ttu-id="41d3e-184">たとえば、`contoso.com` および `https://ssl.server.com` へのアクセスをブロックするには、次のように指定します: </span><span class="sxs-lookup"><span data-stu-id="41d3e-184">For example, to block access to `contoso.com` and `https://ssl.server.com`:</span></span><br>
`<enabled/> <data id=" URLBlocklistDesc" value="contoso.com;https://ssl.server.com"/>`

#### <a name="dictionary-or-string-data-type"></a><span data-ttu-id="41d3e-185">Dictionary または String データ型</span><span class="sxs-lookup"><span data-stu-id="41d3e-185">Dictionary or String data type</span></span>

<span data-ttu-id="41d3e-186">値は常に `<enabled/>` から始まり、その後に `<data id="[textID]" value="[string]"/>` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41d3e-186">The value always needs to start with the `<enabled/>` followed by `<data id="[textID]" value="[string]"/>` .</span></span>

<span data-ttu-id="41d3e-187">textID を見つけてロケースを設定するための値を定義するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="41d3e-187">To find the textID and define the value set the locale, follow these steps:</span></span>

1. <span data-ttu-id="41d3e-188">任意の xml エディターを使用して **msedge.admx** を開きます。</span><span class="sxs-lookup"><span data-stu-id="41d3e-188">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="41d3e-189">設定したポリシー名と一致する name 属性の `<policy>`要素を探します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-189">Search for the `<policy>` element where the name attribute matches the policy name you want to set.</span></span> <span data-ttu-id="41d3e-190">"ApplicationLocaleValue" の場合は、`name="ApplicationLocaleValue"` を探します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-190">For "ApplicationLocaleValue", search for `name="ApplicationLocaleValue"`.</span></span>
3. <span data-ttu-id="41d3e-191">`[textID]` に対応する `<text>` ノードの "id" 属性に含まれる値を使用します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-191">Use the value in the "id" attribute of the `<text>` node for `[textID]`.</span></span>
4. <span data-ttu-id="41d3e-192">"value" をカルチャ コードに設定します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-192">Set the "value" to the culture code.</span></span>

<span data-ttu-id="41d3e-193">"ApplicationLocaleValue" ポリシーを使用してロケールを "es-US" に設定するには、次のように指定します: </span><span class="sxs-lookup"><span data-stu-id="41d3e-193">To set the locale to "es-US" with the "ApplicationLocaleValue" policy:</span></span><br>
`<enabled/> <data id="ApplicationLocaleValue" value="es-US"/>`

### <a name="create-the-oma-uri-for-a-recommended-policies"></a><span data-ttu-id="41d3e-194">推奨ポリシー用の OMA URI を作成する</span><span class="sxs-lookup"><span data-stu-id="41d3e-194">Create the OMA-URI for a recommended policies</span></span>

<span data-ttu-id="41d3e-195">推奨ポリシーの URI パスを定義する方法は、構成するポリシーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="41d3e-195">Defining the URI path for recommended policies depends on the policy you want to configure.</span></span>

#### <a name="to-define-the-uri-path-for-a-recommended-policy"></a><span data-ttu-id="41d3e-196">推奨ポリシーの URI パスを定義するには</span><span class="sxs-lookup"><span data-stu-id="41d3e-196">To define the URI path for a recommended policy</span></span>

<span data-ttu-id="41d3e-197">URI パスを定義するには、URI パスの式 (*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`*) と以下の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-197">Use the URI path formula (*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`*) and the following steps to define the URI path:</span></span>

1. <span data-ttu-id="41d3e-198">任意の xml エディターを使用して **msedge.admx** を開きます。</span><span class="sxs-lookup"><span data-stu-id="41d3e-198">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="41d3e-199">構成するポリシーがグループに含まれていない場合は、手順 4 に進み、パスから `~<ADMXCategory>` を削除します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-199">If the policy you want to configure isn't in a group, skip to step 4 and remove `~<ADMXCategory>` from the path.</span></span>
3. <span data-ttu-id="41d3e-200">構成するポリシーがグループに含まれている場合:</span><span class="sxs-lookup"><span data-stu-id="41d3e-200">If the policy you want to configure is in a group:</span></span>

   - <span data-ttu-id="41d3e-201">`<ADMXCategory>` を探すには、設定するポリシーを検索します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-201">To look up the `<ADMXCategory>`, search for the policy you want to set.</span></span> <span data-ttu-id="41d3e-202">検索する際には、ポリシー名に "_recommended" を追加します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-202">When searching append "_recommended" to the policy name.</span></span> <span data-ttu-id="41d3e-203">たとえば、"RegisteredProtocolHandlers_recommended” を検索すると、次のような結果になります。</span><span class="sxs-lookup"><span data-stu-id="41d3e-203">For example, a search for "RegisteredProtocolHandlers_recommended” has the following result:</span></span>

        ```xml
         <policy class="Both" displayName="$(string.RegisteredProtocolHandlers)" explainText="$(string.RegisteredProtocolHandlers_Explain)" key="Software\Policies\Microsoft\Edge\Recommended" name="RegisteredProtocolHandlers_recommended" presentation="$(presentation.RegisteredProtocolHandlers)">
           <parentCategory ref="ContentSettings_recommended"/>
           <supportedOn ref="SUPPORTED_WIN7_V77"/>
           <elements>
             <text id="RegisteredProtocolHandlers" maxLength="1000000" valueName="RegisteredProtocolHandlers"/>
           </elements>
         </policy>
        ```

   - <span data-ttu-id="41d3e-204">`<parentCategory>` 要素の *ref* 属性の値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="41d3e-204">Copy the value of the *ref* attribute from the `<parentCategory>` element.</span></span> <span data-ttu-id="41d3e-205">"ContentSettings" の場合は、`<parentCategory ref=" ContentSettings_recommended"/>` から "ContentSettings_recommended" をコピーします。</span><span class="sxs-lookup"><span data-stu-id="41d3e-205">For "ContentSettings", copy "ContentSettings_recommended" from `<parentCategory ref=" ContentSettings_recommended"/>`.</span></span>
   - <span data-ttu-id="41d3e-206">`<ADMXCategory>` を *ref* 属性値に置き換えて、URI パス式内の URI パスを作成します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-206">Replace `<ADMXCategory>` with the *ref* attribute value to construct the URI path in the URI path formula.</span></span>

4. <span data-ttu-id="41d3e-207">`<PolicyName>`は、"_recommended" が付加されたポリシーの名前です。</span><span class="sxs-lookup"><span data-stu-id="41d3e-207">The `<PolicyName>` is the name of the policy with "_recommended" appended to it.</span></span>

#### <a name="oma-uri-path-examples-for-recommended-policies"></a><span data-ttu-id="41d3e-208">推奨ポリシーの OMA URI パスの例</span><span class="sxs-lookup"><span data-stu-id="41d3e-208">OMA-URI path examples for recommended policies</span></span>

<span data-ttu-id="41d3e-209">次の表に、推奨ポリシーの OMA-URI パスの例を示します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-209">The following table shows examples of OMA-URI paths for recommended policies.</span></span>

|              <span data-ttu-id="41d3e-210">ポリシー</span><span class="sxs-lookup"><span data-stu-id="41d3e-210">Policy</span></span>               |             <span data-ttu-id="41d3e-211">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="41d3e-211">OMA-URI</span></span>                      |
|-----------------------------------|------------------------------------------|
| [<span data-ttu-id="41d3e-212">RegisteredProtocolHandlers</span><span class="sxs-lookup"><span data-stu-id="41d3e-212">RegisteredProtocolHandlers</span></span>](./microsoft-edge-policies.md#registeredprotocolhandlers)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~ContentSettings_recommended/RegisteredProtocolHandlers_recommended`                        |
| [<span data-ttu-id="41d3e-213">PasswordManagerEnabled</span><span class="sxs-lookup"><span data-stu-id="41d3e-213">PasswordManagerEnabled</span></span>](./microsoft-edge-policies.md#passwordmanagerenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~PasswordManager_recommended/PasswordManagerEnabled_recommended`                        |
| [<span data-ttu-id="41d3e-214">PrintHeaderFooter</span><span class="sxs-lookup"><span data-stu-id="41d3e-214">PrintHeaderFooter</span></span>](./microsoft-edge-policies.md#printheaderfooter)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Printing_recommended/PrintHeaderFooter_recommended`                        |
| [<span data-ttu-id="41d3e-215">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="41d3e-215">SmartScreenEnabled</span></span>](./microsoft-edge-policies.md#smartscreenenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~SmartScreen_recommended/SmartScreenEnabled_recommended`                        |
| [<span data-ttu-id="41d3e-216">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="41d3e-216">HomePageLocation</span></span>](./microsoft-edge-policies.md#homepagelocation)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/HomepageLocation_recommended`                        |
| [<span data-ttu-id="41d3e-217">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="41d3e-217">ShowHomeButton</span></span>](./microsoft-edge-policies.md#showhomebutton)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/ShowHomeButton_recommended`                        |
| [<span data-ttu-id="41d3e-218">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="41d3e-218">FavoritesBarEnabled</span></span>](./microsoft-edge-policies.md#favoritesbarenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~/FavoritesBarEnabled_recommended`                        |

### <a name="oma-uri-examples"></a><span data-ttu-id="41d3e-219">OMA-URI の例</span><span class="sxs-lookup"><span data-stu-id="41d3e-219">OMA-URI examples</span></span>

<span data-ttu-id="41d3e-220">OMA-URI の例を URI パス、型、値の例と共に示します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-220">OMA-URI examples with their URI path, type, and an example value.</span></span>

#### <a name="boolean-data-type-examples"></a><span data-ttu-id="41d3e-221">Boolean データ型の例</span><span class="sxs-lookup"><span data-stu-id="41d3e-221">Boolean data type examples</span></span>

*<span data-ttu-id="41d3e-222">[ShowHomeButton](./microsoft-edge-policies.md#ShowHomeButton):</span><span class="sxs-lookup"><span data-stu-id="41d3e-222">[ShowHomeButton](./microsoft-edge-policies.md#ShowHomeButton):</span></span>*

| <span data-ttu-id="41d3e-223">フィールド</span><span class="sxs-lookup"><span data-stu-id="41d3e-223">Field</span></span>   | <span data-ttu-id="41d3e-224">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-224">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="41d3e-225">名前</span><span class="sxs-lookup"><span data-stu-id="41d3e-225">Name</span></span>    | <span data-ttu-id="41d3e-226">Microsoft Edge: ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="41d3e-226">Microsoft Edge: ShowHomeButton</span></span>                                                       |
| <span data-ttu-id="41d3e-227">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="41d3e-227">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton` |
| <span data-ttu-id="41d3e-228">型</span><span class="sxs-lookup"><span data-stu-id="41d3e-228">type</span></span>    | <span data-ttu-id="41d3e-229">String</span><span class="sxs-lookup"><span data-stu-id="41d3e-229">String</span></span>                                                                               |
| <span data-ttu-id="41d3e-230">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-230">Value</span></span>   | `<enabled/>`                                                                          |

*<span data-ttu-id="41d3e-231">[DefaultSearchProviderEnabled](./microsoft-edge-policies.md#DefaultSearchProviderEnabled):</span><span class="sxs-lookup"><span data-stu-id="41d3e-231">[DefaultSearchProviderEnabled](./microsoft-edge-policies.md#DefaultSearchProviderEnabled):</span></span>*

| <span data-ttu-id="41d3e-232">フィールド</span><span class="sxs-lookup"><span data-stu-id="41d3e-232">Field</span></span>   | <span data-ttu-id="41d3e-233">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-233">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="41d3e-234">名前</span><span class="sxs-lookup"><span data-stu-id="41d3e-234">Name</span></span>    | <span data-ttu-id="41d3e-235">Microsoft Edge: DefaultSearchProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="41d3e-235">Microsoft Edge: DefaultSearchProviderEnabled</span></span>                                         |
| <span data-ttu-id="41d3e-236">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="41d3e-236">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~DefaultSearchProvider/DefaultSearchProviderEnabled`    |
| <span data-ttu-id="41d3e-237">型</span><span class="sxs-lookup"><span data-stu-id="41d3e-237">type</span></span>    | <span data-ttu-id="41d3e-238">String</span><span class="sxs-lookup"><span data-stu-id="41d3e-238">String</span></span>                                                                               |
| <span data-ttu-id="41d3e-239">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-239">Value</span></span>   | `<disable/>`                                                                          |

### <a name="integer-data-type-examples"></a><span data-ttu-id="41d3e-240">Integer データ型の例</span><span class="sxs-lookup"><span data-stu-id="41d3e-240">Integer data type examples</span></span>

*<span data-ttu-id="41d3e-241">[AutoImportAtFirstRun](./microsoft-edge-policies.md#AutoImportAtFirstRun):</span><span class="sxs-lookup"><span data-stu-id="41d3e-241">[AutoImportAtFirstRun](./microsoft-edge-policies.md#AutoImportAtFirstRun):</span></span>*

| <span data-ttu-id="41d3e-242">フィールド</span><span class="sxs-lookup"><span data-stu-id="41d3e-242">Field</span></span>   | <span data-ttu-id="41d3e-243">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-243">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="41d3e-244">名前</span><span class="sxs-lookup"><span data-stu-id="41d3e-244">Name</span></span>    | <span data-ttu-id="41d3e-245">Microsoft Edge: AutoImportAtFirstRun</span><span class="sxs-lookup"><span data-stu-id="41d3e-245">Microsoft Edge: AutoImportAtFirstRun</span></span>                                                 |
| <span data-ttu-id="41d3e-246">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="41d3e-246">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/AutoImportAtFirstRun`   |
| <span data-ttu-id="41d3e-247">型</span><span class="sxs-lookup"><span data-stu-id="41d3e-247">type</span></span>    | <span data-ttu-id="41d3e-248">String</span><span class="sxs-lookup"><span data-stu-id="41d3e-248">String</span></span>                                                                               |
| <span data-ttu-id="41d3e-249">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-249">Value</span></span>   | `<enabled/><data id="AutoImportAtFirstRun" value="1"/>`                             |

*<span data-ttu-id="41d3e-250">[DefaultImagesSetting](./microsoft-edge-policies.md#DefaultImagesSetting):</span><span class="sxs-lookup"><span data-stu-id="41d3e-250">[DefaultImagesSetting](./microsoft-edge-policies.md#DefaultImagesSetting):</span></span>*

| <span data-ttu-id="41d3e-251">フィールド</span><span class="sxs-lookup"><span data-stu-id="41d3e-251">Field</span></span>   | <span data-ttu-id="41d3e-252">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-252">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="41d3e-253">名前</span><span class="sxs-lookup"><span data-stu-id="41d3e-253">Name</span></span>    | <span data-ttu-id="41d3e-254">Microsoft Edge: DefaultImagesSetting</span><span class="sxs-lookup"><span data-stu-id="41d3e-254">Microsoft Edge: DefaultImagesSetting</span></span>                                                 |
| <span data-ttu-id="41d3e-255">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="41d3e-255">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ContentSettings/DefaultImagesSetting`    |
| <span data-ttu-id="41d3e-256">型</span><span class="sxs-lookup"><span data-stu-id="41d3e-256">type</span></span>    | <span data-ttu-id="41d3e-257">String</span><span class="sxs-lookup"><span data-stu-id="41d3e-257">String</span></span>                                                                               |
| <span data-ttu-id="41d3e-258">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-258">Value</span></span>   | `<enabled/><data id="DefaultImagesSetting" value="2"/>`                             |

*<span data-ttu-id="41d3e-259">[DiskCacheSize](./microsoft-edge-policies.md#DiskCacheSize):</span><span class="sxs-lookup"><span data-stu-id="41d3e-259">[DiskCacheSize](./microsoft-edge-policies.md#DiskCacheSize):</span></span>*

| <span data-ttu-id="41d3e-260">フィールド</span><span class="sxs-lookup"><span data-stu-id="41d3e-260">Field</span></span>   | <span data-ttu-id="41d3e-261">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-261">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="41d3e-262">名前</span><span class="sxs-lookup"><span data-stu-id="41d3e-262">Name</span></span>    | <span data-ttu-id="41d3e-263">Microsoft Edge: DiskCacheSize</span><span class="sxs-lookup"><span data-stu-id="41d3e-263">Microsoft Edge: DiskCacheSize</span></span>                                                        |
| <span data-ttu-id="41d3e-264">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="41d3e-264">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`        |
| <span data-ttu-id="41d3e-265">型</span><span class="sxs-lookup"><span data-stu-id="41d3e-265">type</span></span>    | <span data-ttu-id="41d3e-266">String</span><span class="sxs-lookup"><span data-stu-id="41d3e-266">String</span></span>                                                                               |
| <span data-ttu-id="41d3e-267">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-267">Value</span></span>   | `<enabled/><data id="DiskCacheSize" value="1000000"/>`                               |

#### <a name="list-of-strings-data-type-examples"></a><span data-ttu-id="41d3e-268">文字列データ型のリストの例</span><span class="sxs-lookup"><span data-stu-id="41d3e-268">List of strings data type examples</span></span>
<!--
*[NotificationsAllowedForUrls](./microsoft-edge-policies.md#NotificationsAllowedForUrls):*

| Field   | Value                                                                                |
|---------|--------------------------------------------------------------------------------------|
| Name    | Microsoft Edge: NotificationsAllowedForUrls                                          |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ContentSettings/NotificationsAllowedForUrls`    |
| Type    | String                                                                               |
| Value   | `<enabled/><data id="NotificationsAllowedForUrlsDesc" value="https://www.contoso.com"/>`<br>For multiple list items: `<data id="NotificationsAllowedForUrlsDesc" value="https://www.contoso.com;[*.]contoso.edu"/>`                               |
-->
*<span data-ttu-id="41d3e-269">[RestoreOnStartupURLS](./microsoft-edge-policies.md#RestoreOnStartupURLS):</span><span class="sxs-lookup"><span data-stu-id="41d3e-269">[RestoreOnStartupURLS](./microsoft-edge-policies.md#RestoreOnStartupURLS):</span></span>*

| <span data-ttu-id="41d3e-270">フィールド</span><span class="sxs-lookup"><span data-stu-id="41d3e-270">Field</span></span>   | <span data-ttu-id="41d3e-271">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-271">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="41d3e-272">名前</span><span class="sxs-lookup"><span data-stu-id="41d3e-272">Name</span></span>    | <span data-ttu-id="41d3e-273">Microsoft Edge: RestoreOnStartupURLS</span><span class="sxs-lookup"><span data-stu-id="41d3e-273">Microsoft Edge: RestoreOnStartupURLS</span></span>                                                 |
| <span data-ttu-id="41d3e-274">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="41d3e-274">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/RestoreOnStartupURLs`    |
| <span data-ttu-id="41d3e-275">型</span><span class="sxs-lookup"><span data-stu-id="41d3e-275">Type</span></span>    | <span data-ttu-id="41d3e-276">String</span><span class="sxs-lookup"><span data-stu-id="41d3e-276">String</span></span>                                                                               |
| <span data-ttu-id="41d3e-277">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-277">Value</span></span>   | `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com"/>`<br><span data-ttu-id="41d3e-278">複数のリスト項目のがある場合: </span><span class="sxs-lookup"><span data-stu-id="41d3e-278">For multiple list items:</span></span> `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com&#xF000;2&#xF000;http://www.microsoft.com"/>`  |

*<span data-ttu-id="41d3e-279">[ExtensionInstallForcelist](./microsoft-edge-policies.md#ExtensionInstallForcelist):</span><span class="sxs-lookup"><span data-stu-id="41d3e-279">[ExtensionInstallForcelist](./microsoft-edge-policies.md#ExtensionInstallForcelist):</span></span>*

| <span data-ttu-id="41d3e-280">フィールド</span><span class="sxs-lookup"><span data-stu-id="41d3e-280">Field</span></span>   | <span data-ttu-id="41d3e-281">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-281">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="41d3e-282">名前</span><span class="sxs-lookup"><span data-stu-id="41d3e-282">Name</span></span>    | <span data-ttu-id="41d3e-283">Microsoft Edge: ExtensionInstallForcelist</span><span class="sxs-lookup"><span data-stu-id="41d3e-283">Microsoft Edge: ExtensionInstallForcelist</span></span>                                            |
| <span data-ttu-id="41d3e-284">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="41d3e-284">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`    |
| <span data-ttu-id="41d3e-285">型</span><span class="sxs-lookup"><span data-stu-id="41d3e-285">Type</span></span>    | <span data-ttu-id="41d3e-286">String</span><span class="sxs-lookup"><span data-stu-id="41d3e-286">String</span></span>                                                                               |
| <span data-ttu-id="41d3e-287">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-287">Value</span></span>   | `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000;gbchcmhmhahfdphkhkmpfmihenigjmpp;https://extensionwebstorebase.edgesv.net/v1/crx"/>`                               |

#### <a name="dictionary-and-string-data-type-example"></a><span data-ttu-id="41d3e-288">Dictionary および String データ型の例</span><span class="sxs-lookup"><span data-stu-id="41d3e-288">Dictionary and String data type example</span></span>

*<span data-ttu-id="41d3e-289">[ProxyMode](./microsoft-edge-policies.md#ProxyMode):</span><span class="sxs-lookup"><span data-stu-id="41d3e-289">[ProxyMode](./microsoft-edge-policies.md#ProxyMode):</span></span>*

| <span data-ttu-id="41d3e-290">フィールド</span><span class="sxs-lookup"><span data-stu-id="41d3e-290">Field</span></span>   | <span data-ttu-id="41d3e-291">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-291">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="41d3e-292">名前</span><span class="sxs-lookup"><span data-stu-id="41d3e-292">Name</span></span>    | <span data-ttu-id="41d3e-293">Microsoft Edge: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="41d3e-293">Microsoft Edge: ProxyMode</span></span>                                                            |
| <span data-ttu-id="41d3e-294">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="41d3e-294">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ProxyMode/ProxyMode`  |
| <span data-ttu-id="41d3e-295">型</span><span class="sxs-lookup"><span data-stu-id="41d3e-295">Type</span></span>    | <span data-ttu-id="41d3e-296">String</span><span class="sxs-lookup"><span data-stu-id="41d3e-296">String</span></span>                                                                               |
| <span data-ttu-id="41d3e-297">値</span><span class="sxs-lookup"><span data-stu-id="41d3e-297">Value</span></span>   | `<enabled/><data id="ProxyMode" value="auto_detect"/>`                               |

## <a name="configure-microsoft-edge-in-intune-using-admx-ingestion"></a><span data-ttu-id="41d3e-298">ADMX インジェストを使用して Intune で Microsoft Edge を構成する</span><span class="sxs-lookup"><span data-stu-id="41d3e-298">Configure Microsoft Edge in Intune using ADMX ingestion</span></span>

<span data-ttu-id="41d3e-299">Microsoft Intune を使用して Microsoft Edge を構成する場合は、「[Microsoft Intune を使って Microsoft Edge ポリシー設定を構成する](./configure-edge-with-intune.md)」の説明に従って管理用テンプレート プロファイルを使用する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="41d3e-299">The recommended way to configure Microsoft Edge with Microsoft Intune is to use the Administrative Templates profile as described in [Configure Microsoft Edge policy settings with Microsoft Intune](./configure-edge-with-intune.md).</span></span> <span data-ttu-id="41d3e-300">Intune の Microsoft Edge 管理用テンプレートで現在使用できないポリシーを評価する場合は、[Intune で Windows 10 デバイス用カスタム設定](/intune/configuration/custom-settings-windows-10)を使用して Microsoft Edge を構成できます。</span><span class="sxs-lookup"><span data-stu-id="41d3e-300">If you want to evaluate a policy that is currently not available in the Microsoft Edge Administrative Templates in Intune you can configure Microsoft Edge using  [custom settings for Windows 10 devices in Intune](/intune/configuration/custom-settings-windows-10).</span></span>

<span data-ttu-id="41d3e-301">このセクションでは、以下の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-301">This section describes how to:</span></span>

1. [<span data-ttu-id="41d3e-302">Microsoft Edge ADMX ファイルを Intune に取り込む</span><span class="sxs-lookup"><span data-stu-id="41d3e-302">Ingest the Microsoft Edge ADMX file into Intune</span></span>](#ingest-the-microsoft-edge-admx-file-into-intune)
2. [<span data-ttu-id="41d3e-303">Intune でカスタムの OMA URI を使用してポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="41d3e-303">Set a policy using custom OMA-URI in Intune</span></span>](#set-a-policy-using-custom-oma-uri-in-intune)

> [!IMPORTANT]
> <span data-ttu-id="41d3e-304">ベスト プラクティスとして、Intune でカスタムの OMA-URI プロファイルと管理テンプレート プロファイルを使用して、同じ Microsoft Edge 設定を構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="41d3e-304">As a best practice, don’t use a custom OMA-URI profile and an Administration templates profile to configure the same Microsoft Edge setting in Intune.</span></span> <span data-ttu-id="41d3e-305">カスタムの OMA-URI と管理用テンプレート プロファイルの両方を使用して、値が異なる同じポリシーを展開すると、予期しない結果を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="41d3e-305">If you deploy the same policy using both a custom OMA-URI  and an Administrative template profile, but with different values, users will get unpredictable results.</span></span> <span data-ttu-id="41d3e-306">管理用テンプレート プロファイルを使用する場合は、事前にOMA-URI プロファイルを削除するよう強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="41d3e-306">We strongly recommend removing your OMA-URI profile before using an Administration templates profile.</span></span>

### <a name="ingest-the-microsoft-edge-admx-file-into-intune"></a><span data-ttu-id="41d3e-307">Microsoft Edge ADMX ファイルを Intune に取り込む</span><span class="sxs-lookup"><span data-stu-id="41d3e-307">Ingest the Microsoft Edge ADMX file into Intune</span></span>

<span data-ttu-id="41d3e-308">このセクションでは、Microsoft Edge 管理用テンプレート (**msedge.admx**ファイル) を Intune に取り込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-308">This section describes how to ingest the Microsoft Edge administrative template (**msedge.admx** file) into Intune.</span></span>

> [!WARNING]
> <span data-ttu-id="41d3e-309">ADMX ファイルは、取り込み前に変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="41d3e-309">Don't modify the ADMX file before ingesting the file.</span></span>

<span data-ttu-id="41d3e-310">ADMX ファイルを取り込むには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-310">To ingest the ADMX file, follow these steps:</span></span>

1. <span data-ttu-id="41d3e-311">[Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)から Microsoft Edge ポリシー テンプレートフ ァイル (MicrosoftEdgePolicyTemplates.cab) をダウンロードし、内容を展開します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-311">Download the Microsoft Edge policy templates file (MicrosoftEdgePolicyTemplates.cab) from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise) and extract the contents.</span></span> <span data-ttu-id="41d3e-312">取り込むファイルは **msedge.admx** です。</span><span class="sxs-lookup"><span data-stu-id="41d3e-312">The file that you want to ingest is **msedge.admx**.</span></span>
2. <span data-ttu-id="41d3e-313">[Microsoft Azure portal](https://portal.azure.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="41d3e-313">Sign in to the [Microsoft Azure portal](https://portal.azure.com).</span></span>
3. <span data-ttu-id="41d3e-314">_[すべてのサービス]_ から **[Intune]** を選択するか、ポータルの検索ボックスで Intune を検索します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-314">Select **Intune** from _All Services_, or search for Intune in the portal search box.</span></span>
4. <span data-ttu-id="41d3e-315">_[Microsoft Intune - 概要]_ で、**[デバイス構成]** | **[プロファイル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-315">From _Microsoft Intune - Overview_, select **Device configuration** | **Profiles**.</span></span>
5. <span data-ttu-id="41d3e-316">上部のコマンド バーで、**[+ プロファイルの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-316">On the top command bar, select **+ Create profile**.</span></span>

   ![デバイス プロファイルの作成](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile.png)

6. <span data-ttu-id="41d3e-318">以下のプロファイル情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-318">Provide the following profile information:</span></span>

   - <span data-ttu-id="41d3e-319">**[名前]**: わかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-319">**Name**: Enter a descriptive name.</span></span> <span data-ttu-id="41d3e-320">この例では、「Microsoft Edge ADMX ingested configuration」です。</span><span class="sxs-lookup"><span data-stu-id="41d3e-320">For this example, "Microsoft Edge ADMX ingested configuration".</span></span>
   - <span data-ttu-id="41d3e-321">**[説明]**: プロファイルの説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="41d3e-321">**Description**: Enter an optional description for the profile.</span></span>
   - <span data-ttu-id="41d3e-322">**[プラットフォーム]**: [Windows 10 以降] を選択します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-322">**Platform**: Select "Windows 10 and later"</span></span>
   - <span data-ttu-id="41d3e-323">**[プロファイルの種類]**: [カスタム] を選択します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-323">**Profile type**: Select "Custom"</span></span>

7. <span data-ttu-id="41d3e-324">**[カスタム OMA-URI 設定]** で **[追加]** をクリックして ADMX インジェストを追加します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-324">On **Custom OMA-URI Settings**, click **Add** to add an ADMX ingestion.</span></span>

   ![OMA URI 用にインジェストを追加する](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-add-omauri.png)

8. <span data-ttu-id="41d3e-326">**[行の追加]** で、以下の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-326">On **Add Row**, provide the following information:</span></span>

   - <span data-ttu-id="41d3e-327">**[名前]**: わかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-327">**Name**: Enter a descriptive name.</span></span> <span data-ttu-id="41d3e-328">この例では、「Microsoft Edge ADMX ingestion」を使用します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-328">For this example, use "Microsoft Edge ADMX ingestion".</span></span>
   - <span data-ttu-id="41d3e-329">**[説明]**: 設定の説明を入力します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="41d3e-329">**Description**: Enter an optional description for the setting.</span></span>
   - <span data-ttu-id="41d3e-330">**[OMA-URI]**: 「*./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/Edge/Policy/EdgeAdmx*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-330">**OMA-URI**: Enter "*./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/Edge/Policy/EdgeAdmx*"</span></span>
   - <span data-ttu-id="41d3e-331">**[データ型]**: [String] を選択します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-331">**Data type**: Select "String"</span></span>
   - <span data-ttu-id="41d3e-332">**[値]**: この入力領域は、**[データ型]** を選択した後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="41d3e-332">**Value**: This input area appears after you select the **Data type**.</span></span> <span data-ttu-id="41d3e-333">手順 1. で抽出した Microsoft Edge ポリシー テンプレート ファイルから msedge.admx ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="41d3e-333">Open the msedge.admx file from the Microsoft Edge policy templates file you extracted in step 1.</span></span> <span data-ttu-id="41d3e-334">msedge.admx ファイルから**すべてのテキスト**をコピーし、次のスクリーンショットに示されている **[値]** テキスト領域に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="41d3e-334">Copy **ALL the text** from the msedge.admx file and paste it in the **Value** text area shown in the following screenshot.</span></span>

        ![ADMX インジェストの追加](./media/edge-cfg-with-mdm/configure-edge-intune-mdm-omauri-addrow-ingest.png)

   - <span data-ttu-id="41d3e-336">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41d3e-336">Click **OK**.</span></span>

9. <span data-ttu-id="41d3e-337">**[カスタム OMA-URI 設定]** で、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41d3e-337">On **Custom OMA-URI Settings**, click **OK**.</span></span>
10. <span data-ttu-id="41d3e-338">**[プロファイルの作成]** で、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41d3e-338">On **Create profile**, click **Create**.</span></span> <span data-ttu-id="41d3e-339">次のスクリーンショットは、新しく作成されたプロファイルに関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="41d3e-339">The next screenshot shows information about the newly created profile.</span></span>

    ![<span data-ttu-id="41d3e-340">新しいデバイス プロファイル情報</span><span class="sxs-lookup"><span data-stu-id="41d3e-340">New device profile information</span></span> ](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-done.png)

<!--
> [!NOTE]
> You can use the preceding steps to ingest the msedgeupate.admx policy template file.
-->
### <a name="set-a-policy-using-custom-oma-uri-in-intune"></a><span data-ttu-id="41d3e-341">Intune でカスタムの OMA URI を使用してポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="41d3e-341">Set a policy using custom OMA-URI in Intune</span></span>

> [!NOTE]
> <span data-ttu-id="41d3e-342">このセクションの手順を使用する前に、「[Microsoft Edge ADMX ファイルを Intune に取り込む](#ingest-the-microsoft-edge-admx-file-into-intune)」で説明されている手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41d3e-342">Before using the steps in this section you must complete the steps described in [Ingest the Microsoft Edge ADMX file into Intune](#ingest-the-microsoft-edge-admx-file-into-intune).</span></span>

1. <span data-ttu-id="41d3e-343">[Microsoft Azure portal](https://portal.azure.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="41d3e-343">Sign in to the [Microsoft Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="41d3e-344">_[すべてのサービス]_ から **[Intune]** を選択するか、ポータルの検索ボックスで Intune を検索します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-344">Select **Intune** from _All Services_, or search for Intune in the portal search box.</span></span>
3. <span data-ttu-id="41d3e-345">**[Intune]**>**[デバイスの構成]**>**[プロファイル]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-345">Go to **Intune**>**Device configuration**>**Profiles**.</span></span>
4. <span data-ttu-id="41d3e-346">"Microsoft Edge ADMX ingested configuration" プロファイルか、独自にプロファイルに使用した名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-346">Select the "Microsoft Edge ADMX ingested configuration" profile or the name you used for the profile.</span></span>
5. <span data-ttu-id="41d3e-347">Microsoft Edge ポリシー設定を追加するには、**[カスタム OMA-URI 設定]** を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="41d3e-347">To add Microsoft Edge policy settings, you have to open **Custom OMA-URI Settings**.</span></span> <span data-ttu-id="41d3e-348">**[管理]**、**[プロパティ]**、**[設定]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="41d3e-348">Under **Manage**, click **Properties**, and then click **Settings**.</span></span>

    ![プロファイル設定の構成](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings.png)

6. <span data-ttu-id="41d3e-350">**[カスタム OMA-URI 設定]** で、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41d3e-350">On **Custom OMA-URI Settings**, click **Add**.</span></span>

    ![OMA-URI 設定に行を追加する](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings-add-row.png)

7. <span data-ttu-id="41d3e-352">**[行の追加]** で、以下の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-352">On **Add Row**, provide the following information:</span></span>

   - <span data-ttu-id="41d3e-353">**[名前]**: わかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-353">**Name**: Enter a descriptive name.</span></span> <span data-ttu-id="41d3e-354">構成するポリシー名を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="41d3e-354">We suggest using the policy name you want to configure.</span></span> <span data-ttu-id="41d3e-355">この例では、"ShowHomeButton" を使用します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-355">For this example, use "ShowHomeButton".</span></span>
   - <span data-ttu-id="41d3e-356">**[説明]** (オプション): 設定の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-356">**Description** (Optional): Enter a description for the setting.</span></span>
   - <span data-ttu-id="41d3e-357">**[OMA-URI]**: ポリシーの OMA-URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-357">**OMA-URI**: Enter the OMA-URI for the policy.</span></span> <span data-ttu-id="41d3e-358">例として "ShowHomeButton" ポリシーの場合は、"*./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton*" を使用します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-358">Using the for "ShowHomeButton" policy as an example, use this string: "*./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton*"</span></span>
   - <span data-ttu-id="41d3e-359">**[データ型]**: ポリシー設定のデータ型を選択します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-359">**Data type**: Select the policy settings data type.</span></span> <span data-ttu-id="41d3e-360">"ShowHomeButton" ポリシーの場合は、"String" を使用します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-360">For the "ShowHomeButton" policy, use "String"</span></span>
   - <span data-ttu-id="41d3e-361">**[値]**: ポリシー用に構成する設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-361">**Value**: Enter the setting that you want to configure for the policy.</span></span> <span data-ttu-id="41d3e-362">「ShowHomeButton」の例では、「\<enabled/>」と入力します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-362">For "ShowHomeButton" example, enter "\<enabled/>".</span></span> <span data-ttu-id="41d3e-363">次のスクリーン ショットは、ポリシーを構成する場合の設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="41d3e-363">The following screenshot shows the settings for configuring a policy.</span></span>

        ![[行の追加] の OMA-URI 設定](./media/edge-cfg-with-mdm/configure-edge-mdm-custom-omauri-setting.png)

   - <span data-ttu-id="41d3e-365">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41d3e-365">Click **OK**.</span></span>

8. <span data-ttu-id="41d3e-366">**[カスタム OMA-URI 設定]** で、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41d3e-366">On **Custom OMA-URI Settings**, click **OK**.</span></span>
9. <span data-ttu-id="41d3e-367">**[Microsoft Edge ADMX ingested configuration - プロパティ]** プロファイル (または、独自に使用した名前) で、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41d3e-367">On the "**Microsoft Edge ADMX ingested configuration - Properties**" profile (or the name you used), click **Save**.</span></span>

<span data-ttu-id="41d3e-368">プロファイルが作成され、プロパティが設定されたら、[Microsoft Intune でプロファイルを割り当てる](/intune/configuration/device-profile-assign)必要があります。</span><span class="sxs-lookup"><span data-stu-id="41d3e-368">After the profile is created and the properties set, you have to [assign the profile in Microsoft Intune](/intune/configuration/device-profile-assign).</span></span>

#### <a name="confirm-that-the-policy-was-set"></a><span data-ttu-id="41d3e-369">ポリシーが設定されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="41d3e-369">Confirm that the policy was set</span></span>

<span data-ttu-id="41d3e-370">作成したプロファイルが Microsoft Edge ポリシーで使用されていることを確認するには、次の手順に従います </span><span class="sxs-lookup"><span data-stu-id="41d3e-370">Use the following steps to confirm that the Microsoft Edge policy is using the profile you created.</span></span> <span data-ttu-id="41d3e-371">("Microsoft Edge ADMX ingested configuration" プロファイルの例で割り当てたデバイスに、Microsoft Intune からポリシーが伝達されるまで、多少時間がかかる場合があります)。</span><span class="sxs-lookup"><span data-stu-id="41d3e-371">(Give Microsoft Intune time to propagate the policy to a device you assigned in the "Microsoft Edge ADMX ingested configuration" profile example.)</span></span>

1. <span data-ttu-id="41d3e-372">Microsoft Edge を開き、*edge://policy* に移動します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-372">Open Microsoft Edge and go to *edge://policy*.</span></span>
2. <span data-ttu-id="41d3e-373">**[ポリシー]** ページで、プロファイルに設定したポリシーが一覧に含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-373">On the **Policies** page, see if the policy you set in the profile is listed.</span></span>
3. <span data-ttu-id="41d3e-374">ポリシーが表示されていない場合の対処方法については、「[Windows 10 での MDM エラーの診断](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10)」または「[ポリシー設定のトラブルシューティング](#troubleshoot-a-policy-setting)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="41d3e-374">If your policy isn't shown, see [Diagnose MDM failures in Windows 10](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) or [Troubleshoot a policy setting](#troubleshoot-a-policy-setting).</span></span>

#### <a name="troubleshoot-a-policy-setting"></a><span data-ttu-id="41d3e-375">ポリシー設定のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="41d3e-375">Troubleshoot a policy setting</span></span>

<span data-ttu-id="41d3e-376">Microsoft Edge ポリシーが有効にならない場合は、次の手順をお試しください。</span><span class="sxs-lookup"><span data-stu-id="41d3e-376">If a Microsoft Edge policy isn’t taking effect, try the following steps:</span></span>

<span data-ttu-id="41d3e-377">ターゲット デバイス (Microsoft Intune でプロファイルを割り当てたデバイス) で *edge://policy* ページを開き、ポリシーを検索します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-377">Open the *edge://policy* page on the target device (a device you assigned the profile to in Microsoft Intune) and search for the policy.</span></span> <span data-ttu-id="41d3e-378">*edge://policy* ページにポリシーがない場合は、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-378">If the policy isn’t on the *edge://policy* page, try the following:</span></span>

- <span data-ttu-id="41d3e-379">ポリシーがレジストリに保存されており、正しく定義されていることを確認する。</span><span class="sxs-lookup"><span data-stu-id="41d3e-379">Check that the policy is in the registry and is correct.</span></span> <span data-ttu-id="41d3e-380">ターゲット デバイスでopen the Windows 10 レジストリエディターを開きます (**Windows キー + r** キーを押し、「*regedit*」と入力して **Enter** キーを押します)。ポリシーが、*\Software\Policies\ Microsoft\Edge* パスに正しく定義されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="41d3e-380">On the target device open the Windows 10 Registry Editor (**Windows key + r**, enter “*regedit*” and then press **Enter**.) Check that the policy is correctly defined in the *\Software\Policies\ Microsoft\Edge* path.</span></span> <span data-ttu-id="41d3e-381">適切なパスにポリシーがない場合は、ポリシーがデバイスに正しくプッシュされていません。</span><span class="sxs-lookup"><span data-stu-id="41d3e-381">If you don’t find the policy in the expected path, then the policy wasn’t pushed to the device correctly.</span></span>
- <span data-ttu-id="41d3e-382">OMA-URI パスが正しく、値が有効な XML 文字列であることを確認する。</span><span class="sxs-lookup"><span data-stu-id="41d3e-382">Check that the OMA-URI path is correct, and the value is a valid XML string.</span></span> <span data-ttu-id="41d3e-383">いずれかに誤りがあれば、ポリシーがターゲット デバイスにプッシュされません。</span><span class="sxs-lookup"><span data-stu-id="41d3e-383">If either of these are incorrect the policy won’t be pushed to the target device.</span></span>

<span data-ttu-id="41d3e-384">トラブルシューティングのヒントについては、「[Microsoft Intune をセットアップする](/intune/fundamentals/setup-steps)」と「[デバイスの同期](/intune/remote-actions/device-sync)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="41d3e-384">For more trouble shooting tips, see [Set up Microsoft Intune](/intune/fundamentals/setup-steps) and [Sync devices](/intune/remote-actions/device-sync).</span></span>

## <a name="see-also"></a><span data-ttu-id="41d3e-385">関連項目</span><span class="sxs-lookup"><span data-stu-id="41d3e-385">See also</span></span>

- [<span data-ttu-id="41d3e-386">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="41d3e-386">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="41d3e-387">Microsoft Intune を使って Microsoft Edge ポリシー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="41d3e-387">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](configure-edge-with-intune.md)
- [<span data-ttu-id="41d3e-388">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="41d3e-388">Mobile device management</span></span>](/windows/client-management/mdm/)
- [<span data-ttu-id="41d3e-389">Intune で Windows 10 デバイスにカスタム設定を使用する</span><span class="sxs-lookup"><span data-stu-id="41d3e-389">Use custom settings for Windows 10 devices in Intune</span></span>](/intune/configuration/custom-settings-windows-10)
- [<span data-ttu-id="41d3e-390">Win32 およびデスクトップ ブリッジ アプリ ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="41d3e-390">Win32 and Desktop Bridge app policy configuration</span></span>](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)
- [<span data-ttu-id="41d3e-391">ADMX ベースのポリシーについて</span><span class="sxs-lookup"><span data-stu-id="41d3e-391">Understanding ADMX-backed policies</span></span>](/windows/client-management/mdm/understanding-admx-backed-policies)