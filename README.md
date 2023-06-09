# 中英文对照，英语词汇 txt json

该库包含两个版本的词库
1. 乱序 txt 版本，只包含词条和注释，格式： `单词\t释义`
2. 顺序 json 版本，包含词条、多条注释、多条词组及注释

两个版本的词条数量是一样的

| | 类别 | 单词数量|
| ---|---|---:|
| 1 | 初中  | 3223 |
| 2 | 高中  | 6008 |
| 3 | 四级  | 7508 |
| 4 | 六级  | 5651 |
| 5 | 考研  | 9602 |
| 6 | 托福  | 13477 |
| 7 | SAT |  8887 |

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



## 三、其它

该库是从 [https://github.com/kajweb/dict](https://github.com/kajweb/dict) 的 `json` 文件中转过来的

原文件可以看我 fork 出来的库：  
[https://github.com/KyleBing/dict](https://github.com/KyleBing/dict)

**初衷**
有些时候需要单词和释义的 txt 列表，只是单纯的单词列表，结果网上找一圈全是文库里的，还要充会员，相当恶心。  
有点分享精神好不好，为了方便大家用于学习使用放 github 了。
