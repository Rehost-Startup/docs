# Quickstart

> This tutorial will show you how to register a compute machine, deploy a React app and use hot-reload for development.

## Content
1. [Install Rehost CLI](getting-started/quickstart?id=_1-install-rehost-cli)
2. [Register Compute Machine](/getting-started/quickstart?id=_2-register-compute-machine)
3. [Deploy an App](/getting-started/quickstart?id=_3-deploy-an-app)
4. [Update App using Hot-Reload](/getting-started/quickstart?id=_4-use-hot-reload)

## 1. Install Rehost CLI

Please refer to the [Installation Page](/getting-started/installation.md) section for instructions on installing the Rehost CLI.

## 2. Register Compute Machine

Here, you will need SSH access into your remote compute machine.
1. SSH into the machine
2. Create a new file `rehostmachine.yml` anywhere on the remote machine with the following content: 

```
version: 1

label: '<username>.personal.vm'
memory: '2gb'
disk: '256gb'

```

The `memory` and `disk` are optional attributes and play no functional role in deployment. These attributes are simply for information purpose. You can set them as you want. Replace `<username>` with your account username. By default, a team named `personal` is created for you when you sign-up for the first time.

3. In the parent directory of `rehostmachine.yml`, run `rh machine save` to register this machine.
4. Next, run `rh machine up` to turn on your machine in the network. Leave this process running and close the SSH connection.

## 3. Deploy an App
1. Clone this repository

```
git clone https://github.com/Rehost-Startup/template-react.git

```
2. In the root directory of the codebase, edit `rehostapp.yml` file:

```
version: 1

label: '<username>.personal.template-react'
urls:
  - "<username>.personal.react:80"
app_type: 'docker-compose'
machines:
  - "<username>.personal.vm"

```

Here, replace `<username>` with your Rehost Username.

3. Finally, run the following command on local machine to deploy the project:

```
rh app deploy

```
You can monitor the logs of build and app in Rehost Dashboard.

## 4. Use Hot-Reload

In the parent directory of `rehostapp.yml`, run:

```
rh app hot-reload

```

Edit `/src/App.js` file and save to see the changes go live instantly.

<hr/>

In the window where the hot-reload session is running, you can further use the following commands to send specific changes to the running app:

```
shift+r: Soft-Reload. This will reload the app without rebuilding the app. Any changes to environment or dependencies will not be picked up.
ctrl+r: Hard-Reload. This rebuilds the environment and all changes in environment, including package depencies, will be picked up.

```

If you have any feedback regarding this documentation, feel free to reach out to us on [Discord](https://discord.gg/RnkBxDJJhQ).
Note: Only 1 user can use hot-reload at a time for a given deployment.

