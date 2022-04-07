# Installation - Rehost CLI

The CLI is available on [Windows](getting-started/installation?id=windows), [Linux](getting-started/installation?id=linux) and [Mac](getting-started/installation?id=mac). 

## CLI Installation

### Mac
* **Optional**: Docker is required on the compute machine where apps will be deployed. Install Docker using [official Docker(Linux) instructions](https://docs.docker.com/get-docker/). Finally, install [Docker-Compose](https://docs.docker.com/compose/install/) to leverage complete Docker functionality.
* Download zipped binaries from [the link](https://github.com/Rehost-Startup/docs/releases/download/v0.4/rehostcli-macos-0.4.zip) and unzip it.

* The extracted content comprises a single folder `rehost`. Move this folder to any location where you prefer saving the CLI executables. Then, in the parent of `rehost`, run the following commands to install the CLI:

```
# give executable permissions
sudo chmod +x rehost/bin/rh
sudo chmod +x rehost/bin/rhbkg
sudo chmod +x rehost/bin/rhupdate

# initialize CLI config directory
sudo mkdir /etc/rehost
sudo chown -R $(whoami) /etc/rehost/

# Update Path variable
echo "export PATH=$(pwd)/rehost/bin:$PATH" >> ~/.bash_profile
```

Now, close this terminal session and test if the CLI was installed successfully. Check the version:

```
rh -v
```

* **Uninstall**:
Simply removing the binaries will clean the system of any Rehost CLI files:

```
rh logout
rh clean
sudo rm -rf /etc/rehost
```

* Delete the extracted files where the `bin` folder was extracted.

* Finally, update the `PATH` variable in the `~/.bash_profile` file. Remove the line that contains the location where the binaries were extracted.


### Windows
* **Optional**: Docker is required on the compute machine where apps will be deployed. Install Docker using [official Docker(Windows) instructions](https://docs.docker.com/desktop/windows/install/). Finally, install [Docker-Compose](https://docs.docker.com/compose/install/) to leverage complete Docker functionality.

* Download the zipped binaries from here [Rehost CLI - Windows](https://github.com/Rehost-Startup/docs/releases/download/v0.4/rehostcli-win-0.4.zip)
* Extract the zip. Copy the `rehost` folder and paste it in `C:\` directory.
* Update windows environment variables by adding `C:\rehost\bin` to the `$PATH` variable.
  * Search for `Advanced System Settings` in Windows search or go to `This PC>Properties>Advanced System Settings`.
  * Go to `Advanced` Tab and click `Environment Variables...`. It should be present at the bottom.
  * In the `System variables` section, select `Path` variable entry and click on `edit`.
  * Create a `New` entry and set the value to `C:\rehost\bin`.
  * Click on `Ok` recursively to save changes and start a new terminal session. Run `rh -v` to verify if CLI was installed successfully.

* **Uninstall**:
Simply removing the binaries will clean the system of any Rehost CLI files. Delete the `C:\rehost` folder and remove the Environment Variables entry from the system. This process is the same as during creating the environment variable.


### Linux
* **Optional**: Docker is required on the compute machine where apps will be deployed. Install Docker using [official Docker(Linux) instructions](https://docs.docker.com/engine/install/). Finally, install [Docker-Compose](https://docs.docker.com/compose/install/) to leverage complete Docker functionality.
* Download zipped binaries from [the link](https://github.com/Rehost-Startup/docs/releases/download/v0.4/rehostcli-linux-0.4.zip) or using command line:

```
wget https://github.com/Rehost-Startup/docs/releases/download/v0.4/rehostcli-linux-0.4.zip
```

* Install the CLI:

```
# (OPTIONAL): Install unzip if not already installed
sudo apt-get install unzip

# Extract the downloaded files
unzip rehostcli-linux-0.4.zip

# Move the extracted files
sudo mv rehost/bin/rh /bin/rh
sudo mv rehost/bin/rhbkg /bin/rhbkg
sudo mv rehost/bin/rhupdate /bin/rhupdate

# give executable permissions
sudo chmod +x /bin/rh
sudo chmod +x /bin/rhbkg
sudo chmod +x /bin/rhupdate
sudo mkdir /etc/rehost
sudo chown -R $(whoami) /etc/rehost/

# delete the downloaded files:
rm -rf rehostcli-linux-0.4.zip
rm -rf rehost
```

* **Uninstall**:
Simply removing the binaries will clean the system of any Rehost CLI files:

```
rh logout
rh clean
sudo rm -rf /bin/rh
sudo rm -rf /bin/rhbkg
sudo rm -rf /bin/rhupdate
sudo rm -rf /etc/rehost
```
