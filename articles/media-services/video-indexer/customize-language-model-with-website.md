---
title: Video Indexer Web サイトを使用して言語モデルをカスタマイズする
titleSuffix: Azure Media Services
description: Video Indexer Web サイトを使用して言語モデルをカスタマイズする方法について説明します。
services: media-services
author: anikaz
manager: johndeu
ms.service: media-services
ms.subservice: video-indexer
ms.topic: article
ms.date: 05/15/2019
ms.author: anzaman
ms.openlocfilehash: 8917a3ac302d18337d79bffce69bad108667b4d2
ms.sourcegitcommit: 2ec4b3d0bad7dc0071400c2a2264399e4fe34897
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "80128082"
---
# <a name="customize-a-language-model-with-the-video-indexer-website"></a>Video Indexer Web サイトを使用して言語モデルをカスタマイズする

Video Indexer では、カスタム言語モデルを作成し、適応テキストをアップロードすることで音声認識をカスタマイズすることができます。適応テキストとは、エンジンを適応させたいボキャブラリがあるドメインから取得したテキストのことです。 モデルをトレーニングすると、適応テキスト内に含まれる新しい単語が認識されるようになります。

カスタム言語モデルの詳細な概要とベスト プラクティスについては、「[Customize a Language model with Video Indexer](customize-language-model-overview.md)」(Video Indexer を使って言語モデルをカスタマイズする) をご覧ください。

このトピックで説明しているように、Video Indexer の Web サイトを使用すると、アカウント内にカスタム言語モデルを作成し、編集することができます。 また、API を使用することもできます (「[API を使用して言語モデルをカスタマイズする](customize-language-model-with-api.md)」で説明しています)。

## <a name="create-a-language-model"></a>言語モデルの作成

1. [Video Indexer](https://www.videoindexer.ai/) の Web サイトに移動してサインインします。
2. アカウント内のモデルをカスタマイズするには、ページの右上隅にある **[コンテンツ モデルのカスタマイズ]** ボタンを選択します。

   ![Video Indexer でコンテンツ モデルをカスタマイズする](./media/content-model-customization/content-model-customization.png)

3. **[言語]** タブを選択します。

    サポートされている言語の一覧が表示されます。

    ![Video Indexer の言語モデルの一覧](./media/customize-language-model/customize-language-model.png)

4. 目的の言語の下で、 **[モデルを追加]** を選択します。
5. 言語モデルの名前を入力し、Enter キーを押します。

    この手順によってモデルが作成され、モデルにテキスト ファイルをアップロードするオプションが提供されます。

6. テキスト ファイルを追加するには、 **[ファイルの追加]** を選択します。 ファイル エクスプローラーが開かれます。

7. テキスト ファイルの場所に移動し、ファイルを選択します。 言語モデルには複数のテキスト ファイルを追加することができます。

    言語モデルの右側にある **[...]** ボタンを選択し、 **[ファイルの追加]** を選択してテキスト ファイルを追加することもできます。

8. テキスト ファイルのアップロードが完了したら、緑色の **[トレーニング]** オプションを選択します。

    ![Video Indexer で言語モデルをトレーニングする](./media/customize-language-model/train-model.png)

トレーニング プロセスには数分かかることがあります。 トレーニングが完了すると、モデルの横に **[トレーニング済み]** と表示されます。 ユーザーは、モデル内のファイルをプレビュー、ダウンロード、削除することができます。

![Video Indexer でのトレーニング済み言語モデル](./media/customize-language-model/preview-model.png)

### <a name="using-a-language-model-on-a-new-video"></a>新しいビデオに言語モデルを使用する

新しいビデオに対して言語モデルを使用するには、以下のいずれかの操作を行います。

* ページ上部の **[アップロード]** ボタンを選択します。

    ![[アップロード] ボタン、Video Indexer](./media/customize-language-model/upload.png)

* 円の中にオーディオ ファイルまたはビデオ ファイルをドロップするか、ファイルを参照します。

    ![メディア ファイルのアップロード、Video Indexer](./media/customize-language-model/upload2.png)

**ビデオのソース言語**を選択するオプションが使用可能になります。 ドロップダウン リストを選択し、一覧から、作成した言語モデルを選択します。 一覧には、言語モデルの言語と、それに付けた名前 (かっこ内) が表示されます。

ページ下部の **[アップロード]** オプションを選択すると、その言語モデルを使用して、新しいビデオにインデックスが作成されます。

### <a name="using-a-language-model-to-reindex"></a>言語モデルを使用してインデックスを再作成する

言語モデルを使用してコレクション内のビデオのインデックスを再作成するには、[Video Indexer](https://www.videoindexer.ai/) ホーム ページの **[アカウントのビデオ]** に移動し、インデックスを再作成するビデオの名前の上にマウス ポインターを置きます。

ビデオを編集するオプション、ビデオを削除するオプション、およびビデオのインデックスを再作成するオプションが表示されます。 ビデオのインデックスを再作成するオプションを選択します。

![Video Indexer でインデックスを再作成する](./media/customize-language-model/reindex1.png)

ビデオのインデックスの再作成に使用する、**ビデオのソース言語**を選択するオプションが使用可能になります。 ドロップダウン リストを選択し、一覧から、作成した言語モデルを選択します。 一覧には、言語モデルの言語と、それに付けた名前 (かっこ内) が表示されます。

![ビデオのソース言語を選択する—Video Indexer でビデオのインデックスを再作成する](./media/customize-language-model/reindex.png)

**[インデックスの再作成]** ボタンを選択すると、その言語モデルを使用してビデオのインデックスが再作成されます。

## <a name="edit-a-language-model"></a>言語モデルの編集

言語モデルは、名前を変更したり、ファイルを追加したり、ファイルを削除したりして編集することができます。

言語モデルに対してファイルを追加または削除する場合、緑色の **[トレーニング]** オプションを選択して、モデルを再度トレーニングする必要があります。

### <a name="rename-the-language-model"></a>言語モデルの名前変更

言語モデルの右側にある省略記号 ( **[...]** ) ボタンを選択し、 **[名前の変更]** を選択すると、言語モデルの名前を変更できます。

新しい名前を入力し、Enter キーを押します。

### <a name="add-files"></a>ファイルの追加

テキスト ファイルを追加するには、 **[ファイルの追加]** を選択します。 ファイル エクスプローラーが開かれます。

テキスト ファイルの場所に移動し、ファイルを選択します。 言語モデルには複数のテキスト ファイルを追加することができます。

言語モデルの右側にある省略記号 ( **[...]** ) ボタンを選択し、 **[ファイルの追加]** を選択すると、テキスト ファイルも追加できます。

### <a name="delete-files"></a>ファイルの削除

言語モデルからファイルを削除するには、テキスト ファイルの右側にある省略記号 ( **[...]** ) ボタンを選択し、 **[削除]** を選択します。 新しいウィンドウが開き、削除は元に戻せないというメッセージが表示されます。 新しいウィンドウで **[削除]** オプションを選択します。

これにより、言語モデルからファイルが完全に削除されます。

## <a name="delete-a-language-model"></a>言語モデルの削除

アカウントから言語モデルを削除するには、言語モデルの右側にある省略記号 ( **[...]** ) ボタンを選択し、 **[削除]** を選択します。

新しいウィンドウが開き、削除は元に戻せないというメッセージが表示されます。 新しいウィンドウで **[削除]** オプションを選択します。

これにより、アカウントから言語モデルが完全に削除されます。 削除された言語モデルを使用していたすべてのビデオでは、ユーザーがビデオのインデックスを再作成するまで同じインデックスが保持されます。 ビデオのインデックスを再作成すると、ビデオに新しい言語モデルを割り当てることができます。 それ以外の場合、Video Indexer では既定のモデルを使用して、ビデオのインデックスが再作成されます。

## <a name="customize-language-models-by-correcting-transcripts"></a>トランスクリプトの変更による言語モデルのカスタマイズ

Video Indexer では、ユーザーがそのビデオの文字起こしに対して行う実際の変更に基づく、言語モデルの自動カスタマイズがサポートされています。

1. トランスクリプトを変更するには、自分のアカウントのビデオから、編集したいビデオを開きます。 **[タイムライン]** タブを選択します。

    ![言語モデルをカスタマイズする、[タイムライン]タブ—Video Indexer](./media/customize-language-model/timeline.png)

1. 鉛筆アイコンを選択して、文字起こしのトランスクリプトを編集します。

    ![言語モデルをカスタマイズする、文字起こしの編集—Video Indexer](./media/customize-language-model/edits.png)

    Video Indexer によって、ビデオの文字起こし内の変更した行がすべてキャプチャされ、"From transcript edits" というテキスト ファイルにそれらが自動的に追加されます。 これらの編集は、このビデオにインデックスを付けるために使用された特定の言語モデルを再トレーニングするために使用されます。
    
    このビデオのインデックス作成時に言語モデルを指定しなかった場合、このビデオのすべての編集内容は、ビデオの検出された言語内の、"アカウント適応" と呼ばれる既定の言語モデルに格納されます。
    
    同じ行に対して複数の編集が加えられた場合、変更された行の最新バージョンのみが、言語モデルの更新に使用されます。  
    
    > [!NOTE]
    > カスタマイズに使用されるのは、テキストの変更のみです。 実際の単語に関係しない変更 (句読点やスペースなど) は含められません。
    
1. [コンテンツ モデルのカスタマイズ] ページの [言語] タブに、トランスクリプトの変更が表示されます。

    ![言語モデルをカスタマイズする—Video Indexer](./media/customize-language-model/customize.png)

   自分の各言語モデルの "From transcript edits" ファイルを確認するには、そのファイルを選択して開きます。

    ![From transcript edits—Video Indexer](./media/customize-language-model/from-transcript-edits.png)

## <a name="next-steps"></a>次のステップ

[API を使用して言語モデルをカスタマイズする](customize-language-model-with-api.md)
