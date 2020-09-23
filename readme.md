# KNMemoPad 機能追加版
Knatech 氏制作の SHARP Brain 用テキストエディタ **KNMemoPad** に、**文字色と背景色の変更機能**および **UTF-8 と UTF-16 LE のサポート**を追加したフォークです。既存機能はそのままですので、何かミスがなければ\*完全な上位互換として動作するはずです。

オリジナル版との干渉が起こることを防ぐため、設定の保存ファイルは別にしています。

オリジナル版は[ここ](https://bitbucket.org/knatech/brain-tools/src/master/)から入手できます。詳しい使い方も掲載されています。

\* Knatech 氏は独自DLLを用いて便利なダイアログなどの実装を行われていたため、私はMakefileの使えないeVC4で試行錯誤しながらlibの作成や本体プログラムのコンパイルを行った、という過程があります。また、文字コードのサポートを広げるためにファイル読み込み・保存の内部処理を大きく書き換えています。

# 動作要件
これは **Windows CE (ARMv4I)** 専用ソフトウェアです。**SHARP Brain PW-SH1 (Windows Embedded CE 6.0, ARMV4I)** で動作確認を行っています。

# 文字コード切り替えについて
文字コード自動判別などという高尚な機能は搭載していません(足してくださる方がいらっしゃれば大歓迎ですが)。なので、 **Tools -> Charset...** でその時点で選択されている文字コードで Open, Reload, Save が行われます。予め開きたいor保存したい文字コードに設定してからそれらの処理を行ってください(違う文字コードで開いてしまった場合、設定し直してから Reload を行えば大丈夫です。)。

ちなみに、UTF-8 のBOM有り・無しは読み込み時に判別されます(これは簡単なので)。

# 使用上の注意
**製作者は、このプログラムの利用によって生じた、いかなる損害についても責任を負いません。**

# 著作権情報など
オリジナル版が GNU General Public License v3.0 で配布されていますので、その規定に従い同じく **GNU General Public License v3.0** で配布します。

# 変更履歴
## v0.12 rev2 (2020/9/23)
UTF-8(BOM有り無し両方) と UTF-16 LE に対応した。それに伴い、ファイル読み込み・保存の部分を大きく書き換えた。これによりオリジナル版の、ファイル末尾に勝手に改行が追加される仕様はなくなった。

色選択ダイアログ左下の、作成した色リストを保存するようにした。

バージョン情報を追加し、ソフトウェア内からも確認できるようにした。

コマンドラインや関連付けで指定されたファイルも開けるようにした。

## v0.12 rev1 (2020/9/20)
文字色・背景色を変更できる機能を追加した。