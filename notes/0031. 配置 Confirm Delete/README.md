# [0031. 配置 Confirm Delete](https://github.com/Tdahuyou/TNotes.notes/tree/main/notes/0031.%20%E9%85%8D%E7%BD%AE%20Confirm%20Delete)

<!-- region:toc -->
- [1. 📒 配置 Confirm Delete](#1--配置-confirm-delete)
<!-- endregion:toc -->
- 需要知道删除文件时弹出的确认提示框如何配置是否开启。

## 1. 📒 配置 Confirm Delete

- 在 vsocde 中删除文件，默认会弹出确认提示框，若有在 vsocde 中频繁删除文件的需求，可能会勾选【不再询问】，若勾选了，那么接下来每次删除内容的时候，就不会再弹出提示框了。
  - ![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-10-27-22-31-09.png)
  - 勾选上【不再询问】之后，如果是 macOS 系统，你只需要按下键盘上的 Del 键即可删除文件或者目录。在有频繁需要删除的内容的情况下，这可能确实提供了便利。但频繁删除文件可能仅仅是你某一时段的需求，后续也许就不再需要了，到时候不小心按下 Del 键的话，就会导致内容被误删了。
    - 虽然大多数时候可以通过 cmd z 撤销删除，找回文件，但有些时候是没法恢复的。
      - 有些时候当你意识到误删了，可能已经不知道应该撤销到之前的第几步了。
      - 编辑器重开，会导致撤销操作失效。
    - 这里写这么多，主要是个人在使用时遇到的问题，不小心删了比较重要的内容，找回的过程很费精力，还不如一开始就不关闭这个确认提示框嘞。
- 问题：如果还想恢复确认提示的话，应该怎么做？
  - 这东西是可以支持配置的，打开【设置】，搜索 delete，找到 Confirm Delete 选项，勾选上确认提示框即可。
  - ![](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-10-27-22-31-12.png)
