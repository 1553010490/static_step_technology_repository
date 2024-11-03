# 资源管理

## 资源管理介绍

在kubernetes中，所有的内容都抽象为资源，用户需要通过操作资源来管理kubernetes。

> kubernetes的本质上就是一个集群系统，用户可以在集群中部署各种服务，所谓的部署服务，其实就是在kubernetes集群中运行一个个的容器，并将指定的程序跑在容器中。
> kubernetes的最小管理单元是pod而不是容器，所以只能将容器放在Pod中，而kubernetes一般也不会直接管理Pod，而是通过Pod控制器来管理Pod的。
> Pod可以提供服务之后，就要考虑如何访问Pod中服务，kubernetes提供了Service资源实现这个功能。
> 当然，如果Pod中程序的数据需要特久化，kubernetes还提供了各种存储系统。

## 资源管理方式

- 命令式对象管理：直接使用命令去操作kubernetes资源

```shell
kubectl run nginx-pod --image=nginx:1.17.1 --port=80
```

命令式对象配置：通过命令配置和配置文件去操作kubernetes资源

```shell
kubctl create/patch -f nginx-pod.yaml
```

声明式对象配置：通过apply命令和配置文件去操作kubernetes资源

```shell
kubectl apply -f nginx-pod.yaml
```


|类型|操作对象|适用环境|优点|缺点|
| ---------------- | ------ | ------ | --- | --- |
|命令式对象管理|对象|测试|简单|只能操作活动对象，无法审计、跟踪|
|命令式对象配置|文件|开发|可以审计、跟踪|项目大时，配置文件多，操作麻烦|
|声明式对象配置|目录|开发|支持目录操作|意外情况难以调试|

### 3.3.1 命令式对象管理

kubectl命令
kubectl是kubernetes集群的命令行工具，通过它能够对集体本身进行管理，并能够在集群上进行容器化应用的安装部署。kubectl命令的语法如下：

```shell
kubectl [command] [type] [name] [flags]
```
command：指定要对资源执行的操作，例如create、get、delete
type：指定资源类型，比如deployment、pod、service
name：指定资源的名称，名称大小写敏感
flags：指定额外的可选参数






### 3.3.2、命令式对象配置

### 3.3.3、声明式对象配置
