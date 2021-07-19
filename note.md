- reactアプリケーションが開発サーバーで動き始めるまでの順序
    - (TypeScriptを使うとき) tscでトランスパイルする。(*.tsx,*.ts -> *.js)
    - 上でトランスパイルしたものをBabelでトランスパイルする。
        - 少なくともES2017(async/await)を使っている
        - ES2015へ変換する。
    - プロジェクトで必要なファイル(html,css,js,画像ファイルなどなど)をバンドルしてbundle.jsという一つのファイルにまとめる。
        - そうすることで一つのファイルだけを配信すればよくなる。
        - また圧縮機能などもある（？）
    - 開発サーバはwebpackの機能であり、開発モードの時はメモリ上にバンドルされたものが展開され実行される。

- reactをテストする
    - バンドルされたファイルに対してテストを行う？
    - jestを使った単体テスト
    - TS公式
        - https://typescript-jp.gitbook.io/deep-dive/intro-1/jest
        - 
    - Jest公式
        - https://jestjs.io/blog/2019/01/25/jest-24-refreshing-polished-typescript-friendly#typescript-support
    - ソースマップ(sourcemap)
        ```
         CoffeeScript や TypeScript のような言語からコンパイルするように、ページで実行する JavaScript が機械生成されることがあります。
        このような状況では、ブラウザーがダウンロードした変換後のソースよりも、元のソースをデバッグするほうがとても容易です。ソースマップ は変換後のソースと元のソースを関連付けるファイルであり、ブラウザーが元のソースを再構成して、そのソースをデバッガーに提供できます。
        ```
    - バベルと型チェックはしない。（できない）
    - ts-jestは型チェックも行う
    - cssモジュールをインポートしてるとエラー
        - https://jestjs.io/ja/docs/webpack#css%E3%83%A2%E3%82%B8%E3%83%A5%E3%83%BC%E3%83%AB%E3%81%AE%E3%83%A2%E3%83%83%E3%82%AF
    