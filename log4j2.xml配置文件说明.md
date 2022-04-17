log4j2.xml配置文件说明

```xml
level: all < trace < debug < info < warn < error < fatal < off
onMatch/onMismatch ACCEPT 接收  NEUTRAL不管   DENY拒绝
Appender :
    type:输出方式:(4种)
        Cassandra  将其输出写入Apache Cassandra数据库。必须提前配置键空间和表，并且该表的列 Map 在配置文件中
        Console(可以直接使用<Console>标签)
        Failover  如果主 Appender 失败，则将按 Sequences 尝试次要 Appender，直到一个成功或没有其他次要 Appender 为止。
            File   写入文件

    Layout:输出布局
        CSV Layouts:此布局创建逗号分隔值(CSV)条记录，并需要Apache Commons CSV 1.4.
        GELF Layout:
			以 Graylog 扩展日志格式(GELF)1.1布局。
            如果日志事件数据大于 1024 字节(compressingThreshold)，则此布局将 JSON 压缩为 GZIP 或 ZLIB(compressionType)。此布局不实现分块。
        HTML Layout:输出为一个HTML页面
        JSON Layout:输出为json文件
        Pattern Layout:自定义布局
            %d{DEFAULT}      2012-11-02 14:34:02,123
            %d{ABSOLUTE}/%d{HH:mm:ss,SSS}     14:34:02,781
            %d{HH:mm:ss}{GMT+0}      18:34:02
            %L      (line)行
            %l      (line)程序用小写的l很方便
            %msg/%m      信息
            %level    级别
            %t/%tn      线程名
            %C/%class      类名%class{36}
            %style    各种样式(Underline/highlight···)  %highlight%level表示高亮后面的等级
        RFC5424 Layout      Rfc5424Layout 按照增强的 Syslog 规范RFC 5424格式化 LogEvents
        Serialized Layout(弃用,不推荐)
        Syslog Layout      将 LogEvent 格式化为 BSD Syslog 记录，该记录与 Log4j 1.2 使用的格式相同。
        XML Layout      如果complete="true"输出XML文档，其中默认名称空间为 Log4j 名称空间"http://logging.apache.org/log4j/2.0/events"
            Marker      标记一下。在日志消息中使用标记时，Marker 元素才会出现。标记父级的名称将在 Marker 元素的 parent 属性中提供。
        YAML Layout      将一系列 YAML 事件附加为序列化为字节的字符串
```

