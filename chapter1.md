**1、安装GitBook**

安装GitBook，使用npm的方式安装，首先要安装node.js

* Node.js[官网](https://nodejs.org/en/)下载windows版本的安装文件，安装；

安装完毕，命令行查看node.js的版本：

```
C:\Users\Administrator>node -v
v10.16.2
```

使用node.js默认的npm镜像，可能速度比较慢；

* 设置默认npm镜像仓库：

```
C:\Users\Administrator>npm config set registry http://registry.npm.taobao.org
```

* 直接执行命令_**npm install gitbook -g**_安装GitBook，结果报错

```
C:\Users\Administrator>npm install gitbook -g
npm WARN deprecated graceful-fs@3.0.5: please upgrade to graceful-fs 4 for compatibility with current and future versions of Node.js
npm WARN deprecated nunjucks@2.2.0: potential XSS vulnerability in autoescape mode, and with escape filter was fixed in v2.4.3
npm ERR! path git
npm ERR! code ENOENT
npm ERR! errno ENOENT
npm ERR! syscall spawn git
npm ERR! enoent Error while executing:
npm ERR! enoent undefined ls-remote -h -t ssh://git@github.com/gitbookio/i18n-node.git
npm ERR! enoent
npm ERR! enoent
npm ERR! enoent spawn git ENOENT
npm ERR! enoent This is related to npm not being able to find a file.
npm ERR! enoent

npm ERR! A complete log of this run can be found in:
npm ERR!     C:\Users\Administrator\AppData\Roaming\npm-cache\_logs\2019-08-12T12_52_20_703Z-debug.log
```

* 不知道原因，改为_**npm install gitbook-cli -g**_安装gitbook-cli

```
C:\Users\Administrator>npm install gitbook-cli -g
C:\Users\Administrator\AppData\Roaming\npm\gitbook -> C:\Users\Administrator\AppData\Roaming\npm\node_modules\gitbook-cli\bin\gitbook.js
+ gitbook-cli@2.3.2
added 578 packages from 672 contributors in 23.078s
```

* 执行命令_**gitbook -V**_查看gitbook版本；

该命令除了查看版本，应该还有安装或更新GitBook的功能；运行后，会显示CLI版本，并安装GitBook

```
C:\Users\Administrator>gitbook -V
CLI version: 2.3.2
Installing GitBook 3.2.3
gitbook@3.2.3 ..\ADMINI~1\AppData\Local\Temp\tmp-1374031Lh1mjyKIHe\node_modules\gitbook
├── escape-string-regexp@1.0.5
├── destroy@1.0.4
├── escape-html@1.0.3
├── ignore@3.1.2
├── bash-color@0.0.4
├── gitbook-plugin-livereload@0.0.1
├── graceful-fs@4.1.4
├── cp@0.2.0
├── nunjucks-do@1.0.0
├── github-slugid@1.0.1
├── spawn-cmd@0.0.2
├── gitbook-plugin-fontsettings@2.0.0
├── open@0.0.5
├── is@3.3.0
├── direction@0.1.5
├── q@1.4.1
├── object-path@0.9.2
├── extend@3.0.2
├── json-schema-defaults@0.1.1
├── gitbook-plugin-search@2.2.1
├── jsonschema@1.1.0
├── crc@3.4.0
├── urijs@1.18.0
├── semver@5.1.0
├── front-matter@2.3.0
├── immutable@3.8.2
├── omit-keys@0.1.0 (isobject@0.2.0, array-difference@0.0.1)
├── tmp@0.0.28 (os-tmpdir@1.0.2)
├── error@7.0.2 (string-template@0.2.1, xtend@4.0.2)
├── mkdirp@0.5.1 (minimist@0.0.8)
├── resolve@1.1.7
├── gitbook-plugin-theme-default@1.0.7
├── dom-serializer@0.1.0 (domelementtype@1.1.3, entities@1.1.2)
├── js-yaml@3.13.1 (esprima@4.0.1, argparse@1.0.10)
├── send@0.13.2 (statuses@1.2.1, range-parser@1.0.3, fresh@0.3.0, etag@1.7.0, ms@0.7.1, depd@1.1.2, debug@2.2.0, mime@1.3.4, http-errors@1.3.1, on-
finished@2.3.0)
├── fresh-require@1.0.3 (is-require@0.0.1, shallow-copy@0.0.1, sleuth@0.1.1, astw@1.3.0, acorn@0.9.0, escodegen@1.11.1, through2@0.6.5)
├── gitbook-plugin-lunr@1.2.0 (html-entities@1.2.0, lunr@0.5.12)
├── cpr@1.1.1 (rimraf@2.4.5)
├── tiny-lr@0.2.1 (parseurl@1.3.3, livereload-js@2.4.0, qs@5.1.0, debug@2.2.0, body-parser@1.14.2, faye-websocket@0.10.0)
├── gitbook-plugin-highlight@2.0.2 (highlight.js@9.2.0)
├── moment@2.13.0
├── gitbook-plugin-sharing@1.0.2 (lodash@3.10.1)
├── i18n-t@1.0.1 (lodash@4.17.15)
├── gitbook-asciidoc@1.2.2 (gitbook-html@1.3.3, asciidoctor.js@1.5.5-1, lodash@4.17.15)
├── cheerio@0.20.0 (entities@1.1.2, css-select@1.2.0, htmlparser2@3.8.3, jsdom@7.2.2, lodash@4.17.15)
├── gitbook-markdown@1.3.2 (kramed-text-renderer@0.2.1, gitbook-html@1.3.3, kramed@0.5.6, lodash@4.17.15)
├── request@2.72.0 (tunnel-agent@0.4.3, aws-sign2@0.6.0, forever-agent@0.6.1, oauth-sign@0.8.2, is-typedarray@1.0.0, caseless@0.11.0, stringstream@
0.0.6, aws4@1.8.0, isstream@0.1.2, json-stringify-safe@5.0.1, tough-cookie@2.2.2, qs@6.1.2, node-uuid@1.4.8, combined-stream@1.0.8, mime-types@2.1.24,
 bl@1.1.2, hawk@3.1.3, http-signature@1.1.1, har-validator@2.0.6, form-data@1.0.1)
├── juice@2.0.0 (slick@1.12.2, deep-extend@0.4.2, batch@0.5.3, cssom@0.3.1, commander@2.9.0, cross-spawn-async@2.2.5, web-resource-inliner@2.0.0)
├── npm@3.9.2
├── npmi@2.0.1 (semver@4.3.6)
├── rmdir@1.2.0 (node.flow@1.2.3)
├── read-installed@4.0.3 (debuglog@1.0.1, util-extend@1.0.3, slide@1.1.6, readdir-scoped-modules@1.1.0, read-package-json@2.0.13)
├── chokidar@1.5.0 (async-each@1.0.3, path-is-absolute@1.0.1, inherits@2.0.4, glob-parent@2.0.0, is-glob@2.0.1, is-binary-path@1.0.1, anymatch@1.3.
2, readdirp@2.2.1)
└── nunjucks@2.5.2 (asap@2.0.6, yargs@3.32.0, chokidar@1.7.0)
GitBook version: 3.2.3
```

再次执行_**gitbook -V**_，可以看到安装成功了！

```
C:\Users\Administrator>gitbook -V
CLI version: 2.3.2
GitBook version: 3.2.3
```

**2、安装编辑器**

Git Book [legacy（旧版）官网](https://legacy.gitbook.com/editor)下载GitBook Editor（目前好像官网不提供离线编辑器了，点击链接跳转到了新版官网），执行安装文件。

打开Editor，发现是要登录的。

忙活好久，去官网注册账号，发现[legacy（旧版）官网](https://legacy.gitbook.com/)和[新版官网](https://gitbook.com/)的账号**不是**通用的！！

旧版官网注册不成功，新版注册成功，但是不能在Editor上登录成功，桌面编辑器貌似只针对旧版账号可用！

失望之至的时候，看到Editor欢迎页有“Do that later”小字T\_T

![](/assets/gitbookeditorwelcome.png)

点击“Do that later”，可以进入编辑器！

