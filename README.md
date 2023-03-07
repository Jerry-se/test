# test
github test project

## commit style

目前最流行的 Angular 规范，使用 commitizen 

安装 npm:

```shell
# apt 安装的版本太低
dbtu@dbtu:~/code/test$ sudo apt install nodejs npm
# https://github.com/nodesource/distributions
dbtu@dbtu:~/code/test$ curl -fsSL https://deb.nodesource.com/setup_14.x | sudo -E bash -
dbtu@dbtu:~/code/test$ sudo apt-get install -y nodejs
dbtu@dbtu:~/code/test$ node --version
v14.21.3
dbtu@dbtu:~/code/test$ 
dbtu@dbtu:~/code/test$ npm --version
6.14.18
dbtu@dbtu:~/code/test$ 
dbtu@dbtu:~/code/test$ npm init
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help init` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: (test) 
version: (1.0.0) 
description: Test of Github
entry point: (index.js) 
test command: 
git repository: (https://github.com/Jerry-se/test.git) 
keywords: 
author: Jerry
license: (ISC) 
About to write to /home/dbtu/code/test/package.json:

{
  "name": "test",
  "version": "1.0.0",
  "description": "Test of Github",
  "main": "index.js",
  "dependencies": {
    "commitizen": "^4.3.0"
  },
  "devDependencies": {},
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/Jerry-se/test.git"
  },
  "author": "Jerry",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/Jerry-se/test/issues"
  },
  "homepage": "https://github.com/Jerry-se/test#readme"
}


Is this OK? (yes) 
dbtu@dbtu:~/code/test$ 
# network timeout 的话可以加上 --registry=https://registry.npmmirror.com
# 或者使用命令 npm config set registry https://registry.npm.taobao.org 设置 registry
# npm config list 查询当前配置
# 全局安装使用 npm install -g commitizen
dbtu@dbtu:~/code/test$ npm install --save-dev commitizen
npm notice created a lockfile as package-lock.json. You should commit this file.
npm WARN test No repository field.
npm WARN test No license field.

+ commitizen@4.3.0
added 168 packages from 184 contributors in 11.659s

24 packages are looking for funding
  run `npm fund` for details
dbtu@dbtu:~/code/test$ commitizen init cz-conventional-changelog --save-dev --save-exact
# 非全局安装使用 npx commitizen init cz-conventional-changelog --save-dev --save-exact
```

如果是全局安装，可以使用 `git cz` 来代替 `git commit`。此处使用项目局部安装，可以使用 `npx git-cz` 来提交代码。或者手动在 `package.json` 文件中添加一下内容：

```json
  ...
  "scripts": {
    "commit": "cz"
  }
```

然后就可以使用 `npm run commit` 来代替 `git commit` 提交。

- [commitizen](https://github.com/commitizen/cz-cli)
- [阮一峰老师的 Commit message 和 Change log 编写指南](http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html)
- [同类型的简易提交规范 gitlint](https://github.com/jorisroovers/gitlint)
- [vscode git-commit-plugin](https://marketplace.visualstudio.com/items?itemName=redjue.git-commit-plugin)
