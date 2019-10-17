# ufile-fs
ufile对应的文件系统, 可以挂载bucket到一个文件系统上使用

## 使用环境
* 操作系统: linux or mac, x86-64位操作系统

## 安装步骤
* 如果是linux则下载文件 [TARGET](https://github.com/ufilesdk-dev/ufile-fs/releases/download/v0.21.0/ufile-fs-linux.tar.gz)
* 如果是mac上下载文件 [TARGET](https://github.com/ufilesdk-dev/ufile-fs/releases/download/v0.21.0/ufile-fs-mac.tar.gz)
* 解压 tar -xzvf ${TARGET} 到指定目录
* 默认在$HOME/.aws/credentials文件里面配置bucket的公私钥,格式如下
  ```
  [default]
  aws_access_key_id = TOKEN_*****9206d
  aws_secret_access_key = 93614*******b1dc40
  ```
* 执行挂载命令 ./ufile-fs  --endpoint your_ufile_endpoint your_bucket your_local_mount_dir, 例如: ./ufile-fs  --endpoint http://internal.s3-cn-bj.ufileos.com suning2  ./mount_test
* 测试挂载是否成功, 可以拷贝一个本地文件到your_local_mount_dir目录, 看是否上传到ufile

## 文件上传和下载和删除
 挂载UFile存储空间和后，可以像使用本地文件夹一样使用UFile存储空间。
* 拷贝文件到${your_local_mount_dir} ，即是上传文件。
* 将文件从${your_local_mount_dir}拷贝到其他路径，即下载文件。
* 将文件从${your_local_mount_dir}删除掉，则UFile存储空间中，该文件也被删除掉。

## 卸载UFile存储空间(或者说关闭程序)
* sudo umount ${your_local_mount_dir}

