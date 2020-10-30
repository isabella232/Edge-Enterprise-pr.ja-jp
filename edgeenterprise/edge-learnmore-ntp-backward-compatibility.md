---
title: '[エンタープライズ新規] タブページの下位互換性'
ms.author: ruchir
author: dan-wesley
manager: vwehren
ms.date: 10/28/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: '[エンタープライズ新規] タブページの下位互換性'
ms.openlocfilehash: c10671a6ec8e1ff4dcb0db3f3c085f82ae973122
ms.sourcegitcommit: af6ab070d0c09bca4a9cf505b107ed7e04839763
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "11144489"
---
# [エンタープライズ新規] タブページの下位互換性

この記事では、新しいタブページへの変更と、Microsoft Edge バージョン87以前のバージョンと下位互換性を持つために何をしたらよいのかを説明します。

> [!NOTE]
> この記事は Microsoft Edge version 87 以降に適用されます。

## 1つのエンドポイントからの情報フィード

新しいバージョンのエンタープライズ向けの新しいタブページでは、対応型Microsoft 365 のコンテンツと、MSN.com エンドポイント経由で配信される業界の関連する対応型情報フィードを組み合わせます。

> [!NOTE]
> Office 365 のコンテンツは、 [Office.com](https://www.office.com) ドメインを使用して提供されていました。

組織の MSN.com ドメインへのアクセスが制限されている場合は、この [url](https://ntp.msn.com)へのアクセス権をユーザーに付与することを強くお勧めします。

MSN ドメインへのアクセスを有効にするために、さらに時間が必要な場合は、[NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)を使用して、新しいタブページにMicrosoft ニュースまたは Office 365 のフィードのいずれかを選択できるようにすることをお勧めします。

### Office.com の使用を続ける

 **NewTabPageSetFeedType**ポリシーを構成して、非推奨のOffice.com ドメインを引き続き使用できます。

> [!IMPORTANT]
> Microsoft Edge バージョン90がリリースされると、 **NewTabPageSetFeedType** ポリシーと、Office 365 のコンテンツに対応する Office.com ドメインは動作を停止します。

次のポリシー設定では、Enterpriseの新しいタブページで、Office.com ドメインからのOffice ドキュメントのコンテンツが 強制的に表示されます。

- ポリシーを**必須**として設定します。
- ポリシーマッピングの値を **Office (1) = Office 365 フィードエクスペリエンス **に設定します。

Office.com に切り替えることができない場合は、お問い合わせください。 もう1つのオプションは、組織で許可されているエンドポイント URL をポイントするように、 [NewTabPageLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation)を構成することです。

> [!NOTE]
> **NewTabPageSetFeedType**ポリシーも構成されている場合は、**NewTabPageLocation** ポリシーが優先されます。

## マイフィードを使用して、エンタープライズユーザーが Microsoft ニュースコンテンツを取得できるようになります

[エンタープライズ新規] タブページでは、Azure Active Directory (Azure AD) アカウントでサインインしているユーザーのために、**マイフィード** と Office 365 のコンテンツ で一目で見られるように業界関連の情報を表示します。 Azure Active Directory (Azure AD) を使ってサインインしているユーザーで、[設定] ポップアップで [Microsoft ニュース] オプションを選択した場合は、新しいタブページビューが**マイフィード**の コンテンツに 置き換えられます。 ブラウザーで新しいタブページを開くと、次のスクリーンショットの例のようになります。

![[マイフィードのコンテンツを表示する新しいタブページ]。](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-myfeed-view.png)

> [!NOTE]
> Azure AD でサインインしていないユーザーは、新しいタブを開いたときに引き続き MSN ニュースフィードが表示されます。

## ページのレイアウト

新しいタブページが変更されたため、ページレイアウトでは、2つの特定のコンテンツタイプ (Office 365 と Microsoft ニュース) を制御する必要がなくなりました。したがって、コンテンツの切り替えが使用できません。 次のスクリーンショットは、ページレイアウトのポップアップを示しています。

![新しいタブページ用のページレイアウトビュー。](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-page-layout.png)

組織に関連付けられていない Microsoft ニュースコンテンツに引き続きアクセスするには、別のブラウザープロファイルを使用する必要があります。 *edge://settings/profiles* に移動して、Azure AD プロファイルからサインアウトします。 この操作を行うと、[Enterprise新規] タブページの標準ビューが表示されます。 

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Internet Explorer 11 のエンタープライズ モード](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
