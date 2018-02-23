# Demo NuGet Server

A demo for a custom [NuGet Server](https://www.nuget.org/packages/NuGet.Server/).

## Configure the Packages folder

You can configure the folder which contains your packages. The `web.config` file contains a new
`appSetting`, named `packagesPath`. When the key is omitted or left blank, the packages folder is
the default `~/Packages`. You can specify an **absolute path**, or a **virtual path**.

```
<appSettings>
    <add key="packagesPath" value="C:\MyPackages" />
</appSettings>
```

## Add Packages to the Packages folder

 You can add and delete packages to the lightweight feed using `NuGet.exe`. The `web.config` file
 contain a new `appSetting`, named `apiKey`. When the key is omitted or left blank, pushing packages
 to the feed is disabled. Setting the `apiKey` to a value (ideally a strong password) enables pushing
 packages using `NuGet.exe`.

```
<appSettings>
    <add key="requireApiKey" value="true" />
    <add key="apiKey" value="" />
</appSettings>
```

If however your server is already secured and/or you do not require an api key to perform this
operation, set the `requireApiKey` value to **false**.