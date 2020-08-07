
# Aug-03,2020

<details>
<summary><b>DETAILS</b></summary>
<p>
//查询
const db = wx.cloud.database();//小程序端获取数据库的引用
const coll = db.collection('todos');//获取集合引用并不会发起网络请求去拉取它的数据
coll.doc('id').get().then(res => {console.log(res)})
// 插入
db.collection('todos').add({
data:{
  filed1:'string',
  filed2:'Number',
  filed3:'Array',
  filed4:'Object'
}
}).then(res=>{
  console.log(res)
})
// 查询
db.collection('todos').where({openid:'openid',done:false}).get().then(res=>{console.log(res)})
// 获取一个集合的数据：小程序中一次默认最多返回20条记录，在云函数中一次默认最多返回100条记录。可通过limit方法制定需要获取的记录数量。
const cloud = require('wx-server-sdk');
cloud.init();
const db = cloud.database();
const MAX_LIMIT =100;
exports.main = async(event,context) => {
  const countResult = await db.collection('todos').count()
  const total = countResult.total();
  const batchTimes = Math.ceil(total/MAX_LIMIT);
  const tasks = [];
  for(let i=0;i<batchTimes;i++){
    const promise = db.collection('todos').skip(i*btachTimes).limit(MAX_LIMIT).get();
    tasks.push(promise)
  }
  for(await Promise.all(tasks)).reduce((acc,cur)=>{
    return {
      data:acc.data.concat(cur.data),
      errMsg:acc.errMsg,
    }
  })
}
// 查询指令 const _ = db.command
// 大于：_.gt(value)
// 等于：_.eq(value)
// 不等于：_.neq(value)
// 小于：_.lt(value)
// 小于或等于： _.lte(value)
// 在给定数组中：_.in(1,2,3)

// 更新 update、set
db.collection('todos').doc('id').update({
  data:{
    done: true
  }
}).then(res =>{console.log(res)}
// 更新指令
// set 设置字段为指定值
// remove  删除字段
// inc 原子自增字段值--不会受到并发写的影响
// mul 原子子乘字段值
// push 数组末尾增加指定值
const _ = db.command();
db.collection('todos').doc('id').update({
  data:{
    progress:_.inc(10),
    undone:_.push('newTag')
  }
})

db.collection('todos').doc('id').update({
  data:{
    style:{
      color:'blue'
    }
  }
})


db.collection('todos').doc('id').update({
  data:{
    style:_.set({color:.'blue'})
  }
})

// 替换更新
db.collection('todos').doc('id').set({
  data:{
    filed1:'String',
    filed2:'Number'
  }
})

// 删除数据
db.collection('todos').doc('id').remove().then(res=>{console.log(res)})

// 普通匹配：
db.collection('todos').where({
    progress:50,
    done: false
}).get()

db.collection('todos').where({
  'style.color':'red'
}).get().then()

db.collection('todos').where({
  numbers:20
}).get().then()

db.collection('todos').where({
  'numbers.1':20
}).get().then()
 
db.collection('todos').doc('test').update({
  data:{
     'numbers.1':30
  }
})

// 实时数据推送 聊天/广播/多人游戏/协作工具/信息流
// 监听：调用Collection上的watch方法即可监听给定查询条件对应的数据，支持搭配使用orderBy和limit
const db = wx.cloud.database();
const watcher = db.collection('todos')
  .orderBy('progress','desc'),
  .limit(10)
  .where({
    team:'our team'
  })
  .watch({
    onChange:function(snapshot){
      console.log(snapshot.docChanges);
      console.log(snapshot.docs);
      console.log(snapshot.type)
    },
    onError:function(err){
      console.error(err);
    }
  })
watcher.close();


// 聚合：数据批处理的操作

// 分组查询：
// 只取某些字段的统计值或变换值返回
// 流水线式分阶段批处理
// 获取唯一值(去重)
const db = wx.cloud.database()
const $ = db.command.aggregate
db.collection('books').aggregate()
  .group({
    _id:'$category',
    avgSales:$.avg('$sales')
  })
.end()
// 聚合流水线：聚合是一个流水线式的批处理作业，一个流水线作业包含多个批处理阶段，每个阶段接收来自上一个阶段的输入记录列表(如果是第一个阶段则是集合全集)，然后处理成新的记录列表后输出给写一个阶段，直至返回结果。

// 聚合阶段 &操作符：一个聚合阶段是一个将一批输入记录按开发者指定的规则转换为新一批输出记录的过程。一个阶段的输出记录数与其输入记录无关、既可以保持不变，每个输入记录对应一个输出记录，也可以合并或分组输出更少的一个或多个记录，甚至与输出更多的记录。一个聚合流水线操作的第一个阶段是流水线的开始，接收集合所有记录作为输入，最后一个阶段是流水线的结束，其结果作为输出返回给调用方。要定义一个阶段，首先要确定要使用的阶段，聚合能力提供了包括分组阶段group，排序阶段sort、投影阶段project等多种可选的阶段。每个阶段又可以通过一个对象作为参数定义这个阶段操作的具体行为表现，其中i个参数对象的每一个字段的值都必须是一个表达式或聚合操作符，一个操作符可以接收表达式作为输入，可用的操作符列表可以在文档中找到。

// 事务
// 如果原子操作符(如 inc、mul、addToSet)和嵌套记录的数据结构设计无法满足需求，需要更高可自定义的事务操作，或跨多个记录或跨多集合的原子操作时(比如两个账户之间转账)，可以使用云数据事务能力。
// 快照隔离：

// 索引

// Explain查询分析

</p>
</details>


# Aug-05,2020  周三

<details>
<summary><b>今日目标</b></summary>
<p>
1.Just JavaScript第三四节学完，回顾第一二节。
</p>
</details>

<details>
<summary><b>今日复盘</b></summary>
<p>
1.Just JavaScript第三四节学完，且翻译完毕，第一二节未复习。
</p>
</details>

# Aug-07,2020  周五

<details>
<summary><b>今日目标</b></summary>
<p>
1.Just JavaScript第五节学完。
</p>
</details>

<details>
<summary><b>今日复盘</b></summary>
<p>

</p>
</details>
