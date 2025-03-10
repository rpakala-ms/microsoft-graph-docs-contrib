---
title: "mailFolder: delta"
description: "Get a set of mail folders that have been added, deleted, or removed from the user's mailbox."
ms.localizationpriority: medium
author: "SuryaLashmiS"
ms.prod: "outlook"
doc_type: apiPageType
---

# mailFolder: delta

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a set of mail folders that have been added, deleted, or removed from the user's mailbox.

A **delta** function call for mail folders in a mailbox is similar to a GET request, except that by appropriately
applying [state tokens](/graph/delta-query-overview) in one or more of these calls,
you can query for incremental changes in the mail folders. This allows you to maintain and synchronize
a local store of a user's mail folders without having to fetch all the mail folders of that mailbox from the server every time.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).


|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Mail.ReadBasic, Mail.Read, Mail.ReadWrite    |
|Delegated (personal Microsoft account) | Mail.ReadBasic, Mail.Read, Mail.ReadWrite    |
|Application | Mail.ReadBasic.All, Mail.Read, Mail.ReadWrite |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /me/mailFolders/delta
GET /users/{id}/mailFolders/delta
```

## Query parameters

Tracking changes in mail folders incurs a round of one or more **delta** function calls. If you use any query parameter
(other than `$deltatoken` and `$skiptoken`), you must specify
it in the initial **delta** request. Microsoft Graph automatically encodes any specified parameters
into the token portion of the `@odata.nextLink` or `@odata.deltaLink` URL provided in the response.
You only need to specify any desired query parameters once upfront.
In subsequent requests, simply copy and apply the `@odata.nextLink` or `@odata.deltaLink` URL from the previous response, as that URL already
includes the encoded, desired parameters.

| Query parameter	   | Type	|Description|
|:---------------|:--------|:----------|
| $deltatoken | string | A [state token](/graph/delta-query-overview) returned in the `@odata.deltaLink` URL of the previous **delta** function call for the same mail folder collection, indicating the completion of that round of change tracking. Save and apply the entire `@odata.deltaLink` URL including this token in the first request of the next round of change tracking for that collection.|
| $skiptoken | string | A [state token](/graph/delta-query-overview) returned in the `@odata.nextLink` URL of the previous **delta** function call, indicating there are further changes to be tracked in the same mail folder collection. |

### OData query parameters

You can use a `$select` query parameter as in any GET request to specify only the properties your need for best performance. The
_id_ property is always returned.

## Request headers
| Name       | Type | Description |
|:---------------|:----------|:----------|
| Authorization  | string  | Bearer {token}. Required. |
| Content-Type  | string  | application/json. Required. |
| Prefer | string  | odata.maxpagesize={x}. Optional. |

## Response

If successful, this method returns a `200 OK` response code and [mailFolder](../resources/mailfolder.md) collection object in the response body.

## Example
##### Request
The following example shows how to make a single **delta** function call, and limit the maximum number of mail folders
in the response body to 2.

To track changes in the mail folders of a mailbox, you would make one or more **delta** function calls, with
appropriate state tokens, to get the set of incremental changes since the last delta query.

You can find a similar example that shows how to use the state tokens to track changes in the messages of a mail folder:
[Get incremental changes to messages in a folder](/graph/delta-query-messages). The main differences
between tracking mail folders and tracking messages in a folder are in the delta query request URLs, and the query responses
returning **mailFolder** rather than **message** collections.


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "mailfolder_delta"
}-->
```msgraph-interactive
GET https://graph.microsoft.com/beta/me/mailFolders/delta

Prefer: odata.maxpagesize=2
```

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/mailfolder-delta-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/mailfolder-delta-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

##### Response

If the request is successful, the response would include a state token, which is either a _skipToken_
(in an _@odata.nextLink_ response header) or a _deltaToken_ (in an _@odata.deltaLink_ response header).
Respectively, they indicate whether you should continue with the round or you have completed
getting all the changes for that round.

The response below shows a _skipToken_ in an _@odata.nextLink_ response header.

Note: The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.mailFolder",
  "isCollection": true
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.nextLink":"https://graph.microsoft.com/beta/me/mailFolders/delta?$skiptoken={_skipToken_}",
  "value": [
    {
      "displayName": "displayName-value",
      "parentFolderId": "parentFolderId-value",
      "childFolderCount": 99,
      "unreadItemCount": 99,
      "totalItemCount": 99,
      "wellKnownName": "wellKnownName-value"
    }
  ]
}
```

### See also

- [Microsoft Graph delta query](/graph/delta-query-overview)
- [Get incremental changes to messages in a folder](/graph/delta-query-messages)

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "mailFolder: delta",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->


