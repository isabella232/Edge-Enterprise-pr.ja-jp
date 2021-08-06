---
title: 仮想化デスクトップ インフラストラクチャのためのMicrosoft Edge
ms.author: anlake
author: AndreaLBarr
manager: collw
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 仮想化デスクトップ インフラストラクチャのためのMicrosoft Edge。
ms.openlocfilehash: dd9d2bec8cc8caa21149018b033b9bfb53ae7602f974b1152ba91ddbb7cdbab0
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "11724710"
---
# <a name="microsoft-edge-for-virtualized-desktop-infrastructure"></a>仮想化デスクトップ インフラストラクチャのためのMicrosoft Edge

この記事では、仮想化環境で Microsoft Edge を使用する場合の要件と制約について説明します。

## <a name="what-is-vdi"></a>VDI とは?

仮想デスクトップ インフラストラクチャ (VDI) は、デスクトップ オペレーティング システムとアプリケーションをデータ センターの一元的なサーバー上でホストする仮想化テクノロジです。 これにより、完全にセキュリティで保護され、法令準拠した一元化されたソースを持つユーザーに対して、完全にカスタマイズされたデスクトップ エクスペリエンスを実現できます。

Microsoft Edge は、ローカル デバイスで使用できるのと同じ方法で、このような仮想化環境で使用できます。セキュリティで保護された制御されたサーバー環境から実行されます。 選択した VDI ソリューションによっては、イントラネット アプリケーションとサイトへのシームレスなアクセスをユーザーに提供することもできます。

Edge のほとんどの機能は、特別な構成なしで VDI 環境でサポートされます。 ただし、最適なエクスペリエンスを実現するには、以下のガイダンスに従ってください。

## <a name="platforms-certified-for-edge"></a>Edge の認定プラットフォーム

- Azure 仮想デスクトップ
- Citrix 仮想アプリとデスクトップ (旧称:XenApp および XenDesktop)

他の VDI ソリューションはまだ Edge チームによって検証されていませんが、Edge で最も一般的なワークフローをサポートすることが期待されています。 以下に示すガイダンスは、選択したソリューションに適用される場合と適用できない場合があります。

## <a name="edge-on-vdi-performance-considerations"></a>VDI 上の Edge のパフォーマンスに関する考慮事項

VDI 環境を設計する場合は、最適なパフォーマンスの達成のため、サーバー構成による制限も考慮して、ユーザーのワークフローとニーズを慎重に検討する必要があります。

Edge を VDI 環境に展開するには、以下の最小限の要件をお勧めします。

- vCPU – ユーザーごとに 2 から 4 のコア
- RAM – ユーザーあたり 1 GB

大規模な複雑な Web アプリケーションと拡張機能では、より多くのメモリが必要であり、環境を構成するときに考慮する必要があります。

## <a name="edge-on-non-persisted-vdi-environments"></a>非永続的 VDI 環境の Edge

多くの VDI ソリューションでは、セッション間で保持される仮想環境と、ユーザーが複数の利用可能なコンピューターの 1 つ (セッションごとに異なるコンピューターに割り当てられている可能性がある) にユーザーが割り当てられている、保持されない環境へのアクセスを許可しています。ユーザー データはセッション間で同期する場合と同期しない場合があります。

非永続的環境を使用する場合、通常、必要なアプリと構成を含む各デバイスに使用される "ゴールデン イメージ" が作成されます。 次に、このような画像の Edge を準備するための推奨事項を示します。

### <a name="deploy-edge"></a>Edge の展開

Windows 10 のバージョン 1803 以上を使用している場合は、システムに Microsoft Edge がインストールされているはずです。 ただし、 Windows の以前のバージョンを使用している場合や、Edge の異なるチャネルを展開する必要がある場合は、次の手順をお勧めします。

1. VDI VM オペレーティング システムに一致するEdge MSI パッケージを次からダウンロードします。

    - [Microsoft Edge for Business のダウンロード - Microsoft](https://www.microsoft.com/edge/business/download)

2. 次のコマンドを実行して、MSI を VDI VM にインストールします。

    - `msiexec /i <path_to_msi> /qn /norestart /l*v <install_logfile_name>`

### <a name="disable-automatic-updates"></a>自動更新を無効にする

非永続的なコンピューターの場合は、自動更新プログラムを無効にし、代わりに "ゴールデン イメージ" を更新してエッジを更新して、多数のコンピューターの中でバージョンの不一致が発生しないようにすることがベス トプラクティスです。

自動更新を無効にする場合は、次のポリシーを参照してください。

- [更新ポリシーのオーバーライド規定](/deployedge/microsoft-edge-update-policies#updatedefault)

- [更新ポリシーのオーバーライド](/deployedge/microsoft-edge-update-policies#update)

### <a name="profile-management"></a>プロファイル管理

永続的なセットアップでは、VM がセッション間でユーザー状態を維持しない可能性がある場合や、使用したことがない VM がユーザーに割り当てられ、ユーザー データは一切含まれていない可能性があることを考慮することが重要です。

Edge へのアクセス方法に関係なく、Edge では、ユーザー データを同期する複数の方法をサポートしており、ユーザー データは使用可能です。

### <a name="azure-ad-sync"></a>Azure AD Sync

Azure AD プランでサポートされている場合は、Enterprise 同期が、最も高速かつ簡単に、Edge ユーザー データをすべてのユーザー デバイスに同期する方法です。  

要件と構成の詳細については、以下を参照してください。  

- [Microsoft Edge エンタープライズ同期の構成|Microsoft Docs](/deployedge/microsoft-edge-enterprise-sync)

### <a name="on-premise-sync-for-active-directory-users"></a>Active Directory ユーザーのオンプレミス同期

オンプレミス同期を使用すると Microsoft Edge Active Directory ユーザーのお気に入りや設定をファイルに保存し、異なるコンピューター間で簡単に移動することができます。  

要件と構成の詳細については、以下を参照してください。  

- [Active Directory (AD) ユーザーのオンプレミス同期|Microsoft Docs](/deployedge/microsoft-edge-on-premises-sync)

### <a name="user-profile-redirection"></a>ユーザー プロファイルのリダイレクト  

このような非永続的環境でユーザー コンテキストを維持するために、ユーザー フォルダー全体を移行およびリダイレクトするためのいくつかのソリューションがあります。 推奨されるソリューションを確認するには、VDI プロバイダーに確認してください。

一般的なソリューションには、次のものがあります。

- [FSLogix の概要 - FSLogix |Microsoft Docs](/fslogix/overview)
- [Citrix プロファイル管理を構成する方法](https://support.citrix.com/article/CTX222893)

また、この方法を使用する場合は、ユーザーがコンピューターにログオンし、プロファイルを移行する際の初期読み込み時間を短縮するために、バックアップされたユーザー フォルダーから不要なフォルダーを除外することが推奨されます。 その場合は、サイズを小さくするために、バックアップから次のフォルダーを除外することをお勧めします。

- %LocalAppData%\Microsoft\Edge\User Data\Default\Cache
- %%LocalAppData%\Microsoft\Edge\User Data\Default\Code Cache
- %LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsTopSites
- %LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsRecentClosed

## <a name="known-issues"></a>既知の問題

### <a name="microsoft-edge-crashes-in-older-versions-of-xenapp-and-xendesktop"></a>XenApp と XenDesktop の以前のバージョンで で Microsoft Edge がクラッシュする

この問題は新しいバージョンで軽減される必要があります。ただし、お使いの環境でこの問題が発生した場合は、Citrix API Hooks for Edge を無効にして問題を回避できます。「アプリケーションごとに[Citrix API Hooks](https://support.citrix.com/article/CTX107825)を無効にする方法」を参照してください。

### <a name="degraded-performance-when-rendering-pages-with-exceptionally-large-html-tables"></a>非常に大きな HTML テーブルを使用してページをレンダリングする場合のパフォーマンスの低下

次の Citrix ポリシーは、非常に大きい (30,000 行以上の行数) テーブルを持つ HTML ページのレンダリングを遅くすることが知られています。

- キーボードの自動表示
- コンボ ボックスをリモートで操作する

詳細 [については、「モバイル エクスペリエンス ポリシー設定 (citrix.com)」](https://docs.citrix.com/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/mobile-experience-policy-settings.html) を参照してください。 これらのポリシーを無効にすると、問題が軽減されます。

### <a name="windows-account-manager-authorization-scenarios-ie--azure-sync-fail-in-edge-when-run-as-a-citrix-seamless-application"></a>Windows アカウント マネージャーの承認シナリオ (つまり、 Azure 同期) は、Citrix シームレス アプリケーションとして実行すると Edge で機能しません

これは、"シームレス" モードで実行するときに初期化されないようにするシナリオに必要な Windows コンポーネントが原因で WAM (Office) を使用する Edge および他のアプリケーションで既知の問題です。 この問題を回避するには、次の作業を行います。

- シームレスなリモート アプリケーションとしてではなく、リモート デスクトップ経由で Edge を Citrix ホストに使用します。
- 代わりに Azure 仮想デスクトップ リモート アプリを使用します。この問題の軽減策になります。
