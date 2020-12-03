---
title: Microsoft Edge エンドポイントの許可リスト
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 11/25/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge エンドポイントの許可リスト
ms.openlocfilehash: 3d46e2e8c85eadc39cf9788df44b45592ea4fb1b
ms.sourcegitcommit: ed6a5afabf909df87bec48671c4c47bcdfaeb7bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "11194693"
---
# Microsoft Edge エンドポイントの許可リスト

Microsoft Edge の機能を利用するには、インターネットに接続する必要があります。 この記事では、ファイアウォールやその他のセキュリティ メカニズムを介した通信を行うために、許可リストに追加する必要があるドメインの URL について説明します。

> [!NOTE]
> これは、Microsoft Edge version 77 以降に適用されます。

## 許可するドメインの URL

Microsoft Edge で次のドメインの URL を許可します。

### Update Service

Microsoft Edge が新しい更新プログラムを確認するために使用するサービス。

- `https://msedge.api.cdp.microsoft.com`

### Experimentation and Configuration Service

- `https://config.edge.skype.com`

### Microsoft Edge のダウンロード場所

初期インストール中、または更新プログラムが利用可能になった場合に、Microsoft Edge をダウンロードできる場所です。 ダウンロード場所は、Update Service によって決定されます。

#### HTTP

- `http://msedge.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.f.dl.delivery.mp.microsoft.com`
- `http://msedge.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.b.dl.delivery.mp.microsoft.com`

#### HTTPS

- `https://msedge.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sf.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > ダウンロード場所の許可リストを簡略化するには、次のようにワイルドカードを使用します。 `*.dl.delivery.mp.microsoft.com`

### Microsoft Edge 拡張機能のダウンロード場所

初期インストール中、または更新プログラムが利用可能になった場合に、Microsoft Edge 拡張機能をダウンロードできる場所です。 ダウンロード場所は、Update Service によって決定されます。

#### HTTP

- `http://msedgeextensions.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.f.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.dl.delivery.mp.microsoft.com`

#### HTTPS

- `https://msedgeextensions.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sf.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > ダウンロード場所の許可リストを簡略化するには、次のようにワイルドカードを使用します。 `*.dl.delivery.mp.microsoft.com`

### ダウンロード配信の最適化 (オプション)

配信の最適化については、「[Windows 10 更新プログラムの配信の最適化](https://aka.ms/waas-do)」をご覧ください。

- クライアントとサービスの通信の場合: `*.do.dsp.mp.microsoft.com` (HTTP ポート 80、HTTPS ポート 443)
- クライアントとクライアントの通信の場合: TCP ポート7680を受信トラフィック用に開く必要がある

### 同期

これらのエンドポイントは、同期データの読み取りと書き込み、安全なデータの権利管理、新しい同期データが利用可能になったときのブラウザーへの通知を管理します。

- Edge の同期サービス エンドポイント:

  - `https://edge-enterprise.activity.windows.com`
  - `https://edge.activity.windows.com`

- Azure Information Protection エンドポイント:

  - `https://api.aadrm.com` (ほとんどのテナントの場合)
  - `https://api.aadrm.de` (ドイツのテナントの場合)
  - `https://api.aadrm.cn` (中国のテナントの場合)

- [Windows 通知サービス エンドポイント](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)

## その他のブラウザー サポート サービス

追跡防止、証明書失効リスト、その他のブラウザー コンポーネントの更新プログラムなど、ブラウザー機能のメタデータを提供します。 ダウンロード可能なスペルチェック辞書と広告ブロックの禁止リストを提供します。 コレクション、オートフィル、拡張ストアなどのブラウザー機能をサポートするサービスを提供します。

- `http://edge.microsoft.com/`
- `https://edge.microsoft.com/`

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge ドキュメント ランディング ページ](https://docs.microsoft.com/DeployEdge/)
- [Windows 10 Enterprise Version 1903 の接続エンドポイントの管理](https://docs.microsoft.com/windows/privacy/manage-windows-1903-endpoints)
