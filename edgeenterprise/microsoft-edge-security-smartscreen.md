---
title: Microsoft Defender SmartScreen の Microsoft Edge サポート
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Defender SmartScreen の Microsoft Edge サポート
ms.openlocfilehash: 363605200c61807ca526818ab417301273d64f91
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979567"
---
# <a name="microsoft-edge-support-for-microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen の Microsoft Edge サポート

この記事では、Microsoft Defender SmartScreen を使用する利点、その機能、およびこの Microsoft Edge 機能の構成方法について説明します。

> [!NOTE]
> この記事は Microsoft Edge version 77 以降に適用されます。

Microsoft Defender SmartScreen は、Microsoft Edge が Web の閲覧中に安全を確保するために使用するサービスです。 Microsoft Defender SmartScreen は、フィッシング攻撃に関係している可能性のある Web サイトや、集中的な攻撃によってマルウェアを配布しようとしている Web サイトに対抗する、早期警告システムの提供に役立ちます。 詳細については、「[ビデオ: Microsoft Edge での安全な閲覧](microsoft-edge-video-security-smartscreen.md)」をご覧ください。

> [!NOTE]
> Windows 10 Version 1703 より前のバージョンでは、この機能がブラウザー内で使われるときは SmartScreen フィルターと呼ばれ、ブラウザーの外部で使われるときは Microsoft SmartScreen と呼ばれていました。

## <a name="the-benefits-of-microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen の利点

Microsoft Defender SmartScreen にはいくつかの利点があり、それらを以下のリストに要約します。 これらの利点については、[ Microsoft Defender SmartScreen のドキュメント](/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview#benefits-of-windows-defender-smartscreen)で詳しく説明されています。 利点は次のとおりです。

- フィッシング詐欺対策およびマルウェア対策のサポート
- 評判ベースの URL とアプリの保護
- オペレーティング システムとの統合
- 強化されたヒューリスティックと診断データ
- グループ ポリシーと Microsoft Intune による管理
- 望ましくない可能性があるアプリケーションと関連付けられている URL のブロック

## <a name="understand-how-microsoft-defender-smartscreen-works"></a>Microsoft Defender SmartScreen の仕組みを理解する

Microsoft Defender SmartScreen の警告には、いくつかの入力が含まれています。 データは、ユーザー フィードバック、データ プロバイダー、インテリジェンス モデルなど、多くのソースから受信されます。 このデータは、潜在的に悪意のあるコンテンツを特定するために使用されます。 Microsoft Defender SmartScreen は、ダウンロードされたアプリまたはアプリ インストーラーをチェックして、それらが悪意のあるものかどうかを確認します。 どちらのシナリオでも、Microsoft Defender SmartScreen は不審なコンテンツについてユーザーに適切に警告します。

### <a name="site-analysis"></a>サイト分析

Microsoft Defender SmartScreen では、サイトに悪意があると考えられるかどうかを次のように判断します:

- 不審な動作の兆候がないか、アクセスした Web ページを分析します。
- アクセスしたサイトを、報告されているフィッシング詐欺サイトの動的な記録と照合します。

Microsoft Defender SmartScreen がページが悪意のあるものであると判断した場合、そのサイトが安全でないと報告されていることをユーザーに通知する警告ページが表示されます。 次のスクリーンショットは、ユーザーが悪意のある Web サイトを開こうとしたときの Microsoft Defender SmartScreen 警告ページの例です。

![外部サイトへのリンクの Microsoft Defender SmartScreen ブロック ページ](media/microsoft-edge-security-smartscreen/microsoft-edge-smartscreen-warning.png)

ユーザーには、警告メッセージ内でサイトを安全または危険であると報告するオプションがあります。 詳細については、「[サイトの報告方法](/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device#how-users-can-report-websites-as-safe-or-unsafe)」を参照してください。

### <a name="file-analysis"></a>ファイル分析

Microsoft Defender SmartScreen は、ダウンロード トラフィック、ダウンロード履歴、過去のウイルス対策の結果、URL 評判などの多くの基準に基づいて、ダウンロードされたアプリまたはアプリ インストーラーが悪意のある可能性があるかどうかを判断します。

- 安全であることがわかっているファイルは、通知なしでダウンロードされます。  
- 悪意のあることがわかっているファイルには、ファイルが安全ではなく、悪意があると報告されていることをユーザーに知らせる警告が表示されます。 次のスクリーンショットは、悪意のあるファイルに対する警告の例です。

  ![悪意のあることがわかったファイルの Microsoft Defender SmartScreen ブロック通知](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-known-malicious.png)

- 不明なファイルは、ダウンロードに既知のフットプリントがないことをユーザーに通知し、注意を促す警告を表示します。 次のスクリーンショットは、不明なファイルに対する警告の例です。

  ![評判が不明なファイルの Microsoft Defender SmartScreen ブロック通知](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-unknown-malicious.png)

すべての不明なプログラムが悪意があるとは限りません。不明な警告は、特に警告が予期しないものである場合に、それを必要とするユーザーにコンテキストとガイダンスを提供することを目的としています。

  ![悪意のあることがわかったファイルを保持する](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-unknown-malicious-keep.png)

ただし、ユーザーは **[...]、[保持]、[詳細表示]、[保持]** の順にクリックしてアプリケーションをダウンロードして実行できます。

> [!TIP]
> **企業の顧客向けの参考情報です。** 既定では、ユーザーが Microsoft Defender SmartScreen の警告をバイパスできるようになっています。 このユーザー操作は危険を伴う可能性があるため、これらの[推奨されるグループ ポリシー設定](/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-available-settings#recommended-group-policy-and-mdm-settings-for-your-organization)を確認することをお勧めします。

Microsoft Defender SmartScreen が、[デモ サイト](https://demo.smartscreen.msft.net/)を使用してさまざまなシナリオにどのように対応するかがわかります。

## <a name="microsoft-defender-smartscreen-and-user-privacy"></a>Microsoft Defender SmartScreen とユーザーのプライバシー

Microsoft Defender SmartScreen は、評判チェック システムを使用してインターネットを閲覧しているユーザーを保護します。 Microsoft Edge は、評判チェックを開始するために、URL またはファイルに関する関連情報を Microsoft Defender SmartScreen サービスに渡します。 このチェックでは、Web サイトまたはファイルを、危険であることがわかっているサイトおよびファイルの動的リストと比較します。 Microsoft Defender SmartScreen サービスへのすべての要求は、TLS 暗号化で行われます。 サービスは評判チェックの結果を返します。これにより、Microsoft Edge がサイトまたはファイルの警告を表示する可能性があります。 これらの結果は、デバイスのローカルに保存されます。

Microsoft Defender SmartScreen サービスは、評判チェックに関するデータを保存します。 新しいサイトが識別されると、サービスは既知の悪意のある URL とファイルの動的データベースに追加します。 このデータは安全な Microsoft サーバーに保存され、Microsoft セキュリティ サービスでのみ使用されます。 このデータは、決してユーザーの識別やターゲット設定に使用されることはありません。 ブラウジング キャッシュをクリアすると、ローカルに保存されているすべての Microsoft Defender SmartScreen URL データがクリアされます。 ダウンロード履歴をクリアすると、ファイルのダウンロードに関するローカルに保存されている SmartScreen データが削除されます。

Microsoft Defender SmartScreen と Microsoft Edge でのプラ​​イバシーの詳細については、「[Microsoft Edge プライバシー ホワイトペーパー](/microsoft-edge/privacy-whitepaper#smartscreen)」をご覧ください。

## <a name="microsoft-defender-smartscreen-setup-for-admins"></a>管理者向けの Microsoft Defender SmartScreen セットアップ

管理者は、グループ ポリシー、Microsoft Intune、またはモバイル デバイス管理 (MDM) の設定を使用して、Microsoft Defender SmartScreen を構成できます。 Microsoft Defender SmartScreen をどのように設定するかによって、ユーザーに警告ページを表示してからサイトへのアクセスを許可するか、サイトを完全にブロックすることができます。

### <a name="microsoft-defender-smartscreen-set-up-using-group-policy"></a>グループ ポリシーを使用してセットアップされた Microsoft Defender SmartScreen

SmartScreen ポリシーの完全なリストについては、「[Microsoft Defender SmartScreen 設定](./microsoft-edge-policies.md#smartscreen-settings)」を参照してください

### <a name="microsoft-defender-smartscreen-set-up-using-mdm"></a>MDM を使用してセットアップされた Microsoft Defender SmartScreen

詳細については、以下を参照してください。

- [Microsoft Defender SmartScreen の Windows Intune 設定](/mem/intune/protect/endpoint-protection-windows-10#windows-defender-smartscreen-settings)
- [MDM ポリシー設定](/mem/intune/protect/endpoint-protection-windows-10#windows-defender-smartscreen-settings)

## <a name="microsoft-defender-smartscreen-setup-for-users"></a>ユーザー向けの Microsoft Defender SmartScreen セットアップ

Microsoft Defender SmartScreen は、Microsoft Edge では既定でオンになっています。 Microsoft Defender SmartScreen をオフにするには、*edge://settings/privacy > Services > Microsoft Defender SmartScreen* に移動します。 この設定は、デバイスへの Microsoft Edge のインストールに関連付けられているすべてのプロファイルで同じです。 この設定はデバイス間で同期されません。 この設定は、InPrivate ブラウズとゲスト モードに適用されます。 デバイスが組織によって設定されたグループ ポリシーで管理されている場合、この構成は *edge://settings/privacy* に反映されます。

> [!NOTE]
> ユーザーは、グループ ポリシーまたは MDM がそれを防ぐように構成されていない限り、個々のデバイスに対して Microsoft Defender SmartScreen をセットアップできます。 詳細については、「[個々のデバイスでの Microsoft Defender SmartScreen のセットアップと使用](/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device)」を参照してください。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="how-does-the-reputation-check-system-work"></a>評判チェック システムはどのように機能しますか?

Web を閲覧すると、Microsoft Defender SmartScreen は Web サイトとダウンロードを上位トラフィック、危険、または不明として分類します。 上位トラフィックは、Microsoft Defender SmartScreen が信頼できると判断した人気のあるサイトです。 危険とマークされたサイトにアクセスすると、Microsoft Defender SmartScreen はすぐにサイトへのアクセスをブロックします。 不明なサイトにアクセスすると、Microsoft DefenderSmartScreen はその評判をチェックして、サイトにアクセスする必要があるかどうかを判断します。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [ビデオ: Microsoft Edge での安全な閲覧](microsoft-edge-video-security-smartscreen.md)
- [Microsoft Defender SmartScreen の概要](/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)
- [脅威の防止](/windows/security/threat-protection/index)
- [望ましくない可能性のあるアプリケーションから保護する](./microsoft-edge-potentially-unwanted-apps.md)