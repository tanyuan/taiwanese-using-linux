# GNU/Linux 繁體中文字型設定 (Noto)

## 測試環境

* 作業系統：Arch Linux
* 桌面環境：GNOME

## 字型

Noto 是由 Adobe 與 Google 開發的一套中文、日文、韓文(CJK)黑體字型，包含七種粗細(Weight)。字體中包含：

* Noto Sans CJK TC: 黑體
* Noto Serif CJK TC: 明體

TC 代表 Traditional Chinese。

Arch Linux Package: `noto-fonts-cjk`

使用者的字型可用資料夾分類放到 `~/.fonts/`。

## 字型設定檔

字型設定檔位於 `~/.config/fontconfig/`。

圖形介面的字型設定檔主要在 `fonts.conf` ， `conf.d/` 則放置其他設定。

[fonts.conf](fontconfig/fonts.conf) 中每種類型字型會有一個優先順序的清單，當第一順位的字型找不到對應的字時，就會去第二順位的字型找，以此類推。因此第一順位通常是英文字型，第二順位是中文字型。

以下字型皆為開放原始碼(Open Source)：

### Sans-serif (無襯線/黑體)

桌面介面主要字體：

1. Cantarell

  GNOME 預設字型。

  Arch Linux Package: `cantarell-fonts`

2. Noto Sans CJK TC Medium

  選用中粗的 Medium 當作一般桌面介面的字型，搭配同樣較粗寬版的 Cantarell ，易於辨識。

### Serif (襯線/明體)

PDF、網頁中可能會出現：

1. Linux Libertine

  Arch Linux Package: `ttf-linux-libertine`

2. Noto Serif CJK TC

### Monospace (等寬)

終端機所使用：

1. Source Code Pro

  同樣是 Adobe 開發的等寬字型，中性而優美，字母與數字易於辨認，適合長久閱讀，不易看錯。

  Arch Linux Package: `adobe-source-code-pro-fonts`

2. Noto Sans CJK TC Medium

## 參考

- [Arch Linux Wiki: Fonts](https://wiki.archlinux.org/index.php/fonts): 可下載的字型目錄。
- [Arch Linux Wiki: Font configuration](https://wiki.archlinux.org/index.php/Font_configuration): 字型設定與疑難排解。
