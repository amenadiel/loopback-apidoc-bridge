## LoopBack / Apidocs connector template

This is a working example that builds on top of [loopback-example-app](https://github.com/strongloop/loopback-example-app) 
adding an template to use [Loopback](http://loopback.io/)'s raw resources to create an [apiDoc](http://apidocjs.com/) front-end page. [See demo](http://amenadiel.github.io/loopback-apidocs-bridge/).

The purpose of this "bridging" feature is to provide a static, read-only API documentation, 
for those cases when you don't want to promote the current swagger-like, interactive API, which might either be too confusing or too open.


### Replacing contents of /client 

The original [loopback-example-app](https://github.com/strongloop/loopback-example-app) includes an example webpage whose files are at /client. 

Besides the apiDoc template included in this repo, the actual /client folder contents were replaced with the results of regenerating apiDocs files. I did this because it doesn't interfere with Loopback's app whatsoever, and uses the current fallback route to display apiDoc UI at the project root http://localhost:3000/. 

The same procedure (dropping /client folder in place) will work for any existing Loopback 2.0 app. It will just figure out the models and endpoints from existing resources url.

### Configure and run the application

Start the application back-end by running the following command:

```
$ git clone git@github.com:amenadiel/loopback-apidocs-bridge.git
$ cd loopback-apidocs-bridge
$ sudo npm install
$ slc run .
```

Now open your browser and point it to
[http://127.0.0.1:3000](http://127.0.0.1:3000) to access ApiDocs generated UI. The Swagger-like explorer will still be found at [http://127.0.0.1:3000/explorer](http://127.0.0.1:3000/explorer)



If you ever need to regenerate ApiDocs files and folders, just do:

```
$ sudo npm install -g apidoc
$ apidoc  -o client/ -t apidoc_template/
```

