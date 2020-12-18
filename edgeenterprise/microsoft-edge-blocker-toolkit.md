---
title: Microsoft Edge の自動配布を無効にするための Blocker Toolkit
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 12/16/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge の自動配布を無効にするための Blocker Toolkit
ms.openlocfilehash: 9fb97d2dfec4822f8ce76dc3e37b85118c6572ad
ms.sourcegitcommit: 606282995b466a968bab40c16005a6653323c763
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "11229618"
---
# Microsoft Edge (Chromium ベース) の自動配布を無効にするための Blocker Toolkit

この記事では、Microsoft Edge の自動配布とインストールを無効にするための Blocker Toolkit について説明します。

この記事では、次の更新が行われました。

- **2020 年 1 月 9 日** Blocker Toolkit の使用が必要になる可能性のあるデバイスに関する詳細情報
- **2020 年 2 月 28 日** この自動更新から除外するデバイスの基準から「MDM 管理対象」を削除しました
- **2020 年 6 月 30** Windows Update に接続されているすべてのデバイスがこの更新プログラムを受信する範囲内にあることを反映しました（2020 年 7 月 30 日までに有効になります）
- **2020 年 12 月 10** Blocker Toolkit の設定が無視される 20H2 以前の状況を説明しました

> [!NOTE]
> この記事は、Microsoft Edge Stable チャネルに適用されます。

## 概要

お客様のセキュリティを強化し、最新の状態に保つために、Microsoft ではWindows 10 バージョン 1803 以降を実行しているすべての Windows Update で接続されたデバイスに Microsoft Edge (Chromium ベース) を配布します。 このプロセスは、2020 年 1 月 15 日以降に開始され、詳しい情報は当日提供されます。

Blocker Toolkit は、Windows 10 バージョン 1803 以降を実行している Windows Update で接続されたデバイスへの Microsoft Edge (Chromium ベース) の自動配信をブロックする組織を対象としています。 Windows Server Update Services (WSUS) または Windows Update for Business (WUfB) が管理されているデバイスは、この自動 Windows Update から除外されますが、所属している組織を通じて新しい Microsoft Edge (Chromium ベース) を受け取る場合があります。

**次の点に注意してください。**

- Blocker Toolkit を有効にしても、ユーザーはインターネットのダウンロードまたは外部メディアから Microsoft Edge (Chromium ベース) を手動でインストールすることができます。
- Windows Update for Business (WUfB) を通じて更新プログラムが管理されている組織では、この更新プログラムを自動的に受信することはありません。また、Blocker Toolkit を展開する必要はありません。
- 組織の環境が Windows Server Update Services (WSUS) や System Center Configuration Manager (SCCM) などの更新管理ソリューションで管理されている場合、Blocker Toolkit を展開する必要はありません。 これらの製品を使用して、環境内で Windows Update と Microsoft Update を通じてリリースされた更新プログラム (新しい Microsoft Edge の [WSUS](https://support.microsoft.com/help/4584642/update-in-wsus-for-the-new-microsoft-edge)の更新プログラムを含む) の展開を完全に管理できます。
- この更新プログラムは、エンタープライズ ユーザーがこの更新プログラムの展開を柔軟かつ最大限に制御できるように、スタンドアロンの更新プログラムとして提供されます (月例の累積的な更新プログラムの一部ではありません)。
- 新しい Microsoft Edge (Chromium ベース) は、2020 年後半に Windows 10 バージョン 20H2 の機能更新プログラムの一部として含まれています。 Blocker Toolkit は、20H2 の動作や展開に影響を与えません。 Windows 10 バージョン 20H2 の詳細については、[こちら](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/)を参照してください。

Blocker Toolkit の実行可能ファイルは、[https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe) からダウンロードできます。

### Toolkit のコンポーネント

この Toolkit には、次のコンポーネントが含まれています。

- 実行可能な Blocker スクリプト (.CMD)
- グループ ポリシー管理用テンプレート (.ADMX および .ADML)

### サポートされるオペレーティング システム

Windows 10 Version 1803 以降。

## Blocker スクリプト

このスクリプトは、レジストリキーを作成し、関連する値を設定することにより、ローカル コンピューターまたはリモート ターゲット コンピューターで、Microsoft Edge (Chromium ベース) の自動配信を (使用するコマンド ライン オプションに応じて) ブロックまたはブロック解除します。

**レジストリ キー:** `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate`<br>
**キーの値の名前:** `DoNotUpdateToEdgeWithChromium`

| 値                | 結果                         |
|----------------------|--------------------------------|
| *キーが定義されていない* | 配布はブロック*されません*。 |
| 0                    | 配布はブロック*されません*。 |
| 1                    | 配布はブロックされます。       |

このスクリプトのコマンド ライン構文は次のとおりです。<br>
`EdgeChromium_Blocker.cmd [<machine name>] [/B] [/U] [/H]`

### コンピューター名

`<machine name>` パラメーターはオプションです。 指定しない場合、アクションはローカル コンピューターで実行されます。 それ以外の場合は、`REG` コマンドのリモート レジストリ機能を通じてリモート コンピューターにアクセスします。 セキュリティのアクセス許可が原因でリモート レジストリにアクセスできない場合、またはリモート コンピューターが見つからない場合は、`REG` コマンドからエラー メッセージが返されます。

### スイッチ

スクリプトで使用されるスイッチは相互に排他的であり、特定のコマンドからの最初の有効なスイッチのみが処理されます。 同じコンピューターでスクリプトを複数回実行することができます。

| スイッチ       | 説明                              |
|--------------|------------------------------------------|
| `/B`         | 配布をブロックします。                      |
| `/U`         | 配布をブロック解除します。                    |
| `/H` または `/?` | 次の概要ヘルプを表示します。<br>`This tool can be used to remotely block or unblock the delivery of Microsoft Edge (Chromium-based) through Automatic Updates.`<br> `Usage:`<br>`EdgeChromium_Blocker.cmd [<machine name>] [/B][/U][/H]`<br>`B = Block Microsoft Edge (Chromium-based) deployment`<br>`U = Allow Microsoft Edge (Chromium-based) deployment`<br>`H = Help`<br>`Examples:`<br>`EdgeChromium_Blocker.cmd mymachine /B (blocks delivery on machine "mymachine")`<br>`EdgeChromium_Blocker.cmd /U (unblocks delivery on the local machine)`<br> |

## グループ ポリシー管理用テンプレート (.ADMX および .ADML ファイル)

管理者は、グループ ポリシー管理用テンプレート (.ADMX および .ADML ファイル) を使用することによって、新しいグループ ポリシー設定をインポートして、グループ ポリシー環境への Microsoft Edge (Chromium ベース) の自動配布をブロックまたはブロック解除することができます。また、グループ ポリシーを使用して、環境内のシステム全体に一元的にアクションを実行できます。

ユーザーが Windows 10 RS3 Enterprise/EDU および RS4 以降を実行している場合、このポリシーは次のパスに表示されます。

```
/Computer Configuration  
  /Administrative Templates
    /Classic Administrative Templates
      /Windows Components
        /Windows Update  
          /Microsoft Edge (Chromium-based) Blockers  
```

この設定は、コンピューターの設定としてのみ使用できます。ユーザーごとの設定はありません。

> [!IMPORTANT]
> このレジストリ設定は、ポリシー キーに格納されていないため、*優先設定*と見なされます。 したがって、設定を実装するグループ ポリシーオブジェクトが削除された場合や、ポリシーが **[未構成]** に設定されている場合、設定はそのまま残ります。 グループ ポリシーを使用して Microsoft Edge (Chromium ベース) の配布をブロック解除するには、ポリシーを **[無効]** に設定します。

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://www.microsoftedgeinsider.com/enterprise)
- [Microsoft Edge をサポートする Windows 更新プログラム](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)
- [旧バージョンの Microsoft Edge にアクセスする方法](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-access-old-edge)
