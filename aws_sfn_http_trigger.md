# AWS Step Function, Go Lang, HTTP Trigger, Serverless Framework

Very simple example of the AWS step function which can be triggered via HTTP POST endpoint. It also shows how the request body is passed to the lambda as the input.

### Step function definition in serverless.yaml
```yml
stepFunctions:
  stateMachines:
    httpTriggerExample:
      events:
        - http:
            path: sfn/examples/http-trigger
            method: POST
      definition:        
        StartAt: PrintPayload
        States:
          PrintPayload:
            Type: Task
            Resource:
              Fn::GetAtt: [PrintPayloadLambda, Arn]
            End: true
```

### Simple lambda handler function (PrintPayloadLambda)
```go
func handler(ctx context.Context, in interface{}) (events.APIGatewayProxyResponse, error) {	
	fmt.Printf("Payload is = %+v\n", in)
	return http.Ok("done")
}
```

### Invoke the step function via HTTP
```bash
curl -XPOST <API_GATEWAY_URL>/sfn/examples/http-trigger \
    --header "Content-Type:application/json" \
    --data '{"offset": 99}'
```

Output:
```text
Payload is = map[offset:99]
```
