# 静态分析

此处主要介绍安卓的逆向破解中的静态分析：

* 安卓的逆向破解 静态分析
  * 按文件格式类型分
    * 针对`apk`
      * 查看apk信息
        * `aapt`
      * 解包工具：输出`dex`、`so`、`smali`
        * `apktool`
      * 反编译工具
        * 直接apk转java
          * `jadx`
          * `JEB`
          * `GDA`
    * 针对`dex`
      * 各种导出dex的工具=砸壳工具=脱壳工具
        * `FDex2`
        * `DumpDex`
        * `DexExtractor`
      * 各种反编译dex的工具
        * dex转jar
          * `dex2jar`
        * dex转smali
          * `baksmali`
        * dex直接转java
          * `jadx`
          * `GDA`
    * 针对`jar`
      * jar转java=各种反编译工具
        * `Procyon`
        * `CFR`
        * `JD-GUI`
    * 针对`so`库文件=（往往是ARM64架构）的ELF文件
      * 导出静态资源
        * `readelf`
        * `objdump`
        * `razbin2`
      * 反编译代码逻辑
        * `IDA`
        * `Hopper`
        * `Radare2`
        * `Ghidra`
  * 涉及子领域
    * 反代码混淆

详见独立子教程：

[Android逆向：静态分析](https://book.crifan.org/books/android_re_static_analysis/website/)
