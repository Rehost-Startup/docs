# Installation - Rehost CLI

The CLI is available on [Windows](getting-started/installation?id=windows), [Linux](getting-started/installation?id=linux) and [Mac](getting-started/installation?id=mac). 

## CLI Installation

### Mac
Rehost is coming soon to the Mac.

### Windows
* **Optional**: Docker is required on the compute machine where apps will be deployed. Install Docker using [official Docker(Windows) instructions](https://docs.docker.com/desktop/windows/install/). Finally, install [Docker-Compose](https://docs.docker.com/compose/install/) to leverage complete Docker functionality.

* Download the zipped binaries from here [Rehost CLI - Windows](https://github.com/Hive-Space/docs/releases/download/v0.4/rehostcli-win-0.4.zip)
* Make a folder named `rehost` in root of `C:` directory and unzip all the files here, ie, `bin` should be present in `C:\rehost` directory and likewise for all other files and folders that are extracted.
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
* Download zipped binaries using:

```
wget https://github.com/Hive-Space/docs/releases/download/v0.4/rehostcli-linux-0.4.zip
```

* Extract the downloaded files:

```
# Install unzip if not already installed (OPTIONAL)
sudo apt-get install unzip

# Extract the downloaded files
unzip rehostcli-linux-0.4.zip
```

* Move the extracted files and give executable permissions:

```
sudo mv bin/rh /bin/rh
sudo mv bin/rhbkg /bin/rhbkg
sudo mv bin/rhupdate /bin/rhupdate
sudo chmod +x /bin/rh
sudo chmod +x /bin/rhbkg
sudo chmod +x /bin/rhupdate
sudo mkdir /etc/rehost
sudo chown -R $(whoami) /etc/rehost/
```

Now, to use the CLI, use `sudo` to get root access and run `sudo rh -v` to verify if CLI was installed successfully.

* Finally, delete the downloaded files:

```
rm -rf rehostcli-linux-0.4.zip
rm -rf bin
```

* **Uninstall**:
Simply removing the binaries will clean the system of any Rehost CLI files:

```
sudo rm -rf /bin/rh
sudo rm -rf /bin/rhbkg
sudo rm -rf /bin/rhupdate
sudo rm -rf /etc/rehost
```
