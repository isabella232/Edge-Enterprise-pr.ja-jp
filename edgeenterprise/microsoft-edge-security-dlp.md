---
title: Microsoft Edge でのデータ損失防止
ms.author: archandr
author: dan-wesley
manager: seanlynd
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge (DLP) でのデータ損失防止
ms.openlocfilehash: f1a38119e39419cf285a0ef934af9397bd9be3fc509afd1b63655c36aca4e143
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "11727270"
---
# <a name="data-loss-prevention-dlp-in-microsoft-edge"></a>Microsoft Edge (DLP) でのデータ損失防止

データ損失防止 (DLP) は、企業の機密データを特定し、許可されていない公開から保護する技術のシステムです。 業務標準や業界の規制を遵守するために、組織は機密情報を保護し、その許可されていない公開を防止する必要があります。 機密情報には、財務データやクレジット カード番号、社会保障番号、医療記録などの個人を特定できる情報 (PII) が含まれます。

リモート ワークでは、DLP の使用が重視されるようになりました。 デバイス上での個人や業務アクティビティの利用が増加していることから、企業は職場外で企業データが許可なく共有されてしまうリスクに直面しています。

このようなユーザー アクティビティの融合はデバイスにも広がっており、個人のデバイスや企業のデバイスの間を、さまざまなパブリック ネットワークやプライベート ネットワークを介してデータが移動しています。 その結果として、機密データを公開してしまうリスクは飛躍的に高まりました。

Microsoft Edge は、Microsoft エンドポイント DLP と Windows 情報保護 (WIP) という 2 つの異なる DLP ソリューションをネイティブにサポートしています。

## <a name="microsoft-endpoint-data-loss-prevention-endpoint-dlp"></a>Microsoft エンドポイント データ損失防止 (エンドポイント DLP)

Microsoft エンドポイント DLP は、データ中心の保護などの先進の概念を使用して、次世代のデータ損失防止機能を備えています。 これは Windows 10 と Microsoft Edge に組み込まれているため、デバイスに追加のエージェントやプラグインは必要ありません。

> [!NOTE]
> これは、Microsoft Edge バージョン 85 以降に適用されます。

エンドポイントの DLP の詳細については、次のリソースを使用してください。

- [ビデオ: Microsoft Edge とデータ損失防止 (DLP)](microsoft-edge-video-security-dlp.md)
- [Microsoft 365 エンドポイントのデータ損失防止について](/microsoft-365/compliance/endpoint-dlp-learn-about?preserve-view=true&view=o365-worldwide)
- [エンドポイントのデータ損失防止の使用を開始する](/microsoft-365/compliance/endpoint-dlp-getting-started?preserve-view=true&view=o365-worldwide)

Microsoft Edge は、管理者が構成した機密ファイル用のポリシーを強制し、非準拠アクティビティの監査イベントを記録します。

Windows 10 を実行しているデバイスで監査および管理できるユーザー アクティビティには、次のものが含まれます。

- ファイルのアップロード: 許可されていないクラウド上の場所にアップロードされた機密ファイルを保護します。 <!-- The next 3 screenshots show a sequence where a user tries to drop a sensitive data file on to their local storage.-->
- クリップボードの保護: 機密データがファイルからコピーされないように保護します。
- 印刷の保護: 機密ファイルが印刷されないように保護します。
- USB/ネットワークへの保存: 機密ファイルがリムーバブル USB ストレージや許可されていないネットワークの場所に保存されないように保護します。

監査や管理が可能なユーザー アクティビティの詳細については、「[Endpoint activities you can monitor and take action on (監視したり、アクションを実行したりできるエンドポイント アクティビティ)](/microsoft-365/compliance/endpoint-dlp-learn-about?preserve-view=true&view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on)」を参照してください。

## <a name="windows-information-protection"></a>Windows 情報保護

Microsoft Edge が Windows 情報保護 (WIP) をどのようにサポートしているかについては、「[Windows Information Protection のサポート](./microsoft-edge-security-windows-information-protection.md)」をご覧ください。 システム要件、メリット、サポートされている機能については、次のセクションを参照してください。

- [システム要件](./microsoft-edge-security-windows-information-protection.md#system-requirements)
- [Windows 情報保護のメリット](./microsoft-edge-security-windows-information-protection.md#windows-information-protection-benefits)
- [Microsoft Edge でサポートされている WIP の機能](./microsoft-edge-security-windows-information-protection.md#wip-features-supported-in-microsoft-edge)

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [ビデオ: Microsoft Edge でのデータ損失防止](https://www.youtube.com/watch?v=dLD04U9eTqg)
- [データ損失防止の概要](/microsoft-365/compliance/data-loss-prevention-policies?preserve-view=true&view=o365-worldwide)
- [Windows 情報保護を使用して企業データを保護する](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)