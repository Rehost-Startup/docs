# Rehost Basics

## Terminology

Here are terms used throughout the Rehost EcoSystem:
* **Rehost App**: This refers to source files of your app that will be deployed. `rehostapp.yml` file must be present in the root directory of your source files. It belongs to a team and cannot exist independently.

* **Rehost Device**: This refers to remote compute machine where the `Rehost Apps` will be deployed. `rehostdevice.yml` is used to register on Rehost. It belongs to a team and cannot exist independently.

## Naming Teams, Apps and Devices

* **Team Name**: A team name is unique in the Rehost system. A team name that you provide while creating or editing a team on dashboard is saved in the following format:

```
<your_username>.<team_label>
```
The team label serves as a access-barrier and `Rehost Apps` and `Rehost Devices` belong to a team.

* **App Name**: An app name is unique in the Rehost system. It must be saved in the following format:

```
<team_name>.<app_label>

Please note that <team_name> itself follows the format that is defined above.
A typical app name would look like:
<username>.<team_label>.<app_label>
```
The app label serves as an access-barrier and belongs to the team as defined in the label.

* **Device Name**: A device name is unique in the Rehost system. It must be saved in the following format:

```
<team_name>.<device_label>

Please note that <team_name> itself follows the format that is defined above.
A typical app name would look like:
<username>.<team_label>.<device_label>
```
The device label serves as an access-barrier and belongs to the team as defined in the label.
