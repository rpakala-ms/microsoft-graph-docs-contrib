---
title: "getDeviceManagementIntentPerSettingContributingProfiles action"
description: "Not yet documented"
author: "jaiprakashmb"
localization_priority: Normal
ms.prod: "intune"
doc_type: apiPageType
---

# getDeviceManagementIntentPerSettingContributingProfiles action

Namespace: microsoft.graph

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

Not yet documented

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|DeviceManagementConfiguration.Read.All, DeviceManagementConfiguration.ReadWrite.All, DeviceManagementApps.Read.All, DeviceManagementApps.ReadWrite.All, DeviceManagementManagedDevices.Read.All, DeviceManagementManagedDevices.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|DeviceManagementConfiguration.Read.All, DeviceManagementConfiguration.ReadWrite.All, DeviceManagementApps.Read.All, DeviceManagementApps.ReadWrite.All, DeviceManagementManagedDevices.Read.All, DeviceManagementManagedDevices.ReadWrite.All|

## HTTP Request
<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /deviceManagement/reports/getDeviceManagementIntentPerSettingContributingProfiles
```

## Request headers
|Header|Value|
|:---|:---|
|Authorization|Bearer &lt;token&gt; Required.|
|Accept|application/json|

## Request body
In the request body, supply JSON representation of the parameters.

The following table shows the parameters that can be used with this action.

|Property|Type|Description|
|:---|:---|:---|
|name|String|Not yet documented|
|select|String collection|Not yet documented|
|search|String|Not yet documented|
|groupBy|String collection|Not yet documented|
|orderBy|String collection|Not yet documented|
|skip|Int32|Not yet documented|
|top|Int32|Not yet documented|
|sessionId|String|Not yet documented|
|filter|String|Not yet documented|



## Response
If successful, this action returns a `200 OK` response code and a Stream in the response body.

## Example

### Request
Here is an example of the request.

# [HTTP](#tab/http)
<!-- { "blockType": "request" , "name" : "intune_reporting_devicemanagementreports_getdevicemanagementintentpersettingcontributingprofiles_getdevicemanagementintentpersettingcontributingprofiles_action" }-->
``` http
POST https://graph.microsoft.com/v1.0/deviceManagement/reports/getDeviceManagementIntentPerSettingContributingProfiles

Content-type: application/json
Content-length: 278

{
  "name": "Name value",
  "select": [
    "Select value"
  ],
  "search": "Search value",
  "groupBy": [
    "Group By value"
  ],
  "orderBy": [
    "Order By value"
  ],
  "skip": 4,
  "top": 3,
  "sessionId": "Session Id value",
  "filter": "Filter value"
}
```

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/intune-reporting-devicemanagementreports-getdevicemanagementintentpersettingcontributingprofiles-getdevicemanagementintentpersettingcontributingprofiles-action-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/intune-reporting-devicemanagementreports-getdevicemanagementintentpersettingcontributingprofiles-getdevicemanagementintentpersettingcontributingprofiles-action-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

<!-- { "blockType": "response" , "@odata.type" : "microsoft.graph." }-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 131

{
  "value": "Z2V0RGV2aWNlTWFuYWdlbWVudEludGVudFBlclNldHRpbmdDb250cmlidXRpbmdQcm9maWxlcyBJbnR1bmUgRG9jIFNhbXBsZSA4OTc0NTYyMg=="
}
```
