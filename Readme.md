# Hadoop 概论复习题

## 第一章

### 1、数据产生方式三个阶段

+ 运营式系统阶段：数据库系统等
+ 用户原创内容阶段：Web 2.0时代
+ 感知式系统阶段：物联网感知系统

### 2、信息技术发展史三次信息化浪潮及其具体内容

+ 第一次：1980年个人计算机普及
+ 第二次：1995年互联网时代
+ 第三次：2010年前后，云计算、大数据，物联网发展

### 3、大数据的四个基本特征

+ 数据量大（volume）
+ 数据类型繁多（variety）
+ 处理速度快（velocity）
+ 价值密度低（value）

### 4、科学研究经历的四个阶段

+ 实验：比萨尔斜塔
+ 理论：几何数学理论
+ 计算（模型）：计算机程序
+ 数据：以数据为中心发现解决问题

### 5、大数据对思维方式的重要影响

+ 全样而非抽样
+ 效率而非精确
+ 相关而非因果

### 6、大数据关键技术

+ 注释：（【层、工具】、实体、《动作》）

+ **数据采集**：【ETL工具】——（分布、异构数据源）的（关系数据、平面数据文件）——《抽取》——【临时中间层】——《清洗、转换、集成》——《加载》——【数据仓库or数据集市】——（联机分析处理）数据挖掘的基础 |||| （实时采集）数据 ——《输入》——【流计算系统】——《实时处理分析》
+ **数据存储和管理**：【数据库（关系型、非关系型、云）or文件系统（分布式）】 ——海量数据（结构、半结构、非结构）——《存储和管理》
+ **数据处理与分析**：【分布式并行编程模型&计算框架】and [机器学习&数据挖掘算法]——海量数据——《处理分析》|||分析结果——《可视化呈现》
+ **数据隐私和安全**：获得价值的同时构建隐私数据保护体系和数据安全体系，保障个人隐私与数据安全

### 7、大数据技术中的两大核心技术

+ **分布式存储**
+ **分布式处理**

### 8、大数据计算模式及其代表作品

| 大数据计算模式 | 解决问题                       | 代表作品                                                     |
| -------------- | ------------------------------ | ------------------------------------------------------------ |
| 批处理计算     | 针对大规模数据的批量处理       | MapReduce、Spark等                                           |
| 流计算         | 针对流数据的实时计算           | Flink、Storm、S4、Flume、Streams、Puma、DStream、Super Mario、银河流数据处理平台等 |
| 图计算         | 针对大规模图结构数据的计算     | Pergel、GraphX、Giraph、PowerGraph、Hama等                   |
| 查询分析计算   | 大规模数据的存储管理和查询分析 | Dremel、Hive、Cassandra、Impala等                            |

### 9、大数据产业层面

+ IT 基础设施层
+ 数据源层
+ 数据管理层
+ 数据分析层
+ 数据平台层
+ 数据应用层

### 10、云计算及实现层级

+ **定义**：云计算实现了通过网络提供可伸缩、廉价的分布式计算能力
+ 层级
  + SaaS（软件即服务）应用层：将应用程序进行出租
  + PaaS（平台即服务）平台层：类似IaaS，包括操作系统和围绕特定应用的必须服务
  + IaaS（基础设施即服务）基础设施层：将基础设施作为服务出租
+ 关键技术
  + 虚拟化
  + 分布式存储
  + 分布式计算
  + 多租户

### 11、大数据决策与传统数据库决策区别

+ 传统数据仓库：关系数据存储，缺乏数据类型与数据量
+ 大数据仓库：种类繁多，海量数据，非结构化

### 12、物联网

+ **定义**：***物物相连的互联网***、利用局部网络或互联网把传感器、控制器、机器、人员和物质连在一起、实现信息化和远程管理控制

### 13、大数据、云计算和物联网三者之间的区别和联系

+ ***区别***
  + 大数据：侧重于海量数据的存储、处理与分析，从海量数据中发现价值，服务于生产和生活
  + 云计算：本质上在整合和优化各种IT资源，并通过网络以服务的方式廉价提供给用户
  + 物联网：发展目标是实现物物相连，应用创新是物联网发展的核心。
+ ***联系***

![image](https://i.postimg.cc/NMxnCrzG/image.png)

## 第二章

### 1、Hadoop 特性

+ 高可靠性
+ 高效性
+ 高可扩展性
+ 高容错性
+ 成本低
+ 运行在Linux
+ 支持多种编程语言

### 2、Hadoop 版本与选择因素

+ 版本
  + Apache Hadoop：标准平台
  + Hortonworks：Apache Hadoop最大贡献者，如Tez
  + **Cloudera**(CDH)：功能同步，有自主产品
  + MapR：优化量大，由自主产品
  + 星环：本地厂商
+ 因素
  + 开源性
  + 稳定性
  + 实践经验
  + 社区支持

### 3、Hadoop项目结构

+ 大数据三家马车

  + 分布式文件系统GFS(Google File System)
  + 分布式计算框架MapReduce
  + NoSQL数据库系统BigTable

+ 项目结构

  ![](https://i.postimg.cc/RCWfRJbv/1.jpg)

+ 组件详解

  | 组件      | 功能                                     |
  | --------- | ---------------------------------------- |
  | HDFS      | 分布式文件系统                           |
  | MapReduce | 分布式并行编程模型                       |
  | YARN      | 资源管理和调度器                         |
  | Tez       | 运行在YARN之上的下一代Hadoop查询处理框架 |
  | Hive      | Hadoop上的数据仓库                       |
  | HBase     | Hadoop上的非关系型分布式数据库           |
  | Pig       | 基于Hadoop的大规模数据分析平台           |
  | Sqoop     | 用于在Hadoop与传统数据库之间进行数据传递 |
  | Oozie     | Hadoop上的工作流管理系统                 |
  | Zookeeper | 提供分布式协调一致性服务                 |
  | Storm     | 流计算框架                               |
  | Flume     | 分布式海量日志采集、聚合和传输的系统     |
  | Ambari    | Hadoop快速部署工具                       |
  | kafka     | 高吞吐的分布式发布订阅消息系统           |
  | Spark     | 通用并行框架                             |

### 4、Hadoop安装方式

+ 单机模式：一台机器，存储采用本地文件系统，没有采用分布式文件系统HDFS。
+ 伪分布式模式：存储采用分布式文件系统HDFS，但是名称节点和数据节点在同一台机器上。
+ 完全分布式模式：存储采用分布式文件系统HDFS，并且名称和数据节点位于不同机器上。

### 5、SSH

+ SSH为Secure Shell的缩写，是建立在应用层和传输层基础上的安全协议

### 6、配置SSH的原因

+ Hadoop名称节点需要启动集群中所有机器的Hadoop守护进程，这个过程需要通过SSH登录来实现。

### 7、Hadoop三种Shell命令方式区别

+ hadoop fs ： 适用于任何不同的文件系统
+ hsdoop dfs：只能适用于HDFS文件系统
+ hdfs dfs：只能适用于HDFS文件系统

## 第三章

### 1、HDFS优势和局限性

+ 优势
  + 兼容廉价的硬件设备
  + 流数据读写
  + 大数据集
  + 简单的文件模型
  + 强大的跨平台兼容性
+ 局限性
  + 不适合低延迟数据访问
  + 无法高效存储大量小文件
  + 不支持多用户写入及任意修改文件

### 2、HDFS主要组件的功能

| Namenode                                | DataNode                                    |
| --------------------------------------- | ------------------------------------------- |
| 存储元数据                              | 存储文件内容                                |
| 元数据保存在内存中                      | 文件内容保存在磁盘                          |
| 保存文件，block，datanode之间的映射关系 | 维护了block id 到datanode本地文件的映射关系 |

### 3、名称节点

+ FsImage：用于维护文件系统树以及文件树中所有的文件和文件夹的元数据。
  + 所有目录和文件inode的序列化形式（每个inode是一个文件或目录的元数据的内部表示。
    + 文件：文件的复制等级、修改和访问时间、访问权限、块大小以及组成文件的块。
    + 目录：存储修改时间、权限和配额元数据。
  + 不记录块存储位置，由名称节点把位置映射保存在内存中。
  + 新增数据节点时，数据节点报告块列表给名称节点后，定期执行这种告知操作，确保名称节点的块映射是最新的。
+ EditLog：记录了针对文件的创建、删除、重命名等操作。
+ 名称节点记录了每个文件中各个块所在的数据节点的位置信息。
+ 名称节点启动
  + 将FsImage文件中的内容加载到内存中
  + 执行EditLog文件中的各项操作（实现元数据同步）
  + 执行在内存中的元数据支持客户端的读操作
+ 名称节点运行期间EditLog不断变大的问题
  + 所有更新操作的持续写入
  + 容易影响冷启动加载速度

### 4、第二名称节点

+ 保存名称节点中对HDFS元数据信息的备份，并减少名称节点重启的时间，一般运行在一台机器上
+ 工作情况：
  + 定期通信，暂时将新的写操作写到新的文件edit.new
  + HTTP GET方式从namenode 获取 FsImage 和 EditLog，并下载到本地
  + 将下载到本地的文件载入内存，逐条执行EditLog中的各项更新操作（文件合并）
  + 执行完后利用POST请求发送FsImage到name弄得上
  + namenode进行文件替换（EditLog（旧）-》edit.new）

### 5、HDFS体系结构的局限性

+ **命名空间的的限制**
+ **性能的瓶颈**
+ **隔离问题**
+ **集群的可用性**

### 6、冗余数据保存

+ **加快数据传输速度**
+ **容易检查数据错误**
+ **保证数据可靠性**

## 第七章

### 1、MapReduce体系结构四个部分

+ Client
  + 用户编写程序利用Client提交到JobTracker
  + 提供接口便于用户查看作业运行状态
+ JobTracker
  + 负责监控资源和作业调度
  + 监控TaskTracker与Job的健康状况（实时任务转移）
  + 跟踪进度、监视资源、报告给任务调度器、合理分配资源
+ TaskTracker
  + 周期性汇报节点资源情况给JobTracker，同时接收新的操作（心跳）
  + 使用 slot 等量划分本节点的资源量
+ Task
  + 分为Map Task 和 Reduce Task两种
  + 由TaskTeacker启动

### 2、MapReduce工作注意事项

+ 不同的Map任务之间不会进行通信
+ 不同的Reduce任务之间也不会发生任何信息交换
+ 用户不能显式地从一台机器向另一台机器发送消息
+ 所有的数据交换都是通过MapReduce框架自身实现

### 3、HDFS以固定大小的block为基本单位存储数据

### 4、MapReduce基本处理单位是split（逻辑概念），用户自己决定划分方法

### 5、合并和归并

+ 合并：同类加和得结果
+ 归并：同类归类得列表
+ 例子：两个键值对**<“a”,1>**和**<“a”,1>**，如果合并，会得到**<“a”,2>**，如果归并，会得到**<“a”,<1,1>>**

### 6、WorkCount 代码实例

```java
import java.io.IOException;  // 捕获输入输出异常
import java.util.StringTokenizer;  // 用于分割字符串
import org.apache.hadoop.conf.Configuration;  // 读取、解析配置文件
import org.apache.hadoop.fs.Path;  // 统一的文件或目录描述
import org.apache.hadoop.io.IntWritable;  // 指定MapReduce的输入输出键的参数类型为IntWritable
import org.apache.hadoop.io.Text;  // 指定MapReduce的输入输出值的参数类型为Text
import org.apache.hadoop.mapreduce.Job;  // 指定了Job的参数类型，表示它是一个Hadoop作业
import org.apache.hadoop.mapreduce.Mapper;  // 指定Mapper的类型参数，表示它们分别是Mapper实现类
import org.apache.hadoop.mapreduce.Reducer;  // 指定Reducer的类型参数，表示它们分别是Reducer实现类
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;  // Mapreduce标准输入文件类
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;  // Mapreduce标准输出文件类 
import org.apache.hadoop.util.GenericOptionsParser;  // 解析Hadoop框架通用命令行参数的实用程序

public class WordCount{  
    // MyMapper类
    public static class MyMapper extends Mapper<Object,Text,Text,IntWritable>{  
            private final static IntWritable one = new IntWritable(1);  
            private Text word = new Text();  
            public void map(Object key, Text value, Context context) throws IOException,InterruptedException{  
                    StringTokenizer itr = new StringTokenizer(value.toString());  
                    while (itr.hasMoreTokens()){  
                            word.set(itr.nextToken());  
                            context.write(word,one);  
                    }  
            }  
    }  	  
    // MyReducer类
    public static class MyReducer extends Reducer<Text,IntWritable,Text,IntWritable>{  
            private IntWritable result = new IntWritable();  
            public void reduce(Text key, Iterable<IntWritable> values, Context context) throws IOException,InterruptedException{  
                    int sum = 0;  
                    for (IntWritable val : values)  
                    {  
                            sum += val.get();  
                    }  
                    result.set(sum);  
                    context.write(key,result);  
            }  
    }  
    public static void main(String[] args) throws Exception{  
            Configuration conf = new Configuration();  // 程序运行时参数
            String[] otherArgs = new GenericOptionsParser(conf,args).getRemainingArgs();  
            if (otherArgs.length != 2)  
            {  
                    System.err.println("Usage: wordcount <in> <out>");  
                    System.exit(2);  
            }  
            Job job = new Job(conf,"word count");  // 设置环境参数
            job.setJarByClass(WordCount.class);  // 设置整个程序的类名
            job.setMapperClass(MyMapper.class);  // 添加MyMapper类
            job.setReducerClass(MyReducer.class);  // 添加MyReducer类
            job.setOutputKeyClass(Text.class);  // 设置输出类型
            job.setOutputValueClass(IntWritable.class);  // 设置输出类型
            FileInputFormat.addInputPath(job,new Path(otherArgs[0])); // 设置输入文件 
            FileOutputFormat.setOutputPath(job,new Path(otherArgs[1]));  // 设置输出文件
            System.exit(job.waitForCompletion(true)?0:1);  
    }  
} 
```



## 第十五章

### 1、完整的推荐系统的3个组成模块

+ **用户建模模块**：对用户进行建模，根据用户行为数据和用户属性数据来分析用户的兴趣和需求
+ **推荐对象建模模块**：根据对象数据对推荐对象进行建模
+ **推荐算法模块**：基于用户特征和物品特征，采用推荐算法计算用户可能感兴趣的对象

### 2、UserCF 基于用户的协同过滤

+ 原理：**以本人推他人之物**
+ 实现步骤
  + 第一步：找到和目标用户兴趣相投的用户合集
  + 第二步：找到该合集中的用户所喜欢的，且目标用户未被推荐的物品进行推荐
+ 算法实现
  + 泊松相关系数
  + 余弦相似度
  + 调整余弦相似度

### 3、ItemCF 基于物品的协同过滤

+ 原理：**以本人之物推物之物**
+ 实现步骤：
  + 第一步：计算物品间相似度，找到和本物体相似度较高的物体合集
  + 第二步：找到该合集中未被推荐的生成推荐列表推荐给用户

### 4、UserCF vs ItemCF

+ 主要区别
  + UserCF 是推荐那些和目标用户**有共同兴趣爱好**的其他用户所喜欢的物品
  + ItemCF 是推荐那些和目标用户**之前喜欢的物品**类似的其他物品
+ 泛化区别
  + UserCF 算法的推荐更偏向**社会化**
  + ItemCF 算法的推荐更偏向**个性化**
