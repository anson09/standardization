# 代码规范

> 有需要起新项目或者引入我们前端当前未使用到的第三方库前先与 anson 沟通确认

> 新 spa 项目 [fork 这个模版](https://github.com/anson09/crystal) 即包含完整规范，非 spa 类型项目根据以下规则手动引入。

## 使用 eslint、stylelint 和 prettier 执行代码规范

- lint 负责错误检查
- prettier 负责代码风格

eslint 使用 airbnb-base 规则，每条规则有社区充分讨论，根据项目需要再额外开关部分规则。vue 项目额外增加 eslint-plugin-vue [eslint 配置文件](https://github.com/anson09/crystal/blob/dev/.eslintrc.yml)

stylelint 使用 stylelint-config-recommended-scss [stylelint 配置文件](https://github.com/anson09/crystal/blob/dev/.stylelintrc.yml)

prettier 使用默认规则，另外用 eslint-config-prettier 和 stylelint-config-prettier 覆盖 eslint 和 stylelint 的 format 规则

## vscode 最新版配置：（保存时触发检查与格式化）

安装 eslint、 stylelint、prettier 插件, `settings.json` 启用以下配置

```json
"editor.formatOnSave": true,
"editor.defaultFormatter": "esbenp.prettier-vscode",
"editor.codeActionsOnSave": {
    "source.fixAll": true
}
```

## git hook 配置 （提交时触发检查与格式化）

使用 [husky](https://github.com/anson09/crystal/blob/dev/.huskyrc.yml) 与 [lint-staged](https://github.com/anson09/crystal/blob/dev/.lintstagedrc.js) 对即将进入仓库的的代码进行异常检查和自动格式化，阻止异常代码入库

另外我们还使用了 [commitlint](https://github.com/anson09/crystal/blob/dev/.commitlintrc.yml) 对 commit msg 进行规范

## 全局格式化：（手动触法）

初始化代码规范和规范变更时使用 [npm script](https://github.com/anson09/crystal/blob/dev/scripts/lint.sh) 将整个项目跑一遍
