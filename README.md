# BiPaR (Including testing set)

> General Description

This repository contains datasets for EMNLP-IJCNLP 2019 paper "BiPaR: A Bilingual Parallel Dataset for Multilingual
and Cross-lingual Reading Comprehension on Novels" (Yimin Jing, Deyi Xiong and Yan Zhen). BiPaR is an extractive and manually annotated bilingual parallel 
novel-style machine reading comprehension (MRC) dataset, developed to support monolingual, multilingual 
and cross-lingual reading comprehension. 

BiPaR homepage: <https://multinlp.github.io/BiPaR/>  
Paper link: <https://arxiv.org/abs/1910.05040>

**The data format of BiPaR is the same as SQuAD, so you can process BiPaR like SQuAD.**

|  |  |  |
| :-----| :----: | :----: |
|       | English | Chinese |
| ViReader   | 49.40/62.68 | 52.87/70.22 |
| BERT_large | 42.53/56.48 |     -/-     |
| BERT_base  | 41.40/55.03 | 48.87/64.09 |
| DrQA       | 27.00/39.29 | 37.40/53.11 |

##Monolingual MRC

(P<sub>en</sub>, Q<sub>en</sub>, A<sub>en</sub>) or (P<sub>zh</sub>, Q<sub>zh</sub>, A<sub>zh</sub>). With these two
monolingual MRC forms, we can investigate the performance variation of the same MRC model trained on two different 
languages with equivalent training instances.

```sh
"context": "“Do you know what the Lingjiu Place in the Piaomiao Peak is and why the Shennong should be at its command?”“Never have I heard it before until you told me. And indeed, I didn’t know the Shennong troubling us is obeying its order ” replied the master, who thought that even as the Shennong should be at its command, then the Lingjiu Palace in the Piaomiao Peak must be very formidable. But the Piaomiao Peak never had he heard before in the numerous mountains of Yunnan. The thought loaded an even heavier rock on his troubled heart, whose eyebrows were knitted. “Then another said, ‘As maybe the Waternuts in the Wuliang Hill could rid our master of the disease, we should get them anyway, even risking our necks,’” the girl said, after eating two more seeds. “Then the first one sighed, ‘None but Madam Tianshantonglao can break the spell of Life and Death in my body. And when the spell attacks, though the herb is efficacious, merely it can relieve the intense agony, which leaves you between death and life……’ This is what they said as walking away. Have I made it clear?”",			
"id": "TRAIN_tian_long_ba_bu_34_QUERY_3_EN"
"question": "What happens when the Life and Death break out?"
"answers": [{"answer_start": 977, "text": "leaves you between death and life"}]
```

```sh
"context": "那少女道：“缥缈峰灵鹫宫是甚么玩意儿？为甚么神农帮要奉他的号令？”左子穆道：“缥缈峰灵鹫宫甚么的，还是此刻第一遭从姑娘嘴里听到。我实不知神农帮原来还是奉了别人的号令，才来跟我们为难。”想到神农帮既须奉令行事，则那缥缈峰甚么的自然厉害之极，云岭之南千山万峰，可从来没听说有一座缥缈峰，忧心更增，不由得皱起了眉头。那少女吃了两粒瓜子，说道：“那时又听得另一人说道：‘帮主身上这病根子，既然无量山中的通天草或能解得，众兄弟拚着身受千刀万剑，也要去采这通天草到手。’先一人叹了口气，说道：‘我身上这“生死符”，除了天山童姥她老人家本人，谁也无法解得。通天草虽然药性灵异，也只是在“生死符”发作之时，稍稍减轻些求生不得、求死不能的苦楚而已……’他们几个人一面说，一面走远。我说得够清楚了吗？”",
"id": "TRAIN_tian_long_ba_bu_34_QUERY_3_ZH"
"question": "“生死符”发作会怎样?"
"answers": [{"answer_start": 300, "text": "求生不得、求死不能"}]
```

## Multilingual MRC

(P<sub>en</sub>, Q<sub>en</sub>, A<sub>en</sub>, P<sub>zh</sub>, Q<sub>zh</sub>, A<sub>zh</sub>). We can build a single MRC model to handle MRC of multiple languages on BiPaR and explore
whether the alignment feature can significantly improve performance of the two languages. 

```sh
"context": "\"Why? Do you wish to encourage the people to face the possible destruction of Trisolaran civilization with equanimity?\"\"No. It's to encourage them to face the destruction of Earth civilization with equanimity. You know very well that after we publicized our policy toward the Earth civilization, there was a wave of extremely dangerous pacifism. We have only now discovered that there are many like the listener of Post 1379. We must control and eliminate these weak sentiments.\"\"Princeps, this is mainly the result of recent messages received from the Earth. Your prediction has come true: The alienated forces on Earth really are growing. They have built a new transmission site completely under their control, and have begun to send us large amounts of information about Earth civilization.I must admit that their civilization has great appeal on Trisolaris. For our people, it sounds like sacred music from Heaven. The humanism of Earth will lead many Trisolarans onto the wrong path, just as Trisolaran civilization has already become a religion on Earth, Earth civilization has this potential on Trisolaris.\"",
"id": "TRAIN_san_ti_374_QUERY_1_EN"
"question": "What is the impact of earthman's humanistic thought on the trisolaran people?"
"answers": [{"answer_start": 919, "text": "The humanism of Earth will lead many Trisolarans onto the wrong path, just as Trisolaran civilization has already become a religion on Earth, Earth civilization has this potential on Trisolaris."}]
				
"context": "“这有什么意义呢？是让人民能够坦然面对三体文明可能的毁灭吗？”“不，是让他们坦然面对地球文明的毁灭。你也知道，在我们对地球文明的基本政策公布后，激发起一些极其危险的和平主义情绪。我们现在才发现，三体世界中像1379号监听员这样的人其实是很多的，必须控制和消除这种脆弱的情绪。”“元首，这种情绪主要是由最近来自地球的新信息引起的。您的预测实现了，地球上的异己力量果然在发展，他们建立了一个完全由自己控制的发射基地开始源源不断地向我们发送大量地球文明的信息。我得承认，地球文明在三体世界是很有杀伤力的，对我们的人民来说，那是来自天堂的圣乐。地铁人的人文思想会使很多三体人走上精神歧途，三体文明在地球已经成为一种宗教，而地球文明在三体世界也有这个可能。”",
"id": "TRAIN_san_ti_374_QUERY_1_ZH"
"question": "地球人的人文思想会对三体人造成什么影响？"
"answers": [{"answer_start": 268, "text": "地铁人的人文思想会使很多三体人走上精神歧途，三体文明在地球已经成为一种宗教，而地球文明在三体世界也有这个可能。"}]	
```

## Cross-lingual MRC

The first two forms of cross-lingual MRC are (P<sub>en</sub>, Q<sub>zh</sub>, A<sub>en</sub>) or (P<sub>zh</sub>, Q<sub>en</sub>, A<sub>zh</sub>), in which we use questions in one 
language to extract answers from passages written in another language. This form is in essence similar to the early 
cross-lingual question answering (CLQA). We can use a translator to translate questions into the language of passages, 
and then treat them as a monolingual MRC.

```sh
"context": "\"Come on, fish,\" he said. But the fish did not come. Instead he lay there wallowing now in the seas and the old man pulled the skiff up-onto him. When he was even with him and had the fish's head against the bow he could not believe his size. But he untied the harpoon rope from the bitt, passed it through the fish's gills and out his jaws, made a turn around his sword then passed the rope through the other gill, made another turn around the bill and knotted the double rope and made it fast to the bitt in the bow. He cut the rope then and went astern to noose the tail. The fist had turned silver from his original purple and silver, and the strips showed the same pale violet color as his tail. They were wider than a man's hand with his fingers spread and the fish's eye looked as detached as the mirrors in a periscope or as a saint in a procession. \"It was the only way to kill him,\" the old man said. He was feeling better since the water and he knew he would not go away and his head was clear.",
"id": "TRAIN_lao_ren_yu_hai_64_QUERY_2_CROSS_QZH"
"question": "鱼已经由原来的银紫色变成什么颜色？"
"answers": [{"answer_start": 595, "text": "silver"}]
```

```sh
"context": "射击的武器五花八门，有陈旧的美式卡宾枪、捷克式机枪和三八大盖，也有崭新的制式步枪和冲锋枪——后者是在“八月社论”发表之后从军队中偷抢来的——连同那些梭标和大刀等冷兵器，构成了一部浓缩的近现代史……“四．二八”的人在前面多次玩过这个游戏，在楼顶上站出来的人，除了挥舞旗帜外，有时还用喇叭筒喊口号或向下撒传单，每次他们都能在弹雨中全身而退，为自己挣到了崇高的荣誉这次出来的女孩儿显然也相信自己还有那样的幸运她挥舞着战旗，挥动着自己燃烧的青春，敌人将在这火焰中化为灰烬，理想世界明天就会在她那沸腾的热血中诞生……她陶醉在这鲜红灿烂的梦幻中，直到被一颗步枪子弹洞穿了胸膛",
"id": "TRAIN_san_ti_1_QUERY_0_CROSS_QEN"
"question": "What were the old weapons?"
"answers": [{"answer_start": 14, "text": "美式卡宾枪、捷克式机枪和三八大盖"}]
```

The other two forms are (P<sub>en</sub>, P<sub>zh</sub>, Q<sub>zh</sub>, A<sub>zh</sub>, A<sub>en</sub>) or (P<sub>zh</sub>, P<sub>en</sub>, Q<sub>en</sub>, A<sub>en</sub>, A<sub>zh</sub>). The bilinguality of BiPaR provides a 
potential opportunity for building cross-lingual MRC that does not rely machine translation. Such as  (P<sub>zh</sub>, P<sub>en</sub>, Q<sub>en</sub>, A<sub>en</sub>, A<sub>zh</sub>), 
we first obtain A<sub>en</sub> through a English monolingual MRC model, then use a word alignment tool to obtain the aligned A<sub>zh</sub> from P<sub>zh</sub>.


## Notes and Acknowledgments
Chinese evaluation script is from <https://github.com/ymcui/cmrc2018>


## Data License
<a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/">Creative Commons Attribution-NonCommercial 4.0 International License</a>
