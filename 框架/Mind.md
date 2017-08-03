# Mind
***
### 引擎:
- 概念:
	1. Mind驱动了input和output

细腻 丰富  

好奇心  
快乐  
欲望  
需求  

***

### MIND工作方式

```
/**
 *  MARK:--------------------Mind引擎(七情六欲)--------------------
 *
 *  <引擎>
 *  1,驱动input
 *  2,驱动output
 *
 *  <mind策略>
 *  最简单策略(><=)依赖于博弈;
 *
 *  <各类>
 *  1,欲望需求:(外界索取)
 *      比较各mind元的minValue;并以此策略展开decision;
 *  2,兴趣需求:(自身行动)
 *      比较各mind元的maxValue;并以此策略展开decision;
 */

```

***

### Mind-Demand


***

### Question

```
//思考2:当A在偷吃你的苹果时;你理解的重点是;他是不是吃的你的苹果;吃了多少;等相关信息;
//注意力,
//但Input输入A吃苹果时,Understand先理解并分析出苹果的归属及整个事件;然后交由Mind决定是不是打死他;(Mind需要的信息:A是谁,在作什么,吃了谁的什么);
//假如是其它事情呢;我需要找到一种万能的方式去解决Mind的控制流程;而不是把数据全部传过来作处理;Mind从职责上;只负责送出自己的精神层面的值;分析结果应该是Think层的事;
```

- 回答:
	1. 让Mind提供标准化接口;
	2. Think从MindControl获取会标准化值后解析;并影响:
		1. Decision的结果
		2. Understand的结果;
		3. 注意力的投放;
	
	
	
	
### 火花塞:(使mind着火的装置;)
- 无聊感
	- 作用:
		- 引起行为
		- 引起注意力
		- 读取AIMindValue中的Task;
	- 当前感受,如(好无聊)想出去,去哪呢?然后考虑自己的兴趣;mind发出指令;
	- 无聊感;Mind元之一;
	- 无聊感来自副引擎长期无(超爽的)输入;
	- 无聊感打断长期的无注意力状态;
		//2,将mind的意见记到logic和law里;   
		    //1,判断是否无聊;   
		    //2,判断是否需要注意力;   
		    //3,作为火花塞点燃mind;   
		    //xxx   
		
	• 好奇心
		○ 



***

### MindValue;
- 当记忆对MindValue产生影响;即"加强关联" & 存到mindValue表中...(经验Law)(第1维A)





### Mind元二维图;
> 注：参考：N2P17



### ==================Demand==================
```
/**
 *  MARK:--------------------需求模型--------------------
 *  特性:
 *      1,可变性(不同人对同事件在不同情况下会产生不同需求)
 *      2,灵活性(Mind变化,需求就变化)
 *  
 *  数据格式:
 *      1,因为其特性,所以需求不能存在Memory中,也不能存DB;只能实时生成;
 *  分类:
 *      1,记忆相关需求:如参加会议,从Mem里找引起需求变化的记忆,并分析出需求;
 *      2,记忆无关需求:如饥饿,从Mine读取值;
 *  设计:
 *      1,但Demand必须由Mind产生,从Memory生成,
 *      2,Demand不能存死在DB
 *      3,Demand会传递(例如,明天早上起来记得吃个鸡蛋)
 *      4,Demand有解决程度(例如,完成了50%的需求)
 *      5,需求的分析,可以存在记忆中...(参见N2P13)
  *  作用:
 *      1,产生意识
 *      2,使decision中产生 (logic/经验)存储里必须的pointer关联;(不然你会以为吃筷子吃饱的;而不是饭)

 *
 */

/**
 *  MARK:--------------------记忆数据--------------------
 *  1,用Decision分析记忆中数据为mindShakeArr;将mindShakeArr交由Mind决断(Decision与Mind紧密关联)
 *  2,Mind决断后,下达需求任务给FeelOut;
 *  3,FeelOut决定如何输出;
 *  注:(此处引出Decision的"分析决策阶段"和"FeelOut阶段"的不同)(因为我们有可能分析决策;但不行动)
 *
 *  如:早上起来喝牛奶:
 *      1,早上起来,Input记忆时Understand联想到喝牛奶;
 *      2,Understand交给Mind;
 *      3,Mind交@"喝牛奶"给Decision找到喝牛奶找到关联记忆;并分析mindShakeArr交回给Mind;
 *      4,Mind下令喝一个;并交给FeelOut;
 *      5,FeelOut决定行动起来;喝一个走起;
 *  如:饿了:
 *      1,Mind饿了;
 *      2,将找吃的交给Decision找到冰箱里有什么的关联记忆,并分析mindShakeArr交回给Mind;
 *      3,Mind下令喝牛奶;并交给FeelOut;
 *      4,FeelOut决定行动起来;喝一个走起;
 */
@property (strong,nonatomic) NSMutableArray *memArr;    //相关记忆数据;
@property (strong,nonatomic) NSMutableArray *mindShakeArr;  //
```
<br/><br/>
***
### Demand_Old
```
/**
 *  MARK:--------------------需求工厂--------------------
 *  1,充电需求
 *  2,欲望需求
 *  3,例如:看到钱时,要捡起来;并且道德打败欲望,找失主;
 */
@interface DemandFactory : NSObject

/**
 *  MARK:--------------------产生需求任务--------------------
 *  return 任务
 *  参数:任务类型
 *  参数:任务...
 *  1,PhysiologicalDemands生理需求(充电)
 *  2,SafetyDemands安全需求(驱动好奇心)
 *  3,LoveAndBelongingDemands社交需求
 *  4,
 */

```
<br/><br/>
***

### MoodDuration"心情持续"
```
//两种设计:
//1,使用"心情持续"管理器;
//2,使用"神经网络"AILine的类型;
//3,AILine越简单越好,所以当前先用方案1;以后不排除重构使用2;
```



### 求生欲
- 死亡恐惧  



