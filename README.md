# Chat application

Red5 WebSocket chat application example.

The example `index.html` defaults to using a WebSocket connection to localhost on port 5080.

## Add the WebSocket filter servlet to webapps that require WebSocket support

```xml
        <filter>
            <filter-name>WebSocketFilter</filter-name>
            <filter-class>org.red5.net.websocket.server.WsFilter</filter-class>
            <async-supported>true</async-supported>
        </filter>
        <filter-mapping>
            <filter-name>WebSocketFilter</filter-name>
            <url-pattern>/*</url-pattern>
            <dispatcher>REQUEST</dispatcher>
            <dispatcher>FORWARD</dispatcher>
        </filter-mapping>
```

Build the application from the command line with

```sh
mvn package
```

Deploy your application by copying the war file into your `red5/webapps` directory. If the war file does not deploy withing a few minutes, this may indicate the war deployer bean is not created or running; a work-around is to expand the war contents into the webapps directory manually and restart Red5.

After deploy is complete, go to http://localhost:5080/chat/ in your browser (open two tabs if you want to chat back and forth on the same computer).

## Pre-compiled WAR

You can find [compiled artifacts via Maven](http://mvnrepository.com/artifact/org.red5.demos/chat)

[Direct Download](https://github.com/Red5/red5-websocket-chat/releases/download/v2.0.19/chat-2.0.19.war)
