项目结构

[TOC]

# common

#### Constants.go

//常量

#### Errors.go

//错误

#### Protocol.go(协议)

//定时任务// 任务调度计划// 任务执行状态// HTTP接口应答// 变化事件

# master

#### main

##### webroot

###### index.html

##### master.go

//解析命令行参数// 初始化线程数量

##### master.json

#### ApiServer.go(任务的HTTP接口)

//保存任务接口// 删除任务接口// 列举所有crontab任务// 强制杀死某个任务// 查询任务日志

// 获取健康worker节点列表// 初始化服务

#### Config.go

//程序配置//加载配置

#### JobMgr.go(管理任务)

//任务管理器//初始化管理器// 保存任务// 删除任务// 列举任务// 杀死任务

#### LogMgr.go(mongodb日志管理)

//查看任务日志

#### WorkerMgr.go

//获取在线worker列表

# worker

#### main

##### worker.go

//解析命令行参数// 初始化线程数量

##### worker.json

#### Config.go

//程序配置// 加载配置

#### Executor.go(任务执行器)

//执行一个任务// 初始化执行器

#### JobLock.go(分布式锁(TXN事务))

//初始化一把锁// 尝试上锁// 释放锁

#### JobMgr.go(任务管理器)

//监听任务变化// 监听强杀任务通知// 初始化管理器// 创建任务执行锁

#### LogSink.go(mongodb存储日志)

//批量写入日志// 日志存储协程// 发送日志

#### Register.go(注册节点到etcd)

// 获取本机网卡IP// 注册到/cron/workers/IP, 并自动续租

#### Scheduler.go(任务调度)

//处理任务事件// 尝试执行任务// 重新计算任务调度状态// 处理任务结果// 调度协程

// 推送任务变化事件// 初始化调度器// 回传任务执行结果

