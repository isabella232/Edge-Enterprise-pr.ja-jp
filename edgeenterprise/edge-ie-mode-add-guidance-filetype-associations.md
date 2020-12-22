---
title: ファイル拡張子と Internet Explorer モードの関連付け
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 12/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: ファイル拡張子と Internet Explorer モードの関連付け
ms.openlocfilehash: 9f39a3319c3e45001090dd9f0cffb3e7ce2648fb
ms.sourcegitcommit: 306582403d4272831bcac390154c7cc7041a9b7e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2020
ms.locfileid: "11238194"
---
# ファイル拡張子と Internet Explorer モードの関連付け

この記事では、Internet Explorer モードの Microsoft Edge とデスクトップ アプリケーションのファイル拡張子を関連付ける方法について説明します。

> [!NOTE]
> この記事は、Microsoft Edge バージョン 86 以降に適用されます。

## Internet Explorer モードでのファイル拡張子の関連付けに関するガイダンス

次の手順は、IE モードの Microsoft Edge を .mht ファイルの種類を使用して関連付けるための基礎を示しています。 ファイルの関連付けを設定するためのガイドとして、次の手順を使用します。

> [!NOTE]
> **既定の関連付け構成ファイルの設定**ポリシーを使用して、既定で Internet Explorer モードで開く特定のファイル拡張子を設定することができます。 詳細については、「[ポリシー CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)」を参照してください。

1. 新しい ProgID を Internet Explorer モードで開くために使用する Microsoft Edge チャネルで定義します。 ProgID には、アプリケーション名、アイコン、msedge.exe の完全なパスが含まれています。

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

2. IE モードで開くために必要なコマンド ラインを渡すために、シェルの更新プログラムを構成します。

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""
```

3. 最後に、.mht ファイル拡張子を新しい ProgID に関連付けます。 値の名前として ProgID を追加し、値の種類を REG_SZ にします。

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):
```

前の例で説明したキーを設定すると、IE モードの Microsoft Edge\<channel\> を使用して .mht ファイルを開くための追加オプションがユーザーに対して **[プログラムから開く]** メニューに表示されます。

## レジストリの例

次のコード スニペットを .reg ファイルとして保存すれば、これをレジストリにインポートすることができます。

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
## Internet Explorer モードで開くようにファイルの種類を構成する

Edge 88 以降、[[コンテキスト メニューを表示]](https://docs.microsoft.com/deployedge/microsoft-edge-policies#show-context-menu-to-open-a-link-in-internet-explorer-mode) ポリシーを使用して Internet Explorer モードで開くように特定のファイル タイプのリンクを構成し、Internet Explorer モードでリンクを開くことができます。 

このポリシー「[Internet Explorer モードのローカル ファイルのファイル拡張子許可リストを開く](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalfileextensionallowlist)」でファイル拡張子を指定することにより、このオプションを適用するファイル タイプを定義できます。 

## 関連項目

- [IE モードの概要](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [構成可能なサイトの情報](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)
- [その他のエンタープライズ モード情報](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [ファイルの種類の関連付けの設定](https://docs.microsoft.com/windows/win32/shell/fa-file-types)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
