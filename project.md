* 产品优化建议：字段首选项   下拉选择框  
* 工作中的难点与解决方案：
	* 有一个设置范围的可拖动框框。设置采集器的基本配置。刚开始是用的angular-rzslider 进行了一些配置，包括颜色，change事件函数，但没有直接配置尺寸的接口。  后来浏览网页的时候就看到了input type="range" 
	* 主题修改：项目有好几个主题（东方航空、铁路局、浦发、银联、国开行）主题不一样。不仅是颜色不同，而且是logo 文字描述也不一样 解决方法是用scss变量来做的 将主题色的颜色变量放在一个文件下 系统配置下 文字描述不同的地方全部用伪元素来替代
	* table 数据流的配置放在mysql有两个接口 采集状态数据放在es里，调用的接口不一样。先后调用两个不同的接口在通过
	* custom-selector 
	* 任务高级配置功能 有一个table 当时是一个个tr写，代码量太多了。后来发现虽然虽然值不一样，但是可以分为几个主要的类型。框类型 值范围 描述，代码里面不含任何真正的内容，全部是在controller里的配置。ng-repeat ng-switch 来进行控制的。第一个表用了一天做好的，后面五个表用了半天。扩展性和可复用性大大提升。
	* 字典管理功能中的上传文件 FileReader() result onload split('/n') 长度进行限制1000条
	* sankey-chart 图表高度 节点数量关系。

* 工作主线

```
平台简介：夏洛克产品专注于将人工智能技术赋能运维管理，帮助用户发现运维数据的潜在价值。目前我们的产品能够实现：海量，多种类数据采集能力 大数据管理能力 数据查询及分析能力 智能运维及预测能力
大数据管理能力：运维数据种类多，来源丰富，统一管理能力尤为重要。 目前夏洛克统一平台在单一客户处实际每日处理TB级数据量。 目前处理和管理的数据类型包括日志，时间，指标，告警，CMDB，业务流。

数据采集
该模块支持采集各类文件数据、系统日志，将所有的日志进行集中采集管理，不需要在额外的 归档、备份日志。
文件和目录：针对文件和目录的信息采集
监控系统：针对BMC TrueSight，Zabbix类型的采集
SYSLOG：
结构化数据库：针对Oracle,Mysql等数据库信息的采集
自定义脚本：针对上传脚本和路径脚本的采集
TCP/UDP：
kafka：针对Kafka中topic信息

数据处理操作
该模块支持对各类采集文件进行数据处理。包括解析和聚合两类

数据存储
该模块支持对各类采集文件和聚合，解析类文件进行存储。包括ElasticSearch和HDFS两类存储。

启动数据流
数据流配置完成后，在数据流页面可以看到该条记录。 点击“启动”即可开始写入采集日志，页面会显示采集数据时间及采集总量。
```

官网详细叙述、理解github代码、仔细研究简历上的技术