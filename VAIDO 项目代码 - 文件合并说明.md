# VAIDO 项目代码 - 文件合并说明

## 📦 文件分割信息

由于 GitHub 网页上传限制为 25MB，原始的 246MB ZIP 文件已被分割成 13 个小文件：

- `vaido-source.zip.partaa` (20MB)
- `vaido-source.zip.partab` (20MB)
- `vaido-source.zip.partac` (20MB)
- `vaido-source.zip.partad` (20MB)
- `vaido-source.zip.partae` (20MB)
- `vaido-source.zip.partaf` (20MB)
- `vaido-source.zip.partag` (20MB)
- `vaido-source.zip.partah` (20MB)
- `vaido-source.zip.partai` (20MB)
- `vaido-source.zip.partaj` (20MB)
- `vaido-source.zip.partak` (20MB)
- `vaido-source.zip.partal` (20MB)
- `vaido-source.zip.partam` (5.8MB)

## 🔄 合并步骤

### Windows 用户

1. 将所有 `vaido-source.zip.part*` 文件放在同一个文件夹中
2. 打开命令提示符（CMD）或 PowerShell
3. 进入文件所在目录
4. 运行以下命令：

```powershell
# PowerShell
cmd /c "copy /b vaido-source.zip.part* vaido-source.zip"

# 或者使用 PowerShell
Get-Content vaido-source.zip.part* | Set-Content vaido-source.zip -Encoding Byte
```

### macOS / Linux 用户

1. 将所有 `vaido-source.zip.part*` 文件放在同一个文件夹中
2. 打开终端
3. 进入文件所在目录
4. 运行以下命令：

```bash
cat vaido-source.zip.part* > vaido-source.zip
```

## ✅ 验证合并

合并完成后，验证文件完整性：

```bash
# 查看文件大小（应该是 246MB）
ls -lh vaido-source.zip

# 测试 ZIP 文件是否完整
unzip -t vaido-source.zip
```

## 📂 解压文件

合并完成后，解压 ZIP 文件：

```bash
unzip vaido-source.zip
```

这将创建 `vaito` 文件夹，包含所有项目代码。

## 📝 项目内容

解压后的 `vaito` 文件夹包含：

- `client/` - React 前端代码
- `server/` - Express 后端代码
- `drizzle/` - 数据库 Schema 和迁移
- `shared/` - 共享代码
- `package.json` - 项目依赖
- `.env.example` - 环境变量模板
- 其他配置文件和脚本

## 🚀 后续步骤

1. 解压后，在项目根目录运行：
   ```bash
   pnpm install
   ```

2. 配置环境变量：
   ```bash
   cp .env.example .env.local
   # 编辑 .env.local 填写必要的配置
   ```

3. 初始化数据库：
   ```bash
   pnpm db:push
   ```

4. 启动开发服务器：
   ```bash
   pnpm dev
   ```

## ❓ 问题排查

### 合并失败
- 确保所有 part 文件都在同一个文件夹中
- 确保文件名完整（partaa 到 partam）
- 检查磁盘空间是否足够（至少需要 500MB）

### 解压失败
- 使用专业的 ZIP 工具（如 7-Zip、WinRAR）
- 确保 ZIP 文件完整（可用 `unzip -t` 测试）

## 📞 需要帮助？

如有任何问题，请参考项目的 README.md 或联系项目维护者。
