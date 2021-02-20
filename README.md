# Identity Server 4 - Walk through #

## Step 1: create a simple IdentityServer4 and check out the openid-config document ##

Add new .net core web app `dotnet new web`

Add IdentityServer4 package `dotnet add IdentityServer4`

Add to `ConfigureServices` method

```csharp
services.AddIdentityServer()
    .AddInMemoryClients(new List<Client>())
    .AddInMemoryIdentityResources(new List<IdentityResource>())
    .AddInMemoryApiResources(new List<ApiResource>())
    .AddInMemoryApiScopes(new List<ApiScope>())
    .AddTestUsers(new List<TestUser>())
    .AddDeveloperSigningCredential();
```

Add to `Configure` method

```csharp
    app.UseRouting();
    app.UseIdentityServer();
```

Start the server `dotnet run`

Go to https://localhost:5001/.well-known/openid-configuration and you should see the `well-known` openid connect config doc for this API, similarly, this is the one for Google https://accounts.google.com/.well-known/openid-configuration

> Note: checkout other .net core project template here https://github.com/IdentityServer/IdentityServer4.Templates
## Step 2: create a simple IdentityServer4 and check out the openid-config document ##




