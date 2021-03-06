# diagram

## 为什么需要任务编排
ETL 任务处理中，我们需要执行很多sql文件，这些sql文件往往要按照数据的流向顺序执行，手动执行易出错，且耗人力。因此如果可以将任务按照一定顺序编排，自动调度，自动执行，那将 “多是一件美事”

### ETL-PCE提供了什么功能？
- 可视化编排任务（如下图）
 1.1 接近原生IDE的SQL编辑
 1.2 清晰的数据流向图
 1.3 拖拽式流程编辑
 
 ![image](https://user-images.githubusercontent.com/36019799/149656542-11584f01-5dd2-4642-be75-6b353c2fc71c.png)
 
- 调度任务
  提供页面调度执行功能
- 流程一致性顺序执行
  使用锁和key检查等机制保证任务执行有序。


### 原理
1)可视化原理 使用SVG处理流程图
<br>
2)执行原理 类似图的广度遍历，配合redis锁，实现任务调度管理

### TODO List
优化界面操作
优化线程调度

### 技术参考
See [redis 官方文档](https://redis.io/documentation).
See [SVG MDN文档](https://developer.mozilla.org/zh-CN/docs/Web/SVG/Element/svg).
