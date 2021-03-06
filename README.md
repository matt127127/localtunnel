# localtunnel-https

localtunnel-https exposes your localhost to the world for easy testing and sharing! No need to mess with DNS or deploy just to have others test out your changes.

Great for working with browser testing tools like browserling or external api callback services like twilio which require a public url for callbacks.

Will connect to your local dev machine using tls (port 443)

## installation ##

```
npm install -g localtunnel-https
```

This will install the localtunnel-https module globally and add the 'lt' client cli tool to your PATH.

## use ##

Assuming your local server is running on port 8000, just use the ```lt``` command to start the tunnel.

```
lt --port 8000
```

Thats it! It will connect to the tunnel server, setup the tunnel, and tell you what url to use for your testing. This url will remain active for the duration of your session; so feel free to share it with others for happy fun time!

You can restart your local server all you want, ```lt``` is smart enough to detect this and reconnect once it is back.

### arguments

Below are some common arguments. See `lt --help` for additional arguments

* `-p, --port` Required, the port of the local host to connect on
* `--subdomain` request a named subdomain on the localtunnel-https server (default is random characters)
* `--local-host` proxy to a hostname other than localhost
* `-o` Open window when tunnel successful

You may also specify arguments via env variables.  E.x.

```
PORT=3000 lt
```
## License ##
MIT
