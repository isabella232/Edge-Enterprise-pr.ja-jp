---
title: Microsoft Edge チャネル概要
ms.author: srugh
author: RyanHechtMSFT
manager: seanlynd
ms.date: 09/23/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge チャネル概要
ms.openlocfilehash: dd65d932950be90d3d9278fa41ae843335b2074d
ms.sourcegitcommit: 8e5294e82cf62abc916cfd24692f55925330d42b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "12037190"
---
# <a name="overview-of-the-microsoft-edge-channels"></a>Microsoft Edge チャネルの概要

次のバージョンの Microsoft Edge の利点の 1 つは、Microsoft が定期的に新機能を提供できることです。 ただし、組織内のユーザーに Microsoft Edge を展開する管理者は、ユーザーがこれらの新機能を受け取る頻度を細かく制御できる方が良い場合があります。 Microsoft では、Microsoft Edge を新しい機能で更新する頻度を制御するために、チャネルと呼ばれる 4 つのオプションを提供しています。 ここでは、これら 4 つのオプションの概要を説明します。

各チャネルのサポートの詳細については、「[Microsoft Edge のライフサイクル](/deployedge/microsoft-edge-support-lifecycle)」を参照してください。
  
> [!NOTE]
> この記事は Microsoft Edge バージョン 77 以降に適用されます。

## <a name="channel-overview"></a>チャネルの概要

|チャネル|主な目的|新機能に更新される頻度|サポート|
|:---:|---|:---:|:---:|
|[Stable](#stable-channel)|広範な展開|~4 週間|○|
|[Extended Stable](#extended-stable-channel)|より長いリリース サイクルに合わせて安定したエンタープライズ リリース オプション |~8 週間|あり|
|[Beta](#beta-channel)|組織内での代表的な対象での検証|~4 週間|あり|
|[Dev](#dev-channel)|計画と開発|1 週間に 1 回|なし|
|[Canary](#canary-channel)|試験的な内容|毎日|なし|

どの更新チャネルをユーザーに展開するかは、ユーザーが利用する回線オブビジネス アプリケーションの数や、更新されたバージョンの Microsoft Edge がある場合はテストする必要があるなど、いくつかの要因によって異なります。 この決定を行うには、Microsoft Edge で利用可能な 4 つの更新チャネルに関する次の情報をご確認ください。

### <a name="stable-channel"></a>Stable チャネル

Stable チャネルは、組織での広範な展開を目的としており、ほとんどのユーザーに適したチャネルです。 チャネルの中で最も安定しており、以前のベータ チャネル リリースで使用できる機能セットの安定化の結果です。 新機能は約 4 週間ごとに提供されます。 必要に応じて、セキュリティ更新プログラムと品質更新プログラムがリリースされます。 Stable チャネルからのリリースは、チャネルからの次のリリースが利用可能になるまでサービスが提供されます。

### <a name="beta-channel"></a>Beta チャネル

Beta チャネルは、組織内の実稼働環境への展開を目的とし、代表的なユーザーのグループを対象としています。 これはサポートされているリリースであり、Beta からの各リリースは、このチャネルからの次のリリースが利用可能になるまでサービスが提供されます。 ご利用環境で想定どおりに動作するかどうかを検証するための絶好の機会であり、問題が発生した場合は、リリースが Stable チャネルに公開される前に報告することができます。 新機能は約 4 週間ごとに提供されます。 必要に応じて、セキュリティ更新プログラムと品質更新プログラムがリリースされます。

### <a name="dev-channel"></a>Dev チャネル

Dev チャネルは、Canary チャネルよりも高い品質で、Microsoft Edge の最新機能を計画および開発することを目的としています。 このチャネルでは、次の Beta リリースの前にいち早く新機能を確認し、準備できます。

### <a name="canary-channel"></a>Canary チャネル

Canary チャネルは毎日リリースされ、すべてのチャネル内でも最先端で試験的な内容です。 最新の投資にアクセスする場合は、最初にここに表示されます。 このケイデンスの性質上、問題は時間外に発生するため、Canary リリースを活用する場合は、別のチャネルを並べてインストールする必要があります。

### <a name="extended-stable-channel"></a>拡張された安定したチャネル

プレビュー チャネル (Canary、Dev、Beta) とは異なり、拡張安定チャネルは個別のブラウザー アプリケーションとして使用できません。代わりに、Microsoft Edge Stable アプリケーションのエンタープライズ リリース オプションで、より長い 8 週間のメジャー リリース サイクル (Stable で見つかった 4 週間のメジャー リリース サイクルとは対照的) に配置されます。 4 週間のリリース サイクルで Stable を自動的に更新することをお勧めしますが、Extended Stable は、新しいブラウザー バージョンのテストと検証に長いタイムラインが必要な組織により効果的にサービスを提供するために存在します。

Microsoft Edge Stable の 8 週間の "Extended Stable" リリース サイクル オプションは、Microsoft Edge __ 94 で始まる番号の付いたリリースに合わせて累積的な機能更新プログラムを提供します。奇数リリースからの機能更新プログラムは、以降の偶数番号リリースの一部としてパッケージ化され、配信されます。 たとえば、組織が Microsoft Edge 94 で 8 週間の "Extended Stable" リリース サイクルを選択した場合、Microsoft Edge 96、Microsoft Edge 98 などによる以降の機能更新プログラムを受け取ります。 機能更新プログラムは、選択したリリース サイクルに基づいて新しいバージョン リリースでパッケージ化および配信されますが、重要なセキュリティパッチと修正プログラムは、ブラウザーのセキュリティを維持するために、選択したリリース オプションとは関係無く、必要に応じて配信されます。 お客様は、いつでも拡張安定版リリース オプションを選択できます。また、次回の拡張安定版リリースでも有効になります。

![安定したリリース サイクルMicrosoft Edgeのリリース サイクル オプションを比較する例。](./media/microsoft-edge-channels/extended-stable-explainer.png)

#### <a name="opting-in-to-the-extended-stable-release-cadence"></a>拡張安定版リリースケイデンスへのオプトイン

##### <a name="opting-in-to-extended-stable-on-windows-with-automatic-updates-recommended"></a>自動更新プログラムを使用して、Windowsに拡張 Stable にオプトインする (推奨)

グループ ポリシーを自動的に更新Microsoft Edge、グループ ポリシー オブジェクトを使用して、拡張安定リリース ケイデンスにオプトインできます。 [最新のグループ ポリシー](/DeployEdge/configure-microsoft-edge#1-download-and-install-the-microsoft-edge-administrative-template)管理テンプレートのダウンロードとインストールの詳細については、Microsoft Edgeガイドに従います。

1. ローカル グループ ポリシー エディターを開き、 _[コンピューターの構成]、[管理用テンプレート]、[Microsoft Edge 更新プログラム]、[アプリケーション]、[Microsoft Edge]_ の順に移動します。
2. [ターゲット **チャネルの上書き] を** 選択し、[有効] **を選択します**。
3. [ **オプション]** で、[ポリシー] **ドロップダウン リストから [** 拡張安定] を選択します。

拡張安定チャネルの次の更新プログラムがリリースされ、デバイスが現在インストールされているバージョン番号よりも大きい場合、Microsoft Edge は拡張安定チャネルに自動的に更新されます。 バージョン文字列がオン `edge://settings/help` の場合は、別のチャネルを実行している場合を示します。

> [!NOTE]
> 拡張 Stable へのオプトインは、デバイスに現在インストールされているバージョン番号 (メジャーまたはマイナー) が大きい拡張 Stable チャネルに新しい更新プログラムがある場合に有効になります。 最新バージョンの Microsoft Edge Stable を実行し、Extended Stable にオプトインしている場合は、次の更新プログラムまたは更新プログラムMicrosoft Edge。
>
> 既定では、Microsoft Edgeダウングレードされません。 現在、奇数バージョンの Microsoft Edge Stable を実行している場合は、Extended Stable にオプトインすると、次の偶数番号の Microsoft Edge リリースまで更新プログラムは受け取りMicrosoft Edgeされます。
>
> すべてのデバイスが特定のバージョンの Extended Stable で起動する場合は、ロールバックが有効な MSI としてその特定のバージョンの Edge Stable を展開できます。 たとえば、Extended Stable 94 から開始するが、一部のデバイスが Stable 95 に既に更新されている場合は、ロールバックが有効になっているエッジ 94 の MSI を展開できます。 ロールバックが有効になっているエッジ MSIs を展開する方法の詳細については、ロールバック ガイドを [参照してください](/DeployEdge/edge-learnmore-rollback)。

##### <a name="opting-in-to-extended-stable-on-windows-via-intune"></a>Intune 経由でアプリで拡張安定Windowsオプトインする

Microsoft Edge管理用テンプレートは、管理センターのローカル グループ ポリシー オブジェクトと同様Microsoft エンドポイント マネージャー管理できます。 Intune を使用[したアプリの構成に関するMicrosoft Edgeに従います](/mem/intune/configuration/administrative-templates-configure-edge)。 

"ターゲット**チャネルの上書き**" 設定は、"Microsoft Edge Update >"サブフォルダー _>Microsoft Edge_で確認できます。 **"Extended Stable" に設定する必要があります**。 

拡張安定チャネルの次の更新プログラムがリリースされ、デバイスが現在インストールされているバージョン番号よりも大きい場合、Microsoft Edge は拡張安定チャネルに自動的に更新されます。 バージョン文字列がオン `edge://settings/help` の場合は、別のチャネルを実行している場合を示します。

##### <a name="opting-in-to-extended-stable-on-windows-via-configuration-manager"></a>Configuration Manager を介して、Windowsに拡張 Stable にオプトインする

Configuration Manager で更新プログラムを同期および承認するMicrosoft Edge詳細については[、Configuration Manager](/mem/configmgr/apps/deploy-use/deploy-edge#update-microsoft-edge)を使用した更新プログラムの更新に関するMicrosoft Edge参照してください。

拡張安定版の更新プログラムは、Stable チャネル、Beta チャネル、開発チャネルの既存の更新プログラムと同様に、"Microsoft Edge" 製品カテゴリの下のソフトウェア ライブラリに配布されます。 ただし、独自のブラウザー アプリケーションに適用される Beta や Dev とは異なり、拡張安定版の更新プログラムは、Microsoft Edgeアプリケーションに適用されます。 したがって、Windows Update クライアントが Stable または Extended Stable の更新プログラムを適用するかどうかを決定するために、"ターゲット チャネルオーバーライド" グループ ポリシーの状態を確認します。 ポリシーが構成されていない場合、または "Stable" に設定されている場合は、安定した更新プログラムが適用されます。 "Extended Stable" に設定されている場合は、拡張安定版の更新プログラムが適用されます。 グループ ポリシーを適切に設定する方法については、上記の手順に従って、自動更新を使用して拡張 Stable にオプトインします。 

## <a name="flighting-pre-release-channels-in-your-organization"></a>組織内でのプレリリース チャネルのフライト

"ターゲット チャネルオーバーライド" グループ ポリシーを使用すると、ユーザーが 2 つ目の Web ブラウザー アプリケーションを使用することなく、組織内の Microsoft Edge のプレリリース チャネルをシームレスにフライトすることもできます。 たとえば、組織内のユーザーの代表的なサンプル セットの "ターゲット チャネルオーバーライド" ポリシーを "Beta" に設定できます。 これらのユーザーは、Microsoft Edgeを開く際に、Stable ではなく Beta チャネル リリースを実行します (おそらく、それを実現する必要はなかったです)。 これにより、次のバージョンの Microsoft Edge が企業でどのように実行されるのかについて早期に把握し、環境内ですべてが期待通り動作する検証に役立ちます。 問題が発生したユーザーから早期のシグナルを受け取り、リリースが Stable チャネルに公開される前に修復される可能性があります。 ユーザーの問題のトラブルシューティングの一環として、at のバージョン文字列は、ユーザーのチャネルが既定の Stable チャネルと異なる `edge://settings/help` 場合に通知します。

> [!NOTE]
> Microsoft Edge の "Beta" チャネルと "Dev" チャネル上のビルドでは、メジャー バージョン番号が "Stable" よりも大きかったので、"Beta" または "Dev" チャネルに更新を行い、Stable に戻す場合は[、Microsoft Edge](/DeployEdge/edge-learnmore-rollback)のロールバック機能が必要になります。 "ターゲット チャネルオーバーライド" を Stable に戻すだけで、最新の Stable リリースが現在デバイスで実行している Microsoft Edge のバージョンよりも大きいバージョン番号になるまで、更新プログラムは受け取れなきます。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [チャネル ダウンロード](https://aka.ms/EdgeEnterprise)
