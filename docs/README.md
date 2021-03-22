# 快速开始
建议docsify-cli全局安装，这有助于在本地初始化和预览网站。

npm i docsify-cli -g

# 初始化
如果要在./docs子目录中编写文档，则可以使用init命令。

docsify init ./docs

# 写作内容
在之后init完成后，你可以看到在文件列表./docs子目录。

index.html 作为入口文件
README.md 作为主页
.nojekyll 防止GitHub Pages忽略以下划线开头的文件

# 预览您的网站
使用运行本地服务器docsify serve。您可以在上的浏览器中预览站点http://localhost:3000。

docsify serve docs

# 手动初始化
如果您不喜欢npm该工具或在安装该工具时遇到问题，则可以手动创建index.html：

<!-- index.html -->

<!DOCTYPE html>
<html>
<head>
  <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <meta charset="UTF-8">
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/themes/vue.css" />
</head>
<body>
  <div id="app"></div>
  <script>
    window.$docsify = {
      //...
    }
  </script>
  <script src="//cdn.jsdelivr.net/npm/docsify@4"></script>
</body>
</html>

# 指定文档版本
请注意，在以下两个示例中，当发布新的主要版本的docsify（例如v4.x.x=> v5.x.x）时，都需要手动更新docsify URL 。定期检查docsify网站，以查看是否已发布新的主要版本。

在URL（@4）中指定主要版本将使您的网站自动获得不间断的增强功能（即“次要”更新）和错误修复（即“补丁”更新）。这是加载文档资源的推荐方法。

<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/themes/vue.css" />
<script src="//cdn.jsdelivr.net/npm/docsify@4"></script>
如果您希望将docsify锁定为特定版本，请@在URL中的符号后指定完整版本。这是确保您的网站外观和行为相同的最安全的方法，而不管对docsify的未来版本进行任何更改。

<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4.11.4/themes/vue.css">
<script src="//cdn.jsdelivr.net/npm/docsify@4.11.4"></script>

# 手动预览您的网站
如果您在系统上安装了python，则可以轻松地使用它来运行静态服务器来预览您的站点。

cd docs && python -m SimpleHTTPServer 3000
cd docs && python -m http.server 3000

# 载入对话框
如果需要，可以在docsify开始呈现文档之前显示一个加载对话框：

<!-- index.html -->

<div id="app">Please wait...</div>
data-app如果更改，则应设置属性el：

<!-- index.html -->

<div data-app id="main">Please wait...</div>

  <script>
    window.$docsify = {
      el: '#main'
    }
  </script>
比较el配置。