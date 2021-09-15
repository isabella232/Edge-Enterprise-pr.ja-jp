---
title: Microsoft Edge リリース スケジュール
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 08/24/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge リリース スケジュール
ms.openlocfilehash: 8a9438b8031f0f850ca284aeca61f90dfd8fa7a9
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980467"
---
# <a name="microsoft-edge-release-schedule"></a>Microsoft Edge リリース スケジュール

この記事では、Microsoft Edge のリリース サイクルおよびリリース スケジュールについて説明します。

## <a name="release-cadence"></a>リリース サイクル

Microsoft では、Microsoft Edge を新しい機能で更新する頻度を管理するために、チャネルと呼ばれる 4 つのオプションを提供しています。 Microsoft Edge チームは、更新プログラムを 6 週間ごとに、ベータ版および安定版のチャネルに公開する予定です。 チャネルとそのリリース サイクル、サポート レベルの詳細については、「[チャネルの概要](./microsoft-edge-channels.md#channel-overview)」をご参照ください。

> [!NOTE]
> 安定したチャネル バージョン 94 から、Microsoft Edge は 4 週間のメジャー リリース サイクルに移行します。 ただし、複雑な環境を管理する企業のお客様は、Microsoft Edge の更新プログラムの計画とテストにより多くの時間が必要なことを認識しています。 更新プログラムを管理するためにタイムラインを延長する必要がある企業のお客様を支援するために、Microsoft Edge では、より長い 8 週間のメジャー リリース サイクルに合わせた **拡張安定オプション**をご提供いたします。このオプションは、管理された環境をご利用のお客様のみご利用いただけます。 [お知らせのブログ投稿を参照してください](https://blogs.windows.com/msedgedev/2021/07/15/opt-in-extended-stable-release-cycle/)

## <a name="release-schedule"></a>リリース スケジュール

次の表に、ベータ版と Stable チャネルのリリース日を示します。

> [!NOTE]
> リリース日は概算で、ビルドの状態によって異なります。

### <a name="microsoft-edge-releases"></a>Microsoft Edge リリース

次の表は、両方のチャネルのメジャー リリースのみを追跡し、情報を提供します。

| バージョン | リリース状態 | Beta チャネル<br>リリースされる週 | Stable チャネル<br>リリースされる週 |
|---------|-----|------|--------|
| 88 | リリース日<br>バージョン | 2020 年 12 月 9 日<br>[88.0.705.18](/deployedge/microsoft-edge-relnote-archive-beta-channel#version-88070518-december-9) | 2021 年 1 月 21 日<br>[88.0.705.50](/deployedge/microsoft-edge-relnote-archive-stable-channel#version-88070550-january-21)|
| 89 | リリース日<br>バージョン | 2021 年 2 月 3 日<br>[89.0.774.18](/deployedge/microsoft-edge-relnote-beta-channel#version-89077423-february-8) | 2021 年 3 月 4 日<br>[89.0.774.45](/deployedge/microsoft-edge-relnote-stable-channel#version-89077445-march-4) |
| 90 | リリース日<br>バージョン | 16-Mar-2021<br>[90.0.818.8](/deployedge/microsoft-edge-relnote-beta-channel#version-9008188-march-16) | 15-Apr-2021<BR>[90.0.818.39](/deployedge/microsoft-edge-relnote-stable-channel#version-90081839-april-15) |
| 91 | リリース日<br>バージョン | 30-Apr-2021<br>[91.0.864.11](/deployedge/microsoft-edge-relnote-beta-channel#version-91086411-april-30) | 27-May-2021<BR>[91.0.864.37](/deployedge/microsoft-edge-relnote-stable-channel#version-91086437-may-27) |
| 92 | リリース日<br>バージョン | 08-Jun-2021<br>[92.0.902.9](/deployedge/microsoft-edge-relnote-beta-channel#version-9209029-june-08) | 2021 年 7 月 22 日<BR>[92.0.902.55](/deployedge/microsoft-edge-relnote-stable-channel#version-92090255-july-22) |
| 93 | リリース済み<br>バージョン | 03-Aug-2021<br>[93.0.961.11](/deployedge/microsoft-edge-relnote-beta-channel#version-93096111-August-03) | 02-Sep-2021<BR>[93.0.961.38](/deployedge/microsoft-edge-relnote-stable-channel#version-93096138-September-02) |
| 94 | リリース済み<br>バージョン | 02-Sep-2021<br>[94.0.992.9](/deployedge/microsoft-edge-relnote-beta-channel#version-9409929-September-02) | 2021 年 9 月 23 日の週 |
| 95 | ターゲットのリリース | 2021 年 9 月 28 日の週 | 2021 年 10 月 21 日の週 |
| 96 | ターゲットのリリース | 2021 年 10 月 26 日の週 | 2021 年 11 月 18日の週 |
| 97 | ターゲットのリリース | 2021 年 11 月 30 日の週 | 2022 年 1 月 6 日の週 |

## <a name="release-process"></a>リリース プロセス

ベータ版と Stable 版のメジャー リリースのトリガーは、同等の Chromium リリースです。

## <a name="progressive-rollouts"></a>プログレッシブ ロールアウト

Stable チャネルの日付参照（リリース済み/リリースされる週）は、プログレッシブ ロールアウトの開始を参照します。

弊社はプログレッシブ ロールアウト モデルを使用しています。これは、特定のデバイスの新しいリリースの可用性が、今後数日にわたってずれる可能性があることを意味します。 詳細については、「[Microsoft Edge Stable チャネルのプログレッシブ ロールアウト](/deployedge/microsoft-edge-update-progressive-rollout)」を参照してください。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge チャネル](/deployedge/microsoft-edge-channels)
- [チャネル ダウンロード](https://www.microsoft.com/edge/business/download)
