![jane-preview](https://raw.githubusercontent.com/xianmin/hugo-theme-jane/master/images/preview.png)

## hugo-theme-jane

Jane is a readable theme for Hugo. It's a fork of the [hugo-theme-even](https://github.com/olOwOlo/hugo-theme-even) and made a lot of changes.

[Demo](http://en.xianmin.org/hugo-theme-jane/) | [My blog](http://www.xianmin.org) | [中文说明](https://github.com/xianmin/hugo-theme-jane/blob/master/README-zh.md)

This theme focuses on improving reading experience.


## Getting Started

Clone this repository to your hugo theme directory.

```bash
mkdir themes
cd themes
git clone https://github.com/xianmin/hugo-theme-jane.git
```

## Site Configuration

Take a look in the [exampleSite](https://github.com/xianmin/hugo-theme-jane/tree/master/exampleSite) folder.

This directory contains an example config file and the content for the demo.
It serves as an example setup for your documentation.

Copy the `config.toml` in the root directory of your website. Overwrite the existing config file if necessary.

__[config.toml](https://github.com/xianmin/hugo-theme-jane/blob/master/exampleSite/config.toml)__:

```toml
baseURL = "http://localhost:1313/"
title = "Jane - A super concise theme for Hugo"
enableRobotsTXT = true
enableEmoji = true
theme = "jane"

# language support # en / zh-cn / other...
defaultContentLanguage = "en"
[Languages.en]
  languageCode = "en"

hasCJKLanguage = true     # has chinese/japanese/korean ? # 自动检测是否包含 中文\日文\韩文
paginate = 3                                              # 首页每页显示的文章数
disqusShortname = ""      # disqus_shortname
googleAnalytics = ""      # UA-XXXXXXXX-X
copyright = ""            # default: author.name ↓        # 默认为下面配置的author.name ↓

[author]                  # essential                     # 必需
  name = "xianmin"

[sitemap]                 # essential                     # 必需
  changefreq = "weekly"
  priority = 0.5
  filename = "sitemap.xml"

[[menu.main]]             # config your menu              # 配置目录
  name = "Home"
  weight = 10
  identifier = "home"
  url = "/"
[[menu.main]]
  name = "Archives"
  weight = 20
  identifier = "archives"
  url = "/post/"
[[menu.main]]
  name = "Tags"
  weight = 30
  identifier = "tags"
  url = "/tags/"
[[menu.main]]
  name = "Categories"
  weight = 40
  identifier = "categories"
  url = "/categories/"

[params]
  debug = false             # If true, load `eruda.min.js`. See https://github.com/liriliri/eruda

  since = "2017"            # Site creation time          # 站点建立时间

  # site info (optional)                                  # 站点信息（可选，不需要的可以直接注释掉）
  logoTitle = "Jane"        # default: the title value    # 默认值: 上面设置的title值
  keywords = ["Hugo", "theme","jane"]
  description = "Hugo theme jane example site."

  # paginate of archives, tags and categories             # 归档、标签、分类每页显示的文章数目，建议修改为一个较大的值
  archive-paginate = 3

  # The date format to use; for a list of valid formats, see https://gohugo.io/functions/format/
  dateFormatToUse = "2006-01-02"

  # show word count and read time ?                       # 是否显示字数统计与阅读时间
  moreMeta = true

  # 一些全局开关，你也可以在每一篇内容的 front matter 中针对单篇内容关闭或开启某些功能，在 archetypes/default.md 查看更多信息。
  # Some global options, you can also close or open something in front matter for a single post, see more information from `archetypes/default.md`.
  toc = true                                                                            # 是否开启目录
  autoCollapseToc = false   # Auto expand and collapse toc                              # 目录自动展开/折叠
  fancybox = true           # see https://github.com/fancyapps/fancybox                 # 是否启用fancybox（图片可点击）
  bootcdn = false           # In china. @Deprecated: use [params.publicCDN]             # 是否使用bootcdn(@Deprecated: 请使用[params.publicCDN])
  mathjax = false           # see https://www.mathjax.org/                              # 是否使用mathjax（数学公式）
  contentCopyright = '<a rel="license noopener" href="https://creativecommons.org/licenses/by-nc-nd/4.0/" target="_blank">CC BY-NC-ND 4.0</a>'

  changyanAppid = ""        # Changyan app id             # 畅言
  changyanAppkey = ""       # Changyan app key
  baidu_push = false        # baidu push                  # 百度
  baidu_analytics = ""      # Baidu Analytics
  baidu_verification = ""   # Baidu Verification
  google_verification = ""  # Google_Verification         # 谷歌

  [params.publicCDN]        # load these files from public cdn                          # 启用公共CDN，需自行定义
    enable = false
    jquery = '<script src="https://cdn.jsdelivr.net/npm/jquery@3.2.1/dist/jquery.min.js" integrity="sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=" crossorigin="anonymous"></script>'
    slideout = '<script src="https://cdn.jsdelivr.net/npm/slideout@1.0.1/dist/slideout.min.js" integrity="sha256-t+zJ/g8/KXIJMjSVQdnibt4dlaDxc9zXr/9oNPeWqdg=" crossorigin="anonymous"></script>'
    fancyboxJs = '<script src="https://cdn.jsdelivr.net/npm/@fancyapps/fancybox@3.1.20/dist/jquery.fancybox.min.js" integrity="sha256-XVLffZaxoWfGUEbdzuLi7pwaUJv1cecsQJQqGLe7axY=" crossorigin="anonymous"></script>'
    fancyboxCss = '<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fancyapps/fancybox@3.1.20/dist/jquery.fancybox.min.css" integrity="sha256-7TyXnr2YU040zfSP+rEcz29ggW4j56/ujTPwjMzyqFY=" crossorigin="anonymous">'

  [params.reward]                                         # 文章打赏
    enable = false
    wechat = "/path/to/your/wechat-qr-code.png"           # 微信二维码
    alipay = "/path/to/your/alipay-qr-code.png"           # 支付宝二维码

  [params.social]                                         # 社交链接
    a-email = "mailto:your@email.com"
    b-stack-overflow = "http://localhost:1313"
    c-twitter = "http://localhost:1313"
    d-facebook = "http://localhost:1313"
    e-linkedin = "http://localhost:1313"
    f-google = "http://localhost:1313"
    g-github = "http://localhost:1313"
    h-weibo = "http://localhost:1313"
    i-zhihu = "http://localhost:1313"
    j-douban = "http://localhost:1313"
    k-pocket = "http://localhost:1313"
    l-tumblr = "http://localhost:1313"
    m-instagram = "http://localhost:1313"
```

## Build

```
hugo server
```

You can go to localhost:1313 and this theme should be visible.

## License

Hugo-theme-jane is licensed under the MIT license. Check the [LICENSE](LICENSE.md) file for details.