## 选择Vscode 
```
   原因：微软的规范性以及文本编辑器的框架（如果有足够的时间 
```

## 目的
``` 
     了解迭代周期以及规范性
             计划周期内的延期任务如何安排
             对于bugfix和新功能时间预估
             模块测试规范
     了解code review的具体内容
            日常review着重检查逻辑以及性能
      
      关于、迭代遇到的疑惑
         临时紧急需求如何安排
         版本定义以及版本迭代的划分？bugfix推送规范？
         什么样的代码风格为标准？性能与可读性的权衡？如推导式
         代码逻辑性易读以及代码规范冲突的选择？
            如：
               计算逻辑复杂，代码逻辑风格选择
               单个函数囊括所有计算逻辑（引入模块只负责通用功能）
               类似java层层包裹封装（不易于新同学理解）
```    

## 关于开发周期

### roadmap
```
   vs以6-12个月为周期制定规划
```

### 迭代周期划分
```
   以自然月迭代，每个月有单独的plan和endgame
```

### 迭代周期内

```
    week1
          减少上一次迭代遗留的债务，解决上一周期遗留的关键性债务，计划下一周期
    week2
          按week1的计划
     week3
          按week1的计划
     final week
           按测试计划测试新功能等，并补充文档
           pre-release版本，邀请用户帮忙测试
     week1
           检查监控上一周期的pre-release，并解决遗留的关键性issue
           发布pre-release
```

### Triage(任务分配>里程碑)
```
     bug和feature都会被分配到milestone里程碑，带有优先级
          严重的bug会被安排在其他bug前面
     fixbug之后确认相关issue
```

### 周期(周)盘点
```
    每周整理迭代计划，关闭已完成的feature以及分配bug修复任务；
    结束里程碑的要求，必须0bug和0issue，部分bug和feature移动到下一个里程碑
```

### 周期完结
```
    最后一个里程碑被定义为endgame，打包feature，按测试计划测试并修复严重的bug
```


### master打包
```
     确认内部版本为最新
     确认持续生成为绿色（通过状态
     如果，生成失败，从build slack channel确认通知谁处理
     如果，编译失败，push一个修复的commit病通知开发者
     如果，测试失败，提交issue给开发者修复
````

### 关于endgame分支管理

```
    1、在endgame时期创建release-1.10
    2、打包上一步的分支并系统性的测试
    3、任何严重bug都应修复并推送到master以及release-1.10，并通过步骤2
    4、无严重bug即创建tag:release-1.10.0
    5、以tag:release-1.10.0打包并推送给用户
    6、任何修复打包都应该依赖于release-1.10，补丁版本定义为：1.10.1,1.10.2...
```

### Endgame一周的安排
```
      周一：保证持续生成绿色以及冻结代码
      周二：测试
      周三：测试和fix
      周四：fix和签名认证
      周五：暂停封存任务安排表，打包master，测试、修复，更新相关issue、评论等
```

## 代码组织
```
   The core is partitioned into the following layers:
   base: Provides general utilities and user interface building blocks
   platform: Defines service injection support and the base services for Code
   editor: The "Monaco" editor is available as a separate downloadable component
   languages: For historical reasons, not all languages are implemented as extensions (yet)
         - as Code evolves we will migrate more languages to towards extensions
   workbench: Hosts the "Monaco" editor and provides the framework for "viewlets" like the Explorer, 
         Status Bar, or Menu Bar, leveraging Electron to implement the Code desktop application.
```

## 关于code review
```
https://github.com/microsoft/vscode/pulls
```

### 面壁



    