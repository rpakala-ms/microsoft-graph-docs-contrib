---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)


result = await graph_client.groups.by_group_id('group-id').threads.by_thread_id('conversationThread-id').posts.by_post_id('post-id').extensions.by_extension_id('extension-id').get()


```