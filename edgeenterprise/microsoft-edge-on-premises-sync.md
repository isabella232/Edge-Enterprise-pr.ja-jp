---
title: Active Directory (AD) ユーザー用のオンプレミス同期
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 02/12/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Active Directory (AD) ユーザー用のオンプレミス同期
ms.openlocfilehash: 39d13a5d9d712ce2c086112c8de453562e037293
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617717"
---
# <a name="on-premises-sync-for-active-directory-ad-users"></a>Active Directory (AD) ユーザー用のオンプレミス同期

この記事では、Active Directory (AD) ユーザーが Microsoft クラウド サービスに接続することなく、Microsoft Edge のお気に入りや設定をコンピュータ間でローミングする方法について説明します。

> [!NOTE]
> この記事は Microsoft Edge version 85 以降に適用されます。

## <a name="introduction"></a>はじめに

Microsoft Edge でユーザー データを同期するには、通常 Microsoft アカウントか Azure Active Directory (Azure AD) アカウントのいずれかと、Microsoft クラウド サービスへの接続が必要です。 オンプレミス同期を利用すれば、Microsoft Edge で Active Directory ユーザーのお気に入りや設定をファイルに保存し、異なるコンピューター間で移動させることができます。 オンプレミス同期は、使用を許可しているプロファイルについてはクラウド同期の妨げにはなりません。

## <a name="how-it-works"></a>動作のしくみ

Microsoft Edge では、クラウド同期には使用できない Active Directory (AD) アカウントとプロファイルを関連付けることができます。オンプレミス同期を有効にすると、AD プロファイルのデータは profile.pb という名前のファイルに保存されます。 既定では、このファイルは *%APPDATA%/Microsoft/Edge* に保存されます。 このファイルが作成された後は、異なるコンピューター間で移動することができるようになり、ユーザー データはそれぞれのコンピューターで読み書きされます。 Microsoft Edge は、このファイルからの読み取りと書き込みのみを行います。必要に応じてファイルを移動させるのは管理者の責任となります。

## <a name="use-on-premises-sync"></a>オンプレミス同期を使用する

オンプレミス同期を使用するには、オンプレミス同期を有効にし、プロファイルを AD アカウントに関連付ける必要があり、オプションでユーザー データの場所を変更することもできます。

### <a name="enable-on-premises-sync"></a>オンプレミス同期を有効にする

Microsoft Edge でオンプレミス同期を有効にするには、[RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled) ポリシーを構成します。

### <a name="ensure-that-a-profile-is-associated-with-an-active-directory-account"></a>プロファイルが Active Directory アカウントに関連付けられていることを確認する

オンプレミス同期は、Active Directory (AD) アカウントに関連付けられているプロファイルでのみ機能します。 そういったプロファイルが存在しない場合には、オンプレミス同期は機能しません。 ユーザーが AD アカウントを使用してサインインできるようにするには、[ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin) ポリシーを構成します。 オンプレミスの同期の場合、Microsoft Edge はユーザー データの ID を確立するために AD にのみ依存します。Microsoft Edge がオンプレミスのデータの読み取りと書き込みを行う方法と、管理者が AD ユーザーのローミングを構成した方法との間に直接的な関係はありません。

### <a name="change-the-location-of-the-user-data-optional"></a>ユーザー データの場所を変更する (オプション)

既定では、ユーザー データは *%APPDATA%/Microsoft/Edge* の **profile.pb** という名前のファイルに保存されます。 このファイルの場所を変更するには、[RoamingProfileLocation](./microsoft-edge-policies.md#roamingprofilelocation) ポリシーを構成します。

## <a name="changes-in-the-user-experience-when-on-premises-sync-is-enabled"></a>オンプレミス同期が有効になっている場合のユーザー エクスペリエンスの変更

オンプレミス同期を有効にすると、ユーザーは同期を有効にするように要求されません。また、ユーザーは同期設定で同期をオフにすることができず、オンプレミス同期でサポートされていない同期の種類をオンにすることもできません。

## <a name="on-premises-sync-usage-notes"></a>オンプレミス同期の使用上の注意

### <a name="running-cloud-sync-and-on-premises-sync-on-the-same-computer"></a>クラウド同期とオンプレミス同期を同じコンピューター上で実行する

オンプレミス同期がクラウド同期の妨げになることはありません。Microsoft Edge にクラウドと同期している複数の Microsoft アカウントまたは Azure Active Directory プロファイルがある場合、オンプレミス同期が有効になっている間は、これらのプロファイルは引き続き同期されます。

### <a name="running-microsoft-edge-on-more-than-one-computer-at-a-time-isnt-recommended"></a>複数のコンピューターで Microsoft Edge を同時に実行することはお勧めできません

オンプレミス同期はユーザー データのファイルをコンピューター間で移動させることによって機能するため、オンプレミス同期では同時に実行される複数のセッションでの変更は同期されません。 この理由から、オンプレミス同期は一度に 1 台のコンピューター上で使用する場合に最適です。 オンプレミスのセッションが同時に実行される場合、次にブラウザー セッションを開始したときに、いずれかのコンピューター上のデータが他のコンピューター上のデータによって予期せず上書きされる場合があります。

> [!NOTE]
> オンプレミス同期が有効になっている場合、Microsoft Edge では **profile.pb** ファイルがロックされます。 フォルダー リダイレクトを使用して 1 つの **profile.pb** ファイルを異なるコンピューター間で共有する場合には、そのファイルを使用する Microsoft Edge インスタンスは 1 つのみが起動可能です。

### <a name="using-other-sync-policies-with-on-premises-sync"></a>オンプレミスの同期を使用したその他の同期ポリシーの使用

[SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) ポリシーを使用して、お気に入りや設定の同期を必要に応じて選択的に無効にすることができます。 [SyncDisabled](./microsoft-edge-policies.md#syncdisabled) ポリシーはオンプレミスの同期には影響を与えません。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge エンタープライズの同期](microsoft-edge-enterprise-sync.md)