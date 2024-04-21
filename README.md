GitHub Actions 是一个自动化工具，它可以帮助你自动化软件工作流程，比如构建、测试和部署代码。下面是一个非常简单的 GitHub Action 示例，它用于在每次有人向 `main` 分支推送代码时，自动运行一个简单的 "Hello, World!" 脚本。

首先，你需要在你的 GitHub 仓库中创建一个 `.github/workflows` 目录。然后，在这个目录下创建一个 YAML 文件，例如 `hello_world.yml`。这个 YAML 文件将定义你的 GitHub Action 工作流程。

这是一个简单的 GitHub Action 示例文件的内容：

```yaml
name: Hello World Workflow

on:
  push:
    branches:
      - main

jobs:
  say_hello:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Run a one-line script
        run: echo "Hello, World!"
```

解释一下每部分的功能：
- `name`: 这个字段定义了工作流程的名字。
- `on`: 这部分定义了触发工作流程的事件，这里的例子是每次向 `main` 分支推送代码时触发。
- `jobs`: 定义要执行的工作列表。
  - `say_hello`: 这是一个作业的标识符。
  - `runs-on`: 指定运行作业的环境，这里是使用最新版的 Ubuntu。
  - `steps`: 定义作业中的步骤。
    - 第一个步骤使用 `actions/checkout@v3` 检出代码，这是必须的步骤，以便能够在工作流中访问仓库的内容。
    - 第二个步骤运行一行脚本，打印 "Hello, World!"。

这个例子非常基础，但足以展示如何设置一个简单的 GitHub Action 工作流程。你可以根据自己的需要添加更多的步骤和作业。
