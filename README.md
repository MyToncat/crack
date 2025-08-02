# Crack - Software License Tools

一个用于生成和管理各种软件许可证的Python工具集合。

## ⚠️ 免责声明

本项目仅供学习和研究目的使用。请遵守相关软件的许可协议和当地法律法规。作者不对任何滥用行为承担责任。

## 🚀 功能特性

- **多软件支持**: 支持多种主流软件的许可证生成
- **模块化设计**: 每个软件模块独立，易于扩展和维护
- **统一接口**: 所有模块都基于统一的抽象基类
- **Web服务**: 提供HTTP API接口，方便集成使用

## 📦 支持的软件

| 软件 | 模块 | 状态 |
|------|------|------|
| JetBrains IDEs | `jetbrains` | ✅ 完整支持 |
| Atlassian 产品 | `atlassian` | ✅ 完整支持 |
| DBeaver | `dbeaver` | ✅ 完整支持 |
| FinalShell | `finalshell` | ✅ 完整支持 |
| GitLab EE | `gitlab` | ✅ 完整支持 |
| Typora | `typora` | 🚧 开发中 |
| XMind | `xmind` | ✅ 完整支持 |
| Surely | `surely` | ✅ 完整支持 |

## 🛠️ 安装

### 环境要求

- Python 3.12+
- uv (推荐) 或 pip

### 安装步骤

1. 克隆仓库：
```bash
git clone <repository-url>
cd crack
```

2. 安装依赖：
```bash
# 使用 uv (推荐)
uv sync

# 或使用 pip
pip install -e .
```

## 📖 使用指南

### 基本用法

每个软件模块都提供了独立的许可证生成功能：

```python
from crack.jetbrains import JetbrainsKeyGen

# 生成 JetBrains 许可证
keygen = JetbrainsKeyGen()
keygen.run()
```

### Web 服务

启动 JetBrains 许可证服务器：

```python
from crack.jetbrains.server import app
import uvicorn

uvicorn.run(app, host="0.0.0.0", port=5000)
```

访问 `http://localhost:5000` 查看可用的API端点。

### 命令行使用

```bash
# 进入对应模块目录
cd src/crack/jetbrains

# 运行许可证生成
python jetbrains.py
```

## 🏗️ 项目结构

```
crack/
├── src/crack/           # 主要源代码
│   ├── base.py         # 抽象基类
│   ├── jetbrains/      # JetBrains 相关工具
│   ├── atlassian/      # Atlassian 相关工具
│   ├── dbeaver/        # DBeaver 相关工具
│   ├── finalshell/     # FinalShell 相关工具
│   ├── gitlab/         # GitLab 相关工具
│   ├── typora/         # Typora 相关工具
│   ├── xmind/          # XMind 相关工具
│   └── surely/         # Surely 相关工具
├── pyproject.toml      # 项目配置
├── uv.lock            # 依赖锁定文件
└── README.md          # 项目说明
```

## 🔧 开发

### 开发环境设置

1. 安装开发依赖：
```bash
uv sync --dev
```

2. 安装预提交钩子：
```bash
pre-commit install
```

### 代码规范

- 使用 `black` 进行代码格式化
- 使用 `pylint` 进行代码检查
- 使用 `mypy` 进行类型检查
- 遵循 PEP 8 编码规范

### 运行测试

```bash
pytest tests/
```

## 📝 许可证

本项目采用 MIT 许可证。详见 [LICENSE](LICENSE) 文件。

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

## 📞 联系

如有问题或建议，请通过 Issue 联系。

---

**注意**: 请确保在使用本工具时遵守相关法律法规和软件许可协议。