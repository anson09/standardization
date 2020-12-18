# npm 发包约定

对于发布到 npm 的工具类项目使用以下规范：

版本号：遵循 [semver 规范](https://semver.org/lang/zh-CN/)

发布者：

1. rc 版、正式版通过 master 分支发布到 latest，发布时打上 git tag
2. next 版、beta 版通过 dev 分支发布到 next，发布时打上 git tag
3. 开发测试通过 npm link，不发布版本

使用者：

生产环境记得只使用 rc 或者正式版
