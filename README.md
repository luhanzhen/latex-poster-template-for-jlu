# overleaf https://www.overleaf.com

# 注意使用LuaLatex编译器，普通pdfLatex编译不通过

# 通过修改beamercolorthemenott.sty文件中的nottblue，可以更换色彩，其余部分的色彩也可以修改。

# logo是通过如下代码将图片掏成png的，可以替换为其它logo，但是要掏空白色部分， 否则不好看

```python
from PIL import Image

if __name__ == "__main__":
    image = Image.open("你的图片.xxx")
    image = image.convert("RGBA")
    w, h = image.size

    for x in range(0, w):
        for y in range(0, h):
            r, g, b, a = image.getpixel((x, y))
            if r >= 250 and g >= 250 and b >= 250:
                a = 0
                image.putpixel((x, y), (r, g, b, a))
            else:
                image.putpixel((x, y), (224,229, 232, a))

    image.save("output.png")
```

# 允许使用其它latex模板 但是要符合学院的要求

