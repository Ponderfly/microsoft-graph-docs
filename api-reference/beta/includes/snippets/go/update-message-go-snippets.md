---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewMessage()
subject := "subject-value"
requestBody.SetSubject(&subject) 
body := graphmodels.NewItemBody()
content := "content-value"
body.SetContent(&content) 
requestBody.SetBody(body)
inferenceClassification := graphmodels.OTHER_INFERENCECLASSIFICATIONTYPE 
requestBody.SetInferenceClassification(&inferenceClassification) 

result, err := graphClient.Me().MessagesById("message-id").Patch(context.Background(), requestBody, nil)


```