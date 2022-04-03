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
2. Download a sample `rehostdevice.yml` file using `wget TODO`. 
3. Edit `rehostdevice.yml` file using `nano rehostdevice.yml`:

```
version: 1

label: '<username>.personal.StarKiller'
memory: '2gb'
disk: '256gb'
```

The `memory` and `disk` attributes play no role in deployment. These attributes are simply for information purpose. You can set them as you want. Replace `<username>` with your account username. You can replace `personal` with the team you want to register this device with too. By default, a team named `personal` is created for you when you sign-up for the first time.

4. Run `rh device register` to register this device.
5. Run `rh device up` to turn on your device in the network.
6. Leave this process running and close the SSH connection.

## 3. Deploy an App
1. On your localmachine, download this example docker project from github: `https://TODO`
2. Edit rehostapp.yml file:

```
version: 1

label: '<username>.personal.dockerapp'
urls:
  - "<username>.dockerapp:80"
app_type: 'docker-compose'
machines:
  - "<username>.personal.StarKiller"
```

Replace `<username>` with your account username. You can replace `personal` with the team you want to register this device with too. By default, a team named `personal` is created for you when you sign-up for the first time.

This configuration will deploy this app on the device `<username>.personal.StarKiller`. This will also generate a url: `https://dep1.rehost.in` that will redirect all requests to internal port 80 where the docker application will be running.

3. Deploy this app by running `rh app deploy`. The app will be deployed in a minute and you can monitor the logs of your app in your dashboard.

## 4. Use Hot-Reload for Development
1. Start a hot-reload session using `rh app hot-reload`. Keep this terminal alive and open the URL: `https://dep1.rehost.in` in your browser.
2. Edit title of your app by editing `src/TODO.html` and add "General Kenobi" on line `TODO`. Save your file and reload the webpage. The changes should be live.
3. Lets try installing a package and using it. Run `npm i TODO`. Next, edit `src/TODO.js` file and save it. Finally, in your shell where you started the hot-reload, hit `ctrl+r` to hard-reload your app. It usually takes 20-30 seconds for app to completely restart from scratch and your changes should be live again.

If you have any feedback regarding this documentation, feel free to reach out to us on Discord.

