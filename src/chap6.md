# 6章 振幅増幅

## 6.1

- 振幅増幅 (amplitude apmlification) は位相差を振幅の差に変換することで READ しやすくする
- <https://oreilly-qc.github.io/?p=6-1>
- mirror サブルーチン = Grover アルゴリズム

## 6.2, 6.3

- <https://oreilly-qc.github.io/?p=6-2>
- 振幅増幅を繰り返し行うと結果は周期的になる
- 最適な反復回数は \\(N_{AA} = \lfloor { \pi \sqrt{2^n} \over 4 } \rfloor \\) になるとのことだが、これは解析的に出るのか、経験式なのかよく分からない。
- Daiju 氏による補足ノート [hinohi/quantum-note/6-amplitude-amplification.ipynb](https://nbviewer.jupyter.org/github/hinohi/quantum-note/blob/main/6-amplitude-amplification.ipynb)

(ここまで 2021/08/07)

## 6.4

- <https://oreilly-qc.github.io/?p=6-2>
- 位相差がある成分が複数の場合の増幅も考えることができる
- 相対位相なので、半数の状態が反転しているような場合は状態が変わらず、増幅できない
- 複数の場合の 最適な反復回数は \\(N_{AA} = \lfloor { {\pi \over 4} {\sqrt{2^n} \over m} } \rfloor \\)

## 6.5

- 振幅増幅の応用例
  - 振幅増幅と量子フーリエ変換を組み合わせて量子和推定 (quantum sum estimation) (11章) に使える
  - 振幅増幅は boolean satisfiability (SAT) 問題の高速化に使える。ここの計算量の記述は日本語が怪しいので調べたほうがよさそう

## 6.6

- 「際」→「差異」
- 振幅増幅を感覚的に解説すると、重心を求めてそこからの距離で増幅するような感じ。たしかにグローバーにはアダマールが入っているので、平均しているような感じがある？(適当)

(ここまで 2021/08/22)
