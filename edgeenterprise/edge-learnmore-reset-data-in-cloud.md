---
title: Microsoft Edge データをリセットする
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 07/09/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: クラウドで Microsoft Edge データをリセットする方法
ms.openlocfilehash: dc6c0ae1b1bc31228e9b9b1de315a19e99149134
ms.sourcegitcommit: 2a00571483e1d169b2b3b59f4fce43262f460a9a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643742"
---
# <a name="reset-microsoft-edge-data-in-the-cloud"></a>クラウドで Microsoft Edge データをリセットする

この記事では、クラウドで Microsoft Edge データをリセットする手順について説明します。

> [!NOTE]
> この記事は、特に説明がない限り、Microsoft Edge バージョン 88 以降に適用されます。

> [!NOTE]
> テナントが GCC Mod 環境にある場合、テナント管理者はデータをリセットするために Microsoft にサポート リクエストを提出する必要があります。

## <a name="overview"></a>概要

クラウドで Microsoft Edge データをリセットする必要がある場合があります。 たとえば、ユーザーがデータを同期したいと思っても、Microsoft Edge はデータを同期できないと報告することがあります。 または、データが Microsoft のクラウドから削除されるのを確認したい場合があります。 どちらの場合も、Microsoft Edge ではクラウド データのリセットを実行できます。

## <a name="back-up-your-favorites"></a>お気に入りをバックアップする

リセットを実行する前に、お気に入りをバックアップすることをお勧めします。 お気に入りをバックアップするには、次の手順を実行します。

1. Microsoft Edge の右上隅で、**[設定など] > [お気に入り] > [その他のオプション] > [お気に入りのエクスポート]** の順に選択します。
2. お気に入りを保存するファイルを選択します。 独自のファイル名を入力するか、Microsoft Edge が既定で提供する名前 "favorites_month_day_year.html" をファイル名として使用できます。 たとえば、"favorites_12_17_20.html" とします。 お気に入りを後で復元する必要がある場合は、そのファイルから復元できます。
3. **[保存]** をクリックします。

## <a name="perform-a-reset-to-fix-a-synchronization-problem"></a>リセットを実行して同期の問題を修正する

Microsoft Edge がデータを同期できないと報告し、データのリセットを提案する場合は、リセットを実行して問題を解決します。

リセットを行うには、次の手順を実行します。

1. まず、リセットを実行しているデバイスを除き、モバイル デバイスを含むすべてのデバイスで Microsoft Edge からサインアウトしていることを確認してください。 Microsoft Edge からサインアウトするには、Microsoft Edge の右上隅にある **[設定など] > [設定] > [サインアウト]** を選択します。サインアウトするときは、ローカル デバイスからお気に入りや設定などをクリアするオプションを選択しないでください。
2. 他のすべてのデバイスからサインアウトした後、デスクトップで Microsoft Edge を開きます。Microsoft Edge の右上隅にある **[設定など] > [同期] > [同期のリセット] を選択します**。表示されるダイアログ ボックスで、データをリセットした後に同期を再開することを選択し、**[リセット]** を選択します。

## <a name="perform-a-reset-to-remove-your-data-from-microsofts-cloud"></a>リセットを実行して Microsoft のクラウドからデータを削除する

Microsoft のクラウドからデータを削除する場合は、次の手順に従ってリセットします。

1. リセットを実行しているデバイス以外のデバイスで同期を停止します。  Microsoft Edge の右上隅で、**[設定など] > [設定] > [同期] > [同期をオフ]** の順に選択します。  
2. 同期を停止した後、Microsoft Edge の右上隅にある **[設定など] > [同期] > [同期のリセット]** を選択します。表示されるダイアログ ボックスで、データをリセットした後に同期を再開することを選択**しない**でください。 **[リセット]** を選択します。

## <a name="what-to-expect-during-and-after-a-data-reset"></a>データのリセット中およびリセット後に予想される処理

Microsoft のクラウドに保存したデータの量によって、データのリセットに数秒から数分かかる場合があります。 場合によっては、リセットを完了できないというメッセージや、もう一度リセットを提案するメッセージが表示されることがあります。 この場合は、数時間待って、もう一度データのリセットを試みます。 それでもデータをリセットできない場合は、Microsoft Edge サポートにお問い合わせください。

データのリセットが正常に完了すると、リセット後に同期を再開することを選択した場合、データはデバイスから再び同期されます。 それらのデバイスから同期する場合は、他のデバイスにサインインし戻す必要があります。 ただし、同期の再開を選択しなかった場合、Microsoft Edge データはクラウドから削除され、データは同期されません。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge エンタープライズの同期](microsoft-edge-enterprise-sync.md)