# Code

```
ln –s 源文件 目标文件
```

# Hard link

为解决文件的共享使用，Linux 系统引入了两种链接：硬链接 (hard link) 与软链接（又称符号链接，即 soft link 或 symbolic link）。链接为 Linux 系统解决了文件的共享使用，还带来了隐藏文件路径、增加权限安全及节省存储等好处。若一个 inode 号对应多个文件名，则称这些文件为硬链接。换言之，硬链接就是同一个文件使用了多个别名（见 图 2.hard link 就是 file 的一个别名，他们有共同的 inode）。硬链接可由命令 link 或 ln 创建。如下是对文件 oldfile 创建硬链接。

# Reference

 - http://www.cnblogs.com/joeblackzqq/archive/2011/03/20/1989625.html
 - http://www.ibm.com/developerworks/cn/linux/l-cn-hardandsymb-links/