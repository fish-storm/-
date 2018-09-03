# study-notes
记录日常的学习
相关资料和一些感触

 fishmaple 1.0

## 使用node.js进行前端项目构建（预期）
    
element-ui框架的使用 存在问题
   - tooltip 无限加载 卡住(聊天室)
   - textarea组件 rows属性无效
      
      - 初步是npm判断方式兼容性更优

聊天室
   
      
    
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

          
