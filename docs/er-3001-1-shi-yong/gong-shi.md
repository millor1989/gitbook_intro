可以用在线公式编辑器协助书写公式：[https://www.latexlive.com](https://www.latexlive.com)

执行`gitbook serve`后公式无法显示为公式，而是显示为普通文本；需要在book.json中加入`"plugins":["katex"]`，然后还需要执行`gitbook install`安装插件；插件安装完成后，执行`gitbook serve`就能看到正常显示的公式了。

