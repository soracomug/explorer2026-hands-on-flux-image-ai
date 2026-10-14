# 1. SAMユーザーの作成

まず、SORACOM ユーザーコンソールにログインし、ファイルアップロード権限を持つ SAM ユーザーを作成します。

1. SORACOM ユーザーコンソールにログインします。
2. 右上のメニューから「セキュリティ」を選択します。このとき **オペレーターID** も確認し、メモしておいてください。

   ![セキュリティメニューを選択](images/steps/sam-01-security.png)

3. 「SAMユーザー」を選択し、「SAMユーザーを作成」ボタンをクリックします。

   ![SAMユーザーを作成](images/steps/sam-02-create-user.png)

4. 名前（例: `handson-user`）を入力し、「作成」ボタンをクリックします。

   ![ユーザー名を入力して作成](images/steps/sam-03-input-name.png)

5. 作成したユーザーの名前（例: `handson-user`）をクリックします。

   ![作成したユーザーをクリック](images/steps/sam-04-click-user.png)

6. 「権限設定」で「直接指定」を選択し、以下の JSON を貼り付けて「保存」をクリックします。

   ![権限設定](images/steps/sam-05-permission.png)

   ```json
   {
     "statements": [
       {
         "effect": "allow",
         "api": [
           "FileEntry:putFile"
         ]
       }
     ]
   }
   ```

   > これにより、Harvest Files への書き込み権限のみが付与されます。

7. 「認証設定」を選択し、「ログインパスワード」の右側の「+」ボタンをクリックします。

   ![ログインパスワードを追加](images/steps/sam-06-password-add.png)

8. 任意のパスワードを入力し、「設定」ボタンをクリックします。**このパスワードは後で使うのでメモ**してください。

   ![パスワードを設定](images/steps/sam-07-password-set.png)

> このステップで作成した「SAMユーザー名」「パスワード」、そして自分の「オペレーターID」を次のステップで使います。

---

[← 0. はじめに](./00-introduction.md) ｜ [目次](./README.md) ｜ [2. アプリでのログインとファイルアップロード →](./02-upload.md)
