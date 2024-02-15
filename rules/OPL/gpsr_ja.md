<sub>[READMEへ](../../README.md)</sub>

[日本語](./gpsr_ja.md) | [English](./gpsr_en.md)

# General Purpose Service Robot - GPSR

参考動画: https://youtu.be/p9ki89buY68

> [!WARNING]
> この動画は参考動画であり，RoboCup@Home JapanOpenのルールと異なる可能性がある．


## タスク説明 (Description)

スマートスピーカーのように，オペレーターが要求する任意のコマンドを実行するようにロボットに依頼される．
これらのコマンドは，難易度に応じて4つのカテゴリに分類される．
カテゴリの難易度に基づいてスコアも変動する．


## フォーカス (Focus)

*タスクプラニング*，*物体・人検出と認識*，*物体の特徴認識*，*物体のマニピュレーション*


## セットアップ(Setup)

- **場所 (Locations)**:
  - **競技場所 (Task location)**: タスクは*Arena*内で行われるが，一部のコマンドではロボットが外に出ることがある．
  このタスクでは，*Arena*は通常の状態となる．
  - **開始位置 (Start Location)**: ロボットは*Setup Days*で発表される*事前定義された場所 (predefined location)*からスタートする．
  審判から*スタートの合図 (start signal)*が出る際に，ロボットは*Instruction Point*に向かって移動する．
  - **指示位置 (Instruction Point)**: 競技の開始時，および1番目と2番目のコマンドの終了後，ロボットは*Instruction Point*に移動する．
  この*Instruction Point*は*Setup Days*で発表される．
- **人物 (People)**:
  - **オペレーター (Operator)**: オペレーターは審判から与えられたコマンドをロボットに指示する．
  オペレーターは競技チームから選ばれる．
  - **ゲスト (Guests)**: ゲストはジェスチャーや他の手段を通じてロボットとインタラクションする．
  最大で3人のゲストが*Arena*内にいる．


## 手順 (Procedure)

1. 開始フェーズ (Start Phase)

  1. **競技時間 (Task Time)**: 制限時間は**10分**までとする．

  1. **セットアップ (Setup)**: TCはチームにロボットを*Start Location*に移動するよう指示する．

  1. **カテゴリ選択 (Category Selection)**: チームは選択したカテゴリを審判に伝える．
  カテゴリによって，審判は任意のコマンドを選び，オペレーターに与える．
    - カテゴリ0: 事前定義された指示．
    - カテゴリ1: 低難度の指示．
    - カテゴリ2: 中難度の指示．
    - カテゴリ3: 高難度の指示または不十分な/誤った情報を含む指示．

  1. **開始 (Start)**: TCが開始合図(start signal)を出し，タイマーを開始する．
  チームはセットアップを完了させ（スタートボタンを押すなど），エリアを離れる．
  2つ以上のボタンを押すなどの複雑なセットアップ手順は許可されない．

  1. **目的 (Goal)**: ロボットはコマンドフェーズとサービスフェーズを3回行う．

1. コマンドフェーズ (Command Phase)

  1. **オペレーターへの移動 (Navigation to Operator)**: ロボットは*Start Location*から*Instruction point*まで移動する．

  1. **ロボットへの指示 (Instruct the Robot)**: オペレーターは与えられたタスクをロボットに指示する．
  ロボットが名前や好きな飲み物を理解できない場合，ロボットはゲストに指示を繰り返すように要求することができ，ペナルティはない．

1. サービスフェーズ (Service Phase)

  1. **コマンド確認 (Command Confirmation)**: コマンドを受け取った後，ロボットはタスクを実行する前にコマンドを確認する．

  1. **コマンド実行 (Command Execution)**: ロボットは指示に従ってタスクを実行する．


## その他のルールと注意事項 (Additional Rules and Remarks)

### コマンドのスキップ (Skipping Commands)

The robot performs the command phase and service phase for three (3) times.
However, the competing team cannot skip to the next command if no points where obtained during each task.

### コマンドジェネレータ (Command Generator)

カテゴリ0から3のコマンドは，[CommandGenerator](https://github.com/johaq/CommandGenerator/tree/master)から生成される．
TCは環境に応じて事前にコマンドを任意に生成し，コマンドの正確さを確認する．


## デウス・エクス・マキナ (Deus Ex Machina)

競技実行中に*デウス・エクス・マキナ*が*一般ルール*にリストされている項目から，ポイントが減点される．
その重複は最大で10倍までとする．

例えば: 
- 代替のHRIを使用して音声認識を飛ばす
- タスクを達成するために人間の支援を受ける


## リスタート (Restart)

リスタートは段階に応じて以下のように取り扱う．
なお，リスタートした場合，ロボットはスタート地点からタスクを再開する．
Step 1を完了している場合，リスタート後に直前のタスクを継続してもよい．
この場合，コマンドの理解やタスクの実行を繰り返してもよく，一度獲得した得点が減点されることはない
ただしペナルティとして，リスタート直後に獲得した点数は半減される．

先の条件に当てはまらない場合は，以下の手順が適応される．
- $n(\le 2)$回目のコマンドの理解の途中
  - 次のコマンドを$n$回目のコマンドとして再開する．
- $n$回目のStep 1の途中（目的地点への移動が完了していない場合，次のStepへ移る準備ができていない）
  - 次のコマンドを$n$回目のコマンドとして再開する．
- $n'(\le 3)$回目のStep 1完了後
  - $n'$回目のコマンドを$n'$回目のコマンドとして続きから再開して良い．

> [!NOTE]
> 物体を把持している場合，その取り扱いはチームに委ねる．


## コマンドカテゴリ (Command Category)

### タスクカテゴリの一例 (Task Category Examples)

| カテゴリ | コマンド文例 |
| --- | --- |
| **Manipulation** <br>grasp, give\|place | &bullet; Go to the `$ROOM`, grasp the `$OBJECT` on the `$PLACE` and place it on the `$PLACE`. <br>&bullet; Go to the `$ROOM`, grasp the `$OBJECT` on the `$PLACE` and give it to `$PERSON`. |
| **Vision** <br>find (obj \| people)     | &bullet; Tell me how many `$CATEGORY_OBJ` there are on the `$PLACE`. <br>&bullet; Tell me how many people in the `$ROOM` are `$POSTURE`. |
| **Navigation** <br>follow, guide        | &bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and follow (him \| her). <br>&bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and guide `(him\|her)` to the `$ROOM`. |
| **Speech** <br>ask, answer              | &bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and answer (his \| her) question. <br>&bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and ask (him \| her) `$QUESTION`. |

> [!IMPORTANT]
> これらの4つのタスクカテゴリカテゴリの中で，コマンド文例と異なる場合がある．
詳細な文構造については，[CommandGenerator](https://github.com/johaq/CommandGenerator/tree/master)を参照してください．

### タスクカテゴリごとのStep一覧 (Steps per Category)

| カテゴリ | Step 1 | Step 2 | Step 3 | Step 4 |
| --- | --- | --- | --- | --- |
| **Manipulation**    | 物体の前まで移動する      | 物体を把持する                | (配置場所 / 人の前)まで移動する | 物体を(配置 / 手渡し)する |
| **Vision**          | 観測する位置まで移動する  | 対象を観測する                | オペレーターの前まで移動する    | 観測結果を報告する |
| **Navigation**      | 人の前まで移動する        | 人を(追従 / 誘導)する         | (追従 / 誘導)先まで移動する     | (追従終了を認識 / 誘導終了を報告)する |
| **Speech (ask)**    | 人の前まで移動する        | 与えられた質問を人に質問する  | オペレーターの前まで移動する    | 質問の答えを報告する |
| **Speech (answer)** | 人の前まで移動する        | 人に質問を要求する            | 人にその質問を答える            | オペレーターの前まで移動する |

### カテゴリごとの加重 (Weights per Category)

| カテゴリ | $Weight$ |
| -------- | ------ |
| 0 | $0.7$ |
| 1 | $1$ |
| 2 | $2$ |
| 3 | $3$ |


## スコアシート (Score Sheet)

各動作を4つのStepsに分け，1 Stepごとに採点する．
カテゴリ難易度に応じて$Weight$の変数が変化する（以下表を参照）．

| アクション (Action) | スコア (Score) |
| --- | --- |
| **メインタスク (Main Task)**                            |  |
| &emsp; - 命令を理解する | $3 \times 20$                 |
| &emsp; - 1回目の命令タスクを実行する                    | $(5 \times 4) \times Weight$ |
| &emsp; - 2回目の命令タスクを実行する                    | $(10 \times 4) \times Weight$ |
| &emsp; - 3回目の命令タスクを実行する                    | $(20 \times 4) \times Weight$ |
| &emsp; - 全てのコマンドを実行した後*Arena*から退出する  | $20$ |
| ***デウス・エクス・マキナ (Deus Ex Machina)***                        |  |
| &emsp; - 代替手段を用いて命令を理解する                               | $3 \times -6$ |
| &emsp; - $h (\le 10)$ 回の人間の支援により1回目の命令タスクを実行する | $-2h \times Weight$ |
| &emsp; - $h$ 回の人間の支援により2回目の命令タスクを実行する          | $-4h \times Weight$ |
| &emsp; - $h$ 回の人間の支援により3回目の命令タスクを実行する          | $-8h \times Weight$ |
| **ペナルティ (Penalty)**                                |  |
| &emsp; - リスタート                                     | $直後に獲得した点数  \times 0.5$| 
| &emsp; - 不参加（無断）                                 | $-500$ |
| **合計**                                                | $500$ |


## 指示 (Instructions)

### ボランティアへ (To Volunteer)

ボランティアは競技チームによって自由に選ばれ，以下のタスクを行う． 

- 競技が始まる5分前に集まる．
- ゲストの情報についての指示を受ける．
- ゲストはロボットからの指示に従い，自分自身で行動しないでください．

> [!WARNING]
> ゲストに関する情報は競技チームと共有してはいけない．
そのような行為はペナルティの付加や競技の失格につながる可能性がある．

### 審判へ (To Referee)

審判は*General Rules*に定義されているように選ばれ，以下のタスクを行う．

- 競技が始まる30分前に集まる．
- スコアシートとゲストの情報とコマンドについての指示を受ける．
- 競技チームの競技をスコアリングする．
- 他の審判とTCとスコアを確認し合う．
- スコアシートをTCに提出する．

> [!WARNING]
> ゲストに関する情報は競技チームと共有してはいけない．
そのような行為はペナルティの付加や競技の失格につながる可能性がある．

### TCへ (To TC)

- *Setup Days*中:
   - *Start Point*を発表する．
   - *Instruction Location*を発表する．
   - 物体，カテゴリ，場所の位置を発表する．
   - 名前と飲み物のリストを発表する．
- 競技前:
   - 競技チームによって選ばれたゲスト役のボランティアを確認する．
   - ボランティアに名前を割り当てる．
   - 競技チームが使用する*Command Category*を確認する.
   - コマンドに応じて，*Arena*の工夫をする．
- 競技中:
   - オペレーターにコマンドを伝える．
