# Server Readme

This is a documentation of helpful information and documentation about the server usage.

## How Tos

### Screens

We use multiple screens to manage different services.
Please load services in dedicated screens after a restart of a service or of the server.

* List available screens: `screen -list`
* Create a new screen: `screen -dmS myScreen`
* Enter screen with ID: `screen -r <NUMBER>`
* Leave screen: `ctrl+a  d`
* Rename a screen: `ctr+a : sessionname <NAME>`

### Update node-wot

* walk into /home/vserver/thingweb.node-wot
* update repo: "git pull"
* build: "npm ci", "npm run build"

e.g., start TestThing again in a screen

`wot-servient testthing.js counter.js coffee-machine.js > ../logs/TestThing-004.log 2>&1`

OR

`node packages/cli/dist/cli.js examples/testthing/testthing.js examples/scripts/counter.js examples/scripts/smart-coffee-machine.js `

### Quickstart Things

We now use [pm2](https://pm2.keymetrics.io/) to automatically start and manage the Quickstart Things. This avoids the use of screens.

- `pm2 start app.js` will start each Thing
- `pm2 monit` will show currently running Things

### Start wot-fxui (in background / server mode)

cd wot-fxui/
./gradlew -b jpro.gradle jproRestart


## Web Server 

We use Apache 2

HTMLs are available at /var/www/html

## Redirects

The current redirects in place are:

```
<VirtualHost *:80>
    ServerName plugfest.thingweb.io
    RedirectPermanent /playground-new https://playground.thingweb.io
    RedirectPermanent /index.html https://www.thingweb.io/services
</VirtualHost>
```

## Open Ports

Eclipse Thingweb uses a cloud instance provided by Eclipse Foundation to host its services on [plugfest.thingweb.io](http://plugfest.thingweb.io/). 
In order to function as a TCP/UDP server, we have some ports open to the public Internet.
These are documented below, alongside the service using the port.

### TCP Ports

| TCP PORT | Service |
|----------|---------|
|   80     |  Apache Web Server |
|   8080   |  -       |
|   8081   |  -       |
|   8082   |  -        |
|   8083   |  Example Things (HTTP) |
|   8084   |  -       |
|   8085   |  -       |
|   8086   |  -       |
|   8087   |  -       |
|   8088   |  WoT FX UI |
|   8089   |  -       |
|   5685   |  -       |


### UDP Ports

| UDP PORT | Service |
|----------|---------|
|   5680   |  -       |
|   5681   |  -       |
|   5682   |  -       |
|   5683   |  Example Things (CoAP) |
|   5684   |  -       |
|   5686   |  -       |
|   5687   |  -       |
|   5688   |  -       |
|   5689   |  -       |
