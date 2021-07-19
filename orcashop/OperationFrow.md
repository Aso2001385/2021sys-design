```uml 
@startuml 
 center header <size:20><b>メイン処理</b></size>

 opt ログイン
  hnote across: ログイン処理
 end

 loop 購入処理成功まで
  loop 商品を見つけるまで
   hnote across: 商品サーチ処理
  end

  opt カート投入
   ユーザー -> Webサーバー:商品投入(更新申請)
   Webサーバー -> Webサーバー:カート内情報更新処理
   Webサーバー ->ユーザー:カート内情報更新
  end
  opt キャンセル
   ユーザー -> Webサーバー:カート内商品削除(更新申請)
   Webサーバー -> Webサーバー:カート内情報更新処理
   Webサーバー ->ユーザー:カート内情報更新
  end

  opt 購入
   opt 未ログイン
     hnote across: ログイン処理
   end
   ユーザー -> Webサーバー:購入
   Webサーバー -> DBサーバー:カート情報(購入申請)
   DBサーバー -> DBサーバー:購入処理
   DBサーバー -> Webサーバー:購入処理結果
   Webサーバー ->ユーザー:購入メッセージの表示
  end

 end

 opt ログアウト
  hnote across: ログアウト処理
 end
@enduml
```

```uml
@startuml
 center header <size:20><b>ログイン処理</b></size>
 loop ログイン成功まで
  opt 未登録
   ユーザー -> Webサーバー:ユーザー登録
   Webサーバー -> DBサーバー:ユーザー登録
   DBサーバー -> DBサーバー:登録処理
   DBサーバー -> Webサーバー:処理結果

   alt 登録成功
     Webサーバー ->ユーザー:登録メッセージの表示
   else 登録失敗
     Webサーバー ->ユーザー:失敗メッセージの表示
   end
  end

  ユーザー -> Webサーバー:ログイン
  Webサーバー -> DBサーバー:ログイン
  DBサーバー -> DBサーバー:ログイン処理および認証
  DBサーバー -> Webサーバー:認証結果
  
  alt 認証成功
   Webサーバー ->ユーザー:成功表示
  else 認証失敗
   Webサーバー ->ユーザー:失敗表示
  end
 end
  
@enduml
```

```uml
@startuml
 center header <size:20><b>ログアウト処理</b></size>
  ユーザー -> Webサーバー:ログアウト
  Webサーバー -> DBサーバー:ログアウト申請
  DBサーバー -> DBサーバー:ログアウト処理
  DBサーバー -> Webサーバー:ログアウト処理結果
  Webサーバー ->ユーザー:ログアウトメッセージ表示
@enduml
```
```uml
@startuml
 center header <size:20><b>商品サーチ処理</b></size>
 alt 商品一覧

 ユーザー -> Webサーバー:商品一覧閲覧
 Webサーバー -> DBサーバー:全商品情報要求
 DBサーバー -> DBサーバー:商品情報抽出処理
 DBサーバー -> Webサーバー:抽出結果
 Webサーバー -> ユーザー:商品一覧表示

 else 商品検索
  ユーザー -> Webサーバー:商品検索
  alt 商品名
   Webサーバー -> DBサーバー:商品情報要求(商品名送信)
  else カテゴリ
   Webサーバー -> DBサーバー:商品情報要求(カテゴリ送信)
  end
  DBサーバー -> DBサーバー:対象商品情報抽出処理
  DBサーバー -> Webサーバー:抽出結果
  Webサーバー -> ユーザー:対象商品一覧表示
 end
@enduml
