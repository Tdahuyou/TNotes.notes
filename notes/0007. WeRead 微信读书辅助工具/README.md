# [0007. WeRead 微信读书辅助工具](https://github.com/Tdahuyou/TNotes.notes/tree/main/notes/0007.%20WeRead%20%E5%BE%AE%E4%BF%A1%E8%AF%BB%E4%B9%A6%E8%BE%85%E5%8A%A9%E5%B7%A5%E5%85%B7)

<!-- region:toc -->

- [bilibili.TNotes.notes.0007.1](https://www.bilibili.com/video/BV1Ds4y1W7mq)、[bilibili.TNotes.notes.0007.2](https://www.bilibili.com/video/BV1sZ421p7fW)

- [1. ⏰ TODO - 发布一个 chrome 插件版，并优化代码结构，重新录制介绍视频，将早期的视频给下架掉。](#1--todo---发布一个-chrome-插件版并优化代码结构重新录制介绍视频将早期的视频给下架掉)
- [2. 📺 bilibili 在线视频链接 - 0007.1](#2--bilibili-在线视频链接---00071)
- [3. 📺 bilibili 在线视频链接 - 0007.2](#3--bilibili-在线视频链接---00072)
- [4. 🔗 Pack - tw93 大佬的 github 开源项目](#4--pack---tw93-大佬的-github-开源项目)
- [5. 🔗 桌面版 we-read 实现源码见笔记 👉 `TNotes.electron.0044`](#5--桌面版-we-read-实现源码见笔记--tnoteselectron0044)
- [6. 📒 脚本功能说明](#6--脚本功能说明)
- [7. 📒 测试设备（键盘）说明](#7--测试设备键盘说明)
- [8. 💻 微信读书脚本](#8--微信读书脚本)
- [9. 💻 使用 scripty 脚本注入插件来自动运行脚本](#9--使用-scripty-脚本注入插件来自动运行脚本)
- [10. 💻 微信读书桌面版的实现](#10--微信读书桌面版的实现)
  - [10.1. 解决 macos 安装报错问题](#101-解决-macos-安装报错问题)
  - [10.2. 记录开发微信读书桌面版时的桌面环境](#102-记录开发微信读书桌面版时的桌面环境)
- [11. 🤔 问：为什么要写微信读书桌面版？](#11--问为什么要写微信读书桌面版)
- [12. 🤔 问：微信读书脚本如何使用？](#12--问微信读书脚本如何使用)
- [13. 🤔 问：为什么想到要写这个脚本？](#13--问为什么想到要写这个脚本)

<!-- endregion:toc -->

- 本节内容概述：
  - WeRead 辅助脚本
  - scripty 脚本注入工具
  - 微信读书桌面版

## 1. ⏰ TODO - 发布一个 chrome 插件版，并优化代码结构，重新录制介绍视频，将早期的视频给下架掉。

## 2. 📺 bilibili 在线视频链接 - 0007.1

- https://www.bilibili.com/video/BV1Ds4y1W7mq
  - 微信读书 | 优化记录操作 の 工具分享「网页版」
  - 介绍了微信读书脚本的功能，以及如何使用脚本。

<BilibiliOutsidePlayer id="BV1Ds4y1W7mq" />

## 3. 📺 bilibili 在线视频链接 - 0007.2

- https://www.bilibili.com/video/BV1sZ421p7fW
  - 微信读书桌面版（网页套壳）
  - 内容概述：
    - 演示如何安装 macos 安装包
    - 演示脚本的功能
    - 其他一些不重要的信息 …… 个人写代码时的外界环境记录

<BilibiliOutsidePlayer id="BV1sZ421p7fW" />

## 4. 🔗 Pack - tw93 大佬的 github 开源项目

- https://github.com/tw93/Pake
  - 这是早期 `23-02-05` 视频中提到的微信读书桌面版下载地址，这个桌面应用程序是基于 pack 来实现的，其中一个很明显的特点是轻量（包体积很小）。

## 5. 🔗 桌面版 we-read 实现源码见笔记 👉 `TNotes.electron.0044`

- https://github.com/Tdahuyou/electron/tree/main
  - 微信读书桌面版的源码已上传到 github 上，这是对应 electron 笔记仓库的链接。

## 6. 📒 脚本功能说明

| **快捷键** | **功能说明** | **备注** |
| --- | --- | --- |
| `1` | 复制 | 在打开编写想法的弹窗时无效 |
| `2` | 马克笔 | 在打开编写想法的弹窗时无效 |
| `3` | 波浪线 | 在打开编写想法的弹窗时无效 |
| `4` | 直线 | 在打开编写想法的弹窗时无效 |
| `5` | 写想法 | 在打开编写想法的弹窗时无效 |
| `6` | 查询 | 在打开编写想法的弹窗时无效 |
| `esc` | 关闭编辑想法的弹窗 |  |
| `backspace` | 删除下划线、删除想法 | 在打开编写想法的弹窗时无效 |
| `ctrl + enter`、`cmd + enter` | 发表想法 |  |

## 7. 📒 测试设备（键盘）说明

- 目前使用的是 MX Keys Mini 键盘，这是一款非全尺寸键盘，键盘外观如下：
- ![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-12-13-15-59-20.png)
- 视频中介绍的所有操作，都是基于当前这个键盘来操作的，有些朋友使用的也许是全尺寸键盘，全尺寸键盘的按键会相对多一些，按侧边的这些数字键也是等效的。
- 下面这是全尺寸键盘，实际上在按下数字键的时候，按上边儿的数字和下边儿的数字效果都是一样的。
- ![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-12-13-16-00-08.png)

## 8. 💻 微信读书脚本

::: warning

- 视频中使用的插件是 Scripty，目前 `2025 年 4 月 1 日 22:51:59` 测试发现好像不好使了，改为用油猴插件来实现了，脚本的实现原理都是一样的，具体配置的做法基本差不多，只需要将脚本粘贴到油猴插件中即可。

:::

::: details 展开获取脚本源码

::: code-group

```javascript [Scripty 脚本]
console.log('weread script called')

document.onmouseup = () => {
  const toolbarContainer = document.querySelector('.reader_toolbar_container')

  if (!toolbarContainer) return // 未出现工具栏

  let copyBtn = document.querySelector('.toolbarItem.wr_copy'), // 复制按钮
    underlineBgBtn = document.querySelector('.toolbarItem.underlineBg'), // 马克笔按钮
    underlineHandWriteBtn = document.querySelector(
      '.toolbarItem.underlineHandWrite'
    ), // 波浪线按钮
    underlineStraightBtn = document.querySelector(
      '.toolbarItem.underlineStraight'
    ), // 直线按钮
    removeUnderlineBtn = document.querySelector('.toolbarItem.removeUnderline'), // 删除划线按钮
    reviewBtn = document.querySelector('.toolbarItem.review'), // 写想法按钮
    queryBtn = document.querySelector('.toolbarItem.query'), // 查询按钮
    submitIdeaBtn = document.querySelector(
      '.writeReview_submit_button.wr_btn.wr_btn_Big'
    ), // 发表想法按钮
    removeIdeaBtn = document.querySelector(
      '.readerReviewDetail_item .actions .actionItem'
    ), // 删除想法按钮
    closeIdeaBtn = document.querySelector(
      '.readerWriteReviewPanel .closeButton'
    ) // 关闭想法窗口按钮

  document.onkeydown = (e) => {
    const isCmdBtnPressed = e.metaKey, // 是否按下了 cmd 键
      isCtrlBtnPressed = e.ctrlKey // 是否按下了 ctrl 键

    const keyCode = e.keyCode

    console.log('keyCode: ', keyCode)

    if (keyCode === 49) {
      if (isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 1 复制')
      copyBtn && copyBtn.click()
    } else if (keyCode === 50) {
      if (isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 2 马克笔')
      underlineBgBtn && underlineBgBtn.click()
    } else if (keyCode === 51) {
      if (isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 3 波浪线')
      underlineHandWriteBtn && underlineHandWriteBtn.click()
    } else if (keyCode === 52) {
      if (isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 4 直线')
      underlineStraightBtn && underlineStraightBtn.click()
    } else if (keyCode === 53) {
      if (isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 5 写想法')
      reviewBtn && reviewBtn.click()
      e.preventDefault()
    } else if (keyCode === 54) {
      if (isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 6 查询')
      queryBtn && queryBtn.click()
    } else if (keyCode === 8) {
      if (isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 backspace 删除记录（包括想法的删除和下划线的删除）')
      // 删除按钮在鼠标抬起的那一刻，可能还没生成
      removeUnderlineBtn = document.querySelector(
        '.toolbarItem.removeUnderline'
      )
      removeUnderlineBtn && removeUnderlineBtn.click()

      removeIdeaBtn = document.querySelector(
        '.readerReviewDetail_item .actions .actionItem'
      )
      removeIdeaBtn && removeIdeaBtn.click()
    } else if (
      (isCmdBtnPressed && keyCode === 13) ||
      (isCtrlBtnPressed && keyCode === 13)
    ) {
      console.log('按下 cmd + enter | ctrl + enter 提交想法')
      submitIdeaBtn = document.querySelector(
        '.writeReview_submit_button.wr_btn.wr_btn_Big'
      )
      submitIdeaBtn && submitIdeaBtn.click()
    } else if (keyCode === 27) {
      if (!isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 esc 关闭想法记录窗口')
      closeIdeaBtn = document.querySelector(
        '.readerWriteReviewPanel .closeButton'
      ) // 关闭想法窗口按钮
      closeIdeaBtn.click()
    }
  }

  /* help info
  按下 cmd：e.metaKey === true 或 e.keyCode === 91
  按下 ctrl：e.ctrlKey === true 或 e.keyCode === 17
  按下 backspace：e.keyCode === 8
  按下 enter：e.keyCode === 13
  按下 esc：e.keyCode === 27
  按下 1：e.keyCode === 49
  按下 2：e.keyCode === 50
  按下 3：e.keyCode === 51
  按下 4：e.keyCode === 52
  按下 5：e.keyCode === 53
  按下 6：e.keyCode === 54
  */
}

/**
 * 记录想法的弹窗是否可见
 * @returns Boolean
 */
function isVisible_ReaderWriteReviewPanel() {
  const dom = document.querySelector('.readerWriteReviewPanel')
  if (!dom) return false
  return dom.style.display === 'none' ? false : true
}
```

```js [油猴脚本（推荐）]
// ==UserScript==
// @name         微信读书帮助脚本
// @namespace    http://tampermonkey.net/
// @version      2025-04-01
// @description  try to take over the world!
// @author       You
// @match        https://weread.qq.com/web/reader/*
// @icon         https://weread.qq.com/
// @grant        none
// ==/UserScript==

;(function () {
  'use strict'

  // Your code here...
  console.log('weread script called')

  document.onmouseup = () => {
    const toolbarContainer = document.querySelector('.reader_toolbar_container')

    if (!toolbarContainer) return // 未出现工具栏

    let copyBtn = document.querySelector('.toolbarItem.wr_copy'), // 复制按钮
      underlineBgBtn = document.querySelector('.toolbarItem.underlineBg'), // 马克笔按钮
      underlineHandWriteBtn = document.querySelector(
        '.toolbarItem.underlineHandWrite'
      ), // 波浪线按钮
      underlineStraightBtn = document.querySelector(
        '.toolbarItem.underlineStraight'
      ), // 直线按钮
      removeUnderlineBtn = document.querySelector(
        '.toolbarItem.removeUnderline'
      ), // 删除划线按钮
      reviewBtn = document.querySelector('.toolbarItem.review'), // 写想法按钮
      queryBtn = document.querySelector('.toolbarItem.query'), // 查询按钮
      submitIdeaBtn = document.querySelector(
        '.writeReview_submit_button.wr_btn.wr_btn_Big'
      ), // 发表想法按钮
      removeIdeaBtn = document.querySelector(
        '.readerReviewDetail_item .actions .actionItem'
      ), // 删除想法按钮
      closeIdeaBtn = document.querySelector(
        '.readerWriteReviewPanel .closeButton'
      ) // 关闭想法窗口按钮

    document.onkeydown = (e) => {
      const isCmdBtnPressed = e.metaKey, // 是否按下了 cmd 键
        isCtrlBtnPressed = e.ctrlKey // 是否按下了 ctrl 键

      const keyCode = e.keyCode

      console.log('keyCode: ', keyCode)

      if (keyCode === 49) {
        if (isVisible_ReaderWriteReviewPanel()) return
        console.log('按下 1 复制')
        copyBtn && copyBtn.click()
      } else if (keyCode === 50) {
        if (isVisible_ReaderWriteReviewPanel()) return
        console.log('按下 2 马克笔')
        underlineBgBtn && underlineBgBtn.click()
      } else if (keyCode === 51) {
        if (isVisible_ReaderWriteReviewPanel()) return
        console.log('按下 3 波浪线')
        underlineHandWriteBtn && underlineHandWriteBtn.click()
      } else if (keyCode === 52) {
        if (isVisible_ReaderWriteReviewPanel()) return
        console.log('按下 4 直线')
        underlineStraightBtn && underlineStraightBtn.click()
      } else if (keyCode === 53) {
        if (isVisible_ReaderWriteReviewPanel()) return
        console.log('按下 5 写想法')
        reviewBtn && reviewBtn.click()
        e.preventDefault()
      } else if (keyCode === 54) {
        if (isVisible_ReaderWriteReviewPanel()) return
        console.log('按下 6 查询')
        queryBtn && queryBtn.click()
      } else if (keyCode === 8) {
        if (isVisible_ReaderWriteReviewPanel()) return
        console.log('按下 backspace 删除记录（包括想法的删除和下划线的删除）')
        // 删除按钮在鼠标抬起的那一刻，可能还没生成
        removeUnderlineBtn = document.querySelector(
          '.toolbarItem.removeUnderline'
        )
        removeUnderlineBtn && removeUnderlineBtn.click()

        removeIdeaBtn = document.querySelector(
          '.readerReviewDetail_item .actions .actionItem'
        )
        removeIdeaBtn && removeIdeaBtn.click()
      } else if (
        (isCmdBtnPressed && keyCode === 13) ||
        (isCtrlBtnPressed && keyCode === 13)
      ) {
        console.log('按下 cmd + enter | ctrl + enter 提交想法')
        submitIdeaBtn = document.querySelector(
          '.writeReview_submit_button.wr_btn.wr_btn_Big'
        )
        submitIdeaBtn && submitIdeaBtn.click()
      } else if (keyCode === 27) {
        if (!isVisible_ReaderWriteReviewPanel()) return
        console.log('按下 esc 关闭想法记录窗口')
        closeIdeaBtn = document.querySelector(
          '.readerWriteReviewPanel .closeButton'
        ) // 关闭想法窗口按钮
        closeIdeaBtn.click()
      }
    }

    /* help info
  按下 cmd：e.metaKey === true 或 e.keyCode === 91
  按下 ctrl：e.ctrlKey === true 或 e.keyCode === 17
  按下 backspace：e.keyCode === 8
  按下 enter：e.keyCode === 13
  按下 esc：e.keyCode === 27
  按下 1：e.keyCode === 49
  按下 2：e.keyCode === 50
  按下 3：e.keyCode === 51
  按下 4：e.keyCode === 52
  按下 5：e.keyCode === 53
  按下 6：e.keyCode === 54
  */
  }

  /**
   * 记录想法的弹窗是否可见
   * @returns Boolean
   */
  function isVisible_ReaderWriteReviewPanel() {
    const dom = document.querySelector('.readerWriteReviewPanel')
    if (!dom) return false
    return dom.style.display === 'none' ? false : true
  }
})()
```

:::

## 9. 💻 使用 scripty 脚本注入插件来自动运行脚本

scripty 具体如何使用，可以参考 `TNotes.notes.0004` 笔记的介绍。

## 10. 💻 微信读书桌面版的实现

- **启动流程**
  1. `git clone https://github.com/Tdahuyou/electron.git` 克隆代码，编号切到 0044 目录
  2. `npm i` 安装依赖
  3. `npm run dev` 启动开发环境
  4. `npm run build` 出包
- **核心源码**

::: code-group

```javascript {12} [index.js]
const { app, BrowserWindow } = require('electron')
const { join } = require('path')

const createWindow = () => {
  const win = new BrowserWindow({
    width: 800,
    height: 600,

    webPreferences: {
      nodeIntegration: true,
      contextIsolation: false,
      preload: join(__dirname, 'preload.js'),
    },
  })

  win.loadURL('https://weread.qq.com/')
  // win.webContents.openDevTools()
}

app.whenReady().then(() => {
  createWindow()
})
```

```javascript [preload.js]
// 就是上面提到的微信读书脚本。
console.log('weread script called')

document.onmouseup = () => {
  const toolbarContainer = document.querySelector('.reader_toolbar_container')

  if (!toolbarContainer) return // 未出现工具栏

  let copyBtn = document.querySelector('.toolbarItem.wr_copy'), // 复制按钮
    underlineBgBtn = document.querySelector('.toolbarItem.underlineBg'), // 马克笔按钮
    underlineHandWriteBtn = document.querySelector(
      '.toolbarItem.underlineHandWrite'
    ), // 波浪线按钮
    underlineStraightBtn = document.querySelector(
      '.toolbarItem.underlineStraight'
    ), // 直线按钮
    removeUnderlineBtn = document.querySelector('.toolbarItem.removeUnderline'), // 删除划线按钮
    reviewBtn = document.querySelector('.toolbarItem.review'), // 写想法按钮
    queryBtn = document.querySelector('.toolbarItem.query'), // 查询按钮
    submitIdeaBtn = document.querySelector(
      '.writeReview_submit_button.wr_btn.wr_btn_Big'
    ), // 发表想法按钮
    removeIdeaBtn = document.querySelector(
      '.readerReviewDetail_item .actions .actionItem'
    ), // 删除想法按钮
    closeIdeaBtn = document.querySelector(
      '.readerWriteReviewPanel .closeButton'
    ) // 关闭想法窗口按钮

  document.onkeydown = (e) => {
    const isCmdBtnPressed = e.metaKey, // 是否按下了 cmd 键
      isCtrlBtnPressed = e.ctrlKey // 是否按下了 ctrl 键

    const keyCode = e.keyCode

    console.log('keyCode: ', keyCode)

    if (keyCode === 49) {
      if (isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 1 复制')
      copyBtn && copyBtn.click()
    } else if (keyCode === 50) {
      if (isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 2 马克笔')
      underlineBgBtn && underlineBgBtn.click()
    } else if (keyCode === 51) {
      if (isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 3 波浪线')
      underlineHandWriteBtn && underlineHandWriteBtn.click()
    } else if (keyCode === 52) {
      if (isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 4 直线')
      underlineStraightBtn && underlineStraightBtn.click()
    } else if (keyCode === 53) {
      if (isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 5 写想法')
      reviewBtn && reviewBtn.click()
      e.preventDefault()
    } else if (keyCode === 54) {
      if (isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 6 查询')
      queryBtn && queryBtn.click()
    } else if (keyCode === 8) {
      if (isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 backspace 删除记录（包括想法的删除和下划线的删除）')
      // 删除按钮在鼠标抬起的那一刻，可能还没生成
      removeUnderlineBtn = document.querySelector(
        '.toolbarItem.removeUnderline'
      )
      removeUnderlineBtn && removeUnderlineBtn.click()

      removeIdeaBtn = document.querySelector(
        '.readerReviewDetail_item .actions .actionItem'
      )
      removeIdeaBtn && removeIdeaBtn.click()
    } else if (
      (isCmdBtnPressed && keyCode === 13) ||
      (isCtrlBtnPressed && keyCode === 13)
    ) {
      console.log('按下 cmd + enter | ctrl + enter 提交想法')
      submitIdeaBtn = document.querySelector(
        '.writeReview_submit_button.wr_btn.wr_btn_Big'
      )
      submitIdeaBtn && submitIdeaBtn.click()
    } else if (keyCode === 27) {
      if (!isVisible_ReaderWriteReviewPanel()) return
      console.log('按下 esc 关闭想法记录窗口')
      closeIdeaBtn = document.querySelector(
        '.readerWriteReviewPanel .closeButton'
      ) // 关闭想法窗口按钮
      closeIdeaBtn.click()
    }
  }

  /* help info
  按下 cmd：e.metaKey === true 或 e.keyCode === 91
  按下 ctrl：e.ctrlKey === true 或 e.keyCode === 17
  按下 backspace：e.keyCode === 8
  按下 enter：e.keyCode === 13
  按下 esc：e.keyCode === 27
  按下 1：e.keyCode === 49
  按下 2：e.keyCode === 50
  按下 3：e.keyCode === 51
  按下 4：e.keyCode === 52
  按下 5：e.keyCode === 53
  按下 6：e.keyCode === 54
  */
}

/**
 * 记录想法的弹窗是否可见
 * @returns Boolean
 */
function isVisible_ReaderWriteReviewPanel() {
  const dom = document.querySelector('.readerWriteReviewPanel')
  if (!dom) return false
  return dom.style.display === 'none' ? false : true
}
```

:::

### 10.1. 解决 macos 安装报错问题

- macos 报错 - “weread-helper” 已损坏
  - ![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-12-13-16-21-33.png)
- 将 weread-helper 丢到应用程序 Applications 目录中
- 执行命令解决报错问题
  - `sudo xattr -rd com.apple.quarantine /Applications/weread-helper.app`
  - 通过执行这条命令，即可解决安装时的错误问题。

### 10.2. 记录开发微信读书桌面版时的桌面环境

- ![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-12-13-16-07-26.png)
- 右边是我家的 we，已经 1 岁了，巨社恐～
- 桌面番茄钟从 30 开始倒计时，写完出包时还剩 10min，比想象得快了好多……

## 11. 🤔 问：为什么要写微信读书桌面版？

- 其实现在 `2025 年 3 月 2 日 11:31:05` 想来没必要做这东西，当时写它的目的可能是考虑到有些网友在使用脚本的过程中遇到了些许麻烦，就想着想着通过一种方式将脚本集成到应用中，帮用户完成套壳。
- 以下是一些网友的在视频中的一些评论。

::: swiper

![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-12-13-16-12-58.png)

![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-12-13-16-13-41.png)

![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-12-13-16-14-34.png)

![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-12-13-16-14-45.png)

:::

## 12. 🤔 问：微信读书脚本如何使用？

- 这里记录的是一些历史问题，在 24.06.02 做了一个桌面版的工具，可以直接下载桌面版来使用，脚本已经注入到程序中了，只需要安装即可使用。
- 问题背景：

::: swiper

![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-12-13-16-17-50.png)

![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-12-13-16-17-58.png)

![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-12-13-16-18-05.png)

![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-12-13-16-18-23.png)

:::

- 图 4 大概率是因为快捷方式冲突导致的，这种情况可以尝试换一个环境再试试看。

## 13. 🤔 问：为什么想到要写这个脚本？

在使用网页版的微信读书时，很多时候想要发表想法时，会碍于操作成本太高而放弃记录 📝 的行为。心想，如果有对应的快捷键就好了，这样记录的话就会方便很多，便给官方提了建议。隔天觉得官方可能不会采纳亦或者压根就看不到这条建议，而自己又急着用，想着自己好像也能实现，于是就 ……

::: swiper

![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-12-13-15-45-18.png)

![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-12-13-15-45-35.png)

:::

问题描述：

在 [微信读书的网页端](https://weread.qq.com/) 读书时，遇到了一个问题 —— 记录成本太高，影响阅读节奏。（尤其是在竖屏的情况下浏览）
