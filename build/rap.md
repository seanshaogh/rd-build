## RAP

RAP是一个由阿里提供的可视化接口管理开源工具。通过分析接口结构，动态生成模拟数据，校验真实接口正确性， 围绕接口定义，通过一系列自动化工具提升我们的协作效率。

### 安装RAP

已经将rap环境做成了docker镜像push到了[dockerhub](https://hub.docker.com/r/ifintech/rap/)上，所以优先采用docker安装。

1. 一键拉取，并部署

   ```shell
   docker run -itd --name rap ifintech/rap
   ```

2. 分配ip

   ```shell
   pipework br0 rap 172.16.2.6/24@172.16.2.1
   ```

到这步骤已经可以通过`http://172.16.2.6`进行访问了，接下来分配域名。

1. 解析rap.nw.com

   ```shell
   echo `172.16.2.6 rap.nw.com` >> /ect/hosts
   service dnsmasq restart
   ```


现在可以通过 http://rap.nw.com 来访问我们本地的rap了
