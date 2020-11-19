## 用Markdown语言编辑站点

每次编辑.md文件之后，Github都会通过jerkyll那个服务把对应的视觉效果加上去，从而形成一个（一系列）风格比较统一的网页。

可以用三个“`”来高亮显示并标注代码块，后面跟所用语言即可。 结束时用三个同样的符号标注即可。

测试：
```python
def plotScatter(var1, var2, cutoff = 10):
    plt.scatter(x,y, vmin = np.quantile(var2, cutoff)
        , vmax = np.quantile(var2, 100-cutoff))
```

两个`之间的内容也会被识别为代码。

井号用于heading，井号数量多则字体小（级别低）。减号用于bullet list，星号也是。
次级列表的话，每打2个空格缩进一级。

数字列表的格式是数字加dot加空格，空格之后再输入内容。

粗体内容前后各加两个星号，或者两个下划线；斜体前后只需各一个星号或者各一个下划线。
划掉的内容是用前后两个波浪线~来表示

-, 空格，[, x, ]可以组成一个打勾框

- [x] this is a complete item


添加链接：
[Link alt text](url) 

添加图像：
![Image alt text](image url)


For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

修改 `_config.yml` 可以改页面主题。
