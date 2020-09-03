---
title: Microsoft Edge エンタープライズ プライバシー設定
ms.author: likravit
author: dan-wesley
manager: srugh
ms.date: 05/26/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge エンタープライズ プライバシー設定を構成する
ms.openlocfilehash: 2b7a33087ae5110c53d18b3192486d4ae62fa540
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980508"
---
# 企業のプライバシーをサポートするように Microsoft Edge ポリシーを構成する

Microsoft では、Microsoft Edge のデータ収集に関する選択を行うために必要な情報とコントロールを企業のお客様に提供できるよう取り組んでいます。

## 概要

既定では、Windows 以外のプラットフォームに展開された Microsoft Edge では、診断データやサイト情報は Microsoft に送信されません。 Microsoft Edge が Windows 10 に導入されている場合、規定では、ユーザーの [Windows 診断データ設定](https://go.microsoft.com/fwlink/?linkid=2099569)に基づいて診断データが送信されます。

次のグループポリシーを使用して、Microsoft Edge が組織のデータ収集を処理する方法を構成することもできます。

- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - 使用状況とクラッシュ関連のデータレポートを有効にします。
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Microsoft サービスを改善するためにサイト情報を送信します。

## ポリシー設定を構成する

始める前に、最新の Microsoft Edge ポリシーテンプレートをダウンロードして使用してください (詳細については、「[Microsoft Edge を構成する](configure-microsoft-edge.md)」を参照してください)。

### 使用状況とクラッシュ関連データのレポートを有効にする

このポリシーによって、Microsoft Edge の使用状況およびクラッシュに関連するデータの Microsoft への送信が有効になります。

Microsoft Edge では、製品を最新の状態に保ち、セキュリティで保護し、適切に実行するために必要な一連のデータが収集されます。 このデータには、現在のデータ収集の同意、アプリのバージョン、Microsoft Edge のインストール状態に関する、Microsoft Edgeからの基本的なデバイス接続と構成情報が含まれています。このデータ収集は、ポリシーを無効にすることでオフにできます。

使用状況およびクラッシュに関連するデータのレポートを Microsoft に送信するには、このポリシーを有効にします。 このデータを Microsoft に送信しない場合は、このポリシーを無効にします。 いずれの場合でも、ユーザーがこの設定を変更または上書きすることはできません。

Microsoft Edge が Windows 10 で実行されている場合: 

- このポリシーが構成されていない場合、Microsoft Edge は既定で Windows 診断データの設定になります。
- このポリシーが有効になっている場合、Microsoft Edge は、Windows 診断データの設定が **[拡張]** または **[完全]** に設定されている場合にのみ使用状況データを送信します。
- このポリシーが無効になっている場合、Microsoft Edge は使用状況データを送信しません。 クラッシュに関連するデータは、Windows 診断データの設定に基づいて送信されます。 [Windows 診断データ設定の詳細を参照してください](https://go.microsoft.com/fwlink/?linkid=2099569)。

Microsoft Edge が Windows 7、8、または macOS で実行されている場合：

- このポリシーが構成されていない場合、Microsoft Edge は既定でユーザーの設定に従います。

### Microsoft サービスの品質向上のためにサイト情報を送信する

このポリシーでは、検索などの Microsoft 製品やサービスの品質を向上させるために Microsoft Edge で訪問した Web サイトに関する情報を Microsoft に送信できます。

Microsoft Edge でアクセスした Web サイトに関する情報を Microsoft に送信する場合は、このポリシーを有効にします。 Microsoft Edge でアクセスした Web サイトに関する情報を Microsoft に送信しない場合は、このポリシーを無効にします。 いずれの場合でも、ユーザーがこの設定を変更または上書きすることはできません。

Microsoft Edge が Windows 10 で実行されている場合: 

- このポリシーが構成されていない場合、Microsoft Edge は既定で Windows 診断データの設定になります。
- このポリシーが有効になっている場合、Microsoft Edge は、Windows 診断データの設定が **[完全]** に設定されている場合にのみ、アクセスした Web サイトに関する情報を送信します。
- このポリシーが無効になっている場合、Microsoft Edge はアクセスした Web サイトに関する情報を送信しません。 詳細については、[Windows 診断データの設定に関するトピック](https://go.microsoft.com/fwlink/?linkid=2099569)を参照してください。

Microsoft Edge が Windows 7、8、または macOS で実行されている場合：

- このポリシーが構成されていない場合、Microsoft Edge は既定でユーザーの設定に従います。

## 実装の詳細

Windows 10 で、実装が Windows 診断データの設定にどのように依存しているかを説明するために、**[使用状況とクラッシュ関連データのレポートを有効にする]** と **[Microsoft サービスの品質向上のためにサイト情報を送信する]** が構成されていない場合の構成を次の表に示します。。

| Windows 診断データの設定 | 使用状況とクラッシュ関連データのレポートを有効にする | Microsoft サービスの品質向上のためにサイト情報を送信する |
|---------------------------------|-----------------------------------------------|-----------------------------------------------------|
| セキュリティ                        | 送信されない                                      | 送信されない                                            |
| 基本                           | 送信されない                                      | 送信されない                                            |
| 拡張                        | 送信される                                          | 送信されない                                            |
| 完全                            | 送信される                                          | 送信される                                                |

Windows 10 の構成が上記の表に従って正しく構成されていない場合は、より少ないデータ収集設定に戻されます。

次に、例を示します。

- [使用状況とクラッシュ関連データのレポートを有効にする] ポリシーは **[有効]** に設定されていますが、Windows 診断データの設定が **[基本]** に設定されています。 この場合、使用状況やクラッシュに関連するデータは送信されません。
- [Microsoft サービスの品質向上のためにサイト情報を送信する] ポリシーは **[無効]** に設定されていますが、Windows 診断データの設定が **[完全]** に設定されています。 この場合、アクセスしたサイトに関する情報は送信されません。

以前の設定の正しい実装は、「使用状況とクラッシュ関連のデータレポートを有効にする」ポリシーを **[有効]** に設定し、Windows診断データ設定を **[拡張]** または **[完全]** に設定することです。

## その他のプライバシー ポリシー オプション

データのプライバシーに関連する次のグループ ポリシーも検討することをお勧めします。

- 特定のサイトでの Cookie のブロック
- サード パーティの Cookie のブロック
- トラッキング拒否を構成する
- InPrivate モードの無効化

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge ポリシー](microsoft-edge-policies.md)
- [Microsoft Edge プライバシー ホワイトペーパー](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper)
