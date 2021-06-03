---
marp: true
theme: default
title: 如何打造一个舒适的开发环境
description: 如何打造一个舒适的开发环境
paginate: true
_paginate: false
---

<!-- Global style -->
<style>
section {
  background-size: 100% 100%;
}

h1 {
  color: rgba(255,134,72,.96);
}

img[src*="#width-full"] {
 width: 80%;
 height: 80%;
}

</style>


程序员的基本素养-工具篇
==
数据服务组 程鹏飞

---
# 别人眼中的程序员？

- 妈妈：上班玩电脑的
- 阿姨：修电脑的
- 朋友：要么加班，要么摸鱼的
- 我：……

---
# 什么是程序员？

- 首先，你得会写代码
- 其次，一个可以充分利用网络资源，发挥自己特长，解决问题的人
---
# 工欲善其事 必先利其器

1. 科学上网
2. 如何给开发提速（前端）
3. 使用工具、高效学习
4. MacOS、Windows 工具推荐

---
# 1.科学上网-选择一个好的搜索引擎

- 浏览器，前端用谷歌，其他人随意
- 最佳选择， Google 搜索
- 你一定要学会科学上网(怎么做，请自行谷歌)
- 或者：[开发者版百度](https://kaifa.baidu.com/)

---
# 2.如何给开发提速（前端）

- 选择易用的终端：item2 + zsh + on-my-zsh + plugins [更多参考](https://github.com/Michaelooo/just_write/blob/master/draft/iterm2%E7%9A%84%E9%AA%9A%E6%93%8D%E4%BD%9C.md)
- 选择好用 vscode 的插件：如[tabNine](https://github.com/codota/tabnine-vscode)，更多请自行探索
- 解决问题的方法论：发现疑难问题 -> Google(学习分词技巧) -> github issue -> stackoverflow -> 专业论坛 -> 仍未解决，一起探讨
- **拥抱开源：不要觉得你天命不凡，你遇到的问题大部分是别人遇到过的**

---
# 3. 如何高效学习？
- 如何读书：浅阅读（博客周刊） + 深阅读（读书），软技能最好纸质书籍，技术类最好 PDF 看
- 高效阅读：过滤低质量读物，使用 RSS 订阅
- 记笔记: notion、语雀、有道云、为知笔记等，选择最喜欢的
- 待办：滴答清单、番茄周期等

---
# 4. MacOS、Windows 工具推荐（部分）
---
# 换电脑的痛苦，善用云备份
一定要注册的账号

- Google 账号
- [vscode setting sync](https://confluence.fangdd.cn/pages/viewpage.action?pageId=352853619)
- 拥有一个自己云服务账号吧

---
# 逃不了的安全隐私问题

- 密码管理：1Passwword、 使用自己 hash 的个人密码、 使用谷歌给你自动生成的密码（推荐）
- 软件安全： windows 要多注意防毒，涉及到修改注册表的要做注意
- 目录权限问题：建议系统学习(了解)一下 [Linux 文件系统机制](https://www.linuxprobe.com/linux-rights-control.html)
---

# Tampermonkey

- 下载地址：[Chrome 商店安装](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo) 需翻墙，或者离线安装
- 使用方法：https://zhuanlan.zhihu.com/p/34967781
- 推荐插件：手动翻页 ✋🏻

---
# Tampermonkey 推荐插件

![](https://oss-public.fangdd.com/prod/static/Fq11dRILgpsGu-SvJdAh4079n4C6.jpg)

更推荐大家主动去探索

---
# Alfred

- Alfred + 浏览器搜索:  快速搜索 npm、git、mdn 等文档
- Alfred + 书签搜索： 书签随便加
- Alfred + Dash: dash + keyword ，离线查文档
- Alfred + workflow: 翻译、查 IP 等

具体使用方式请参考[官网](https://www.alfredapp.com/)。
同时也有一个不错的替代工具:[uTools](https://u.tools/),很多常用的功能：host 修改，颜色转换，一键内网穿透等。


---
# 参考链接

- [macos 宝藏网站，你懂的 1](https://xclient.info/)
- [macos 宝藏网站，你懂的 2](https://www.macwk.com/)
- [工具整理](https://www.processon.com/view/link/60b8871e7d9c08051f655e57)
- [当我有了我的新电脑，我该怎么配置(多年前整理的，有些陈旧)](https://github.com/Michaelooo/just_write/blob/master/archived/%E5%BD%93%E6%88%91%E6%9C%89%E4%BA%86%E6%88%91%E7%9A%84%E6%96%B0%E7%94%B5%E8%84%91%EF%BC%8C%E6%88%91%E8%AF%A5%E6%80%8E%E6%A0%B7%E5%8E%BB%E9%85%8D%E7%BD%AE%EF%BC%9F.md)


---
<!-- Scoped style -->
<style scoped>
img {
  width: 100%;
  height: 80%;
  margin-top: 5%;
}
</style>

![](https://tva1.sinaimg.cn/large/9150e4e5ly1fnw96eu3g1g208c05uwek.gif)

