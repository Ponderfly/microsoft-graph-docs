---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewOnenoteSection()
displayName := "Section name"
requestBody.SetDisplayName(&displayName) 

result, err := graphClient.Me().Onenote().NotebooksById("notebook-id").Sections().Post(context.Background(), requestBody, nil)


```