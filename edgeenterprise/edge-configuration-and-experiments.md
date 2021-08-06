---
title: Microsoft Edge の構成と試験
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge の構成と試験
ms.openlocfilehash: d6aee10133b5cbc0f7a784fab561864303d3dc6eb4e1cb6547562b9e6107961a
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "11726170"
---
# <a name="microsoft-edge-configurations-and-experimentation"></a>Microsoft Edge の構成と試験

この記事では、Microsoft Edge と Experimentation and Configuration Service (ECS) の間でのやり取りについて説明します。 Microsoft Edge は、このサービスと通信して、さまざまな種類のペイロードを要求して受け取ります。 これらのペイロードには、構成、機能のロールアウト、試験が含まれます。

> [!IMPORTANT]
> ペイロードを受信できるように、クライアントが `https://config.edge.skype.com` にアクセスできることを確認します。

> [!NOTE]
> これは、Microsoft Edge version 77 以降に適用されます。

## <a name="configurations"></a>構成

構成は、製品の正常性、セキュリティ、プライバシーに関するコンプライアンスを保証するためのペイロードであり、(プラットフォームとチャネルに基づいて) すべてのユーザーに同じ値を使用することを目的としています。これにより、ドメイン アクションの機能フラグを有効にすることも、バグの発生時に機能フラグを無効にすることもできます。

## <a name="controlled-feature-rollout"></a>制御された機能ロールアウト

制御された機能ロールアウト (Controlled Feature Rollout: CFR) は、機能を受け取るユーザー グループのサイズを徐々に拡大するための手順です。 ユーザー母集団からランダムに選択されたサブセットに新しい機能を配布することで、その機能が配布されていない同じサイズのコントロール グループとユーザー フィードバックを比較して、機能の影響を測定することができます。

## <a name="experiments"></a>テスト

Microsoft Edge のビルドには、まだ開発中の機能や、試験的な機能が含まれています。 試験は CFR に似ていますが、新しい概念をテストするために、ユーザー グループのサイズはずっと小さくなります。 これらの機能は、機能がロールアウトされるか試験が終了するまで、既定で非表示になります。 これらの機能を有効または無効にするには、試験フラグを使用します。

## <a name="about-the-ecs"></a>ECS について

上記のすべてのシナリオでは、ブラウザー クライアントに適用できるように、このサービスによって機能フラグの値が配布されます。 更新プログラムによって、構成が直ちに適用される場合も、ユーザーがブラウザーを再起動したときに適用される場合もあります。

このサービスと Microsoft Edge との間のやり取りは、[ExperimentationAndConfigurationServiceControl](./microsoft-edge-policies.md#experimentationandconfigurationservicecontrol) ポリシーの設定によって制御されます。 ポリシー設定は、次のように構成できます。

- 構成のみを取得する
- 構成と試験を取得する
- サービスとの通信を無効にする

  > [!CAUTION]
  > サービスとの通信を無効にすると、Microsoft が深刻なバグに迅速に対応するための機能に影響します。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://www.microsoftedgeinsider.com/enterprise)
- [Microsoft Edge ドキュメント ランディング ページ](./index.yml)