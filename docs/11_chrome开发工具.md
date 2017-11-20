## 没有jquery时控制台选取元素
- 类似jquery的写法，使用两个'$'完成选取：$$("#XXX")

## 直接在界面编辑文本，无需选中dom在操作
- 控制台输入document.body.contentEditable = true 即可

## 监控事件
- monitorEvents(selector,[type1,type2]):测试不够灵敏，使用querySelecter实现了一次。

## 将变排成表格
- cosole.table(var)

## 打印代码执行时间
- console.time(tag) console.endTime(tag)
- $_ 获取上次的执行结果