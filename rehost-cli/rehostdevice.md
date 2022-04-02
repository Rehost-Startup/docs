# rehostdevice.yml

This is a configuration file used to save compute machine on Rehost Servers. Once it is saved on the server, any app can deployed on this machine using the CLI.

Here's what it looks like:

```
version: 1

label: 'john.jedi.StarKiller'
memory: '8gb'
disk: '256gb'
```

* `version (required)`: It is used to identify the syntax used. In case of any updates to this configuration syntax in future, the version number will help Rehost in maintaining support for previous versions.

* `label (required)`: It is used to give a **unique identifier** to the machine. The label must follow the following syntax:

```
<username>.<teamname>.<label>
```
Please refer to [Rehost Basics](/getting-started//basics.md) for complete information on naming conventions.

The complete label must be unique in the system, ie, two teams can have a device with the same label since team names are different.

Moreover, defining the `teamname` will make sure that the device can be used by the members of the given team only, ie, only those team members will be able to update the configuration of this machine. And, only those team member will be able to deploy apps on this machine.

Teams can be managed using the dashboard [here](https://rehost.in/dashboard/team).

* `memory (optional)`: This is for information purpose only and currently serves no functional use in deployment process. If defined, it will be stored in the database associated with the label. It exepects as string in the following format:

```
<number><unit>

where unit can be 'mb' or 'gb'. For example: '8gb', '512mb', etc.
```

* `disk (optional)`: This is for information purpose only and currently serves no functional use in deployment process. If defined, it will be stored in the database associated with the label. It exepects as string in the following format:

```
<number><unit>

where unit can be 'mb' or 'gb'. For example: '8gb', '512mb', etc.
```

