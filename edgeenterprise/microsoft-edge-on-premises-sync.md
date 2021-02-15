---
title: Active Directory (AD) ユーザー用のオンプレミス同期
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 02/12/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Active Directory (AD) ユーザー用のオンプレミス同期
ms.openlocfilehash: adf0adc8370aa1e18d07d0d2e91727d1ac607bf1
ms.sourcegitcommit: 90b8eab62edbed0e0a84780abd7d3854bf95c130
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2021
ms.locfileid: "11328049"
---
# Active Directory (AD) ユーザー用のオンプレミス同期

この記事では、Active Directory (AD) ユーザーが Microsoft クラウド サービスに接続することなく、Microsoft Edge のお気に入りや設定をコンピュータ間でローミングする方法について説明します。

> [!NOTE]
> この記事は Microsoft Edge version 85 以降に適用されます。

## はじめに

Microsoft Edge でユーザー データを同期するには、通常 Microsoft アカウントか Azure Active Directory (Azure AD) アカウントのいずれかと、Microsoft クラウド サービスへの接続が必要です。 オンプレミス同期を利用すれば、Microsoft Edge で Active Directory ユーザーのお気に入りや設定をファイルに保存し、異なるコンピューター間で移動させることができます。 オンプレミス同期は、使用を許可しているプロファイルについてはクラウド同期の妨げにはなりません。

## 動作のしくみ

Microsoft Edge では、クラウド同期には使用できない Active Directory (AD) アカウントとプロファイルを関連付けることができます。オンプレミス同期を有効にすると、AD プロファイルのデータは profile.pb という名前のファイルに保存されます。 既定では、このファイルは *%APPDATA%/Microsoft/Edge* に保存されます。 このファイルが作成された後は、異なるコンピューター間で移動することができるようになり、ユーザー データはそれぞれのコンピューターで読み書きされます。 Microsoft Edge は、このファイルからの読み取りと書き込みのみを行います。必要に応じてファイルを移動させるのは管理者の責任となります。

## オンプレミス同期を使用する

オンプレミス同期を使用するには、オンプレミス同期を有効にし、プロファイルを AD アカウントに関連付ける必要があり、オプションでユーザー データの場所を変更することもできます。

### オンプレミス同期を有効にする

Microsoft Edge でオンプレミス同期を有効にするには、[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled) ポリシーを構成します。

### プロファイルが Active Directory アカウントに関連付けられていることを確認する

オンプレミス同期は、Active Directory (AD) アカウントに関連付けられているプロファイルでのみ機能します。 そういったプロファイルが存在しない場合には、オンプレミス同期は機能しません。 ユーザーが AD アカウントを使用してサインインできるようにするには、[ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin) ポリシーを構成します。 オンプレミスの同期の場合、Microsoft Edge はユーザー データの ID を確立するために AD にのみ依存します。Microsoft Edge がオンプレミスのデータの読み取りと書き込みを行う方法と、管理者が AD ユーザーのローミングを構成した方法との間に直接的な関係はありません。

### ユーザー データの場所を変更する (オプション)

既定では、ユーザー データは *%APPDATA%/Microsoft/Edge* の **profile.pb** という名前のファイルに保存されます。 このファイルの場所を変更するには、[RoamingProfileLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilelocation) ポリシーを構成します。

## オンプレミス同期が有効になっている場合のユーザー エクスペリエンスの変更

オンプレミス同期を有効にすると、ユーザーは同期を有効にするように要求されません。また、ユーザーは同期設定で同期をオフにすることができず、オンプレミス同期でサポートされていない同期の種類をオンにすることもできません。

## オンプレミス同期の使用上の注意

### クラウド同期とオンプレミス同期を同じコンピューター上で実行する

オンプレミス同期がクラウド同期の妨げになることはありません。Microsoft Edge にクラウドと同期している複数の Microsoft アカウントまたは Azure Active Directory プロファイルがある場合、オンプレミス同期が有効になっている間は、これらのプロファイルは引き続き同期されます。

### 複数のコンピューターで Microsoft Edge を同時に実行することはお勧めできません

オンプレミス同期はユーザー データのファイルをコンピューター間で移動させることによって機能するため、オンプレミス同期では同時に実行される複数のセッションでの変更は同期されません。 この理由から、オンプレミス同期は一度に 1 台のコンピューター上で使用する場合に最適です。 オンプレミスのセッションが同時に実行される場合、次にブラウザー セッションを開始したときに、いずれかのコンピューター上のデータが他のコンピューター上のデータによって予期せず上書きされる場合があります。

> [!NOTE]
> オンプレミス同期が有効になっている場合、Microsoft Edge では **profile.pb** ファイルがロックされます。 フォルダー リダイレクトを使用して 1 つの **profile.pb** ファイルを異なるコンピューター間で共有する場合には、そのファイルを使用する Microsoft Edge インスタンスは 1 つのみが起動可能です。

### オンプレミスの同期を使用したその他の同期ポリシーの使用

[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) ポリシーを使用して、お気に入りや設定の同期を必要に応じて選択的に無効にすることができます。 [SyncDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#syncdisabled) ポリシーはオンプレミスの同期には影響を与えません。

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge エンタープライズの同期](microsoft-edge-enterprise-sync.md)
