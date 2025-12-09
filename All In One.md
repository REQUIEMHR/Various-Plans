# All In One 配置及其相关配置测试

## 测试nas配置

- nextcloud测试小主机配置

|配件类型| 型号 | 价格 |
| :----: | :----: | :----: |
| 主板 | 技嘉B85 小板 | 59 | 
| CPU | i3 4170 | 19 | 
|散热器|超频青鸟3|24|
| 内存 | 威刚4G*2 ddr3 1333hz | 32 |
|固态| 联想120G | 48 | 
|机械硬盘| 西部数据 500g | 44 |
|电源| 长城电源 | 43 | 
|机箱| matx | 25 |

### 在初始Ubuntu系统下安装docker，并基于LNMP搭建Nextcloud

#### 1. 系统更新

更新系统包列表
``` bash
sudo apt update
sudo apt upgrade -y
```

安装Docker所需的基础工具
``` bash
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common gnupg lsb-release
```

#### 2. 安装Docker

添加Docker官方GPG密钥
``` bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

添加Docker仓库
``` bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

安装Docker引擎
``` bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

验证Docker安装
```bash
sudo docker --version
```

将当前用户添加到docker组，避免每次使用sudo
```bash
sudo usermod -aG docker $USER
```

启动Docker服务
```bash
sudo systemctl start docker
sudo systemctl enable docker
```
重新登录或运行以下命令使组更改生效
```bash
newgrp docker
```





## All In One 配置

|配件类型| 型号 | 价格 |
| :----: | :----: | :----: |
| 主板 | 微星 MAG B760M MORTAR WIFI DDR4 | 1200 | 
| CPU | i5 12400 | 1268 | 
| 散热器| 利民 AXP120 - X47| 153 |
| 内存 | 金士顿 DDR4内存条 黑爵 16*2 | 1098 |
|固态| 金士顿NV3 M2固态硬盘 500G | 559 | 
|机械硬盘| 希捷酷狼 4T*4 | 4000 | 
|电源| 利民（Thermalright）TR-TGFX550 SFX金牌全模组小电源 | 429 | 
|机箱| 乔斯伯N2 | 579 | 

