# bolog-archive
将`iusses blog`生成 `README.md` Summary

- action 配置方式
```yml

name: sync issues blog
on:
  workflow_dispatch:
  issues:
    types: [opened, deleted]
  issue_comment:
    types: [edited]

jobs:
  iusses-sync:
    runs-on: ubuntu-latest
    steps:
      - name: sync blog
        uses: ZSCGR/blog-archive@main
        with:
          api-github-token: ${{ secrets.API_GITHUB_TOKEN }}
          repo: ${{ secrets.REPO }}
          owner: ${{ secrets.OWNER }}
          git-user-name: username
          git-user-email: user@gmail.com
          backup-branch: issues-blog
          backup-path: docs/blog
```

- 参数配置说明
  
| inputs   | Desc         |
| ------ | ---------------- |
| api-github-token   | 用来访问 github issues 接口    |
| repo    | issues仓库名称 |
| git-user-name | commit README.md 用户      |
| git-user-email | commit README.md 邮箱     |
| backup-branch | 备份分支      |
| backup-path | 备份分支路径     |


> 需要开启action提交README.md 权限设置， `setting > actions > general > Workflow permissions > Read and write permissions`


---
> 生成内容格式示例
# Summary

- [Cloudflare 设置 Origin Rules](https://github.com/zhangwt-cn/notes/issues/16) - 2023-09-19 12:06:49
- [`Spring Boot` 适配部署 `TongWeb7`](https://github.com/zhangwt-cn/notes/issues/15) - 2023-09-12 08:44:36
- [/swagger-resources 404](https://github.com/zhangwt-cn/notes/issues/14) - 2023-09-11 09:41:07
- [yum 报错，无法使用](https://github.com/zhangwt-cn/notes/issues/13) - 2023-09-06 14:42:47
- [Linux 安装 python](https://github.com/zhangwt-cn/notes/issues/12) - 2023-09-06 14:19:29
- [Nginx 配置 WebSocket 代理 ](https://github.com/zhangwt-cn/notes/issues/11) - 2023-09-05 08:12:04
- [Linux yum 安装 Redis 踩坑](https://github.com/zhangwt-cn/notes/issues/10) - 2023-09-05 01:46:16
- [Linux yum 安装 nginx 踩坑](https://github.com/zhangwt-cn/notes/issues/9) - 2023-09-05 01:36:25
- [vscode rust-analyzer 提示 Failed to spawn one or more proc-macro servers.](https://github.com/zhangwt-cn/notes/issues/8) - 2023-08-31 06:34:46
- [Mac 命令行](https://github.com/zhangwt-cn/notes/issues/7) - 2023-08-29 09:47:34
- [MySQL迁移DM数据库](https://github.com/zhangwt-cn/notes/issues/6) - 2023-08-29 09:38:11
- [Ubuntu 安装firefox报错](https://github.com/zhangwt-cn/notes/issues/5) - 2023-08-03 09:53:32
- [软考备考](https://github.com/zhangwt-cn/notes/issues/4) - 2023-07-19 07:28:11
- [高性能 MySQL](https://github.com/zhangwt-cn/notes/issues/1) - 2023-02-02 07:02:23
- [深入理解 Java 虚拟机](https://github.com/zhangwt-cn/notes/issues/2) - 2023-02-02 01:48:22
- [书单 & 学习方向](https://github.com/zhangwt-cn/notes/issues/3) - 2023-02-02 01:39:55
