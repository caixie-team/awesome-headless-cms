# Headless CMS 资源贡献方法

_提示: **不要** 去生成 README.md. 我们会在你的 pull request 之后生成._

## GitHub 中的贡献方式

### 1. 在 [data 文件夹中](/data) 按下面的命名方式 [新建文件][]:

- 开源项目? 文件名必需使用 _小写英文字母_ 命名文件名, 示例 `org#repo.toml`.
- 闭源项目? 文件名必需使用 _小写英文字母_ 命名产品名, 二级名称用 _-_ 短横线分隔，示例 `product-name.toml`.

### 2. 完善文件内容, 采用 toml 格式，示例如下:

```toml
name = ""
description = ""
# Github 项目的访问地址，或者官方网站
url = ""
# 如果这个项目有更多优秀资源，可以填写资源列表地址
awesome_repo = "org/repo"
# 只有项目是开源的情况下需要添写
github_repo = "org/repo"
# 项目采用的程序语言，小写英文字母.示例: javascript, php, c#.
language = ""
```

**完整示例**

```toml
name = "Directus"
description = "Directus is an API-driven content management framework for custom databases. It decouples content for use in apps, websites, or any other data-driven projects."
url = "https://getdirectus.com/"
github_repo = "directus/directus"
language = "javascript"
```

### 3. 开始一个 pull request 之前.

请再次确认已完成请求模板中的检查项 [pull request template](/PULL_REQUEST_TEMPLATE.md).

## 项目贡献步骤

1. Fork the repo on GitHub.
1. Clone the project.
1. Follow the steps above.
1. Push your work back up to your fork.
1. Submit a pull request.

## 从 URL 中生成 [TOML][]

在 [`scripts`](/scripts) 中包含一个脚本文件 `urlToToml.js`, 使用这个脚本会使容易从 URL 中提取 TOML. 用法如下：

```
node scripts/urlToToml.js https://github.com/jekyll/jekyll-admin
```

生成

```toml
name = "Jekyll Admin - A Jekyll plugin that provides users with a traditional CMS-style graphical interface to author content and administer Jekyll sites."
description = "A Jekyll plugin that provides users with a traditional CMS-style graphical interface to author content and administer Jekyll sites."
url = "https://jekyll.github.io/jekyll-admin/"
github_repo = "jekyll/jekyll-admin"
language = "javascript"
```

数据抓取采用 [X-Ray](https://github.com/lapwinglabs/x-ray). 

# README.md 是怎样生成的

_所有脚本的运行需要 **Node 6** 或更高的版本. 使用 [NVM][] 可以很容易管理安装适合的版本库._

### readme.md 所需的数据文件

在 [`/data`](/data) 文件夹中的数据文件与 [meta.toml](/meta.toml) 一起生成了 README 文件，这些数据文件采用了一种比较人性化的脚本标语言 [TOML][], 

执行生成的命令如下：

```
# Edit something in /data
npm install
npm run generateReadme
```

[NVM]: https://github.com/creationix/nvm
[TOML]: https://github.com/toml-lang/toml
[Create a new file]: https://github.com/postlight/awesome-cms/new/master/data?filename=org%23repo.toml