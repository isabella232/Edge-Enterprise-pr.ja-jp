---
title: Microsoft Edge と Enterprise State Roaming
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge と Enterprise State Roaming
ms.openlocfilehash: 34ee5bf7970834a2e2211db9e2c0bc6ae99bcd6b
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980316"
---
# <a name="microsoft-edge-and-enterprise-state-roaming"></a>Microsoft Edge と Enterprise State Roaming

この記事では、Enterprise State Roaming (ESR) サービスでの Microsoft Edge の動作がどのように変更され、プラットフォームおよびデバイス間での同期のサポートがどのように向上しているかについて説明します。

> [!NOTE]
> この記事は Microsoft Edge version 77 以降に適用されます。

## <a name="introduction"></a>はじめに

Windows 10 を使用することで、[Azure Active Directory (Azure AD)](/azure/active-directory/fundamentals/active-directory-whatis) ユーザーは、ユーザー設定とアプリケーション設定のデータをクラウドに安全に同期できるようになりました。 [Enterprise State Roaming (ESR)](/azure/active-directory/devices/enterprise-state-roaming-overview) は、ユーザーが所有する複数の Windows デバイスで統一されたエクスペリエンスを実現し、新しいデバイスを構成するために必要な時間を短縮します。

Microsoft Edge での Chromium プラットフォーム採用の一環として、Microsoft Edge の同期ソリューションは Windows の同期フレームワークから切り離されました。 これは、Microsoft Edge と ESR サービスの関係にも影響します。

> [!IMPORTANT]
> 新しい Microsoft Edge は、ESR サービスの対象には含まれません。

## <a name="whats-changing-with-microsoft-edge"></a>Microsoft Edge の変更点

新しい Microsoft Edge の同期ソリューションは、Windows 同期エコシステムに結び付けられていません。 これにより、Microsoft は、Windows 7、Windows 8.1、iOS、Android、macOS など、すべてのプラットフォームで Microsoft Edge を提供できます。 また、Windows でプライマリ アカウント以外のアカウントでも同期を実行できます。 さらに、Windows よりも頻繁かつ柔軟に Microsoft Edge をリリースできます  (詳しくは、「[次のバージョンの Microsoft Edge をサポートする Windows 更新プログラム](microsoft-edge-sysupdate-windows-updates.md)」をご覧ください)。 これらの要素はすべて、ESR サービスでの Microsoft Edge の処理を再評価することの必要性を示していました。

ESR は、Windows デバイスのデータの処理方法が約束された、Windows 製品サービスとして構築されていますが、Microsoft Edge の同期は Windows デバイスの枠を越えて実行されます。 また、これらのデバイス間でデータがローミングされる場合、ESR のコンテキストで Microsoft Edge の動機サービスを定義するのは困難です。 同期の動作と管理方法を簡素化するため、および強調されている変更に対応するために、ESR サービスから Microsoft Edge を切り離すことを決定しました。

## <a name="does-this-mean-enterprises-will-lose-the-abilities-they-had-as-part-of-esr"></a>これにより、企業は、ESR の一部としての機能を失うことになるのでしょうか。

いいえ、そうではありません。 Microsoft Edge は、ESR サービスで提供されるほとんどの機能を引き続きサポートします。

### <a name="unified-experience-across-devices-and-new-device-configuration-time"></a>デバイス間での統一されたエクスペリエンスと新しいデバイスの構成時間

ユーザーが Azure Active Directory (Azure AD アカウント) を使用して Windows デバイスにサインインすると、Microsoft Edge は新しいブラウザーの初回起動時にその ID を暗黙的に継承します。

ユーザーが新しい Microsoft Edge で同期を有効にすることに明示的に同意すると、ブラウザーによって、お気に入り、パスワード、履歴などのすべてのブラウザー データが同期されます。 これにより、デバイス間で統一されたエクスペリエンスが実現され、ブラウザーのパーソナル設定を行うために必要な時間が短縮されます。

### <a name="separation-of-corporate-and-consumer-data"></a>企業データとコンシューマー データの分離

組織は組織のデータを管理することができ、企業データがコンシューマー クラウド アカウントに混在したり、コンシューマー データが企業のクラウド アカウントに混在したりすることはありません。

### <a name="enhanced-security"></a>強化されたセキュリティ

データは、Azure Information Protection を使用してユーザーの Windows 10 デバイスから送信される前に自動的に暗号化され、クラウドでも暗号化されたままです。 設定名のような名前空間を除き、すべてのコンテンツが暗号化されたままクラウドに保存されます。

### <a name="monitoring"></a>監視

Azure AD ポータルとの統合によって、だれが、どのデバイスで、組織内で設定を同期するかを制御し、可視化できるようにします。 この機能は、今後のリリースで実現されます。

### <a name="management"></a>管理

管理者は、組織内のどのメンバーが同期を有効にできるかを制御できます。「[Microsoft Edge の同期を構成する](microsoft-edge-enterprise-sync.md#configure-microsoft-edge-sync)」と「[同期グループ ポリシー](microsoft-edge-enterprise-sync.md#sync-group-policies)」を参照してください。 さらに、ユーザーは、デバイスごとに同期をオン/オフにしたり、各データ属性の同期を個別に切り替えたりすることができます。

### <a name="key-management"></a>キーの管理

同期機能は Azure Information Protection (AIP) を使用して、ユーザーとエンタープライズ管理者についてのみ、同期されたデータを保護します。 AIP では、クラウド キー管理用に、Microsoft が管理する (既定) のキーとユーザー独自のキーの両方をサポートしています。 組織が使用するクラウド キー管理戦略は Microsoft Edge に対して透過的であり、同期機能には影響しません。

> [!IMPORTANT]
> [Hold Your Own Key (HYOK)](/azure/information-protection/configure-adrms-restrictions) と Active Directory Rights Management サービスはサポートされていません。

## <a name="summary-of-sync-attributes"></a>同期属性の概要

次のデータ属性が、初回起動時に Microsoft Edge の新しいバージョンで同期されます。

- お気に入り
- パスワード
- フォームの入力情報
- 履歴
- 開いているタブ (セッション)
- 設定 (基本設定)
- 拡張機能

前の属性の一覧は、従来の Microsoft Edge で同期できる属性とは異なります  (従来の Microsoft Edge の設定の詳細については、[Windows 10 ローミング設定](/azure/active-directory/devices/enterprise-state-roaming-windows-settings-reference)に関するトピックを参照してください)。ユーザーは、Microsoft Edge の設定を使用して、これらの属性を選択的に有効または無効にすることができます。 2つのバージョン間での属性の違い (履歴など) によって、ユーザーはもう一度同期に関する同意を求められる場合があります。

> [!NOTE]
> 従来の Microsoft Edge とは異なり、新しい Microsoft Edge はパスワードの管理に Windows 資格情報マネージャーを使用しないため、Windows 資格情報マネージャーを使用する Internet Explorer やその他のアプリとパスワードを同期しません。

## <a name="terms-of-service"></a>サービス条件

Microsoft Edge 同期のサービス条件は、Microsoft Edge で *edge://terms* にアクセスすると表示される Microsoft ソフトウェア ライセンスに従います。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge の同期](microsoft-edge-enterprise-sync.md)