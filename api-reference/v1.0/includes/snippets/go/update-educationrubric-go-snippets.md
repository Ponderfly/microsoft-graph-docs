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


requestBody := graphmodels.NewEducationRubric()
displayName := "Example Credit Rubric after display name patch"
requestBody.SetDisplayName(&displayName) 

result, err := graphClient.Education().Me().RubricsById("educationRubric-id").Patch(context.Background(), requestBody, nil)


```