# RailsのAPIモードでAPI作成

rails newコマンドの末尾に--apiをつけることでAPIモードでアプリを作成できる。
(APIに必要ない部分をデフォルトで作成しなくなる。)
```
$ rails new blog --api
```

# テスト
適切なAPIはHTTPのレスポンスのステータスコードと実際のデータを含んだレスポンスボディを返す。  
APIによって返されるステータスコードの分類
* 200: OK - リクエストは成功し、レスポンスとともに要求に応じた情報が返される。
* 401: Unauthorized - 認証失敗。認証が必要である。
* 403: Forbidden - 禁止されている。リソースにアクセスすることを拒否された。
* 404: Not Found - 未検出。リソースが見つからなかった。

レスポンスボディ  
GETリクエストの場合は単にリクエストボディに要求したデータが入っているかをテストします。
POST、PUT、 DELETE　リクエストの際にはそれぞれ要求したデータ通りの動きをするかテストします。

(APIのテストは特定のURLに対してデータの要求等をした際の動きをテストするため、インテグレーションテスト(結合テスト)として扱う。)

