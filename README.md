# Graylog Plugin Openwire
Bridges `ActiveMQ->Graylog`

Provides an input for Graylog using the ActiveMQ client library. Openwire is the native protocol for ActiveMQ, but all valid client ActiveMQ URLs can be used. 

If you use Logback inside your JavaEE applications, I have two logback appenders you can use:

* https://github.com/exabrial/logback-jms-appender  (Best for Java EE apps with a managed JMS Configuration)
* https://github.com/exabrial/logback-openwire-appender (Best for Spring Boot or non EE standalone apps)

## Acknowledgements

The Graylog MQTT plugin lays the groundwork on how to accomplish writing your own inputs for Graylog. The code is well organized and very readable. https://github.com/graylog-labs/graylog-plugin-mqtt


## License
Since Upsteam Graylog and the MQTT plugin are GPL, this project is GPL to conform with the terms of the license.


## Installation

[Download the plugin](https://github.com/exabrial/graylog-plugin-openwire/releases) and place the .jar file in your Graylog plugin directory, which is usually called `plugins`.

```
cd ~
gpg --keyserver pool.sks-keyservers.net --recv-keys 871638A21A7F2C38066471420306A354336B4F0D
wget https://github.com/exabrial/graylog-plugin-openwire/releases/download/graylog-plugin-openwire-1.0.1/graylog-plugin-openwire-1.0.1.jar.asc
wget https://github.com/exabrial/graylog-plugin-openwire/releases/download/graylog-plugin-openwire-1.0.1/graylog-plugin-openwire-1.0.1.jar
gpg --verify graylog-plugin-openwire-1.0.1.jar.asc graylog-plugin-openwire-1.0.1.jar
rm graylog-plugin-openwire-1.0.1.jar.asc
sudo mv graylog-plugin-openwire-1.0.1.jar /usr/share/graylog-server/plugin/
sudo chown root:root /usr/share/graylog-server/plugin/graylog-plugin-openwire-1.0.1.jar
sudo systemctl restart graylog-server
```

After that step is completed, restart your server and you should have the new input options available.

## Configuration

