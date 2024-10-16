# 主要API

此处简单介绍初版框架的主要API：

```python

# 0. agent
# 每个设备对应一个agent实例，依靠消息队列单线程工作，成员变量中维护所有 API 的类实例
RuyiAgent.__init__(AgentConfig) # 根据 config 实例化 Agent 及其所有成员变量并启动
RuyiAgent.serve()  # 启动消息队列轮询
RuyiAgent.stop()  # 停止消息队列轮询并停止所有成员变量的 API 实例
RuyiAgent.log(message, tag="INFO", reply_msg=None)  # 日志记录

# 1. task
RuyiTask.__init__()     # 配置 name、description、status、permissions等属性
RuyiTask.main()         # 任务主体函数，实现具体的功能

RuyiAgent.task.execute_task(taskCls)    # 执行任务

# 2. device
RuyiDevice.take_picture()  # 拍照
RuyiDevice.sms(phone_num, msg)  # 发送短信

RuyiDevice.app.start(app_name)  # 启动应用
RuyiDevice.app.kill(app_name)  # 关闭应用

# 3. ui
RuyiUI.root() -> UI_View    # 获取 UI 根节点
RuyiUI.back()    # 返回上一级 UI 页面

RuyiView.root -> UI_View    # 获取当前 UI 节点的根节点
RuyiView.locate_view(description)    # 根据描述获取 UI 节点
RuyiView.iterate_views(description, limit=-1)    # 根据描述获取多个 UI 节点
RuyiView.wait_view(description, timeout=10)    # 等待 UI 节点出现
# 还有 .contet .image .snapshot .click .input .scroll_up

RuyiLocator

# 4. fm

RuyiModel.__call__(*args, returns)    # 模型调用

# 5. data 

RuyiLiveTable.add_row(row_data)    # 添加一行数据

# maybe a stream api here
```