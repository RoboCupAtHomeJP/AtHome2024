

[日本語](./tc_ja.md) | [English](./tc_en.md)

# 競技課題作成手順

公平性の観点から，競技で使用する問題の一部を各チームで作成していただきます．
問題作成手順は以下の各競技の問題作成手順からご確認ください。


# Handymanの競技問題作成

基本的な課題作成の流れについては、GitHub の [Readme](https://github.com/RoboCupatHomeSim/handyman-unity) と [Wiki](https://github.com/RoboCupatHomeSim/handyman-unity/wiki/AdvancedExecutionProcedures#how-to-create-the-environmentinfoxxjson) を参考にしてください。
作成したレイアウトが適切であるか以下の手順で確認してください。

## 難易度調整について
- 課題の難易度は、原則として易しいものを意識します。
- 試行間の難易度差を十分に設けてください。現状、易しいものが多いため、特に問題はありません。
- 難易度に影響する要素:
  - 部屋の広さ
  - 通路の狭さ
  - 動的障害物アバター(EthanWoman)の存在
  - 移動距離の長さ
  - 物体が多い間取り
  - 把持対象がa-likeオブジェクトである場合
  - 指示者(Ethan)の移動
  - 把持対象の移動先が移動可能家具(ゴミ箱など)の場合
  - タスクメッセージに位置関係を表現する単語が含まれる場合
  - タスクメッセージに矛盾が含まれている場合
  - 把持対象が倒れている場合
- 現状、未知環境は設けず、全て事前に公開します。

## 課題の作成手順

1. **Googleスプレッドシート準備**:
   - 「Handyman課題メモ」というGoogleスプレッドシートに課題内容シートを追加しながら進めます。

   [テンプレートはこちら](https://docs.google.com/spreadsheets/d/1bPj9ja2-1zixFmQ5BribwEPBQejnv7Dh/edit#gid=2127521637)

2. **テンプレシートをコピー**:
   - テンプレシートをコピーして課題シートを作成します。テンプレシートはレイアウト毎に異なります。

3. **課題の考案**:
   - 把持対象や届け先が一意に定まるようなタスク文章を考え、修正します。タスク文章は150文字程度に収めてください。

4. **Unityでの課題作成**:
   - Unityで競技シーン(Handyman.unity)をコピーし、課題作成用シーンを作成します。課題作成用シーンは `Assets/AssetStoreTools` フォルダに入れ、gitignore設定を利用して誤ってGitHubにPushされることを防ぎます。

5. **課題の詳細調整**:
   - Wiki手順を参考にしつつ、必要に応じてゴミ箱を移動させたり、GraspingCandidatesPositionXXを調整します。

6. **ファイルの保存**:
   - AvatarMotions01.dat と EnvironmentInfo01.json に課題が出力されるため、これらをコピーして保存します。

7. **課題の確認**:
   - isGraspableObjectsPositionRandomをfalseに戻し、競技シーンを使用して作成したタスクを実行し、課題が想定通りであることを確認します。

## 課題の動作確認

1. **本番用Unityシーンの準備**:
   - Handyman.unityをコピーして本番用UnityシーンをHiddenフォルダ配下に作成します。

2. **a-likeオブジェクトの追加**:
   - 本番用UnityシーンのGraspingCandidatesの下にa-likeオブジェクトを追加します。

3. **全課題の動作確認**:
   - 本番用Unityシーンを使用して、作成した全課題の動作確認を行います。

## 3Dモデル一覧(Object Labelリスト)の更新

- 各競技で使用する3Dモデル一覧は、Object LabelというGoogleスプレッドシートで事前に参加者に共有されます。
- 更新点には、新規の3Dモデルの追加や既存の3Dモデルの扱い変更などが含まれます。


# Interactive Cleanupの課題作成手順
