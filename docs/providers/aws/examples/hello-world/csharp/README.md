<!--
title: Hello World C# Example
menuText: Hello World C# Example
description: Create a C# Hello World Lambda function
layout: Doc
-->

<!-- DOCS-SITE-LINK:START automatically generated  -->
### [Read this on the main serverless docs site](https://www.serverless.com/framework/docs/providers/aws/examples/hello-world/csharp/)
<!-- DOCS-SITE-LINK:END -->

# Hello World C# Example

Make sure `serverless` is installed. [See installation guide](../../../guide/installation.md).

## 1. Create a service
`serverless create --template aws-csharp --path myService` or `sls create --template aws-csharp --path myService`, where 'myService' is a new folder to be created with template service files.  Change directories into this new folder.

## 2. Build using .NET CLI tools and create zip package

```
dotnet restore
dotnet publish -c release

pushd bin/Release/netcoreapp1.0/publish
zip -r ./deploy-package.zip ./*
popd
```

`./build.sh` runs the dotnet restore and package commands then creates the zip file to upload to lambda.

## 3. Deploy
`serverless deploy` or `sls deploy`. `sls` is shorthand for the Serverless CLI command

## 4. Invoke deployed function
`serverless invoke --function hello` or `serverless invoke -f hello`

`-f` is shorthand for `--function`

In your terminal window you should see the response from AWS Lambda

```bash
{
    "Message": "Go Serverless v1.0! Your function executed successfully!",
    "Request": {
        "Key1": null,
        "Key2": null,
        "Key3": null
    }
}
```

Congrats you have just deployed and run your Hello World function!
