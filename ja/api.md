# API リファレンス

## `createRenderer([options])`

任意の引数  [options](#renderer-options) を用いて [`Renderer`](#class-renderer) インスタンスを生成します。

```js
const { createRenderer } = require('vue-server-renderer')
const renderer = createRenderer({ ... })
```

## `createBundleRenderer(bundle[, options])`

サーババンドルと任意の引数  [options](#renderer-options) を用いて [`BundleRenderer`](#class-bundlerenderer) インスタンスを生成します。

```js
const { createBundleRenderer } = require('vue-server-renderer')
const renderer = createBundleRenderer(serverBundle, { ... })
```

引数 `serverBundle` には次のいずれか１つを指定できます:

- 生成されたバンドルファイル (`.js` または `.json`)への絶対パス。ファイルパスとして扱われるために `/` で開始されなければなりません。

- webpack と `vue-server-renderer/server-plugin` によって生成されたバンドルオブジェクト。

- JavaScript コードの文字列 (非推奨)。

より詳しい情報は、 [サーババンドルの紹介](./bundle-renderer.md) と [ビルド設定](./build-config.md) の項目を参照してください。

## `クラス: Renderer`

- #### `renderer.renderToString(vm[, context], callback)`

    Vue インスタンスを文字列として描画します。context オブジェクトの指定は、任意です。callback は、第１引数にエラー内容、 第２引数に描画された文字列を受け取る、典型的な Node.js のコーディングスタイルである関数を指定します。

- #### `renderer.renderToStream(vm[, context])`

    Vue インスタンスを Node.js のストリームへ描画します。context オブジェクトの指定は任意です。より詳しい情報は、[ストリーミング](./streaming.md) の項目を参照してください。

## `クラス: BundleRenderer`

- #### `bundleRenderer.renderToString([context, ]callback)`

    サーババンドルを文字列として描画します。context オブジェクトの指定は、任意です。callback は、第１引数にエラー内容、 第２引数に描画された文字列を受け取る、典型的な Node.js のコーディングスタイルである関数を指定します。

- #### `bundleRenderer.renderToStream([context])`

    サーババンドルを Node.js のストリームへ描画します。context オブジェクトの指定は任意です。より詳しい情報は、[ストリーミング](./streaming.md) の項目を参照してください。
