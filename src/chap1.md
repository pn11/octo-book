# 1章 はじめに

- QPU の説明
- QPU simulator の [QCEngine](https://oreilly-qc.github.io/) の使い方
  - マウスホバーでその時点での状態が分かるの便利そう。
- QPU 命令のリストアップ
- シミュレータの限界
  - 量子ビットが1つ増えるごとに必要なメモリが2倍になるため、現実的には手元では26個、世界最大でも51個。
- ハードウェア制限
  - 現在世界最大のものは70量子ビット程度で誤り訂正を持たない ([NISQ](https://dojo.qulacs.org/ja/latest/notebooks/2.1_NISQ_and_long_term.html))。
  - 本書ではハードウェアのことは意識せず、理想的な論理量子ビットを仮定し、もっと高レイヤーのみ考える。
- QPU と GPU はわりと特徴が共通している
