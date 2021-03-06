# 【第五人格】戦績管理ツール
第五人格の戦績を管理するツール

## できること
第五人格のゲームをすると、戦績画面が出てくる。
このスクショをとってツールに分析させると、  

* 勝率/使用ハンターの割合/当たるサバイバーの割合/当たるステージの割合を円グラフで表示可能
* ステージ/ハンター/勝率別、かつ、サバイバー別の、平均チェイス時間/平均解読進捗/治療回数/板攻撃回数を表で表せる
* 平均チェイス時間/平均解読進捗/平均余剰解読進捗/板破壊の枚数/板攻撃をもらった回数/恐怖入れた回数/攻撃回数/索敵時間を折れ線/棒グラフで表示可能

## 使い方 
### stage-0 pythonの確認
1. コマンドプロンプト(Windows)もしくはターミナル（Mac)を開く
![画像2](https://github.com/Kaede-Dewey/image_repo/blob/master/%E7%AC%AC%E4%BA%94%E4%BA%BA%E6%A0%BC%E6%88%A6%E7%B8%BE%E7%AE%A1%E7%90%86%E3%83%84%E3%83%BC%E3%83%AB/2.png)

2. pythonと打ってエンター（Macの場合はpython3でエンター）

3. 下の画像のようになったらstage-2へ
![画像1](https://github.com/Kaede-Dewey/image_repo/blob/master/%E7%AC%AC%E4%BA%94%E4%BA%BA%E6%A0%BC%E6%88%A6%E7%B8%BE%E7%AE%A1%E7%90%86%E3%83%84%E3%83%BC%E3%83%AB/1.png)

4. 下のように言われたらstage-1へ
```
'ｋｋ' は、内部コマンドまたは外部コマンド、
操作可能なプログラムまたはバッチ ファイルとして認識されていません。
```

### stage-1 pythonの導入
1. [python公式のダウンロードサイト](https://www.python.org/downloads/)にいって、ダウンロードする。バージョンは、3.~ならオッケー

2. ダウンロードしたものを実行して、インストールを進めていく。この時、一番最初の画面で、下の部分にチェックを入れておく

![画像3](https://github.com/Kaede-Dewey/image_repo/blob/master/%E7%AC%AC%E4%BA%94%E4%BA%BA%E6%A0%BC%E6%88%A6%E7%B8%BE%E7%AE%A1%E7%90%86%E3%83%84%E3%83%BC%E3%83%AB/3.png)

3. ターミナルを開いてみて、python(or python3)と打って、下のようになったらstage-2へ。
![画像1](https://github.com/Kaede-Dewey/image_repo/blob/master/%E7%AC%AC%E4%BA%94%E4%BA%BA%E6%A0%BC%E6%88%A6%E7%B8%BE%E7%AE%A1%E7%90%86%E3%83%84%E3%83%BC%E3%83%AB/1.png)

e. もし上のようにならなかった場合、修正をここに記すのはめんどくさいので、以下に二つの修正方法を記す
  * 環境変数PATHに、pythonをインストールしたディレクトリを追加
      →もしこっちをやってみたい場合は、「環境変数　追加」とかで調べればたぶんやり方が出てきます。
  * インストール時にチェックをつけ忘れていると思うので、アンインストールして、もう一度インストールする

### stage-2 必要なもののインストール
1. ターミナル（コマンドプロンプト）を起動

2. 戦績管理ツール.zipを展開したディレクトリに移動する
ex)もし
```
C\\:Users\\dewey\\documents\\戦績管理ツール
```
以下にダウンロードしたファイルを展開している場合、
```
cd C\\:Users\\dewey\\documents\\戦績管理ツール

```
と打つ。ただし、windowsの場合は\\(￥マーク×2）、Macの場合は/で区切る。
その状態で
```
dir
```
と打った時に、windowsでは
```
 ドライブ C のボリューム ラベルがありません。
 ボリューム シリアル番号は 82CC-317C です

 C/:Users/dewey/documents/戦績管理ツール のディレクトリ

2019/04/26  09:57    <DIR>          .
2019/04/26  09:57    <DIR>          ..
2019/04/26  00:15    <DIR>          conf
2019/03/29  21:20    <DIR>          data
2019/04/26  00:46    <DIR>          src
2019/04/25  16:20                39 【第五人格】戦績管理ツール.bat
2019/04/25  17:06                47 戦績追加.bat
               2 個のファイル                  86 バイト
               5 個のディレクトリ  866,714,079,232 バイトの空き領域

```
と、戦績管理ツールの名前があればおけ。Macは、たしかdirの部分はlsでよかった気がする。
こんな感じで【第五人格】戦績管理ツール.batというものがあることを確認！

3. 次のコードをコピペする
```
cd data/setup
pip install requirements.txt
```
すると、いろいろダウンロードが始まるので、終わるまで待つ。

4. tesseractを[こちら](https://github.com/UB-Mannheim/tesseract/wiki)のサイトから、自分のPCにあったものを選んでダウンロード。32bitか64bitかを確認してダウンロードすること

5. ダウンロードしたら、実行してインストールする。インストールできたら終わり
インストールする場所は自由にどぞ！　additional languageとか、そういったオプションは全部いらないです。


### stage-3 戦績画像の準備
1. 下のような戦績画像を準備する。スクショでおけ
![画像4](https://github.com/Kaede-Dewey/image_repo/blob/master/%E7%AC%AC%E4%BA%94%E4%BA%BA%E6%A0%BC%E6%88%A6%E7%B8%BE%E7%AE%A1%E7%90%86%E3%83%84%E3%83%BC%E3%83%AB/4.PNG)

これは、戦績→データから見ることができる。

2. その画像を、まとめておきたい人は./data/img/sensekiにおいておくといいかも。

3. 戦績管理ツールに追加する画像を選択して、戦績追加にD&Dする。

![画像5](https://github.com/Kaede-Dewey/image_repo/blob/master/%E7%AC%AC%E4%BA%94%E4%BA%BA%E6%A0%BC%E6%88%A6%E7%B8%BE%E7%AE%A1%E7%90%86%E3%83%84%E3%83%BC%E3%83%AB/5.png)
  
4. 追加した画像を解析して、保存してくれるので、あとはいろいろデータの推移などを見ていく感じ

### 戦績管理ツール
【第五人格】戦戦績管理ツール.batというファイルをダブルクリックで使える。
 * file => set_winsizeで、過去何試合分の試合結果を参考にして表示するかを決められる。デフォルトは10
 * file => set_gnumで、表にして出すときの、横軸に何人分入れるかというのを決められる。
 * plot => plotで、グラフの軸をいろいろいじれる。
 

### 戦績の追加
戦績追加.batというファイルに、追加する画像をまとめてドラッグ＆ドロップで追加

## もし需要がありそうなら...
* カスタムで特質や人格別に表示できるように変更しておきたい

## 現在の進捗
2019/3/25
* 戦績のスクショとスクショ内のデータのある位置を示したcsvファイルがあれば、各ハンター、サバイバー、各キャラの数値、勝ち負け、ステージ部分を切り抜ける
* 切り抜いた部分から各数値を認識できるようになった
* ハンター等のアイコンから、キャラクターを識別できるようになった

2019/4/26
* 完成
