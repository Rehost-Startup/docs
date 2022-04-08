# rh app hot-reload

```
Usage:
rh app hot-reload [OPTIONS]

OPTIONS:
-s, --soft    Restarts docker container runs your app for every change.
-h, --hard    Stops, rebuilds and starts the app for every change.

```
The changes are accumulated and sent periodically every 1.5s.
Starts tracking changes in the current directory and the remote directory that contains the app files.

* **Default-Reload**: Triggered on changes in file. This will simply refelect the changes on remote machine. Its useful in case the remote-machine has volumes mounted and the docker environment is designed to fetch changes in the mounted volume. Read through [our templates](https://rehost.in/templates) for a demo.
* **Soft-Reload**: This will reload the app without rebuilding the app. Any changes to environment or dependencies are not be picked up.
* **Hard-Reload**: This rebuilds the app and all changes in environment and package dependencies are picked up.

After starting hot-reload in any mode, you can trigger soft-reload by pressing `shift+r` and hot-reload by pressing `ctrl+r` in the terminal.

Note: 
* `rehostapp.yml` should be present in the current directory. 
* Only 1 user can use hot-reload at a time for a given deployment.




