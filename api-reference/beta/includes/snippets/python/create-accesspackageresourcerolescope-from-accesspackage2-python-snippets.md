---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = AccessPackageResourceRoleScope(
	access_package_resource_role = AccessPackageResourceRole(
		origin_id = "4",
		origin_system = "SharePointOnline",
		access_package_resource = AccessPackageResource(
			id = "53c71803-a0a8-4777-aecc-075de8ee3991",
		),
	),
	access_package_resource_scope = AccessPackageResourceScope(
		id = "5ae0ae7c-d0a5-42aa-ab37-1f15e9a61d33",
		origin_id = "https://microsoft.sharepoint.com/portals/Community",
		origin_system = "SharePointOnline",
	),
)

result = await graph_client.identity_governance.entitlement_management.acce_packages.by_acce_package_id('accessPackage-id').acces_package_resource_role_scopes.post(body = request_body)


```