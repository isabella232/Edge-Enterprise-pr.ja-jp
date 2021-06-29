---
title: ファイル拡張子と Internet Explorer モードの関連付け
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 05/19/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: ファイル拡張子と Internet Explorer モードの関連付け
ms.openlocfilehash: c027b11e426cd665cb9e6cc25b4c9f66a0c6762a
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617457"
---
# <a name="associate-file-extensions-with-internet-explorer-mode"></a><span data-ttu-id="75ead-103">ファイル拡張子と Internet Explorer モードの関連付け</span><span class="sxs-lookup"><span data-stu-id="75ead-103">Associate file extensions with Internet Explorer mode</span></span>

>[!Note]
> <span data-ttu-id="75ead-104">Internet Explorer 11 デスクトップ アプリケーションは廃止され、2022 年 6 月 15 日にサポートが終了します (スコープ内の一覧については、[FAQ を参照してください](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549))。</span><span class="sxs-lookup"><span data-stu-id="75ead-104">The Internet Explorer 11 desktop application will be retired and go out of support on June 15, 2022 (for a list of what’s in scope, [see the FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span></span> <span data-ttu-id="75ead-105">現在使用しているものと同じ IE11 アプリとサイトを、Internet Explorer モードの Microsoft Edge で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="75ead-105">The same IE11 apps and sites you use today can open in Microsoft Edge with Internet Explorer mode.</span></span> <span data-ttu-id="75ead-106">[こちらをご覧ください](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。</span><span class="sxs-lookup"><span data-stu-id="75ead-106">[Learn more here](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span></span>

<span data-ttu-id="75ead-107">この記事では、Internet Explorer モードの Microsoft Edge とデスクトップ アプリケーションのファイル拡張子を関連付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="75ead-107">This article explains how to associate Microsoft Edge with Internet Explorer mode with file extensions for desktop applications.</span></span>

> [!NOTE]
> <span data-ttu-id="75ead-108">この記事は、Microsoft Edge バージョン 86 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="75ead-108">This article applies to Microsoft Edge version 86 or later.</span></span>

## <a name="guidance-for-file-extension-association-with-internet-explorer-mode"></a><span data-ttu-id="75ead-109">Internet Explorer モードでのファイル拡張子の関連付けに関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="75ead-109">Guidance for file extension association with Internet Explorer mode</span></span>

<span data-ttu-id="75ead-110">次の手順は、IE モードの Microsoft Edge を .mht ファイルの種類を使用して関連付けるための基礎を示しています。</span><span class="sxs-lookup"><span data-stu-id="75ead-110">The following instructions show an entry that associates Microsoft Edge with IE mode with the .mht file type.</span></span> <span data-ttu-id="75ead-111">ファイルの関連付けを設定するためのガイドとして、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="75ead-111">Use the following steps as a guide for setting a file association.</span></span>

> [!NOTE]
> <span data-ttu-id="75ead-112">**既定の関連付け構成ファイルの設定**ポリシーを使用して、既定で Internet Explorer モードで開く特定のファイル拡張子を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="75ead-112">You can set specific file extensions to open in Internet Explorer mode by default using the policy to **Set a default associations configuration file**.</span></span> <span data-ttu-id="75ead-113">詳細については、「[ポリシー CSP - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75ead-113">For more information, see [Policy CSP - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration).</span></span>

1. <span data-ttu-id="75ead-114">新しい ProgID を Internet Explorer モードで開くために使用する Microsoft Edge チャネルで定義します。</span><span class="sxs-lookup"><span data-stu-id="75ead-114">Define a new ProgID with the Microsoft Edge channel to use to open with Internet Explorer mode.</span></span> <span data-ttu-id="75ead-115">ProgID には、アプリケーション名、アイコン、msedge.exe の完全なパスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="75ead-115">The ProgID includes the application name and Icon and the full path to msedge.exe.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\Application]
"ApplicationCompany"="Microsoft Corporation"
"ApplicationName"="Microsoft Edge with IE Mode"
"ApplicationIcon"="C:\\<edge_installation_dir>\\msedge.exe,4"
"AppUserModelId"=""
```

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\DefaultIcon]
@="C:\\<edge_installation_dir>\\msedge.exe,4"
```

2. <span data-ttu-id="75ead-116">IE モードで開くために必要なコマンド ラインを渡すために、シェルの更新プログラムを構成します。</span><span class="sxs-lookup"><span data-stu-id="75ead-116">Configure shell updates to pass the command line needed to open with IE mode.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""
```

3. <span data-ttu-id="75ead-117">最後に、.mht ファイル拡張子を新しい ProgID に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="75ead-117">Finally, associate the .mht file extension with a new ProgID.</span></span> <span data-ttu-id="75ead-118">値の名前として ProgID を追加し、値の種類を REG_SZ にします。</span><span class="sxs-lookup"><span data-stu-id="75ead-118">Add your ProgID as a value name, with the value type of REG_SZ.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):
```

<span data-ttu-id="75ead-119">前の例で説明したキーを設定すると、IE モードの Microsoft Edge\<channel\> を使用して .mht ファイルを開くための追加オプションがユーザーに対して **[プログラムから開く]** メニューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="75ead-119">After you set the keys described in the previous example, your users will see an additional option on the **Open with** menu to open an .mht file using Microsoft Edge \<channel\> with IE mode.</span></span>

## <a name="registry-example"></a><span data-ttu-id="75ead-120">レジストリの例</span><span class="sxs-lookup"><span data-stu-id="75ead-120">Registry Example</span></span>

<span data-ttu-id="75ead-121">次のコード スニペットを .reg ファイルとして保存すれば、これをレジストリにインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="75ead-121">You can save the following code snippet as a .reg file and import it into the registry.</span></span>

```markdown
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT]

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\Application]
"ApplicationCompany"="Microsoft Corporation"
"ApplicationName"="Microsoft Edge with IE Mode"
"ApplicationIcon"="C:\\<edge_installation_dir>\\msedge.exe,4"
"AppUserModelId"=""

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\DefaultIcon]
@="C:\\<edge_installation_dir>\\msedge.exe,4"

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell]

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open]

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""

```

## <a name="configuring-file-types-to-open-in-internet-explorer-mode"></a><span data-ttu-id="75ead-122">Internet Explorer モードで開くようにファイルの種類を構成する</span><span class="sxs-lookup"><span data-stu-id="75ead-122">Configuring file types to open in Internet Explorer mode</span></span>

<span data-ttu-id="75ead-123">Edge 88 以降、[[コンテキスト メニューを表示]](./microsoft-edge-policies.md#internetexplorerintegrationreloadiniemodeallowed) ポリシーを使用して Internet Explorer モードで開くように特定のファイル タイプのリンクを構成し、Internet Explorer モードでリンクを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="75ead-123">Starting Edge 88, you can configure specific file type links to open in Internet Explorer mode using the policy [Show context menu to open links in Internet Explorer mode](./microsoft-edge-policies.md#internetexplorerintegrationreloadiniemodeallowed).</span></span>

<span data-ttu-id="75ead-124">このポリシー「[Internet Explorer モードのローカル ファイルのファイル拡張子許可リストを開く](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist)」でファイル拡張子を指定することにより、このオプションを適用するファイル タイプを定義できます。</span><span class="sxs-lookup"><span data-stu-id="75ead-124">You can define file types this option should apply to, by specifying file extensions in this policy [Open local files in Internet Explorer mode file extension allow list](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist).</span></span> 

## <a name="see-also"></a><span data-ttu-id="75ead-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="75ead-125">See also</span></span>

- [<span data-ttu-id="75ead-126">IE モードの概要</span><span class="sxs-lookup"><span data-stu-id="75ead-126">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="75ead-127">構成可能なサイトの情報</span><span class="sxs-lookup"><span data-stu-id="75ead-127">Configurable sites information</span></span>](./edge-learnmore-configurable-sites-ie-mode.md)
- [<span data-ttu-id="75ead-128">その他のエンタープライズ モード情報</span><span class="sxs-lookup"><span data-stu-id="75ead-128">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="75ead-129">ファイルの種類の関連付けの設定</span><span class="sxs-lookup"><span data-stu-id="75ead-129">Setting file type associations</span></span>](/windows/win32/shell/fa-file-types)
- [<span data-ttu-id="75ead-130">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="75ead-130">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)