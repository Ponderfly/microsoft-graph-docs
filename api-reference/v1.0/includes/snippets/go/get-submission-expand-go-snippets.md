---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphconfig "github.com/microsoftgraph/msgraph-sdk-go/education"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestParameters := &graphconfig.EducationClasseItemAssignmentItemSubmissionItemRequestBuilderGetQueryParameters{
	Expand: [] string {"*"},
}
configuration := &graphconfig.EducationClasseItemAssignmentItemSubmissionItemRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

result, err := graphClient.Education().ClassesById("educationClass-id").AssignmentsById("educationAssignment-id").SubmissionsById("educationSubmission-id").Get(context.Background(), configuration)


```