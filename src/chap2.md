# 2章 単一キュビット

## 2.2

- 円表示の説明

## 2.3

- QPU演算の説明
  - HAD (アダマール) 演算は重ね合わせ状態を作る演算で重要
    - 円表示より行列で計算したほうが分かりやすい cf. [1入力量子ゲート - EMANの量子力学](https://eman-physics.net/quantum/computer3.html)
  - WRITE -> HAD -> READ でランダムビット生成器を作れる -> <https://oreilly-qc.github.io/?p=2-1>
  - ランダムビットを8個に増やせばランダムバイト -> <https://oreilly-qc.github.io/?p=2-2>

## 2.5

- QPU 演算の組み合わせの例
  - NOT = HAD + PHASE(180) + HAD
  - ROOT-of-NOT = HAD + PHASE(-90) + HAD  
    (なぜ90度ではなく-90度を定義としている？)  
    <https://oreilly-qc.github.io/?p=2-3>

## 2.6

- 暗号通信の例として量子スパイハンター
  - 実際は暗号化はしていない。送ったメッセージが盗聴されているかどうかを検出する
  - Web の例 <https://oreilly-qc.github.io/?p=2-4> よりも本のコードの方が意図を汲みとりやすい
