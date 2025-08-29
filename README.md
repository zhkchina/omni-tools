<div align="center">
        <img src="src/assets/logo.png" width="220" />
        <br /><br />
        <br /><br />
</div>

Welcome to OmniTools, a self-hosted web app offering a variety of online tools to simplify everyday tasks.
Whether you are coding, manipulating images/videos, PDFs or crunching numbers, OmniTools has you covered. Please don't
forget to
star the repo to support us.
 

All files are processed entirely on the client side: nothing ever leaves your device.
Plus, the Docker image is super lightweight at just 28MB, making it fast to deploy and easy to self-host.

![img.png](docs-images/img.png)

## Table of Contents

- [Features](#features)
- [Self-host](#self-hostrun)
- [Contribute](#contribute)
- [Contact](#contact)
- [License](#license)

## Features

We strive to offer a variety of tools, including:

### **Image/Video/Audio Tools**

- Image Resizer
- Image Converter
- Image Editor
- Video Trimmer
- Video Reverser
- And more...

### **PDF Tools**

- PDF Splitter
- PDF Merger
- PDF Editor
- And more...

### **Text/List Tools**

- Case Converters
- List Shuffler
- Text Formatters
- And more...

### **Date and Time Tools**

- Date Calculators
- Time Zone Converters
- And more...

### **Math Tools**

- Generate Prime Numbers
- Calculate voltage, current, or resistance
- And more...

### **Data Tools**

- JSON Tools
- CSV Tools
- XML Tools
- And more...

Stay tuned as we continue to expand and improve our collection!

## Self-host/Run

### Docker

```bash
docker run -d --name omni-tools --restart unless-stopped -p 8080:80 zhkchina/omni-tools:latest
```

### Docker Compose

```yaml
services:
  omni-tools:
    image: zhkchina/omni-tools:latest
    container_name: omni-tools
    restart: unless-stopped
    ports:
      - "8080:80"

```

## Contribute

This is a React Project with Typescript Material UI.

### Project setup

```bash
git clone https://github.com/zhkchina/omni-tools.git
cd omni-tools
npm i
npm run dev
```

### Create a new tool

```bash
npm run script:create:tool my-tool-name folder1 # npm run script:create:tool split pdf
```

For tools located under multiple nested directories, use:

```bash
npm run script:create:tool my-tool-name folder1/folder2 # npm run script:create:tool compress image/png
```

Use `folder1\folder2` on Windows.

### Run tests

```bash
npm run test
```

- For e2e tests

```bash
npm run test:e2e
```

 

## 🤝 Looking to contribute?

We welcome contributions! You can help by:

- Reporting bugs
- Suggesting new features
- Improving documentation
- Submitting pull requests

 

## Contact

For any questions or suggestions, feel free to open an issue or contact me at:
[zhkchina@gmail.com](mailto:zhkchina@gmail.com)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## TODO

- [x] CICD流程适配 用github action 自动推送docker，
  - [ ] 服务器先手工拉取镜像，正式上线标签才进入服务器自动更新
- [ ] 更新界面，去除不必要的版权标记和功能，页面静态化
  - [x] 去除不必要版权标记
- [ ] 修改语言模块，适配小语种
- [ ] 测试Google
- [ ] 调研多个docker的服务放在同一个域名不同目录下traefik或者caddy

## 关于测试

已有本地测试流程。下面是最小命令清单。
开发/预览
开发启动：npm run dev
生产预览：npm run build && npm run serve（E2E 会自动用这条）
单元测试（Vitest）
运行：npm run test
可视化模式：npm run test:ui
端到端测试（Playwright）
首次安装浏览器：npx playwright install
运行：npm run test:e2e
查看报告：npx playwright show-report
说明：会先执行 npm run build && npm run serve，预览端口默认 4173
质量检查
类型检查：npm run typecheck
Lint 修复：npm run lint
依赖安装（首次或切分支后）
npm install