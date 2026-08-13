# full TSV

由 [full JSONL](../full_line_jsonl/README.md) 转成的一词一行 TSV，目录对齐。给表格软件、Anki、脚本按列切用，比 JSONL 小、不用解析嵌套 JSON。

```
{simple,sentence,full}/{正序,乱序}/四级.txt
```

# 正序 · 23 本 · 116,953 词

| 词库 | 单词 | | simple | sentence | full |
|------|-----:|-|-------:|---------:|-----:|
| GRE | 13,714 | `███████████` | 1.47 MB | 3.60 MB | 7.37 MB |
| 托福 | 13,477 | `███████████` | 3.16 MB | 5.73 MB | 10.26 MB |
| 专八 | 12,881 | `██████████░` | 3.01 MB | 5.20 MB | 9.18 MB |
| 考研 | 9,602 | `████████░░░` | 3.28 MB | 4.94 MB | 8.74 MB |
| SAT | 8,887 | `███████░░░░` | 1.46 MB | 2.90 MB | 5.80 MB |
| 四级 | 7,508 | `██████░░░░░` | 2.85 MB | 4.24 MB | 9.62 MB |
| 雅思 | 7,002 | `██████░░░░░` | 1.90 MB | 3.06 MB | 5.66 MB |
| GMAT | 6,301 | `█████░░░░░░` | 1.48 MB | 2.62 MB | 4.83 MB |
| 高中 | 6,008 | `█████░░░░░░` | 2.48 MB | 3.68 MB | 6.03 MB |
| 六级 | 5,651 | `█████░░░░░░` | 1.55 MB | 2.49 MB | 6.09 MB |
| 商务英语 | 5,578 | `████░░░░░░░` | 2.07 MB | 3.09 MB | 5.34 MB |
| 专四 | 4,620 | `████░░░░░░░` | 1.15 MB | 1.94 MB | 3.43 MB |
| 人教高中 | 3,877 | `███░░░░░░░░` | 989 KB | 1.75 MB | 2.95 MB |
| 北师高中 | 3,293 | `███░░░░░░░░` | 874 KB | 1.47 MB | 2.58 MB |
| 初中 | 3,223 | `███░░░░░░░░` | 1.61 MB | 2.33 MB | 3.61 MB |
| 外研社初中 | 2,162 | `██░░░░░░░░░` | 890 KB | 1.33 MB | 2.02 MB |
| 人教初中八年级 | 885 | `█░░░░░░░░░░` | 330 KB | 539 KB | 836 KB |
| 人教初中七年级 | 884 | `█░░░░░░░░░░` | 361 KB | 575 KB | 828 KB |
| 人教初中九年级 | 551 | `█░░░░░░░░░░` | 197 KB | 316 KB | 496 KB |
| 人教小学五年级 | 287 | `█░░░░░░░░░░` | 102 KB | 182 KB | 259 KB |
| 人教小学六年级 | 238 | `█░░░░░░░░░░` | 93.1 KB | 161 KB | 228 KB |
| 人教小学四年级 | 188 | `█░░░░░░░░░░` | 69.4 KB | 114 KB | 163 KB |
| 人教小学三年级 | 136 | `█░░░░░░░░░░` | 63.7 KB | 96.8 KB | 137 KB |
| **合计** | **116,953** | | **31.35 MB** | **52.30 MB** | **96.39 MB** |

# 乱序 · 9 本 · 36,056 词

| 词库 | 单词 | | simple | sentence | full |
|------|-----:|-|-------:|---------:|-----:|
| 专八 | 12,197 | `███████████` | 2.94 MB | 5.01 MB | 8.82 MB |
| 四级 | 4,901 | `████░░░░░░░` | 1.86 MB | 2.92 MB | 6.64 MB |
| 专四 | 4,620 | `████░░░░░░░` | 1.15 MB | 1.94 MB | 3.43 MB |
| 高中 | 3,668 | `███░░░░░░░░` | 1.55 MB | 2.27 MB | 3.66 MB |
| 雅思 | 3,427 | `███░░░░░░░░` | 896 KB | 1.42 MB | 2.64 MB |
| GMAT | 3,254 | `███░░░░░░░░` | 822 KB | 1.39 MB | 2.53 MB |
| 初中 | 1,420 | `█░░░░░░░░░░` | 758 KB | 1.06 MB | 1.63 MB |
| 考研 | 1,341 | `█░░░░░░░░░░` | 495 KB | 817 KB | 1.37 MB |
| 六级 | 1,228 | `█░░░░░░░░░░` | 313 KB | 538 KB | 1.02 MB |
| **合计** | **36,056** | | **10.71 MB** | **17.33 MB** | **31.74 MB** |

# 格式特点

| 目录 | 列数 | 一行里有什么 | 示例 |
|------|-----:|--------------|------|
| `simple/` | 3 | 词条、释义、短语 | [sample_simple.txt](./sample_simple.txt) |
| `sentence/` | 6 | + 音标、例句 | [sample_sentence.txt](./sample_sentence.txt) |
| `full/` | 13 | + 同近义、同根、真题等 | [sample_full.txt](./sample_full.txt) |

乱序不并进正序。三种详略词数相同，列数不同，不要混读。校验：`python3 scripts/json_to_line.py --check`

- UTF-8、无 BOM、LF 换行，**无表头**；一词一行，列数固定。
- 列用 Tab（`U+0009`）分隔；缺值留空，Tab 仍在（末尾空列会留下连续 Tab）。
- 同一列多条用 `¦`（`U+00A6` broken bar，**不是** `|`），一条内各段用 `::`。
- 字段里若出现换行 / Tab / `\`，写成 `\n` `\t` `\\`；读入后先按 `\\` → `\`、`\n` → 换行、`\t` → Tab 还原。
- 单元格内不再出现真实换行或 Tab，所以用 `split('\t')` 即可，不必按 CSV 引号规则解析。

嵌套两层：

```
行  →  Tab 切成列
列  →  ¦  切成多条
条  →  :: 切成字段
```

例（`simple` 的 `translations`）：

```
v::说话；谈话¦n::交谈
```

| 条 | 词性 | 中文 |
|----|------|------|
| 1 | v | 说话；谈话 |
| 2 | n | 交谈 |

# 列

下标从 0。`sentence` / `full` 在 `word` 后插入音标，后面列顺延。

## `simple/` · 3 列

| # | 名 | 一条的形态 | 说明 |
|--:|----|------------|------|
| 0 | word | 纯文本 | 词头 |
| 1 | translations | `词性::中文` | 多义用 `¦` |
| 2 | phrases | `短语::释义` | 可空 |

## `sentence/` · 6 列

| # | 名 | 一条的形态 | 说明 |
|--:|----|------------|------|
| 0 | word | 纯文本 | |
| 1 | us | 纯文本 | 美音，可空 |
| 2 | uk | 纯文本 | 英音，可空 |
| 3 | translations | `词性::中文` | 同 simple |
| 4 | phrases | `短语::释义` | |
| 5 | sentences | `英文::中文` | 例句 |

## `full/` · 13 列

| # | 名 | 一条的形态 | 说明 |
|--:|----|------------|------|
| 0 | word | 纯文本 | |
| 1 | us | 纯文本 | 美音 |
| 2 | uk | 纯文本 | 英音 |
| 3 | translations | `词性::中文::英释` | 英释可空，仍保留 `::` |
| 4 | phrases | `短语::释义` | |
| 5 | sentences | `英文::中文` | |
| 6 | synonyms | `词性::释义::w1, w2` | 同近义，词用逗号空格连 |
| 7 | related | `词性::词::释义` | 同根词，一词一条 |
| 8 | antonyms | 词 | 反义；多条 `¦`，一般无 `::` |
| 9 | memory | 纯文本 | 助记 |
| 10 | exam_sents | `片段::来源` | 真题原句，如 `2017.6/CET4/阅读理解/第三套` |
| 11 | exams | `题干::答案序号::选项::解析` | 选择题；序号从 1；多题 `¦` |
| 12 | picture | URL | 配图，多数词库为空 |

`full` 的释义比 `simple` / `sentence` 多一段英释。`exams` 一条 4 段，不要按 2 段去拆。

# 怎么用

## 表格软件

Excel / Numbers / Google 表格：数据 → 导入文本，分隔符选 **Tab**，编码 **UTF-8**。不要当 CSV（逗号）打开，也不要双击让软件猜分隔符。`¦` 会留在单元格里，需要的话再分列。

## Anki

导入时选 Tab，第一列 Front、第二列 Back。`simple/正序/四级.txt` 可直接当「单词 → 词性+释义」。要拆多义，先按下面脚本把 `¦` 换成换行或 `<br>`。

## 命令行

```bash
# 单词 + 释义（simple）
cut -f1,2 full_line_tsv/simple/正序/四级.txt | head

# 单词 + 美音 + 英音 + 例句（sentence）
cut -f1,2,3,6 full_line_tsv/sentence/正序/四级.txt | head

# 行数 = 词数
wc -l full_line_tsv/simple/正序/四级.txt
```

## Python

```python
from pathlib import Path

def unescape(s: str) -> str:
    # 先占住 \\，避免和 \n \t 打架
    return s.replace('\\\\', '\0').replace('\\n', '\n').replace('\\t', '\t').replace('\0', '\\')

def items(cell: str) -> list[str]:
    return [unescape(x) for x in cell.split('¦') if x]

def segs(item: str) -> list[str]:
    return item.split('::')

cols = Path('full_line_tsv/simple/正序/四级.txt').read_text(encoding='utf-8').splitlines()[0].split('\t')
word, trans, phrases = cols[0], cols[1], cols[2]
for t in items(trans):
    pos, cn = segs(t)          # simple / sentence：两段
    print(word, pos, cn)
```

读 `full` 时 `translations` 是三段 `(词性, 中文, 英释)`，`exams` 是四段。空列是 `''`。

## pandas

```python
import pandas as pd

names = ['word', 'us', 'uk', 'translations', 'phrases', 'sentences',
         'synonyms', 'related', 'antonyms', 'memory', 'exam_sents', 'exams', 'picture']
df = pd.read_csv(
    'full_line_tsv/full/正序/四级.txt',
    sep='\t', header=None, names=names,
    dtype=str, keep_default_na=False, quoting=3,  # QUOTE_NONE
)
```

`simple` 用 `names=['word', 'translations', 'phrases']`；`sentence` 用前 6 个名字。
