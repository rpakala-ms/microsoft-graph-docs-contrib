---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = DeviceCompliancePolicyDeviceStateSummary(
	odata_type = "#microsoft.graph.deviceCompliancePolicyDeviceStateSummary",
	in_grace_period_count = 2,
	config_manager_count = 2,
	unknown_device_count = 2,
	not_applicable_device_count = 8,
	compliant_device_count = 4,
	remediated_device_count = 5,
	non_compliant_device_count = 7,
	error_device_count = 0,
	conflict_device_count = 3,
)

result = await graph_client.device_management.device_compliance_policy_device_state_summary.patch(body = request_body)


```