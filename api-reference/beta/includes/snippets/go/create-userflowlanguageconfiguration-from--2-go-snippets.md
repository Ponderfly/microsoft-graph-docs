---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/Identity/B2cUserFlows/Item/Languages/Item"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewLanguage()
additionalData := map[string]interface{}{
	isEnabled := false
requestBody.SetIsEnabled(&isEnabled) 
}
requestBody.SetAdditionalData(additionalData)

graphClient.Identity().B2cUserFlowsById("b2cIdentityUserFlow-id").LanguagesById("userFlowLanguageConfiguration-id").Put(context.Background(), requestBody, nil)


```