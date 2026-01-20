# wm-itemstructure-effect-3

視覚的ワーキングメモリと物体配置構造が視覚探索に与える影響を検証する心理学実験

## 概要

本プロジェクトは、制限された視野を移動して行う視覚探索場面において、視覚的ワーキングメモリおよび物体の配置構造が探索効率に与える影響を解明することを目的とした実験プログラムです。jsPsych v7を使用してブラウザ上で実行される心理学実験として実装されています。本プログラムはPavloviaにホスティングされることを想定して作成されています。

## 主な機能

### 実験条件

本実験では以下の3つの独立変数を操作しています：

1. **表示条件（被験者間要因）**
   - 全画面条件：画面全体に図形が表示される
   - ウィンドウ条件：小さな窓をドラッグして移動させながら探索
   - スクロール条件：背景をドラッグしてスクロールしながら探索

2. **配置構造（被験者内要因）**
   - 構造化条件：図形が規則的なグリッドに配置される
   - 非構造化条件：図形がランダムに配置される

3. **記憶負荷（被験者内要因）**
   - 記憶負荷あり：視覚探索前に4×4グリッドの位置記憶課題を実施
   - 記憶負荷なし：記憶課題なしで視覚探索のみ実施

### 実験の流れ

1. インフォームドコンセント
2. 基本情報（年齢・性別）の入力
3. 実験説明（割り当てられた条件に応じた説明）
4. 練習試行（3回、繰り返し可能）
5. 本番試行（第1ブロック：30試行）
6. 中間説明
7. 本番試行（第2ブロック：30試行）
8. 結果表示と確認ID発行

## 必要要件

- モダンブラウザ（Chrome、Firefox、Safari、Edge等）
- JavaScript有効化
- フルスクリーンモード対応
- インターネット接続（jsPsychライブラリの読み込みに必要）

## 使用方法

### データの収集

実験終了時に、jspsychおよびPavloviaの機能によってデータが出力されます。このデータには主に以下の情報が含まれます：

- 参加者情報（年齢、性別）
- 各試行の反応時間
- 正誤データ
- 実験条件（表示条件、配置構造、記憶負荷）
- マウス移動経路と総移動距離
- 記憶課題の成績
- 確認ID

## プロジェクト構造

```
wm-itemstructure-effect-2/
├── index.html              # メインの実験ファイル
├── styles.css              # スタイルシート
├── screen_shots/           # 説明画面で使用するスクリーンショット
│   ├── 1_target_presentation.png
│   ├── 2_fullscreen.png
│   ├── 3_window_initial.png
│   ├── 4_window_after_move.png
│   ├── 5_scroll_initial.png
│   ├── 6_scroll_after_move.png
│   ├── 7_memory_task_presentation.png
│   └── 8_memory_task_response.png
├── preview_pages/          # プレビュー用のHTMLファイル
├── tests/                  # テスト関連ファイル
├── LICENSE                 # MITライセンス
└── README.md              # 本ファイル
```

## 実験パラメータ

以下のパラメータは `index.html` 内で調整可能：

- `numObjects`: 1試行あたりの図形数（デフォルト: 25）
- `objectSize`: 図形のサイズ（デフォルト: 40px）
- `windowWidth/Height`: ウィンドウ・スクロール条件の表示窓サイズ
- `trialsPerCondition`: 各条件あたりの試行数（デフォルト: 15）
- `memoryGridSize`: 記憶課題のグリッドサイズ（デフォルト: 4×4）
- `memoryPositions`: 記憶する位置の数（デフォルト: 4）

## 技術仕様

- **フレームワーク**: jsPsych v7
- **プラグイン**:
  - `@jspsych/plugin-html-keyboard-response`
  - `@jspsych/plugin-survey-text`
  - `@jspsych/plugin-preload`
  - `@jspsych/plugin-instructions`
  - `@jspsych/plugin-canvas-keyboard-response`
  - `@jspsych/plugin-survey-multi-choice`
- **描画**: HTML5 Canvas API
- **スタイリング**: カスタムCSS

## ライセンス

このプロジェクトはMITライセンスの下で公開されています。詳細は [LICENSE](LICENSE) ファイルをご覧ください。

## 著者・連絡先

- **研究実施者**: 野﨑 優晴（東京学芸大学大学院 連合学校教育学研究科 博士課程）
- **研究に関するお問い合わせ先**: r241004y@st.u-gakugei.ac.jp

## 謝辞

本実験プログラムは認知心理学研究のために開発されました。jsPsychコミュニティおよびPavloviaコミュニティに感謝いたします。
