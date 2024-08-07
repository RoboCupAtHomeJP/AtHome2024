<sub>[READMEへ](../../README.md)</sub>

[日本語](./tu_ja.md) | [English](./tu_en.md)

# TidyUp for OPL

参考動画：https://youtu.be/sVmFMCnJf8s

> [!NOTE]  
> この動画は過去に実施された参考動画である．今年度とはルールが異なるため注意すること．

## メインゴール

このタスクでは，ロボットが散らかった部屋の片付けをすることを想定している．事前に物体をどこに片付けるかが指定されているため，ロボットはその情報をもとに所定の場所に片付けていく．その後，別の部屋へ移動し，手を振っている（もしくは，手を上げている）人に，棚から事前に指定された物を提供していく．[WRS（World Robot Summit）2020](https://wrs.nedo.go.jp/wrs2020/challenge/download/Rules/DetailedRules_Partner_EN.pdf)で行われた競技をRoboCup JapanOpen @Home OPL用にアレンジした競技になっている．

**制限時間**：20分（タスク１：15分，タスク２：5分）

## テクニカルフォーカス

このタスクは，既知環境での自律移動，物体認識，物体把持，タスクプランニングなどに焦点を当てている．

## セットアップ

- **ロケーション**：家庭環境を模したアリーナ環境が用いられる．特に競技はリビングルームで行われる．アリーナ内は事前にマッピングすることが可能とする（既知環境）．
- **スタートロケーション**：ロボットは，アリーナの外から`ドアオープン`（扉を開くこと）よりスタートする．
- **ゲスト**：2人のゲストは椅子に座っており，そのうち手を挙げている1人がロボットから物体を受け取る．

## シナリオ

### スタートフェーズ

1. **配置**：`TC`は，チームにロボットをスタート位置へ移動させるよう指示する．また，チームメンバーは`TC`からの指示通りに，使用する物体を配置する．配置する物体数は最大で10個である．
1. **スタート**：`TC`はスタートの合図を出し，タイマーをスタートさせる．同時にチームは最後の簡単なセットアップ（スタートボタンを押す等）を完了し，エリアを離れる．このとき，ボタンを2つ以上押すなど複雑なセットアップ手順の実施は認められない．
1. **ドアオープン**：チームの1人はスタートの合図と同時にドアを開ける．このとき，ロボットはドアが開いたことを認識し，自律的にアリーナへ入場する．

### タスク１：片付けフェーズ

1. **競技時間**：`片付けフェーズ`（タスク１）の競技時間は**15分間**である．
2. **片付け**：ドアオープン後，ロボットはテーブル（`Long Table B`）の上に並べられた物体を全て片付ける．家庭環境には，既知と未知の物体が混同して設置されている．それぞれの物体にはカテゴリがあり，それぞれで片付ける場所（`Long Table A`, `Trash Bin A`, `Storage Box A`）が決まっている．これらは事前に指定されているので，ロボットはそれをもとに物体を片付ける．
<!-- 家具名を要検討 -->

### タスク２：デリバリーフェーズ

1. **競技時間**：`デリバリーフェーズ`（タスク２）の競技時間は**5分間**である．
1. **ナビゲーション**：ロボットは一方の部屋（`Room 1: Living Room`）からもう一方の部屋（`Room 2: Dining Room`）へ移動する．このとき，ロボットの移動を妨げるようなダミ物体を**3個**設置するので，ロボットはこれらと接触しないように移動を行っていく．
1. **デリバリー**：ロボットは，棚に並ぶ物体から事前に指示された物体を見つけて把持する．把持した物体は，イスに座っている人のうち，手を振っている（もしくは手を上げている）人に渡する．
1. **ゴール**：ロボットが人に物体を渡した時点で，タスク終了になる．

> [!NOTE]  
> デリバリー物体は既知物体（事前公開）とする．また，事前に指定された物体の隣に，未知物体や対象でない物体を配置する可能性がある．

## 使用物体

`Tidy Up for OPL`のタスクで使用される物体については，一般規定（General Rules & Regulations）の[物体（Objects）](gr_ja.md#物体objects)を確認すること．

### 物体種類の割合

- `標準オブジェクト` ｜　公開：9個　→　競技：6個
- `事前公開オブジェクト` ｜　公開：3個　→　競技：3個
- `未知オブジェクト` ｜　公開：0個　→　競技：1個
- `ダミーオブジェクト` ｜　公開：1個　→　競技：3個（1種類のみ）

> [!WARNING]
> 使用される未知オブジェクトは同一トライアルないにおいては全チーム共通である．トライアルごとに異なる未知オブジェクトが使用される．

## 物体カテゴリーごと配置場所

物体カテゴリーごとの配置場所については以下の通りである．

| ID | Placement Goal (Furniture) | Object Category |
| --- | --- | --- |
| 5a | Tray A        | Food Item |
| 5b | Tray B        | Food Item |
| 6  | Container​     | Kitchen Item​ |
| 8a | Trash Bin A   | Unknown Item​ |
| 9a | Storage Box A | Task Item​ |
​

## リスタート

リスタート時に以下の行為が認められる．

- チームメンバーがリスタートを宣言した時点で，ロボットが把持しているオブジェクトを取り除くこと（アリーナ外へ出す）．
- ロボットがスタート地点で待機している間に物体の配置を元に戻すこと（倒れたオブジェクトや落ちているオブジェクトを初期位置へ配置し直す）．

## デウス・エクス・マキナ

本タスクでは，次のデウス・エクス・マキナが採用される．デウス・エクス・マキナでは該当アクションの点数は入らないが，より簡単な手法で部分的なタスクをスキップし，全体的なタスクを継続することができる．

|Action|Bypassing|
|------|---------|
| 物体の把持 | ロボットが指示した物体を，`TC`がロボットに持たせる（あるいは特定の場所に置く．このとき，ロボットは物体の位置と名前，指示などを正確に伝える必要がある |
| 物体の設置 | `TC`がロボットの持っている（あるいは特定の場所にある）物体を，ロボットの指示した場所に設置する．このとき，ロボットは物体の配置位置と名前，指示などを正確に伝える必要がある |
| 物体の受け渡し | ゲストがロボットの持っている（あるいは特定の場所にある）物体を，ロボットから渡されることなく受け取る．このとき，ロボットは対象ゲストの位置と物体の名前，指示などを正確に伝える必要がある |

## スコアシート

| Action                                              | Score |
| --------------------------------------------------- | ----- |
| **1. 物体を片付ける**                                      |       |
| &nbsp;&nbsp;物体を把持する                          | 10x10 |
| &nbsp;&nbsp;物体を運搬し，設置・収納する            | 10x10 |
| &nbsp;&nbsp;物体を正しい場所に設置・収納する        | 15x10 |
| **2a. 障害物に衝突することなく`Room 2: Dining Room`に入る** | 30    |
| **2b. 物体を提供する**                                      |    |
| &nbsp;&nbsp;棚からフードアイテムを把持する                      | 30    |
| &nbsp;&nbsp;棚から指示されたフードアイテムを把持する            | 30    |
| &nbsp;&nbsp;人に物体を渡す                                      | 30    |
| &nbsp;&nbsp;手を挙げている人を検出し，物体を渡す                | 30    |
| ペナルティ                                          |       |
| 不参加（無断）                                      | -500  |
|                                                     |       |
| 合計（ボーナスタスクを含む）                        | 500   |

**得点係用のスコアシート**: [TU-score_sheet](./doc/RCJ2024_OPL_TU-score_sheet.pdf)


## 指示 (Instructions)

### ボランティアへ (To Volunteer)

ボランティアは競技チームによって自由に選ばれ，以下のタスクを行う． 

- ボランティアを2名選ぶ．
- 競技が始まる**30分前**に集まる．
- ボランティアはTCの指示に従い，手を振る．
- ボランティアはロボットからの指示に従い，自分自身で行動しないでください．

> [!WARNING]
> ゲストに関する情報は競技チームと共有してはいけない．
そのような行為はペナルティの付加や競技の失格につながる可能性がある．

> [!NOTE]
> ボランティアできる人数が足りない場合，
他チームからの支援をお願いする場合がある．

### 得点係へ (To Scorer)

得点係は*General Rules*の[採点方法](./gr_ja.md#採点方法scoring-system)に定義されているように選ばれ，以下のタスクを行う．

- 競技が始まる**30分**前に集まる．
- スコアシートの情報についての指示を受ける．
- 競技チームの競技をスコアリングする．
- 他の得点係とTCとスコアを確認し合う．
- スコアシートをTCに提出する．

### TCへ (To TC)

- *Setup Days*中: 
  - `事前公開オブジェクト`のリストを発表する．
  - `未知物体`を準備する．
- 競技前: 
  - 2名のボランティアの存在を確認する．
  - 未知物体を指定し，アナウンスする．
  - 物体の初期設置場所を選択し，アナウンスする．
- 競技中: 
   - 手を振るように1人のボランティアに指示する．
