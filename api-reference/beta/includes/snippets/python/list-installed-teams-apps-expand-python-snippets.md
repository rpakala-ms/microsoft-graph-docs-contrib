---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

query_params = InstalledAppsRequestBuilder.InstalledAppsRequestBuilderGetQueryParameters(
		expand = ["teamsAppDefinition($expand=bot)"],
)

request_configuration = InstalledAppsRequestBuilder.InstalledAppsRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.teams.by_team_id('team-id').installed_apps.get(request_configuration = request_configuration)


```