---
title: 企業で Microsoft Edge 拡張機能を管理する
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 企業で Microsoft Edge 拡張機能を管理する
ms.openlocfilehash: 26134a8c352354c0c447518120f3d79332100c80
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642923"
---
# <a name="manage-microsoft-edge-extensions-in-the-enterprise"></a>企業で Microsoft Edge 拡張機能を管理する

この記事は、組織で Microsoft Edge の拡張機能を管理する管理者向けのベスト プラクティス ガイダンスです。 この記事の内容を活用して、組織内での拡張機能を管理するための戦略を立てることができます。

> [!NOTE]
> この記事は Microsoft Edge バージョン 77 以降に適用されます。

## <a name="introduction"></a>はじめに

組織では、企業やユーザのデータを保護し、ブラウザー拡張機能を評価して、その安全性と企業への関連性を確認する必要があります。 管理者には、以下の内容が必要です。

- アプリや拡張機能がインストールされないようする。
- ユーザーが自分のジョブを行うために必要な拡張機能を保持する。
- ユーザーや企業のデータへのアクセスを管理する。  

この記事は、管理者が拡張機能を管理して、ユーザーに安全で生産的なエクスペリエンスを提供するためのシリーズの第一弾です。 このシリーズでは、さまざまなオプションを紹介し、拡張機能の管理に最適な方法を選択できるようにしています。 このシリーズは、以下の記事で構成されます。

- [企業で Microsoft Edge 拡張機能を管理する](microsoft-edge-manage-extensions.md)。 拡張機能を管理するための戦略を立て、ブラウザーの管理に必要な管理用テンプレートを設定します。
- [グループ ポリシーを使用して Microsoft Edge の拡張機能を管理する](microsoft-edge-manage-extensions-policies.md)。 グループ ポリシーを使用して拡張機能を管理するオプション。
- [Microsoft Edge 拡張機能をホストする Web ストアを作成する](microsoft-edge-manage-extensions-webstore.md)。 拡張機能を作成してホストします。
- [Microsoft Edge の拡張機能についての FAQ](microsoft-edge-manage-extensions-faq.md)。 よく寄せられる質問。

## <a name="things-to-consider-when-managing-extensions"></a>拡張機能を管理する場合の考慮事項

ユーザーがジョブを行うには、特定のアプリ、サイト、および拡張機能にアクセスする必要がありますが、同時にユーザーや企業データを保護する必要もあります。 効果的なセキュリティ戦略とは、企業にとって適切な質問をし、拡張機能が企業のニーズにどのように適合するかを考えることです。 そのためには、以下のような鍵となる質問をする必要があります。

- どのような規制やコンプライアンス対策を講じる必要がありますか?
- 拡張機能の中には、会社のデータ セキュリティ ポリシーに反する可能性のある、過度に広範な許可を求めるものがありますか?
- ユーザーや企業のデータは、ユーザーのデバイスにどれくらい保存されていますか?

これらの質問に答えていくと、Microsoft Edge が提供する以下の詳細なポリシーを利用できます。

- データ保護ポリシーに基づいて、ユーザーのコンピュータ上の拡張機能をブロックまたは許可します。
- ユーザーのデバイスに拡張機能を強制的にインストールすることで、ユーザーが生産性を高めるために必要なツールを利用できるようになります。
- Allowlist または Blocklist 拡張機能を使用して、ユーザーが作業を行うのに必要な最小限の権利を許可することができます。

拡張機能を管理する従来のモデルでは、特定の拡張機能に対して allowlist と blocklist のアプローチを使用します。 ただし、Microsoft Edge では、拡張機能に要求されるアクセス許可を管理することもできます。 このモデルを使用すると、コンピュータやデバイス上で拡張機能の使用を許可する権利やアクセス許可を決定し、要件に基づいて拡張機能を許可またはブロックするグローバル ポリシーを実装することができます。  

## <a name="understand-extension-permissions"></a>拡張機能のアクセス許可を理解する

拡張機能には、デバイスや Web ページを適切に動作させるための変更アクセス許可が必要になる場合があります。 このような権利はアクセス許可と呼ばれます。 開発者は、拡張機能にどのような権利やアクセス許可が必要か一覧表示する必要があります。 アクセス許可には大きく分けて 2 つのカテゴリがあり、多くの拡張機能では以下の両方のアクセス許可が必要です。

- ホスト アクセス許可では、拡張機能を表示または変更できる Web ページを一覧表示する必要があります。
- デバイス アクセス許可とは、拡張機能が実行されているデバイス上で拡張機能に必要な権利のことです。

これらのアクセス許可の例としては、USB ポートへのアクセス、ストレージや画面の表示、ネイティブ プログラムとの通信などがあります。  

## <a name="get-ready-to-manage-extensions"></a>拡張機能を管理するための準備

## <a name="before-you-begin"></a>始める前に

拡張機能オプションでは、ユーザーがすでに Microsoft Edge を管理していることが想定されています。 Microsoft Edge ポリシーの管理用テンプレートの設定については、以下を参照してください。

-   [Windows で Microsoft Edge ポリシー設定を構成する](/DeployEdge/configure-microsoft-edge)
-   [Intune で Windows 用に構成する](/mem/intune/configuration/administrative-templates-configure-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)
-   [モバイル デバイス管理で Windows 用に構成する](/deployedge/configure-edge-with-mdm)
-   [.plist を使用して macOS 用に構成する](/deployedge/configure-microsoft-edge-on-mac)
-   [Jamf を使用して macOS 用に構成する](/deployedge/configure-microsoft-edge-on-mac-jamf)

本記事の設定手順は Windows 向けです。MAC や Linux に対応する実装については、Microsoft Edge ブラウザーのポリシー リファレンスを参照してください。

## <a name="decide-which-extensions-to-allow"></a>許可する拡張機能を決める

ほとんどの組織では、アクセス許可やどの Web サイトにアクセスできるかによって拡張機能を管理する必要があります。 この方法は、より安全で、管理が容易であり、大規模な組織にもスケーラブルです。  

- ブロック済み/許可済みアクセス許可 - 必要なアクセス許可によって拡張機能を制御できます。
- ランタイム ブロック ホスト - これらの拡張機能がアクセスできる Web サイトを制御できます。

このアプローチでは、一度だけ設定すればいいので、時間の節約になります。 また、ランタイム ホスト ポリシーを使用して、最も重要なサイトが保護されます。その他のオプションは以下のとおりです。

-   強制インストール拡張機能 - 拡張機能を静かにインストールすることができます。
-   Allowlist/blocklist (必要な場合) - どのような拡張機能のインストールを許可するかを決定します。

以下の手順を使用して、組織内で許可する拡張機能を決定します。

1. 従業員のパソコンに必要な拡張機能の一覧を作成します。 テスト環境で拡張機能をテストし、社内アプリとの互換性の問題を診断します。
2. どのサイトをセキュリティで保護する必要があるかを選択します。

   - 拡張機能による変更やデータの読み取りをブロックする必要のある、社内の機密性の高い Web サイトやドメインを確認します。  
   - 拡張機能の実行時に API 呼び出しをブロックすることで、これらのサイトへのアクセスを防止します。 これには、Web 要求のブロック、Cookie の読み取り、JavaScript の取り込み、XHR などが含まれます。

3. これらの拡張機能を実行するために必要なアクセス許可を決定します。 どのアクセス許可がユーザーに潜在的なリスクをもたらすかを特定します。

   - ユーザーがインストールした拡張機能を監査し、どのようなアクセス許可が必要か確認します。 Web アプリのマニフェストの JSON ファイルは、拡張機能のコードで見ることができます。 以下の手順で、拡張機能に必要な権利を確認します。

     - 拡張機能を[Microsoft Edge アドオン](https://microsoftedge.microsoft.com/addons/) Web サイトまたは [Chrome Web ストア](https://chrome.google.com/webstore)でインストールします。
     - 拡張機能をテストして、組織でどのように機能するかを理解します。
     - *edge://extensions* に移動して、拡張機能が必要とするアクセス許可を確認します。 たとえば、次のスクリーンショットに表示されている Microsoft Office の拡張機能では、「閲覧履歴の読み取り」と「通知の表示」というアクセス許可を要求しています。 この拡張機能の有用性と要求されるアクセス許可のレベルを比較します。 組織のために拡張機能を承認した後、以下のツールを使用して拡張機能を管理します。
   :::image type="content" source="media/microsoft-edge-manage-extensions/manage-extesions-office-extension.png" alt-text="アクセス許可を含む Microsoft Office の拡張機能。":::

   - 組織内のユーザーが要求した拡張機能を、組織内で承認する前に検証することもできます。 拡張機能に使用するアクセス許可の中には、曖昧なものもあります。 ビジネスに不可欠なアプリの場合は、アプリの開発者や仕入先に直接連絡を取り、拡張機能に関する詳細情報を入手したり、ソース コードを見たりすることができます。 その拡張機能がデバイスや Web サイトに及ぼす変更点についても詳しく理解することが必要です。
   - 拡張機能が使用できるすべてのアクセス許可を一覧表示した「アクセス許可の宣言」リストを確認します。 このリストから、組織内で許可するアクセス許可を決めることができます。

4. 収集したデータからマスター リストを作成します。このリストには次の情報が含まれます。

   - **必要な拡張機能**。 このリストは、部署やオフィスの所在地など、関連する情報で整理することができます。
   - **拡張機能の「allowlist」**。 ブロックされていても実行が許可されるアクセス許可を含む必須の拡張機能です。 これらの拡張機能は、ユーザーが必要としているものや、仕入先と会話を通してリスクがないと判断されたものです。
   - **拡張機能の「blocklist」**。 インストールがブロックされる拡張機能です。 このリストの拡張機能には、実行が許可されないアクセス許可が含まれます。 また、セキュリティを確保し、拡張アクセスを許可しないコア サイトやドメインも含まれます。 後で、この blocklist と既存の blocklist を比較することができます。 現在の blocklist ポリシーを緩和できることを発見する可能性もあります。

5. このリストを関係者や IT チームに提示し、賛同を得ます。
6. 組織内のラボや小規模な試験運用で、新しいポリシーをテストします。
7. この新しいポリシーを段階的に社員に展開していきます。 詳細については、「[グループ ポリシーを使用して Microsoft Edge の拡張機能を管理する](microsoft-edge-manage-extensions-policies.md)」を参照してください。
8. ユーザーからのフィードバックを確認します。
9. このプロセスを毎月、四半期ごと、または毎年繰り返し、微調整していきます。

許可されたアクセス許可のベースラインが実施され、機密性の高い企業サイトが保護されることで、企業にさらなるセキュリティを提供すると同時に、ユーザーに優れたエクスペリエンスを提供することができます。 スタッフは、以前はインストールできなかった拡張機能をインストールする場合もありますが、機密性の高いビジネス サイトでは実行しません。  

## <a name="see-also"></a>関連項目

- [グループ ポリシーを使用して Microsoft Edge の拡張機能を管理する](microsoft-edge-manage-extensions-policies.md)
- [Microsoft Edge 拡張機能をホストする Web ストアを作成する](microsoft-edge-manage-extensions-webstore.md)
- [ExtensionSettings ポリシーのリファレンス ガイド](microsoft-edge-manage-extensions-ref-guide.md)
- [Microsoft Edge の拡張機能についてのよくある質問](microsoft-edge-manage-extensions-faq.md)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)