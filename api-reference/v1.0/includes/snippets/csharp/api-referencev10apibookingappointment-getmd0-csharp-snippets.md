---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var result = await graphClient.Solutions.BookingBusinesses["{bookingBusiness-id}"].Appointments["{bookingAppointment-id}"].GetAsync();


```