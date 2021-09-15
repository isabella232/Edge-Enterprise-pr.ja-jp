---
title: ユーザー環境内の Microsoft Edge
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: ユーザー環境内の Microsoft Edge
ms.openlocfilehash: 2381380cb399f6a1fbb5efa9378ffeba20fa774f
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979663"
---
# <a name="microsoft-edge-in-your-environment"></a>ユーザー環境内の Microsoft Edge

この記事では、Microsoft Edge レガシがサービスを終了したときに Microsoft Edge を展開する準備をする方法について説明します。

Microsoft Edge 製品チームの[ブログ投稿](https://aka.ms/EdgeLegacyEOS)に示す通り、Microsoft Edge レガシ デスクトップ アプリケーションのサポートは 2021 年 3 月 9 日に終了します。 4 月に Update Tuesday (または "B") リリースを適用すると、Windows 10 RS4 ~ 20H1 を実行しているデバイスから Microsoft Edge レガシが削除され、Microsoft Edge に置き換えられます。

## <a name="how-to-prepare"></a>準備する方法

Microsoft Edge が 4 月の Update Tuesday リリースで Windows 10 RS4 ~ 20H1 デバイスにインストールされる準備を行う場合は、「[Microsoft Edgeの展開を計画する](deploy-edge-plan-deployment.md)」を参照することをお勧めします。

展開を計画した後、次のいずれかの方法を使用して Microsoft Edge の展開を準備します。

- **グループ ポリシーをインストールして、Microsoft Edge の更新方法をカスタマイズします**。 詳しくは、「[Windows での Microsoft Edge ポリシー設定の構成](configure-microsoft-edge.md)」をご覧ください。また、[更新ポリシー リファレンス](microsoft-edge-update-policies.md)資料 に特に注意してください。 4 月の Update Tuesday リリースをインストールする前に、更新を管理するためにグループ ポリシーをインストールすると、Microsoft Edge はtadatini ポリシーの順守を開始します。 インストールされているグループ ポリシーがインストールされていない場合、Microsoft Edge は自動的に更新されます。

- **2021年 3 月 9 日のサービス終了日より前に Microsoft Edge レガシ デスクトップ アプリケーションを削除し、Microsoft Edge を展開します**。 Windows 10 RS4 ~ 20H1 の場合は、Windows 更新プログラムを使用して展開できます。 詳しくは、「[Windows 10 更新プログラムを適用した Microsoft Edge の展開](deploy-edge-with-windows-10-updates.md)」をご覧ください。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge の展開を計画する](deploy-edge-plan-deployment.md)