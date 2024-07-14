### 框架学习

- shiro 

1对1 ： 

1对多： --->id

多对多:  -----> 中间表 也就是说第三张表





~~~ sql
--查询当前登录人所有的权限菜单数据（登录人ID=2)--


select * from sys_menu t1
left join sys_role_menu t2 on  t1.menu_id = t2.menu_id;
where  t2.role_id = 2;
~~~





~~~sql
--查询当前登录人所有的权限菜单数据（登录人ID=2)--


select * from sys_menu t1
left join sys_role_menu t2 on  t1.menu_id = t2.menu_id
left join sys_user_role t3 on  t2.role_id = t3.role_id;
where  t3.user_id  = 2;
~~~

### 很长  sys_menu--->  sys-role-menu  ----> sys-user-role where user_id = 2;



~~~sql 
--查询当前登录人所有的权限菜单数据（登录人ID=2)--


select t1.* from sys_menu t1
left join sys_role_menu t2 on  t1.menu_id = t2.menu_id
left join sys_user_role t3 on  t2.role_id = t3.role_id;
where  t3.user_id  = 2;
~~~



### 关联关系

![image-20231219111859922](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20231219111859922.png)





### 查询性别（一对一关系)

~~~sql
--查询性别--
select * from sys_dict_data t1 where t1.dict_type = 'sys_user_sex';
~~~

![image-20231219112934466](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20231219112934466.png)



### 权限管理

![image-20231219114209221](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20231219114209221.png)





![image-20231219114256438](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20231219114256438.png)







![image-20231219114525719](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20231219114525719.png)



![image-20231219114727650](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20231219114727650.png)



### 模块之间的功能



### 后台（后端)结构

~~~text
1. com.ruoyi     
2. ├── common            // 工具类
3. │       └── annotation                    // 自定义注解
4. │       └── config                        // 全局配置
5. │       └── constant                      // 通用常量
6. │       └── core                          // 核心控制
7. │       └── enums                         // 通用枚举
8. │       └── exception                     // 通用异常
9. │       └── json                          // JSON数据处理
10. │       └── utils                         // 通用类处理
11. │       └── xss                           // XSS过滤处理
12. ├── framework         // 框架核心
13. │       └── aspectj                       // 注解实现
14. │       └── config                        // 系统配置
15. │       └── datasource                    // 数据权限
16. │       └── interceptor                   // 拦截器
17. │       └── manager                       // 异步处理
18. │       └── shiro                         // 权限控制
19. │       └── web                           // 前端控制
20. ├── ruoyi-generator   // 代码生成（不用可移除）
21. ├── ruoyi-quartz      // 定时任务（不用可移除）
22. ├── ruoyi-system      // 系统代码
23. ├── ruoyi-admin       // 后台服务
24. ├── ruoyi-xxxxxx      // 其他模块
~~~



### 前端结构

### 路线 [基于SpringCloud Alibaba技术栈，若依微服务版(RuoYi-Cloud)脚手架入门精解，保证上手那种~_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV14g4y1N7tD/)

~~~text
├── build                      // 构建相关  
├── bin                        // 执行脚本
├── public                     // 公共文件
│   ├── favicon.ico            // favicon图标
│   └── index.html             // html模板
│   └── robots.txt             // 反爬虫
├── src                        // 源代码
│   ├── api                    // 所有请求
│   ├── assets                 // 主题 字体等静态资源
│   ├── components             // 全局公用组件
│   ├── directive              // 全局指令
│   ├── layout                 // 布局
│   ├── plugins                // 通用方法
│   ├── router                 // 路由
│   ├── store                  // 全局 store管理
│   ├── utils                  // 全局公用方法
│   ├── views                  // view
│   ├── App.vue                // 入口页面
│   ├── main.js                // 入口 加载组件 初始化等
│   ├── permission.js          // 权限管理
│   └── settings.js            // 系统配置
├── .editorconfig              // 编码格式
├── .env.development           // 开发环境配置
├── .env.production            // 生产环境配置
├── .env.staging               // 测试环境配置
├── .eslintignore              // 忽略语法检查
├── .eslintrc.js               // eslint 配置项
├── .gitignore                 // git 忽略项
├── babel.config.js            // babel.config.js
├── package.json               // package.json
└── vue.config.js              // vue.config.js
~~~

### 学习路线

- 

![image-20231220111341612](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20231220111341612.png)





### 样式布局

![image-20231221135804497](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20231221135804497.png)





### 判断删除

![image-20231221135820985](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20231221135820985.png)

![image-20240712101948945](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240712101948945.png)

---

>若依框架要明确一个问题那就是
>
>用户---> 角色---->菜单权限， 中间还有很多中间表
>
>![image-20240713214625178](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240713214625178.png)

---



#### 关于循环问题

> ![image-20240714111809992](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240714111809992.png)
>
> 

#### 项目上手技巧

>工作中：
>
>- 导入项目，看jar包和环境 --- maven 项目 SpringBoot 项目  微服务项目
>- 看项目组织架构，代码结构
>- 简单看看工具类（jwt,跨域，UUID） -- 可以直接导出API文档
>- 解析功能 -- 登录 -- 最简单的表的增删改查来学习
>- 尝试一张表来实现增删改查功能
>
>

### 导出API文档

![image-20240714113201245](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240714113201245.png)

---



#### 走读代码

>前端访问---> getway--> 认证中心
>
>![image-20240714115604872](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240714115604872.png)

---

>### 微服务启动的所需要的组件环境
>
>- Nacos环境
>- Sentinel 环境
>- ![image-20240714120817626](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240714120817626.png)
>
>~~~cmd
>使用cmd 命令，进入命令框，执行下面命令
>startup.cmd -m standalone
>
>~~~
>
>![image-20240714121600411](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240714121600411.png)

![image-20240714121730052](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240714121730052.png)

![image-20240714121922193](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240714121922193.png)

>从数据库中读取配置文件到Nacos中
>
>application.properties 这里需要修改配置的数据的用户名和密码
>
>![image-20240714122536556](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240714122536556.png)

#### 查看微服务的个数

>![image-20240714124547175](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240714124547175.png)
>
>

![image-20240714124658148](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240714124658148.png)

![image-20240714124753275](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240714124753275.png)

---

![image-20240714125046213](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240714125046213.png)