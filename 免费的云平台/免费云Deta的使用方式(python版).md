# 免费云Deta的使用方式(python版)



## 一.安装 Deta CLI

```shell
# Mac
curl -fsSL https://get.deta.dev/cli.sh | sh

# Linux
curl -fsSL https://get.deta.dev/cli.sh | sh

# Windows
iwr https://get.deta.dev/cli.ps1 -useb | iex

```



## 二.通过 CLI 登录 Deta

成功安装 Deta CLI 后，您需要登录 Deta。

```shell
# 在终端中，键入以下命令: 
deta login
```



## 三.使用 Deta



### 1.Micro



#### a.创建 micro

```shell
deta new --python [你的micro名称]

# 例如: 
deta new --python demo
```

这将在“云”中创建一个新的 Python Micro，并在名为 `demo` 的目录中创建一个本地副本，`demo`该目录将包含一个`main.py`文件。



#### b.设置和依赖项

进入目录 `demo` ，然后创建一个文件 ，`requirements.txt` 它告诉 Deta 要安装哪些依赖项。

让我们将 **fastapi** 添加到 `requirements.txt` 本地并保存此文件。

```tex
fastapi
```


在 `main.py` 中使用简单的 fastapi 应用程序创建一个文件。

```python
from fastapi import FastAPI
app = FastAPI()

@app.get("/")
async def root():    
    return "Hello World!"
```



#### c.部署本地更改

```shell
deta deploy
```



#### d.访问我们的网站

浏览器访问



#### e.其他问题



> 公开网站，禁用身份验证

```shell
deta auth disable
```



> 打开日志记录

```
deta visor enabled
```

