---
title: Microsoft Edge Stable チャネル更新プログラムのプログレッシブ ロールアウト
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Stable チャネル更新プログラムのプログレッシブ ロールアウト
ms.openlocfilehash: d11fd825c7f4de37fe0b6555f503d9a496fb2b427a9645489a165c91490ff5d7
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "11724860"
---
# <a name="progressive-rollouts-for-microsoft-edge-stable-channel-updates"></a>Microsoft Edge Stable チャネル更新プログラムのプログレッシブ ロールアウト

Microsoft Edge 83 リリース以降、Microsoft Edge Stable チャネルへのメジャーアップデートのプログレッシブ ロールアウトを数日間にわたって実行します。 このプログレッシブ ロールアウトにより、アップグレードを監視し、組織全体でブラウザーを安全に更新できます。

> [!NOTE]
> これは、Microsoft Edge Stable チャネルバージョン 83 以降に適用されます。

## <a name="why-do-we-need-progressive-rollout"></a>なぜプログレッシブ ロールアウトが必要なのですか。

更新プログラムの状態を注意深く監視し、数日間にわたって更新プログラムを展開することにより、新しい更新プログラムで発生する可能性がある問題の影響を抑えることができます。 Microsoft Edgeリリース83では、Windows 7、Windows 8 と 8.1、および Windows 10 バージョンのすべての Microsoft Edge でプログレッシブロールアウトが有効になります。 準備ができ次第、Mac 上の Microsoft Edge もサポートします。

## <a name="how-will-the-updates-work"></a>更新プログラムはどのように機能しますか。

Microsoft Edge の各インストールには、アップグレード値が割り当てられます。 段階的なロールアウトを開始すると、デバイスの値がアップグレード値の範囲内にある場合は、更新プログラムが表示されます。 ロールアウトが (数日以内に) 進行して、最終的にすべてのユーザーが更新を取得します。 重要なセキュリティ修正が含まれているブラウザの更新は、重要なセキュリティ修正が含まれていない更新よりも展開の頻度が高くなります。 これは、脆弱性からの保護を迅速にするために行われます。

## <a name="how-does-this-affect-enterprises"></a>これは企業にどのように影響しますか。

Microsoft Edge アーティファクト は、Microsoft Intune、Windows Server Update Service (WSUS)、Configuration Manager などの複数のメカニズムを使用して企業に配布されます。 これらの展開ツールは、プログレッシブロールアウトによって動作が異なります。

- Microsoft Intune を介して配布を管理する企業は、自動更新に登録されています。 プログレッシブロールアウトが使用され、すべてのユーザーに数日で更新が表示されます。
- WSUS (Windows Server Update Services) または構成マネージャーを介して配布を管理する企業は、自動更新に登録されていません。 管理者は、最初から利用可能なアップデートを管理し、適用します。 プログレッシブロールアウトはこのプロセスには影響しません。

懸念や質問がある場合は、ユーザーの声、アプリケーション内のフィードバックボタン、またはコメントの下部を利用して、貴重なフィードバックを共有してください。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
