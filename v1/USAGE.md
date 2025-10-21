<!-- Start SDK Example Usage [usage] -->
```go
package main

import (
	"context"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/v1"
	"log"
	"os"
)

func main() {
	ctx := context.Background()

	s := squadcastsdk.New(
		squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
	)

	res, err := s.Analytics.GetOrganization(ctx, "<value>", "<value>", nil, nil)
	if err != nil {
		log.Fatal(err)
	}
	if res.Object != nil {
		// handle response
	}
}

```
<!-- End SDK Example Usage [usage] -->