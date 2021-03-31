# 不明源
这里就是源文件了。
![不明](/Project/feature/u660E.logo.svg)

## 示例字体.otf
可在[Releases](https://github.com/MY1L/unMing/releases)下载。目前没有实用价值，仅供演示OpenType字体特性（OT特性），包含字符不完全列举如下：

不明朝体BlanKFairyGMhＢＶＷ0012478[]［〔 ゙ ゚゛゜］〕〇编編集ほのぼの神社遊園地百本クッキー☆タグカウボーイビバップキャラクタ年月ネット上のとぁる界隈でバッハシャユンヌアニメーション・—⸺⸻¹ºª°⁰ ⃠
⺅⻎⺝⼀⼞⼌⼣⽉㇐
 ~~中国智造，慧及全球~~

- 上文重复的字符表示有变体。
- ~~因为不希望视窗预览缺字就搞了非常应付的八个字。看起来挺搞笑。~~
- 缺失大量英文用[Monu](https://my1l.github.io/wwwoff)和不区分大小写来补足。
- OT特性用的字符有意暴露于私用区，这里不列举了。你可以用我推荐的[NexusFont](https://github.com/MY1L/Chinese)打开字体查看私用区内容。

### 更新 (2021-3-31)
添加字符：J(+j+Ｊ)、o、淫、語(+语)、百.ss01、連(+连)、発(+发+發)
- - `(+某)`的意思是这几个互为繁简关系的字，随便打哪个输出的都是同一括号外的字形。

添加特性：
- ss01/字形变体01：百
- calt/上下文替换：淫語_百連発
- - 注：插一个“_”是避免打“淫語百連発”时自动连字。注意这个连字呈现效果为“淫語[换行]百連発”

## glyph
默认单字字形.svg
### 问题
发现Lunacy旧版可能会错误处理其自己生成的svg，尤其涉及布尔运算（如：打孔）的情况，一段时间我只好作如此处理回避布尔运算：凡打孔一概改为填白。但最近遇到些不涉及布尔运算也会出错的情况，我在考虑是否另发布.sketch源文件。

有些特小、特矮或特窄的字形是留着准备当作偏旁用的（都是不明原笔迹，如有意见可以试着找他本人……），将来如有更好的字形会调到变体不作默认的。

## radical
包含[中日韩部首补充](https://unicode-table.com/cn/blocks/cjk-radicals-supplement/)`U+2E80-2EFF`（示例字体含`⺅⻎⺝`）、[康熙字典部首](https://unicode-table.com/cn/blocks/kangxi-radicals/)`U+2F00-2FDF`（示例字体含`⼀⼞⼌⼣⽉`），这里用作拼字零件。但排除与笔画重复的一笔字，清单详见[unMing/Project/radical](https://github.com/MY1L/unMing/tree/master/Project/radical)。

## stroke (to be…)
包含[中日韩笔画](https://unicode-table.com/cn/blocks/cjk-strokes/)`U+31C0-31EF`，基本只有一笔（示例字体含`㇐`），这里用作拼字零件。

**注意**，部首和笔画区域内的字符并不用于正文只是拼字零件，因此没有也不需变体特性，`.`之后的文字为注释兼作区分，变体如一时没想到准确命名可默认用.`cv01`-`cv99`（[Character Variant 1~99](https://docs.microsoft.com/zh-cn/typography/opentype/spec/features_ae#tag-cv01--cv99)）作后缀，方便起见，仅部首和笔画命名用字符自身，例如横折折撇的窄版之二十一：`㇋.cond.cv21.svg`。如果有些偏旁或笔画不属于 部首补充、康熙部首、中日韩笔画 任意一个，请到[Issues](https://github.com/MY1L/unMing/issues)商议，我是打算新开个'character'文件夹放那些能单独成字的笔画偏旁。

## .otlfd
演示用OT特性脚本。纯文本，感兴趣可以直接在这网页打开看看。

## feature
有特效的字形.svg
### 字形命名
命名规则：用`.`标注字形涉及的OT特性标签。由于文件名不能用冒号，以键盘`_`号表示后方为注释。典型的有：

- `_radi`：radical，部首补充
- `_kgxi`：kangxi，康熙部首
- `_strk`：stroke，笔画
- `_kana`：katakana（カタカナ）片仮名，`_hira`：hiragana（ひらがな）平仮名，`_s_`：小型假名；此处缩写遵循[ISO 15924](https://www.unicode.org/iso15924/iso15924-codes.html)
- `_comb`：附在其它符号上的符号，比如゚U+309A katakana.hiragana.semi-voiced.sound.mark.combining，略作u309A_si_vm_comb
- `_L`：left，大写，左
- `_R`：right，大写，右
- `_w_`：white，空心（统一码别致的命名法，同理`_b_`(black)是实心）
- `_i_`：ideographic，东亚符号，兼作fullwidth全角符号，因为本字体不等宽无所谓全角了，只会是空隙宽些。

`+`号表示该图形被用于多个符号，命名将多个符号列举出。
### 特性标签
既然看过脚本了，那么介绍一下[OT特性标签](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Fonts/OpenType_fonts_guide)——就是这些4字缩写。可以点击前个链接学习如果作为网页字体用的话怎样在CSS中调用特性。下图仅作示意，与实际字体有差异。

![示意图](/preview.png)

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

`liga`连字（ligatures）暂时还用不到，因为涉及多个字符**目前示例字体不含**，或用于「RUjimaku」作空心字符替换，但可能和'ccmp'重复，命名可考虑`titl`标题大字替换（titling alternates）／`nalt`／自定义。浏览器默认开启。

不考虑特性的话，字符命名也可以自定义4字缩写，如“u660E.logo”，实质用的是'nalt'特性。
