---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = QueryPostRequestBody(
	requests = [
		SearchRequest(
			entity_types = [
				EntityType.ChatMessage,
			]
			query = SearchQuery(
				query_string = "test",
			),
			from = 0,
			size = 25,
		),
	]
)

result = await graph_client.search.query.post(body = request_body)


```