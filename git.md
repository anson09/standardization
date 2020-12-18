# git flow

repo 装上 commitlint，commit message 符合[@commitlint/config-conventional](https://www.conventionalcommits.org/en/v1.0.0/) 规范

每个 repo 有三个分支：release（线上）master（UAT）分支和 dev（ST）分支。若长期存在其他分支请在 readme 添加分支说明

UAT：部署环境/配置与生产一致，用于上线前的回归

ST：以测试 case 为主

流程：

常规开发：

1. 从 dev 拉出分支，根据 commit 类型做分支前缀比如 feat/... fix/...
2. 本地开发
3. 本地 rebase 远程 dev 分支
4. 自测（也可提供本地 ip 给他人）
5. 往 dev 提 pr
6. code review
7. ST 提测
8. 如果提测阶段测试童鞋反馈有 bug，则重复 1-7 的操作。

线上紧急 bug：

1. 从 master 拉出 hotfix/...分支
2. 本地开发
3. 自测
4. 往 master 提交 pr
5. code review
6. UAT 提测
7. 合并回 dev

发布：

1. dev 合并进 master，UAT 提测
2. UAT 测试通过后合并进 release 分支完成发布

类型列表：

- feat: add new feature
- fix: fixing bug
- perf: improving performance
- test: adding missing tests, refactoring tests; no production code changes
- build: build flow
- ci: continuous integration
- docs: updating documentation
- refactor: refactoring production code
- style: formatting; no production code change
- chore: updating config, dependencies or something; no production code change
- revert: roll back
