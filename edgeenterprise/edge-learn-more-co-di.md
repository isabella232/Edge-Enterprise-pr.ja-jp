---
title: Microsoft Edge で ClickOnce と DirectInvoke を使用する
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge での ClickOnce と DirectInvoke の使用について説明します。
ms.openlocfilehash: 3d124f141e9212ba5ab25d4b725d32add62077a3
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642053"
---
# <a name="understand-the-clickonce-and-directinvoke-features-in-microsoft-edge"></a>Microsoft Edge での ClickOnce と DirectInvoke の機能について

ClickOnce と DirectInvoke は、IE および Microsoft Edge (version 45 以前) で利用可能な機能で、Web サイトからファイルをダウンロードするためのファイル ハンドラーの使用をサポートします。 この 2 つの機能は異なる目的で使用されますが、どちらの場合も Web サイトでは、ダウンロードが要求されたファイルをユーザー デバイス上のファイル ハンドラーに渡すことを指定できます。 ClickOnce 要求は、Windows のネイティブ ファイル ハンドラーによって処理されます。 DirectInvoke 要求は、ファイルをホストしている Web サイトで指定された登録済みのファイル ハンドラーによって処理されます。

これらの機能について詳しくは、以下をご覧ください。

- [ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment?view=vs-2019)
- [DirectInvoke]( https://technet.microsoft.com/learning/jj215788(v=vs.94).aspx)

> [!NOTE]
> 現時点では、ClickOnce または DirectInvoke のネイティブ サポートが Chromium では提供されていません。

## <a name="overview-prerequisites-and-process"></a>概要: 前提条件とプロセス

ClickOnce および DirectInvoke が設計どおりに動作し、ファイル ハンドラーへの要求が正しく行われるためには、ClickOnce または DirectInvoke をサポートするように、ファイル ハンドラーをオペレーティング システムに登録しておく必要があります。 この登録は通常、元のオペレーティング システムのインストール時か、インストールされた新しいプログラムが更新のために DirectInvoke を使用できるように要求した場合に行われます。

ClickOnce または DirectInvoke を必要とするダウンロード要求を Web サイトが受け取ると、次の処理が行われます。

- Web サイトは、指定されたファイル ハンドラーを使用するようにブラウザーに要求します。
- ブラウザーは、オペレーティング システムのレジストリをチェックして、要求されたファイルの種類に対してファイル ハンドラーが登録されているかどうかを確認します。
- ファイル ハンドラーが登録されている場合、ブラウザーはファイル ハンドラーを呼び出し、引数として URL をファイル ハンドラーに渡します。
- ファイル ハンドラーによって URL が処理され、ファイルがダウンロードされます。

  > [!NOTE]
  > URL は、ファイルのソースと、ファイルへのアクセス時に使用するパラメーターを決定するために使用されます。  パラメーターには、エンドポイント、マニフェスト、メタデータなどがあります。

## <a name="use-cases"></a>使用例

次に、代表的な使用例を示します。

ClickOnce を使用すると、最小限のユーザー操作で、デバイス上のソフトウェアを簡単に展開し、更新できます。 ユーザーは、Web ページ内のリンクをクリックして、Windows アプリケーションをインストールして実行できます。 正しく構成されていれば、ClickOnce アプリケーションは、ユーザーがインストーラー用に構成を設定しなくてもプログラムをインストールできます。 たとえば、ファイルの場所、インストールするオプションなどです。

DirectInvoke の使用方法は、DirectInvoke を要求している Web サイトの目的によって異なります。 例として、Microsoft Word での共同作業によるファイル編集機能があります。 リンクをクリックして同僚と一緒に作業中のドキュメントのコピー全体をダウンロードする代わりに、DirectInvoke を使用すると、ドキュメントのうち、変更された部分だけをダウンロードできます。 これにより、転送されるデータの量が減り、ドキュメントを開くために必要な時間を短縮できます。  

## <a name="current-support-for-clickonce-and-directinvoke-in-microsoft-edge"></a>Microsoft Edge での ClickOnce と DirectInvoke のサポート状況

ClickOnce と DirectInvoke のサポート状況は次のとおりです。

- ClickOnce と DirectInvoke は、すべての Windows ユーザーが標準でサポートしています。

  > [!NOTE]
  > ClickOnce のサポートを無効にするユーザーは、*edge://flags/#edge-click-once* に移動し、ドロップダウン リストから **[無効にする]** を選択してください。 ブラウザーを**再起動**する必要があります。

- ClickOnce と DirectInvoke は、Windows 以外のプラットフォームではサポートされていません。

## <a name="clickonce-and-directinvoke-file-handling-security"></a>ClickOnce と DirectInvoke のファイル処理のセキュリティ

ClickOnce と DirectInvoke は、Microsoft Defender SmartScreen の URL レピュテーション スキャン サービスによって保護されます。

Microsoft Defender SmartScreen URL レピュテーション サービスによって ClickOnce 要求または DirectInvoke 要求が安全でないとフラグ付けされた場合、ClickOnce または DirectInvoke を有効にしているユーザーに対して、2 つのポップアップが表示されます。

最初のポップアップは、ファイルを開くかどうかをユーザーに尋ねます。 このポップアップは、ファイルに安全であるとフラグ付けされた場合も安全でないとフラグ付けされた場合も、表示されます。 ユーザーは、**[このファイルは安全ではないことを報告する]** か、要求を **[キャンセル]** することもできます。続行するには、**[開く]** をクリックします。

   ![ファイルを開くかどうかを尋ねるメッセージ](./media/edge-learn-more-co-di/edge-clickonce-modal-1.png)

ユーザーがファイルを開こうとしたときに、安全でないというフラグがファイルに設定されている場合は、2 つ目のポップアップが表示されます。  このポップアップは、ファイルが安全でないとフラグ付けされていることをユーザーに警告し、それでもファイルをダウンロードするかどうかを確認します。

2 番目のポップアップは、次の場合にのみ表示されます。

- ファイルが ClickOnce ファイルまたは DirectInvoke ファイルである
- ClickOnce または DirectInvoke が有効になっている
- ファイルが安全でないとフラグ付けされている

 ![安全でないファイルを開くかどうかを尋ねるメッセージ](./media/edge-learn-more-co-di/edge-clickonce-modal-2.png)

> [!NOTE]
> ClickOnce または DirectInvoke が無効になっている場合、要求されたファイルは通常のダウンロードとして扱われ、安全でないとフラグ付されている場合は、安全ではないとマークされます。 これは、安全でない他のダウンロードの処理と一致しています。

## <a name="clickonce-and-directinvoke-policies"></a>ClickOnce と DirectInvoke のポリシー

エンタープライズ ユーザー用に ClickOnce と DirectInvoke を有効または無効にするには、2 つのグループ ポリシーを使用できます。 [ClickOnceEnabled](./microsoft-edge-policies.md#clickonceenabled) と [DirectInvokeEnabled](./microsoft-edge-policies.md#directinvokeenabled) です。 これら 2 つのポリシーには、グループ ポリシー エディターで、"ユーザーが ClickOnce プロトコルを使用してファイルを開けるようにする" と "ユーザーが DirectInvoke プロトコルを使用してファイルを開けるようにする" というラベルがそれぞれ付けられています。

## <a name="clickonce-and-directinvoke-behavior"></a>ClickOnce と DirectInvoke の動作

次の例は、ClickOnce と DirectInvoke が有効または無効になっているときのファイル処理を示しています。

### <a name="clickonce-enabled"></a>ClickOnce が有効になっている場合

1. ユーザーが ClickOnce のサポートを要求するページへのリンクを開くと、次のスクリーンショットに示されているメッセージが表示されます。

   ![安全でないファイルを開くかどうかを尋ねるメッセージ](./media/edge-learn-more-co-di/edge-clickonce-enabled-1.png)

2. ユーザーが **[開く]** をクリックすると、ClickOnce はアプリケーションの起動を試行します。

   ![ClickOnce がアプリケーションの起動を試行する](./media/edge-learn-more-co-di/edge-clickonce-enabled-launch-app.png)

3. ユーザーが **[開く]** をクリックすると、ブラウザーには、アプリケーションをインストールするかどうかをユーザーに尋ねるポップアップが表示されます。

   ![ファイルを開くかどうかを尋ねるメッセージ](./media/edge-learn-more-co-di/edge-clickonce-enabled-2.png)

   > [!NOTE]
   > ClickOnce ファイル ハンドラーによって表示されるインターフェイス、メッセージ、オプションは、アクセスするファイルの種類と構成によって異なります。

### <a name="clickonce-disabled"></a>ClickOnce が無効になっている場合

1. ユーザーが ClickOnce のサポートを要求するページへのリンクを開くと、次のスクリーンショットに示されているようなメッセージがダウンロード トレイに表示されます。

   ![ファイルのダウンロードを確認するメッセージ](./media/edge-learn-more-co-di/edge-clickonce-disabled-1.png)

### <a name="directinvoke-enabled"></a>DirectInvoke が有効になっている場合

1. ユーザーが DirectInvoke のサポートを要求するページへのリンクを開くと、次のスクリーンショットに示されているメッセージが表示されます。

   ![ファイルを開くかどうかを尋ねるメッセージ](./media/edge-learn-more-co-di/edge-directinvoke-open-link-1.png)

2. ユーザーが **[開く]** をクリックすると、要求されたファイル ハンドラーが開きます。 この例では、前のスクリーンショットに示されているドキュメントを開くために Microsoft Word が使用されています。

   > [!NOTE]
   > DirectInvoke ファイル ハンドラーによって表示されるインターフェイス、メッセージ、オプションは、アクセスするファイルの種類と構成によって異なります。

### <a name="directinvoke-disabled"></a>DirectInvoke が無効になっている場合

1. ユーザーが DirectInvoke のサポートを要求するページへのリンクを開くと、DirectInvoke は、ClickOnce が無効になっている場合と同じように動作します。 次のスクリーンショットのようなメッセージがダウンロード トレイに表示されます。

   ![ファイルを開くかどうかを尋ねるメッセージ](./media/edge-learn-more-co-di/edge-directinvoke-open-link-2.png)

## <a name="see-also"></a>関連項目

- [ClickOnce のセキュリティと展開](/visualstudio/deployment/clickonce-security-and-deployment)
- [Internet Explorer での DirectInvoke の使用](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/jj215788(v=vs.85))
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)