推薦システムのアルゴリズム
==========================

* Author : [Toshihiro Kamishima](http://www.kamishima.net/)
* Copyright : Copyright (c) 2007-2014 Toshihiro Kamishima all rights reserved.
* Download : <http://www.kamishima.net/archive/recsysdoc.pdf>

本稿は推薦システムについてまとめたものである．

人工知能学会誌2007年11月号 (vol.22 no.6)，2008年1月号 (vol.23 no.1) ，および2008年3月号 (vol.23 no.2) の3回に渡って連載した解説記事「推薦システムのアルゴリズム(1)〜(3)」をもとにしている．
この原稿に，誤りの訂正，目次と索引の追加，新しい内容の追加などを随時行って更新している．

コンパイル手順
--------------

ここにあるファイルの他に以下のファイルも必要です．

* <http://www.kamishima.net/asset/ebib.bib>
* <http://www.kamishima.net/asset/emisc.bib>
* <http://www.kamishima.net/asset/epublist.bib>
* <http://www.kamishima.net/asset/jbib.bib>
* <http://www.kamishima.net/asset/jmisc.bib>
* <http://www.kamishima.net/asset/jpublist.bib>
* <http://www.kamishima.net/asset/mybook.bib>
* <http://www.kamishima.net/asset/mathsymbols.sty>

UTF-8 で符号化した日本語ファイルをコンパイルできる pLaTeX 環境にて，以下のコマンドでコンパイルできます::

    git --no-pager log -1 --pretty='%ai; %h' > version.tex
    platex main
    pbibtex main
    mendex -r -c -g -p any -s main.ist -d main.dic main.idx
    platex main
    platex main
    platex main
    dvipdfmx -p a4 -o recsysdoc.pdf main
