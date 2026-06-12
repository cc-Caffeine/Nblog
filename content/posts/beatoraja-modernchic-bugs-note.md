---
date: '2026-06-13T00:16:21+08:00'
draft: false
title: 'Beatoraja Modernchic 在linux下的运行小指南'
description: "分析 Beatoraja 在 Linux 环境中的启动环境准备"
---

[beatoraja-modernchic 官方仓库](https://mocha-repository.info/download.php)
[信息来源](https://github.com/wcko87/beatoraja-english-guide/wiki#setting-up-beatoraja-with-java)

---

# 过程

选择下载 `beatoraja-0.8.8-modernchic` 后, 会发现 `beatoraja-config.command` 一般无法直接正常运行, Java FX 会报错, 此时需要装一个 `Liberica OpenJDK` , 在arch linux中可以直接从AUR中获取:

```yay -S liberica-jdk-full-bin```

然后通过

```sudo archlinux-java set liberica-jdk-full```

来改变环境. 将终端重启, 改变一下默认的JAVA启动参数, 增加一个 `-Dfile.encoding="UTF-8"`, 最终也就是:

```export _JAVA_OPTIONS='-Dsun.java2d.opengl=true -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true -Dswing.defaultlaf=com.sun.java.swing.plaf.gtk.GTKLookAndFeel -Dfile.encoding="UTF-8"'```

来支持UTF-8的编码. 接下来就可以愉快启动游戏了~

---

# 后续

这边还碰到过因为 xremap 导致使用虚拟设备进行游戏时直接卡死的问题, 所以要么得把 xremap 给杀了要么就再接一个键盘设备... 好麻烦, bug真多.

