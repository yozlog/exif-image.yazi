[English](README.md) | [繁體中文](README.zh-TW.md) | [한국어](README.ko.md)

# exif-image.yazi

이미지에 대한 듀얼 패인 미리보기를 제공하는 [Yazi](https://github.com/sxyazi/yazi) 플러그인으로, 고화질 네이티브 이미지 렌더링과 이미지 메타데이터 목록을 결합합니다.

![미리보기](preview.png)

## 요구 사항 및 의존성

- [`exiftool`](https://github.com/exiftool/exiftool): 이미지 메타데이터 추출에 필요합니다.

### macOS

Homebrew를 통해 설치할 수 있습니다:

```bash
brew install exiftool
```

## 설치 방법

### [`ya pkg` 패키지 매니저](https://yazi-rs.github.io/docs/cli/#pm)를 사용하여 설치 (권장)

```bash
ya pkg add yozlog/exif-image
```

### 수動 설치

`git`을 사용하여 클론:

```bash
git clone https://github.com/yozlog/exif-image.yazi.git ~/.config/yazi/plugins/exif-image.yazi
```

## 구성 설정

`yazi.toml`에 미리보기 설정을 추가합니다:

```toml
[plugin]
prepend_previewers = [
  { mime = "image/*", run = "exif-image" }
]
```

## 단축키

`keymap.toml`에 단축키를 설정합니다:

```toml
[[mgr.prepend_keymap]]
on   = [ "<C-j>" ]
run  = "plugin exif-image 1"
desc = "메타데이터 다음 페이지"

[[mgr.prepend_keymap]]
on   = [ "<C-k>" ]
run  = "plugin exif-image -1"
desc = "메타데이터 이전 페이지"
```

## 사용법

이미지 파일 위에 커서를 올리면 미리보기 창이 자동으로 분할되어 상단에는 이미지가, 하단에는 메타데이터가 표시됩니다. 설정된 `Ctrl-j`와 `Ctrl-k` 키를 사용하여 메타데이터 페이지를 스크롤할 수 있습니다.
