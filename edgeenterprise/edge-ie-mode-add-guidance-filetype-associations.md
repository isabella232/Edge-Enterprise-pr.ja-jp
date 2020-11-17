---
title: '[プログラムから開く] コンテキスト メニューに Internet Explorer モードを追加する'
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 11/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: '[プログラムから開く] コンテキスト メニューに Internet Explorer モードを追加する'
ms.openlocfilehash: 6453cd2587e3bec10404d2491914debb999fcf3f
ms.sourcegitcommit: e3c80274a9b8ef15761c968214b3cba593476132
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "11168489"
---
# <span data-ttu-id="84a19-103">[プログラムから開く] コンテキスト メニューに Internet Explorer モードを追加する</span><span class="sxs-lookup"><span data-stu-id="84a19-103">Add Internet Explorer mode to the "Open with" context menu</span></span>

<span data-ttu-id="84a19-104">この記事では、Internet Explorer モードの Microsoft Edge とデスクトップ アプリケーションのファイル拡張子を関連付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="84a19-104">This article explains how to associate Microsoft Edge with Internet Explorer mode with file extensions for desktop applications.</span></span>

> [!NOTE]
> <span data-ttu-id="84a19-105">この記事は、Microsoft Edge バージョン 86 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="84a19-105">This article applies to Microsoft Edge version 86 or later.</span></span>

## <span data-ttu-id="84a19-106">Internet Explorer モードでのファイル拡張子の関連付けに関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="84a19-106">Guidance for file extension association with Internet Explorer mode</span></span>

<span data-ttu-id="84a19-107">次の手順は、IE モードの Microsoft Edge を .mht ファイルの種類を使用して関連付けるための基礎を示しています。</span><span class="sxs-lookup"><span data-stu-id="84a19-107">The following instructions show an entry that associates Microsoft Edge with IE mode with the .mht file type.</span></span> <span data-ttu-id="84a19-108">ファイルの関連付けを設定するためのガイドとして、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="84a19-108">Use the following steps as a guide for setting a file association.</span></span>

> [!NOTE]
> <span data-ttu-id="84a19-109">**既定の関連付け構成ファイルの設定**ポリシーを使用して、既定で Internet Explorer モードで開く特定のファイル拡張子を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="84a19-109">You can set specific file extensions to open in Internet Explorer mode by default using the policy to **Set a default associations configuration file**.</span></span> <span data-ttu-id="84a19-110">詳細については、「[ポリシー CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84a19-110">For more information, see [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration).</span></span>

1. <span data-ttu-id="84a19-111">新しい ProgID を Internet Explorer モードで開くために使用する Microsoft Edge チャネルで定義します。</span><span class="sxs-lookup"><span data-stu-id="84a19-111">Define a new ProgID with the Microsoft Edge channel to use to open with Internet Explorer mode.</span></span> <span data-ttu-id="84a19-112">ProgID には、アプリケーション名、アイコン、msedge.exe の完全なパスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="84a19-112">The ProgID includes the application name and Icon and the full path to msedge.exe.</span></span>

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

2. <span data-ttu-id="84a19-113">IE モードで開くために必要なコマンド ラインを渡すために、シェルの更新プログラムを構成します。</span><span class="sxs-lookup"><span data-stu-id="84a19-113">Configure shell updates to pass the command line needed to open with IE mode.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""
```

3. <span data-ttu-id="84a19-114">最後に、.mht ファイル拡張子を新しい ProgID に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="84a19-114">Finally, associate the .mht file extension with a new ProgID.</span></span> <span data-ttu-id="84a19-115">値の名前として ProgID を追加し、値の種類を REG_SZ にします。</span><span class="sxs-lookup"><span data-stu-id="84a19-115">Add your ProgID as a value name, with the value type of REG_SZ.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):
```

<span data-ttu-id="84a19-116">前の例で説明したキーを設定すると、IE モードの Microsoft Edge\<channel\> を使用して .mht ファイルを開くための追加オプションがユーザーに対して **[プログラムから開く]** メニューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="84a19-116">After you set the keys described in the previous example, your users will see an additional option on the **Open with** menu to open an .mht file using Microsoft Edge \<channel\> with IE mode.</span></span>

## <span data-ttu-id="84a19-117">レジストリの例</span><span class="sxs-lookup"><span data-stu-id="84a19-117">Registry Example</span></span>

<span data-ttu-id="84a19-118">次のコード スニペットを .reg ファイルとして保存すれば、これをレジストリにインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="84a19-118">You can save the following code snippet as a .reg file and import it into the registry.</span></span>

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

## <span data-ttu-id="84a19-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="84a19-119">See also</span></span>

- [<span data-ttu-id="84a19-120">IE モードの概要</span><span class="sxs-lookup"><span data-stu-id="84a19-120">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="84a19-121">構成可能なサイトの情報</span><span class="sxs-lookup"><span data-stu-id="84a19-121">Configurable sites information</span></span>](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)
- [<span data-ttu-id="84a19-122">その他のエンタープライズ モード情報</span><span class="sxs-lookup"><span data-stu-id="84a19-122">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="84a19-123">ファイルの種類の関連付けの設定</span><span class="sxs-lookup"><span data-stu-id="84a19-123">Setting file type associations</span></span>](https://docs.microsoft.com/windows/win32/shell/fa-file-types)
- [<span data-ttu-id="84a19-124">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="84a19-124">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
