# apidoc2

用于从Java项目中批量提取ApiDoc注解并生成API文档的Python工具，
支持多版本对比和自动生成apidoc文档。
仅仅适用于使用apidoc项目

## 功能简介

- 支持从指定Git仓库克隆Java项目，提取所有Java文件中的ApiDoc注解
- 支持多版本API文档对比，输出差异统计
- 自动生成apidoc格式文档，便于前端/后端协作
- 支持命令行参数自定义仓库、版本、输出文件名等

## 安装方法

推荐使用pip安装（需先打包上传到PyPI）：

```bash
pip install apidoc2
```

或本地安装：

```bash
git clone <your_repo_url>
cd apidoc2
pip install .
```

## 使用说明

### 基本用法

```bash
apidoc2 -r <git仓库地址> -v1 <当前版本号> [-v2 <对比版本号>] [-o <输出文件名>]
```

### 参数说明

- `-r, --repourl`：Git仓库地址（必填）
- `-v1, --version1`：当前版本号或分支名（必填）
- `-v2, --version2`：对比的历史版本号或分支名（可选）
- `-o, --output`：输出文件目录（可选，默认为output）

### 示例

1. 只提取当前版本API文档：
   ```bash
   apidoc2 -r https://your.git.repo/project.git -v1 master
   ```
2. 对比两个版本API文档差异：

   ```bash
   apidoc2 -r https://your.git.repo/project.git -v1 master -v2 develop
   ```

### 依赖

- Python 3.6+
- git
- apidoc（需全局安装，`npm install -g apidoc`）
