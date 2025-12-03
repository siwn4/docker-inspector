# 🔍 通用 Docker 镜像侦查器

一键深度分析任何 Docker 镜像，支持 Docker Hub、GitHub Container Registry 等所有镜像源！

## 🚀 快速使用

1. 点击 [Actions](../../actions)
2. 选择 **Universal Image Inspector**
3. 点击 **Run workflow**
4. 输入镜像名，支持多种格式：
   - `nginx` → 自动识别为 docker.io/library/nginx:latest
   - `lmentory/wee` → 自动识别为 docker.io/lmentory/wee:latest
   - `ghcr.io/用户/仓库:tag` → GitHub 镜像
   - `node:18-alpine` → 指定版本
5. （可选）修改提取路径，默认 `/app`

## 📦 支持的镜像格式

| 输入格式 | 自动处理结果 |
|----------|------------|
| `nginx` | `docker.io/library/nginx:latest` |
| `nginx:alpine` | `docker.io/library/nginx:alpine` |
| `lmentory/wee` | `docker.io/lmentory/wee:latest` |
| `mysql:8.0` | `docker.io/library/mysql:8.0` |
| `ghcr.io/owner/repo` | `ghcr.io/owner/repo:latest` |
| `quay.io/xxx/yyy` | `quay.io/xxx/yyy:latest` |

## 📊 侦查内容

### 在 Summary 中查看
- ✅ 镜像基本信息（大小、创建时间、架构）
- ✅ 启动配置（Entrypoint、CMD、WorkingDir）
- ✅ 环境变量列表
- ✅ 文件系统结构
- ✅ 所有脚本文件路径
- ✅ 启动脚本完整内容
- ✅ 配置文件列表

### 在 Artifacts 中下载
- 📦 `docker-image-files.zip` - 包含：
  - 镜像完整配置 JSON
  - 提取的文件目录
  - 所有启动脚本
  - 配置文件

## 🔍 示例镜像

### 官方镜像
- `nginx` - Web 服务器
- `redis` - 缓存数据库
- `mysql:8.0` - 关系数据库
- `node:18` - Node.js
- `python:3.11` - Python
- `alpine` - 轻量 Linux

### GitHub 镜像
- `ghcr.io/fish2018/pansou`
- `ghcr.io/你的用户名/你的仓库`

### 其他镜像
- `lmentory/wee` - WebDAV
- `quay.io/coreos/etcd` - etcd

## 💡 使用技巧

### 自定义提取路径
- 默认提取 `/app`
- 可改为 `/` 提取整个文件系统
- 或指定如 `/etc` 只看配置

### 查看特定内容
运行后在 Summary 中可以看到：
1. 启动命令是什么
2. 需要哪些环境变量
3. 有哪些脚本文件
4. 工作目录在哪里

## 🎯 使用场景

- 🔧 改造现有镜像前的调研
- 📚 学习其他镜像的构建方式
- 🐛 调试镜像启动问题
- 🔍 安全审计镜像内容
- 📦 提取镜像中的文件

---

Made with ❤️ for Docker exploration
