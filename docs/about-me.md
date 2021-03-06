# 个人简历

## 个人信息

姓名: 宋封帅

性别: 男

年龄: 24

学历: 河南职业技术学院（软件技术）、郑州大学（计算机科学与技术）

工作经验: 4.5年

电话: 17600205539(微信同号)

邮箱: 17600205539@163.com

## 求职意向
期望薪水: 面议
地点: 上海
职位: 前端开发工程师

## 个人技能
- 熟练掌握 `Vue` 全家桶（含 vue3），看过 `Vue 响应式原理`、`依赖收集原理`、`编译原理`、`diff 算法`、`vue-router`，`vuex `等部分源码。
- 熟练使用 `Vue` 封装业务组件、公共组件等。
- 熟练掌握 `React` 全家桶，掌握 `hooks` 组件开发模式。了解 `React` 底层原理实现
- 熟练掌握微信小程序、支付宝小程序开发技能。
- 熟练掌握 `typescript`、`ES6` 的新特性。熟练面向对象和组件化开发，熟悉MV*开发
- 熟练掌握工程化编程，熟悉 webpack 基本配置，熟悉 loader 及 plugin 开发流程
- 熟悉 `node`，可以使用 `node` 做前端工具、也可以借 `node` 做 `BFF` 
- 熟练使用 `Git`版本管理工具。
- 了解数据结构和算法。

### 工作经验

- 2021.06 — 至今 微盟

  职 位 : 高级前端工程师

  职 能 : 负责小程序业务开发，基础工具建设开发，kratos主要负责人，小程序组件开发者。

- 2019.11 — 2021.03 阿里巴巴口碑会员项目
  
  职 位 : web 前端工程师

  职 能 : 负责会员中心模块的更新迭代优化、CRM sass 后台会员营销模块迭代、组件库基础建设

- 2017_10 — 2018_04 颐老乐科技有限公司
- 2018_04 — 2019.11 深圳前海热浪出海有限公司（同一个负责人）
  
  职 位 : web 前端工程师

  职 能 : 根据 UI 设计图进行页面开发，负责项目的更新维护等等。项目为 B/C项目，采用 jQuery+bootstarp 开发响应式端网站。Vue 全家桶+rem 布局开发移动端网站，优化用户体验，达到接近原生 APP 效果，优化渲染速度。独立负责前端架构，开发 H5 小游戏等等。兴趣驱使学习 Vue 源代码。

### 项目经历

### kratos

项目背景: 因为我们部门大多数代码都是微信小程序代码，客户端有一些页面想直接复用微信小程序的页面，于是有了这个项目。
项目介绍: kratos是用来微信小程序代码转vue代码运行到客户端的webview上面，借鉴了miniprogram-to-uniapp的思想，结合我们的项目及UI库做了自定义的代码转译
技术栈: **Nodejs**、**Typescript**
职责: 
1. 封装`template paser`，把`wxml`转换成`ast`，再解析成`vue template`
2. `wxs`文件和标记处理，抹平`wsx`和`js`的差异问题
3. 分业务线做`tree shaking`，忽略不需要的模块代码
4. 命令行工具的开发，方便业务方使用，实现转译代码自动构建，代码包自动上传等
5. 实现命令行工具版本更新检测，自动更新
6. 主导项目的推进、代码`CR`、落地等


### 微盟商户助手小程序重构

项目背景: 微盟商户助手之前是基于店铺id的，商户数据量比较多，为了解决商户的痛点，重构了整个前端后端架构
项目介绍: 微盟商户助手的小程序
技术栈: 微信小程序、saas预处理器
职责: 
1. 负责登录模块的重构，接通微信登录，账号密码登录，企微一键登录，企微自动登录等。
2. 负责工作台模块的开发，实现工作台新手引导，动画交互，拖拽排序等
3. 负责虚拟路由模块的开发，每个模块的路径由服务端下发，虚拟路由模块解析服务端下发的进行解析，然后再进行前端的页面跳转
4. 负责站外安装模块的开发，站外安装是通过第三方的方式进行企业微信应用安装，然后创建店铺等操作
5. 负责个人中心模块的重构，包括修改头像，修改昵称，修改手机号，注销账号等基础操作。
6. 完成微盟商户助手新老体系的融合，做到商户无感知升级迁移
7. 封装自定义`BasePage`，注入插件能力的实现
8. 优化小程序体验，优化小程序包体积

### 移动运营平台

项目背景: 为了方便运营人员管理app版本，白名单，组件标识等，开发的后管页面
项目介绍: 基于bosid体系的移动运营平台
技术栈: **React**、**Ant Design Pro**
职责: 
1. 使用`useContext` + `useReducer`封装`Antd Modal`，提供一个`useNiceModal`api，实现promise方式弹出，关闭后接收参数
2. 完成表单和表格复杂场景的数据交互
3. 解决分页后修改页码数量的bug
4. 配合天狼星(微盟微前端平台)完成权限的校验，项目上线

### 品牌商家会员中心

项目背景: 品牌商家会员中心的日常迭代
项目介绍: 支付宝、饿了么 、淘宝：小程序品牌商家会员中心
技术栈: 微信小程序、**Typescript**、less预处理器
职责: 
1. 编写需求系分文档，参与日常迭代需求评审
3. 饿了么联名卡承接页小程序的开发
4. 负责积分商城，我的页面，优惠券等模块的迭代开发
5. 处理端之间的兼容、封装可复用性业务组件
6. 监控线上异常情况上报、处理；以及性能首屏加载优化

### proxy king

项目背景: 口碑crm项目开发比较繁琐，需要修改hosts文件，还要开代理，才能进行开发，而且线上如果出问题，查找bug比较困难，故开发了这个工具
项目介绍: 一键化配置项目代理，实现线上环境本地debug
技术栈: **Nodejs**、anyproxy、**React**
职责: 
1. 基于`proxy`完成静态资源的代理，提供开启代理，关闭代理等`api`
2. 完成线上环境使用本地代码调试
3. 实现界面化操作（开启关闭代理），项目管理
4. 使用`graphql`完成`GUI`界面和`node`通信
5. 解决`https`代理痛点

### Cook Design组件平台

项目背景: Ant Design的主题和组件不复合口碑风格，基于Ant Design做了二次封装。还有一些移动端，小程序组件的管理
项目介绍: 基于Ant Design组件的二次封装。移动端组件的开发封装等。
技术栈: React、Ant Design
职责: 
1. 完成部分`Ant Design`组件的迁移，代码修改，文档编写等
2. npm包发布，版本管理
3. 扩展移动端、小程序端组件、封装业务组件等
4. 编写组件的使用文档，使用demo

### koinrocket

项目背景: 区块链最火时候的产物
项目描述: 区块链交易所项目，夹杂一些小游戏
技术栈: Vue、Typescript、tradingview、node
职责: 
1. 独立开发 pc 端移动端， 并完成上线。
2. 负责项目的开发更新迭代，pc 端，移动端页面，交互效果等。
3. 接入`tradingview`，完成曲线图，和火币类似，实现买入卖出等功能。
4. 开发一些与币相关的小游戏，砸金蛋，挖金矿等
5. 基于`Vue SSR`并配合`SEO工程师同事`完成`SEO`优化
6. 开发`webpack loader`，实现`vue-i18n`自动化
7. 完成项目上线，性能优化等

## 自我评价

- 代码强迫症，无lint不代码
- 有很好的自学能力和处理问题的能力，善用技术书籍，官方文档，搜索引擎学习、解决问题。
- 拥有较丰富的移动端开发经验，喜欢钻研有趣的交互动画
- 接受加班，适应出差。服从安排。乐观开朗，能快速融入团队
- 热衷前端技术，对前端相关领域技术保持持续关注，喜欢研究优质开源项目，有良好的英文文档阅读能力，
- 较强的理解和沟通能力，能够承担工作压力；