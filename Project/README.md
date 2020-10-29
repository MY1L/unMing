# 不明源
这里就是源文件了。
![不明](/Project/feature/u660E.logo.svg)

## 示例字体
可在[Releases](https://github.com/MY1L/unMing/releases)下载。目前没有实用价值，仅供演示OpenType字体特性（OT特性），包含字符不完全列举如下：

不明体朝ほのぼの神社遊園イ本地BlanKFairyGMhＢＶＷ0012478[]编編集［〔゙゚゛゜］〕〇百クッキー☆タグカウボーイビバップキャラクタ年月 ネット上のとぁる界隈でバッハシャユンヌアニメーション・—⸺⸻¹ºª°⁰
⺅⻎⺝⼀⼞⼌⼣⽉㇐
 ~~中国智造，慧及全球~~

- 上文重复的字符表示有变体。
- ~~因为不希望视窗预览缺字就搞了非常应付的八个字。看起来挺搞笑。~~
- 缺失大量英文用[Monu](https://my1l.github.io/wwwoff)和不区分大小写来补足。
- OT特性用的字符有意暴露于私用区，这里不列举了。你可以用我推荐的[NexusFont](https://github.com/MY1L/Chinese)打开字体查看私用区内容。

## glyph
默认单字字形.svg
### 问题
发现Lunacy旧版可能会错误处理其自己生成的svg，尤其涉及布尔运算（如：打孔）的情况，因此我只好作如此处理回避布尔运算：凡打孔一概改为填白。

## radical (to be…)
包含[中日韩部首补充](https://unicode-table.com/cn/blocks/cjk-radicals-supplement/)`U+2E80-2EFF`（示例字体含`⺅⻎⺝`）、[康熙字典部首](https://unicode-table.com/cn/blocks/kangxi-radicals/)`U+2F00-2FDF`（示例字体含`⼀⼞⼌⼣⽉`），这里用作拼字零件。

## stroke (to be…)
包含[中日韩笔画](https://unicode-table.com/cn/blocks/cjk-strokes/)`U+31C0-31EF`，基本只有一笔（示例字体含`㇐`），这里用作拼字零件。

**部首和笔画区域内的字符并不用于正文只是拼字零件，因此没有也不需变体特性，.ss后缀只是一时没想到命名的默认，`-`之后的文字为注释兼作区分。**

## .otlfd
演示用OT特性脚本。纯文本，感兴趣可以直接在这网页打开看看。

## feature
### 字形命名
命名规则：用`.`标注字形涉及的OT特性标签。由于文件名不能用冒号，以键盘`-`号表示后方为注释。典型的有：

- -radc：radical，部首补充
- -kgxi：kangxi，康熙部首
- -stok：stroke，笔画
- -kana：katakana—hiragana，假名；-s-，小型假名
- -comb：附在其它符号上的符号，比如゚U+309A katakana.hiragana.semi-voiced.sound.mark.combining，略作u309A-si-vm-comb
- -L：left，大写，左
- -R：right，大写，右
- -w-：white，空心（统一码别致的命名法，同理-b-(black)是实心）
- -i-：ideographic，东亚符号，兼作fullwidth全角符号。本字体不等宽无所谓全角了，只是空隙宽些。

`+`号表示该图形被用于多个符号，命名将多个符号列举出。
### 特性标签
既然看过脚本了，那么介绍一下[OT特性标签](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Fonts/OpenType_fonts_guide)——就是这些4字缩写。可以点击链接学习如果作为网页字体用的话怎样在CSS中调用特性。

![unMing/preview.png](/preview.png)

字符命名用不到的标签：`kern`字偶距（Kerning）、`vkrn`纵排字偶距（Vertical Kerning），这是设置特定两个字（字偶）之间间距用的，当然对单字无效。
'kern'浏览器默认开启，'vkrn'不清楚。

替换（alternates）
- `ss01`-`ss20`风格组合（Stylistic Set 1~20），用于字符命名，OpenType提供的风格变体可以在同一字体内为一个字符创建多达20种变体。浏览器默认关闭。
- `calt`上下文替换（Contextual Alternates）按上下文调用风格组合，字符命名不一定用到。浏览器默认开启。
- `nalt`注释形式替换（Alternate Annotation Forms）把文字转换为符号的样式（例如🉑🈲这样把字放在空心或实心圆圈方块里），字符命名不一定用到。浏览器默认关闭。
- `vert`纵排替换（Vertical Alternates）有些字横排纵排不一样，尤其假名的ー转成竖。浏览器大概支持。
- `rand`随机（Randomize）伪随机替换字符以模拟手写。浏览器大概不支持，我加这个应付专业排版软件。大多数设计师推荐用'calt'代替。
- `sups`上标（Superscript）。相对的，`subs`下标（Subscript）。浏览器默认关闭。
- `tnum`列表数字（Tabular Figures），出于列表对齐的要求数字必须等宽，也称等宽数字。本字体用于原作「閲覧 コメント」计数的情况。浏览器默认关闭。**目前示例字体不含。**

`ccmp`字形组合/分解（Glyph Composition/Decomposition），像[Monu11](https://my1l.github.io/wwwoff)的'ccmp'特性会自动将 Shift+_ 打出的2个—合并为⸺。浏览器默认开启。
本示例字体也可以，理论上会伸展无限长……

`mark`用于许多语言的附加符号，东亚这边是给假名加浊点，但思源是用'ccmp'达成的。浏览器默认开启。

`liga`连字（ligatures）暂时还用不到，因为涉及多个字符**目前示例字体不含**，或许用于「RUjimaku」作空心字符替换，但可能和'ccmp'重复，命名可以考虑`titl`标题大字替换（titling alternates）／`nalt`／自定义。浏览器默认开启。

不考虑特性的话，字符命名也可以自定义4字缩写，如“u660E.logo”，实质用的是'nalt'特性。