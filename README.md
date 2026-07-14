# opene906-env
一键获取平头哥 openE906 RISC-V 处理器仿真环境，基于 Docker。

## 快速开始

```bash
# 1. 拉取镜像
docker pull jiqian/opene906-env:latest

# 2. 启动容器
docker run -it --rm jiqian/opene906-env:latest /bin/bash

# 3. 加载环境
source ~/e906-setup

# 4. 运行 Hello World
make runcase CASE=hello_world

```
## 预期输出

```bash
Hello Friend!
Welcome to T-HEAD World!
a is 1!
b is 2!
c is 0!
!!! PASS !!!after ASM c is changed to 3!
**********************************************
*    simulation finished successfully        *
**********************************************
```
