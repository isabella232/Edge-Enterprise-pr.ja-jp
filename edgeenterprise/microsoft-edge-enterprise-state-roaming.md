---
title: Microsoft Edge と Enterprise State Roaming
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 02/14/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge と Enterprise State Roaming
ms.openlocfilehash: a759b1d9d4be8dced7bfcc2ef8d0f23b514f4be0
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980518"
---
# Microsoft Edge と Enterprise State Roaming

この記事では、Enterprise State Roaming (ESR) サービスでの Microsoft Edge の動作がどのように変更され、プラットフォームおよびデバイス間での同期のサポートがどのように向上しているかについて説明します。

> [!NOTE]
> この記事は Microsoft Edge version 77 以降に適用されます。

## はじめに

Windows 10 を使用することで、[Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) ユーザーは、ユーザー設定とアプリケーション設定のデータをクラウドに安全に同期できるようになりました。 [Enterprise State Roaming (ESR)](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) は、ユーザーが所有する複数の Windows デバイスで統一されたエクスペリエンスを実現し、新しいデバイスを構成するために必要な時間を短縮します。

Microsoft Edge での Chromium プラットフォーム採用の一環として、Microsoft Edge の同期ソリューションは Windows の同期フレームワークから切り離されました。 これは、Microsoft Edge と ESR サービスの関係にも影響します。

> [!IMPORTANT]
> 新しい Microsoft Edge は、ESR サービスの対象には含まれません。

## Microsoft Edge の変更点

新しい Microsoft Edge の同期ソリューションは、Windows 同期エコシステムに結び付けられていません。 これにより、Microsoft は、Windows 7、Windows 8.1、iOS、Android、macOS など、すべてのプラットフォームで Microsoft Edge を提供できます。 また、Windows でプライマリ アカウント以外のアカウントでも同期を実行できます。 さらに、Windows よりも頻繁かつ柔軟に Microsoft Edge をリリースできます  (詳しくは、「[次のバージョンの Microsoft Edge をサポートする Windows 更新プログラム](microsoft-edge-sysupdate-windows-updates.md)」をご覧ください)。 これらの要素はすべて、ESR サービスでの Microsoft Edge の処理を再評価することの必要性を示していました。

ESR は、Windows デバイスのデータの処理方法が約束された、Windows 製品サービスとして構築されていますが、Microsoft Edge の同期は Windows デバイスの枠を越えて実行されます。 また、これらのデバイス間でデータがローミングされる場合、ESR のコンテキストで Microsoft Edge の動機サービスを定義するのは困難です。 同期の動作と管理方法を簡素化するため、および強調されている変更に対応するために、ESR サービスから Microsoft Edge を切り離すことを決定しました。

## これにより、企業は、ESR の一部としての機能を失うことになるのでしょうか。

いいえ、そうではありません。 Microsoft Edge は、ESR サービスで提供されるほとんどの機能を引き続きサポートします。

### デバイス間での統一されたエクスペリエンスと新しいデバイスの構成時間

ユーザーが Azure Active Directory (Azure AD アカウント) を使用して Windows デバイスにサインインすると、Microsoft Edge は新しいブラウザーの初回起動時にその ID を暗黙的に継承します。

ユーザーが新しい Microsoft Edge で同期を有効にすることに明示的に同意すると、ブラウザーによって、お気に入り、パスワード、履歴などのすべてのブラウザー データが同期されます。 これにより、デバイス間で統一されたエクスペリエンスが実現され、ブラウザーのパーソナル設定を行うために必要な時間が短縮されます。

### 企業データとコンシューマー データの分離

組織は組織のデータを管理することができ、企業データがコンシューマー クラウド アカウントに混在したり、コンシューマー データが企業のクラウド アカウントに混在したりすることはありません。

### 強化されたセキュリティ

データは、Azure Information Protection を使用してユーザーの Windows 10 デバイスから送信される前に自動的に暗号化され、クラウドでも暗号化されたままです。 設定名のような名前空間を除き、すべてのコンテンツが暗号化されたままクラウドに保存されます。

### 監視

Azure AD ポータルとの統合によって、だれが、どのデバイスで、組織内で設定を同期するかを制御し、可視化できるようにします。 この機能は、今後のリリースで実現されます。

### 管理

管理者は、組織内のどのメンバーが同期を有効にできるかを制御できます。[Microsoft Edge の同期の構成オプション](microsoft-edge-enterprise-sync.md#configuration-options-for-microsoft-edge-sync)と[同期グループ ポリシー](microsoft-edge-enterprise-sync.md#sync-group-policies)に関する説明を参照してください。 さらに、ユーザーは、デバイスごとに同期をオン/オフにしたり、各データ属性の同期を個別に切り替えたりすることができます。

### キーの管理

同期機能は Azure Information Protection (AIP) を使用して、ユーザーとエンタープライズ管理者についてのみ、同期されたデータを保護します。 AIP では、クラウド キー管理用に、Microsoft が管理する (既定) のキーとユーザー独自のキーの両方をサポートしています。 組織が使用するクラウド キー管理戦略は Microsoft Edge に対して透過的であり、同期機能には影響しません。

> [!IMPORTANT]
> [Hold Your Own Key (HYOK)](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions) と Active Directory Rights Management サービスはサポートされていません。

## 同期属性の概要

次のデータ属性が、初回起動時に Microsoft Edge の新しいバージョンで同期されます。

- お気に入り
- パスワード
- フォームの入力情報
- 履歴
- 開いているタブ (セッション)
- 設定 (基本設定)
- 拡張機能

前の属性の一覧は、従来の Microsoft Edge で同期できる属性とは異なります  (従来の Microsoft Edge の設定の詳細については、[Windows 10 ローミング設定](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-windows-settings-reference)に関するトピックを参照してください)。ユーザーは、Microsoft Edge の設定を使用して、これらの属性を選択的に有効または無効にすることができます。 2つのバージョン間での属性の違い (履歴など) によって、ユーザーはもう一度同期に関する同意を求められる場合があります。

> [!NOTE]
> 従来の Microsoft Edge とは異なり、新しい Microsoft Edge はパスワードの管理に Windows 資格情報マネージャーを使用しないため、Windows 資格情報マネージャーを使用する Internet Explorer やその他のアプリとパスワードを同期しません。

## サービス条件

Microsoft Edge 同期のサービス条件は、Microsoft Edge で *edge://terms* にアクセスすると表示される Microsoft ソフトウェア ライセンスに従います。

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge の同期](microsoft-edge-enterprise-sync.md)