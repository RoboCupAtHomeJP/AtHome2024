<sub>[READMEへ](../../README.md)</sub>

[日本語](./tu_ja.md) | [English](./tu_en.md)

# TidyUp for OPL

参考動画：https://youtu.be/sVmFMCnJf8s

> [!NOTE]  
> 参考動画は完璧ではありません．RoboCupのルールによってタスク内容が異なる可能性があるので，あくまで参考程度にしてください．
> 気になる点や議論したい点などがありましたら，GitHubの[Issues](https://github.com/RoboCupAtHomeJP/Rule2023/issues)にてご記入ください．


## メインゴール（Main Goal）

このタスクでは，ロボットが散らかった部屋のお片付けをすることを想定している．事前に物体をどこに片付けるかが指定されているため，ロボットはその情報をもとに所定の場所に片付けていく．その後，別の部屋へ移動し，手を振っている（もしくは，手を上げている）人に，棚から事前に指定された物を提供していく．[WRS（World Robot Summit）2020](https://wrs.nedo.go.jp/wrs2020/challenge/download/Rules/DetailedRules_Partner_EN.pdf)で行われた競技をRoboCup Japan Open @Home OPL用にアレンジした競技になっている．

**制限時間**：20分（タスク１：15分，タスク２：5分）

## テクニカルフォーカス（Technical Focus）

このタスクは，既知環境での自律移動，物体認識，物体把持，タスクプランニングなどに焦点を当てている．


## セットアップ（Settings）

- **ロケーション**：家庭環境を模したアリーナ環境が用いられる．特に競技はリビングルームで行われる．アリーナ内は事前にマッピングすることが可能とする（既知環境）．
- **スタートロケーション**：ロボットは，アリーナの外から`ドアオープン`（扉を開くこと）よりスタートする．
- **ゲスト**：2人のゲストは椅子に座っており，そのうち手を挙げている1人がロボットから物体を受け取る．2人のゲストは各チームから選出してください．


## シナリオ（Scenario）

### スタートフェーズ（Starting Phase）

1. **競技時間**：競技時間は`片付けフェーズ`（タスク１）が15分，`デリバリーフェーズ`（タスク２）が5分の**計20分間**になる．
1. **配置**：レフェリーは，チームにロボットをスタート位置へ移動させるよう指示する．また，このときレフェリーの指示通りに，使用する物体を配置していく．配置する物体数は最大で10個です．
1. **スタート**：レフェリーはスタートの合図を出し，タイマーをスタートさせる．同時にチームは最後の簡単なセットアップ（スタートボタンを押す等）を完了し，エリアを離れる．このとき，ボタンを2つ以上押すなど複雑なセットアップ手順の実施は認められません．
1. **ドアオープン**：チームの1人はスタートの合図と同時にドアを開ける．このとき，ロボットはドアが開いたことを認識し，自律的にアリーナへ入場する．

### タスク１：片付けフェーズ（Task 1: Tidy Up Phase）

1. **競技時間**：`片付けフェーズ`（タスク１）の競技時間は**15分間**です．
1. **片付け**：ドアオープン後，ロボットはテーブル（`Long Table B`）の上に並べられた物体を全て片付けていく．家庭環境には，既知と未知の物体が混同して設置されている．それぞれの物体にはカテゴリがあり，それぞれで片付ける場所（`Long Table A`, `Bin A`, `Bin B`）が決まっている．これらは事前に指定されているので，ロボットはそれをもとに物体を片付けていく．

### タスク２：デリバリーフェーズ（Task 2: Delivery Phase）

1. **競技時間**：`デリバリーフェーズ`（タスク２）の競技時間は**5分間**です．
1. **ナビゲーション**：ロボットは一方の部屋（`Room 1: Living Room`）からもう一方の部屋（`Room 2: Dining Room`）へ移動する．このとき，ロボットの移動を妨げるようなダミ物体を**3個**設置するので，ロボットはこれらと接触しないように移動を行っていく．
1. **デリバリー**：ロボットは，棚に並ぶ物体から事前に指示された物体を見つけて把持する．把持した物体は，イスに座っている人のうち，手を振っている（もしくは手を上げている）人に渡する．
1. **ゴール**：ロボットが人に物体を渡した時点で，タスク終了になる．

> [!NOTE]  
> デリバリー物体は既知物体（事前公開）とする．また，事前に指定された物体の隣に，未知物体や対象でない物体を配置する可能性があるので，ご注意ください．


## 使用物体（Objects to manipulate）


`Tidy Up for OPL`のタスクで使用される物体については，一般規定（General Rules & Regulations）の[物体（Objects）](gr_ja.md#物体objects)という項目をご確認ください．

<!-- RCAP2021に使用された9個の物体リストを用いる．物体リストは下記のリンクから確認できる．リストには，各物体の写真，正式名称，物体カテゴリ（例えば，`Noodle`は`Food`のカテゴリに属す）が記載される．ほとんどのオブジェクトは軽量で，ロボットが簡単に掴める物になっている．各物体のカテゴリーごとに，設置されている場所や，片づけるべき場所が決まっている．このカテゴリを参照することで，競技中にそのカテゴリの物体を見つけたり，片づけたりしていく．物体を加工することは禁止とするので，ご注意ください． -->

<!-- また，競技タスクでは，物体を「`既知物体`（事前公開＋直前公開）」と「`未知物体`」として分けて使用していく．このとき，`既知物体`とは，競技のルールの公開とともに事前公開している物体と，競技の`Setup Day`に公開する直前公開の物体という2つの種類に分ける．競技本番は，各チームが持ち寄せた物体を使用する．また，`未知物体`とは，物体リストにない物体で，把持・操作可能なものを指している．競技タスクによっては，この未知物体を使用することがある． -->

<!-- 最後に，障害物として使用される物体は`ダミ物体`と呼ばれ，`Setup Day`の日に公開する． -->

<!-- > [!NOTE]  
# > `既知物体`（事前公開）：https://github.com/RoboCupAtHomeJP/AtHome2021/blob/master/Data/opl_known_object_list.pdf -->

### 物体種類の割合（Proportion of the objects）

- `既知物体` （事前公開）｜　公開：9個　→　競技：6個
- `既知物体` （直前公開）｜　公開：3個　→　競技：3個
- `未知物体` （当日公開）｜　公開：0個　→　競技：1個
- `ダミ物体` （直前公開）｜　公開：1個　→　競技：3個（1種類のみ）

> [!NOTE]  
> `既知物体` （事前公開）と未知物体以外の物体は，運営側が用意し，それぞれのチームに`Setup Day`のときに配布する．

> **Warning**
> 全チームの初トライアルを終えた後，元の`未知物体`を別の未知物体に変える．

## 物体カテゴリーごと配置場所（Object Category and placement goal）

物体カテゴリーごとの配置場所については以下の通りです．
<div align="center"><img src="./tu_layout.jpg" width="70%"></div>
<br>

## デウス・エクス・マキナ（Deus ex Machina）

本タスクでは，次のデウス・エクス・マキナが採用される．デウス・エクス・マキナでは該当アクションの点数は入らないが，より簡単な手法で部分的なタスクをスキップし，全体的なタスクを継続することができる．

<table>
  <tr>
    <th> <b>Action<b> </th>
    <th> <b>Bypassing<b> </th>
  </tr>
  <tr>
    <td> 物体数の調整 </td>
    <td>
      <ul>
        <li> 配置する物体の数を任意の数に減らす </li>
        <li> 既知物体の中でどの物体を減らすかはチームで選択することを可能とする </li>
      </ul> 
    </td>
  </tr>
  <tr>
    <td> 物体の把持 </td>
    <td>
      <ul>
        <li> ロボットが指示した物体を，レフェリーがロボットに持たせる（あるいは特定の場所に置く </li>
        <li> このとき，ロボットは物体の位置と名前，指示などを正確に伝える必要がある </li>
      </ul> 
    </td>
  </tr>
   <tr>
    <td> 物体の設置 </td>
    <td>
      <ul>
        <li> レフェリーがロボットの持っている（あるいは特定の場所にある）物体を，ロボットの指示した場所に設置する </li>
        <li> このとき，ロボットは物体の配置位置と名前，指示などを正確に伝える必要がある </li>
      </ul> 
    </td>
  </tr>
  <tr>
    <td> 物体の受け渡し </td>
    <td>
      <ul>
        <li> ゲストがロボットの持っている（あるいは特定の場所にある）物体を，ロボットから渡されることなく受け取る </li>
        <li> このとき，ロボットは対象ゲストの位置と物体の名前，指示などを正確に伝える必要がある </li>
      </ul> 
    </td>
  </tr>
</table>


## スコアシート（Score Sheet）

<table>
  <tr>
    <th> <b>Action</b> </th>
    <th> <b>Score</b> </th>
  </tr>
  <tr>
    <td colspan="2" align="center"> <b>タスク１：片付けフェーズ</b> </td>
  </tr>
  <tr>
    <td> 物体を片付ける <br> 
      <ul>
        <li> 物体を把持する（10点／1個） </li>
        <li> 物体を運搬し，設置・収納する（10点／1個） </li>
        <li> 物体を正しい場所に設置・収納する（15点／1個） </li>
      </ul> 
    </td>
    <td align="center"> <!-- 200 <br> --> 10 × 10 <br> 10 × 10 <br> 10 × 15 </td>
  </tr>
  <tr>
    <td colspan="2" align="center"> <b>タスク２：デリバリーフェーズ</b> </td>
  </tr>
  <tr>
    <td> 障害物に衝突することなく`Room 2: Dining Room`に入る </td>
    <td align="center"> 30 </td>
  </tr>
  <tr>
    <td> 物体を提供する <br> 
      <ul>
        <li> 棚からフードアイテムを把持する </li>
        <li> 棚から指示されたフードアイテムを把持する </li>
        <li> 人に物体を渡す </li>
        <li> 手を挙げている人を検出し，物体を渡す </li>
      </ul> 
    </td>
    <td align="center"> <!-- 200 <br> --> 30 <br> 30 <br> 30 <br> 30 </td>
  </tr>
  <tr>
    <td colspan="2" align="center"> <b>ペナルティ</b> </td>
  </tr>
  <tr>
    <td> 不参加（無断） </td>
    <td align="center"> -500 </td>
  </tr>
  <tr>
    <td> <b>合計（ボーナスタスクを含む）</b> </td>
    <td align="center"> <b>500</b> </td>
  </tr>
</table>

**スコアシート**：[RCJ2023 OPL Tidy Up Score Sheet v1](https://docs.google.com/spreadsheets/d/1Dn0LTINAVYMcSL2Yoqi4iicPZOmU6h8e/edit?usp=sharing&ouid=115914283332872721627&rtpof=true&sd=true)


## 運営(EC)による指示（Instructions from the Executive Committee(EC)）

- 準備（競技の数日～数週間前）
  - 既知（直前公開）と未知物体を選択し，購入する．
- アナウンス（競技の30分前から）
  - 物体の初期設置場所を選択し，アナウンスする．
  - 未知物体を指定し，アナウンスする．


## レフェリー(TC)の動き（Role of the Referee(TC)）

- 競技開始30分前に集まり，説明を受け，スコアシートを受け取る．
- シナリオに記載のレフェリーとして行動する．
- 競技を採点する．
- 他のTCと採点内容を確認し合う．
- スコアシートを提出する．

> [!NOTE]  
> TCは各チームから数名選出され，他チームの競技において以下を行ってもらう．詳細については，一般規定の[採点方法](./gr_ja.md#採点方法scoring-system)をご確認ください．