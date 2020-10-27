# 不明源
这里就是源文件了。
![不明](/Project/feature/u660E.logo.svg)

## stroke (to be…)
[中日韩笔划](https://unicode-table.com/cn/blocks/cjk-strokes/)`U+31C0-31EF`，基本只有一笔，这里用于拼字。

## radical (to be…)
[康熙字典部首](https://unicode-table.com/cn/blocks/kangxi-radicals/)`U+2F00-2FDF`、[中日韩部首补充](https://unicode-table.com/cn/blocks/cjk-radicals-supplement/)`U+2E80-2EFF`，这里用于拼字。

## glyph
一般单字，不含特效。
### 问题
Lunacy有概率会错误处理其生成的svg，尤其是涉及布尔运算的情况，因此我作了些处理回避布尔运算。

## feature
介绍一下[OpenType字体特性](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Fonts/OpenType_fonts_guide)标签——就是这些密码般的4字缩写。可以点击链接学习如果作为网页字体用的话怎样在CSS中调用特性。

字符命名用不到的标签：`kern`字偶距（kerning）、`vkrn`纵排字偶距（vertical kerning），这是设置特定两个字（字偶）之间间距用的，对单字无效。浏览器默认开启。

替换（alternates）
- `ss01`-`ss20`风格组合（stylistic set），用于字符命名，OpenType提供的风格变体可以在同一字体内为一个字符创建多达20种变体。浏览器默认关闭。
- `salt`变体替换默认字形（stylistic alternates）调用风格组合，字符命名一般用不到。
- `calt`上下文替换（contextual alternates）调用风格组合，字符命名不一定用到。浏览器默认开启。
- `nalt`注释形式替换（alternate annotation forms）把文字转换为符号的样式（例如🉑🈲这样把字放在空心或实心圆圈方块里），字符命名不一定用到。浏览器默认关闭。
- `vert`纵排替换（vertical alternates）有些字横排纵排不一样，尤其假名的ー转成竖。浏览器大概支持。
- `tnum`列表数字（tabular figures），出于列表对齐的要求数字必须等宽，也称等宽数字。本字体用于原作「閲覧 コメント」计数的情况。浏览器默认关闭。

`ccmp`字形组合/分解（Glyph Composition/Decomposition），像[Monu11](https://my1l.github.io/wwwoff)的'ccmp'特性会自动将 Shift+_ 打出的2个—合并为⸺。浏览器默认开启。这里也许会用上。

`mark`用于许多语言的附加符号，东亚这边是给假名加浊点。浏览器默认开启。

`liga`连字（ligatures）暂时还用不到，因为涉及多个字符不适用目前命名规则，或许用于「RUjimaku」作空心字符替换，但可能和'ccmp'重复，命名可以考虑`titl`标题大字替换（titling alternates）／`nalt`／自定义。浏览器默认开启。

不考虑特性的话，字符命名也可以自定义4字缩写，如“u660E.logo”，实质用的是'nalt'特性。

## .otlfd (to be…)
OpenType字体特性脚本（目前是示意）。纯文本，感兴趣可以直接打开看看。