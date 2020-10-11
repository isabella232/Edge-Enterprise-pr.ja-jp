---
title: Microsoft Edge でのデータ損失防止
ms.author: archandr
author: dan-wesley
manager: seanlynd
ms.date: 10/08/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge (DLP) でのデータ損失防止
ms.openlocfilehash: 59c1b68c0526a49a2ee30283893707852514828d
ms.sourcegitcommit: 2af303fc97e8493024e2359fa2e8be162ab95a59
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104620"
---
# Microsoft Edge (DLP) でのデータ損失防止

データ損失防止 (DLP) は、企業の機密データを特定し、許可されていない公開から保護する技術のシステムです。 業務標準や業界の規制を遵守するために、組織は機密情報を保護し、その許可されていない公開を防止する必要があります。 機密情報には、財務データやクレジット カード番号、社会保障番号、医療記録などの個人を特定できる情報 (PII) が含まれます。

リモート ワークでは、DLP の使用が重視されるようになりました。 デバイス上での個人や業務アクティビティの利用が増加していることから、企業は職場外で企業データが許可なく共有されてしまうリスクに直面しています。

このようなユーザー アクティビティの融合はデバイスにも広がっており、個人のデバイスや企業のデバイスの間を、さまざまなパブリック ネットワークやプライベート ネットワークを介してデータが移動しています。 その結果として、機密データを公開してしまうリスクは飛躍的に高まりました。

Microsoft Edge は、Microsoft エンドポイント DLP と Windows 情報保護 (WIP) という 2 つの異なる DLP ソリューションをネイティブにサポートしています。

## Microsoft エンドポイント DLP

Microsoft エンドポイント DLP は、データ中心の保護などの最新のコンセプトを用いた次世代の DLP です。 これは Windows 10 と Microsoft Edge に組み込まれているので、デバイスに追加のエージェントやプラグインは必要ありません。 エンドポイント DLP の詳細については、「[Learn about Microsoft 365 Endpoint data loss prevention (Microsoft 365 エンドポイント データ損失防止について)](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide)」を参照してください。

> [!NOTE]
> これは、Microsoft Edge バージョン 85 以降に適用されます。

Microsoft Edge は、管理者が構成した機密ファイル用のポリシーを強制し、非準拠アクティビティの監査イベントを記録します。

Windows 10 を実行しているデバイスで監査および管理できるユーザー アクティビティには、次のものが含まれます。

- ファイルのアップロード: 許可されていないクラウド上の場所にアップロードされた機密ファイルを保護します。 次の 3 つのスクリーンショットは、ユーザーがローカル ストレージに機密データ ファイルをドロップする順序を示しています。
- クリップボードの保護: 機密データがファイルからコピーされないように保護します。
- 印刷の保護: 機密ファイルが印刷されないように保護します。
- USB/ネットワークへの保存: 機密ファイルがリムーバブル USB ストレージや許可されていないネットワークの場所に保存されないように保護します。

監査や管理が可能なユーザー アクティビティの詳細については、「[Endpoint activities you can monitor and take action on (監視したり、アクションを実行したりできるエンドポイント アクティビティ)](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on)」を参照してください。

## Windows 情報保護

Microsoft Edge が Windows 情報保護 (WIP) をどのようにサポートしているかについては、「[Windows Information Protection のサポート](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection)」をご覧ください。 システム要件、メリット、サポートされている機能については、次のセクションを参照してください。

- [システム要件](https://docs.microsoft.com/deployedge/:microsoft-edge-security-windows-information-protection#system-requirements)
- [Windows 情報保護のメリット](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection#windows-information-protection-benefits)
- [Microsoft Edge でサポートされている WIP の機能](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-information-protection#wip-features-supported-in-microsoft-edge)

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [ビデオ: Microsoft Edge でのデータ損失防止](https://www.youtube.com/watch?v=dLD04U9eTqg)
- [データ損失防止の概要](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)
- [Windows 情報保護を使用して企業データを保護する](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)
