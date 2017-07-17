# MQTT-sdk

mqttwe31.js为mqtt协议基于html5的websocket客户端。

mqttclient.jd为此次为故事机公众号用二次封装的mqtt-jssdk。

MQTT是为了物联网场景设计的基于TCP的Pub/Sub协议。

其与硬件通信流程为：

1.检查浏览器是否支持WebSocketCheck

2.向mqttserver发送询问设备是否在线的信令

3.收到在线确认后向硬件终端发送注册连接的请求

4.硬件收到连接后会回发一条统一建立连接的请求

5.建立连接后，可以通过封装的js方法向设备发送心跳和控制信令，所有发送的信令均是具备一定格式的string

6.web端收到的硬件发来的信令，会自动触发client.onMessageArrived方法（此为websocket客户端所提供），获得的数据为方法的参数，经过JSON.parse后可进行业务处理

7.连接的注册，断开，发送，接受请求的方法均是mqttwe31.js提供。

8.因为信令内容和格式均是iot业务多方协商定义的，顾不具备通用性。
