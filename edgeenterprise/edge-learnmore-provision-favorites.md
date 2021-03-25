---
title: Microsoft Edge のお気に入りをプロビジョニングする
ms.author: capoon
author: dan-wesley
manager: abutcher
ms.date: 09/29/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge のお気に入りをプロビジョニングする
ms.openlocfilehash: 67627fa10806435d76cecae00f79867bc5af03df
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447601"
---
# <a name="provision-favorites-for-microsoft-edge"></a>Microsoft Edge のお気に入りをプロビジョニングする

お客様からのフィードバックに基づいて、お気に入りの プロビジョニング を改善しました。 Microsoft Edge バージョン 85 以降、管理者はお気に入りをプロビジョニングするために手動でファイルを作成する必要がなくなりました。 管理者は、Microsoft Edge UI を使用してお気に入りとフォルダーを追加し、グループポリシーにエクスポートできるファイルを生成できます。

この記事では、組織のお気に入りとフォルダーのセットをプロビジョニングする方法について説明します。 [[お気に入りの構成](//DeployEdge/microsoft-edge-policies#configure-favorites)] ポリシーを使用して、お気に入りとフォルダーをプロビジョニングできます。

> [!NOTE]
> この記事は Microsoft Edge version 85 以降に適用されます。

## <a name="prerequisites-and-recommendations"></a>前提条件と推奨事項

- グループポリシー用に適切な管理用テンプレートがインストールされた Microsoft Edge バージョン 85。
- これらのお気に入りをプロビジョニングするには、Microsoft Edge の新しいプロファイルを使用することをお勧めします。 プロファイルとともに保存されたすべてのお気に入りがエクスポートに含まれます。  

## <a name="provision-favorites-and-folders"></a>お気に入りとフォルダをプロビジョニングする

次の手順を使用して、ユーザーのお気に入りとフォルダーをプロビジョニングします。

1. Microsoft Edgeのアドレスバーに移動し、次のURLを入力します: *edge://flags/#edge-favorites-admin-export*。
2. [**管理者向けのお気に入り構成のエクスポート**] で、ドロップダウンリストから [**有効**] を選択し、[**再起動**] をクリックします。

3. プロビジョニングする**お気に入り**とフォルダーを追加できるように、*edge://favorites* の [お気に入り] ページに移動します。

<!--
4. On the **Favorites bar**, click **Add folder**. The folder structure of favorites that are set in the profile you're using will be reflected in the folder you provision for your users. The next screenshot shows "Managed favorites", the folder we'll use to provision favorites.

   ![Add a folder](media/edge-learnmore-provision-favorites/provision-favorites-add-folder.png)

   > [!TIP]
   > Add existing folders that contain favorites you want to provision for your users.

5. Select "Managed favorites" and then click **Add favorite**. The next screenshot shows the favorite we've added.

   ![Add a favorite](media/edge-learnmore-provision-favorites/provision-favorites-add-favorite.png)-->

4. お気に入りとフォルダの追加が完了したら、それらをエクスポートして、**お気に入りの構成** ポリシーで使用できるようにします。 アドレスバーに移動して *edge://favorites* に移動し、省略記号 "**…**" をクリックして、[**お気に入りの構成をエクスポート**] を選択します。 次のスクリーンショットは、お気に入りをプロビジョニングするときに使用できるオプションを示しています。

   ![お気に入りを操作するためのメニューオプション。](media/edge-learnmore-provision-favorites/provision-favorites-menu-options.png)

5. [**お気に入りの構成をエクスポート**] で、ユーザーに表示されるフォルダーの名前を指定します。 フォルダ名を入力し、使用するプラットフォーム形式を選択します。 [**クリップボードにコピー**] をクリックします。 次のスクリーンショットは、フォルダー名の「管理されているお気に入り」を示しており、プラットフォームは Windows です。

   ![お気に入りを Windows フォルダにエクスポートするためのダイアログ。](media/edge-learnmore-provision-favorites/provision-favorites-export.png)

6. グループポリシーエディターを開き、*[コンピューターの構成] / [管理用テンプレート]* に移動して [**お気に入りの構成**] を選択します。 "お気に入りの構成" ポリシーを有効にします。 [**オプション:**] で、エクスポートしたコンテンツを [お気に入りの構成] テキスト領域に貼り付けて、[**適用**] をクリックします。 次のスクリーンショットは、手順 5 の "Managedfavorites" フォルダの例を示しています。

   ![gpedit を使用して、「お気に入りの構成」ポリシーを有効にして構成します。](media/edge-learnmore-provision-favorites/provision-favorites-gpedit.png)

7. [**OK**] または [**適用**] をクリックして、このポリシー設定を保存します。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)