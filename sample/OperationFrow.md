```uml 
@startuml 
center header <size:20><b>メイン処理</b></size>

opt ログイン
 hnote across: ログイン処理
end

loop 購入するまで
 loop 商品を見つけるまで
  ユーザー -> ユーザー:商品サーチ
 end
 
 opt カート投入
  ユーザー -> Webサーバー:更新申請
  Webサーバー -> Webサーバー:更新処理
  Webサーバー ->ユーザー:内容更新
 end
 opt キャンセル
  ユーザー -> Webサーバー:カート内商品削除(更新申請)
  Webサーバー -> Webサーバー:更新処理
  Webサーバー ->ユーザー:内容更新
 end

end


Webサーバー -> DBサーバー:カート情報
DBサーバー -> DBサーバー:購入処理
DBサーバー -> Webサーバー:購入情報
Webサーバー ->ユーザー:購入メッセージの表示

opt ログアウト
 hnote across: ログアウト処理
end
 


@enduml
```

```uml

@startuml
center header <size:20><b>ログイン処理</b></size>

 opt 未登録
  ユーザー -> Webサーバー:ユーザー登録
  Webサーバー -> DBサーバー:ユーザー登録
  DBサーバー -> DBサーバー:登録処理

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

 alt 認証失敗
  Webサーバー ->ユーザー:失敗メッセージの表示
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
