### 发布到Github Pages

Github repository的`Settings`选项下，有`Pages`设置——用来配置仓库的Pages（之前是直接在`Settings`下的`Options`中设置Github Pages，现在GitHub Pages有了专用的独立选项卡）。

![1623046492521](/assets/1623046492521.png)

只用选择代码分支、Pages目录即可。配置完成，通过Github Pages页面提示的URL，即可随时随地通过浏览器访问Pages。

GitHub pages的目录只支持使用`/` 或 `/docs/` 两个目录，如果仓库根目录下不是Pages内容，最好使用`/docs/`目录。使用`/docs`目录保存pages，将源代码和 pages 分开也是不错的选择。

已知`gitbook build` 可以将pages编译到自定义的目录，所以使用 `gitbook build` 编译gitbook 代码时将pages编译到`docs` 目录，推送到对应github仓库即可。