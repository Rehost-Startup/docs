# Quickstart

> This tutorial will show you how to register a compute machine, deploy a docker-compose app and use hot-reload for development.

## Content
1. Install Rehost CLI
2. Register Compute Machine
3. Deploy an App
4. Update App using Hot-Reload

## 1. Install Rehost CLI

Please refer to the [Installation Page](/getting-started/installation.md) section for instructions on installing the Rehost CLI.

## 2. Register Compute Machine

Here, you will need SSH access into your remote compute machine.
1. SSH into the machine
2. Download a sample `rehostmachine.yml` file from `TODO`. 
3. Edit `rehostmachine.yml` file and replace `<username>` with your username:

```
version: 1

label: '<username>.personal.gcp'
memory: '2gb'
disk: '256gb'
```

The `memory` and `disk` attributes play no role in deployment. These attributes are simply for information purpose. You can set them as you want. Replace `<username>` with your account username. By default, a team named `personal` is created for you when you sign-up for the first time.

4. Run `rh machine register` to register this machine.
5. Run `rh machine up` to turn on your machine in the network.
6. Leave this process running and close the SSH connection.

## 3. Deploy an App
1. On your localmachine, download this example docker project from github: `TODO`
2. Edit rehostapp.yml file:

```
version: 1

label: '<username>.personal.dockerapp'
urls:
  - "<username>.reactapp:80"
app_type: 'docker-compose'
machines:
  - "<username>.personal.gcp"
```

Replace `<username>` with your account username. You can replace `personal` with the team you want to register this app with too. By default, a team named `personal` is created for you when you sign-up for the first time.

This configuration will deploy this app on the machine `<username>.personal.gcp`. This will also generate a url: `https://<username>.reactapp.rehost.in` that will redirect all requests to internal port 80 where the docker application will be running.

3. Deploy this app by running `rh app deploy`. The app will be deployed in a minute and you can monitor the logs of your app in your dashboard.

## 4. Use Hot-Reload for Development
1. Start a hot-reload session using `rh app hot-reload`. Keep this terminal alive and open the URL: `https://<username.reactapp.rehost.in` in your browser.
2. Edit title of your app by editing `TODO` and add "General Kenobi" on line `TODO`. Save your file and reload the webpage. The changes should be live.
3. Lets try installing a package and using it. Run `npm i TODO`. Next, edit `src/TODO.js` file and save it. Finally, in your shell where you started the hot-reload, hit `ctrl+r` to hard-reload your app. It usually takes 20-30 seconds for app to completely restart from scratch and your changes should be live again.

If you have any feedback regarding this documentation, feel free to reach out to us on [Discord](https://discord.gg/RnkBxDJJhQ).

