# 动态调试

此处主要介绍安卓逆向破解中的动态调试：

* 安卓的逆向破解 动态调试
  * （绕过限制去）抓包
    * 绕过证书绑定的Exposed插件或Frida的脚本
  * 反root检测
  * 反反调试
  * 各种动态调试手段
    * 调试smali：`AS+smalidea插件`
      * app进程可调试
        * Magisk插件：`MagiskHide Props Config`
    * 调试Frida：`Frida`
      * Frida环境搭建
        * Magisk插件：`MagiskFrida`
    * 调试lldb：`LLDB`
    * 调试Xposed插件
      * [XPosed](https://book.crifan.org/books/android_re_xposed_framework/website/)
        * [EdXposed](https://book.crifan.org/books/android_re_xposed_framework/website/install_xposed/edxposed_manager/)
        * [LSPosed](https://book.crifan.org/books/android_re_xposed_framework/website/install_xposed/lsposed/)
    * 模拟代码执行
      * `Unidbg`
        * `Unicorn`
    * 辅助调试工具
      * `adb`
      * `DDMS`

详见独立子教程：

[Android逆向：动态调试](https://book.crifan.org/books/android_re_dynamic_debug/website/)
