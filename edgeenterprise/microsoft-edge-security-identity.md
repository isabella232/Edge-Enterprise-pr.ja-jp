---
title: Microsoft Edge の ID サポートと構成
ms.author: avvaid
author: dan-wesley
manager: srugh
ms.date: 12/08/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge の ID サポートと構成
ms.openlocfilehash: e553174fa40cb60046e5a46af4d81a0787957a93
ms.sourcegitcommit: b3f8ef9e4944efa3be15c7bfc0cd13360a350c1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2020
ms.locfileid: "11201294"
---
# Microsoft Edge の ID サポートと構成

この記事では、Microsoft Edge で ID を使用して、同期やシングル サインオン (SSO) などの機能がどのようにサポートされているかについて説明します。 Microsoft Edge では、Active Directory Domain Services (AD DS)、Azure Active Directory (Azure AD)、および Microsoft アカウント (MSA) を使用したサインインがサポートされています。 現在、Microsoft Edge は、グローバル クラウドまたは GCC ソブリン クラウドに属している Azure Active Directory (Azure AD) アカウントのみをサポートしています。 他のソブリン クラウドのサポートを追加しています。 

> [!NOTE]
> これは、Microsoft Edge version 77 以降に適用されます。

## ブラウザーのサインインと認証された機能

Microsoft Edge は、Azure AD、MSA、またはドメイン アカウントを使用したブラウザー プロファイルへのサインインをサポートしています。 サインインに使用するアカウントの種類によって、Microsoft Edge でユーザーが使用できる認証済みの機能が決定されます。 次の表は、各アカウントの種類ごとに、機能のサポートをまとめたものです。

|    | Azure AD Premium | Azure AD Free | 組織内の AD DS | MSA     |
|----|------------------|---------------|----------------|---------|
| 同期 | あり | × | いいえ | あり |
| プライマリ更新トークンによる SSO | あり | あり | いいえ | あり |
| シームレス SSO | あり | あり | ○ | 該当せず |
| 統合 Windows 認証 | あり | あり | ○ | 該当せず |
| Enterprise [新しいタブ] ページ | O365 が必要 |   O365 が必要 | なし | 該当せず |
| Microsoft Search | O365 が必要 | O365 が必要 | なし | 該当せず |

## ユーザーが Microsoft Edge にサインインする方法

### 自動サインイン

Microsoft Edge では、OS の既定のアカウントを使用してブラウザーに自動サインインします。 デバイスの構成方法によっては、ユーザーは次のいずれかの方法を使用して、Microsoft Edge に自動サインインできます。

- **デバイスはハイブリッド/AAD-J である:** Win10、下位レベルの Windows、および対応するサーバー バージョンで使用できます。
ユーザーは、その Azure AD アカウントで自動的にサインインします。
- **デバイスはドメインに参加している:** Win10、下位レベルの Windows、および対応するサーバー バージョンで使用できます。
既定では、ユーザーは自動的にサインインしません。 ドメイン アカウントを使用してユーザーを自動的にサインインさせる場合は、[ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/deployedge/microsoft-edge-policies#configureonpremisesaccountautosignin) ポリシーを使用します。 Azure AD アカウントを使用してユーザーを自動的にサインインさせる場合は、デバイスへのハイブリッド参加を検討してください。
- **OS の既定アカウントは MSA である:** Win10 RS3 (バージョン 1709/ビルド 10.0.16299) 以上です。 このシナリオは、エンタープライズ デバイスではほとんどありません。 ただし、OS の既定のアカウントが MSA の場合、Microsoft Edge は、MSA アカウントで自動的にサインインします。

### 手動サインイン

ユーザーが Microsoft Edge に自動的にサインインしない場合、最初の実行エクスペリエンス、ブラウザー設定、または ID フライアウトを開くことにより、ユーザーは Microsoft Edge に手動でサインインできます。 

### ブラウザーのサインインを管理する

ブラウザーのサインインを管理する場合は、次のポリシーを使用できます。

- ユーザーが Microsoft Edge に常に作業プロファイルを持っていることを確認します。 [NonRemovableProfileEnabled をご覧ください](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled)
- 信頼できる一連のアカウントにサインインを制限します。 [RestrictSigninToPattern をご覧ください](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern)
- ブラウザーのサインインを無効にするか強制します。 [BrowserSignin をご覧ください](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)

## ブラウザーから Web シングル サインオン (Web SSO)

一部のプラットフォームでは、ユーザーが Web サイトに自動的にサインインするように Microsoft Edge を構成できます。 このオプションにより、資格情報を再入力して仕事用の Web サイトにアクセスする手間が省け、生産性が向上します。

### プライマリ更新トークン (PRT) による SSO

Microsoft Edge は、PRT ベースの SSO をネイティブでサポートしており、拡張機能は必要ありません。 Windows 10 RS3 以降では、ユーザーがブラウザー プロファイルにサインインしている場合は、PRT ベースの SSO をサポートしている Web サイトに対して PRT メカニズムを使用して SSO を取得します。

プライマリ更新トークン (PRT) は、Windows 10、iOS、および Android デバイスの認証に使用される Azure AD キーです。 これにより、これらのデバイスで使用されるアプリケーション全体で、シングル サインオン (SSO) が有効になります。 詳しくは、「[プライマリ更新トークンとは](https://docs.microsoft.com/azure/active-directory/devices/concept-primary-refresh-token)」をご覧ください。

### シームレス SSO

Microsoft Edge は、PRT SSO と同様に、拡張機能を必要としないネイティブのシームレスな SSO をサポートします。 Windows 10 RS3 以降では、ユーザーがブラウザー プロファイルにサインインしている場合は、PRT ベースの SSO をサポートしている Web サイトに対して PRT メカニズムを使用して SSO を取得します。

企業ネットワークに接続されている企業のデバイスをユーザーが使用している場合、シームレス シングルサインオンではユーザーのサインインが自動的に行われます。 有効にすると、Azure AD にサインインするためにユーザーがパスワードを入力する必要がなくなります。 通常、ユーザー名を入力する必要はありません。 詳しくは、「[Azure Active Directory シームレス シングル サインオン](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)」をご覧ください。

### Windows 統合認証 (WIA)

Microsoft Edge は、認証にブラウザーを使用するすべてのアプリケーションに対する組織の内部ネットワーク内での認証要求に Windows 統合認証もサポートします。 これは、Windows 10 のすべてのバージョンと下位レベルの Windows でサポートされています。 既定では、Microsoft Edge は、WIA の許可リストとしてイントラネット ゾーンを使用します。 または、[AuthServerAllowlist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#authserverallowlist) ポリシーを使用して、統合認証が有効になっているサーバーのリストをカスタマイズできます。 macOS では、このポリシーは統合認証を有効にするために必要です。

Microsoft Edge (バージョン 77 以降) で WIA ベースの SSO をサポートするには、サーバー側構成の一部の実施が必要となることがあります。 新しい Microsoft Edge ユーザー エージェント文字列のサポートを追加するには、Active Directory フェデレーション サービス (AD FS) プロパティ **WiaSupportedUserAgents** の構成が必要となることがあります。 これを行う方法の手順については、[View WIASupportedUserAgent](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia#view-wiasupporteduseragent-settings) 設定および [Change WIASupportedUserAgent](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia#change-wiasupporteduseragent-settings) 設定をご覧ください。 Windows 10 での Microsoft Edge ユーザー エージェント文字列の例を以下に示します。[Microsoft Edge UA 文字列の詳細についてはこちらをご覧ください](https://docs.microsoft.com/microsoft-edge/web-platform/user-agent-string)。 

次に示す UA 文字列の例は、この記事の公開時点で最新の Dev チャネル ビルド用です。<br> `"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3951.0 Safari/537.36 Edg/80.0.334.2"`

ネゴシエート資格情報の委任が必要なサービスの場合、Microsoft Edge は [AuthNegotiateDelegateAllowlist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#authnegotiatedelegateallowlist) ポリシーを使用した制約付き委任をサポートします。

## 追加の認証の概念

### プロアクティブ認証

プロアクティブ認証は、ブラウザーから Web サイト SSO への最適化であり、特定のファーストパーティ Web サイトに認証をフロント ロードします。 これにより、ユーザーが検索エンジンとして Bing を使用している場合、アドレス バーのパフォーマンスが向上します。 これにより、ユーザーはカスタマイズされた Microsoft Search for Business (MSB) 検索結果を取得できます。 また、Office の新しいタブ ページなど、重要なサービスへの認証を許可します。 これは、[ProactiveAuthEnabled]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled) ポリシーを使用して制御できます。

### Windows Hello CredUI for NTLM 認証

Web サイトが NTLM またはネゴシエート メカニズムを使用してユーザーにサインインしようとしたときに SSO を利用できない場合、Microsoft は、Windows Hello Cred UI を使用して認証の課題を満たすために、OS の資格情報を Web サイトと共有できるエクスペリエンスをユーザーに提供します。 このサインイン フローは、NTLM またはネゴシエート チャレンジ中にシングルサインオンを取得できない Windows 10 のユーザーにのみ表示されます。

### 保存したパスワードを使用して自動的にサインインする

ユーザーが Microsoft Edge にパスワードを保存する場合は、資格情報を保存した Web サイトに自動的にログインする機能を有効にすることができます。 ユーザーは *edge://settings/passwords* に移動して、この機能を切り替えることができます。 この機能を構成する場合は、[パスワード マネージャー](https://docs.microsoft.com/deployedge/microsoft-edge-policies#password-manager-and-protection) ポリシーを使用できます。

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge ドキュメント ランディング ページ](https://docs.microsoft.com/DeployEdge/)
- [ID とアクセス管理](https://www.microsoft.com/security/technology/identity-access-management)
- [ID プラットフォーム](https://developer.microsoft.com/identity)
- [Azure Active Directory を使って強固な ID 基盤を構築するための 4 つのステップ](https://docs.microsoft.com/azure/active-directory/hybrid/four-steps)
