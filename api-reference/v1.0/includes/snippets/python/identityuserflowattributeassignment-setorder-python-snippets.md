---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = SetOrderPostRequestBody(
	new_assignment_order = AssignmentOrder(
		order = [
			"City",
			"extension_GUID_ShoeSize",
		]
	),
)

await graph_client.identity.b2x_user_flows.by_b2x_user_flow_id('b2xIdentityUserFlow-id').user_attribute_assignments.set_order.post(body = request_body)


```