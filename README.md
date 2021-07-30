# 『動かして学ぶ量子コンピュータプログラミング』 (タコ本) のやっていき記録

- 公開ページ: <https://pn11.github.io/octo-book/>
- GitHub Pages 用 ブランチ: <https://github.com/pn11/octo-book/tree/gh-pages>
  - このブランチは [peaceiris/actions-gh-pages](https://github.com/peaceiris/actions-gh-pages) が作ったもの
- GitHub Actions: <https://github.com/pn11/octo-book/blob/master/.github/workflows/gh-pages.yml>

## 開発用情報

1. VSCode で開く
1. コマンドパレットで `Reopen in Container` を実行 (要 remote containers extension)
1. ターミナルで `mdbook serve` を実行
1. <http://localhost:3000> でプレビュー
1. 変更を master に push すると GitHub Actions によって [gh-pages](https://github.com/pn11/octo-book/tree/gh-pages) にビルドされて公開される
