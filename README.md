# 服务器代理服务 Server Proxy Service

如果你觉得本项目对你有用,而且你也恰巧有这方面的需求,你也可以选择通过我的购买链接赞助我  
- [搬瓦工GIA服务器](https://bandwagonhost.com/aff.php?aff=41846)  - - - 仅推荐购买GIA套餐 - - -   

如果你希望购买一些现成的代理服务,可选择下述代理服务
- [搬瓦工官方机场](https://justmysocks.net/members/aff.php?aff=16884)  

## 微软azure文本转语音 音频下载
*Demo* : [https://tts.131213.xyz/](https://tts.131213.xyz/)


> *本文由GitHub Copilot 生成*

### 1. 介绍

本项目是基于微软azure的文本转语音服务，通过调用微软azure的api接口，将文本转换为语音，然后下载到本地。

### 2. 安装说明

#### 利用Cloudflare Workers部署

1. 新建一个 Cloudflare Worker

2. 将 [cf_worker.js](https://github.com/x-dr/tts/blob/main/cf_worker.js) 中的代码复制到 Cloudflare Worker 中并部署即可

<img src="https://img1.131213.xyz/file/23f45cf2a989a13842839.png" width="600px">

> 修改前端
 
`https://raw.githubusercontent.com/x-dr/cf_pages/main/tts.html` 是前端代码 ，想修改的自己修改cf_worker.js中的下面行就行

```javascript
    const html = await fetch("https://raw.githubusercontent.com/x-dr/cf_pages/main/tts.html")
```

***

#### 利用docker部署

1. 下载docker镜像

```bash
docker pull gindex/tts-azure:latest
```

2. 运行容器

```bash
docker run -itd \
           --name tts \
            -p 3035:3035 \
           --restart=always \
           gindex/tts-azure:latest
```

3. 访问地址

```bash
http://ip:3035/
```


***

#### 利用Vercel部署


[![Deploy with Vercel](https://vercel.com/button?utm_source=busiyi&utm_campaign=oss)](https://vercel.com/new/clone?utm_source=busiyi&utm_campaign=oss&repository-url=https://github.com/x-dr/tts)

#### 利用Linux服务器部署

1. 安装nodejs (如果已经安装过nodejs则跳过此步骤)

```bash
curl -sL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt-get install -y nodejs
```

2. 安装git (如果已经安装过git则跳过此步骤)

```bash
sudo apt-get install git
```

3. 下载项目

```bash
git clone https://github.com/x-dr/tts.git
```

4. 安装依赖

```bash
cd tts
npm install
```

5. 运行项目

```bash
node index.js
```

6. 访问地址

```bash
http://ip:3035/
```

### 3. 使用说明

