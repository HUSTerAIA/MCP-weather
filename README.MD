[reference](https://modelcontextprotocol.io/quickstart/server#claude-for-desktop-integration-issues)

[show](https://claude.ai/share/2eb48931-2fd3-4522-9174-f92603225029)

```json
{
  "mcpServers": {
    "weather": {
      "command": "node",
      "args": ["D:\\fanruan\\MCP\\weather\\build\\index.js"]
    }
  }
}
```


# 通信流程
```mermaid
graph TD
    A[客户端请求] --> B[stdio传输层]
    B --> C[MCP服务器]
    C --> D{解析工具调用}
    D -->|get_alerts| E[查询天气警报]
    D -->|get_forecast| F[查询天气预报]
    E --> G[NWS API]
    F --> G
    G --> H[处理响应]
    H --> I[格式化数据]
    I --> J[返回客户端]
```