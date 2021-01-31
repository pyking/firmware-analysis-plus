# firmware-analysis-plus
[![Python 3.7+](https://img.shields.io/badge/python-3.7+-3776AB?logo=Python&logoColor=FFFFFF&style=flat)](https://www.python.org/)
[![issues](https://img.shields.io/github/issues/liyansong2018/firmware-analysis-plus)](https://github.com/liyansong2018/firmware-analysis-plus/issues)
![license](https://img.shields.io/github/license/liyansong2018/firmware-analysis-plus)

本项目依赖于 [firmadyne](https://github.com/firmadyne/firmadyne) 以及 [firmware-analysis-toolkit](https://github.com/attify/firmware-analysis-toolkit)，修复了其中的大量bug，可直接运行固件。

| FAP 版本                                                     | python 版本      | 支持系统                                        | 安装方法                                                     |
| ------------------------------------------------------------ | ---------------- | ----------------------------------------------- | ------------------------------------------------------------ |
| [v0.1](https://github.com/liyansong2018/firmware-analysis-plus/releases/tag/0.1) | python2、python3 | Ubuntu16.04、Ubuntu 18.04、Kali 2020.02         | [FAP v0.1 版本手册](https://github.com/liyansong2018/firmware-analysis-plus/wiki/FAP-v0.1-%E7%89%88%E6%9C%AC%E6%89%8B%E5%86%8C) |
| [v1.0](https://github.com/liyansong2018/firmware-analysis-plus/releases/tag/1.0) | python2、python3 | beta                                            | beta                                                         |
| [v2.0](https://github.com/liyansong2018/firmware-analysis-plus/releases/tag/2.0) | python3          | Kali 2020.04（不支持 Ubuntu 20.04，其他未测试） | 如下所示                                                     |



## 安装 binwalk
以编译源码的方式安装`binwalk`，时至今日，`binwalk` 构建脚本中的诸多依赖已无法正常安装，于是自己 `fork` 了一份新的 `binwalk`，进行了修改。关于修改细节的描述，可参考：https://github.com/liyansong2018/binwalk
```
git clone https://github.com/liyansong2018/binwalk.git
cd binwalk
./deps.sh
sudo python3 setup.py install
```

## 安装 FAP

```shell
git clone https://github.com/liyansong2018/firmware-analysis-plus.git
cd firmware-analysis-plus
./setup.sh
```

## 配置
修改 `fat.config` 文件中的密码，改为 root 系统用户的密码

## 运行

```
./fat.py -q ./2.5.0/ ./testcases/wnap320_V3.7.11.4_firmware.tar
```

![run](images/run.png)

## 重新运行固件时，请删除中间文件
```shell
./reset.py
```

博客: [使用 firmware-analysis-plus 一键模拟固件](https://blog.csdn.net/song_lee/article/details/105518309)
