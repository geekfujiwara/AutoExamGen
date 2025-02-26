# AutoExamGen

![image](https://github.com/user-attachments/assets/4a305065-35c8-4ed9-bf36-9e0c28a22d6a)


https://github.com/user-attachments/assets/1638a3aa-3dda-416a-b0a0-fb62da1d672b

### 研修プログラム構成アプリ

研修プログラム名をつけます。研修プログラム名と合格点などに基づき説明文は自動的に作成されます。

![image](https://github.com/user-attachments/assets/19c4cb59-5f34-48ac-b43c-33b513ad9b65)

研修プログラムの内容をより精度良くするために、作成したい研修プログラムに関係するファイルをアップロードします。また見やすいようにサムネイル画像を任意で添付します。

> [!Note]
> 添付ファイルは現時点では必須の項目になっています。 研修作成ボタンの DisplayMode で制御しているのでボタンを押すことができない仕様になっています。

![image](https://github.com/user-attachments/assets/6cb621f0-f8c3-41f9-9423-5f61cc298564)

ファイルに基づきプログラム案を作成します。環境にもよりますが、約1分ほど時間がかかります。

![image](https://github.com/user-attachments/assets/312b33ef-f7be-4066-8db2-39cc417b8e68)

生成されたプログラムは Power Automate にデータが渡され Dataverse に登録されます。

研修プログラムが作成されま表示されます。すでにDataverseに登録されている状況です。

![image](https://github.com/user-attachments/assets/210d3c11-c829-4b04-a381-1c45af9b2a8b)

問題を必要に応じて修正することができます。また、問題追加ボタンで追加して、研修用の動画を追加することもできます。

![image](https://github.com/user-attachments/assets/97f2a7db-15f1-41af-98af-827e414fbc04)

出題モードがURLの場合、動画を追加することが出来ます。YouTubeのリンクを貼ってください。

![image](https://github.com/user-attachments/assets/bdfb1b05-06dc-4b69-a6a1-7c430bcb5f32)

入力した後カーソルを動かすと即座に Dataverse に登録されます。

出題モードは、URLの他に single-choice、multi-choice が用意されています。複数選択させる問題の場合は multi-choice を利用します。正解がひとつだけの場合は single-choice を利用します。

![image](https://github.com/user-attachments/assets/77bd4f30-2e8a-457a-a448-4db08d067a1e)

例えばこのように 出題モードを single-choiceとした場合、選択肢を追加することが出来ます。

![image](https://github.com/user-attachments/assets/47f70f09-c591-483d-8c83-0a4d8fb09d53)

選択肢や問題はそれぞれゴミ箱ボタンで削除できます。

![image](https://github.com/user-attachments/assets/08205e40-b0a4-4370-8097-b85cc29b2eed)

### 研修プログラムの翻訳

作成したプログラムを別の言語に翻訳することができます。

コンボボックスで言語を選びます。一度に多数の言語を選ぶことが出来ます。Power Automate にて非同期的に出力されるので Power Apps へのパフォーマンスの影響はありません。

![image](https://github.com/user-attachments/assets/986539e0-6515-4950-9d21-58cbd79ccfd9)

> [!Note]
> 現在、翻訳したプログラムの更新には対応していません。翻訳したプログラムを更新したいときは一度翻訳したプログラムをモデル駆動型アプリのメニューから削除してから行ってください。
>
> 本機能は次のアップデートで対応する予定です。アップデートに備えるためにソリューションのインポートはマネージドソリューションを利用してください。

### 研修プログラム実行アプリ

作成した研修プログラムを実行することが出来る、こちらはエンドユーザー向けのアプリです。

![image](https://github.com/user-attachments/assets/6672dca4-96a7-4c15-91f9-9793340aaa5e)

多言語に翻訳していれば、ユーザーの既定の言語に翻訳されて表示されます。ドロップダウンから希望の言語に変更することも出来ます。

![image](https://github.com/user-attachments/assets/58961c0f-7b26-4419-81b4-62aee01872a5)

問題の内容についても翻訳されています。

![image](https://github.com/user-attachments/assets/c6343247-77f9-4df5-900b-fca79346a65c)

保存しているデータだけでなく、アプリのラベルも多言語に対応しています。これにより、エンドユーザーが利用したい言語を利用して研修を受けることができます。

![image](https://github.com/user-attachments/assets/2829ffb9-3c26-419f-b05c-989e6d597951)

## 業務での利用イメージ

研修プログラムを生成します。

多言語で出力します。

生成した研修プログラムを関係のある部署に割り当てます。

これにより部署に所属するユーザーには研修プログラムがアサインされます。

エンドユーザーは、アサインされた研修プログラムを確認できるようになります。合格点を取り研修プログラムを完了すると完了した研修プログラムのリストに移動します。

## インストール

ソリューションが提供されています。ソリューションを入手して利用したい環境にインポートします。ソリューションにはセキュリティロールが用意されています。

研修プログラムアプリで利用しているテーブルは正規化されています。カスタムテーブルは以下のテーブルがあります。




