# iotedge-demo
A demonstration of the capabilities of IoTEdge

https://docs.microsoft.com/en-us/azure/iot-edge/how-to-install-iot-edge-linux

```
$ cd edge
$ docker build -t iotedge .
```

```
$ docker run -d --privleged -e connectionString='' iotedge
```
