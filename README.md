

https://github.com/user-attachments/assets/861903ab-d810-473d-a415-f1772090a183

# 🎬 在线短视频去水印解析工具

一个功能强大的在线短视频去水印解析工具，支持抖音、快手、B站、微博等 20+ 主流平台。

---



## ✨ 功能特性

- 🔗 **多平台支持** - 支持抖音、快手、B站、微博、微信、皮皮虾等 20+ 平台
- 🎯 **自动去水印** - 自动解析获取无水印视频链接
- 📺 **视频预览** - 解析后可直接在线预览视频
- ⬇️ **一键下载** - 支持视频、封面一键下载
- 🎨 **精美界面** - 深色主题设计，毛玻璃效果
- 📱 **响应式布局** - 完美适配手机、平板、桌面设备
- 🐳 **Docker 部署** - 支持 Docker 一键部署

---

## 🛠️ 技术栈

- **后端**: Python 3.10+ + FastAPI + Uvicorn
- **HTTP 客户端**: httpx
- **HTML 解析**: BeautifulSoup4
- **前端**: HTML5 + CSS3 + JavaScript (原生)

---

## 🚀 快速开始

### 环境要求

- Python 3.10+
- pip 包管理工具

### 安装依赖

```bash
# 克隆项目
git clone https://github.com/zwl568633995/douyin-video-decode.git
cd douyin-video-decode

# 安装依赖
pip install -r requirements.txt
```

### 启动服务

```bash
# 开发模式运行
python main.py

# 或使用 Uvicorn 启动
uvicorn main:app --host 0.0.0.0 --port 8000
```

访问地址: http://localhost:8000

### Docker 部署

```bash
# 构建镜像
docker build -t video-parser .

# 运行容器
docker run -d -p 8000:3308 --name video-parser video-parser
```

---

## 📡 API 接口

### 1. 通过分享链接解析

```
GET /video/share/url/parse?url=<视频链接>
```

**示例**:
```bash
curl "http://localhost:8000/video/share/url/parse?url=https://v.douyin.com/dpbzIoJ_hwo/"
```

**响应**:
```json
{
    "code": 200,
    "msg": "解析成功",
    "data": {
        "video_url": "https://.../video.mp4",
        "cover_url": "https://.../cover.jpg",
        "title": "视频标题",
        "images": [],
        "author": {
            "uid": "作者ID",
            "name": "作者昵称",
            "avatar": "头像URL"
        }
    }
}
```

### 2. 通过视频ID解析

```
GET /video/id/parse?source=<平台>&video_id=<视频ID>
```

**支持的平台**:
- `douyin` - 抖音
- `kuaishou` - 快手
- `bilibili` - 哔哩哔哩
- `weibo` - 微博

---

## 📁 项目结构

```
douyin-video-decode/
├── src/
│   └── parse_video_py/
│       ├── __init__.py
│       ├── cli/
│       ├── parser/          # 各平台解析器
│       │   ├── douyin.py
│       │   ├── kuaishou.py
│       │   └── ...
│       ├── templates/       # HTML 模板
│       │   └── index.html
│       ├── img/             # 静态图片资源
│       └── web.py           # Web 路由
├── main.py                  # 入口文件
├── Dockerfile
└── requirements.txt
```

---

## 📱 支持平台

| 平台 | 状态 |
|------|------|
| 🎵 抖音 | ✅ |
| 🎬 快手 | ✅ |
| 📺 B站 | ✅ |
| 📱 微博 | ✅ |
| 💬 微信 | ✅ |
| 🎭 皮皮虾 | ✅ |
| 🔥 火山 | ✅ |
| 🍉 西瓜视频 | ✅ |
| 🎮 虎牙 | ✅ |
| 📖 小红书 | ✅ |
| 以及更多... | ✅ |

---

## ⚠️ 免责声明

本项目仅用于学习和研究目的，请勿用于商业用途。请遵守各平台的使用条款和法律法规。

---

## 📄 许可证

MIT License

---

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

---

Made with ❤️
