# 繁體中文字型設定

Font configuration for my [Arch Linux](https://www.archlinux.org/) machine.

![Nautilus Screenshot](screenshot.png)

Screenshot of Nautilus: Sans-serif font Cantarell with Traditional Chinese font Source Han Sans TC Medium

## Font preferences

圖形介面的字型設定檔主要在 `fontconfig/fonts.conf` ， `fontconfig/conf.d/` 則放置其他設定。

[fonts.conf](fontconfig/fonts.conf) 中每種類型字型會有一個優先順序的清單，當第一順位的字型找不到對應的字時，就會去第二順位的字型找，以此類推。因此第一順位通常是英文字型，第二順位是中文字型。

以下字型皆為開放原始碼(Open Source)：

### Sans-serif (無襯線/黑體)

桌面介面主要字體：

1. **[Cantarell](https://github.com/GNOME/cantarell-fonts)**

  GNOME 預設字型。 

  Arch Linux Package: `cantarell-fonts`

2. **[Source Han Sans TC Medium (思源黑體)](https://github.com/adobe-fonts/source-han-sans)**

  由 Adobe 與 Google 開發的一套中文、日文、韓文(CJK)黑體字型，包含七種粗細(Weight)。
  
  TC 代表 Traditional Chinese ，選用中粗的 Medium 當作一般桌面介面的字型，搭配同樣較粗寬版的 Cantarell ，易於辨識。

  Arch Linux Package: `adobe-source-han-sans-tw-fonts`

### Serif (襯線/明體)

PDF、網頁中可能會出現：

1. **[Linux Libertine](http://www.linuxlibertine.org/)**

  Arch Linux Package: `ttf-linux-libertine`

2. **Source Han Sans TC Regular (思源黑體)**

  尚未找到優美適合的中文明體字型，先以較細的 Regular 思源黑體代替。

### Monospace (等寬)

終端機所使用：

1. **[Source Code Pro](https://github.com/adobe-fonts/source-code-pro)**

  同樣是 Adobe 開發的等寬字型，中性而優美，字母與數字易於辨認，適合長久閱讀，不易看錯。

  Arch Linux Package: `adobe-source-code-pro-fonts`

2. **Source Han Sans TC Medium (思源黑體)**

## How to use the configuration

Put folder `fontconfig` under `~/.config/` hidden directory.

Note that user fonts are put under `~/.fonts/` hidden directory.

## Reference

- [Arch Linux Wiki: Fonts](https://wiki.archlinux.org/index.php/fonts): Font packages to install.
- [Arch Linux Wiki: Font configuration](https://wiki.archlinux.org/index.php/Font_configuration): Font configuration explaination and troubleshooting.

## Environment

- Operating System: Arch Linux
- Desktop Environment: GNOME
- GTK+ Theme: Arc Dark
- Icon Theme: Elementary 
