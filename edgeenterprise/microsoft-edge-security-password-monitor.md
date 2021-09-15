---
title: パスワード モニターがユーザーに対して自動的に有効にされます
ms.author: supalsul
author: AndreLBarr
manager: tulasim
ms.date: 07/12/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: パスワード モニターがユーザーに対して自動的に有効にされます
ms.openlocfilehash: bd1fe390b972c66cd9b4c20ab3a9fabde76c7e03
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980337"
---
# <a name="password-monitor-auto-enabled-for-users"></a>パスワード モニターがユーザーに対して自動的に有効にされます

この記事では、選択されたユーザーに対して Microsoft Edge のパスワード モニターがどのように有効になるかについて説明し、管理者が監視を有効にする方法を制御する手順について説明します。

> [!NOTE]
> この記事は Microsoft Edge バージョン 88 以降に適用されます。

## <a name="introduction-benefits-and-availability"></a>概要、利点、可用性

パスワード モニターは、オンライン リークでパスワードが見つかった場合にユーザーに知らせることで、Microsoft Edge ユーザーがオンライン アカウントを保護するのに役立ちます。 オンライン リークやデータ侵害は、攻撃者がサード パーティ製のアプリや Web サイトからデータを盗むと発生します。 詳細については、Microsoft Research ブログの「[パスワード モニター: Microsoft Edge でのパスワードの保護](https://www.microsoft.com/research/blog/password-monitor-safeguarding-passwords-in-microsoft-edge/)」ペーパーを参照してください。

### <a name="benefits"></a>利点

これらのオンラインからの攻撃の頻度と範囲を考慮すると、このような保護をすべてのユーザーが入手する必要があります。 Microsoft Edge には、侵害されたことが判明しているパスワードに対して、保存されたユーザーのパスワードを安全に確認し、一致が見つかった場合にはユーザーに警告する組み込みの機能が用意されています。  

## <a name="configure-group-policy-for-password-monitor"></a>パスワード モニターのグループ ポリシーを構成する

この機能は [PasswordMonitorAllowed](./microsoft-edge-policies.md#passwordmonitorallowed) グループ ポリシーによって制御されます。

ポリシーを有効にした後も、ユーザーは機能を有効にすることについて同意する必要があります。 この機能にはユーザーの機密データと個人データ (パスワード) が含まれているため、同意が必要です。 グループ ポリシーを使用して機能が無効になっている場合、ユーザーはこの設定を上書きできません。  

## <a name="enabling-password-monitor-for-users"></a>ユーザーに対してパスワード モニターを有効にする

パスワード モニター ポリシーが有効になると、さまざまな方法でこの機能をユーザーに利用可能にできます。

- 自動有効化。 仕事用アカウント (Active Directory または Azure Active Directory) を使用してサインインし、パスワードを同期しているユーザーの場合、この機能が自動的に有効になります。 次のスクリーンショットに示されているように、ユーザーには機能が有効になっていることを知らせる通知が表示されます。

  :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-enabled-notice.png" alt-text="パスワード モニターの有効化に関する通知":::

-  明示的な同意を得る。 パスワード同期が有効になっていないユーザーには、パスワード モニターを有効にするためのアクセス許可が要求されます。 次のアクションが発生すると、メッセージが表示されます。
   - ユーザーが新しいパスワードを保存した場合。
 
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-save-pw-prompt.png" alt-text="パスワードを保存するかどうかを尋ねるメッセージ":::

   - ユーザーが保存されたパスワードを使用してブラウザーにサインインした場合。
  
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-after-signin.png" alt-text="サインイン後の確認プロンプト":::
   
- 直接のライセンス認証。 ユーザーは、いつでも **[設定]** > **[パスワード]** に移動して、機能のオンとオフを切り替えることができます。

## <a name="user-scenarios-with-password-monitor-auto-enabled"></a>パスワード モニターが自動的に有効になっているユーザー シナリオ

次の表は、パスワード モニターが自動的に有効になっているシナリオと、ユーザーのデバイスでのパスワード モニターの動作を示しています。

| シナリオ | 基本条件 | 影響 |
|--|--|--|
| 1. 同期がオン | 同期オン<br>以前に機能が有効にされた: いいえ<br>同意の UI への応答: なし | 機能は既定で有効になっており、ブラウザーが起動した 2 分後に通知バブルが表示されます。<br>- その後に同期がオフになると、機能は無効になります。<br>- 同期を変更する前に機能をオフにした場合、同期は機能に影響を与えなくなります。   |
| 2. 同期がオン | 同期オン<br>以前に機能が有効にされた: はい<br>同意の UI への応答: なし | 機能はユーザーの選択と同じままになります。  通知バブルは表示されず、同期の変更が機能の値に影響を与えることはありません。|
| 3. 同期がオフ | 同期オフ<br>以前に機能が有効にされた: いいえ<br>同意の UI への応答: なし | 同期がオフになり、機能は無効のままになります<br>- ユーザーが機能を変更せずに、その後の任意の時点で同期を有効にした場合: 機能が有効になり、同期が有効になった 2 分後に自動有効化の通知が表示されます。 <br> - 同期が再びオフになった場合、機能は無効になります <br>- 同期を有効にする前に機能を変更した場合、同期がパスワード モニターに影響を与えることはありません。  |  
| 4. 同期がオフ | 同期オフ<br>以前に機能が有効にされた: はい<br>同意の UI への応答: なし | 機能はユーザーの選択と同じままになり、通知バブルは表示されません。また、同期の変更が機能の値に影響を与えることはありません。  |

さらに、ユーザーが次のいずれかに対するポリシーによって制限されている仕事用アカウントを使用してサインインしている場合、機能がユーザーに対して自動的に有効になることはありません。

- パスワード モニターが無効になっている  
- パスワード同期が無効になっている
- Microsoft サーバーとのデータ共有が無効になっている

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="how-can-password-monitor-be-disabled-for-my-organization"></a>組織でパスワード モニターを無効にするにはどうすればよいですか。

組織のパスワード モニターは、次の方法で無効にできます。
- PasswordMonitorAllowed グループ ポリシーの使用。
- データが同期され、Microsoft サーバーに送信されることを防ぐ。

  > [!NOTE]
  > パスワードの同期が無効になっている場合でも、ユーザーが機能をオンにすることに明示的に同意した場合や、自分で [設定] から有効にしている場合は、パスワード モニターが機能します。

### <a name="what-happens-if-a-user-for-whom-the-feature-has-been-auto-enabled-turns-password-monitor-off-via-settings"></a>機能が自動的に有効になっているユーザーが [設定] からパスワード モニターをオフにした場合、どうなりますか。

ユーザー設定が優先され、そのユーザーに対しては機能が無効のままになります。 ただし、これまで同意プロンプトに一度も応答したことがない場合は、もう一度同意ダイアログが表示される場合があります。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)