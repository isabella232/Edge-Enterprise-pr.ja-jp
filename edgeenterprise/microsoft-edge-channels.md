---
title: Microsoft Edge チャネル概要
ms.author: srugh
author: srugh
manager: seanlynd
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge チャネル概要
ms.openlocfilehash: 7d1fb72b458569cb4e4c6f44a6d89be7f65984df
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641993"
---
# <a name="overview-of-the-microsoft-edge-channels"></a>Microsoft Edge チャネルの概要

次のバージョンの Microsoft Edge の利点の 1 つは、Microsoft が定期的に新機能を提供できることです。 ただし、組織内のユーザーに Microsoft Edge を展開する管理者は、ユーザーがこれらの新機能を受け取る頻度を細かく制御できる方が良い場合があります。 Microsoft では、Microsoft Edge を新しい機能で更新する頻度を制御するために、チャネルと呼ばれる 4 つのオプションを提供しています。 ここでは、これら 4 つのオプションの概要を説明します。

各チャネルのサポートの詳細については、「[Microsoft Edge のライフサイクル](/deployedge/microsoft-edge-support-lifecycle)」を参照してください。
  
> [!NOTE]
> この記事は Microsoft Edge バージョン 77 以降に適用されます。

## <a name="channel-overview"></a>チャネルの概要

|チャネル|主な目的|新機能に更新される頻度|サポート|
|:---:|---|:---:|:---:|
|[Stable](#stable-channel)|広範な展開|6 週間に 1 回以上|あり|
|[Beta](#beta-channel)|組織内での代表的な対象での検証|6 週間に 1 回以上|あり|
|[Dev](#dev-channel)|計画と開発|1 週間に 1 回|なし|
|[Canary](#canary-channel)|試験的な内容|毎日|なし|

どの更新チャネルをユーザーに展開するかについては、Microsoft Edge の更新されたバージョンでテストする必要がある、ユーザーが使用中の基幹業務アプリケーションの数など、いくつかの要因によって異なります。 この決定を行うには、Microsoft Edge で利用可能な 4 つの更新チャネルに関する次の情報をご確認ください。

### <a name="stable-channel"></a>Stable チャネル

Stable チャネルは、組織での広範な展開を目的としており、ほとんどのユーザーに適したチャネルです。 これはすべてのチャネルの中で最も安定しており、前の Beta チャネル リリースに含まれていた機能セットを安定させたものです。 約 6 週間ごとに新機能がリリースされます。 必要に応じて、セキュリティ更新プログラムと品質更新プログラムがリリースされます。 Stable チャネルからのリリースは、チャネルからの次のリリースが利用可能になるまでサービスが提供されます。

### <a name="beta-channel"></a>Beta チャネル

Beta チャネルは、組織内の実稼働環境への展開を目的とし、代表的なユーザーのグループを対象としています。 これはサポートされているリリースであり、Beta からの各リリースは、このチャネルからの次のリリースが利用可能になるまでサービスが提供されます。 ご利用環境で想定どおりに動作するかどうかを検証するための絶好の機会であり、問題が発生した場合は、リリースが Stable チャネルに公開される前に報告することができます。 約 6 週間ごとに新機能がリリースされます。 必要に応じて、セキュリティ更新プログラムと品質更新プログラムがリリースされます。

### <a name="dev-channel"></a>Dev チャネル

Dev チャネルは、Canary チャネルよりも高い品質で、Microsoft Edge の最新機能を計画および開発することを目的としています。 このチャネルでは、次の Beta リリースの前にいち早く新機能を確認し、準備できます。

### <a name="canary-channel"></a>Canary チャネル

Canary チャネルは毎日リリースされ、すべてのチャネル内でも最先端で試験的な内容です。 ここには、最新の投資内容が反映されます。 リリース頻度の性質上、長い目で見ると問題が発生することもあるため、Canary リリースを使用する場合は、別のチャネルを並行インストールすることもご検討ください。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [チャネル ダウンロード](https://aka.ms/EdgeEnterprise)
