# 中英文对照，英语词汇 txt json jsonl tsv

该库包含几个不同复杂程度的词库


| 格式    | 内容              |
| ----- | --------------- |
| txt   | 词条、释义           |
| json  | 词条、词组、释义        |
| jsonl | 词条、词组、近义词、释义、例句 |
| tsv   | 词条、词组、近义词、释义、例句 |


各格式都是下面这 7 个词库，词条数量相同。体积单位为 MB。

- jsonl、tsv 取正序文件，同一词库按详略有三份；
- 乱序是另一套词表，词数不同。


|          | 初中    | 高中    | 四级    | 六级    | 考研    | 托福     | SAT   | 合计         |
| -------- | ----- | ----- | ----- | ----- | ----- | ------ | ----- | ---------- |
| 词条数量     | 3,223 | 6,008 | 7,508 | 5,651 | 9,602 | 13,477 | 8,887 | **54,356** |
| txt      | 0.20  | 0.32  | 0.28  | 0.22  | 0.51  | 0.49   | 0.41  | **2.42**   |
| json     | 2.85  | 4.40  | 5.06  | 2.78  | 5.82  | 5.77   | 2.69  | **29.37**  |
| jsonl 简单 | 2.85  | 4.41  | 5.07  | 2.80  | 5.85  | 5.84   | 2.75  | **29.58**  |
| jsonl 例句 | 3.88  | 6.13  | 7.06  | 4.14  | 8.23  | 9.36   | 4.75  | **43.55**  |
| jsonl 完整 | 6.69  | 11.47 | 17.68 | 11.44 | 16.92 | 21.10  | 12.21 | **97.50**  |
| tsv 简单   | 1.61  | 2.48  | 2.85  | 1.55  | 3.28  | 3.16   | 1.46  | **16.39**  |
| tsv 例句   | 2.33  | 3.68  | 4.24  | 2.49  | 4.94  | 5.73   | 2.90  | **26.31**  |
| tsv 完整   | 3.61  | 6.03  | 9.62  | 6.09  | 8.74  | 10.26  | 5.80  | **50.15**  |




## 一、 txt 版本的文件内容

```
boat	n. 小船；轮船 v. 划船
group	n. 组；团体 adj. 群的；团体的 v. 聚合
nineteen	num. 十九
party	n. 政党，党派；聚会，派对；当事人 [复数 parties] v. 参加社交聚会 [ 过去式 partied 过去分词 partied 现在分词 partying ]
marriage	n. 结婚；婚姻生活；密切结合，合并
clean	adj. 清洁的，干净的；清白的 v. 使干净 adv. 完全地 n. 打扫
bottle	n. 瓶子；一瓶的容量 v. 控制；把…装入瓶中
tail	n. 尾巴；踪迹；辫子；燕尾服 v. 尾随；装上尾巴 adj. 从后面而来的；尾部的
very	adj. 恰好是，正是；甚至；十足的；特有的 adv. 非常，很；完全 n. (Very)人名；(英)维里
bag	n. 袋；猎获物；（俚）一瓶啤酒 v. 猎获；把…装入袋中；占据，私吞；使膨大
Tuesday	n. 星期二
```



## 二、 json 版本的文件内容

单个词条的内容如下：

```json
{
  "word": "ability",
  "translations": [
    {
      "translation": "能力，能耐；才能",
      "type": "n"
    }
  ],
  "phrases": [
    {"phrase": "innovation ability", "translation": "创新能力"}, 
    {"phrase": "ability for", "translation": "在…的能力"}, 
    {"phrase": "learning ability", "translation": "学习能力"}, 
    {"phrase": "practical ability", "translation": "实践能力；实际能力"}, 
    {"phrase": "technical ability", "translation": "技术能力"}, 
    {"phrase": "reading ability", "translation": "阅读能力"}, 
    {"phrase": "management ability", "translation": "管理能力"}, 
    {"phrase": "writing ability", "translation": "写作能力；书写能力"}, 
    {"phrase": "working ability", "translation": "工作能力，加工能力"}, 
    {"phrase": "physical ability", "translation": "体能，体质能力；身体能力"}, 
    {"phrase": "cognitive ability", "translation": "认知能力"}, 
    {"phrase": "service ability", "translation": "工作能力"}, 
    {"phrase": "ability to pay", "translation": "支付能力"}, 
    {"phrase": "combining ability", "translation": "配合力"}, 
    {"phrase": "develop ability", "translation": "发挥才能"}, 
    {"phrase": "executive ability", "translation": "执行力；行政能力"}, 
    {"phrase": "natural ability", "translation": "本能"}, 
    {"phrase": "administrative ability", "translation": "行政能力；经营才能"}, 
    {"phrase": "unique ability", "translation": "独有能力"}, 
    {"phrase": "adaptive ability", "translation": "自适应能力"}
  ]
}
```



## 三、JSONL 格式

正式 JSON 在 `full_line_jsonl`：一词一行，同一本书的分册已合并，按正序 / 乱序分开放（例如 `sentence/正序/四级.jsonl`）。


| 目录       | 注释                 | 例子                                                               |
| -------- | ------------------ | ---------------------------------------------------------------- |
| simple   | 词条、解释、短语           | [sample_simple.jsonl](./full_line_jsonl/sample_simple.jsonl)     |
| sentence | 再加上音标、例句           | [sample_sentence.jsonl](./full_line_jsonl/sample_sentence.jsonl) |
| full     | 原库完整结构（同近义、同根、真题等） | [sample_full.jsonl](./full_line_jsonl/sample_full.jsonl)         |


说明见 [full_line_jsonl/README.md](./full_line_jsonl/README.md)。

## 四、TSV 格式

同一套目录，嵌套拍成 Tab 分隔，放在 `full_line_tsv`。

格式说明见 [full_line_tsv/README.md](./full_line_tsv/README.md)，从 JSONL 生成：`python3 scripts/json_to_line.py`

## 五、其它

**[https://github.com/kajweb/dict](https://github.com/kajweb/dict)** → fork → **[https://github.com/KyleBing/dict](https://github.com/KyleBing/dict)** → 简化 → 本库

## 六、衍生项目


| 项目图标 | 项目名 | 作者 | github |
|---|---|---|---|
| <img width="50" src="https://github.com/heygsc/word-wind/blob/main/doc/logo-big.png"/> | Word Wind | [heygsc](https://github.com/heygsc) | [https://github.com/heygsc/word-wind](https://github.com/heygsc/word-wind) | 
| <img width="50" src="https://github.com/KyleBing/vocabulary/raw/master/public/logo.png"/> |  蚕食 | [KyleBing](https://github.com/KyleBing) |  [https://github.com/KyleBing/vocabulary](https://github.com/KyleBing/vocabulary) | 


---



## 初衷

有些时候需要单词和释义的 txt 列表，只是单纯的单词列表，结果网上找一圈全是文库里的，还要充会员，相当恶心。  
有点分享精神好不好，作为一个学习资源，该共享出来一起做一些可以方便学习的项目，为了方便大家用于学习使用放 github 了。  
后来发现只有词条不够用，真正学习的时候还是需要例句才能更好的帮助单词记忆，所以又添加了带例句的 jsonl tsv 文件。
