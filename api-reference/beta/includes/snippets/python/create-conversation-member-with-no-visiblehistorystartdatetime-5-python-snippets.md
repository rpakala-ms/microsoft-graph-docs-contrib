---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = AadUserConversationMember(
	odata_type = "#microsoft.graph.aadUserConversationMember",
	roles = [
		"guest",
	]
	additional_data = {
			"user@odata_bind" : "https://graph.microsoft.com/beta/users/8ba98gf6-7fc2-4eb2-c7f2-aef9f21fd98g",
	}
)

result = await graph_client.chats.by_chat_id('chat-id').members.post(body = request_body)


```