<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "d700e180ce74b2675ce51a567a36c9e4",
  "translation_date": "2025-07-13T20:13:47+00:00",
  "source_file": "03-GettingStarted/05-sse-server/solution/python/README.md",
  "language_code": "tw"
}
-->
# 執行此範例

建議安裝 `uv`，但非必要，詳見[說明](https://docs.astral.sh/uv/#highlights)

## -0- 建立虛擬環境

```bash
python -m venv venv
```

## -1- 啟動虛擬環境

```bash
venv\Scrips\activate
```

## -2- 安裝相依套件

```bash
pip install "mcp[cli]"
```

## -3- 執行範例

```bash
mcp run server.py
```

## -4- 測試範例

在一個終端機啟動伺服器後，開啟另一個終端機並執行以下指令：

```bash
mcp dev server.py
```

這會啟動一個帶有視覺介面的網頁伺服器，讓你可以測試範例。

伺服器連線後：

- 嘗試列出工具並執行 `add`，參數為 2 和 4，結果應該會顯示 6。
- 前往 resources 和 resource template，呼叫 get_greeting，輸入一個名字，你應該會看到帶有該名字的問候語。

### CLI 模式測試

你執行的 inspector 實際上是個 Node.js 應用程式，而 `mcp dev` 是它的包裝器。

你可以直接用以下指令以 CLI 模式啟動：

```bash
npx @modelcontextprotocol/inspector --cli http://localhost:8000/sse --method tools/list
```

這會列出伺服器中所有可用的工具。你應該會看到以下輸出：

```text
{
  "tools": [
    {
      "name": "add",
      "description": "Add two numbers",
      "inputSchema": {
        "type": "object",
        "properties": {
          "a": {
            "title": "A",
            "type": "integer"
          },
          "b": {
            "title": "B",
            "type": "integer"
          }
        },
        "required": [
          "a",
          "b"
        ],
        "title": "addArguments"
      }
    }
  ]
}
```

要呼叫工具，輸入：

```bash
npx @modelcontextprotocol/inspector --cli http://localhost:8000/sse --method tools/call --tool-name add --tool-arg a=1 --tool-arg b=2
```

你應該會看到以下輸出：

```text
{
  "content": [
    {
      "type": "text",
      "text": "3"
    }
  ],
  "isError": false
}
```

> ![!TIP]
> 通常在 CLI 模式下執行 inspector 比在瀏覽器中快很多。
> 更多關於 inspector 的資訊請見[這裡](https://github.com/modelcontextprotocol/inspector)。

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們力求準確，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生的任何誤解或誤釋負責。