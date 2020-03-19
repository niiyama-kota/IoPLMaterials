# 京都大学工学部専門科目「プログラミング言語処理系」講義資料

## お知らせ

- 3月4日: 2020年の講義資料ページを作りました．

## 教科書

（鋭意 Markdown 化中．）

- [オリエンテーション資料](misc/orientation.md)
- [OCaml入門テキスト by 五十嵐淳](textbook/mltext.pdf)
- プログラミング言語処理系テキスト by 五十嵐淳，馬谷誠二，末永幸平
  - [1章: イントロダクション](textbook/chap01.md)
  - [2章: 概論的な話](textbook/chap02.md)
  - 3章
    - [3.1: MiniML1 のシンタックス](textbook/chap03-1.md)
    - [3.2: 各モジュールの機能 (1)](textbook/chap03-2.md)

## リンク集

- [実験3ホームページ](https://kuis-isle3sw.github.io/kuis-isle3sw-portal/)
- [専門科目「プログラミング言語」ホームページ](https://github.com/aigarashi/PL-LectureNotes)
  - [の中の OCaml のページ（最低このくらいはわかってないとキツイ）](http://www.fos.kuis.kyoto-u.ac.jp/~igarashi/class/pl/03-ocaml.html)
  - [の中の OCaml で二分探索木を書くページ（これもわかってないとキツイ）](http://www.fos.kuis.kyoto-u.ac.jp/~igarashi/class/pl/04-bst-ocaml.html)

## 講義に関する情報

- 講義をする人: 末永幸平（[@ksuenaga](http://www.twitter.com/ksuenaga/), https://researchmap.jp/ksuenaga/）
- 講義が行われる時間: 月曜2限
- 講義が行われる場所: 総合研究7号館講義室1
- Language used in the class: Japanese

## 講義予定

一部の資料と過去問は PandA で配布するので，PandA を見られる状態にしておくこと．
   
| 日付 | 内容 | 対応する教科書中の場所 |
|------|-----------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 4/13 | オリエンテーション，イントロダクション，OCaml復習| [オリエンテーション資料](misc/orientation.md), [教科書1章](textbook/chap01.md), [教科書2章](textbook/chap02.md), [OCaml入門テキスト](textbook/mltext.pdf) |
| 4/20 | OCaml復習| [OCaml入門テキスト](textbook/mltext.pdf) |
| 4/27 | | |
| 5/11 | | |
| 5/18 | | |
| 5/25 | 中間試験 | |
| 6/1 | | |
| 6/8 |  | |
| 6/15 | | |
| 6/22 | | |
| 6/29 | | |
| 7/6 | | |
| 7/13 | | |
| 7/20 | | |
| ?/?? | 期末試験 | |

## OCaml の設定方法

OCaml のパッケージシステムである OPAM を用いてインストールするのが簡単である．
https://opam.ocaml.org/doc/Install.html を読んでインストールすること．
以下は簡便のために抜粋したものであるが，最新の情報ではないかもしれないので，できれば上記ページを読むこと．

- `sh <(curl -sL https://raw.githubusercontent.com/ocaml/opam/master/shell/install.sh)`
  - `curl` 関係のエラーが出る場合は https://raw.githubusercontent.com/ocaml/opam/master/shell/install.sh のスクリプトをダウンロードして `sh install.sh` を実行．
  - 各自のパッケージ管理システム（Mac なら homebrew や macport，Linux なら yum や apt 等）を用いて opam をインストールしてもよい．
- _以下では実行ログの最後に`eval $(opam env)`を実行せよと書いてあることがあるので，その時は次の作業に移る前に `eval $(opam env)` を実行すること．_
- `opam init` を実行
  - 途中設定ファイルに opam が書き込んでよいか聞かれる．全部 `y` にしておくと楽は楽である．
- `opam switch create 4.07.1`を実行
- `opam install depext`
- `opam install user-setup`

演習にはいくつかのパッケージが必要である．OPAM が入った状態であれば，以下のコマンドを順に実行することでこれらのパッケージを導入できる．

- `opam depext menhir dune ounit`
- `opam install menhir dune ounit`

便利情報がいくつかある．

- Emacs を使う人は tuareg-mode を使うとよい．`opam install tuareg` のあとに `opam user-setup install` を実行．
- emacs と vim では merlin https://ocaml.github.io/merlin/ が便利である．これがあるとエディタが IDE になる．`opam install merlin` のあとに `opam user-setup install` を実行．
  - Sublime-Text バージョンもベータ版として提供されている https://github.com/let-def/sublime-text-merlin
- VSCode で OCaml を使う方法がいくつかあるらしい．（調べた人は情報ください．）
  
