# Installation - Rehost CLI

The CLI is available on [Windows](getting-started/installation?id=windows), [Linux](getting-started/installation?id=linux) and [Mac](getting-started/installation?id=mac). 

## CLI Installation

### Mac
Rehost is coming soon to the Mac.

### Windows
* **Optional**: Docker is required on the compute machine where apps will be deployed. Install Docker using [official Docker(Windows) instructions](https://docs.docker.com/desktop/windows/install/)

* Download the zipped binaries from here [Rehost CLI - Windows](https://github.com/Hive-Space/docs/releases/download/v0.3/rehostcli-win-0.3.zip)
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
* **Optional**: Docker is required on the compute machine where apps will be deployed. Install Docker using [official Docker(Linux) instructions](https://docs.docker.com/engine/install/)
* Download zipped binaries using:

```
wget -o rehost-cli.zip https://github.com/Hive-Space/docs/releases/download/v0.3/rehostcli-linux-0.3.zip
```

* Extract the downloaded files:

```
# Install unzip if not already installed (OPTIONAL)
sudo apt-get install unzip

# Extract the downloaded files
unzip rehost-cli.zip
```

* Move the extracted files and give executable permissions:

```
mv bin/* /bin/*
chmod +x /bin/rh
chmod +x /bin/rhbkg
chmod +x /bin/rhupdate
```

Now, to use the CLI, use `sudo` to get root access and run `sudo rh -v` to verify if CLI was installed successfully.

* Finally, delete the downloaded files:

```
rm -rf rehost-cli.zip
rm -rf bin
```

* **Uninstall**:
Simply removing the binaries will clean the system of any Rehost CLI files:

```
rm -rf /bin/rh
rm -rf /bin/rhbkg
rm -rf /bin/rhupdate
```
