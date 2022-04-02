# rh app hot-reload

```
Usage:
rh app delete [OPTIONS]

OPTIONS:
-s, --soft    Restarts docker container runs your app for every change.
-h, --hard    Stops, rebuilds and starts the app for every change.

```
The changes are accumulated and sent periodically every 1.5s.
Starts tracking changes in the current directory and the remote directory that contains the app files.

After starting hot-reload in any mode, you can trigger soft-reload by pressing `shift+r` and hot-reload by pressing `ctrl+r` in the terminal.

Note: `rehostapp.yml` should be present in the current directory. 



