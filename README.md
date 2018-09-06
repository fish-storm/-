# study-notes
记录日常的学习
相关资料和一些感触



 fishmaple 1.0

## 使用node.js进行前端项目构建（预期）
    
element-ui框架的使用 存在问题
   - tooltip 无限加载 卡住(聊天室)
   - textarea组件 rows属性无效
   - 上传组件的蜜汁问题 魔改删除操作函数会发生强制删除 删除失败等问题 现在是进行的手动删除
   
      
      - 初步是npm判断方式兼容性更优

聊天室

工具箱
   - post请求 使用参数{emulateJSON:true}后 contentType会变为application/x-www-form-urlencoded 这种格式在后台是无法直接绑定为对象的 注意规范格式
   - vue-for 并不能动态地刷新，使用vue.set()和相关的变异方法可以响应式的刷新push() pop() shift() unshift() splice() sort() reverse()      
    
## 后台部分


 技术栈阐释
  - 定时任务
  - mybatis
  - 阿里的数据源Druid
  - 使用slf4j作为入口的log4j2

 聊天室 
  - 随机名策略
      - 使用sessionId作为单一用户的判断标识(ip+cookie?)
      - 考虑并发 使用最高级别事务隔离
      - 防止产生坏数据 启动定时任务定期清理过期sessionId(存入操作时间)
      - 由于是单条查找 暂时不考虑性能 
      
 工具箱
   - mybatis的使用
     - mybatis并不像ConventionDAO增删改也可以返回数据值 所以uuid放在后台生成
     - 文件下载时 有&会被解析导致下载失败 所以不能用get直接体现在url里
     - 案例分析：在一个for循环外定义了一个对象，for循环内反复赋值 发现最后读取的是同一个对象
 

          
