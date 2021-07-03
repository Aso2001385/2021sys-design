```uml
@startuml
center header <size:20><b>メイン</b></size>
[*] --> トップページ
トップページ: 商品一覧
トップページ --> メニューバー
state メニューバー {
メニューバー: ID/PASS入力でログイン
 商品一覧 --> [*]
 ||
 カートの中 --> [*]
 ||
 登録情報 --> [*]
 hnote across: ログイン処理
}
メニューバー --> backpoint
backpoint --> メニューバー
backpoint --> [*]

@enduml
```
