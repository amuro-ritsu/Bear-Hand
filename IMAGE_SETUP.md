# 画像ファイルの配置方法

## 📁 必要なファイル

このHTMLファイルと**同じフォルダ**に以下の画像ファイルを配置してください：

```
DrawingHandAnimator_Browser_v1.0/
├── drawing_hand_animator.html  ← このHTMLファイル
├── hand.png                     ← 手+ペンの画像（透過PNG）
└── tablet.png                   ← タブレットの画像（透過PNG）
```

## 🎨 画像の準備

### hand.png（手+ペンの画像）
- **形式**: PNG（透過推奨）
- **推奨サイズ**: 300×400px〜500×600px
- **内容**: ペンを持った手

### tablet.png（タブレット画像）
- **形式**: PNG（透過推奨）
- **推奨サイズ**: 400×300px〜600×400px
- **内容**: タブレットを真上から見た図

## 🚀 使い方

### 1. 基本的な使い方

1. `hand.png` と `tablet.png` を用意
2. このHTMLと同じフォルダに配置
3. OBSのブラウザソースでHTMLを指定
4. 自動的に画像が読み込まれます！

### 2. 複数パターンを使う場合

異なる画像セットを複数用意する場合：

#### ファイル構成例
```
DrawingHandAnimator_Browser_v1.0/
├── drawing_hand_animator.html
├── hand.png              ← デフォルト
├── tablet.png            ← デフォルト
├── hand_anime.png        ← アニメ調
├── tablet_anime.png      ← アニメ調
├── hand_real.png         ← リアル系
└── tablet_real.png       ← リアル系
```

#### OBSでの設定

**シーン1: デフォルト**
```
ローカルファイル: drawing_hand_animator.html
（URLパラメータなし = hand.png, tablet.png を使用）
```

**シーン2: アニメ調**
```
ローカルファイル: drawing_hand_animator.html
                 ?hand=hand_anime.png&tablet=tablet_anime.png
```

**シーン3: リアル系**
```
ローカルファイル: drawing_hand_animator.html
                 ?hand=hand_real.png&tablet=tablet_real.png
```

### 3. URLパラメータの指定方法

OBSのブラウザソースで：

```
ローカルファイル: 
C:\OBS\DrawingHandAnimator\drawing_hand_animator.html?hand=hand_anime.png&tablet=tablet_anime.png
```

このように、ファイルパスの後ろに `?` を付けてパラメータを指定します。

## 📝 プリセット機能

設定を複数パターン保存したい場合は `preset` パラメータを使用：

```
?preset=anime&hand=hand_anime.png&tablet=tablet_anime.png
```

これで、`anime` という名前で設定が個別に保存されます。

### プリセット例

#### アニメ調配信用
```
?preset=anime&hand=hand_anime.png&tablet=tablet_anime.png
```

#### リアル系配信用
```
?preset=real&hand=hand_real.png&tablet=tablet_real.png
```

#### お絵描き講座用
```
?preset=tutorial&hand=hand_simple.png&tablet=tablet_simple.png
```

各プリセットで設定（感度、角度など）を個別に保存できます。

## 🖼️ 画像の作り方

詳しくは [IMAGE_GUIDE.md](IMAGE_GUIDE.md) を参照してください。

### 簡単な手順

1. **CLIP STUDIO PAINT** や **Photoshop** などで新規キャンバス作成
2. 透過背景で手とペンを描く
3. PNG形式でエクスポート
4. ファイル名を `hand.png` に変更
5. HTMLと同じフォルダに配置

## ⚠️ 重要な注意点

### OBSでは相対パスの画像しか使えません

❌ **これはできません：**
- 設定パネルから画像をアップロード
- ブラウザで開いて設定を変更

✅ **これができます：**
- HTMLと同じフォルダに画像ファイルを配置
- URLパラメータで画像を指定
- LocalStorageに設定を保存（プリセット機能）

### なぜアップロード機能が使えないのか

OBSのブラウザソースは独立したブラウザインスタンスです。
通常のブラウザで開いた画面とは完全に別物なので、
アップロードした画像はOBSには反映されません。

## 🔧 トラブルシューティング

### 画像が表示されない

#### 原因1: ファイル名が間違っている
```
✅ 正: hand.png
❌ 誤: Hand.png（大文字小文字を区別）
❌ 誤: hand.PNG（拡張子も区別）
```

#### 原因2: ファイルの場所が違う
```
✅ 正: drawing_hand_animator.html と同じフォルダ
❌ 誤: サブフォルダや別の場所
```

#### 原因3: 画像形式が対応していない
```
✅ 正: PNG, WEBP, JPG
❌ 誤: PSD, AI, SVG（非対応）
```

### 設定が保存されない

#### 原因: プリセット名が違う
```
各URLパラメータのpresetごとに設定が別々に保存されます。
presetを指定していない場合は共通の設定になります。
```

### 複数シーンで画像が混ざる

#### 解決策: プリセットを使う
```
各シーンで異なる preset パラメータを指定してください。

シーン1: ?preset=scene1
シーン2: ?preset=scene2
```

## 💡 よくある質問

### Q1. 画像は何度でも変更できますか？
A. はい。ファイルを上書きするだけで反映されます。OBSのブラウザソースを「更新」すれば読み込まれます。

### Q2. 画像のサイズは自由ですか？
A. はい。ただし、大きすぎる画像（5MB以上）はパフォーマンスに影響する可能性があります。

### Q3. JPG形式でも使えますか？
A. 使えますが、背景を透過したい場合はPNG形式を推奨します。

### Q4. 別のフォルダに画像を置けますか？
A. URLパラメータで相対パスを指定すれば可能です：
```
?hand=images/hand.png&tablet=images/tablet.png
```

### Q5. 絶対パスは使えますか？
A. セキュリティ上の理由で推奨しません。相対パスを使用してください。

## 📚 関連ドキュメント

- [README.md](README.md) - 詳細マニュアル
- [QUICKSTART.md](QUICKSTART.md) - クイックスタート
- [IMAGE_GUIDE.md](IMAGE_GUIDE.md) - 画像制作ガイド
- [TROUBLESHOOTING.md](TROUBLESHOOTING.md) - トラブルシューティング

---

**画像を配置したらお絵かき配信を始めましょう！🎨✨**

最終更新: 2024-12-05
