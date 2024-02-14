<sub>[READMEへ](../../README.md)</sub>

[日本語](./gpsr_ja.md) | [English](./gpsr_en.md)

# General Purpose Service Robot - GPSR

参考動画：https://youtu.be/p9ki89buY68

> [!WARNING]
> この動画は参考動画であり，RoboCup@Home JapanOpenのルールと異なる可能性がある．


## タスク説明 (Description)

Similar to a smart speaker, the robot is asked to execute arbitrary commands requested by an
operator.
These commands are classified into four (4) categories according to their complexity.
The score also changes based on the difficulty of the category.


## フォーカス (Focus)

*Task planning*, *object/people detection and recognition*, *object feature recognition*, *object manipulation*


## セットアップ(Setup)

-**Locations**:
  - **Task location**: The task takes place inside the *Arena*, but some commands may require the robot to go out.
  The *Arena* is in its nominal state for this task.
  - **Start Location**: The robot starts from a *predefined location* announced in the *Setup Days*.
  When the Referee gives the *start signal*, the robot moves towards the *Instruction Point*.
  - **Instruction point**: At the beginning of the test, as well as after finishing the first and second command, the robot moves to the *Instruction Point*.
  This *Instruction point* is a *predefined location* and is announced in the *Setup Days*.
- **People**:
  - **Operator**: The operator instructs the robot commands given by the Referee.
  The operator is selected from the competing team.
  - **Guests**: Guests interact with the robot through gestures and other means depending on the selected task.
  Up to three (3) guests will be inside the *Arena*.


## 手順 (Procedure)

1. Start Phase

    1. **Task Time**: The time limit is ten (10) minutes.

    1. **Setup**: The TC instructs the team to move the robot to the *Starting Location*.

    1. **Category Selection**: The team tells the referee the selected category.
    Depending on the category, the referee choose an arbitrary command and gives it to the operator.
        - Category 0: Predefined instructions.
        - Category 1: Low-difficulty instructions.
        - Category 2: Medium-difficulty instructions.
        - Category 3: High-difficulty instructions or instructions containing insufficient/mistaken information.

    1. **Start**: The TC gives the start signal and starts the timer.
    The team completes the setup (pressing the start button, etc.) and leaves the area.
    No complex setup procedures are allowed, such as pressing two or more buttons.

    1. **Goal**: The robot performs the command phase and service phase for three (3) times.

1. Command Phase

    1. **Navigation to Operator**: The robot navigates from the *Start Location* to the *Instruction point*.

    1. **Instruct the Robot**: The operator commands the given task to the robot.
    If the robot cannot understand the name or favorite drink, the robot can request the guest to repeat the command and no penalty is given.

1. Service Phase

    1. **Command Confirmation**: After receiving the command, the robot confirms it before starting to execute the task.

    1. **Command Execution**: The robot performs the task given in the instructions.


## その他のルールと注意事項 (Additional Rules and Remarks)

### コマンドのスキップ (Skipping Commands)

The robot performs the command phase and service phase for three (3) times.
However, the competing team cannot skip to the next command if no points where obtained during each task.

### コマンドジェネレータ (Command Generator)

Commands from categories 0-3 are generated using the [CommandGenerator](https://github.com/johaq/CommandGenerator/tree/master).
The TC generates arbitrarily the commands in advance to confirm the commands are correct according to the environment.

## デウス・エクス・マキナ (Deus Ex Machina)

If the *Deus Ex Machina* listed in the *General Rules* is used during the execution of a task, points are deducted, up to ten (10) times.

For example:
- bypassing speech recognition by using an alternative HRI
- receiving human assistance to accomplish a task

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

### 一例 (Examples)

| カテゴリ | 命令文例 |
| --- | --- |
| **Manipulation** <br>grasp, give\|place | &bullet; Go to the `$ROOM`, grasp the `$OBJECT` on the `$PLACE` and place it on the `$PLACE`. <br>&bullet; Go to the `$ROOM`, grasp the `$OBJECT` on the `$PLACE` and give it to `$PERSON`. |
| **Vision** <br>find (obj \| people)     | &bullet; Tell me how many `$CATEGORY_OBJ` there are on the `$PLACE`. <br>&bullet; Tell me how many people in the `$ROOM` are `$POSTURE`. |
| **Navigation** <br>follow, guide        | &bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and follow (him \| her). <br>&bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and guide `(him\|her)` to the `$ROOM`. |
| **Speech** <br>ask, answer              | &bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and answer (his \| her) question. <br>&bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and ask (him \| her) `$QUESTION`. |

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
