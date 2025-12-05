# サンプル画像について

このフォルダには実際の画像ファイルは含まれていません。
以下の方法で画像を用意してください。

## 🎨 画像の入手方法

### 方法1: 自分で描く（推奨）

#### 必要なソフト
- **CLIP STUDIO PAINT** (有料/体験版あり)
- **Photoshop** (有料)
- **Krita** (無料)
- **GIMP** (無料)
- **FireAlpaca** (無料)

#### 制作手順

**hand.png（手+ペンの画像）**
```
1. 新規キャンバス: 300×400px
2. 背景: 透過
3. 内容: ペンを持った手を描く
4. エクスポート: PNG形式
5. ファイル名: hand.png
```

**tablet.png（タブレット画像）**
```
1. 新規キャンバス: 400×300px
2. 背景: 透過
3. 内容: タブレットを真上から見た図
4. エクスポート: PNG形式
5. ファイル名: tablet.png
```

詳しくは [../IMAGE_GUIDE.md](../IMAGE_GUIDE.md) を参照。

### 方法2: AI生成

#### Stable Diffusion
```
プロンプト例（手の画像）:
"anime style hand holding digital pen, 
transparent background, top view, 
clean design, simple illustration"

ネガティブプロンプト:
"background, complex, realistic"
```

#### Midjourney / DALL-E
```
"hand holding stylus pen, anime style, 
transparent background, illustration"
```

生成後、背景を透過処理してPNG形式で保存。

### 方法3: フリー素材を加工

#### おすすめサイト
- **いらすとや**: https://www.irasutoya.com/
- **Pixabay**: https://pixabay.com/
- **unDraw**: https://undraw.co/

検索キーワード：
- "hand holding pen"
- "digital drawing"
- "tablet illustration"

ダウンロード後、必要に応じて背景を透過処理。

### 方法4: 写真を加工

1. 自分の手でペンを持った写真を撮影
2. 背景を透過処理
3. イラスト風に加工（オプション）

#### 背景透過ツール
- **remove.bg**: https://www.remove.bg/ja
- **Photoshop**: 自動選択ツール
- **GIMP**: 前景抽出ツール

## 📐 推奨サイズと形式

### hand.png
- **サイズ**: 300×400px〜500×600px
- **形式**: PNG（透過）
- **容量**: 1MB以下推奨

### tablet.png
- **サイズ**: 400×300px〜600×400px
- **形式**: PNG（透過）
- **容量**: 1MB以下推奨

## 🎯 デザインのポイント

### 手の画像

```
┌───────────┐
│           │
│    ✋    │  ← ペンを持った手
│    /│\   │     自然な角度で
│   / │ \  │
│  ペン │  │     ペン先が画像の
│   ｜ │  │     中心付近にあると良い
│   ▼  │  │
│ ●ペン先 │
│      │  │
└───────────┘
```

#### ポイント
- ペン先を画像の中心〜下寄りに配置
- 手首から先を描く（腕全体は不要）
- 自然な描画姿勢（15〜30度傾ける）
- 透過背景

### タブレット画像

```
┌─────────────────┐
│  ┏━━━━━━━━━┓  │
│  ┃           ┃  │
│  ┃  TABLET   ┃  │  ← 真上から見た図
│  ┃           ┃  │     シンプルなデザイン
│  ┗━━━━━━━━━┛  │
└─────────────────┘
```

#### ポイント
- 真上から見た図（俯瞰）
- 長方形の画面部分
- シンプルなフレーム
- 透過背景

## 🌈 画風のバリエーション

### アニメ調
- はっきりとした線
- ベタ塗り
- シンプルな影

### リアル系
- 詳細な陰影
- 肌の質感
- ハイライト

### ミニマル
- シンプルな線
- 単色
- デフォルメ

### ドット絵
- ピクセルアート
- レトロ風
- 8bit/16bit風

## 📦 このフォルダに配置する場合

HTMLファイルがあるフォルダではなく、
このsamplesフォルダに配置したい場合：

### OBSでの設定
```
ローカルファイル: 
drawing_hand_animator.html?hand=samples/hand.png&tablet=samples/tablet.png
```

URLパラメータで相対パスを指定します。

## 💾 ファイル名のルール

### 基本
- `hand.png` - デフォルトの手
- `tablet.png` - デフォルトのタブレット

### バリエーション例
- `hand_anime.png` - アニメ調の手
- `hand_real.png` - リアル系の手
- `hand_simple.png` - シンプルな手
- `tablet_black.png` - 黒いタブレット
- `tablet_white.png` - 白いタブレット

### 命名のコツ
- 小文字を推奨
- スペース不可（アンダースコア `_` を使用）
- 日本語ファイル名は避ける

## 🔄 複数パターンの管理

### フォルダ構成例
```
DrawingHandAnimator_Browser_v1.0/
├── drawing_hand_animator.html
├── samples/
│   ├── README.md（このファイル）
│   ├── anime/
│   │   ├── hand.png
│   │   └── tablet.png
│   ├── real/
│   │   ├── hand.png
│   │   └── tablet.png
│   └── simple/
│       ├── hand.png
│       └── tablet.png
```

### 使用方法
```
アニメ調: ?hand=samples/anime/hand.png&tablet=samples/anime/tablet.png
リアル系: ?hand=samples/real/hand.png&tablet=samples/real/tablet.png
シンプル: ?hand=samples/simple/hand.png&tablet=samples/simple/tablet.png
```

## 🎓 学習リソース

### チュートリアル
- **CLIP STUDIO TIPS**: https://tips.clip-studio.com/ja-jp
- **YouTube**: "hand drawing tutorial"で検索

### 参考資料
- 手のポーズ集
- 3Dモデル（VRoid等）
- 写真素材

## ⚠️ 注意事項

### 著作権
- 他人の作品を無断使用しない
- フリー素材でもライセンスを確認
- AI生成画像も規約を確認

### ファイルサイズ
- 大きすぎる画像（5MB以上）は避ける
- 必要に応じて圧縮
- 推奨: 1MB以下

### 画質
- 解像度は適度に（150dpi程度）
- 過度に高解像度にしない
- OBSで表示するサイズに最適化

## 📞 サポート

画像の作り方で困ったら：
- [IMAGE_GUIDE.md](../IMAGE_GUIDE.md) を参照
- [TROUBLESHOOTING.md](../TROUBLESHOOTING.md) を参照
- コミュニティで質問

---

**素敵な画像を作って、楽しいお絵かき配信を！🎨✨**

最終更新: 2024-12-05
