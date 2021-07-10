---
title: モバイル デバイス管理を使用して Microsoft Edge を構成する
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: モバイル デバイス管理を使用して Microsoft Edge を構成します。
ms.openlocfilehash: 0927d64366652986b87c2f517ca8ebafd4c9ac55
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641653"
---
# <a name="configure-microsoft-edge-using-mobile-device-management"></a>モバイル デバイス管理を使用して Microsoft Edge を構成する

この記事では、[ADMX インジェスト](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)を通じ、[モバイル デバイス管理 (MDM)](/windows/client-management/mdm/) を使用して、Windows 10 で Microsoft Edge を構成する方法について説明します。 以下についても説明します。

- [Microsoft Edge ポリシー用に Open Mobile Alliance Uniform Resource Identifier (OMA-URI) を作成する](#create-an-oma-uri-for-microsoft-edge-policies)方法。
- [ADMX インジェストとカスタムの OMA-URI を使用して Intune で Microsoft Edge を構成する](#configure-microsoft-edge-in-intune-using-admx-ingestion)方法。

> [!NOTE]
> この記事は、Microsoft Edge version 77 以降に適用されます。

## <a name="prerequisites"></a>前提条件

以下の最小システム要件を満たす Windows 10:

- [KB4512941](https://support.microsoft.com/help/4512941/) および [KB4517211](https://support.microsoft.com/help/4517211/) をインストール済みの Windows 10 Version 1903
- [KB4512534](https://support.microsoft.com/help/4512534/) および [KB4520062](https://support.microsoft.com/help/4520062/) をインストール済みの Windows 10 Version 1809
- [KB4512509](https://support.microsoft.com/help/4512509/) および [KB4519978](https://support.microsoft.com/help/4519978) をインストール済みの Windows 10 Version 1803
- [KB4516071](https://support.microsoft.com/help/4516071/) および [KB4520006](https://support.microsoft.com/help/4520006) をインストール済みの Windows 10 Version 1709

## <a name="overview"></a>概要

[ADMX インジェスト](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)をサポートする Enterprise Mobility Management (EMM) または MDM プロバイダーで、MDM を使用して Windows 10 の Microsoft Edge を構成できます。

MDM を使用した Microsoft Edge の構成は、次の 2 つのプロセスで構成されます。

1. Microsoft Edge ADMX ファイルを EMM または MDM プロバイダーに取り込む。 ADMX ファイルの取り込み方法については、プロバイダーの説明をご覧ください。

   > [!NOTE]
   > Microsoft Intune の場合は、「[ADMX インジェストを使用して Intune で Microsoft Edge を構成する](#configure-microsoft-edge-in-intune-using-admx-ingestion)」をご覧ください。

2. [Microsoft Edge ポリシー用の OMA-URI を作成](#create-an-oma-uri-for-microsoft-edge-policies)する。

## <a name="create-an-oma-uri-for-microsoft-edge-policies"></a>Microsoft Edge ポリシー用の OMA-URI を作成する

以下のセクションでは、OMA-URI パスを作成し、必須および推奨のブラウザー ポリシー用に XML 形式で値を検索および定義する方法について説明します。

開始する前に、[Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)から Microsoft Edge ポリシー テンプレートフ ァイル (MicrosoftEdgePolicyTemplates.cab) をダウンロードし、内容を展開します。

OMA-URI を定義するには、次の 3 つの手順を実行します。

1. [OMA-URI パスを作成する](#create-the-oma-uri-path)
2. [OMA-URI データ型を指定する](#specify-the-data-type)
3. [OMA-URI 値を設定する](#set-the-value-for-a-browser-policy)

### <a name="create-the-oma-uri-path"></a>OMA-URI パスを作成する

OMA-URI パスを作成するためのガイドとして、次の式を使用できます。 <br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`* <br/><br/>

| パラメーター         | 説明                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| \<ADMXIngestName> | "Edge" を使用するか、管理用テンプレートの取り込み時に定義した名前を使用します。 たとえば、"./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/MicrosoftEdge/Policy/EdgeAdmx" を使用した場合は、"MicrosoftEdge" を使用します。<br/><br/> `<ADMXIngestionName>` は、ADMX ファイルの取り込み時に使用した名前と一致する必要があります。 |
| \<ADMXNamespace>  | 必須のポリシーと推奨のポリシーのどちらを設定しているかによって、"microsoft_edge" または "microsoft_edge_recommended" を指定します。 |
| \<ADMXCategory>   | ポリシーの "parentCategory" は、ADMX ファイルで定義されています。 ポリシーがグループ化されていない ("parentCategory" が定義されていない) 場合は、`<ADMXCategory>` を省略します。 |
| \<PolicyName>     | ポリシー名については、[「ブラウザー ポリシー リファレンス](./microsoft-edge-policies.md)」をご覧ください。 |

#### <a name="uri-path-example"></a>URI パスの例:

この例は、`<ADMXIngestName>` ノードの名前が "Edge" で、必須ポリシーを設定する場合を想定しています。 URI パスは次のようになります。<br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~<ADMXCategory>/<PolicyName>`*

ポリシーがグループに含まれていない場合 (DiskCacheSize など)、`~<ADMXCategory>` を削除します。 `<PolicyName>` をポリシーの名前「DiskCacheSize」に置き換えます。 URI パスは次のようになります。<br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`*

ポリシーがグループ内にある場合は、次の手順を実行します。

1. 任意の xml エディターを使用して **msedge.admx** を開きます。
2. 設定するポリシー名を検索します  ("ExtensionInstallForceList" など)。
3. *parentCategory* 要素の *ref* 属性の値を使用します  たとえば、\<parentCategory ref=" Extensions"/> の「拡張機能」です。
4. `<ADMXCategory>` を *ref* 属性値に置き換えて、URI パスを作成します。 URI パスは次のようになります。<br/><br/>
*`/Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`*

### <a name="specify-the-data-type"></a>データ型を指定する

OMA URI のデータ型は常に "String" です。

### <a name="set-the-value-for-a-browser-policy"></a>ブラウザー ポリシーの値を設定する

このセクションでは、データ型ごとに XML 形式で値を設定する方法について説明します。 ポリシーのデータ型については、「[ブラウザー ポリシー リファレンス](./microsoft-edge-policies.md)」をご覧ください。

> [!NOTE]
> Boolean でないデータ型の場合、値は常に `<enabled/>` で始まります。

#### <a name="boolean-data-type"></a>Boolean データ型

Boolean 型のポリシーの場合は、`<enabled/>` また `<disabled/>` を使用します。

#### <a name="integer-data-type"></a>Integer データ型

値は常に`<enabled/>` 要素から始まり、その後に `<data id="[valueName]" value="[decimal value]"/>` を指定する必要があります。

新しいタブ ページの値の名前と 10 進値を検出するには、次の手順を使用します。

1. 任意の xml エディターを使用して **msedge.admx** を開きます。
2. 設定したポリシー名と一致する name 属性の `<policy>`要素を探します。 "RestoreOnStartup" の場合は、`name="RestoreOnStartup"` を探します。
3. `<elements>` ノードで、設定する値を探します。
4. `<elements>` ノード内の "valueName" 属性に含まれる値を使用します。 "RestoreOnStartup" の場合、"valueName" は "RestoreOnStartup" です。
5. `<decimal>` ノード内の "value" 属性に含まれる値を使用します。 "RestoreOnStartup" で新しいタブ ページを開く場合、値は "5" になります。

起動時に新しいタブ ページを開くには、以下を使用します。<br>
`<enabled/> <data id="RestoreOnStartup" value="5"/>`

#### <a name="list-of-strings-data-type"></a>文字列データ型のリスト

値は常に`<enabled/>` 要素から始まり、その後に `<data id="[listID]" value="[string 1];[string 2];[string 3]"/>` を指定する必要があります。

> [!NOTE]
> "id=" 属性名はポリシー名ではありません (ほとんどの場合はポリシー名と一致します)。 これは、ADMX ファイルに含まれている、\<list> ノードの ID 属性値です。

listID を見つけて URL をブロックするための値を定義するには、次の手順に従います。

1. 任意の xml エディターを使用して **msedge.admx** を開きます。
2. 設定したポリシー名と一致する name 属性の `<policy>`要素を探します。 "URLBlocklist" の場合は、`name="URLBlocklist"` を探します。
3. `<list> node for [listID]` の "id" 属性に含まれる値を使用します。
4. "value" は、セミコロン (;) で区切られた URL のリストです。

たとえば、`contoso.com` および `https://ssl.server.com` へのアクセスをブロックするには、次のように指定します: <br>
`<enabled/> <data id=" URLBlocklistDesc" value="contoso.com;https://ssl.server.com"/>`

#### <a name="dictionary-or-string-data-type"></a>Dictionary または String データ型

値は常に `<enabled/>` から始まり、その後に `<data id="[textID]" value="[string]"/>` を指定する必要があります。

textID を見つけてロケースを設定するための値を定義するには、次の手順に従います。

1. 任意の xml エディターを使用して **msedge.admx** を開きます。
2. 設定したポリシー名と一致する name 属性の `<policy>`要素を探します。 "ApplicationLocaleValue" の場合は、`name="ApplicationLocaleValue"` を探します。
3. `[textID]` に対応する `<text>` ノードの "id" 属性に含まれる値を使用します。
4. "value" をカルチャ コードに設定します。

"ApplicationLocaleValue" ポリシーを使用してロケールを "es-US" に設定するには、次のように指定します: <br>
`<enabled/> <data id="ApplicationLocaleValue" value="es-US"/>`

### <a name="create-the-oma-uri-for-a-recommended-policies"></a>推奨ポリシー用の OMA URI を作成する

推奨ポリシーの URI パスを定義する方法は、構成するポリシーによって異なります。

#### <a name="to-define-the-uri-path-for-a-recommended-policy"></a>推奨ポリシーの URI パスを定義するには

URI パスを定義するには、URI パスの式 (*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`*) と以下の手順を使用します。

1. 任意の xml エディターを使用して **msedge.admx** を開きます。
2. 構成するポリシーがグループに含まれていない場合は、手順 4 に進み、パスから `~<ADMXCategory>` を削除します。
3. 構成するポリシーがグループに含まれている場合:

   - `<ADMXCategory>` を探すには、設定するポリシーを検索します。 検索する際には、ポリシー名に "_recommended" を追加します。 たとえば、"RegisteredProtocolHandlers_recommended” を検索すると、次のような結果になります。

        ```xml
         <policy class="Both" displayName="$(string.RegisteredProtocolHandlers)" explainText="$(string.RegisteredProtocolHandlers_Explain)" key="Software\Policies\Microsoft\Edge\Recommended" name="RegisteredProtocolHandlers_recommended" presentation="$(presentation.RegisteredProtocolHandlers)">
           <parentCategory ref="ContentSettings_recommended"/>
           <supportedOn ref="SUPPORTED_WIN7_V77"/>
           <elements>
             <text id="RegisteredProtocolHandlers" maxLength="1000000" valueName="RegisteredProtocolHandlers"/>
           </elements>
         </policy>
        ```

   - `<parentCategory>` 要素の *ref* 属性の値をコピーします。 "ContentSettings" の場合は、`<parentCategory ref=" ContentSettings_recommended"/>` から "ContentSettings_recommended" をコピーします。
   - `<ADMXCategory>` を *ref* 属性値に置き換えて、URI パス式内の URI パスを作成します。

4. `<PolicyName>`は、"_recommended" が付加されたポリシーの名前です。

#### <a name="oma-uri-path-examples-for-recommended-policies"></a>推奨ポリシーの OMA URI パスの例

次の表に、推奨ポリシーの OMA-URI パスの例を示します。

|              ポリシー               |             OMA-URI                      |
|-----------------------------------|------------------------------------------|
| [RegisteredProtocolHandlers](./microsoft-edge-policies.md#registeredprotocolhandlers)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~ContentSettings_recommended/RegisteredProtocolHandlers_recommended`                        |
| [PasswordManagerEnabled](./microsoft-edge-policies.md#passwordmanagerenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~PasswordManager_recommended/PasswordManagerEnabled_recommended`                        |
| [PrintHeaderFooter](./microsoft-edge-policies.md#printheaderfooter)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Printing_recommended/PrintHeaderFooter_recommended`                        |
| [SmartScreenEnabled](./microsoft-edge-policies.md#smartscreenenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~SmartScreen_recommended/SmartScreenEnabled_recommended`                        |
| [HomePageLocation](./microsoft-edge-policies.md#homepagelocation)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/HomepageLocation_recommended`                        |
| [ShowHomeButton](./microsoft-edge-policies.md#showhomebutton)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/ShowHomeButton_recommended`                        |
| [FavoritesBarEnabled](./microsoft-edge-policies.md#favoritesbarenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~/FavoritesBarEnabled_recommended`                        |

### <a name="oma-uri-examples"></a>OMA-URI の例

OMA-URI の例を URI パス、型、値の例と共に示します。

#### <a name="boolean-data-type-examples"></a>Boolean データ型の例

*[ShowHomeButton](./microsoft-edge-policies.md#showhomebutton):*

| フィールド   | 値                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 名前    | Microsoft Edge: ShowHomeButton                                                       |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton` |
| 型    | String                                                                               |
| 値   | `<enabled/>`                                                                          |

*[DefaultSearchProviderEnabled](./microsoft-edge-policies.md#defaultsearchproviderenabled):*

| フィールド   | 値                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 名前    | Microsoft Edge: DefaultSearchProviderEnabled                                         |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~DefaultSearchProvider/DefaultSearchProviderEnabled`    |
| 型    | String                                                                               |
| 値   | `<disable/>`                                                                          |

### <a name="integer-data-type-examples"></a>Integer データ型の例

*[AutoImportAtFirstRun](./microsoft-edge-policies.md#autoimportatfirstrun):*

| フィールド   | 値                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 名前    | Microsoft Edge: AutoImportAtFirstRun                                                 |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/AutoImportAtFirstRun`   |
| 型    | String                                                                               |
| 値   | `<enabled/><data id="AutoImportAtFirstRun" value="1"/>`                             |

*[DefaultImagesSetting](./microsoft-edge-policies.md#defaultimagessetting):*

| フィールド   | 値                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 名前    | Microsoft Edge: DefaultImagesSetting                                                 |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ContentSettings/DefaultImagesSetting`    |
| 型    | String                                                                               |
| 値   | `<enabled/><data id="DefaultImagesSetting" value="2"/>`                             |

*[DiskCacheSize](./microsoft-edge-policies.md#diskcachesize):*

| フィールド   | 値                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 名前    | Microsoft Edge: DiskCacheSize                                                        |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`        |
| 型    | String                                                                               |
| 値   | `<enabled/><data id="DiskCacheSize" value="1000000"/>`                               |

#### <a name="list-of-strings-data-type-examples"></a>文字列データ型のリストの例
<!--
*[NotificationsAllowedForUrls](./microsoft-edge-policies.md#NotificationsAllowedForUrls):*

| Field   | Value                                                                                |
|---------|--------------------------------------------------------------------------------------|
| Name    | Microsoft Edge: NotificationsAllowedForUrls                                          |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ContentSettings/NotificationsAllowedForUrls`    |
| Type    | String                                                                               |
| Value   | `<enabled/><data id="NotificationsAllowedForUrlsDesc" value="https://www.contoso.com"/>`<br>For multiple list items: `<data id="NotificationsAllowedForUrlsDesc" value="https://www.contoso.com;[*.]contoso.edu"/>`                           |
-->
*[RestoreOnStartupURLS](./microsoft-edge-policies.md#restoreonstartupurls):*

| フィールド   | 値                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 名前    | Microsoft Edge: RestoreOnStartupURLS                                                 |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/RestoreOnStartupURLs`    |
| 型    | String                                                                               |
| 値   | `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com"/>`<br>複数のリスト項目のがある場合:  `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com&#xF000;2&#xF000;http://www.microsoft.com"/>`  |

*[ExtensionInstallForcelist](./microsoft-edge-policies.md#extensioninstallforcelist):*

| フィールド   | 値                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 名前    | Microsoft Edge: ExtensionInstallForcelist                                            |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`    |
| 型    | String                                                                               |
| 値   | `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000;gbchcmhmhahfdphkhkmpfmihenigjmpp;https://extensionwebstorebase.edgesv.net/v1/crx"/>`                               |

#### <a name="dictionary-and-string-data-type-example"></a>Dictionary および String データ型の例

*[ProxyMode](./microsoft-edge-policies.md#proxymode):*

| フィールド   | 値                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 名前    | Microsoft Edge: ProxyMode                                                            |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ProxyMode/ProxyMode`  |
| 型    | String                                                                               |
| 値   | `<enabled/><data id="ProxyMode" value="auto_detect"/>`                               |

## <a name="configure-microsoft-edge-in-intune-using-admx-ingestion"></a>ADMX インジェストを使用して Intune で Microsoft Edge を構成する

Microsoft Intune を使用して Microsoft Edge を構成する場合は、「[Microsoft Intune を使って Microsoft Edge ポリシー設定を構成する](./configure-edge-with-intune.md)」の説明に従って管理用テンプレート プロファイルを使用する方法をお勧めします。 Intune の Microsoft Edge 管理用テンプレートで現在使用できないポリシーを評価する場合は、[Intune で Windows 10 デバイス用カスタム設定](/intune/configuration/custom-settings-windows-10)を使用して Microsoft Edge を構成できます。

このセクションでは、以下の方法について説明します。

1. [Microsoft Edge ADMX ファイルを Intune に取り込む](#ingest-the-microsoft-edge-admx-file-into-intune)
2. [Intune でカスタムの OMA URI を使用してポリシーを設定する](#set-a-policy-using-custom-oma-uri-in-intune)

> [!IMPORTANT]
> ベスト プラクティスとして、Intune でカスタムの OMA-URI プロファイルと管理テンプレート プロファイルを使用して、同じ Microsoft Edge 設定を構成しないでください。 カスタムの OMA-URI と管理用テンプレート プロファイルの両方を使用して、値が異なる同じポリシーを展開すると、予期しない結果を招く可能性があります。 管理用テンプレート プロファイルを使用する場合は、事前にOMA-URI プロファイルを削除するよう強くお勧めします。

### <a name="ingest-the-microsoft-edge-admx-file-into-intune"></a>Microsoft Edge ADMX ファイルを Intune に取り込む

このセクションでは、Microsoft Edge 管理用テンプレート (**msedge.admx**ファイル) を Intune に取り込む方法について説明します。

> [!WARNING]
> ADMX ファイルは、取り込み前に変更しないでください。

ADMX ファイルを取り込むには、以下の手順を実行します。

1. [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)から Microsoft Edge ポリシー テンプレートフ ァイル (MicrosoftEdgePolicyTemplates.cab) をダウンロードし、内容を展開します。 取り込むファイルは **msedge.admx** です。
2. [Microsoft Azure portal](https://portal.azure.com) にサインインします。
3. _[すべてのサービス]_ から **[Intune]** を選択するか、ポータルの検索ボックスで Intune を検索します。
4. _[Microsoft Intune - 概要]_ で、**[デバイス構成]** | **[プロファイル]** を選択します。
5. 上部のコマンド バーで、**[+ プロファイルの作成]** を選択します。

   ![デバイス プロファイルの作成](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile.png)

6. 以下のプロファイル情報を指定します。

   - **[名前]**: わかりやすい名前を入力します。 この例では、「Microsoft Edge ADMX ingested configuration」です。
   - **[説明]**: プロファイルの説明を入力します (オプション)。
   - **[プラットフォーム]**: [Windows 10 以降] を選択します。
   - **[プロファイルの種類]**: [カスタム] を選択します。

7. **[カスタム OMA-URI 設定]** で **[追加]** をクリックして ADMX インジェストを追加します。

   ![OMA URI 用にインジェストを追加する](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-add-omauri.png)

8. **[行の追加]** で、以下の情報を指定します。

   - **[名前]**: わかりやすい名前を入力します。 この例では、「Microsoft Edge ADMX ingestion」を使用します。
   - **[説明]**: 設定の説明を入力します (省略可能)。
   - **[OMA-URI]**: 「*./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/Edge/Policy/EdgeAdmx*」と入力します。
   - **[データ型]**: [String] を選択します。
   - **[値]**: この入力領域は、**[データ型]** を選択した後に表示されます。 手順 1. で抽出した Microsoft Edge ポリシー テンプレート ファイルから msedge.admx ファイルを開きます。 msedge.admx ファイルから**すべてのテキスト**をコピーし、次のスクリーンショットに示されている **[値]** テキスト領域に貼り付けます。

        ![ADMX インジェストの追加](./media/edge-cfg-with-mdm/configure-edge-intune-mdm-omauri-addrow-ingest.png)

   - **[OK]** をクリックします。

9. **[カスタム OMA-URI 設定]** で、**[OK]** をクリックします。
10. **[プロファイルの作成]** で、**[作成]** をクリックします。 次のスクリーンショットは、新しく作成されたプロファイルに関する情報を示しています。

    ![新しいデバイス プロファイル情報 ](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-done.png)

<!--
> [!NOTE]
> You can use the preceding steps to ingest the msedgeupate.admx policy template file.
-->
### <a name="set-a-policy-using-custom-oma-uri-in-intune"></a>Intune でカスタムの OMA URI を使用してポリシーを設定する

> [!NOTE]
> このセクションの手順を使用する前に、「[Microsoft Edge ADMX ファイルを Intune に取り込む](#ingest-the-microsoft-edge-admx-file-into-intune)」で説明されている手順を完了する必要があります。

1. [Microsoft Azure portal](https://portal.azure.com) にサインインします。
2. _[すべてのサービス]_ から **[Intune]** を選択するか、ポータルの検索ボックスで Intune を検索します。
3. **[Intune]**>**[デバイスの構成]**>**[プロファイル]** に移動します。
4. "Microsoft Edge ADMX ingested configuration" プロファイルか、独自にプロファイルに使用した名前を選択します。
5. Microsoft Edge ポリシー設定を追加するには、**[カスタム OMA-URI 設定]** を開く必要があります。 **[管理]**、**[プロパティ]**、**[設定]** の順にクリックします。

    ![プロファイル設定の構成](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings.png)

6. **[カスタム OMA-URI 設定]** で、**[追加]** をクリックします。

    ![OMA-URI 設定に行を追加する](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings-add-row.png)

7. **[行の追加]** で、以下の情報を指定します。

   - **[名前]**: わかりやすい名前を入力します。 構成するポリシー名を使用することをお勧めします。 この例では、"ShowHomeButton" を使用します。
   - **[説明]** (オプション): 設定の説明を入力します。
   - **[OMA-URI]**: ポリシーの OMA-URI を入力します。 例として "ShowHomeButton" ポリシーの場合は、"*./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton*" を使用します。
   - **[データ型]**: ポリシー設定のデータ型を選択します。 "ShowHomeButton" ポリシーの場合は、"String" を使用します。
   - **[値]**: ポリシー用に構成する設定を入力します。 「ShowHomeButton」の例では、「\<enabled/>」と入力します。 次のスクリーン ショットは、ポリシーを構成する場合の設定を示しています。

        ![[行の追加] の OMA-URI 設定](./media/edge-cfg-with-mdm/configure-edge-mdm-custom-omauri-setting.png)

   - **[OK]** をクリックします。

8. **[カスタム OMA-URI 設定]** で、**[OK]** をクリックします。
9. **[Microsoft Edge ADMX ingested configuration - プロパティ]** プロファイル (または、独自に使用した名前) で、**[保存]** をクリックします。

プロファイルが作成され、プロパティが設定されたら、[Microsoft Intune でプロファイルを割り当てる](/intune/configuration/device-profile-assign)必要があります。

#### <a name="confirm-that-the-policy-was-set"></a>ポリシーが設定されたことを確認する

作成したプロファイルが Microsoft Edge ポリシーで使用されていることを確認するには、次の手順に従います  ("Microsoft Edge ADMX ingested configuration" プロファイルの例で割り当てたデバイスに、Microsoft Intune からポリシーが伝達されるまで、多少時間がかかる場合があります)。

1. Microsoft Edge を開き、*edge://policy* に移動します。
2. **[ポリシー]** ページで、プロファイルに設定したポリシーが一覧に含まれているかどうかを確認します。
3. ポリシーが表示されていない場合の対処方法については、「[Windows 10 での MDM エラーの診断](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10)」または「[ポリシー設定のトラブルシューティング](#troubleshoot-a-policy-setting)」をご覧ください。

#### <a name="troubleshoot-a-policy-setting"></a>ポリシー設定のトラブルシューティング

Microsoft Edge ポリシーが有効にならない場合は、次の手順をお試しください。

ターゲット デバイス (Microsoft Intune でプロファイルを割り当てたデバイス) で *edge://policy* ページを開き、ポリシーを検索します。 *edge://policy* ページにポリシーがない場合は、次の操作を実行します。

- ポリシーがレジストリに保存されており、正しく定義されていることを確認する。 ターゲット デバイスでopen the Windows 10 レジストリエディターを開きます (**Windows キー + r** キーを押し、「*regedit*」と入力して **Enter** キーを押します)。ポリシーが、*\Software\Policies\ Microsoft\Edge* パスに正しく定義されていることを確認します。 適切なパスにポリシーがない場合は、ポリシーがデバイスに正しくプッシュされていません。
- OMA-URI パスが正しく、値が有効な XML 文字列であることを確認する。 いずれかに誤りがあれば、ポリシーがターゲット デバイスにプッシュされません。

トラブルシューティングのヒントについては、「[Microsoft Intune をセットアップする](/intune/fundamentals/setup-steps)」と「[デバイスの同期](/intune/remote-actions/device-sync)」をご覧ください。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Intune を使って Microsoft Edge ポリシー設定を構成する](configure-edge-with-intune.md)
- [モバイル デバイス管理](/windows/client-management/mdm/)
- [Intune で Windows 10 デバイスにカスタム設定を使用する](/intune/configuration/custom-settings-windows-10)
- [Win32 およびデスクトップ ブリッジ アプリ ポリシーの構成](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)
- [ADMX ベースのポリシーについて](/windows/client-management/mdm/understanding-admx-backed-policies)