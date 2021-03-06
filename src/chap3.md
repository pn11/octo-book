# 3章 多重キュビット

## 3.1

- 多重キュビットはブロッホ球では表わせない
- 円表示ではNキュビットを \\(2^N\\) 個の円で表せる
- 図3-2の下から上へは  
  \\[
    (\ket{0}_3+\ket{1}_3) ({1\over\sqrt{2}}\ket{0}_2+{1\over\sqrt{2}}\ket{1}_2) ({1\over\sqrt{2}}\ket{0}_1+{1\over\sqrt{2}}\ket{1}_1) \\\\
    = {1\over 2}\ket{0}_3\ket{0}_2\ket{0}_1 + {1\over 2}\ket{0}_3\ket{0}_2\ket{1}_1 + \cdots
  \\]  
  ただし、下添字はキュビットを表し、\\( \ket{0}:=\ket{0}_3\ket{0}_2\ket{0}_1, \cdots, \ket{7}:=\ket{1}_3\ket{1}_2\ket{1}_1 \\)  
  上から下へは難しそう (因数分解っぽい?)。
- <https://oreilly-qc.github.io/?p=3-1>  
  で、 `qc.reset(3)` はレジスタを準備して、 `qint.new(1, 'qubit 1')` でレジスタを qint に割りあてている。普通のプログラミングではアセンブラを書いたりしない限りレジスタのことを考えないが、少なくともこのシミュレータではそうなっている。
- もつれた多重キュビットの状態は各キュビットの組み合わせで表現できず、単一キュビットの演算からもつれた状態を生成することもできない  
  図3-3 は3キュビットの場合だが、2キュビットの場合以下のようになる。   
  \\(\ket{0}+\ket{3}\\) を2キュビットの組み合わせで書けるとすると、  
  \\[ a,b,c,d \in \mathbb{C} \\\\
      (a\ket{0}_2 + b\ket{1}_2) (c\ket{0}_1+d\ket{1}_1) \\\\
      = ac\ket{0}_2\ket{0}_1 + ad\ket{0}_2\ket{1}_1 +  bc\ket{1}_2\ket{0}_1 +bd\ket{1}_2\ket{1}_1 \\\\
      = ac\ket{0} + ad\ket{1} + bc\ket{2} + bd\ket{3}
  \\]  
  と表すことができることになる。これが \\(\ket{0}+\ket{3}\\) と等しいためには、  
  \\(ac=bd=1\\) かつ \\(ad=bc=0\\) が必要だが、これは矛盾する。(証明 by ふぇるみうむ氏)

### 3.2

- レジスタが16進数で書いてあるけど実質2進数なのややこしい (訳注ありがたい)
- なぜ0はじまりではないのか

### 3.3

- N番目のキュビットに対する単一キュビット演算 (NOT, PHASE, HAD)は、円表示ではN個離れた「演算対象ペア」の円に適用される
- READ の場合、「演算対象ペア」の左側を半径を2乗して足し上げると出力が0になる確率。右側が1

### 3.4

- キュビットが増えると円表示の円の数も増えるけど、パターンとして見ると意味があるかも？

### 3.5 CNOT

- アダマールしてから CNOT をすると量子もつれ状態を生成できる
  - p. 49 の「これは意味のある結果です」は make sense の翻訳がおかしい？ (原書未確認)

### 3.6

- 節題がだいぶ怪レい...
- p.50 QNRG -> QRNG
- <https://oreilly-qc.github.io/?p=3-2>

### 3.7

- CPHASE の場合、制御キュビットとターゲットは可換
  - なので演算の記号もそのように描く
  - 制御キュビットが \\(\ket{1}\\} のときに作用するという条件と、PHASE演算は相対位相だけ気にするのでターゲットキュビットの \\(\ket{1}\\} にのみ作用するという条件が同じため
- Z=PHASE(180) が HAD と NOT で作れたように、 CZ=CPHASE(180) は HAD と CNOT で作れる

#### 3.7.1 位相キックバック

- ~~何やってるのかよくわからん~~
- Register 2が操作できるブーリアンだと思って、これが制御キュビットなので、 Register 2 の状態によって Register 1を制御できているとい動きになっている。
- Register 2 は操作の前後で変化しない
- <https://oreilly-qc.github.io/?p=3-3>
- register 分けるなら円表示も分けたほうが分かりやすい気がする

### 3.8 CCNOT (Toffoli Gate)

- CNOT にさらに condition が追加されただけなので特に難しくない
- [IBM Quantum Challenge 2021](https://challenges.quantum-computing.ibm.com/iqc21) の第一問に出てきたやつ

### 3.9 SWAP and CSWAP
 
- CCNOT 3つで CSWAP を実装できる
- CSWAP を用いて2の乗算を実装できる？ (詳しくは5章、12章)

#### 3.9.1 Swap Test

- READ を使わずに2つのキュビットが同じ状態かどうかを判定できる
- <https://oreilly-qc.github.io/?p=3-4>
- input1 と input2 の状態が一致していたら `output.read()` の結果は必ず1になり、そうでない場合は状態の忠実度 (fidelity) に応じて0か1がランダムに得られる
- input1 と input2 は任意のベクトルなので、 \(\ket{0}\) \(\ket{1})( だけじゃなく、 \(\textrm{input1}=\textrm{input2}=1\over\sqrt{2}\ket{0}+1\over\sqrt{2}\ket{1}\) でもちゃんと output1 が1になる 
 
 ### 3.10
 
 - CNOT と他の演算を組み合わせて単一キュビット演算を多重キュビット演算にできることは分かったが、自分で思いつくのは難しそう
 - <https://oreilly-qc.github.io/?p=3-5>

### 3.11

- <https://oreilly-qc.github.io/?p=3-6>
- このハンズオンは特に新しい内容は出てこないが、 PHASE 演算でもつれの割合を操作できることが確認できる

以下のように for を使って多数回試行できる (daiju 氏)

```javascript
qc.reset(2);
var a = qint.new(1, 'a');
var b = qint.new(1, 'b');

var c = [0, 0, 0, 0];
for (var i =0; i < 1000; i++) {
    qc.write(0);
    a.had();
    // now prob of a is 50%
    b.had();
    b.phase(45);
    b.had();
    // now prob of b is 15%
    b.cnot(a);
    // Now, you can read *either*
    // qubit and get 50% prob.
    // If the result is 0, then
    // the prob of the *remaining*
    // qubit is 15%, else it's 85%
    var a_result = a.read();
    var b_result = b.read();
    c[a_result + b_result * 2] += 1;
}
// 00, 01, 10, 11 の各状態の頻度をプリント
qc.print(c + '\n')
```
