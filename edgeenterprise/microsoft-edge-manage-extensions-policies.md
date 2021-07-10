---
title: グループ ポリシーを使用して Microsoft Edge の拡張機能を管理する
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: グループ ポリシーを使用して、エンタープライズの Microsoft Edge 拡張機能を管理する
ms.openlocfilehash: dad239a448ec1f0ebef60c7072bfaad5c3baed57
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641373"
---
# <a name="use-group-policies-to-manage-microsoft-edge-extensions"></a><span data-ttu-id="0ac23-103">グループ ポリシーを使用して Microsoft Edge の拡張機能を管理する</span><span class="sxs-lookup"><span data-stu-id="0ac23-103">Use group policies to manage Microsoft Edge extensions</span></span>

<span data-ttu-id="0ac23-104">この記事では、グループ ポリシーを使用して拡張機能を管理するためのオプションと手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-104">This article describes the options and steps for managing extensions by using group policies.</span></span> <span data-ttu-id="0ac23-105">これらのオプションは、ユーザー向けに Microsoft Edge が既に管理されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0ac23-105">These options  assume that you already have Microsoft Edge managed for your users.</span></span> <span data-ttu-id="0ac23-106">ユーザー向けに管理する Microsoft Edge をまだ設定していない場合は、以下のリンクをたどって今すぐ設定してください。</span><span class="sxs-lookup"><span data-stu-id="0ac23-106">If you have not already set up Microsoft Edge to be managed for your users please follow the below link to do so now.</span></span>

- [<span data-ttu-id="0ac23-107">エンタープライズの Microsoft Edge 拡張機能を管理する</span><span class="sxs-lookup"><span data-stu-id="0ac23-107">Manage Microsoft Edge extensions in the enterprise</span></span>](/deployedge/microsoft-edge-manage-extensions)

> [!NOTE]
> <span data-ttu-id="0ac23-108">この記事は Microsoft Edge バージョン 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-108">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="block-extensions-based-on-their-permissions"></a><span data-ttu-id="0ac23-109">アクセス許可に基づいて拡張機能をブロックする</span><span class="sxs-lookup"><span data-stu-id="0ac23-109">Block extensions based on their permissions</span></span>

<span data-ttu-id="0ac23-110">[ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) ポリシーを使用して、アクセス許可に基づいてユーザーがインストールできる拡張機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-110">You can control what extensions your users can install based on permissions using the [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) policy.</span></span> <span data-ttu-id="0ac23-111">インストールされている拡張機能にブロックされているアクセス許可が必要な場合は、実行されません。</span><span class="sxs-lookup"><span data-stu-id="0ac23-111">If an installed extension needs a permission that’s blocked, it just won't run.</span></span> <span data-ttu-id="0ac23-112">拡張機能は削除されず、無効になるだけです。</span><span class="sxs-lookup"><span data-stu-id="0ac23-112">The extension isn't removed, just disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="0ac23-113">ブロックされたアクセス許可の設定は、拡張機能の設定ポリシー内でのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-113">The blocked permissions setting can only be set within the extension settings policy.</span></span>  

<span data-ttu-id="0ac23-114">拡張機能をブロックするためのガイドとして、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-114">Use the following steps as a guide for blocking an extension.</span></span>

1. <span data-ttu-id="0ac23-115">グループ ポリシー管理エディターを開き、**[管理用テンプレート] > [Microsoft Edge] > [拡張機能]** に移動し、**[拡張機能管理設定を構成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-115">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions**  and then select **Configure extension management settings**.</span></span>
2. <span data-ttu-id="0ac23-116">ポリシーを有効にし、圧縮される JSON 文字列を使用して、許可またはブロックするアクセス許可を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-116">Enable the policy, then enter the permissions that you want allowed or blocked, by using a JSON string that gets compressed.</span></span> <span data-ttu-id="0ac23-117">次のスクリーンショットは、アクセス許可 "usb" を使用する拡張機能をブロックする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0ac23-117">The next screenshot shows how to block an extension that uses the permission "usb".</span></span>

    :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-1.png" alt-text="拡張機能をブロックするようにグループ ポリシーを構成します。":::

<span data-ttu-id="0ac23-119">次の例は、アクセス許可 "usb" とその圧縮文字列を使用する必要がある拡張機能をブロックする JSON を示しています。</span><span class="sxs-lookup"><span data-stu-id="0ac23-119">The following example shows the JSON to block any extension that needs the use of permission "usb" and its compressed string.</span></span>

### <a name="json-example"></a><span data-ttu-id="0ac23-120">JSON の例</span><span class="sxs-lookup"><span data-stu-id="0ac23-120">JSON example</span></span>

   ```json
   { 
        "*": { 
             "blocked_permissions": ["usb"] 
        } 
   } 
   ```

   ```json
   {"*":{"blocked_permissions":["usb"]}} 
   ```

   > [!NOTE]
   > <span data-ttu-id="0ac23-121">アクセス許可を使用するすべての拡張機能をブロックするには、前の例に示すように、拡張子 ID にアスタリスクを使用します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-121">To block all extensions that use the permission, use an asterisk for the extension ID, as shown in the previous example.</span></span> <span data-ttu-id="0ac23-122">1 つの拡張子 ID を指定すると、ポリシーはその拡張機能にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-122">If you specify one extension ID, the policy will only apply to that extension.</span></span> <span data-ttu-id="0ac23-123">複数をブロックできますが、それらは別々のエントリである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ac23-123">You can block more than one, but they need to be separate entries.</span></span>

## <a name="prevent-extensions-from-altering-web-pages"></a><span data-ttu-id="0ac23-124">拡張機能による Web ページの変更を防止する</span><span class="sxs-lookup"><span data-stu-id="0ac23-124">Prevent extensions from altering web pages</span></span>

<span data-ttu-id="0ac23-125">この設定により、拡張機能が機密性の高い Web サイトやドメインからデータを読み取ったり変更したりするのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-125">This setting prevents extensions from reading and changing  data from sensitive websites and domains.</span></span> <span data-ttu-id="0ac23-126">不要なアクションをブロックするには、Web サイトへのスクリプトの挿入、Cookie の読み取り、Web 要求の変更などのアクションをブロックします。</span><span class="sxs-lookup"><span data-stu-id="0ac23-126">Blocking unwanted actions is done by blocking actions such as script injection into your websites, reading the cookies, or making web-request modifications.</span></span> <span data-ttu-id="0ac23-127">この設定は、ユーザーが拡張機能をインストールまたは削除するのを防ぐのではなく、拡張機能が指定された Web サイトを変更するのを防ぐだけです。</span><span class="sxs-lookup"><span data-stu-id="0ac23-127">This setting doesn’t prevent your users from installing or removing extensions, it only prevents extensions from altering the specified websites.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0ac23-128">[ランタイムが許可/ブロックされたホスト] 設定は、拡張機能の設定ポリシー内でのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-128">The Runtime allowed/blocked hosts setting can only be set within the extension settings policy.</span></span>  

<span data-ttu-id="0ac23-129">ExtensionSettings ポリシーで、Web サイトまたはドメインの変更を防止 (または許可) するように、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-129">You can configure the following settings in the ExtensionSettings policy to prevent (or allow) alterations of websites or domains:</span></span>

- <span data-ttu-id="0ac23-130">**Runtime_blocked_hosts**。</span><span class="sxs-lookup"><span data-stu-id="0ac23-130">**Runtime_blocked_hosts**.</span></span> <span data-ttu-id="0ac23-131">この設定は、拡張機能が変更を加えたり、指定した Web サイトからデータを読み取ったりするのをブロックします。</span><span class="sxs-lookup"><span data-stu-id="0ac23-131">This setting blocks extensions from making changes or reading data from the websites you specify.</span></span>
- <span data-ttu-id="0ac23-132">**Runtime_allowed_hosts**。</span><span class="sxs-lookup"><span data-stu-id="0ac23-132">**Runtime_allowed_hosts**.</span></span> <span data-ttu-id="0ac23-133">この設定により、拡張機能は指定した Web サイトからデータの変更または読み取りを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-133">This setting allows extensions to make changes or read data from the websites you specify.</span></span> <span data-ttu-id="0ac23-134">ポリシーの JSON 文字列でサイトを指定するには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-134">The following format is used for specifying your site(s) in the JSON string in the policy:</span></span>

  ```json
  [http|https|ftp|*]://[subdomain|*].[hostname|*].[eTLD|*] [http|https|ftp|*],
  ```

  > [!NOTE]
  > `[hostname|*], and [eTLD|*]` <span data-ttu-id="0ac23-135">セクションは必須ですが、`[subdomain|*]` セクションは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="0ac23-135">sections are required, but `[subdomain|*]` section is optional.</span></span>

<span data-ttu-id="0ac23-136">次の表に、有効なホスト パターンと一致するパターンの例を示します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-136">The following table shows examples of valid host patterns and matching patterns.</span></span>

|<span data-ttu-id="0ac23-137">有効なホスト パターン</span><span class="sxs-lookup"><span data-stu-id="0ac23-137">Valid host patterns</span></span>|<span data-ttu-id="0ac23-138">一致する</span><span class="sxs-lookup"><span data-stu-id="0ac23-138">Matches</span></span>|<span data-ttu-id="0ac23-139">一致しない</span><span class="sxs-lookup"><span data-stu-id="0ac23-139">Doesn't match</span></span>|
|--|--|--|
|  `*://*.example.*` | `http://example.com`<br>`https://test.example.co.uk`   | `https://example.microsoft.com`<br>`http://example.microsoft.co.uk`  |
| `http://example.*` | `http://example.com`<br>`http://example.ly` | `https://example.com`<br>`http://test.example.com`   |
| `http://example.com`   | `http://example.com` | `https://example.com`<br>`http://test.example.co.uk` |
| `*://*`   | <span data-ttu-id="0ac23-140">すべての URL</span><span class="sxs-lookup"><span data-stu-id="0ac23-140">All URLs</span></span>  |   |

<span data-ttu-id="0ac23-141">拡張機能による Web サイトまたはドメインへのアクセスをブロックまたは許可するガイドとして、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-141">Use the following steps as a guide to block or allow extensions to access a website or domain.</span></span>

1. <span data-ttu-id="0ac23-142">グループ ポリシー管理エディターを開き、**[管理用テンプレート] > [Microsoft Edge] > [拡張機能]** に移動し、**[拡張機能管理設定を構成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-142">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions**, and then select **Configure extension management settings**.</span></span>  
2. <span data-ttu-id="0ac23-143">ポリシーを有効にしてから、許可またはブロックするアクセス許可を入力し、アクセス許可を単一の JSON 文字列に圧縮します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-143">Enable the policy, then enter the permissions that you want allowed or blocked, compressing the permissions to a single JSON string.</span></span>

<span data-ttu-id="0ac23-144">次の例は、ホスト名の拡張機能をブロックする方法と、同じドメインの拡張機能をブロックする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0ac23-144">The following examples show how to block extensions on a hostname and how to block extensions on the same domain.</span></span>

### <a name="json-example-to-block-hostname"></a><span data-ttu-id="0ac23-145">ホスト名をブロックする JSON の例</span><span class="sxs-lookup"><span data-stu-id="0ac23-145">JSON example to block hostname</span></span>

<span data-ttu-id="0ac23-146">この例は、拡張機能が `www.microsoft.com` ホスト名にアクセスするのをブロックするための JSON と圧縮された JSON 文字列を示しています。</span><span class="sxs-lookup"><span data-stu-id="0ac23-146">This example shows the JSON and compressed JSON string to block any extension from accessing the `www.microsoft.com` hostname.</span></span>

```json
{ 
    "*":{ 
            "runtime_blocked_hosts":["www.microsoft.com"] 
    } 
} 
```

```json
{"*":{"runtime_blocked_hosts":["www.microsoft.com"]}} 
```

> [!NOTE]
> <span data-ttu-id="0ac23-147">すべての拡張機能の Web ページへのアクセスをブロックするには、前の例に示すように、拡張子 ID にアスタリスクを使用します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-147">To block all extensions from accessing a webpage, use an asterisk for the extension ID, as shown in the previous example.</span></span>  <span data-ttu-id="0ac23-148">アスタリスクの代わりに 1 つの拡張子 ID を指定した場合、ポリシーはその拡張機能にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-148">If you specify one extension ID instead of an asterisk, the policy will only apply to that extension.</span></span> <span data-ttu-id="0ac23-149">複数の拡張機能をブロックできますが、それらは別々のエントリである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ac23-149">You can block more than one extension, but they need to be separate entries.</span></span>

### <a name="json-example-to-block-extensions-on-same-domain"></a><span data-ttu-id="0ac23-150">同じドメインの拡張機能をブロックする JSON の例</span><span class="sxs-lookup"><span data-stu-id="0ac23-150">JSON example to block extensions on same domain</span></span>

<span data-ttu-id="0ac23-151">この例は、特定の拡張機能が同じドメイン "importantwebsite" で実行されるのをブロックするための JSON と圧縮された JSON 文字列を示しています。</span><span class="sxs-lookup"><span data-stu-id="0ac23-151">This example shows the JSON and compressed JSON string to block specific extensions from running on the same domain, "importantwebsite".</span></span>

```json
{ 
    "aapbdbdomjkkjkaonfhkkikfgjllcleb": { 
        "runtime_blocked_hosts": ["*://*.importantwebsite"] 
    }, 
    "bfbmjmiodbnnpllbbbfblcplfjjepjdn": { 
        "runtime_blocked_hosts": ["*://*.importantwebsite"] 
    } 
} 
```

```json
{"aapbdbdomjkkjkaonfhkkikfgjllcleb": {"runtime_blocked_hosts": ["*://,*.importantwebsite"]},"bfbmjmiodbnnpllbbbfblcplfjjepjdn": {"runtime_blocked_hosts": ["*://*.importantwebsite"]}} 
```

## <a name="allow-or-block-extensions-in-group-policy"></a><span data-ttu-id="0ac23-152">グループ ポリシーで拡張機能を許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="0ac23-152">Allow or block extensions in group policy</span></span>

<span data-ttu-id="0ac23-153">[ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist) ポリシーと [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallallowlist) ポリシーを使用して、ブロックまたは許可する拡張機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-153">You can use the [ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist) and [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallallowlist) policies to control which extensions are blocked or allowed.</span></span> <span data-ttu-id="0ac23-154">次の手順をガイドとして使用して、ブロックする拡張機能を除くすべての拡張機能を許可します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-154">Use the following steps as a guide to allow all extensions except those you want to block.</span></span>

1. <span data-ttu-id="0ac23-155">グループ ポリシー管理エディターを開き、**[管理用テンプレート] > [Microsoft Edge] > [拡張機能]** に移動し、**[インストールできない拡張機能を制御する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-155">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions >** and then select **Control which extensions cannot be installed**.</span></span>
2. <span data-ttu-id="0ac23-156">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-156">Select **Enabled**.</span></span>
3. <span data-ttu-id="0ac23-157">**[表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ac23-157">Click **Show**.</span></span>
4. <span data-ttu-id="0ac23-158">ブロックする拡張機能のアプリ ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-158">Enter the app ID of the extensions that you want to block.</span></span> <span data-ttu-id="0ac23-159">複数のアプリ ID を追加する場合は、ID ごとに個別の行を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-159">When adding multiple app ID’s use a separate row for each ID.</span></span>
5. <span data-ttu-id="0ac23-160">すべての拡張機能をブロックするには、\* _ をポリシーに入力して、拡張機能 *\** がインストールされるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="0ac23-160">To block all extensions, type \**\**_ into the policy to prevent any extensions from being installed.</span></span> <span data-ttu-id="0ac23-161">これを "特定の拡張機能のインストールを許可する" ポリシーと組み合わせて使用すると、特定の拡張機能のインストールのみを許可できます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-161">You can use this in conjunction with the "Allow specific extensions to be installed" policy to only allow certain extensions to be installed.</span></span> <span data-ttu-id="0ac23-162">次のスクリーンショットは、提供されたアプリ ID に基づいてブロックされる拡張機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="0ac23-162">The next screenshot shows an extension that will be blocked based on the app ID that's provided.</span></span>

   :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-2.png" alt-text="アプリ ID を使用して拡張機能をブロックします。":::

   > [!TIP]
   > <span data-ttu-id="0ac23-164">拡張機能のアプリ ID が見つからない場合は、Microsoft Edge アドオンの Web サイトで拡張機能を確認してください。</span><span class="sxs-lookup"><span data-stu-id="0ac23-164">If you can’t find the app ID of an extension, look at the extension in the Microsoft Edge Add-ons website.</span></span> <span data-ttu-id="0ac23-165">特定の拡張機能を見つけると、オムニボックスの URL の末尾にアプリ ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-165">Find the specific extension and you will see the app ID at the end of the URL in the omnibox.</span></span>

> [!NOTE]
> <span data-ttu-id="0ac23-166">ユーザーのコンピューターに既にインストールされているブロックリストに拡張機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-166">You can add an extension to the blocklist that’s already installed on a user’s computer.</span></span> <span data-ttu-id="0ac23-167">これにより、拡張機能が無効になり、ユーザーが再度有効にすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="0ac23-167">This will disable the extension and prevent the user from re-enabling it.</span></span> <span data-ttu-id="0ac23-168">アンインストールされず、無効になるだけです。</span><span class="sxs-lookup"><span data-stu-id="0ac23-168">It won't be uninstalled, just disabled.</span></span>

## <a name="force-install-an-extension"></a><span data-ttu-id="0ac23-169">拡張機能を強制的にインストールする</span><span class="sxs-lookup"><span data-stu-id="0ac23-169">Force-install an extension</span></span>

<span data-ttu-id="0ac23-170">[ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) ポリシーを使用して、ブロックまたは許可する拡張機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-170">Use the [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) policy to control which extensions are blocked or allowed.</span></span> <span data-ttu-id="0ac23-171">拡張機能を強制的にインストールするためのガイドとして、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-171">Use the following steps as a guide to force-install an extension.</span></span>

1. <span data-ttu-id="0ac23-172">グループ ポリシー エディターで、[_*管理*用テンプレート]> Microsoft Edge > [ >\*] に移動し、[サイレント モードでインストールされている拡張機能を制御する] を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="0ac23-172">In the Group Policy Editor, go to _*Administrative Templates> Microsoft Edge >  Extensions >*\* and then select **Control which extensions are installed silently**.</span></span>
2. <span data-ttu-id="0ac23-173">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-173">Select **Enabled**.</span></span>  
3. <span data-ttu-id="0ac23-174">**[表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ac23-174">Click **Show**.</span></span>
4. <span data-ttu-id="0ac23-175">強制的にインストールする 1 つまたは複数の拡張機能のアプリ ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-175">Enter the app ID or IDs of the extension or extensions you want to force-install.</span></span>  

<span data-ttu-id="0ac23-176">拡張機能は、ユーザーの操作を必要とせずにサイレント インストールされます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-176">The extension will be installed silently with no need for user interaction.</span></span> <span data-ttu-id="0ac23-177">ユーザーは、拡張機能をアンインストールしたり無効にしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0ac23-177">The user also won’t be able to uninstall or disable the extension.</span></span> <span data-ttu-id="0ac23-178">この設定は、有効になっているブロックリスト ポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="0ac23-178">This setting will overwrite over any blocklist policy that’s enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="0ac23-179">Chrome Web ストアでホストされている拡張機能の場合は、次のような文字列を使用します: `pckdojakecnhhplcgfflhndiffaohfah;https://clients2.google.com/service/update2/crx`。</span><span class="sxs-lookup"><span data-stu-id="0ac23-179">For extensions hosted in the Chrome web store use a string such as: `pckdojakecnhhplcgfflhndiffaohfah;https://clients2.google.com/service/update2/crx`.</span></span>

## <a name="block-extensions-from-a-specific-store-or-update-url"></a><span data-ttu-id="0ac23-180">特定のストアまたは更新 URL からの拡張機能をブロックする</span><span class="sxs-lookup"><span data-stu-id="0ac23-180">Block extensions from a specific store or update URL</span></span>

<span data-ttu-id="0ac23-181">特定のストアまたは URL からの拡張機能をブロックするには、[ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) ポリシーを使用してそのストアの *update_url* をブロックするだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-181">To block extensions from a particular store or URL, you only need to block the *update_url* for that store using the [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) policy.</span></span>

<span data-ttu-id="0ac23-182">特定のストアまたは URL からの拡張機能をブロックするガイドとして、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-182">Use the following steps as a guide to block extensions from an particular store or URL.</span></span>

1. <span data-ttu-id="0ac23-183">グループ ポリシー管理エディターを開き、**[管理用テンプレート] > [Microsoft Edge] > [拡張機能]** に移動し、**[拡張機能管理設定を構成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-183">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions >** and then select **Configure extension management settings**.</span></span>  
2. <span data-ttu-id="0ac23-184">ポリシーを有効にしてから、許可またはブロックするアクセス許可を入力し、単一の JSON 文字列に圧縮します。</span><span class="sxs-lookup"><span data-stu-id="0ac23-184">Enable the policy, then enter the permissions that you want allowed or blocked, compressing it to a single JSON string.</span></span>

<span data-ttu-id="0ac23-185">次の例は、更新 URL (`https://clients2.google.com/service/update2/crx`) を使用して Chrome Web ストアからブロックする JSON と圧縮された JSON 文字列を示しています。</span><span class="sxs-lookup"><span data-stu-id="0ac23-185">The next example shows the JSON and compressed JSON string to block from the Chrome Web Store using its update URL (`https://clients2.google.com/service/update2/crx`).</span></span>

### <a name="json-example-for-blocking-on-update-url"></a><span data-ttu-id="0ac23-186">更新 URL でブロックするための JSON の例</span><span class="sxs-lookup"><span data-stu-id="0ac23-186">JSON example for blocking on update URL</span></span>

```json
{ 
"update_url:https://clients2.google.com/service/update2/crx":{ 
                                                             " installation_mode":"blocked" 
                                                             } 
} 
```

```json
{"update_url:https://clients2.google.com/service/update2/crx":{"installation_mode":"blocked"}} 
```

> [!NOTE]
> <span data-ttu-id="0ac23-187">前の例で JSON を使用してストアがブロックされている場合でも、**ExtensionInstallForcelist** と **ExtensionInstallAllowlist** を使用して特定の拡張機能のインストールを許可または強制することができます。</span><span class="sxs-lookup"><span data-stu-id="0ac23-187">You can still use **ExtensionInstallForceList** and **ExtensionInstallAllowList** to allow/force install specific extensions even if the store is blocked using the JSON in the previous example.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ac23-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ac23-188">See also</span></span>

- [<span data-ttu-id="0ac23-189">エンタープライズの Microsoft Edge 拡張機能を管理する</span><span class="sxs-lookup"><span data-stu-id="0ac23-189">Manage Microsoft Edge extensions in the enterprise</span></span>](microsoft-edge-manage-extensions.md)
- [<span data-ttu-id="0ac23-190">Microsoft Edge 拡張機能をホストする Web ストアを作成する</span><span class="sxs-lookup"><span data-stu-id="0ac23-190">Create a web store to host Microsoft Edge extensions</span></span>](microsoft-edge-manage-extensions-webstore.md)
- [<span data-ttu-id="0ac23-191">ExtensionSettings ポリシーのリファレンス ガイド</span><span class="sxs-lookup"><span data-stu-id="0ac23-191">Reference guide for the ExtensionSettings policy</span></span>](microsoft-edge-manage-extensions-ref-guide.md)
- [<span data-ttu-id="0ac23-192">Microsoft Edge の拡張機能についてのよくある質問</span><span class="sxs-lookup"><span data-stu-id="0ac23-192">FAQ for Microsoft Edge Extensions</span></span>](microsoft-edge-manage-extensions-faq.md)
- [<span data-ttu-id="0ac23-193">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="0ac23-193">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
