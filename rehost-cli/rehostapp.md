# rehostapp.yml

This is a configuration file used to save compute machine on Rehost Servers. Once it is saved on the server, any app can deployed on this machine using the CLI.

**Note:** This file must be placed in the root (`/`) directory of your app.

Here's what it looks like:

```
version: 1

label: 'john.personal.webapp'
app_type: 'docker-compose'
urls:
  - 'john.personal.webapp:80'
machines:
  - 'john.personal.vm'

```

* `version (required)`: It is used to identify the syntax used. In case of any updates to this configuration syntax in future, the version number will help Rehost in maintaining support for previous versions.

* `label (required)`: It is used to give a **unique identifier** to the app. The label must follow the following syntax:

```
<username>.<teamname>.<label>
```
Please refer to [Rehost Basics](/getting-started//basics.md) for complete information on naming conventions.

The complete label must be unique in the system, ie, two teams can have an app with the same label since team names are different.

Moreover, defining the `teamname` will make sure that the app can be used by the members of the given team only, ie, only those team members will be able to update the configuration and deploy this app.

Teams can be managed using the dashboard [here](https://rehost.in/dashboard/team).

* `app_type (required)`: This is used to identify the type of app running and is restricted to the following values:

  * `docker-compose`

The `app_type` lets Rehost identify the app and the commands used to manage the processes that run it. Every `app_type` expects a codebase in a format that is defined [here](#).

* `machines (required)`: This is a list of labels of [Rehost Machines](/rehost-cli/rehostmachine.md) where this app will be deployed.

* `urls (optional)`: This is a list of subdomains mapped to port numbers of the running app. All API requests on the generated url are mapped to specified port numbers. It exepects a list of strings that are in the following format:

```
<subdomain>:<number>
```
The subdomain provided will finally generate a HTTPS url in the format: `https://<subdomain>.rehost.in`. It is a safe practise to format the subdomain in the format: `<username>.<teamname>.<applabel>` to avoid conflicting subdomains.


