# 2560_mcp

## 如何在 VS Code 啟用 GitHub MCP Server

1. 在 VS Code 的 `settings.json` 新增以下設定：

```json
"github": {
  "command": "docker",
  "args": [
    "run",
    "-i",
    "--rm",
    "-e",
    "GITHUB_PERSONAL_ACCESS_TOKEN",
    "ghcr.io/github/github-mcp-server"
  ],
  "env": {
    "GITHUB_PERSONAL_ACCESS_TOKEN": "${input:github_token}"
  }
}
```

2. 這段設定參考自 [github-mcp-server 官方說明](https://github.com/github/github-mcp-server)。

3. 設定說明：
   - 這會讓 VS Code 透過 Docker 啟動 GitHub MCP Server。
   - 你需要有 Docker 環境，並準備好 GitHub Personal Access Token。
   - `${input:github_token}` 可在 VS Code 的 `settings.json` 內以 `inputs` 機制設定。

4. 進階設定與疑難排解，請參考官方文件。

---

如有問題，請參考官方文件或至 Issues 區回報。