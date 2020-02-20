
# Kinectv1 for mac :ofxOpenNI

こちらのブランチをoF10.1で動作するように改良しました。

https://github.com/73-ch/ofxOpenNI

---

&nbsp;
&nbsp;


１  `oF release v0.10.1` をダウンロード

[https://openframeworks.cc/ja/download/older/](https://openframeworks.cc/ja/download/older/)


&nbsp;

２   `ofxOpenNI`をこのリポジトリからダウンロード

&nbsp;

３  `ofxOpenNI-master` を `ofxOpenNI` に名前を変えて、addonフォルダにいれる。

&nbsp;


４  新規プロジェクト作成（ここでofxOpenNIは選択しなくて良いみたい。 `ofxPoco`というaddonを一応追加。必要ないと思うけど）

&nbsp;


５ `ofxOpenNI/examples/opeNI-SimpleExamples/`の`bin`を自分で作った新規プロジェクトのbinと入れ替える。

&nbsp;

６  `ofxOpenNI/mac/copy_to_data_openni_path/`の`lib`を 自分のプロジェクト `/bin/data/openni/`　の中にいれる。

&nbsp;

7 Xcode左フォルダ一覧の` addon` を右クリックして `New Group` を選択して`ofxOpenNI`というフォルダを作る。

&nbsp;

8 `addons/ofxOpenNI`の中の`include`と`src`フォルダをXcode上の`ofxOpenNI`フォルダにドラッグ。<br>

<img src="capture1.png" width="500">

上記の設定にする

&nbsp;

9 自分で作った新規プロジェクトの`bin/data/openni/` の中の`lib`フォルダもドラッグ。

&nbsp;

10 ofApp.h に　`#include "ofxOpenNI.h"`　を記述して一度ビルド。

&nbsp;

11 `framework not found QuickTime` というエラーが出るので CoreOF.configに書いてある-framework QuickTimeの記述を削除
> これは出なかったです。
 
&nbsp;

12 `clang: error: linker command failed with exit code 1`というエラーが出たので、左サイドバーから1Projectを選択して、2`BuildSetting`を選び、`Search Paths`の`Library Search Paths` に 6で指定した`lib`フォルダのパスを指定する。

![](capture2.png)

&nbsp;

13:成功
