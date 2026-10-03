# 概要
- このプロジェクトでは、OpenAI o1 proが出力したキャラクタータイプの分類データからデータベースを作り、ランダムに取り出したキャラクタタイプからキャラクターのアイデアを生成します。
- このプロジェクトは、ChatGPT Proで使用できる、OpenAIのo1 pro modeの検証を兼ねています

# 手順
- ChatGPT Proのo1 pro modeに、物語のキャラクタータイプを生成させます
  - [character-type-protagonist-1.md](https://github.com/masa-jp-art/character-type-db/blob/main/character-type-protagonist-1.md)
  - [character-type-protagonist-2.md](https://github.com/masa-jp-art/character-type-db/blob/main/character-type-protagonist-2.md)
  - [Character-type-SubCharacter.md](https://github.com/masa-jp-art/character-type-db/blob/main/Character-type-SubCharacter.md)
  - [Character-type-antagonist.md](https://github.com/masa-jp-art/character-type-db/blob/main/Character-type-antagonist.md)
- 各キャラクターをスプレッドシートに転記してデータベースを作ります
  - [20250101-Character-type-snapshot](https://docs.google.com/spreadsheets/d/19C8QyBmT4gazWGgDIjvax4VwzGr_POiDX0nXsoZP9QQ/edit?usp=sharing)
- Google colabでプログラムを動かし、キャラクターとあらすじを生成します
  - [code-for-google-colab.py](https://github.com/masa-jp-art/character-type-db/blob/main/code-for-google-colab.py)
 
# 関連
- [OpenAI o1 pro mode検証:物語のキャラクタータイプデータベースが作れるか](https://note.com/msfmnkns/n/nfe0e4f07d4b5)

# 用語と使い方の例

ここでの「キャラクタータイプ」は、人物を発想するための物語上の類型です。例えば収録資料の「古典的ヒーロー」は使命や正義感を軸にした主人公像です。架空の舞台を与え、主人公・サブキャラクター・対立者の候補を各シートから一つずつ選び、その組合せから人物像とあらすじを生成します。心理診断や実在人物の分類のためのデータではありません。

[Colab用コード](code-for-google-colab.py)は各シートの2列目から見出しを除いてランダム抽出し、主人公の生成結果を他の人物の生成にも渡します。分類資料を作るo1 pro modeの検証と、コード内で人物・あらすじを作る `gpt-4o` のAPI呼び出しは別の工程です。分類を固定の答えではなく、組合せから発想を広げる材料として使う構成です。

# 成立と展開

[2025年1月1日のコード追加](https://github.com/masa-san-jp/character-type-db/commit/9c0f0c06f314bbd189ac7a16dc6b017ed51da31d)と同日の分類資料・READMEの履歴に、o1 proの出力をスプレッドシートとColabへつなぐ実験が記録されています。上記の関連記事は当時の検証の入口です。

既存の流れは、舞台を変えた人物案の比較や創作のたたき台作りに利用できます。分類の学術的網羅性や生成物の品質を保証するものではありません。コードは当時の `openai==0.28` とColab認証を前提とするため、利用時には依存関係とAPIの対応を確認してください。シートURL・鍵の例示欄へ実値を入れたコードは公開せず、送信する創作資料の権利・取扱いも確認します。更新や新しい評価機能は別途実装・検証が必要です。
