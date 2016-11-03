# emacs-chinese-font

emacs上默认的中文字体设置有误，导致显示中文时特别卡，推荐用`文泉驿等宽中文字体`

```
 ;;中文与外文字体设置
 (defun set-font (english chinese english-size chinese-size)
   (set-face-attribute 'default nil :font
                       (format   "%s:pixelsize=%d"  english english-size))
   (dolist (charset '(kana han symbol cjk-misc bopomofo))
     (set-fontset-font (frame-parameter nil 'font) charset
                       (font-spec :family chinese :size chinese-size))))

 (set-font   "WenQuanYi Micro Hei Mono" "WenQuanYi Micro Hei Mono Light" 14 14)
 ```
