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
ms.openlocfilehash: b8f793edcc23798199fe5de1bfae912a63468464
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11448201"
---
# <a name="allow-list-for-microsoft-edge-endpoints"></a>Microsoft Edge エンドポイントの許可リスト

Microsoft Edge の機能を利用するには、インターネットに接続する必要があります。 この記事では、ファイアウォールやその他のセキュリティ メカニズムを介した通信を行うために、許可リストに追加する必要があるドメインの URL について説明します。

> [!NOTE]
> これは、Microsoft Edge version 77 以降に適用されます。

## <a name="domain-urls-to-allow"></a>許可するドメインの URL

Microsoft Edge で次のドメインの URL を許可します。

### <a name="update-service"></a>Update Service

Microsoft Edge が新しい更新プログラムを確認するために使用するサービス。

- `https://msedge.api.cdp.microsoft.com`

### <a name="experimentation-and-configuration-service"></a>Experimentation and Configuration Service

- `https://config.edge.skype.com`

### <a name="download-locations-for-microsoft-edge"></a>Microsoft Edge のダウンロード場所

初期インストール中、または更新プログラムが利用可能になった場合に、Microsoft Edge をダウンロードできる場所です。 ダウンロード場所は、Update Service によって決定されます。

#### <a name="http"></a>HTTP

- `http://msedge.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.f.dl.delivery.mp.microsoft.com`
- `http://msedge.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.b.dl.delivery.mp.microsoft.com`

#### <a name="https"></a>HTTPS

- `https://msedge.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sf.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > ダウンロード場所の許可リストを簡略化するには、次のようにワイルドカードを使用します。 `*.dl.delivery.mp.microsoft.com`

### <a name="download-locations-for-microsoft-edge-extensions"></a>Microsoft Edge 拡張機能のダウンロード場所

初期インストール中、または更新プログラムが利用可能になった場合に、Microsoft Edge 拡張機能をダウンロードできる場所です。 ダウンロード場所は、Update Service によって決定されます。

#### <a name="http"></a>HTTP

- `http://msedgeextensions.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.f.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.dl.delivery.mp.microsoft.com`

#### <a name="https"></a>HTTPS

- `https://msedgeextensions.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sf.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > ダウンロード場所の許可リストを簡略化するには、次のようにワイルドカードを使用します。 `*.dl.delivery.mp.microsoft.com`

### <a name="optionally-for-download-delivery-optimization"></a>ダウンロード配信の最適化 (オプション)

配信の最適化については、「[Windows 10 更新プログラムの配信の最適化](/windows/deployment/update/waas-delivery-optimization)」をご覧ください。

- クライアントとサービスの通信の場合: `*.do.dsp.mp.microsoft.com` (HTTP ポート 80、HTTPS ポート 443)
- クライアントとクライアントの通信の場合: TCP ポート7680を受信トラフィック用に開く必要がある

### <a name="sync"></a>同期

これらのエンドポイントは、同期データの読み取りと書き込み、安全なデータの権利管理、新しい同期データが利用可能になったときのブラウザーへの通知を管理します。

- Edge の同期サービス エンドポイント:

  - `https://edge-enterprise.activity.windows.com`
  - `https://edge.activity.windows.com`

- Azure Information Protection エンドポイント:

  - `https://api.aadrm.com` (ほとんどのテナントの場合)
  - `https://api.aadrm.de` (ドイツのテナントの場合)
  - `https://api.aadrm.cn` (中国のテナントの場合)

- [Windows 通知サービス エンドポイント](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)

## <a name="other-browser-support-services"></a>その他のブラウザー サポート サービス

追跡防止、証明書失効リスト、その他のブラウザー コンポーネントの更新プログラムなど、ブラウザー機能のメタデータを提供します。 ダウンロード可能なスペルチェック辞書と広告ブロックの禁止リストを提供します。 コレクション、オートフィル、拡張ストアなどのブラウザー機能をサポートするサービスを提供します。

- `http://edge.microsoft.com/`
- `https://edge.microsoft.com/`

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge ドキュメント ランディング ページ](./index.yml)
- [Windows 10 Enterprise Version 1903 の接続エンドポイントの管理](/windows/privacy/manage-windows-1903-endpoints)