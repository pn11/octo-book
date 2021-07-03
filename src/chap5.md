# 5章 量子算術演算と量子論理演算

## 5.1

- 復習
  - CCNOT = Toffoli gate
  - qubit はコピーできない
  - READ 以外の基本的な QPU 演算は可逆 (WRITE は READ + NOT でできる -> 2.3.4)
  - 演算が可逆なのはユニタリだから？

## 5.2

- 量子ニブル (qunible) を使った算術演算を考える

### 5.2.1

- increment と decriment <https://oreilly-qc.github.io/?p=5-1>
- これらは普通の整数と量子整数の足し算になっている

## 5.3

- 「複製不可能性に違反する」の説明は「可逆性の要件に違反する」の偽の命題を仮定していておかしい？ 演算がユニタリであることから可逆的であることが言えて、複製不可能性はそこから導かれるという方が自然？
- +演算子は可逆性と複製不可能性に反するので += 演算子を実装する  
  <https://oreilly-qc.github.io/?p=5-2>
- QCEngine で add が実装されているのはこのあたり -> [QCEngine/qcengine_int.js at master · machinelevel/QCEngine](https://github.com/machinelevel/QCEngine/blob/master/src/qcengine_int.js#L1162)

## 5.4

- [補数（complement）とは - IT用語辞典 e-Words](https://e-words.jp/w/%E8%A3%9C%E6%95%B0.html)
- 実は C++ で負の整数を2の補数で表すことが仕様で定められたのは C++20 ! ([符号付き整数型が2の補数表現であることを規定 - cpprefjp C++日本語リファレンス](https://cpprefjp.github.io/lang/cpp20/signed_integers_are_twos_complement.html))

## 5.5

- 乗算は可逆にするのが困難
- 可逆な演算の例: 二乗してから足す <https://oreilly-qc.github.io/?p=5-3>
- `b <- b*b` は不可逆だが、 `a += b*b` の逆演算は `a -= b*b` で、可逆
