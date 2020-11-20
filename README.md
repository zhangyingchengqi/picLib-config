# picLib-config
picLib项目的配置文件
   本项目有三个配置中心，分别占用 7101,7102,7103端口

Refresh All:
curl -X POST http://localhost:7101/actuator/bus-refresh    

其它刷新配置操作如下: 
   /actuator/bus-refresh?destination=XXX，指定destination参数可以用来定位具体要刷新的应用程序，有两种方式：

   1) 定位具体实例
        /actuator/bus-refresh?destination=piclibapi:9000，此时总线上的各应用实例会根据destination指定的属性值来判断是否是自己的实例ID，符合才进行配置刷新。这里是piclibapi服务下，端口号为9000的实例才会进行配置更新。
   2) 定位具体服务
         /actuator/bus-refresh?destination=piclibapi:**，该请求会触发piclibapi服务的所有实例来进行刷新。


