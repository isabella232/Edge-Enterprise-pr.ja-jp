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
# <a name="provision-favorites-for-microsoft-edge"></a><span data-ttu-id="114d8-103">Microsoft Edge のお気に入りをプロビジョニングする</span><span class="sxs-lookup"><span data-stu-id="114d8-103">Provision favorites for Microsoft Edge</span></span>

<span data-ttu-id="114d8-104">お客様からのフィードバックに基づいて、お気に入りの プロビジョニング を改善しました。</span><span class="sxs-lookup"><span data-stu-id="114d8-104">Based on customer feedback, we've made improvements to provisioning favorites.</span></span> <span data-ttu-id="114d8-105">Microsoft Edge バージョン 85 以降、管理者はお気に入りをプロビジョニングするために手動でファイルを作成する必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="114d8-105">Starting with Microsoft Edge version 85, Admins no longer have to manually craft a file to provision favorites.</span></span> <span data-ttu-id="114d8-106">管理者は、Microsoft Edge UI を使用してお気に入りとフォルダーを追加し、グループポリシーにエクスポートできるファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="114d8-106">Admins can add favorites and folders using the Microsoft Edge UI to generate a file that can be exported to a group policy.</span></span>

<span data-ttu-id="114d8-107">この記事では、組織のお気に入りとフォルダーのセットをプロビジョニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="114d8-107">This article describes how to provision a set of favorites and folders for your organization.</span></span> <span data-ttu-id="114d8-108">[[お気に入りの構成](//DeployEdge/microsoft-edge-policies#configure-favorites)] ポリシーを使用して、お気に入りとフォルダーをプロビジョニングできます。</span><span class="sxs-lookup"><span data-stu-id="114d8-108">You can use the [Configure favorites](//DeployEdge/microsoft-edge-policies#configure-favorites) policy to provision favorites and folders.</span></span>

> [!NOTE]
> <span data-ttu-id="114d8-109">この記事は Microsoft Edge version 85 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="114d8-109">This article applies to Microsoft Edge version 85 or later.</span></span>

## <a name="prerequisites-and-recommendations"></a><span data-ttu-id="114d8-110">前提条件と推奨事項</span><span class="sxs-lookup"><span data-stu-id="114d8-110">Prerequisites and recommendations</span></span>

- <span data-ttu-id="114d8-111">グループポリシー用に適切な管理用テンプレートがインストールされた Microsoft Edge バージョン 85。</span><span class="sxs-lookup"><span data-stu-id="114d8-111">Microsoft Edge version 85 with the appropriate administrative template installed for group policies.</span></span>
- <span data-ttu-id="114d8-112">これらのお気に入りをプロビジョニングするには、Microsoft Edge の新しいプロファイルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="114d8-112">We recommend that you use a new profile in Microsoft Edge to provision these favorites.</span></span> <span data-ttu-id="114d8-113">プロファイルとともに保存されたすべてのお気に入りがエクスポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="114d8-113">All favorites that are saved with the profile will be included in the export.</span></span>  

## <a name="provision-favorites-and-folders"></a><span data-ttu-id="114d8-114">お気に入りとフォルダをプロビジョニングする</span><span class="sxs-lookup"><span data-stu-id="114d8-114">Provision favorites and folders</span></span>

<span data-ttu-id="114d8-115">次の手順を使用して、ユーザーのお気に入りとフォルダーをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="114d8-115">Use the following steps to provision favorites and folders for your users.</span></span>

1. <span data-ttu-id="114d8-116">Microsoft Edgeのアドレスバーに移動し、次のURLを入力します: *edge://flags/#edge-favorites-admin-export*。</span><span class="sxs-lookup"><span data-stu-id="114d8-116">Go to the Microsoft Edge address bar and type this URL: *edge://flags/#edge-favorites-admin-export*.</span></span>
2. <span data-ttu-id="114d8-117">[**管理者向けのお気に入り構成のエクスポート**] で、ドロップダウンリストから [**有効**] を選択し、[**再起動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="114d8-117">Under **Favorites configuration export for administrators**, pick **Enabled** from the dropdown list and then click **Restart**.</span></span>

3. <span data-ttu-id="114d8-118">プロビジョニングする**お気に入り**とフォルダーを追加できるように、*edge://favorites* の [お気に入り] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="114d8-118">Go to the **Favorites** page at *edge://favorites* so you can add the favorites and folders that you want to provision.</span></span>

<!--
4. On the **Favorites bar**, click **Add folder**. The folder structure of favorites that are set in the profile you're using will be reflected in the folder you provision for your users. The next screenshot shows "Managed favorites", the folder we'll use to provision favorites.

   ![Add a folder](media/edge-learnmore-provision-favorites/provision-favorites-add-folder.png)

   > [!TIP]
   > Add existing folders that contain favorites you want to provision for your users.

5. Select "Managed favorites" and then click **Add favorite**. The next screenshot shows the favorite we've added.

   ![Add a favorite](media/edge-learnmore-provision-favorites/provision-favorites-add-favorite.png)-->

4. <span data-ttu-id="114d8-119">お気に入りとフォルダの追加が完了したら、それらをエクスポートして、**お気に入りの構成** ポリシーで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="114d8-119">When you finish adding favorites and folders you'll export them so they can be used by the **Configure favorites** policy.</span></span> <span data-ttu-id="114d8-120">アドレスバーに移動して *edge://favorites* に移動し、省略記号 "**…**" をクリックして、[**お気に入りの構成をエクスポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="114d8-120">Go to the address bar and navigate to *edge://favorites*, click the ellipsis "**…**" and choose **Export favorites configuration**.</span></span> <span data-ttu-id="114d8-121">次のスクリーンショットは、お気に入りをプロビジョニングするときに使用できるオプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="114d8-121">The next screenshot shows the options you have when provisioning favorites.</span></span>

   ![お気に入りを操作するためのメニューオプション。](media/edge-learnmore-provision-favorites/provision-favorites-menu-options.png)

5. <span data-ttu-id="114d8-123">[**お気に入りの構成をエクスポート**] で、ユーザーに表示されるフォルダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="114d8-123">Under **Export your favorites configuration** you provide a name for the folder that your users will see.</span></span> <span data-ttu-id="114d8-124">フォルダ名を入力し、使用するプラットフォーム形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="114d8-124">Type the Folder name and pick the Platform format you want to use.</span></span> <span data-ttu-id="114d8-125">[**クリップボードにコピー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="114d8-125">Click **Copy to clipboard**.</span></span> <span data-ttu-id="114d8-126">次のスクリーンショットは、フォルダー名の「管理されているお気に入り」を示しており、プラットフォームは Windows です。</span><span class="sxs-lookup"><span data-stu-id="114d8-126">The next screenshot shows "Managed favorites" for the folder name and the platform is Windows.</span></span>

   ![お気に入りを Windows フォルダにエクスポートするためのダイアログ。](media/edge-learnmore-provision-favorites/provision-favorites-export.png)

6. <span data-ttu-id="114d8-128">グループポリシーエディターを開き、*[コンピューターの構成] / [管理用テンプレート]* に移動して [**お気に入りの構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="114d8-128">Open the Group Policy Editor, navigate to *Computer Configuration/Administrative Templates/* and pick **Configure Favorites**.</span></span> <span data-ttu-id="114d8-129">"お気に入りの構成" ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="114d8-129">Enable the "Configure Favorites" policy.</span></span> <span data-ttu-id="114d8-130">[**オプション:**] で、エクスポートしたコンテンツを [お気に入りの構成] テキスト領域に貼り付けて、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="114d8-130">Under **Options:**, paste the exported contents in the Configure favorites text area then click **Apply**.</span></span> <span data-ttu-id="114d8-131">次のスクリーンショットは、手順 5 の "Managedfavorites" フォルダの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="114d8-131">The next screenshot shows an example of the "Managed favorites" folder from step 5.</span></span>

   ![gpedit を使用して、「お気に入りの構成」ポリシーを有効にして構成します。](media/edge-learnmore-provision-favorites/provision-favorites-gpedit.png)

7. <span data-ttu-id="114d8-133">[**OK**] または [**適用**] をクリックして、このポリシー設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="114d8-133">Click **OK** or **Apply** to safe the policy settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="114d8-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="114d8-134">See also</span></span>

- [<span data-ttu-id="114d8-135">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="114d8-135">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)