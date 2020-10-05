---
title: Microsoft Edge と条件付きアクセス
ms.author: srugh
author: srugh
manager: seanlyn
ms.date: 10/02/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge と条件付きアクセス
ms.openlocfilehash: a81d39c15f418dab6565ee7acc45de17f66e3828
ms.sourcegitcommit: 3478cfcf2b03944213a7c7c61f05490bc37aa7c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2020
ms.locfileid: "11094777"
---
# Microsoft Edge と条件付きアクセス
  
この記事では、Microsoft Edge が条件付きアクセスをサポートする方法と、条件付きアクセスによって保護されているリソースにアクセスする方法について説明します。

> [!NOTE]
> この記事は Microsoft Edge version 77 以降に適用されます。

クラウド リソースを管理する場合、クラウドのセキュリティで重要になる要素は ID とアクセスです。 モバイル ファースト、クラウド ファーストの環境では、ユーザーはどこからでもさまざまなデバイスとアプリを使用して、組織のリソースにアクセスできます。 このため、どのユーザーがリソースにアクセスできるかという点を考えるだけでは不十分です。 リソースへのアクセス方法についても考慮する必要があります。 Azure Active Directory (Azure AD) の条件付きアクセスは、セキュリティと生産性のバランスを制御するために役立ちます。

## Microsoft Edge で条件付きアクセスによって保護されたリソースにアクセスする

Microsoft Edge では、Azure AD 条件付きアクセスがネイティブにサポートされています。 別の拡張機能をインストールする必要はありません。 エンタープライズ Azure AD 資格情報を使用して Microsoft Edge プロファイルにサインインすると、条件付きアクセスを使用して保護されたエンタープライズ クラウド リソースへのシームレスなアクセスが、Microsoft Edge によって許可されます。

準拠デバイスで、リソースにアクセスする ID は、プロファイルの ID と一致している必要があります。  一致していない場合は、次のスクリーンショットに示されているようなメッセージが表示されます。 スクリーンショットの例で、"testadmin@evostsoneboxtest.com" は、リソースにアクセスするために必要なサインイン アカウントです。

![ブラウザーに表示された、条件付きアクセスのメッセージ](./media/edge-security/microsoft-edge-security-conditional-access.png)

続行するには、必要なプロファイル (ある場合) に切り替えるか、ID が一致するプロファイルを作成する必要があります。

サインインしてプロファイルを使用するには、ブラウザーの右上隅にあるアカウントの画像をクリックします。 ドロップダウン メニューを使用すると、次のことができます。

- 別のプロファイルを選択する。 プロファイル名をクリックします。
- プロファイルを作成する。 **[プロファイルの追加]** をクリックします。
- プロファイルを管理する。 **[プロファイルの設定を管理]** をクリックします。

このサポートは、サポートされているすべてのバージョンの Windows および macOS を含めて、すべてのプラットフォームに適用されます。

### Azure Active Directory の条件付きアクセスを展開する方法

[条件付きアクセスの展開に関するページ](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)には、Azure Active Directory での条件付きアクセスの展開に役立つ詳細なガイドが用意されています。

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [ビデオ - セキュリティ、互換性、管理の容易性](/microsoft-edge-video-security-compatibility-manageability.md)
