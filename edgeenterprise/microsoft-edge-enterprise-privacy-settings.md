---
title: Microsoft Edge エンタープライズ プライバシー設定
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge エンタープライズ プライバシー設定を構成する
ms.openlocfilehash: fe2a6e57d70a6a37297e28854291b913af1fd08e826df845fc3572fecb09f07a
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "11726190"
---
# <a name="configure-microsoft-edge-policies-to-support-enterprise-privacy"></a>企業のプライバシーをサポートするように Microsoft Edge ポリシーを構成する

Microsoft では、Microsoft Edge のデータ収集に関する選択を行うために必要な情報とコントロールを企業のお客様に提供できるよう取り組んでいます。

## <a name="overview"></a>概要

Microsoft Edge が Windows 10 に導入されている場合、規定では、ユーザーの [Windows 診断データ設定](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)に基づいて診断データが送信されます。

Microsoft Edge が Windows 以外のプラットフォームで展開されるとき、以下のグループ ポリシーに従って診断データが収集されます。

- (非推奨) [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) - 使用状況とクラッシュ関連データのレポートを有効にします。 このポリシーは Microsoft Edge バージョン 89 で廃止されます。
- (非推奨) [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) - Microsoft サービスの品質向上のためにサイト情報を送信します。 このポリシーは Microsoft Edge バージョン 89 で廃止されます。

上記の非推奨のポリシーは、Windows 10 では[利用統計情報の許可](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)に、その他のすべてのプラットフォームでは[DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) ポリシーに置き換えられます。  

## <a name="configure-policy-settings"></a>ポリシー設定を構成する

始める前に、最新の Microsoft Edge ポリシーテンプレートをダウンロードして使用してください (詳細については、「[Microsoft Edge を構成する](configure-microsoft-edge.md)」を参照してください)。

### <a name="send-required-and-optional-diagnostic-data-about-browser-usage"></a>ブラウザーの使用状況に関する必須およびオプションの診断データを送信する

[DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) ポリシーが構成されている場合、[MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled)  と [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) よりも優先されます。

#### <a name="required-and-optional-diagnostic-data"></a>必須診断データとオプションの診断データ

必須の診断データは、Microsoft Edge のセキュリティ、最新の状態、期待どおりの動作を維持するために収集されます。

オプションの診断データには、ブラウザーの使用方法に関するデータ、アクセスした Web サイト、Microsoft Edge のセキュリティ、最新の状態、期待どおりの動作を維持するためのクラッシュ レポートが含まれます。このデータは、Microsoft Edge とすべてのユーザー向けのその他の Microsoft 製品とサービスの品質向上のために使用されます。

> [!NOTE]
> このポリシーは、Windows 10 デバイスではサポートされていません。 Windows 10 でデータの収集を制御するには、IT 管理者が Windows 診断データ グループ ポリシーを使用する必要があります。 このポリシーは、使用している Windows のバージョンに応じて、**利用統計情報を許可する**、または**診断データを許可する**、となります。 詳細については、「[Windows 10 の診断データの構成](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)」を参照してください。

**DiagnosticData** を構成するには、次のいずれかの設定を使用します。

- オフ (非推奨) (0) にすると、必須診断データおよびオプションの診断データの収集をオフにします。 
- 必須データ (1) は、必須診断データを送信しますが、オプションの診断データの収集をオフにします。 Microsoft Edge では、セキュリティ、最新の状態、期待どおりの動作を維持するために必要な必須の診断データが送信されます。 
- オプションのデータ (2) は、ブラウザーの使用状況、アクセスした Web サイト、Microsoft Edge のセキュリティ、最新の状態、期待どおりの動作を維持するために Microsoft に送信されたクラッシュ レポートを含むオプションの診断データを送信します。このデータは、Microsoft Edge とすべてのユーザー向けのその他の Microsoft 製品とサービスの品質向上のために使用されます。

Windows 7、Windows 8/8.1、macOS では、このポリシーによって必須診断データとオプションの診断データの Microsoft への送信が制御されます。

このポリシーを構成しなかった場合、または無効にした場合は、Microsoft Edge は既定でユーザーの設定に従います。

### <a name="deprecated-enable-usage-and-crash-related-data-reporting"></a>(非推奨) 使用状況とクラッシュ関連データのレポートを有効にする

**MetricsReportingEnabled** ポリシーによって、Microsoft Edge の使用状況とクラッシュに関連するデータの Microsoft への送信が有効になります。

Microsoft Edge では、製品の最新の状態、セキュリティによる保護、期待どおりの動作を維持するために必要な、一連の必須データが収集されます。 このデータには、現在のデータ収集の同意、アプリのバージョン、Microsoft Edge のインストール状態に関する、Microsoft Edgeからの基本的なデバイス接続と構成情報が含まれています。このデータ収集は、ポリシーを無効にすることでオフにできます。

使用状況およびクラッシュに関連するデータのレポートを Microsoft に送信するには、このポリシーを有効にします。 このデータを Microsoft に送信しない場合は、このポリシーを無効にします。 いずれの場合でも、ユーザーがこの設定を変更または上書きすることはできません。

Microsoft Edge が Windows 10 で実行されている場合: 

- このポリシーが構成されていない場合、Microsoft Edge は既定で Windows 診断データの設定になります。
- このポリシーが有効になっている場合、Microsoft Edge は、Windows 診断データの設定が **[拡張]** または **[完全]** に設定されている場合にのみ使用状況データを送信します。
  - このポリシーを有効にすると、[SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) も有効になっている場合にのみ、Microsoft Edge は使用状況データを送信します。
- このポリシーが無効になっている場合、Microsoft Edge は使用状況データを送信しません。 クラッシュに関連するデータは、Windows 診断データの設定に基づいて送信されます。 [Windows 診断データ設定の詳細を参照してください](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)。

Microsoft Edge が Windows 7、8、または macOS で実行されている場合：

- このポリシーが構成されていない場合、Microsoft Edge は既定でユーザーの設定に従います。
-  このポリシーを有効にすると、[SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) も有効になっている場合にのみ、Microsoft Edge は使用状況データを送信します。

### <a name="deprecated-send-site-information-to-improve-microsoft-services"></a>(非推奨) Microsoft サービスの品質向上のためにサイト情報を送信する

**SendSiteInformationToImproveServices** ポリシーは、検索などの Microsoft 製品やサービスの品質向上のために、Microsoft Edge でアクセスした Web サイトに関する情報を Microsoft に送信できるようにします。

Microsoft Edge でアクセスした Web サイトに関する情報を Microsoft に送信する場合は、このポリシーを有効にします。 Microsoft Edge でアクセスした Web サイトに関する情報を Microsoft に送信しない場合は、このポリシーを無効にします。 いずれの場合でも、ユーザーがこの設定を変更または上書きすることはできません。

Microsoft Edge が Windows 10 で実行されている場合: 

- このポリシーが構成されていない場合、Microsoft Edge は既定で Windows 診断データの設定になります。
- このポリシーが有効になっている場合、Microsoft Edge は、Windows 診断データの設定が **[完全]** に設定されている場合にのみ、アクセスした Web サイトに関する情報を送信します。
  - このポリシーを有効にすると、[MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) も有効になっている場合にのみ、Microsoft Edge は使用状況データを送信します。 
- このポリシーが無効になっている場合、Microsoft Edge はアクセスした Web サイトに関する情報を送信しません。 詳細については、[Windows 診断データの設定に関するトピック](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)を参照してください。

Microsoft Edge が Windows 7、8、または macOS で実行されている場合：

- このポリシーを有効にすると、[MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) も有効になっている場合にのみ、Microsoft Edge は使用状況データを送信します。
- このポリシーが構成されていない場合、Microsoft Edge は既定でユーザーの設定に従います。

## <a name="implementation-details"></a>実装の詳細

Windows 10 以外のデバイスの場合: 
- [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) ポリシーが構成されている場合、[MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled)  と [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) よりも優先されます。 
- [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) ポリシーが構成されていない場合、Microsoft Edge は [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled)  と [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) をリッスンします。  

Windows 10 については、実装と Windows 診断データの設定への依存関係を説明するために、 **必須**または**オプション**のどちらの診断データが Microsoft に送信されるかを次の表に示します。

| Windows 診断データの設定 | 必須診断データ  | オプションの診断データ |
|---------------------------------|-----------------------------------------------|-----------------------------------------------------|
| セキュリティ                        | 送信されない                                      | 送信されない                                            |
| 基本                           | 送信される                                      | 送信されない                                            |
| 拡張                        | 送信される                                          | 送信されない                                            |
| 完全                            | 送信される                                          | 送信される                                                |

> [!IMPORTANT]
> Microsoft Edge は、Microsoft Edge バージョン 86 〜 88 では **MetricsReportingEnabled**  と **SendSiteInfoToImproveServices** をサポートします。 Microsoft Edge バージョン 89 で **MetricsReportingEnabled**  と **SendSiteInfoToImproveServices** はサポートされなくなり、既定で Windows 10 以外のプラットフォームでは **DiagnosticData**、Windows 10 では **利用統計情報の許可** ポリシーに従います。

## <a name="additional-privacy-policy-options"></a>その他のプライバシー ポリシー オプション

データのプライバシーに関連する次のグループ ポリシーも検討することをお勧めします。

- 特定のサイトでの Cookie のブロック
- サード パーティの Cookie のブロック
- トラッキング拒否を構成する
- InPrivate モードの無効化

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge ポリシー](microsoft-edge-policies.md)
- [Microsoft Edge プライバシー ホワイトペーパー](/microsoft-edge/privacy-whitepaper)