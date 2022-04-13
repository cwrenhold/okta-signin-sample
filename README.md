# Okta Sign-in Sample

This was built using Okta's [ASP.NET Core guide](https://developer.okta.com/docs/guides/sign-into-web-app-redirect/asp-net-core-3/main/).

## Requirements

Despite the guide being for ASP.NET Core 3.0, this was actually changed to ASP.NET Core 5.0, although this didn't require any changes to be made in the process.

* .NET 5.0 SDK
* ASP.NET Core 5.0 SDK
* Docker (if you want to run this via Docker)
* A configured application in Okta

I have specifically not included the credentials for Okta for obvious reasons, these can be added into `appSettings.json` file in a format like this:

```json
"Okta": {
  "OktaDomain": "<INSERT YOUR OKTA DEV URL HERE, INCLUDING HTTPS://",
  "ClientId": "<INSERT YOUR CLIENT ID HERE>",
  "ClientSecret": "<INSERT YOUR CLIENT SECRET HERE>",
  "AuthorizationServerId": "default"
}
```

## Notes

This has been configured to use port 30469 for HTTP, and port 44345 for SSL. If you configure a new Okta application for this, ensure that the correct ports are set in the callback URLs. You can change these ports by updating the `launchSettings.json` file, under Properties.

## Claims visible after configuration

After following the guide and logging in, here are the claims which are returned, values have been hidden in case anything is sensitive.

![Claims returned screenshot](claims%20returned.png)