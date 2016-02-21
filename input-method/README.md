# GNU/Linux 中文輸入法

輸入法需要有「輸入法框架」、以及框架底下的「輸入法本身」，才能夠正常輸入。以下以輸入法框架 **fcitx** 、與輸入法本身**新酷音(chewing)**、**中州韻(rime)**為例。

## 測試環境

* 作業系統：Arch Linux
* 桌面環境：GNOME

## 輸入法框架 fcitx

若是其他桌面環境，或更多資訊請見 [Fcitx - ArchWiki](https://wiki.archlinux.org/index.php/Fcitx)。

### 安裝 fcitx

1. GNOME 環境下「必須」先移除預設的輸入法框架 `ibus` ，再裝 `fcitx` 才有用。

    移除 `ibus`：

        sudo pacman -Rs ibus

    安裝 `fcitx` 本身，以及其支援不同圖形介面程式的 `fcitx-im` 與圖形介面的設定工具 `fcitx-configtool`:

        sudo pacman -S fcitx fcitx-im fcitx-configtool

2. GNOME 的設定程式還是會擋掉其他輸入法框架，因此要設定以下：

        gsettings set org.gnome.settings-daemon.plugins.keyboard active false

3. 在 GNOME 上方的工具列顯示輸入法狀態與選單，安裝擴充套件 [Input Method Panel - GNOME Shell Extensions](https://extensions.gnome.org/extension/261/kimpanel/) 。

其他桌面環境可能需新增設定至 `~/.xinitrc` ：

```
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS=@im=fcitx
```

### 設定 fcitx

* 我將PC鍵盤空白鍵旁的「右鍵選單」設定成切換輸入法，非常方便。
* Global Config > Show Advance Option > Appearance > Do not show input window if there is only preedit string

## 新酷音輸入法 chewing

### 安裝

    sudo pacman -S fcitx-chewing

### 設定

若想問換掉 GNOME 工具列圖示，例如[我用的](icons/fcitx-chewing.png)，取代以下檔案：

```
/usr/share/icons/hicolor/48x48/apps/fcitx-chewing.png
```

## 中州韻輸入法 rime

此輸入法引擎包含多種輸入法，使用說明請見官方網站[中州韻輸入法引擎](http://rime.im/)。

中州韻其中注音輸入法的特色是類似觸控輸入法，在尚未輸入完完整的注音符號，即會提示候選字詞。此為快速，但需要費眼力的輸入法。

### 安裝

    sudo pacman -S fcitx-rime

### 設定

設定檔位於：

```
~/.config/fcitx/rime/default.custom.yaml
```

若想要替換 GNOME 工具列圖示，例如[我用的](icons/fcitx-rime.svg)，取代以下檔案：

```
/usr/share/icons/hicolor/scalable/status/fcitx-rime.svg
```

如果輸入法顯示的不是台灣的繁體中文，請替換成以下設定（以注音輸入法為例）：

```
patch:
  schema_list:
    - schema: bopomofo
  ascii_composer/good_old_caps_lock: true
  ascii_composer/switch_key:
    Caps_Lock: noop
    Shift_L: noop
    Shift_R: inline_ascii
    Control_L: noop
    Control_R: noop
  "key_binder/bindings":
    - { when: paging, accept: bracketleft, send: Page_Up }
    - { when: has_menu, accept: bracketright, send: Page_Down }
```
