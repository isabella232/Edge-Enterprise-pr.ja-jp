---
title: Microsoft Edge キオスク モード
ms.author: brianalt
author: brianalt
manager: seanlynd
ms.date: 01/16/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge キオスク モード
ms.openlocfilehash: 7a690820752b5361349bf394055a737bd8175215
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980520"
---
# Microsoft Edge キオスク モード

この記事では、Microsoft Edge (version 77 以降) のキオスク モード オプションの概要を説明します。 また Microsoft Edge レガシのキオスク モード (version 45 以前) を使用するための要件についても説明します。

Microsoft Edge レガシのキオスク モード (version 45 以前) については、「[Microsoft Edge キオスク モードの展開](https://aka.ms/edgekioskmode)」をご覧ください。

## 割り当てられたアクセスによる Microsoft Edge の使用

Microsoft Edge は、Windows 10 で[複数アプリの割り当てられたアクセス](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)によって実行できます。これは Microsoft Edge レガシでの "通常の閲覧" タイプのキオスク モードに相当します。 複数アプリの割り当てられたアクセスで Microsoft Edge を構成するには、[複数アプリ キオスクの設定](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)方法の手順に従います。 Microsoft Edge Stable チャネルの AUMID は **MSEdge** です。

複数アプリの割り当てられたアクセスで Microsoft Edge を使用する場合は、[Microsoft Edge ブラウザーポリシー](microsoft-edge-policies.md)を使用して、固有の要件を満たすことができるように閲覧エクスペリエンスを構成できます。

現在 Microsoft Edge では、シングル アプリの割り当てられたアクセス用の同じ Microsoft Edge レガシ キオスク モード タイプや、複数アプリの割り当てられたアクセスでの "公共閲覧" キオスク モード タイプがサポートされていません。 シングル アプリの割り当てられたアクセスのキオスク デバイス用にブラウザーが必要であれば、[Microsoft Edge レガシ キオスク モード](https://aka.ms/edgekioskmode)または [Microsoft キオスク ブラウザー アプリ](https://www.microsoft.com/p/kiosk-browser/9ngb5s5xg2kp?activetab=pivot:overviewtab)の使用をお勧めします。 

## Microsoft Edge "--kiosk" コマンド ライン パラメーター

"`--kiosk`" コマンド ライン パラメーターを使用すると、キオスク モードで Microsoft Edge を起動できます。 このとき、ブラウザーが全画面で開き、全画面のキーボード ショートカット (F11) が無効になります。 これを行うには、ターゲットを次のように設定してショートカットを作成します。<br>
*`"<local path>\msedge.exe" --kiosk http://bing.com`*

> [!NOTE]
> "`--kiosk`" パラメーターを指定しても、ユーザーによる Windows キーボード ショートカットへのアクセスは無効にならず、他のアプリケーションの実行も回避できません。 このような種類の制御を実現するには、[AppLocker の使用による Windows 10 キオスクの作成](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-applocker)や[キーボード フィルターの使用](https://docs.microsoft.com/windows-hardware/customize/enterprise/keyboardfilter)を検討してください。

キオスク モードを終了してブラウザーを閉じるには、Alt キーを押しながら F4 キーを押します。

## Microsoft Edge レガシ キオスク モードのサポート

新しいバージョンの Microsoft Edge Stable チャネルがインストールされると、Microsoft Edge レガシが非表示になり Microsoft Edge レガシを起動しようとすると、新しいバージョンにリダイレクトされます。 以下の情報も参照してください。

- Windows 更新プログラムの要件については、「[次のバージョンの Microsoft Edge をサポートする Windows 更新プログラム](microsoft-edge-sysupdate-windows-updates.md)」をご覧ください。 
- Microsoft Edge のインストール後に Microsoft Edge レガシにアクセスする方法については、「[Microsoft Edge の新しいバージョンをインストールした後 Microsoft Edge レガシにアクセスする](microsoft-edge-sysupdate-access-old-edge.md)」をご覧ください。
 
キオスク デバイスで Microsoft Edge レガシ キオスク モードを引き続き使用するには、次のいずれかの操作を実行します。 

- Microsoft Edge Stable チャネルをインストールする場合や、インストールを許可する場合、またはキオスク デバイスに既にインストールされている場合は、Microsoft Edge の [[Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する]](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs) ポリシーを展開します。
- キオスク デバイスへの Microsoft Edge Stable チャネルのインストールを回避するには、Stable チャネルに Microsoft Edge の [[インストールの既定の動作を許可する]](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allow-installation-default) ポリシーを展開するか、[Blocker Toolkit を使用して Microsoft Edge の自動配布を無効にする](microsoft-edge-blocker-toolkit.md)ことを検討します。 

## 関連項目

- [Windows デスクトップ エディションでのキオスクおよびデジタル サイネージの構成](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [Microsoft Edge レガシ キオスク モードの展開](https://aka.ms/edgekioskmode) 
- [Microsoft Edge の展開を計画する](deploy-edge-plan-deployment.md)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
