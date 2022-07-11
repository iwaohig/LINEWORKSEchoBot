# LINEWORKSEchoBot
LINE WORKS オウム返し Bot が試せる Power Automate のサンプル フロー パッケージを用意しました。

https://github.com/iwaohig/LINEWORKSEchoBot

LINEWORKSEchoBot_20220626103039.zip ファイルをダウンロードしてください。

## Power Automate カスタム コネクタの設定
以下の URL の記事の手順で、Power Automate にカスタム コネクタを設定してください。

TITLE: LINE WORKS トーク Bot 用 Power Automate カスタム コネクタ (OAuth 認証対応) LINE WORKS API 2.0

URL: https://qiita.com/iwaohig/items/4c47a2a1aabe2cb864a8

## LINE WORKS の Bot を追加
### Developer Console の設定

LINE WORKS Developer Console にログインします。

https://developers.worksmobile.com/jp/console/bot/view

[Bot] のページで、[登録] ボタンをクリック。

![l_1517737_1955_df81352d099d4b5a327a5caaa633e9dd.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/5f2eddb4-a19d-73f9-4d53-2ad82d309a3c.png)

[Bot登録] のページが表示されます。

![l_1517737_1956_fc6efb48184fa5553193bd4412d0fe0d.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/07eade4b-2d3b-166e-0741-f881f9ff4308.png)


以下のとおり、入力します。

 Bot名  : 任意の名前 
 「説明」: 任意の説明文

![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/c0e6f45f-5cf4-ed2b-e9d2-157fd5ce61dc.png)

"API Interface" : API 2.0
"固定メニュー" は設定しません。

![l_1517737_1957_693879f0e21c9cb1dc1b64e0eeb03522.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/a868c823-1780-d899-1ac7-bbedcd32d6cb.png)

"Callback URL" を [On] にします。
以下の URL を入力します。なお、この URL は一時的なダミーです。後で書き換えます。

```
https://example.com
```

"メンバーが送信可能なメッセージタイプ" で [テキスト] を選択します。

![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/16c9d546-a4f2-c85c-c5a6-385208dec463.png)

[Botポリシー]: 変更しません。

[管理者] の [主担当]: 自分の ID を [名前またはメールアドレスを検索] で検索して指定

![l_1517737_1967_7f41695af509cb7c42c883fc569e17b5.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/d787ad10-5136-143d-09ca-1b33dc5b1168.png)

[管理者] の [副担当]: 設定しません。

[保存] ボタンをクリック。

![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/0acad3c4-9d01-caf2-d392-b8d739dad3f2.png)

Bot ID が付与されます。この後の手順で必要なのでメモしましょう。

![l_1517737_1958_42f7fb5a1cccbf8c575397a085568f5a.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/b176c655-ec06-98ca-d33d-9956417059eb.png)

### 管理画面の設定
LINE WORKS の管理画面にアクセスします。

https://common.worksmobile.com/p/admin

#### Bot 追加
[サービス] - [Bot] のページにアクセスし、[Bot追加] ボタンをクリック。

![l_1517737_1959_407c5ba8a154eb4c9aee393e33d7f9c2.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/8071fc60-42bb-b38f-9e0f-217ddf09d7b3.png)

Bot を選択して [Bot追加] ボタンをクリック。

![l_1517737_1960_9e0f802a56b38b72d64cbd95a8086b76.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/c1ec8a6c-940e-1dd3-ffc0-2a522ad4c554.png)

Bot が追加されたら、[前に戻る] をクリック。

![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/7c25e728-6226-ad01-63e1-471d54f80d0a.png)

追加された Bot をクリック。

![l_1517737_1961_46613f4eb5f398b7894fcf13396d9b5b.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/952b2570-d0e8-7459-d323-6234d4af1095.png)


[修正] ボタンをクリック。

![l_1517737_1962_579460db22323d760f6aab54d492827e.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/b7a211b0-e4f3-1cc9-74b0-cb1ec3160d91.png)


"使用権限" で [メンバー指定] を選択し、自分を指定。

"公開設定" でトグルスイッチを [On] に設定。

[保存] ボタンをクリック。

![l_1517737_1963_248ecae80bd13a4894b6438f6bb80f6d.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/a943e5f7-c18c-8e3c-8d02-07bd9742a63a.png)

### サービス通知トークルーム確認
使用権限で指定したユーザーのサービス通知トークルームに、Bot 追加の通知が届きます。[Botを利用] のボタンをタップ。

![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/ea04ffb1-745e-1a66-6336-485ce4791628.png)

### Bot の利用開始
登録した Bot が表示されます。[利用開始] をタップ。

![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/537e342b-2f76-3f22-d15f-ed9a883947aa.png)

Bot との 1:1 トークルームが開きます。

![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/c2057013-955a-0b22-27d2-acddc1f480f0.png)

## Power Automate カスタム コネクタの接続の作成

Power Automate カスタム コネクタの一覧で、追加したカスタム コネクタの [+] をクリックして "接続の作成" を行います。

![l_1517737_1942_ed0a056eea9b4c3fe2e652fa89cbc6f2.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/7bdce782-47e1-3410-1863-764b40a897bc.png)

サブ ウィンドウで LINE WORKS の認証画面が開きます。LINE WORKS のアカウントでログインします。

![l_1517737_1943_4114d1dd5150822f7f6f4a09818d7d52.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/77acd184-a50e-7654-c37e-a7e127a12704.png)

接続が作成されました。

![l_1517737_1944_3dcd51ba12399e78df74fb81aec4ddff.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/bbf6e142-43ba-9d65-33e1-d6d54c9136a5.png)

## Power Automate フローのインポート
[マイ フロー] で [← インポート] をクリックします。

![l_1517737_1938_1ac757c5a79c625e768b24f638780d88.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/c8649e43-6157-31e4-8ba2-6fefef830b5c.png)

[アップロード] ボタンをクリックし、ダウンロードしておいた zip ファイルを指定します。

![l_1517737_1939_1bf53406f87724d92d815fe9633f249a.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/dfa3bf96-392d-6f5d-72ba-481edefa7214.png)

![l_1517737_1940_d8e1cba373a208d123a5c9aa275f1b85.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/a6eb6b9c-6ef5-2477-d42b-b5b5de8157b7.png)

アップロードされました。

![l_1517737_1941_51a7c41d389183e83c7677b7f65d208b.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/de11ce43-9055-d42b-a643-347918f5af4a.png)

[関連リソース] の [インポートの設定] を行います。
[インポート時に選択する] をクリック。

![l_1517737_1964_5afbe3a37299b1a878f0942419b3b439.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/a734cccd-d983-2638-f2cc-3290840beb2d.png)

一覧に表示されるコネクタを選択します。

![l_1517737_1946_7e767710ac0b13389e6d338b6c1103b4.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/6eede885-6c06-7551-379c-9cf0201f382f.png)

[インポート時に選択する] をクリック。

![l_1517737_1965_deeff49e5fb511f9f06c2bb851cafd81.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/05904c5f-1b2b-049e-067e-8bd3c34d90cc.png)

一覧に表示される接続を選択します。

![l_1517737_1947_775cb89522caec877a34aeb25eca1999.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/27d958e5-a60c-1630-eda5-1db71d9a5a80.png)

インポートを実行します。

![l_1517737_1948_54647ae2f36ea7dacc1839783b32485a.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/538cc9cb-c904-f27c-508e-c911c82aed32.png)

インポートが完了しました。[開く] をクリックします。

![l_1517737_1949_076cd28f27548319c1ab402c7daa1486.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/974a3f42-3419-070c-82a4-ff9616c61766.png)

### フローの編集
[HTTP 要求の受信時] をクリックします。

![l_1517737_1951_9366787137a128c79f83e285af0f0eb6.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/9fc35932-b9cc-c186-0e7a-dc4ed458a509.png)

[HTTP POST の URL] をコピー ボタンでコピーします。

![l_1517737_1952_4c52982f874b9f7d988efbfce98260fe.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/534fbbe5-0ad0-996d-e695-e5c39d4567df.png)

LINE WORKS Developer Console で登録した Bot の Callback URL を置き換えます。

![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/72449cb2-86d7-4bf1-ab3e-4fea3d6f333b.png)

[ユーザーにテキスト メッセージを送信する] をクリックします。

![l_1517737_1953_b32ca86b0a64503fc6eb81e4fe5b00b6.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/63505c70-ffe3-ddaf-26c5-2d73b7da62e5.png)

botId を LINE WORKS Developer Console で付与されたものに置き換えます。

![l_1517737_1954_4e1706f2cf046c3c48534ff7c585b529.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/396107/a7ed109a-12ac-13ba-0335-9df35734f799.png)

## 動作確認
LINE WORKS で Bot に話しかけると、オウム返しされます。


