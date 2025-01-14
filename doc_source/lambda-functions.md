# Configuring AWS Lambda functions<a name="lambda-functions"></a>

You can use the AWS Lambda API or console to create functions and configure function settings\. The workflow to create a function is different for a function deployed as a [container image](configuration-images.md) and for a function deployed as a [\.zip file archive](configuration-function-zip.md)\. 

After you create the function, you can configure settings for many [function capabilities and options ](configuration-function-common.md) such as permissions, environment variables, tags, and layers\.

To keep secrets out of your function code, store them in the function's configuration and read them from the execution environment during initialization\. [Environment variables](configuration-envvars.md) are always encrypted at rest, and can be encrypted client\-side as well\. Use environment variables to make your function code portable by removing connection strings, passwords, and endpoints for external resources\.

[Versions and aliases](configuration-versions.md) are secondary resources that you can create to manage function deployment and invocation\. Publish [versions](configuration-versions.md) of your function to store its code and configuration as a separate resource that cannot be changed, and create an [alias](configuration-aliases.md) that points to a specific version\. Then you can configure your clients to invoke a function alias, and update the alias when you want to point the client to a new version, instead of updating the client\.

As you add libraries and other dependencies to your function, creating and uploading a deployment package can slow down development\. Use [layers](configuration-layers.md) to manage your function's dependencies independently and keep your deployment package small\. You can also use layers to share your own libraries with other customers and use publicly available layers with your functions\.