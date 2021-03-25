---
title: Windows 情報保護のための Microsoft Edge のサポート
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 04/24/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Windows 情報保護のための Microsoft Edge のサポート
ms.openlocfilehash: a9981947462627ae4884f18f4df6accf2ee60f12
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447191"
---
# <a name="microsoft-edge-support-for-windows-information-protection-wip"></a>Windows 情報保護 (WIP) のための Microsoft Edge のサポート

この記事では、Microsoft Edge が Windows 情報保護 (WIP) をサポートする方法をについて説明します。

> [!NOTE]
> これは、Microsoft Edge version 81 以降に適用されます。

## <a name="overview"></a>概要

Windows 情報保護 (WIP) は Windows 10 の機能で、不正または偶発的な漏洩から企業データを保護するのに役立ちます。 リモート ワークの台頭により、企業のデータを職場外で共有するリスクが高まっています。 このリスクは、個人の活動や仕事による活動が企業のデバイス上で発生した場合に増加します。

Microsoft Edge は、ユーザーがコンテンツを共有し、配信することが多い Web 環境でのコンテンツ保護を支援するために、WIP をサポートしています。

### <a name="system-requirements"></a>システム要件

企業内で WIP を使用するデバイスには、以下の要件が適用されます。

- Windows 10 バージョン 1607 以降
- Windows クライアント SKU のみ
- [WIP の前提条件](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#prerequisites)に記載されている管理ソリューションのいずれか

### <a name="windows-information-protection-benefits"></a>Windows 情報保護のメリット

WIP には、次の利点があります。

- 個人と企業データが明確に分離されるため、従業員が環境またはアプリを切り替える必要はありません。
- アプリを更新することなく、既存の基幹業務アプリのデータ保護が強化されます。
- Intune Mobile Device Management (MDM) に登録されたデバイスから企業データをリモート ワイプし、個人データに影響を与えないようにします。 
- 監査レポートを通して問題の追跡や、ユーザーへのコンプライアンス トレーニングなどの改善措置を行います。
- 既存の管理システムとの統合により、WIP の構成、展開、管理を行うことができます。 いくつかの例としては、Microsoft Intune、Microsoft Endpoint Configuration Manager、または現在ご利用のモバイル デバイス管理 (MDM) システムがあります。

## <a name="wip-policy-and-protection-modes"></a>WIP ポリシーと保護モード

ポリシーを使用して、次の表で説明されている 4 つの保護モードを構成できます。 詳細については、「[WIP 保護モード](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#wip-protection-modes)」を参照してください。

| モード | 説明 |
|------|-------------|
| ブロック | WIP によって不適切なデータ共有操作が検出され、従業員がその操作を完了することは禁止されます。 この検索では、アプリ間での企業データの共有や、組織のネットワーク外部との共有の実行に加え、企業で保護されていないアプリとの企業データの共有も対象となります。 |
| 上書きの許可 | WIP によって不適切なデータ共有が検出され、危険と見なされる操作を従業員が実行しようとすると警告が表示されます。 ただし、この管理モードでは、従業員はポリシーを上書きしてデータを共有でき、従業員が行った操作が監査ログに記録されます。 |
| Silent | WIP がメッセージを表示せずに実行され、上書きの許可モードであれば従業員による対話操作を要求する操作を一切禁止せずに、不適切なデータ共有をログに記録します。 ネットワーク リソースや WIP で保護されたデータにアプリから不適切にアクセスしようとした場合など、許可されていない操作は引き続き禁止されます。 |
| オフ | WIP がオフになり、データの保護や監査は行われません。 WIP を無効にすると、ローカルで接続されたドライブ上にある WIP タグの付いたファイルに対して暗号化の解除が試みられます。 WIP 保護を再び有効にしても、以前の復号化とポリシーの情報は自動的には再適用されません。
 |

## <a name="wip-features-supported-in-microsoft-edge"></a>Microsoft Edge でサポートされている WIP の機能

Microsoft Edge バージョン 81 以降では、次の機能がサポートされています。

- ワーク サイトは、アドレス バーに表示されたブリーフケースのアイコンで示されます。  
- 作業場所からダウンロードされたファイルは自動的に暗号化されます。
- 作業場所以外の場所への仕事用ファイルのアップロードには、サイレント、ブロック、上書きが強制適用されます。  
- ファイルのドラッグ アンド ドロップ操作には、サイレント、ブロック、上書きが強制適用されます。
- クリップボード操作には、サイレント、ブロック、上書きが強制適用されます。
- 仕事用プロファイル以外のプロファイルからの作業場所の閲覧は、自動的に仕事用プロファイルへとリダイレクトされます (Azure AD の ID に関連付けられています)。
- IE モードは、WIP 機能を完全にサポートしています。

## <a name="working-with-wip-in-microsoft-edge"></a>Microsoft Edge での WIP の使用

Microsoft Edge で WIP サポートが有効になると、ユーザーが仕事関連の情報にアクセスしたときに表示されるようになります。 次のスクリーンショットでは、アドレス バーにブリーフケースのアイコンが表示されており、ブラウザ経由で仕事関連の情報にアクセスしていることを示しています。

 !["仕事" としてマークされているサイトのアドレス バー インジケーター](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-notify.png)

Microsoft Edge では、未承認のウェブサイトの保護されたコンテンツを共有する機能をユーザーに提供しています。 次のスクリーンショットは、保護されたコンテンツを未承認のウェブサイトで使用できるようにする Microsoft Edge のプロンプトを示しています。

 ![保護されたコンテンツの上書きを要求する](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-override.png)

## <a name="configure-policies-to-support-wip"></a>WIP をサポートするようにポリシーを構成する

Microsoft Edge で WIP を使用するには、仕事用プロファイルが必要です。

### <a name="ensure-the-presence-of-a-work-profile"></a>仕事用プロファイルの存在を確認する

ハイブリッドに参加しているコンピューターでは、Microsoft Edge は Azure Active Directory (Azure AD) アカウントで自動的にサインインされます。 WIP に必要なこのプロファイルをユーザーが削除しないようにするために、次のポリシーを構成します。

- [NonRemovableProfileEnabled](./microsoft-edge-policies.md#nonremovableprofileenabled)

> [!NOTE]
> ハイブリッドに参加していない環境でご利用の場合は、「[Plan your hybrid Azure Active Directory join implementation (ハイブリッド Azure Active Directory への参加の実装を計画する)](/azure/active-directory/devices/hybrid-azuread-join-plan)」の手順を使用してハイブリッドに参加することができます。

ハイブリッド参加がオプションではない場合は、オンプレミスの Active Directory アカウントを使用して、Microsoft Edge がユーザーのドメイン アカウントを使用して特別な仕事用プロファイルを自動的に作成できるようにすることができます。 オンプレミス アカウントでは、クラウド同期、Office NTP など、Azure AD の機能のすべてを受け取ることが不可能な場合があることに注意してください。

#### <a name="active-directory-ad-accounts"></a>Active Directory (AD) アカウント

AD アカウントの場合、Microsoft Edge に特別な仕事用プロファイルを自動作成させるには、次のポリシーを構成する必要があります。

- [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin)

### <a name="windows-policies-for-wip"></a>WIP のための Windows ポリシー

Windows ポリシーを使用して、WIP を構成することができます。 詳細については、「[Create and deploy WIP policies using Microsoft Intune (Microsoft Intune を使用して WIP ポリシーを作成して展開する)](/windows/security/information-protection/windows-information-protection/overview-create-wip-policy)」を参照してください。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="how-do-i-resolve-error-code--2147024540"></a>エラー コード -2147024540 の解決方法を教えてください

このエラーコードは、次の Windows 情報保護エラーに対応しています: *ERROR_EDP_POLICY_DENIES_OPERATION: 要求された操作は Windows 情報保護ポリシーによってブロックされました。詳細については、システム管理者に問い合わせてください。*

組織で Windows 情報保護 (WIP) が有効になっており、承認されたアプリケーションを使用するユーザーのみに企業リソースへのアクセスが許可されている場合に、Microsoft Edge によってこのエラーが示されます。 この場合、承認されたアプリケーションの一覧に Microsoft Edge がないため、管理者は Microsoft Edge へのアクセスが許可されるように WIP ポリシーを更新する必要があります。

次のスクリーンショットは、Microsoft Intune を使用して Microsoft Edge を許可された WIP 用アプリとして追加するための方法を示しています。

 ![Microsoft Intune のダイアログで、Microsoft Edge を WIP 用アプリとして追加します。](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-exemption.png)

Microsoft Intune を使用していない場合は、[WIP Enterprise AppLocker Policy](https://download.microsoft.com/download/8/9/9/8995d820-065c-4ab1-aa2a-9d6dc0cd7ffa/MsEdge%20-%20WIP%20Enterprise%20AppLocker%20Policy%20Files.zip) ファイルに含まれているポリシー更新をダウンロードして適用してください。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise) 
- [Windows 情報保護を使用して企業データを保護する](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)