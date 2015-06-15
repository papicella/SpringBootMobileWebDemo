<h1> IBM Bluemix - Spring Boot Mobile / Web demo </h1>

The following demo shows how to use Spring Boot to render the correct view depending on the device being used to access the application. It uses
Spring Boot mobile support to do this.

Mobile View

![alt tag](https://dl.dropboxusercontent.com/u/15829935/bluemix-docs/images/mobile-springcloud.png)

View From a Web Browser

![alt tag](https://dl.dropboxusercontent.com/u/15829935/bluemix-docs/images/browser-springcloud.png)

<h2> Steps to Deploy </h2>

- Clone code as follows

```
> git clone https://hub.jazz.net/project/pasapples/SpringBootMobileWeb.git
```

- package as shown below

```
> mvn package
```

- Deploy using manifest.yml ensuring you edit it to specify a unique name

manifest.yml

```
applications:
 - name: pas-mobile-web
   memory: 512M
   instances: 1
   path: SpringBootMobileWebDemo-0.0.1-SNAPSHOT.jar
   host: pas-mobile-web
   domain: mybluemix.net
```

deploy command

```
cf push -f manifest.yml
```