# AWS Request Signing Interceptor

An AWS request signing interceptor for arbitrary HttpRequests.

This enables you to sign requests to any service that leverages SigV4 this means you have a client that can access any Amazon or AWS Service or Amazon API Gateway backed service.

This library is based on the archived [AWS Interceptor](https://github.com/amazon-archives/aws-request-signing-apache-interceptor) library, but uses the AWS SDK for Java version 2.X.X.

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This project is licensed under the Apache-2.0 License.

## Usage
```java
Aws4Signer signer = Aws4Signer.create();

HttpRequestInterceptor interceptor = new AwsRequestSigningApacheInterceptor(serviceName, signer, credentialsProvider, AWS_REGION);

HttpClients.custom()
        .addInterceptorLast(interceptor)
        .build();
```

## Examples

See [tests](src/test/java/io/github/acm19/aws/interceptor/test) for examples of requests.

## Contributors

Many thanks to [acm19](https://github.com/acm19), who shepharded the update to the archived library in the GitHub repo [https://github.com/acm19/aws-request-signing-apache-interceptor](https://github.com/acm19/aws-request-signing-apache-interceptor/issues/16).