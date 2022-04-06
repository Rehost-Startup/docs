# Rehost Basics

## Terminology

Here are terms used throughout the Rehost EcoSystem:
* **Rehost App**: This refers to source files of your app that will be deployed. `rehostapp.yml` file must be present in the root directory of your source files. It belongs to a team and cannot exist independently.

* **Rehost Machine**: This refers to remote compute machine where the `Rehost Apps` will be deployed. `rehostmachine.yml` is used to register on Rehost. It belongs to a team and cannot exist independently.

## Naming Teams, Apps and Machines

* **Team Name**: A team name is unique in the Rehost system. A team name that you provide while creating or editing a team on dashboard is saved in the following format:

```
<username>.<team_label>
```
The team label serves as a access-barrier and `Rehost Apps` and `Rehost Machines` belong to a team.

* **App Name**: An app name is unique in the Rehost system. It must be saved in the following format:

```
<team_name>.<app_label>

Note: <team_name> itself follows the format that is defined above.
Eventually, a typical app name would look like:
<username>.<team_label>.<app_label>
```
The app label serves as an access-barrier and belongs to the team as defined in the label.

* **Machine Name**: A machine name is unique in the Rehost system. It must be saved in the following format:

```
<team_name>.<machine_label>

Note: <team_name> itself follows the format that is defined above.
Eventually, a typical machine name would look like:
<username>.<team_label>.<machine_label>
```
The machine label serves as an access-barrier and belongs to the team as defined in the label.

## Hot Reload App

Hot-Reload is designed for development purpose only. These changes are not permanent ,ie, the next a Rehost Machine comes in `Up` state, all changes made during hot-reload will be lost. To make these changes permanent, you need to use `rh app deploy` command.

## Lifecycle of a Rehost Machine

The lifecycle of a Rehost Machine is as follows:
1. `Save`: A Rehost Machine is saved using `rh machine save` command. It can also be updated using `rh machine save` command too.
2. `Status: Up`: A Rehost Machine is in `Up` state using `rh machine up` command. This is the state where it will download all Rehost Apps allocated to it and start running them.
3. `Status: Down`: A Rehost Machine is in `Down` state using `rh machine down` command. This is the state where it will stop running all Rehost Apps allocated to it, remove all docker containers and delete all local files. The images used by the Rehost Apps are not removed. They need to be manually removed or by using `docker system prune` command.
4. `Deleted`: A Rehost Machine can be deleted permanently by using `rh machine delete` command.

## Lifecycle of a Rehost App

The lifecycle of a Rehost App is as follows:
1. `Deploy`: A Rehost Machine is saved using `rh app deploy` command. It can also be updated using `rh app deploy` command too. When the requested Rehost Machines are in `Up` state, the app will be deployed on them.
2. `Deleted`: A Rehost Machine can be deleted permanently by using `rh machine delete` command.

## Troubleshooting

All CLI logs saved to a `default.log` file.

On Linux, this file can be found at `/etc/rehost/logs/default.log`.

On Windows, this file can be found at `C:\rehost\logs\default.log`.