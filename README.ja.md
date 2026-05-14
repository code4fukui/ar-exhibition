# ar-exhibition

> DATA: [神山まるごと高専 学生](https://kamiyama-marugoto.com/) (Students of Kamiyama Marugoto Kosen)

バーチャルアート展覧会を作成するための、シンプルなウェブベースのARアプリケーションです。このプロジェクトではThree.jsと`egxr.js`を使用して、一連の画像を3D平面上に表示し、拡張現実（AR）環境または標準的なデスクトップブラウザで閲覧できるようにします。

**[デモを見る](https://code4fukui.github.io/ar-exhibition/)**

## 機能

-   **WebXRによるAR:** 互換性のあるARデバイスを使用して、現実空間で画像ギャラリーを閲覧できます。
-   **デスクトップ対応:** 標準的なデスクトップブラウザ向けに、一人称視点コントロール（マウスルックとキーボードナビゲーション）を備えています。
-   **動的な画像読み込み:** 設定可能なリストから画像を読み込み、3D平面上に表示します。
-   **調整可能な3Dライティング:** 環境光（アンビエントライト）と平行光（ディレクショナルライト）を使用した、シンプルで効果的なライティング設定。

## 使い方

このプロジェクトをローカルで実行するには、CORSエラーを回避するためにローカルWebサーバーが必要です。

1.  **リポジトリのクローン:**
    ```bash
    git clone https://github.com/code4fukui/ar-exhibition.git
    cd ar-exhibition
    ```

2.  **ローカルサーバーの起動:**
    Python 3がインストールされている場合は、以下を使用できます:
    ```bash
    python3 -m http.server
    ```

3.  **ブラウザで開く:**
    ChromeやFirefoxなどのWebXR対応ブラウザで `http://localhost:8000` にアクセスします。

## カスタマイズ

`index.html` の `imgs` 配列を編集することで、独自の画像を表示できます。配列内の各オブジェクトで、表示する画像を定義します:

-   `fn`: 画像ファイルへのパス。
-   `height`: 3Dシーンにおける画像平面の高さ。幅はアスペクト比を維持するように自動計算されます。
-   `text`: 説明文（メタデータ）。

```javascript
// index.html 内
const imgs = [
  { fn: "./img1.jpg", height: .32, text: "意味のないツイテール" },
  { fn: "./img2.jpg", height: .41, text: "できかけのショートケーキ" },
  { fn: "./img3.png", height: .41, text: "幸福の証明は、幸福の中で不幸に鳴ること" },
  // ここに独自の画像を追加
];
```

含まれている画像は以下の通りです:
-   `img1.jpg`: 手描きのアバター。
-   `img2.jpg`: 抽象的なプレースホルダー画像。
-   `img3.png`: 日本語テキストを含むコンセプトアート。

## 依存関係

このプロジェクトは、以下のオープンソースライブラリを使用して構築されています:

-   [three.js](https://code4fukui.github.io/three.js/): JavaScript用の3Dグラフィックスライブラリ。
-   [egxr.js](https://code4fukui.github.io/egxr.js/): WebXR開発を簡略化するためのThree.jsラッパー。
-   [PCControl.js](https://code4fukui.github.io/vr-beetle/PCControl.js): デスクトップでの一人称視点コントロール用モジュール。
-   [loadTexture.js](https://code4fukui.github.io/ar-wall/loadTexture.js): テクスチャ読み込み用ユーティリティ。

## ライセンス

このプロジェクトはMIT Licenseの下で利用可能です。

---
[GitHubのソースコード](https://github.com/code4fukui/ar-exhibition/)
