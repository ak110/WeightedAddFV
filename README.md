MergeFV
=======

重みファイル(Bonanzaのfv.binのような2バイト符号付整数値が連続で記録されたバイナリファイル)の重み付き加算を行うコマンドラインツールです。
エラー時も出力ファイルが半端な状態で残るなど、いろいろ適当実装なので悪しからず。


使い方
----
    MergeFV [options] InFile1 [InFile2 ...] OutFile

* InFile     入力元のファイルパス
* OutFile    出力先のファイルパス

* -w 重み     各入力の重みを実数のカンマ区切りで指定する。省略時は1.0/入力ファイル数になる。(通常の算術平均)


例
----
    MergeFV FV1.bin FV2.bin result.bin

FV1.binとFV2.binの各要素の平均をresult.binに出力。

    MergeFV -w 0.3,0.7 FV1.bin FV2.bin result.bin

FV1.binの各要素の値に0.3を掛けたものと
FV2.binの各要素の値に0.7を掛けたものの和(端数は四捨五入)を、
result.binに出力。
