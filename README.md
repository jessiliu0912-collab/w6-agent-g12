（請記得將該檔名改命名為 `README.md`）

# AI agent 開發分組實作

> 課程：AI agent 開發 — Tool 與 Skill
> 主題： 旅遊前哨站 /  偵探事務所 /  生活顧問

---

## Agent 功能總覽

> 說明這個 Agent 能做什麼，使用者可以輸入哪些指令

| 使用者輸入   | Agent 行為                             | 負責組員 |
| ------------ | -------------------------------------- | -------- |
| （例：天氣） | 呼叫 weather_tool，查詢即時天氣        |          |
| （例：景點） | 呼叫 search_tool，搜尋熱門景點         |          |
| （例：建議） | 呼叫 advice_tool，取得隨機建議         |          |
| （例：美食） | 呼叫 food_search_tool，搜尋當地必吃美食 | jessiliu0912 |
| （例：出發） | 執行 trip_briefing Skill，產出行前簡報 |          |

---

## 組員與分工

| 姓名         | 負責功能     | 檔案                         | 使用的 API |
| ------------ | ------------ | ---------------------------- | ---------- |
| jessiliu0912 | 當地美食搜尋 | `tools/food_search_tool.py`  | DuckDuckGo |
|              |              | `tools/`                     |            |
|              |              | `tools/`                     |            |
|              | Skill 整合   | `skills/`                    | —          |
|              | Agent 主程式 | `main.py`                    | —          |

---

## 專案架構

範例：

```
├── tools/
│   ├── xxx_tool.py   
│   ├── xxx_tool.py   
│   └── xxx_tool.py  
├── skills/
│   └── xxx_skill.py  
├── main.py        
├── requirements.txt
└── README.md
```

---

## 使用方式

範例：

```bash
# linux
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python main.py

# windows
python -m venv .venv
.\.venv\Scripts\activate
pip install -r requirements.txt
python main.py
```

---

## 執行結果

> 貼上程式執行的實際範例輸出

```
（貼上執行結果，例如下的指令與輸出結果）
```

---

## 各功能說明

### 當地美食搜尋（負責：jessiliu0912）

- **Tool 名稱**：`search_local_food`
- **使用 API**：DuckDuckGo Search (python `ddgs`)
- **輸入**：`destination` (str), `food_type` (str, optional), `max_results` (int, default=5)
- **輸出範例**：
  ```json
  {
    "destination": "台南",
    "food_type": "所有美食",
    "results": [
      {
        "title": "台南必吃美食名單...",
        "snippet": "牛肉湯、碗粿、虱目魚粥...",
        "url": "https://example.com/tainan-food"
      }
    ],
    "message": "成功找到 5 筆關於 台南 的美食資訊。"
  }
  ```

```python
TOOL = {
    "name": "search_local_food",
    "description": "搜尋指定目的地的當地美食與特色小吃。",
    "parameters": {
        "type": "object",
        "properties": {
            "destination": {"type": "string", "description": "目的地名稱"},
            "food_type": {"type": "string", "description": "美食類型"},
            "max_results": {"type": "integer"}
        },
        "required": ["destination"]
    }
}
```

### [功能名稱]（負責：姓名）

- **Tool 名稱**：
- **使用 API**：
- **輸入**：
- **輸出範例**：

### [功能名稱]（負責：姓名）

- **Tool 名稱**：
- **使用 API**：
- **輸入**：
- **輸出範例**：

### Skill：[Skill 名稱]（負責：姓名）

- **組合了哪些 Tool**：
- **執行順序**：

```
Step 1: 呼叫 ___ → 取得 ___
Step 2: 呼叫 ___ → 取得 ___
Step 3: 組合輸出 → 產生 ___
```

---

## 心得

### 遇到最難的問題

> 寫下這次實作遇到最困難的事，以及怎麼解決的

### Tool 和 Skill 的差別

> 用自己的話說說，做完後你怎麼理解兩者的不同

### 如果再加一個功能

> 如果可以多加一個 Tool，你會加什麼？為什麼？
