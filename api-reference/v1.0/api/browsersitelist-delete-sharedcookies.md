---
title: "Delete browserSharedCookie"
description: "Delete a browserSharedCookie from a browserSiteList."
author: "edward-day-vii"
ms.localizationpriority: medium
ms.prod: "browser-management"
doc_type: apiPageType
---

# Delete browserSharedCookie
Namespace: microsoft.graph

Delete a [browserSharedCookie](../resources/browsersharedcookie.md) from a [browserSiteList](../resources/browsersitelist.md).

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|BrowserSiteLists.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|BrowserSiteLists.ReadWrite.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
DELETE /admin/edge/internetExplorerMode/siteLists/{browserSiteListId}/sharedCookies/{browserSharedCookieId}
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If the shared cookie was not previously published, then this method returns a `204 No Content` response code on a successful delete. If the shared cookie was previously published, then this method returns a `200 OK` response code and a [browserSiteList](../resources/browsersitelist.md) object in the response body with the status as `pendingDelete`. You must publish (for example, via the [browserSiteList: publish](../api/browsersitelist-publish.md) API) the shared cookie to fully remove it from the site list.

## Examples

### Example 1: Delete a shared cookie that was not previously published

#### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "delete_browsersharedcookie",
  "@odata.type": "microsoft.graph.browserSharedCookie",
  "sampleKeys": ["7cf831d2-8a9b-4826-b120-911566f6fd6a", "07b4cc32-237f-4a1a-9d7f-531efc26220e"]
}
-->
``` http
DELETE https://graph.microsoft.com/v1.0/admin/edge/internetExplorerMode/siteLists/7cf831d2-8a9b-4826-b120-911566f6fd6a/sharedCookies/07b4cc32-237f-4a1a-9d7f-531efc26220e
```


#### Response
The following is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```

### Example 2: Delete a shared cookie that was previously published

#### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "delete_browsersharedcookie",
  "sampleKeys": ["7cf831d2-8a9b-4826-b120-911566f6fd6a", "07f4030f-45ff-4ad1-9277-3b8f6ee74141"]
}
-->
``` http
DELETE https://graph.microsoft.com/v1.0/admin/edge/internetExplorerMode/siteLists/7cf831d2-8a9b-4826-b120-911566f6fd6a/sharedCookies/07f4030f-45ff-4ad1-9277-3b8f6ee74141
```


#### Response
The following is an example of the response where the **status** has changed to `pendingDelete` but the shared cookie is still published. You must publish the shared cookie to fully remove it from the site list.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.browserSharedCookie"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "status": "pendingDelete",
    "id": "07f4030f-45ff-4ad1-9277-3b8f6ee74141",
    "hostOrDomain": "www.microsoft.com",
    "sourceEnvironment": "internetExplorer11",
    "displayName": "Microsoft Cookie",
    "path": "/",
    "hostOnly": true,
    "comment": "A cookie for microsoft.com",
    "lastModifiedDateTime": "2022-06-29T11:38:39.6732721-04:00",
    "createdDateTime": "2022-06-29T11:32:39.673272-04:00",
    "deletedDateTime": "2022-06-29T11:38:39.673272-04:00",
    "lastModifiedBy": {
        "user": {
            "id": "f6ff107e-bc40-4918-a432-8d7b60030a7c",
            "displayName": "Joe Smith"
        },
        "application": null
    },
    "history": []
}
```
