编译方法
===============

准备目标结构
--------
将vboot代码放置在coreboot/3rdparty/vboot, depthcharge解压后放在coreboot/payloads/external/depthcharge。

配置config文件
--------
**make nconfig**  
配置配置项，按F6保存配置后将在coreboot目录下生成.config文件。

编译交叉编译器
--------
**make crossgcc-arm**  
将会编译arm的交叉编译器，如果直接make crossgcc会编译各个平台的编译器时间太长。

编译rom文件
--------
**make -j16**  
编译完成后将在coreboot/build目录下生成coreboot.rom文件。这个文件即可使用flashrom工具输入设备的flash中。
刷flash方式参考《更新BIOS.MD》。
