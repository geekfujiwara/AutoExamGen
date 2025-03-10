# AutoExamGen
## ソリューションの構成
* 生成AIを用いてドキュメントから研修プログラムを作成し、ユーザーに作成した研修プログラムを配布して合否を管理します。
* 数クリックで様々な言語に研修プログラムを翻訳します。

![image](https://github.com/user-attachments/assets/1ab80793-ce10-43c9-92d9-4e1b0983428a)

上記のように、ソリューションは主に2つのアプリで構成されています。

* 研修プログラム構成アプリ
* 研修プログラム実行アプリ (Training Player)

[ソリューションはこちらから](https://github.com/geekfujiwara/AutoExamGen/releases/tag/AutoExamGen)入手できます。以下では、利用方法やインストール方法について紹介していきます。

### 研修プログラム構成アプリ

研修プログラム構成アプリでは、研修に際してアンケート、動画の登録、選択問題(複数・単一)の作成を行うことが出来ます。

> [!Note]
> 桁数の一致を利用すれば社員番号に利用できます。また、メールの形式を利用すればメールアドレスの入力に利用することが出来ます。

https://github.com/user-attachments/assets/276d96c3-e3a2-4161-81e6-5cb557f6cedb

資料をアップロードすることで研修プログラム名などが提案されます。必要に応じて修正します。

![image](https://github.com/user-attachments/assets/19c4cb59-5f34-48ac-b43c-33b513ad9b65)

> [!Note]
> 添付ファイルは現時点では必須の項目になっています。 研修作成ボタンの DisplayMode で制御しているのでボタンを押すことができない仕様になっています。

![image](https://github.com/user-attachments/assets/6cb621f0-f8c3-41f9-9423-5f61cc298564)

ファイルに基づきプログラム案を作成します。環境にもよりますが、約1分ほど時間がかかります。

![image](https://github.com/user-attachments/assets/312b33ef-f7be-4066-8db2-39cc417b8e68)

生成されたプログラムは Power Automate にデータが渡され Dataverse に登録されます。

研修プログラムが作成され、表示されます。すでにDataverseに登録されている状況です。

![image](https://github.com/user-attachments/assets/210d3c11-c829-4b04-a381-1c45af9b2a8b)

問題を必要に応じて修正することができます。また、問題追加ボタンで追加して、研修用の動画を追加することもできます。

![image](https://github.com/user-attachments/assets/97f2a7db-15f1-41af-98af-827e414fbc04)

出題モードがURLの場合、動画を追加することが出来ます。YouTubeのリンクを貼ってください。

![image](https://github.com/user-attachments/assets/bdfb1b05-06dc-4b69-a6a1-7c430bcb5f32)

入力した後カーソルを動かすと即座に Dataverse に登録されます。

出題モードは、URLの他に `single-choice` 、`multi-choice` が用意されています。複数選択させる問題の場合は `multi-choice` を利用します。正解がひとつだけの場合は `single-choice` を利用します。

![image](https://github.com/user-attachments/assets/f0d1e21a-9ca2-4e2f-b3f8-de6c59163144)


例えばこのように 出題モードを `single-choice` とした場合、選択肢を追加することが出来ます。

![image](https://github.com/user-attachments/assets/47f70f09-c591-483d-8c83-0a4d8fb09d53)

選択肢や問題はそれぞれゴミ箱ボタンで削除できます。

![image](https://github.com/user-attachments/assets/08205e40-b0a4-4370-8097-b85cc29b2eed)

#### 翻訳

グローバルに活動する企業では、一つの言語だけではなく様々な言語に研修プログラムを翻訳する必要があります。このアプリにて一気通貫で翻訳することが出来ます。

作成した研修プログラムを主要な10か国語に翻訳することができます。

> [!Note]
> 生成AIが対応している言語であれば拡張することが出来ますが、実行アプリのラベルも対応する必要があります。現在実行アプリのラベルは10言語に対応しています。後段で説明します。

翻訳先の言語マスタは以下のように自動生成することが出来ます。

https://github.com/user-attachments/assets/cf766adb-ab34-42ed-a132-45fb8166f996

生成した言語マスターを利用して、生成AIにより研修プログラムを一括で多言語に翻訳することができます。

https://github.com/user-attachments/assets/6ef45d29-7049-4a3c-96bd-7eef88086e4a

> [!Note]
> マスターデータとして翻訳先の言語データが用意されていない場合は、一括で生成することが出来ます。その際はこちらのボタンをクリックしてください。Microsoft オンラインサービスで対応している言語のうち主要な10か国語のマスターデータを自動的に作成します。
> ![image](https://github.com/user-attachments/assets/814840ae-e115-4dea-9416-216b6e2bd103)
>
> こちらの機能が利用できるのは言語テーブルにデータが入っていないときです。言語データが残っている場合は一度削除してから実行してください。

コンボボックスで言語を選びます。一度に多数の言語を選ぶことが出来ます。Power Automate にて非同期的に出力されるので Power Apps へのパフォーマンスの影響はありません。

![image](https://github.com/user-attachments/assets/986539e0-6515-4950-9d21-58cbd79ccfd9)

> [!Note]
> すでに同じ研修プログラム翻訳が存在する場合、一度削除され、翻訳データが新規作成されます。


#### 言語ごとの動画の設定

翻訳した言語ごとに動画を変更したいときは以下のように設定することが出来ます。

https://github.com/user-attachments/assets/3f2872ac-1bb1-4287-af92-4adbf8ab06f1

ここまででオリジナルの研修プログラムをデザインすることが出来ました。



### 研修プログラム実行アプリ (Training Player)

研修プログラムが作成できたら、研修プログラムを関係する組織に割り当てして研修を受けさせるようにします。現在このアプリでは、代表的な以下の10言語にラベル上対応しています。必要に応じてラベル言語を追加するようにしてください。

```
    "Japanese", "研修プログラム実行アプリ",
    "English (United States)", "Training Program Execution App",
    "Chinese (Traditional)", "培训 程序 执行 应用",
    "French (France)", "Application Exécution Programme De Formation",
    "German", "Trainingsprogramm Ausführungs App",
    "Italian", "App Esecuzione Programma Di Formazione",
    "Korean", "교육 프로그램 실행 앱",
    "Portuguese", "Aplicativo Execução Programa De Treinamento",
    "Russian", "Приложение Выполнения Программы Обучения",
    "Spanish", "Aplicación Ejecución Programa De Formación"
```

![image](https://github.com/user-attachments/assets/f750d707-2e31-4f04-8beb-fe05d236bc97)


> [!Note]
> 実行用や現場での管理用のユーザーに必要な基本的なセキュリティロールが提供されています。セキュリティロールは後段で説明しています。


最初は日本語で研修プログラムを生成します。その後で指定した複数の言語に一括で翻訳します。



#### 翻訳結果の確認と更新

翻訳した結果を確認したり、修正したりする場合はモデル駆動型アプリにて確認できます。

研修プログラムの翻訳はこちらから確認できます。

![image](https://github.com/user-attachments/assets/7d5ddbd9-0707-4d30-902b-e3b5562b6f26)

問題の翻訳は同じ問題テーブルに保存されています。



言語を切り替えて確認することが出来ます。こちらから任意の言語に切り替えるとすべての翻訳を確認できます。

![image](https://github.com/user-attachments/assets/95a760d7-ca18-47a5-9123-a02f9fc53fcf)



### 研修プログラム実行アプリ

作成した研修プログラムを実行することが出来る、こちらはエンドユーザー向けのアプリです。

![image](https://github.com/user-attachments/assets/6672dca4-96a7-4c15-91f9-9793340aaa5e)

多言語に翻訳していれば、ユーザーの既定の言語に翻訳されて表示されます。ドロップダウンから希望の言語に変更することも出来ます。

![image](https://github.com/user-attachments/assets/58961c0f-7b26-4419-81b4-62aee01872a5)

問題の内容についても翻訳されています。

![image](https://github.com/user-attachments/assets/c6343247-77f9-4df5-900b-fca79346a65c)

保存しているデータだけでなく、アプリのラベルも多言語に対応しています。これにより、エンドユーザーが利用したい言語を利用して研修を受けることができます。

![image](https://github.com/user-attachments/assets/2829ffb9-3c26-419f-b05c-989e6d597951)


## インストール

### 前提条件

* 利用には、Power Apps Premium のライセンスが必要です。
* AI Builder 及び Dataverse を利用しています

### インストール方法

[ソリューションが提供されています](https://github.com/geekfujiwara/AutoExamGen/releases/tag/AutoExamGen)。環境にインポートします。

> [!Note]
> 今後のアップデートに対応するためにマネージドソリューションの利用を推奨します。

![image](https://github.com/user-attachments/assets/9ef0b968-933c-4106-814a-6f8041b9ae20)

Dataverse の接続を必要に応じて作成します。

![image](https://github.com/user-attachments/assets/b9284f17-c1d9-495a-85d5-703d293dc4c8)

暫く待つと環境にソリューションがインポートされます。

インポートされたソリューションに入り、フローが有効になっていることを確認し、ソリューションをすべて公開します。

![image](https://github.com/user-attachments/assets/c06e0fc8-2367-47d5-96c5-43d3edc5aaea)


## セキュリティロール

以下のセキュリティロールを用意しています。

### セキュリティロール名: AutoExamGen Admin
* 説明: ソリューションで利用するデータの完全なアクセスを提供します。
* 権限の詳細: 
![image](https://github.com/user-attachments/assets/6c0c9635-55a5-4a2e-a7c3-5daf4287a3ab)

### セキュリティロール名: AutoExamGen Manager
* 説明: ソリューションで利用するデータの組織配下レベルのアクセスを提供します。
* 権限の詳細: 
![image](https://github.com/user-attachments/assets/c2f8a73e-947f-49a9-85d9-acb346bbe7f8)

### セキュリティロール名: AutoExamGen Player
* 説明: ソリューションで利用するデータのユーザーレベルのアクセスを提供します。
* 権限の詳細: 
![image](https://github.com/user-attachments/assets/8220f841-3cae-41a7-8682-fcecbf5af4d3)

以上、ご参考になれば幸いです。
