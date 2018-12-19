# 准备配置本地仓库

在设置您的本地仓库之前，您必须满足某些要求。

- 选择一个运行着受支持操作系统的集群中的或者可访问的现有服务器。

- 使集群中的所有主机能够访问镜像服务器。

- 确保镜像服务器已经安装了包管理工具，比如yum（针对RHEL，CensOS，Oracle，或者Amazon Linux），zypper（针对SLES），或者apt-get（针对Debian和Ubuntu）。

- 可选：如果您的仓库有临时网络访问，而且您使用了RHEL，CentOS，Oracle，或者Amazon Linux作为操作系统，安装yum工具：

  ```shell
  yum install yum-utils createrepo
  ```

  在满足了这些要求之后，您就可以进行设置本地仓库的步骤了。

## 设置本地仓库步骤

  1. 创建一个HTTP服务器

       a.  在镜像服务器上安装HTTP服务（比如Apache httpd），您可以使用在Apache社区网站上提供的说明。

       b.  激活服务器。

       c.  确保所有防火墙允许您集群中所有节点到您镜像服务器内网HTTP访问。

> **[info] 注意**
>
> 如果您使用Amazon EC2，请确保禁用了SELinux。

  2. 在您的镜像服务器上，为您的web服务创建一个目录。

     - 比如，在一个shell窗口输入：

       **对于 RHEL/CentOS/Oracle/Amazon Linux:**

       ```shell
       mkdir -p /var/www/html
       ```

       **对于SLES：**

       ```shell
       mkdir -p /srv/www/htdocs/rpms
       ```

       **对于Debian/Ubuntu：**

       ```shell
       mkdir -p /var/www/html
       ```

     - 如果您使用symlink，请启用您web服务器上的`followsymlinks`。

## 接下来的步骤

接下来，不管有没有网络访问，您都必须设置本地仓库。

## More Information

[httpd.apache.org/download.cgi](http://httpd.apache.org/download.cgi)

