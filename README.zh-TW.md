[English](README.md) | [繁體中文](README.zh-TW.md) | [한국어](README.ko.md)

# exif-image.yazi

為圖片提供雙欄位預覽的 [Yazi](https://github.com/sxyazi/yazi) 插件，結合了高品質的原生圖片渲染與圖片元數據列表。

![畫面預覽](preview.png)

## 需求與依賴

- [`exiftool`](https://github.com/exiftool/exiftool)：用於提取圖片元數據。

### macOS

可透過 Homebrew 安裝：

```bash
brew install exiftool
```

## 安裝

### 使用 [`ya pkg` 套件管理器](https://yazi-rs.github.io/docs/cli/#pm) (推薦)

```bash
ya pkg add yozlog/exif-image
```

### 手動安裝

使用 `git` 拉取：

```bash
git clone https://github.com/yozlog/exif-image.yazi.git ~/.config/yazi/plugins/exif-image.yazi
```

## 配置設定

在 `yazi.toml` 中加入預覽器：

```toml
[plugin]
prepend_previewers = [
  { mime = "image/*", run = "exif-image" }
]
```

## 快捷鍵

在 `keymap.toml` 中配置快捷鍵：
   
```toml
[[mgr.prepend_keymap]]
on   = [ "<C-j>" ]
run  = "plugin exif-image 1"
desc = "元數據 下一頁"

[[mgr.prepend_keymap]]
on   = [ "<C-k>" ]
run  = "plugin exif-image -1"
desc = "元數據 上一頁"
```

## 使用方法

當游標移動到圖片檔案時，預覽窗格會自動分割，上方顯示圖片，下方顯示元數據。使用配置的 `Ctrl-j` 和 `Ctrl-k` 鍵捲動元數據頁面。
