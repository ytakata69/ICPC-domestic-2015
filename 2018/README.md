# 2018 ACM-ICPC 国内予選

## A: 所得格差

簡単なので省略。

## B: 折り紙

紙を折る手順をそのまま模倣して，各マスの紙の厚さを計算すればよい。
が，原点が毎回変わることとか，紙の中央より右や上で折ることも考慮しないといけなかったりとかで，ミスしやすい感じ。

## C: 超高層ビル「みなとハルカス」

C言語なら単純な尺取法でok。低い階から始めて最初に見つかった解が最適解。

Pythonだと少し時間が掛かり過ぎ。
`c2.py`のコメントに書いた通り，解となるフロアの総数 n は2 * bの約数であり，√(2 * b) 以下である。√(2 * b) 以下のすべての n について順に解になるか調べればよい。

## D: 全チームによるプレーオフ

C言語なら普通のバックトラック法でok。数独やその他のパズルの解をバックトラックで求めるのとほぼ同じ。

Pythonだと少し時間が掛かり過ぎるので，`d.py`では対称性を利用して少し探索空間を減らした。
もっとよく考えればもっと減らせると思う。

## E: 浮動小数点数

糸口を見つけるまで時間が掛かったが，「桁上がりが起きるまでは普通の加算と同じ」ということに気づいたら後は比較的簡単。

## F: 正三角形の柵

あきらめ。

## G: 数式探し

「1倍」がなければ多少楽なのに…。

「かっこの中は，その中だけ考えるか全体をひとかたまりとして扱うかのどちらか」
ということが容易にわかるので，以下のような構造を考えて式の中の部分リスト（一般に項の途中から始まって項の途中で終わる）を調べていけばよい。

- 式 = 項のリスト
- 項 = 因子のリスト
- 因子 = 整数または式

その際，因子である式はひとかたまり（1整数）と見なせる。値が減る演算はないので，尺取法で，目標値と等しくなる部分リストを探せばよい（ただし「1倍の列」を特別扱いする必要がある）。

Pythonはデフォルトでは再帰の深さが1000程度に制限されているようだ。デフォルトのままだとstack overflowになってしまうので，`g.py`では`sys.setrecursionlimit`を呼び出してスタック長を増やしている。

## H: 優秀なプログラマになるには

まだ糸口が見つからず。
