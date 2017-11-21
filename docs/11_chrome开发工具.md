### 没有jquery时控制台选取元素
- 类似jquery的写法，使用两个'$'完成选取：$$("#XXX")

### 直接在界面编辑文本，无需选中dom在操作
- 控制台输入document.body.contentEditable = true 即可

### 监控事件
- monitorEvents(selector,[type1,type2]):测试不够灵敏，使用querySelecter实现了一次。

### 将变排成表格
```javascript 1.7
    let a = {};
    cosole.table(a)
```

### 打印代码执行时间
    console.time(tag) console.endTime(tag)
    //$_ 获取上次的执行结果

## chrome62新增功能
[原文链接](https://developers.google.com/web/updates/2017/08/devtools-release-notes)
### console支持顶级await关键字
### 支持屏幕截图（ctrl + alt + c + 鼠标左键）
### css Grid 高亮
### 根据构造函数查询实例
    queryObject(constructor) //将返回实例数组
### console支持自定义（negative filters）过滤输出
### Network支持导入HAR文件
- 直接拖放即可
### 预览缓存资源
### 更易预测的缓存调试
- Cache Storage 会实时更新
### Coverage 标签代码使用率判定将细到块级代码。（62以前是函数级）
