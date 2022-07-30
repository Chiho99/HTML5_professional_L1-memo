# マルチメディアグラフィックスAPI

## 1.マルチメディア

>マルチメディアコンテンツ(`audio要素`と`video要素`)をJavaScriptを使って制御することが可能

### JavaScriptで実行可能な操作

- コンテンツの再読み込み
- 再生開始
- 再生中断

### 以下のようなデータを取得し、利用可能

- コンテンツが再生・早送り等可能な状態か
- ネットワークの状態
- エラー情報
- コンテンツの場所
- コンテンツの長さ
- 音量
- トラック情報

## 2. ストリーミング

>ストリーミングを実現する技術

### Adaptive Streaming技術

通信状況に合わせて、適切なビットレートの動画を選択し、スムーズなストリーミングを再生する技術

- HLS(HTTP Live Streaming)
  - 米Apple社が開発した動画をストリーミング配信するためのプロトコル
  - **HTTPベース**で特別なストリーミングサーバを使わず、通常のWebサーバから配信する事が可能
  - HTTPSを使った暗号化や認証にも対応している
- MPEG-DASH
  - 米Adobe社やMS社などにより開発されたプロトコル
  - DASHはDynamic Adaptive Streaming over HTTPの略で、HLSと同様にHTTPプロトコルを利用しているので、通常のWebサーバーから配信することが可能
  - MPEG-DASHは2012にISOにて**標準化**された

> ストリーミング配信のためのJavaScript API

### Media Source Extensions

- HLSやMPEG-DASHのように、HTTPでストリーミング配信されるコンテンツを再生するために作られたAPI
  - `video要素`でストリーミング配信されるコンテンツを再生可能
  - Adaptive Streaming技術にも対応しているため、再生途中で動画のビットレートを変更することも可能

### Digital Rights Management

- デジタル著作権管理

### Encrypted Media Extensions

- 暗号で保護されたストリーミングコンテンツを再生する際に使用する
  - Media Source ExtensionsとEncrypted Media Extensionsを組み合わせることで、DRMで保護されたストリーミングコンテンツをWebブラウザ上で再生することができる

> グラフィックス

### Canvas

- JavaScriptを使って画像を描画するための仕様
- 画像を**ビットマップ**形式で描画する
  - ビットマップ形式のため、拡大・縮小すると画像が粗くなる
  - 描画した画像を変更するには、全体を書き直す必要がある

### Canvasを利用する際の流れ

1. HTMLに`canvas要素`を用意する
2. JavaScriptで`canvas要素`を参照し、描画用のContextオブジェクトを取得する
3. JavaScriptを使って描画する

以下のような、描画操作が可能

- 線を書く
- 円、四角を書く
- 色を塗る
- テキストを書く
- 画像ファイルを読み込む
- 拡大・縮小・回転する

### SVG(Scable Vector Graphics)

- ベクター形式の画像
  - SVGは**ベクター形式**のため、拡大・縮小・回転といった変形をしても、**画像が粗くならない**
  - **XML形式**で画像を作成する

以下のような要素がある

- 円を作成する`circle`
- 楕円を作成する`ellipse`
- 線を作成する`line`
- 四角形を作成する`rect`
- パスを定義する`path`

使用例

```html
<svg width="640" height="320">
  <circle cx="320" cy="160" r="150" stroke="black" fi>
</svg>
```
