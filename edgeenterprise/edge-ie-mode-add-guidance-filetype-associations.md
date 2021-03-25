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
ms.openlocfilehash: 6c651499401757d9a58e697d1d019a7294bb5fa7
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447371"
---
# <a name="associate-file-extensions-with-internet-explorer-mode"></a>ファイル拡張子と Internet Explorer モードの関連付け

この記事では、Internet Explorer モードの Microsoft Edge とデスクトップ アプリケーションのファイル拡張子を関連付ける方法について説明します。

> [!NOTE]
> この記事は、Microsoft Edge バージョン 86 以降に適用されます。

## <a name="guidance-for-file-extension-association-with-internet-explorer-mode"></a>Internet Explorer モードでのファイル拡張子の関連付けに関するガイダンス

次の手順は、IE モードの Microsoft Edge を .mht ファイルの種類を使用して関連付けるための基礎を示しています。 ファイルの関連付けを設定するためのガイドとして、次の手順を使用します。

> [!NOTE]
> **既定の関連付け構成ファイルの設定**ポリシーを使用して、既定で Internet Explorer モードで開く特定のファイル拡張子を設定することができます。 詳細については、「[ポリシー CSP - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)」を参照してください。

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

## <a name="registry-example"></a>レジストリの例

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
## <a name="configuring-file-types-to-open-in-internet-explorer-mode"></a>Internet Explorer モードで開くようにファイルの種類を構成する

Edge 88 以降、[[コンテキスト メニューを表示]](./microsoft-edge-policies.md#show-context-menu-to-open-a-link-in-internet-explorer-mode) ポリシーを使用して Internet Explorer モードで開くように特定のファイル タイプのリンクを構成し、Internet Explorer モードでリンクを開くことができます。 

このポリシー「[Internet Explorer モードのローカル ファイルのファイル拡張子許可リストを開く](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist)」でファイル拡張子を指定することにより、このオプションを適用するファイル タイプを定義できます。 

## <a name="see-also"></a>関連項目

- [IE モードの概要](./edge-ie-mode.md)
- [構成可能なサイトの情報](./edge-learnmore-configurable-sites-ie-mode.md)
- [その他のエンタープライズ モード情報](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [ファイルの種類の関連付けの設定](/windows/win32/shell/fa-file-types)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)