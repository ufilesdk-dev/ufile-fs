# ufile-fs
ufile-fs 可以把 ufile 挂载到本地，当做文件系统来访问。

## 使用环境
* 操作系统: linux or mac, x86-64位操作系统

## 安装步骤
* 如果是linux则下载文件 [TARGET](https://github.com/ufilesdk-dev/ufile-fs/releases/download/v0.21.1/ufile-fs-linux.tar.gz)
* 如果是mac上下载文件 [TARGET](https://github.com/ufilesdk-dev/ufile-fs/releases/download/v0.21.1/ufile-fs-mac.tar.gz)
* 解压 tar -xzvf ${TARGET} 到指定目录
* 默认在$HOME/.aws/credentials文件里面配置bucket的公私钥,格式如下
  ```
  [default]
  aws_access_key_id = TOKEN_*****9206d
  aws_secret_access_key = 93614*******b1dc40
  ```
* 执行挂载命令 ```./ufile-fs  --endpoint bucket_domain bucket local_mount_dir``` (可查看下面小节bucket_domain分布), 例如: ```./ufile-fs  --endpoint http://internal.s3-cn-bj.ufileos.com suning2  ./mount_test```
* 测试挂载是否成功, 可以拷贝一个本地文件到${local_mount_dir}目录, 看是否上传到ufile

## 文件上传和下载和删除
 挂载UFile存储空间和后，可以像使用本地文件夹一样使用UFile存储空间。
* 拷贝文件到${local_mount_dir} ，即是上传文件。
* 将文件从${local_mount_dir}拷贝到其他路径，即下载文件。
* 将文件从${local_mount_dir}删除掉，则UFile存储空间中，该文件也被删除掉。

## 卸载UFile存储空间(或者说关闭程序)
* ```sudo umount ${your_local_mount_dir}```

## bucket_domain分布
* 北京二:
  * 外网: s3-cn-bj.ufileos.com
  * 内网: internal.s3-cn-bj.ufileos.com

* 上海:
  * 外网: s3-cn-sh2.ufileos.com
  * 内网: internal.s3-cn-sh2.ufileos.com

* 海康威视专区:
  * 外网: division.s3-cn-bj.ufileos.com
  * 内网: internal.division.s3-cn-bj.ufileos.com

* 尼日利亚
  * 外网: s3-afr-nigeria.ufileos.com
  * 内网: internal.s3-afr-nigeria.ufileos.com

* 浪潮2
  * 外网: s3.infile.inspurcloud.cn
  * 内网: s3-internal.infile.inspurcloud.cn

* 越南
  * 外网: s3-vn-sng.ufileos.com
  * 内网: internal.s3-vn-sng.ufileos.com

注意: 目前北京二地域已经支持https协议，其他地域后续支持
