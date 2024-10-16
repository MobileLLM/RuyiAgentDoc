# Main API

Here is a brief introduction to the main APIs of the initial framework:

```python
# 0. agent
# Each device corresponds to an agent instance, which operates in a single thread through a message queue. 
# All class instances of the APIs are maintained as member variables.
RuyiAgent.__init__(AgentConfig)  # Instantiate the Agent and all its member variables based on the config and start it
RuyiAgent.serve()  # Start message queue polling
RuyiAgent.stop()  # Stop message queue polling and halt all API instances in the member variables
RuyiAgent.log(message, tag="INFO", reply_msg=None)  # Log messages

# 1. task
RuyiTask.__init__()  # Configure properties like name, description, status, permissions, etc.
RuyiTask.main()  # The main function of the task, implementing specific functionality

RuyiAgent.task.execute_task(taskCls)  # Execute a task

# 2. device
RuyiDevice.take_picture()  # Take a picture
RuyiDevice.sms(phone_num, msg)  # Send an SMS

RuyiDevice.app.start(app_name)  # Start an application
RuyiDevice.app.kill(app_name)  # Close an application

# 3. ui
RuyiUI.root() -> UI_View  # Get the root UI node
RuyiUI.back()  # Go back to the previous UI page

RuyiView.root -> UI_View  # Get the root node of the current UI view
RuyiView.locate_view(description)  # Get a UI node based on the description
RuyiView.iterate_views(description, limit=-1)  # Get multiple UI nodes based on the description
RuyiView.wait_view(description, timeout=10)  # Wait for a UI node to appear
# Also available: .content, .image, .snapshot, .click, .input, .scroll_up

RuyiLocator

# 4. fm
RuyiModel.__call__(*args, returns)  # Call a model

# 5. data
RuyiLiveTable.add_row(row_data)  # Add a row of data

# Maybe a stream API here
```