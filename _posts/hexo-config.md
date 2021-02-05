---
title: hexo_config
date: 2021-02-06 04:12:26
tags:
---

###参考地址

```ba
https://zhuanlan.zhihu.com/p/132823826
```



###生成/删除静态文件

```bash 
生成静态文件命令：hexo generate或 hexo g
删除静态文件命令：hexo clean
```

正常情况下，每次启动本地端口前只需更新静态文件即可。Hexo引入了差分机制，如果 `public` 目录存在，那么 `hexo g` 只会重新生成改动的文件。

如果发生了一些错误，可以先删除静态文件，然后再重新生成。`hexo g`命令还提供了一个参数`-f`提供以类似效果。这样做的缺点就是当文章数变多以后渲染时间会更久一些。



###自定义主题

``` bash
启用主题的步骤：

- 在GitHub上克隆你喜欢的hexo主题到本地博客的根目录的theme文件夹下：`git clone <url> themes/<theme_name>`
- 在theme中新建文件夹将主题git clone到此位置
- 修改`_config.yml 文件的theme字段为下载好的主题名，例如：`theme: yilia` 主题里的_config.yml也可以进行修改
- 对主题文件进行777权限赋予(宝塔linux面板有这样的问题 需要手动基于777)
- 删除已有静态文件：`hexo clean`（为了避免可能的错误）
- 重新生成静态文件：`hexo g`
- 启动本地端口查看效果：`hexo s`
- 重新部署：`hexo d`，稍等一段时间后刷新网页，发现主题生效

```



###自定义主题

```bas
命令：hexo deploy或 hexo d
```

部署之后等待一会就能通过公网访问到博客了。

