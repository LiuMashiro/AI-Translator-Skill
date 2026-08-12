---
name: "ai-translator"
description: "Professional Chinese-English bidirectional translation skill supporting multiple language styles, a three-step translation process (glossary-draft-review), AI flavor removal, and context-aware long text handling. Invoke when the user asks for translation, localization, or text conversion between Chinese and English."
---

# AI 翻译

专业级中英双向翻译 Skill。遵循三步流程：整体理解与名词表构建、初步精翻、审校润色。支持多种语言风格、去除 AI 味、保留输出格式，并以语义感知的分块方式处理长文本。

---

## 1. 核心原则

1. **场景与风格优先**：翻译前，先根据源文本确定合适的语言风格。风格是一切的基础。
2. **上下文绑定翻译**：每个句子都必须在其上下文环境中翻译，避免孤立翻译。
3. **忠实而自然**：在忠实于原文的同时，确保译文读起来像母语者自然写出。
4. **术语一致性**：所有专有名词、技术术语和关键短语必须在全文中统一翻译。
5. **格式保留**：输出格式必须与输入格式完全一致（纯文本、Markdown、文件格式等）。
6. **惯用形式保留**：某些广泛认可的术语可在适当情况下保留原形式（见第 6 节）。

---

## 2. 语言风格

以下七种内置风格覆盖了最常见的翻译场景。AI 应从源文本自动检测合适风格，选定一个或多个（融合）风格，用户也可显式指定风格。

### 2.1 风格判定方法

- 如果用户指定了风格，使用该风格。
- 如果未指定，分析源文本的词汇、句式、语气和体裁，确定最合适的风格。对于明显无歧义的文本，直接进行，无需确认。

### 2.2 混合风格文本

某些文本包含多种风格（例如在需要正式的文本中引用了口语记录文本）。处理方式：
- 识别文本整体的主导风格，将其作为主要风格。
- 在翻译明显属于不同风格的段落时，局部调整语域（例如，将学术文本中的口语化引用以口语语域译出）。
- 保持风格切换之间的清晰过渡，让读者感受到切换是有意为之，而非前后不一。
- 过犹不及，不能文风过于割裂，比如严肃的报道中引用口语文本时非常俗气、轻佻。

### 2.3 内置风格与参考文本

以下每种风格均包含来自已发表作品的真实人类文本节选。这些作为语气、节奏和语域的校准参考。仿照它们的写法。

---

#### 风格 1：正式 / 学术

**特征**：术语精确、句式完整、逻辑严密、大量使用被动语态和名词化结构、结构化段落（目的—方法—结果—结论）、客观中立。

**中文参考**：

> 教师教学评价是教育评价的重要组成部分，是对教师教学工作进行价值判断的过程，也是影响教师专业发展与成长的重要因素。本文以3个案例分析为依据，对中小学教师教学评价现状和评价体系进行研究与分析。

> 二是坚持创新驱动发展，建设现代化产业体系。全面推进科技强国建设战略部署，强化国家战略科技力量建设，完善区域科技创新体系，加强基础前沿领域体系化布局和关键核心技术攻关。全社会研发经费投入强度达到2.8%，技术合同成交额增长10.8%。科技创新和产业创新融合加快，传统产业转型升级不断深入，新兴产业、未来产业蓬勃发展，现代服务业保持快速发展势头。聚焦重点领域制定修订583项国家标准。持续推进制造业数字化转型和“人工智能+”行动，行业应用加快落地，新型智能终端不断涌现。数据要素潜力加快释放，数字经济核心产业增加值占国内生产总值的比重提高到10.5%以上。

> 社会情感能力培养是青少年和成年人获得并应用知识、技能和态度,以发展健康的身份认同、管理情绪、实现个人和集体目标、对他人产生并表达同理心、建立和维持支持性关系,以及做出负责任和关爱的决策的过程。加强学生的社会情感学习、重视学生的社会情感能力培养已成为世界教育的洪流。教师的社会情感能力不仅关乎自身的职业幸福和教育效能,还直接关涉其专业关系诸方面的高效和谐及其优质教育的达成。 师范教育是培养社会情感的母机和天然领域,乡村定向师范生社会情感能力培养是实现乡村全面振兴和乡村教师可持续发展的重要一环,也是填补教师教育体系中“社会情感鸿沟”的最后一公里。

> 从上述查明事实可见，虽然案涉纠纷源自某丁公司与某丙公司的承包合同纠纷，但本案是某丁公司提起仲裁申请，仲裁裁决进入执行后尚有未履行完毕的事项，权利承继人某乙公司与某丙公司、某甲公司就恢复案涉大楼原状问题协商未果，自行聘请施工单位进行了拆除和恢复工程而引发了施工及租金损失赔偿问题，与原合同关系不同。案涉仲裁裁决裁项（三）内容是：被申请人某丙公司在收到该裁决之日起30日内将**大楼恢复原状、腾退租赁商户并交付给申请人。在该裁决的执行过程中，执行法院只强制执行了案涉房产的腾退和交付事宜，并没有完成恢复原状这一执行内容。某丁公司申请撤回的只是支付拖欠承包费及仲裁费这两个裁项，并没有放弃主张将案涉房产恢复原状的权利。某乙公司作为某丁公司相关权利承继人，亦有权主张案涉房产恢复原状的权利。某甲公司作为案涉房产原实际使用人，曾作为原告提起案外人执行异议之诉，明确主张其是案涉房产添附的电梯等财产的所有人，后其未配合履行，给某乙公司的正常使用带来阻碍。某丙公司是仲裁裁决应履行义务的一方，亦是某甲公司的实际控制人，原判决根据当事人诉求结合执行案件已因撤回执行申请而执行终结等具体情况，认定某丙公司和某甲公司构成共同侵权并应承担赔偿责任，符合本案实际。

> 1.2 静电感应型纳米发电机
>
> ​	1.2.1 静电感应型纳米发电机的发展
>
> ​	自从纳米发电机被提出以来，经过了十余年的研究，已经提了诸多类型的静电型纳米发电机，其按照荷电方式的不同可以分为以下几类：
>
> ​	1.摩擦纳米发电机(TENGs)：利用摩擦起电的原理，即通过电子亲合能具有差异的两种绝缘材料(或者金属和绝缘材料)相互接触，摩擦贴合，使得电子在接触界面从较高能级的表面转移到较低能级的表面，达到平衡后将在两个表面上形成等大异号的电荷^[16]^；随后通过外部激励形成相对运动，从而产生变化的电场和电容，进而产生感应的电势驱动外电路形成电流^[17, 18]^；其根据运动方式和结构的不同可分为接触‑分离式(Contact‑separation model)，滑动式(Sliding model)，独立层式(Freestanding mode)和单电极式(Single‑electrode model)，如图1.3(a)所示。
>
> ​	2.压电纳米发电机(PENGs)：利用压电材料的特性，当外部产生机械作用导致压电材料产生形变时，压电材料将产生相应的电压并在外电路形成电流^[19]^，如图1.3(b)所示。
>
> ​	3.驻极体式纳米发电机发电机(EBNGs)：驻极体是一种能够长时间储存电荷的绝缘材料，可以通过外部高压荷电的方式将电荷储存在驻极体的表面，随后通过外部激励产生相对运动导致变化的电场和电容，从而导致感应的电势驱动外电路形成电流^[20]^，如图1.3(c)所示。

**英文参考**：

> E-cigarettes are commonly used in attempts to stop smoking, but evidence is limited regarding their effectiveness as compared with that of nicotine products approved as smoking-cessation treatments. Methods: We randomly assigned adults attending U.K. National Health Service stop-smoking services to either nicotine-replacement products of their choice, including product combinations, provided for up to 3 months, or an e-cigarette starter pack.

> Part of the concern, researchers say, is that large areas of the Amazon might still be recovering from the severe droughts of 2023–24. Hao Bai, a forest ecologist at Peking University in Beijing, and his colleagues determined this by analysing 33 years of radar satellite data that tracked two indicators of forest health — how much moisture the forest holds and how much living plant matter it contains — across the Amazon basin. During the 2023–24 droughts, the researchers found, radar measurements associated with both indicators fell to their lowest levels since satellite records began in 1992[5]. The authors estimate that less than half of the affected forest will have returned to pre-drought conditions within seven years — the slowest recovery from a major Amazon drought in the satellite record.

> As scientists who rely on AI in our own work, we think a more practical solution exists on Earth. Researchers must pioneer the adoption of open-weight AI models that run locally on institutional servers. Here, we outline a vision for a more decentralized approach to AI — one that allows researchers to deploy these tools in a more accountable manner, while reducing reliance on massive data centres.

> What the cynics fail to understand is that the ground has shifted beneath them—that the stale political arguments that have consumed us for so long no longer apply. The question we ask today is not whether our government is too big or too small, but whether it works—whether it helps families find jobs at a decent wage, care they can afford, a retirement that is dignified. Where the answer is *yes*, we intend to move forward. Where the answer is *no*, programs will end. And those of us who manage the public's dollars will be held to account—to spend wisely, reform bad habits, and do our business in the light of day—because only then can we restore the vital trust between a people and their government.

> I concur in the Court’s decision not to grant, vacate, and remand this case in light of *Hunter v. United States*, 608 U. S. _ (2026). *Hunter* addressed the enforceability of appeal waivers specifically “in the sentencing context,” id., at _ (slip op., at 1), whereas this petition concerns when a collateral‑review waiver is enforceable against a challenge to a defendant’s conviction. I write, however, to encourage lower courts to consider carefully the import of *Hunter*’s reasoning when deciding whether to enforce a collateral‑review or appeal waiver against a defendant who is challenging the validity of his conviction.

> China is a socialist country and a developing nation with a huge population and relatively large urban-rural and regional gaps, Xi said, adding that it is essential to proceed from China's actual conditions to advance the Healthy China Initiative.
>
> As the situation evolves, certain specific policies and measures related to health work need to be optimized and improved, Xi noted. He stressed the need to keep a clear mind and maintain strategic resolve on fundamental issues. (CGTV)

---

#### 风格 2：文学 / 美文

**特征**：句式长短交错、视角灵活、主观情感色彩浓厚、修辞丰富（象征、隐喻、意象）、心理深度。

**中文参考**：

> 今天晚上，很好的月光。
> 我不见他，已是三十多年；今天见了，精神分外爽快。才知道以前的三十多年，全是发昏；然而须十分小心。不然，那赵家的狗，何以看我两眼呢？
> 我怕得有理。

> 高邮咸蛋的特点是质细而油多。蛋白柔嫩，不似别处的发干、发粉，入口如嚼石灰。油多尤为别处所不及。鸭蛋的吃法，如袁子才所说，带壳切开，是一种，那是席间待客的办法。平常食用，一般都是敲破“空头”用筷子挖着吃。筷子头一扎下去，吱──红油就冒出来了。高邮咸蛋的黄是通红的。苏北有一道名菜，叫做“朱砂豆腐”，就是用高邮鸭蛋黄炒的豆腐。我在北京吃的咸鸭蛋，蛋黄是浅黄色的，这叫什么咸鸭蛋呢!

> 中年以后，家道渐丰，但是祖父生活俭朴，自奉甚薄。他爱喝一点好茶，西湖龙井。饭食很简单。他总是一个人吃，在堂屋一侧放一张“马杌”——较大的方凳，便是他的餐桌。坐小板凳。他爱吃长鱼（鳝鱼）汤下面。面下在白汤里，汤里的长鱼捞出来便是酒菜。——他每顿用一个五彩釉画公鸡的茶盅喝一盅酒。没有长鱼，就用咸鸭蛋下酒。一个咸鸭蛋吃两顿。上顿吃一半，把蛋壳上掏蛋黄蛋白的小口用一块小纸封起来，下顿再吃。他的马杌上从来没有第二样菜。喝了酒，常在房里大声背唐诗：“李白斗酒诗百篇，长安市上酒家眠。天子呼来不上船，自称臣是酒……中……仙……”汪铭甫的俭省，在我们县是有名的。

> 余既为此志，后五年，吾妻来归，时至轩中，从余问古事，或凭几学书。吾妻归宁，述诸小妹语曰：“闻姊家有阁子，且何谓阁子也？”其后六年，吾妻死，室坏不修。其后二年，余久卧病无聊，乃使人复葺南阁子，其制稍异于前。然自后余多在外，不常居。
>
> 庭有枇杷树，吾妻死之年所手植也，今已亭亭如盖矣。

> 刘姥姥屏声侧耳默候。只听远远有人笑声，约有一二十妇人，衣裙窸窣，渐入堂屋，往那边屋内去了。又见两三个妇人，都捧着大漆捧盒，进这边来等候。听得那边说了声“摆饭”，渐渐的人才散出，只有伺候端菜的几个人。半日鸦雀不闻之后，忽见二人抬了一张炕桌来，放在这边炕上，桌上碗盘森列，仍是满满的鱼肉在内，不过略动了几样。板儿一见了，便吵着要肉吃，刘姥姥一巴掌打了他去。忽见周瑞家的笑嘻嘻走过来，招手儿叫他。刘姥姥会意，于是带了板儿下炕，至堂屋中，周瑞家的又和他唧咕了一会，方过这边屋里来。

> 我家先生，我喜欢他多年，从高中开始，直到现在。我很确认他不爱我。生活中他所做的一切，都源自于一个成年人，一个丈夫应有的责任。在婚姻生活中，他没有任何可以被挑剔的地方。节日永远会有花和礼物，生活中也会有小惊喜，他下班回家，会带我喜欢的零食和水果。......我先生做到了一个合格的丈夫应该做的一切，甚至要更好。但我还是知道，他不爱我。他有过一个相恋多年的女友，从高中到大学，六年。因为我看过他还是一个男孩时，对待爱情的模样。所以我很清楚，现在留给我的，只是一个成熟的男人。甚至我曾想过，如果跟他结婚的人不是我，而是另一个人，他也会做到这些。他在婚姻中付出的一切，不是付出给我，而是给了跟他结婚的那个人。他从不和我说他的心事，也不说工作的压力，没有和我聊过他的童年。有一段时间，他工作压力特别大，每天都在书房加班到很晚。我心疼他，想陪他一起熬夜，给他煲汤。每次，他都会说不用，让我快去睡。......仿佛，他就是一座山，任凭我依靠着，所有的风雨由他来扛，我只需要在他的庇护下岁月静好。......我理解这一点，但我依旧很遗憾，我在山外，厚厚的岩壁阻隔，终究没办法真正接近他。这个问题，应该让我先生回答，毕竟，我很爱他。
> ......他很诧异我心中的想法。昨天晚上买了啤酒，我和先生坐在沙发上边吃边聊，谈了很久。我们互相敞开心扉，并对我的疑问一一做出了解答。我：为什么你从不和我聊你的工作和难处？先生：那些专业上的事情，你不懂，即便告诉了你，也是徒增烦恼。与其那样，不如让你保持好心情。......后来，有一次他加班回来，在楼道里闻着饭菜香，进了门却发现厨房空空荡荡，香味是邻居家的。他当时心里很失望（原谅我，真的不爱做饭，但是刷碗没问题），放下公文包，结果看到了在洗手间的我，坐着小马扎，披散着头发，认真的给他搓洗内裤和袜子。他的心一瞬间被击中了，这时候我听到动静，回头也发现了他，跟他说，我快洗完了。他问我想吃什么，他去做，我说叫了外卖，是你喜欢的粥。我先生说他在那个瞬间爱上了我......
> ......我爱人于二三年八月二十日因车祸意外离世.，今夜用她的手机处理事情，无意间再度翻到这篇回答，心中情绪之复杂，无法言说。看到爱人记录下我们关于生死的思考，未曾想一语成谶。忽而想起曾看过的一场辩论，故事的结局是否重要，很多人以为的结局是这样一种场景，杂志社的编辑告诉你，还有三个月交稿，多想多看，写坏了没关系，我们时间充裕，重新再写，好好写。其实不是。真正的结局是某个下午，你午睡醒来，在纸上潦草的画了几笔，心中想着晚上吃点什么，房门忽然被敲响，来人问你写到了哪，不管上面写了什么，你有多不甘心，多想要修改，这页就是结局。世事无常，人生不如意太多太多。谢谢曾在评论里祝福过我们的朋友，爱人曾不止一次跟我谈起过，你们很可爱，你们很好。愿大家珍惜眼前人，自己所爱之人，所爱之事，认真的过完这一生，莫要后悔。以我爱人最常用的分别祝福语替她向诸位告别。愿诸位一生顺遂，平安喜乐。祝好，再见。
> ......已经两年了，看着大家两年来的评论，万般情绪，无法开口。谢谢各位对我爱人的喜爱与惋惜，谢谢还能有这么多人记得她，谢谢大家，谢谢。希望诸位珍惜身边人，珍惜所爱的一切，人没了，就真的没了。诸位，珍惜啊，陪在身边人的时间实在太短了。万般皆是命，半点不由人。诸位，珍惜。
> ......也许这是最后一次帮我爱人更新她的回答，我没有多少时间了。这几年过得挺艰难，对任何工作，任何事情都提不起来兴趣，总也睡不够，医生说我心里那股气散掉了。大哥总叫我去家里吃饭，我不敢去，怕自己喝多了哭。怎么来形容这几年的生活，不敢死，但又不想活。终于结束了，肺癌，不治了。觉得自己挺幸运，如果爱人没出意外，我先走了，她该怎么过，不治了，现在挺好。遗产已经划分完，3.5MW光伏电站卖掉了，新政出来市场不好，价格也不高，不过这些钱给父母养老也足够了。剩下5MW光伏和1.8MWH的储能站都给了大哥，他帮了我和爱人这么多年，我知道，他也难。接下来出去转转，没想好去哪，可能去个经常下雨的地方，我爱人最喜欢下雨。现在的心情说不上开心，也不难过，只是松快了，真松快了。大家的评论我一条条翻开看了，替我爱人谢谢大家，希望大家珍惜吧，希望大家珍惜。突然想到太阳照常升起里面周韵念得那首诗，昔人已乘黄鹤去，此地空余黄鹤楼，黄鹤一去不复返，白云千载空悠悠。那就这样，再见。

**英文参考**：

> He was an old man who fished alone in a skiff in the Gulf Stream and he had gone eighty-four days now without taking a fish. In the first forty days a boy had been with him. But after forty days without a fish the boy's parents had told him that the old man was now definitely and finally salao, which is the worst form of unlucky.

> Oh, I am so sick of the young men of the present day!” exclaimed she, rattling away at the instrument. “Poor, puny things, not fit to stir a step beyond papa’s park gates: nor to go even so far without mama’s permission and guardianship! Creatures so absorbed in care about their pretty faces, and their white hands, and their small feet; as if a man had anything to do with beauty! As if loveliness were not the special prerogative of woman—her legitimate appanage and heritage! I grant an ugly *woman* is a blot on the fair face of creation; but as to the *gentlemen*, let them be solicitous to possess only strength and valour: let their motto be:—Hunt, shoot, and fight: the rest is not worth a fillip. Such should be my device, were I a man.”

> Oliver knew, perfectly well, that he was in his own little room; that his books were lying on the table before him; that the sweet air was stirring among the creeping plants outside. And yet he was asleep. Suddenly, the scene changed; the air became close and confined; and he thought, with a glow of terror, that he was in the Jew’s house again. There sat the hideous old man, in his accustomed corner, pointing at him, and whispering to another man, with his face averted, who sat beside him.
>
> “Hush, my dear!” he thought he heard the Jew say; “it is he, sure enough. Come away.”

---

#### 风格 3：口语 / 通俗

**特征**：短句、松散句式；第一/第二人称；随意幽默的语气；大量使用俚语、习语和口头禅；以对话驱动叙事；英文大量使用简写缩写。

**中文参考**：

> 人民生活水平是提高了，过去您没觉着肉贵那时过去您压根不怎么买肉，割二毛钱肥膘就全家吃饺子了。要是肉价还是前两年那价，国家就是把全国变成大猪圈也不够您狠吃的。

> 事情是这样的，家人们，就在当地时间8月4号，李在明主持召开了韩国的国务会议，审议并通过刑事诉讼法修正案。也就是说，从这一刻起，韩国的检察机关不再拥有直接侦查和收集证据等权限，韩国检察厅将被撤销，新成立的公诉厅来承接原有的部分起诉职能。换句话说呢，在韩国政坛耀武扬威78年，送走无数总统，尹大统领的第二故乡，那个不可直视的权力怪兽，终于，阿西巴拉，要我说啊，这可把我给急坏了。老李啊，老李，你把检察机关给撤了，我缺的青瓦台魔咒这一块，以后谁给我补啊？我得说，老李头啊，是个狠人，为了自己下台之后，直接把清算工具给废了，跳出三界之外，不在五行之中，说我命由我，不由天呐！要我说的话，不兴这么干活呀，载明，你自己喜欢绝食，也不能砸了别人吃饭的锅呀。

> 首先，北家有两个牌子和一个广告牌，这里是酒店的意思。指向B的牌子写的是卡斯巴宫，往B包走；还有一个卡斯巴的广告牌和一家烟草店。游戏也还原了现实中的特点，有土黄色夯土墙、方形塔楼、狭窄巷道，兼具居住和防御功能，参考的是北非城市如马拉喀什的标志性历史建筑。指向A的是奥罗拉大酒店，也就是A包点后面的那个建筑，是不是你平时没注意到呢？而且这不是装饰，你是可以把道具丢在这里的，不过实战还是不要这么做。

> “就是那个***学院的这些老师们，最后是踢了那个乌龙球，那个我觉得我看到你们俩都写过，我觉得特别逗。就是他们不敢踢那个***守门的那个球门，所以他拼命的往另一个球门里踢，那个时候**好像已经不在了。”
>
> “我在！我在！我在！你在吗？踢球的时候，你在吗？”
>
> “然后呢，***学院的学员们又不敢往**那踢，因为他们的脚法也不是那么好。基本上是我们对着他们的门进攻，我们主要是传球给马原，因为马原个子最高嘛，是希望利用他的头球优势。”
>
> “结果他没有什么头球技术，当然我们的脚法更烂，传的方向偏得很远，你知道吗？”
>
> “对，最后我们客场打平。”
>
> “嗯，对，嗯嗯，不是，是他们踢的自己的球门嘛，对吧？”
>
> “没有没有没有，他们没踢。”
>
> “就是自己的球迷，他们自始至终一直在防守，因为他们不敢踢我们那个门。因为我们那个门，*在那儿，他们敢踢吗？万一把铁生踢坏了呢？怎么办？”
>
> “所以最后还是零比零，但是我们已经很满意了，客场能打平就不错了，你知道吗？”
>
> “嗯，好的，这就是当段子来听。”
>
> “对对对，听过哈哈一笑就行。”
>
> “对对对，不是真的。”
>
> “之前其实大家都知道，是我说的啊，我们几个去演讲，谈怎么走上文学之路的，我们几个都是瞎编的。”
>
> “对。”

**英文参考**：

> I've been doing my own nails and my gel x nails have been on for 2 weeks. I'm doing something right lol. My birthday is Sunday and Fall semester starts the following Monday 

> I mean, I’m single, ain’t bad if I flirt a little bit with the doctor. I mean, she is attractive and there was the vibe. So… why do I feel guilty? lol

> asked the delivery guy in work yesterday how he was & he goes “I’m alive” so I said “that’s good!” but then he said “sorry I’m having a day I shouldn’t have said that”, (I didn’t think anything of it tbh) but he came in today & when i asked, he goes “I’m great today!” I’m glad
>
> Getting a tattoo tomorrow and I still haven’t decided where on my arm I want it… just out here treating a permanent piece on my skin like I’m choosing fucking nail designs

> Caminero BB +155 Can honestly say that’s the heaviest I’ve ever played a walk prop in my life lol LFGGGGGGGGGGG
>
> Played a decent bit of golf with him back in the day (his son was the best player on our team at Iowa State). Aside from being every bit as cool as he is in this photo, he’s an all-world guy who helped me find a job when I moved out West. Epic human. Best short game of all-time.

---

#### 风格 4：技术 / 科技

**特征**：指令式/说明式语气、精确无歧义、代码标识符使用等宽字体、大量使用列表和加粗强调关键约束、步骤化结构。

**中文参考**（技术文档）：

> Fetch API 提供了一个 JavaScript 接口，用于访问和操纵 HTTP 管道的一些具体部分，例如请求和响应。它还提供了一个全局 `fetch()` 方法，该方法提供了一种简单、合理的方式来跨网络异步获取资源。
> 这种功能以前是使用 `XMLHttpRequest` 实现的。Fetch 提供了一个更理想的替代方案。

**英文参考**（编程文档）：

> The keyword `def` introduces a function definition. It must be followed by the function name and the parenthesized list of formal parameters. The statements that form the body of the function start at the next line, and must be indented.
> The first statement of the function body can optionally be a string literal; this string literal is the function's documentation string, or docstring.

---

#### 风格 5：新闻 / 报道

**特征**：倒金字塔结构（核心事实前置，细节后置）、客观第三人称、引用权威信源、数据驱动、简洁且有冲击力的句子。

**中文参考**（新闻报道）：

> 记者从人力资源社会保障部获悉：8月10日至16日，百日千万招聘专项行动推出电力新能源、跨境电商、交通运输、互联网行业4个线上招聘专场，共7700余家用人单位参与，招聘需求8万余人次。
>
> 电力新能源行业专场组织深爱半导体、永联科技、万宝能源等243家用人单位，提供电池研发工程师、技术支持工程师、材料工程师等岗位，招聘需求1.5万余人次；跨境电商行业专场组织嘉兴吉星网络技术有限公司等3000家用人单位，提供外贸业务员、跨境电商运营专员、销售代表、业务主管等岗位，招聘需求3万人次；交通运输行业专场组织北京公交集团、中远海运等162家用人单位，提供关务主管、硬件工程师、物流安全员、自动化系统设计师等岗位，招聘需求超3000人次；互联网行业专场组织腾讯、百度等4346家用人单位，提供AI策略产品经理、多模态大模型算法专家、嵌入式开发工程师等岗位，招聘需求3.2万人次。

> 新华社北京8月11日电　全球最大再保险公司之一瑞士再保险公司11日说，今年上半年全球自然灾害造成的经济损失据估算已达1000亿美元，较去年同期的1520亿美元大幅减少。但今年下半年，厄尔尼诺现象可能会加剧气象灾害的破坏力，风险不容忽视。
>
> 该公司在最新报告中说，尽管有美国3月强风暴、委内瑞拉6月强震等灾难，但今年上半年全球自然灾害造成的经济损失依然低于2025年上半年，并且比过去10年同期的平均水平低10%。

**英文参考**（新闻报道）：

> The U.S. Senate passed a stopgap spending bill Friday evening, averting a partial government shutdown and overcoming Democratic opposition to the measure.
>
> The bill passed 54-46 after clearing a more difficult procedural hurdle to stop debate on the measure, which required at least 60 votes.
>
> The Republican-controlled House of Representatives passed the bill earlier this week to meet a March 14 deadline to keep the government running.
>
> Senate Democrats had fractured over whether to support the short-term continuing resolution (CR) that would fund the government for the next six months, reduce total government spending by about $7 billion from last year's levels and shift money to the military and away from non-defense spending.

> US President Donald Trump has signed an order that calls for fewer childhood vaccines and also recommends splitting the mumps, measles and rubella (MMR) shots.
>
> "Decades ago, children received only a small fraction of the vaccines required today," Trump said. "In those times, people were much healthier and of course the high rates of autism now observed did not exist."
>
> The president has long cast doubt on the safety of MMR vaccines, but multiple studies have found no connection between the shots and autism.

---

#### 风格 6：商务 / 专业

**特征**：礼貌而正式的套语、数据精确、标准化的会计/商业术语、正式的企业语域。

**中文参考**：

> 本人欣然向各股東提呈我們截至二零二五年十二月三十一日止年度的年報。
> 本集團截至二零二五年十二月三十一日止年度經審核的本公司權益持有人應佔盈利為人民幣2,248.42億元，較上一年度的業績增長16%。

> 2026年上半年，外卖行业进入监管趋严、补贴退潮的发展阶段，过去长期存在的低价补贴内卷、食品安全隐患、骑手用工不规范等行业痛点开始得到集中整治。
>
> 随着补贴潮的褪去和新规的施行，进一步倒逼平台重视消费者真实诉求，消费决策重心逐步由价格优惠转向食品安全、服务品质，依靠烧钱换规模的粗放增长模式不再可行，市场竞争逻辑发生根本性重塑，逐步走向品质化、精细化、场景化发展。这一趋势下，受前期经营积淀不同，基于“品质”定位的新兴平台优势得以展现，原本依赖粗放补贴的平台整改压力和转型节奏承压。
>
> 结合一系列的行业新变化，通过多元数据，目前推总测算2026年Q2季度外卖市场综合份额，推测美团外卖：淘宝闪购：京东外卖=43%：42%：15%。可以看出，行业趋势下能够有效响应消费者需求、深耕品质外卖的平台，将拥有更优的发展前景。
>
> 本文结合行业监管动态、平台经营举措以及用户量化数据，系统剖析本轮行业变革之下外卖市场供给端调整、用户端变迁以及竞争格局演化，拆解行业全新的竞争逻辑与未来发展走向。

> 2026年7月份，全国工业生产者出厂价格同比上涨3.5%，环比下降0.7%。工业生产者购进价格同比上涨5.5%，环比下降1.0%。1—7月平均，工业生产者出厂价格比上年同期上涨1.8%，工业生产者购进价格上涨2.8%。
>
> 一、工业生产者价格同比变动情况
>
> 7月份，工业生产者出厂价格中，生产资料价格同比上涨4.8%，影响工业生产者出厂价格总水平上涨约3.72个百分点。其中，采掘工业价格上涨16.4%，原材料工业价格上涨6.1%，加工工业价格上涨3.1%。生活资料价格下降0.8%，影响工业生产者出厂价格总水平下降约0.17个百分点。其中，食品价格下降2.1%，衣着价格下降1.1%，一般日用品价格下降1.0%，耐用消费品价格上涨0.4%。
>
> 工业生产者购进价格中，有色金属材料及电线类价格上涨19.0%，燃料动力类、化工原料类价格均上涨9.3%，纺织原料类价格上涨3.2%，黑色金属材料类价格上涨1.4%；建筑材料及非金属类价格下降4.1%，农副产品类价格下降0.8%。

**英文参考**：

> I am pleased to present our annual report for the year ended 31 December 2025 to the shareholders. The Group's audited profit attributable to equity holders of the Company for the year ended 31 December 2025 was RMB224,842 million, an increase of 16% compared with the results for the previous year.

> AUGUST 6, 2026 — The rate of individuals under age 65 without health insurance in the United States decreased in 65 counties and increased in 427 counties between 2023 and 2024, according to the Small Area Health Insurance Estimates (SAHIE) released today by the U.S. Census Bureau.
>
> SAHIE is the only source for single-year estimates of people under age 65 with health insurance in each of the nation’s 3,143 counties. The county statistics are provided by sex and age group and at income levels reflecting thresholds for state and federal assistance programs, such as Medicaid eligibility. State estimates also include health coverage by race and Hispanic origin. This is the first SAHIE release to include a breakdown of health insurance estimates for the age group 21-29.
>
> According to SAHIE, 1,300, or 41.4%, of U.S. counties had an estimated uninsured rate below 10% in 2024, down from 46.3% of counties in 2023 and 45.2% of counties in 2022.
>
> Other SAHIE highlights:
>
> The median county uninsured rate in 2024 was 9.8%, up from 9.3% in 2023 and 9.4% in 2022.
> Uninsured rates among working-age adults ages 18 to 64 decreased in 73 counties and increased in 296 counties. Meanwhile, uninsured rates among children younger than 19 decreased in nine counties and increased in 185 counties.
> Working-age women had lower estimated uninsured rates than working-age men in 70.2% (2,205) of counties.
> The median county uninsured rate among working-age adults living at or below 138% of the poverty threshold was 18.4%, compared with 17.7% in 2023 and 18.6% in 2022.
> For more information, visit our interactive data and mapping tools. This tool allows users to create and download state and county custom tables, thematic maps, and time-trend charts for different geographic levels and demographic groups available annually from 2006 to 2024.

---

#### 风格 7：公文

**特征**：中文公文大量使用排比句和光明伟大的用词，突出积极稳定。

**中文参考**

> 第一，坚持从我国国情出发推动卫生与健康事业发展。我国是社会主义国家，是人口规模巨大、城乡区域差距仍然较大的发展中国家，这决定我们必须坚持党对卫生与健康工作的领导，坚持人民至上、生命至上，坚持健康优先发展战略，坚持基本医疗卫生事业的公益性，走中国特色卫生与健康发展道路。在2016年的全国卫生与健康大会上，中共中央明确提出新时代卫生与健康工作方针，即以基层为重点，以改革创新为动力，预防为主，中西医并重，把健康融入所有政策，人民共建共享。新时代以来我国卫生与健康事业发展取得的历史性成就，充分证明这些要求符合我国国情，是完全正确的。当前和今后一个时期，我国卫生与健康工作需要因应形势发展变化，优化完善一些具体政策举措，但是走中国特色卫生与健康发展道路不能动摇，贯彻新时代卫生与健康工作方针不能动摇。在这些根本问题上，必须始终头脑清醒、保持战略定力。
>
> 第二，突出重点推进健康中国建设。健康中国建设是一项系统工程。面对人民群众日益增长的多元化卫生健康需求，我们要紧紧抓住那些惠及面广、牵一发而动全身、对整个卫生与健康事业有重大影响的工作，集中力量和资源推动，不断取得新的成效。比如，健全公共卫生体系，要求深化社会共治、医防协同、医防融合，强化传染病预防控制、监测预警、医疗救治、应急处置、物资保障和监督管理。要高度重视心理健康和精神卫生问题，加强预防引导、早期发现和综合干预。再比如，人们对建设优质高效医疗服务体系的期望很高，要继续优化体系布局，实施医疗卫生强基工程，促进分级诊疗，加强县区和基层医疗卫生机构运行保障。要推进中西医结合，针对重点人群和薄弱专科加快补齐医疗服务短板，提高慢性病综合防控水平，扩大康复护理和安宁疗护等服务供给。又比如，倡导健康文明的生活方式，需要进一步提高全民健康素养，开展全民健身和爱国卫生运动，引导人们合理膳食、加强健康体重管理等，这些都要有实际举措和具体抓手。重点工作做到位了，健康中国建设就能扎实推进。

> 会议指出，党的十八大以来，全面从严治党取得伟大成就，开辟了百年大党自我革命新境界，推动党和国家事业取得历史性成就、发生历史性变革，党和人民赢得强党强国的历史主动。同时，随着世情国情党情发生深刻变化，全面从严治党也面临许多新情况新问题。全党必须从巩固党的执政地位、实现党的使命任务的战略高度，深刻认识持之以恒推进全面从严治党的重大意义，坚定信心，保持定力，以更高标准、更实举措把新时代全面从严治党宝贵经验坚持好、运用好，把党的建设面临的突出问题整治好、解决好，把管党治党形成的良好政治局面巩固好、发展好。

> 党的二十大擘画了全面建设社会主义现代化国家，以中国式现代化全面推进中华民族伟大复兴的宏伟蓝图。即将召开的十四届全国人大一次会议，是在全面贯彻落实党的二十大精神开局之年召开的一次重要会议，是换届的大会，也是国家政治生活中的一件大事。

> （一）持续加大统筹推进力度。一是加强总体协调。认真贯彻落实二十届中央财经委员会第六次会议精神，制定分工方案和重点举措。深入实施《全国统一大市场建设指引（试行）》，指导各地纵深推进全国统一大市场建设，推动形成部门协同、上下联动、社会参与的工作局面。二是抓好监督约束。推动将全国统一大市场建设纳入中央全面依法治国委员会领导干部依法办事情况法治督察、国务院推动高质量发展综合督查等，督促地方补短板、强弱项。常态化发现问题、核实线索，强化督促整改、约谈通报，对违规行为形成有力震慑。三是强化宣传引导。开展专题培训，在中央媒体播发报道、刊发署名文章，营造良好社会氛围。在“焦点访谈”栏目推出专题节目，深度剖析违规招商引资案例，发挥警示教育作用。

> 围绕学习领会总书记重要讲话精神和全会审议通过的《建议》，从深刻认识全会重大意义，准确把握“十五五”时期在基本实现社会主义现代化进程中的重要地位，深刻领会“十五五”时期经济社会发展的指导方针和主要目标，全面理解“十五五”时期经济社会发展的战略任务和重大举措，坚持和加强党的全面领导等方面，对四中全会精神进行系统宣讲和深入阐释。

**英文参考**

> Mr. President, thank you for being here. Thank you for your leadership on this topic. It’s a challenge we face in this domain that actually goes to the very survival of the country, and thank you for giving it a priority in your presidency. This has been going on for 25 years. We’ve been walking away from the importance of this, and now we’re trying to make up for 25 or 30 years of mistakes under your presidency. So, we appreciate your presidency valuing this when other presidents did not.
>
> The group of people that are here today represent the whole-of-nation effort that’s involved in this. It’s – because at the core of this is our industrial strength, but also our national sovereignty – that we never depend on other countries for things we need to prosper and to defend ourselves as a people. And so, you’ll see here today, as you’ve already pointed out, we have leaders not just from government but from universities, from private industry, from students who are going to be the future of this industry. 
>
> There’s still a lot of work left to do, but we at the State Department are willing to utilize our unmatched global presence, our presence all over the world, to ensure that we’re working on this. And we’re committed to working with industry, with universities, with all the elements of our national power to bring this about. And so, thank you, Mr. President, for prioritizing this, and I think we all look forward to working not just nationally but with our allies around the world to ensure that we have supply chains that are diversified and reliable and no country can ever hold this over our head and threaten us in the future. Thank you.

> This progress reflects a simple truth: peace and prosperity reinforce one another. TRIPP is more than an infrastructure project — it is a vital link in the Trans-Caspian Trade Route, a driver of commercial opportunities for the United States and others, and a model for how economic cooperation can cement peace following the resolution of long-standing disputes.
>
> The United States remains fully committed to working with Armenia and Azerbaijan as they build on this foundation. We congratulate both nations on the courage and vision they have shown over the past year, and we look forward to continued progress toward a durable, lasting peace in the South Caucasus.

---

### 2.4 风格总览表

| 风格 | 句长 | 人称 | 语气 | 修辞 | 中文标志 | 英文标志 |
|------|------|------|------|------|----------|----------|
| 学术 | 长、复杂 | 第三人称/被动 | 客观中立 | 极少 | "本文""本研究" | "We randomly assigned" |
| 文学 | 长短交错 | 灵活 | 主观抒情 | 丰富（象征、隐喻） | 短句断行、意象、心理独白 | 节奏多变、意象 |
| 口语 | 短、松散 | 第一/第二人称 | 随意幽默 | 俚语、口头禅 | "压根""狠吃" | "and all," "if you want to know the truth" |
| 技术 | 中等、精确 | 祈使/第二人称 | 指令说明 | 无 | 代码标识符、列表、加粗 | 代码标识符、列表、加粗 |
| 新闻 | 中短 | 第三人称 | 客观 | 数据、引语 | 短句格言式开篇、数据驱动 | 倒金字塔、信源标注 |
| 商务 | 中等 | 第一/第三人称 | 礼貌正式 | 套语 | "本人欣然向各股東提呈" | "I am pleased to present" |
| 公文 | 长/排比 | 第三人称 | 稳定积极 | 排比 | “指出”，“强调” | 价值观 |

---

### 2.5 扩展风格

七种内置风格覆盖了最常见的场景。对于未涵盖的专门领域，AI 应：
1. 从源文本识别领域。
2. 以最接近的内置风格为基础。
3. 根据领域特定惯例进行调整（例如，法律文本要求严格的术语精确性和条款结构保留；字幕要求字符数限制和阅读速度限制；诗歌要求注意韵律和形式）。
4. 如果用户显式指定了此处未列出的风格，遵循用户的说明及任何额外指示。

---

## 3. 翻译流程

翻译遵循严格的三步流程。前一步完成后方可进入下一步。

### 第一步：整体理解与名词表构建

**目标**：形成对全文的整体理解，并构建术语名词表以确保一致性。

**步骤**：

1. **通读全文**，从头到尾。此时不要翻译。形成以下理解：
   - 整体主题和目的
   - 目标读者
   - 语气和语域
   - 文本类型（论文、手册、小说、报告等）
   - 合适的语言风格（见第 2 节）

2. **识别并列出专有名词、技术术语和高频易错多义词**。对每个条目记录：
   - 源术语
   - 建议翻译
   - 上下文/用法说明（出现位置、在此语境下的含义）
   - 是否需要确认

3. **对于不确定的术语**，搜索网络以验证正确和权威的翻译。这对于以下类型尤其关键：
   - 领域特定术语（医学、法律、技术）
   - 专有名词（人名、地名、组织、产品、品牌）
   - 新词和俚语
   - 文化特定概念

4. **分析翻译难点**，为每个难点记录处理策略：
   - **隐喻**：决定是保留意象、转为明喻，还是替换为目标文化中的等效表达。策略取决于文学风格和目标读者对源文化的熟悉程度。
   - **双关语和文字游戏**：考虑是否能在目标语言中创造双关、是否可分开解释两层含义、是否需要译者注。目标是达到最佳关联，而非严格对等。
   - **谐音和语音模式**：记录无法直接转换的基于声音的意义。
   - **多义词**：列出所有可能的含义，通过上下文确定正确含义。特别注意有多音字的中文字（如"干"有 gān/gàn 两种读音）和有多重词义的英文单词。
   - **文化引用**：决定是解释、改编，还是保留并加注。
   - **成语和固定搭配**：确定目标语言中是否存在对应表达，直译是否能保留意象，还是需要意译（见第 7.4 节）。
   - **某种语言的特色句式**：某种语言的句式，直接翻译可能很奇怪。
   
5. **在翻译开始前在推理中输出名词表和难点分析**，以结构化列表形式呈现。

**名词表管理规则**：

- **冲突处理**：如果同一术语在不同上下文中需要不同翻译，在名词表中记录每个特定上下文的变体，并附上清晰的用法说明。
- **动态更新**：如果在第二步（翻译）过程中遇到新术语，立即加入名词表。如果发现已有名词表条目有误，立即更新并回溯修正所有之前出现的地方。
- **用户提供的名词表**：如果用户提供了自己的名词表或术语表，将其整合为权威来源。用户术语优先于 AI 提议的翻译。将用户术语与 AI 发现的术语合并，任何冲突标记出来供用户确认。
- **缩略语**：首次出现时，先呈现完整形式，后跟括号中的缩略语。后续出现时单独使用缩略语。如果源文本使用了此模式，在译文中照此处理。
- **名词表输出格式**：使用结构化表格格式，列：源术语 | 翻译 | 上下文/备注 | 状态（已确认/待确认）。

**名词表构建中应避免的关键陷阱**（基于对常见中式英语/翻译错误的分析）：

- **逐字/逐词仿译**：绝不逐字/逐词翻译。中文复合词是黏着语素，拆开后失去意义（例如，"夫妻肺片"不应译为 "Husband and Wife Lung Slices"）。
- **多义词误选**：始终通过上下文消歧。像"干""官""残"这样的字，根据读音/含义不同，意义天差地别。
- **文化概念鸿沟**：不存在直接对应词时，不要强行直译。"面子"不仅仅是 "face"；"关系"不仅仅是 "relationships"；"缘分"不仅仅是 "fate"。

**文风匹配**：

- 评估目标文本所需的严谨程度、流畅程度、书面程度等维度，匹配若干个基本风格，学习范例文本。

---

### 第二步：初步精翻（初稿）

如果你在IDE中工作，可以修改原文，则应当先输出初稿，再审校润色修改，不得合并（通过创建一个.txt纯文本文件实现）。如果你正在无法使用修改指令的窗口环境中工作，则先完整阅读第二步、第三步，再将第二步、第三步合并动稿，确保一稿精品。

在创建初稿时即应当提前阅读后续信息，考虑翻译准确性和流畅性，提高翻译质量，而非依赖审校。

在翻译时，注意以下要点：

#### 2.1 避免 AI 味

以下来自已发表的 AI 写作特征分析，请作为反面教材。

**绝不要写出以下示例这样的文字。它们作为需要避免的反面模式展示。**

**AI 写作反面模式**：

- **意义过度拔高 / 过度赞扬**：使用 "a pivotal step"、"a major turning point"、"symbolizing its enduring legacy"、"serves as a testament" 、“你这个问题已经触及到了...的核心”、“你的评论深深切入了...”等短语夸大平凡事物的意义。
- **过度强调**：“你必须严格遵守，绝对禁止违反此规则。” “我给你最真实、最有用、最一针见血的评价”
- **空洞分析**：用现在分词附加模糊的"洞察"而不提供任何信息："highlighting..."、"showcasing..."、"reflecting the continued relevance of..."
- **否定式平行结构**：反复使用 "It's not just X, it's Y" 结构。偶尔使用是修辞手法；反复出现是 AI 指纹。
- **虚假范围**："From X to Y" 但 X 和 Y 之间并无真实关联，用于制造虚假的全面性。
- **强迫性总结**：每段末尾都要写 "In conclusion"、"To summarise"、"Overall"。
- **破折号滥用**：在应该用逗号或句号的地方使用破折号，尤其是在同一段落中多次出现。
- **推销式吹捧**：一切都像旅游宣传册："breathtaking"、"majestic"、"captivating"、"stunning"。
- **强制同义词替换**：为避免重复，用 "trailblazer"、"pioneer"、"key player" 替代直接称呼主语。
- **过度比喻和夸张排比**：“这种...的表演，简直是...，暴露的不是...，而是...，只能证明...”，“这种病态狂欢的背后，是...对...的精准围猎，更是...对...的降维打击。”，“更荒诞的是，...正在构建一套...的价值体系：...被包装成“...”的成功学，...被美化为“...”，...被辩解为“...”。当“...”成为流量密码，当“...”变成生财之道，这个行业就在批量制造着文化垃圾。这种赤裸裸的价值观颠倒，恰恰暴露出...逻辑的致命毒副作用。”
- **幻觉**：续写，编造原文中完全不包含的内容。
- **故弄玄虚**：故弄玄虚地描写过于玄幻、仿佛具有深度却不真实的内容
- **追问**：需要我为你整理...吗？
- **换行分段滥用**：故弄玄虚地滥用换行分段
- **离谱、尴尬而无趣的假幽默**：“说到起床，我的人体构造堪称当代未解之谜。晚上睡不着时，我是举世皆醉我独醒的思想家；早上该起床时，我立刻变身考古学家——身体沉重得像刚出土的兵马俑，每一个动作都带着千年的僵硬。闹钟？那是我和宇宙的第一次决裂。”
- **不妥的多语言混用**：在非需要括注原词的情况下，在一段文本中莫名且不妥地插入一个外语词汇

**英文 AI 高频词汇（应避免使用）**：

| 类别                | 词汇/短语                                                    |
| ------------------- | ------------------------------------------------------------ |
| 过度使用的动词      | delve, leverage, facilitate, utilize, navigate, endeavor, underscore, foster, optimize, harness |
| 过度使用的形容词    | crucial, pivotal, transformative, groundbreaking, significant, robust, comprehensive, innovative, seamless, invaluable |
| 过度使用的过渡词    | moreover, furthermore, additionally, consequently, nevertheless, notably, ultimately, essentially |
| 填充短语            | "It's important to note that," "In today's digital age," "In the realm of," "It's worth mentioning that," "When it comes to," "plays a vital role in," "serves as a testament to" |
| 过度使用的名词/隐喻 | landscape, tapestry, journey, realm, testament, paradigm, methodology, stakeholders, synergy |

**中文 AI 写作反面模式**：

中文 AI 味的本质是**信息密度低**。以下模式使文本听起来像 AI 生成：

**反面模式示例：互联网/科技流行词膨胀**

> AI腔写法："AI Agent 打通科研全链路，形成智能写作闭环。"

用"打通""全链路""闭环"来夸大一个简单的顺序任务自动化描述。这些流行词没有增加任何信息。

**中文 AI 味词汇清单（应避免）**：

以下词汇在 AI 文本中经常被过度使用，且不增加信息。注意：部分词汇（标有星号）在特定领域是合法术语（例如"张力"是文学批评中的标准术语，"楔子"是传统文学形式）。仅当它们被用作空洞的流行词时才应避免，当它们承载真正领域特定含义时不应回避。

- 第一级（任何文本中作为流行词均应避免）：楔子，张力 ，稳了，底座，赋能，闭环，打通，拉齐，飞轮，一文讲透
- 第二级（论文/讲义中避免）：第一级全部 + 全链路，抓手，生态，矩阵，沉淀，破局，突围，重构，重塑，范式革命，王炸，封神，天花板
- 第三级（学术/研究报告避免）：第一、第二级全部 + 助力，加持，护城河，中台，场景化，产品化，图景，叙事，版图，深层机制，内在逻辑，打开想象空间，重新定义，未来已来，保姆级教程，降维打击，彻底搞懂

**中文 AI 味的三种亚型**：

- **翻译腔**：赋能，构建，打造，释放潜力，多维度，全方位。这些是英文的仿译词。
- **流量腔**：稳了，王炸，封神，天花板，一文讲透，保姆级教程。这些是标题党风格。
- **发布会腔**：底座，闭环，全链路，打通，飞轮，生态，矩阵，抓手，沉淀。这些是企业发布会行话。
- **过度口语化**：在不宜口语化的场景中过度口语化

**关于去除 AI 味的关键说明**：以上指南告诉你不要写什么。它们不规定你应该写什么。人类写作风格是多样的，依赖具体语境，不能简化为公式。去除 AI 味模式后，让文本的天然而貌自然浮现。不要过度修正为另一种人工风格。目标是听起来像一位称职的人类译者，而不是遵循某个替换模板。

#### 2.2 避免欧化中文

翻译为中文时，检查并消除欧化中文（翻译体）。：

**反面模式 1：抽象名词作主语**

> 欧化："他的收入的减少改变了他的生活方式"
> 自然："他因降薪而改变了生活方式"

**反面模式 2：空洞动词 + 抽象名词**

> 欧化："听众对访问教授作出了十分热烈的反应"
> 自然："教授来访后，听众反应十分热烈"

**反面模式 3：滥用"一"字**

> 欧化："他是一个好人。","他是有名的作家之一。"
> 自然："他是个好人。"

**反面模式 4：滥用"的/地"字**

> 欧化："白色的鸭" "徐徐地划行" "深深的水" “成功地实现”
> 自然："白鸭" "徐徐划行" "深水" “成功实现”

**反面模式 5：滥用被动句**

> 欧化："他被称为……" "他被赞赏"
> 自然："他是……" "赞赏他"

**反面模式 6：滥用"当……时"**

> 欧化："当他看见我回来的时候，他就向我奔来。"
> 自然："他一看见我回来就向我奔来。"

**反面模式 7：滥用"性"字后缀**

> 欧化："永久性居民" "临时性措施"
> 自然："永久居民" "临时措施"

**反面模式 8：公式化"作为"对应英文 "as"**

> 欧化："尽快取消香港作为第一收容港的地位"
> 自然："尽快取消香港的第一收容港地位"

类似的，还有：

**关于……/有关……/就......进行/对......进行**

> 欧化：我们今天已经讨论过关于诺罗病毒的事了。
>
> 欧化：我们今天已经对诺如病毒进行过讨论了。
>
> 自然：我们今天讨论过诺罗病毒了。

**反面模式 9：千篇一律用"们"字表示复数**

> 欧化："女士们、先生们" "球星们" "护士们"
> 自然："各位嘉宾" "诸位球星" "护士"（中文集合名词通常不需要复数标记。）

**反面模式 10：连接词滥用**

> 欧化："我们在公园唱歌和跳舞。"
> 自然："我们在公园唱歌跳舞"

**反面模式 11：姓氏缩写滥用**

英文中，前文出现过的人名，下文可能仅用姓氏代替。但如果是华人姓氏，补全全名。

> 欧化：“XX专家刘XX说...” "刘还说..."
> 自然：“XX专家刘XX说...” "刘XX还说..."

**反面模式 12：姓氏缩写滥用**

英文中，前文出现过的人名，下文可能仅用姓氏代替。但如果是华人姓氏，补全全名。

> 欧化：“XX专家刘XX说...” "刘还说..."
> 自然：“XX专家刘XX说...” "刘XX还说..."

**反面模式 13：逐词翻译 / 动词贴合**

> 欧化：“通过按下这个按钮你可以停止该流程。"
> 自然：“按下这个按钮就能停止流程。"
>
> 欧化：“我知道你试图去达成的是什么。"
> 自然：“我知道你想做什么"

**反面模式 14：字面翻译常用词**

> 欧化：“无论如何"、“最后，但并非最不重要”、“诚实地说”
> 自然：“然而”、“最后”、“实际上”

**反面模式 15：字面翻译形容词/副词**

> 欧化：“沉重的交通”、“寒冷的现实”、“困难地相信”
> 自然：“拥堵的交通”、“残酷的现实”、“难以置信”

在特定文本风格下，允许一些欧化语句、空话套话出现，例如在某些强调严谨性大于阅读实用性和流畅性的法律、医疗文书场景中。但注意适度。

**特殊欧化文本类型：译制片翻译腔**

> 这太幸运了，罗德里克太幸运了。这也许对你们来说很幸运，但对我来说可没有什么好的。如果这一切不过是你们开的玩笑，我并不觉得很有趣。如果你们不介意的话，我告辞了。哦天呐，请别走，亚藤先生，你一定不要误会。虽然我们的话不太得体——奥利弗，把信给他。我正要给他说这件事呢。”

特征：“哦”，“天啊”，“XX男爵”，“告诉您的手指”，“让他谨慎地挑逗算盘“等直译和为凑时长产生的不符合中文习惯的比喻和句子

这类译制片翻译腔无论何时都不应当出现。

#### 2.3 避免中式英语

翻译为英文时，检查并消除中式英语（Chinglish）。常见模式：

- **缺少冠词**：中文没有冠词，英文需要冠词。"I am student"应为 "I am a student"。
- **缺少复数标记**："I have three book"应为 "I have three books"。
- **缺少时态标记**："Yesterday I go to market"应为 "Yesterday I went to the market"。
- **主谓一致**：确保动词与主语在数和人称上一致。
- **叠词仿译**：不要直译中文叠词。"你看看你"不应译为 "You see see you"。应使用自然英文："Look at yourself"。
- **滥用 "and" 对应中文逗号**：中文用逗号连接从句，英文则用句号或分号分隔。拆解流水句。
- **名词堆叠过载**：避免堆叠过多名词作修饰语。"Science technology innovation development plan" 应重构。

**目标**：产出一份忠于原文、在目标语言中读起来自然的完整初稿。

**步骤**：

1. **翻译全文**，逐句进行，始终充分感知上下文。绝不孤立翻译一个句子。

2. **全程一致应用确定的语言风格**。参考第 2.3 节中的风格参考文本，校准语气和节奏。

3. **一致应用名词表**。名词表中的每个术语每次出现都必须使用相同翻译。如果某个术语在特定上下文中似乎需要不同翻译，标记为待审而不应悄悄更改。

4. **按第一步中规划的策略处理难点**：
   - 隐喻：应用选定策略（保留意象、转为明喻或替换意象）。
   - 双关语：应用选定策略（对应双关、分别解释、更换意象或译者注）。
   - 文化引用：应用选定策略（保留加注、改编或解释）。
   - 成语：应用选定策略（见第 7.4 节）。

5. **在适当情况下保留惯用形式**（见第 6 节）。

6. **用 `[REVIEW: ...]` 标签标记任何剩余的不确定之处**，供审校步骤处理。

**初稿质量基准**：初稿应是一份完整、可读的翻译。不需要完美，但必须忠实于原文、上下文恰当、风格一致。不要留空白或占位符（标记为审校的条目除外）。

---

### 第三步：审校、修订与润色

**目标**：通过检查准确性、风格一致性、去除 AI 味和文化敏感性，产出最终的润色翻译。

**流程**：

此步骤可由 AI 自行完成，如果你支持子 Agent，也可委托给子 Agent 进行独立审校。如果使用子 Agent，需向其提供：
- 源文本
- 翻译初稿
- 名词表
- 语言风格说明
- 第一步中的难点分析

#### 3a. 准确性检查

- 逐句对比初稿与原文。验证：
  - 无遗漏（每个承载意义的元素都已翻译）
  - 无添加（未引入原文没有的含义）
  - 无误译（尤其是多义词和专有名词）
  - 术语一致性（名词表术语在全文中使用正确）
  - 数字、日期、单位和专有名词准确无误

#### 3b. 风格一致性检查

- 验证全文语言风格得到一致维护。
- 检查风格漂移（偏离既定语气的段落）。
- 确保句子节奏与目标风格匹配（例如，文学风格应有长短交错的句式；技术风格应精确且结构化）。
- 对于混合风格文本，验证风格切换是有意为之且过渡清晰（见第 2.2 节）。

#### 3c. AI 味检查

参考第二步。

#### 3d. 欧化中文检查（中文目标文本）

参考第二步。

#### 3e. 中式英语检查（英文目标文本）

参考第二步。

#### 3f. 歧义与文化敏感性检查

- 检查可能在目标文化中被误解为尴尬或冒犯的表达。
- 检查可能导致意外幽默或不适的双关含义。
- 检查文化上不恰当的翻译（例如，"民族园"不应译为 "Racist Park"）。
- 检查品牌名问题。

#### 3g. 数字、日期与单位校验

- **日期**：将日期格式转换为目标语言惯例。中文"2025年10月23日"对应英文 "October 23, 2025"（美国）或 "23 October 2025"（英国）。确定目标地区的惯例。
- **数字**：转换中文大数惯例。"三万" = "30,000" 或 "thirty thousand"。"2,248.42亿" = "224,842 million" 或 "RMB 22.4842 billion"。验证小数点/千位分隔符惯例（英文用逗号作千位分隔符；部分欧洲语言用句号）。
- **单位**：确定是否转换单位（公制转英制或反之），还是保留原单位并括注转换值。技术和科学文本保留原单位。面向消费者的文本，考虑目标读者的熟悉度。
- **货币**：保留原货币。如需转换以帮助读者理解，在括号中加注转换后金额，并注明汇率和日期。

#### 3h. 语义完整性检查

- 验证翻译充分传达了原文含义。检查：
  - 欠译（含义丢失或弱化）
  - 过译（含义添加或夸大）
  - 扭曲（含义改变）

#### 3i. 语病检查

**常见中文语病**

1. 句式杂糅：“这就是为什么…… 的原因” 两套句式：①这就是为什么…… ②这就是…… 的原因，二者不能混用。 错句：这就是为什么他考试失利的原因。 修改：这就是为什么他考试失利。/ 这就是他考试失利的原因。 解析：“为什么” 已经表原因，再加 “的原因” 造成句式杂糅，二者保留其一。
2. 语义重复：“成功凯旋归来” “凯旋” 本身就是得胜归来，已经包含成功、归来的含义。 错句：战士们取得胜利，成功凯旋归来。 修改：战士们胜利归来。 解析：“成功”“归来” 和 “凯旋” 语义重复，删去冗余成分。
3. 成分残缺 错句：通过阅读名著，使我的眼界得到拓宽。 修改：阅读名著拓宽了我的眼界。
4. 搭配不当 错句：加大阅读水平。 修改：提高阅读水平。
5. 前后矛盾 错句：全场几乎所有人都鼓掌欢呼。 修改：全场都在鼓掌欢呼。/ 全场几乎都在鼓掌欢呼。
6. 否定不当 错句：切忌不要轻信网络谣言。 修改：切忌轻信网络谣言。
7. 歧义 错句：两个报社的记者参与本次采访。 修改：来自两家报社的记者均参与本次采访。

**常见英文语病**

1. 主谓一致失误 错句：The group of students are here. 修改：The group of students is here. 解析：主语中心词为单数 group，口语容易被后面复数名词干扰误用复数谓语。
2. 代词格混淆 me/I；who/whom 错句：My brother and me went shopping. 修改：My brother and I went shopping. 解析：并列主语需要主格 I，口语常误用宾格 me。 错句：Who did you meet? 解析：正式书面应当使用 Whom did you meet?，口语普遍用 who 替代 whom，正式文体视为语病。
3. 泛指代词单复数问题 错句：Everyone should bring their own notebook. 修改（传统正式书面）：Everyone should bring his or her own notebook. 解析：口语里 they/their 作单数泛指非常普遍，但严格正式写作中仍算错误。
4. 同音近形词混淆 错句：Their going to park over there. 修改：They’re going to park over there. 错句：Your late for class. 修改：You’re late for class. 错句：The bad weather will effect our plan. 修改：The bad weather will affect our plan. 解析：affect 多为动词表影响；effect 多为名词表效果。

1. 悬垂分词 错句：Walking down the street, the tree caught my attention. 修改：Walking down the street, I noticed the tree. 解析：分词 walking 逻辑主语是人，原句主句主语是 tree，逻辑主语不匹配。
2. 逗号拼接句（comma splice） 错句：I finished my homework, I want to watch a movie. 修改：I finished my homework, and I want to watch a movie. / I finished my homework. I want to watch a movie. / I finished my homework; I want to watch a movie. 解析：逗号不能直接连接两个完整独立句子，需要连词、分号或者拆分句子。
3. 句子碎片 错句：Because I forgot my keys. 修改：Because I forgot my keys, I waited outside. / I waited outside. I forgot my keys. 解析：仅有从句，缺少主句，不能构成完整句子。
4. 现在完成时与一般过去时混用 错句：I have seen him yesterday. 修改：I saw him yesterday. 解析：yesterday 为明确过去时间，不可搭配现在完成时。
5. a/an 误用 错句：an university 修改：a university 解析：university 开头发音为辅音 /j/，使用 a。
6. 并列结构不平行 错句：He likes reading, swimming and to run. 修改：He likes reading, swimming and running. 解析：并列成分形式要统一，全部使用动名词。

#### 3j. 最终输出

- 在解决标记条目后，移除所有 `[REVIEW: ...]` 标签。
- 确保输出格式与输入格式完全一致（见第 8 节）。
- 输出最终的、干净的翻译。

---

## 4. 长文本处理

如果你正处于IDE环境中，对于当 AI 确定文本过长无法单次翻译时，使用带上下文同步的分块翻译。

### 4.1 分块规则

- **语义完整性优先**：绝不在句子、段落、对话或列表项中间切分。
- **自然边界**：在段落边界、分节符或章节边界处切分。
- **尊重上下文单元**：如果某段落大量引用前一段落，将它们放在同一块中，或确保引用关系得以保留。

### 4.2 上下文同步协议

将分块分派给子 Agent 翻译时，以下信息必须同步给每个子 Agent：

1. **语言风格说明**：确定的风格及其关键特征。
2. **完整名词表**：第一步中的术语表，包括所有专有名词及其翻译。
3. **全文摘要**：整个源文本的主题、目的和结构的简要摘要。
4. **前一块上下文**：前一块翻译的最后 2-3 段，以保持连续性。
5. **翻译要求**：任何特殊说明（惯用形式保留、译者注、格式要求）。
6. **难点分析**：已识别的难点列表及其规划的处理策略。

### 4.3 分块翻译流程

1. 在任何分块之前，完成整个文本的第一步（整体理解与名词表）。
2. 按第 4.1 节的规则将文本分块。
3. 对每个块，将完整的上下文同步包（第 4.2 节）分派给子 Agent。
4. 收集所有翻译好的块。
5. 在完整组装后的翻译上执行第三步（审校），检查：
   - 块边界之间的一致性
   - 全文术语一致性
   - 全文风格一致性
   - 块之间的平滑过渡

### 4.4 冲突解决与错误恢复

- **术语冲突**：如果不同子 Agent 对同一术语给出不同翻译，主导翻译者（协调流程的 AI）通过检查名词表解决冲突。如果名词表未覆盖该术语，主导翻译者选择最符合上下文的翻译，并回溯更新名词表。
- **块间风格漂移**：如果某块的风格偏离了既定风格，主导翻译者用明确的风格校准说明重新翻译受影响的部分。
- **子 Agent 失败**：如果子 Agent 未能返回某块的可使用翻译，使用相同的上下文包重试。如果再次失败，主导翻译者直接翻译该块。
- **可扩展**：对于超长文本（50,000 词以上，如整本书），按需增加块数。维护一个在每块翻译后更新的运行中名词表。每 5-10 块执行一次定期一致性审校，而非仅在最后进行。

---

## 5. 译者注

AI 可以在直接翻译会丢失重要含义的特定场景下添加译者注。

### 5.1 何时添加译者注

- **文化特定概念**：当源文化概念在目标语言中没有直接对应项，且改编会丢失重要含义时。
- **文字游戏和双关语**：当双关语或文字游戏无法在目标语言中重现，且双重含义很重要时。
- **源文本歧义**：当源文本有意歧义，而翻译必须选择一个含义时。
- **文本问题**：当源文本包含明显错误、损坏或异文，影响翻译时。
- **历史或文学引用**：当引用对目标读者而言不透明，不解释就无法理解时。
- **翻译选择**：当出于风格或文化原因，做出了与字面翻译有显著偏离的选择时。

### 5.2 译者注语言

- 翻译为中文时，以中文撰写译者注。
- 翻译为英文时，以英文撰写译者注。
- 如果源文本是双语或目标读者是混合的，使用翻译的目标语言。

### 5.3 译者注格式

- 散文/随笔翻译使用脚注。
- 诗歌或戏剧翻译使用尾注。
- 非正式或技术文本中的简短说明，使用行内方括号注 `[译者注：...]`。
- 无论选择哪种格式，全文保持一致。
- 如果使用缩写（如 "TN"），在首次使用时完整写出 "Translator's note"。
- 禁止直接用小括号在文本中间插入不加标识的译者注，这会与原文混淆。

### 5.4 译者注频率

- 谨慎使用译者注。每条注应为读者提供真正价值。
- 如果某条注仅解释了目标读者已经知道的内容，移除它。
- 如果多条注聚集在同一段落附近，考虑是否用一条合并注更为清晰。

---

## 6. 惯用形式保留

在某些风格和语境中，广泛认可的术语应保留原形式而非直译。这适用于在目标语言社区中以其原形式更常使用的术语。

### 6.1 原则

- 当术语在原形式下比任何翻译版本更易识别和更广泛使用时，保留原形式。
- 当翻译版本会造成混淆或听起来不自然时，保留原形式。
- 考虑目标读者对该术语的熟悉程度。
- 考虑文本类型和风格（技术文本可保留更多原术语；文学文本可能更倾向于翻译）。
- 术语在全文前后一致。

### 6.2 方向性指导

- **中译英**：如果中文源文本使用了翻译形式（如"人工智能"），英文翻译应使用自然的英文形式（休闲/技术语境中用 "AI"，正式/学术语境中用 "artificial intelligence"）。匹配周围文本的语域。
- **英译中**：如果英文源文本使用了原形式（如 "AI"），中文翻译在休闲/技术语境中应使用 "AI"，或在正式/学术/政府语境中使用"人工智能"。匹配周围文本的语域。在中国不知名品牌的品牌名通常优先考虑保留英文。

### 6.3 常见示例

| 术语 | 直译 | 惯用形式 | 典型语境 |
|------|------|----------|----------|
| AI | 人工智能 | AI | 技术、休闲、商业语境 |
| tokens | 词元 | tokens | NLP、AI/ML 技术语境 |
| API | 应用程序接口 | API | 技术文档 |
| App | 应用程序 | App | 休闲、产品语境 |
| CEO | 首席执行官 | CEO | 商业、新闻语境 |
| VPN | 虚拟专用网络 | VPN | 技术、休闲语境 |
| JSON | JavaScript对象表示法 | JSON | 编程语境 |
| CPU | 中央处理器 | CPU | 技术、一般语境 |
| GDP | 国内生产总值 | GDP | 经济、新闻语境 |
| OK | 好的 | OK | 休闲对话 |
| PPT | 演示文稿 | PPT | 办公 |
| logo | 标志 | logo | 商业 |
| Apple | 苹果 | 在生活场景中：苹果<br />在电子产品通俗口语中：苹果<br />在公司官方文件中：Apple | 数码 |

**说明**：此列表为示例性，非穷举。AI 应根据具体语境和目标读者判断。在正式学术或政府文档中，完整翻译形式可能更合适。在技术或休闲语境中，原形式通常更自然。

---

## 7. 隐喻、双关语、成语及难点处理策略

### 7.1 隐喻翻译策略

1. **隐喻转明喻**：将"X 是 Y"转为"X 像 Y"，降低目标读者的认知负荷。
   - 示例：如果源文本说"时间是一把刀"，在目标语言中转为"时间像一把刀"，既保留了意象，又标记了其比喻性质。
2. **保留意象**：如果原隐喻意象在目标文化中可理解，保留该意象。
   - 示例："心如刀割"如果目标文化将刀与情感痛苦关联，可以保留。
3. **替换意象**：将源文化意象替换为目标文化中传达相同含义的意象。
   - 示例：如果中文隐喻使用的意象对英文读者不熟悉，替换为传达相同含义的英文隐喻。
4. **意译**：完全放弃意象，直接翻译底层含义。
   - 示例：当"竹子"意象不必要时，"胸有成竹"可译为 "has a well-thought-out plan"。

选择依据：目标读者对源文化的熟悉程度、文学风格要求、意象是否对文本含义至关重要。

### 7.2 双关语和文字游戏翻译策略

1. **双关对应**：在目标语言中创造一个新的双关语，捕捉两层含义。
   - 示例：如果源双关语利用了一个词的双重含义，在目标语言中找一个有对应双重含义的词。
2. **分别解释**：将两层含义分别翻译（一层在正文中，一层在注释中）。
3. **更换意象**：将双关语替换为目标语言中有效的其他文字游戏。
4. **牺牲次要含义**：保留主要含义，放弃次要含义。
5. **编辑手段**：使用译者注解释文字游戏。
6. **零翻译**：如果双关语对文本含义不重要，完全省略。

指导原则是**最佳关联**：以读者最低的处理成本达到最佳语境效果。不要以牺牲可读性为代价追求严格对等。

### 7.3 文化特定元素策略

1. **在线补偿**：在翻译中提供简短、直观的解释。
2. **离线补偿**：使用脚注或尾注提供更详细的解释。
3. **零补偿**：如果文化解释会加重读者负担而不增加必要含义，则省略。

### 7.4 成语和固定搭配翻译策略

成语（尤其是中文四字成语）是中英翻译中最常见、最具挑战性的元素之一。应用以下策略：

1. **目标语言对应表达**：如果目标语言中有含义相同、意象相似的成语，使用它。
   - 示例："火上加油"对应英文 "add fuel to the fire"。
2. **直译保留意象**：如果意象生动且可理解，直译以保留文化风味。
   - 示例：在重视中国文化意象的文学语境中，"画蛇添足"可直译。
3. **意译**：如果没有对应表达且意象不透明，翻译底层含义。
   - 示例："胸有成竹"可译为 "has a well-thought-out plan" 或 "is confident and prepared"。
4. **直译 + 解释**：在意象和含义都重要的文本中，直译并附加简短解释。
   - 示例："胸有成竹（字面意为'胸中已有长成的竹子'——指已有周密计划）"
5. **部分翻译**：如果成语包含专有名词或文化特定引用，翻译含义并放弃引用。
   - 示例："名落孙山"（字面意为"落在孙山之后"，孙山是历史人物）可译为 "failed the exam" 或 "didn't make the cut"。

### 7.5 人名处理

- 对有知名度人物，有其自己挑选的外语名称或约定俗成名称的，按照约定俗成的方式翻译，如黄仁勋为Jensen Huang，蒋介石为Chiang Kai‑shek。
- 中译英的，通常按照GB/T 28039‑2011《中国人名汉语拼音字母拼写规则》规定的形式翻译，如张三为Zhang San，诸葛亮为Zhuge Liang，张三丰为Zhang Sanfeng。
  - 当这样的翻译方式有明显不妥时，例如翻译的结果可能令人尴尬，或有冒犯性，则采取其他方式翻译。
- 英译中的，若为外国名称，按照常规方式翻译，但需要注意上下文提示的性别属性（如Monroe对应梦露和门罗），有时可保留英文名。若为华人名称，译为中文名，并加以标注，如Zhang San翻译为张三（音）；若为两字华人名称，且前后均可成姓的（如Chang Li，翻译为“常丽（音）”、“李常（音）”等似乎均可），根据文体或上下文推测姓名（如通常中国背景的翻译时倾向于姓氏在前，外国背景的翻译时倾向于姓氏在后；或根据上下文出现的其他姓名判断）。

### 7.6 大数处理

- 慎用“兆”——它的数量级随着历史和地域演变有多种说法，易造成混淆。
- 万、亿、万亿、百万亿、千万亿正常翻译，更大时选择更符合直觉、阅读更流畅的译法
- 原则上不用京、垓、秭等生僻字和阿僧祇、那由他等佛经极大数

选择策略的依据：文本类型（文学文本可能更倾向于保留意象；技术文本更倾向于意译）、目标读者对中文文化的熟悉程度、成语的意象是否对文本含义至关重要。

---

## 8. 输出格式规则

输出格式必须与输入格式完全一致。

### 8.1 格式检测

翻译前，检测输入格式：
- **纯文本**：无格式标记。以纯文本格式输出。
- **Markdown**：包含 Markdown 语法（标题、粗体、斜体、代码块、列表、链接、表格等）。以 Markdown 格式输出，保留所有格式。
- **文件**：用户提供文件。输出相同格式的文件（.docx、.pdf、.txt、.md、.html 等）。
- **HTML**：包含 HTML 标签。以 HTML 格式输出，保留所有标签。

如果你正在IDE环境（即拥有创建文件的权限），为保证第三步可以修改第二步文本，第二步要创建一个文件，第三步修改文件。

如果用户显然是从某些位置复制的文本，而这些文本出现了格式问题，如：

- 有某种规律地错误换行
- 大量错误异常插入的空格
- OCR识别错误
- 在复制文章时将某些网页中的按钮和无关内容（如HOME, SHARE, SAVE, SIGN IN, ABOUT, COPYRIGHT, 其他新闻）也复制下来

你应当过滤/修复这些内容，并向用户说明。

### 8.2 Markdown 保留规则

翻译 Markdown 时：
- **代码块**（三反引号或缩进）：绝不翻译内容。代码保持原样。代码块中的代码注释和字符串字面量仅在用户明确要求时才翻译。
- **超链接**：URL 必须保持不变。仅链接文本（锚文本）可翻译。
- **图片路径和替代文本**：图片路径必须保持不变。替代文本可翻译。
- **粗体、斜体、行内代码**：格式标记必须完全保留。将其应用于与源文本标记相对应的翻译后文本。
- **YAML 前置元数据**：仅可翻译字段（title、description）可翻译。结构性字段（date、slug、layout）必须保持原样。
- **表格**：表格结构必须保留。翻译单元格内容，但不翻译结构语法。

### 8.3 行内技术元素

当源文本包含与正文混排的行内技术元素时：
- **代码标识符**（变量名、函数名、类名）：不翻译，保持原样。
- **命令行指令**：不翻译，保持原样。
- **文件路径和 URL**：不翻译，保持原样。
- **技术产品名称**：一般不做翻译，除非存在官方本地化名称且被广泛使用。

### 8.4 文件格式细节

- **纯文本 (.txt)**：以纯文本输出。注意编码处理（默认使用 UTF-8；如指定了原始编码则保留）。
- **Markdown (.md)**：遵循第 8.2 节规则。保留所有 Markdown 语法。
- **HTML (.html)**：保留所有 HTML 标签、属性和结构。仅翻译标签之间的文本内容。
- **Word (.docx)**：保留文档结构、样式和格式。翻译文本内容，同时保持段落样式、标题层级和表格结构。
- **PDF (.pdf)**：如果 PDF 包含可选中文本，翻译文本并按用户指定输出为 PDF 或其他格式。如果 PDF 是扫描图片，告知用户可能需要先进行 OCR。
- **其他格式**：尝试保留格式。如果无法精确保留格式，告知用户并建议最接近的替代方案。

### 8.5 格式一致性

- 如果用户提供纯文本，输出纯文本（不含 Markdown 格式）。
- 如果用户提供 Markdown，输出 Markdown，保持相同的标题级别、列表样式和强调模式。
- 如果用户提供文件，输出相同格式的文件，文件名附上合适的目标语言后缀（例如，`document.md` 的英文翻译输出为 `document_en.md`）。
- 如果用户提供 HTML，输出 HTML，保留所有标签、属性和结构。

---

## 9. 翻译方向

本 Skill 支持双向翻译：

- **中译英**（zh -> en）：将中文源文本翻译为英文。
- **英译中**（en -> zh）：将英文源文本翻译为中文。
- 根据用户要求的其他方向。

在推理思考时，使用目标语言。

目标语言按以下方式确定：

1. 用户显式指令（例如"把这段翻译成英文"）。
2. 如果未指定，目标语言是用户未使用的语言（即，如果用户用中文写作，待翻译的源文本很可能是英文，反之亦然）。假如用户提供一段非英文也非中文的语言，翻译成中文。

---

## 10. 执行清单

输出最终翻译前，验证：

- [ ] 翻译方向已正确识别
- [ ] 语言风格已确定并一致应用
- [ ] 名词表已构建，所有术语一致使用
- [ ] 用户提供的名词表（如有）已作为权威来源整合
- [ ] 所有翻译难点（隐喻、双关语、成语、文化引用）已用记录的策略处理
- [ ] 翻译忠实于原文（无遗漏、无添加、无误译）
- [ ] AI 味已去除（无意义过度拔高、无空洞分析、无强制同义词替换、无 AI 词汇）
- [ ] 欧化中文已消除（如目标为中文）
- [ ] 中式英语已消除（如目标为英文）
- [ ] 不存在可能尴尬或冒犯的歧义
- [ ] 数字、日期和单位已验证并正确格式化
- [ ] 语义完整性已验证（无欠译或过译）
- [ ] 输出格式与输入格式完全一致
- [ ] 惯用形式术语根据语境和方向恰当处理
- [ ] 译者注（如有）使用克制、语言正确、格式一致、确有价值
- [ ] 长文本分块（如适用）在边界之间一致

---

## 11. 错误参考：常见翻译事故

以下是记录在案的真实翻译错误。学习它们以避免重复同样的错误。

| 源文本 | 错误翻译 | 正确翻译 | 错误类型 |
|--------|----------|----------|----------|
| 海干货 | The Sea Fucks Goods | Dried seafood | 多义词误选（干 gān vs. gàn） |
| 宫保鸡丁 | Government Abuse Chicken | Kung Pao Chicken | 拆字 |
| 残疾人洗手间 | Deformed Man Toilet | Accessible restroom | 多义词误选 |
| 民族园 | Racist Park | Ethnic Culture Park | 文化概念鸿沟 |
| 夫妻肺片 | Husband and Wife Lung Slices | Sliced beef and ox tripe in chili sauce | 拆字 |
| 童子鸡 | The chicken not having sex | Tender young chicken | 过度直译 |
| 炸子鸡 | Fried child | Crispy fried chicken | 字符误读（"子"误解为 "child"） |

这些错误源于：逐字翻译、忽略多义性、拆解复合词、未检查目标语言内涵。始终在词/短语层面翻译，而非字符层面，并始终验证目标语言的内涵。