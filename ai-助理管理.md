# AI 助理管理

## 取得 AI 助理列表

```
GET /api/v1/chatbots/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| page | 否 | integer | A page number within the paginated result set. |
| pageSize | 否 | integer | Number of results to return per page. |

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/chatbots/" \
  -H "Authorization: Api-Key YOUR_API_KEY"\
```

```javascript
const axios = require('axios');

// 準備請求設定
const config = {
  headers: {
    'Authorization': 'Api-Key YOUR_API_KEY'
  }
};

axios.get("https://api.maiagent.com/api/v1/chatbots/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/chatbots/"
headers = {
    "Authorization": "Api-Key YOUR_API_KEY"
}

response = requests.get(url, headers=headers)
try:
    print("回應:", response.json())
except Exception as e:
    print("錯誤:", e)
```

```php
<?php
require 'vendor/autoload.php';

$client = new GuzzleHttpClient();

try {
    $response = $client->get("https://api.maiagent.com/api/v1/chatbots/", [
        'headers' => [
            'Authorization' => 'Api-Key YOUR_API_KEY'
        ]
    ]);
    $data = json_decode($response->getBody(), true);
    print_r($data);
} catch (Exception $e) {
    echo '錯誤: ' . $e->getMessage();
}
?>
```


### 回應內容

```json
{
  "count": 0,
  "next": "example_string",
  "previous": "example_string",
  "results": [
    {
      "id": "550e8400-e29b-41d4-a716-446655440000",
      "name": "客服助理",
      "largeLanguageModel": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "name": "客服助理"
      },
      "rag": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "name": "客服助理"
      },
      "embeddingModel": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "name": "客服助理",
        "isDefault": false
      },
      "rerankerModel": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "name": "客服助理",
        "isDefault": false
      },
      "updatedAt": "example_string",
      "enableChineseConversion": false
    }
  ]
}
```

---

## 建立新 AI 助理

```
POST /api/v1/chatbots/
```

### 請求內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "workflow": "example_string",
  "name": "客服助理",
  "largeLanguageModel": "example_string",
  "rag": "example_string",
  "embeddingModel": "example_string",
  "rerankerModel": "example_string",
  "instructions": "example_string",
  "webhookUrl": "example_string",
  "apiWebChatId": "example_string",
  "updatedAt": "example_string",
  "organization": "example_string",
  "builtInWorkflow": "example_string",
  "replyMode": null,
  "template": "example_string",
  "unanswerableTemplate": "example_string",
  "totalWordsCount": 0,
  "enableChineseConversion": false,
  "outputFormat": null,
  "databaseUrl": "example_string",
  "databaseType": "example_string"
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X POST "https://api.maiagent.com/api/v1/chatbots/" \
  -H "Authorization: Api-Key YOUR_API_KEY"\
```

```javascript
const axios = require('axios');

// 準備請求資料
const data = {}; 

// 準備請求設定
const config = {
  headers: {
    'Authorization': 'Api-Key YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
};

axios.post("https://api.maiagent.com/api/v1/chatbots/", data, config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests
import json

url = "https://api.maiagent.com/api/v1/chatbots/"
headers = {
    "Authorization": "Api-Key YOUR_API_KEY",
    "Content-Type": "application/json"
}
data = {}

response = requests.post(url, json=data, headers=headers)
try:
    print("回應:", response.json())
except Exception as e:
    print("錯誤:", e)
```

```php
<?php
require 'vendor/autoload.php';

$client = new GuzzleHttpClient();

try {
    $response = $client->post("https://api.maiagent.com/api/v1/chatbots/", [
        'headers' => [
            'Authorization' => 'Api-Key YOUR_API_KEY',
            'Content-Type' => 'application/json'
        ],
        'json' => {}
    ]);
    $data = json_decode($response->getBody(), true);
    print_r($data);
} catch (Exception $e) {
    echo '錯誤: ' . $e->getMessage();
}
?>
```


### 回應內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "workflow": "example_string",
  "name": "客服助理",
  "largeLanguageModel": "example_string",
  "rag": "example_string",
  "embeddingModel": "example_string",
  "rerankerModel": "example_string",
  "instructions": "example_string",
  "webhookUrl": "example_string",
  "apiWebChatId": "example_string",
  "updatedAt": "example_string",
  "organization": "example_string",
  "builtInWorkflow": "example_string",
  "replyMode": null,
  "template": "example_string",
  "unanswerableTemplate": "example_string",
  "totalWordsCount": 0,
  "enableChineseConversion": false,
  "outputFormat": null,
  "databaseUrl": "example_string",
  "databaseType": "example_string"
}
```

---

## 取得特定 AI 助理

```
GET /api/v1/chatbots/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| id | 是 | string | A UUID string identifying this chatbot. |

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/" \
  -H "Authorization: Api-Key YOUR_API_KEY"\
```

```javascript
const axios = require('axios');

// 準備請求設定
const config = {
  headers: {
    'Authorization': 'Api-Key YOUR_API_KEY'
  }
};

axios.get("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/"
headers = {
    "Authorization": "Api-Key YOUR_API_KEY"
}

response = requests.get(url, headers=headers)
try:
    print("回應:", response.json())
except Exception as e:
    print("錯誤:", e)
```

```php
<?php
require 'vendor/autoload.php';

$client = new GuzzleHttpClient();

try {
    $response = $client->get("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/", [
        'headers' => [
            'Authorization' => 'Api-Key YOUR_API_KEY'
        ]
    ]);
    $data = json_decode($response->getBody(), true);
    print_r($data);
} catch (Exception $e) {
    echo '錯誤: ' . $e->getMessage();
}
?>
```


### 回應內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "workflow": "example_string",
  "name": "客服助理",
  "largeLanguageModel": "example_string",
  "rag": "example_string",
  "embeddingModel": "example_string",
  "rerankerModel": "example_string",
  "instructions": "example_string",
  "webhookUrl": "example_string",
  "apiWebChatId": "example_string",
  "updatedAt": "example_string",
  "organization": "example_string",
  "builtInWorkflow": "example_string",
  "replyMode": null,
  "template": "example_string",
  "unanswerableTemplate": "example_string",
  "totalWordsCount": 0,
  "enableChineseConversion": false,
  "outputFormat": null,
  "databaseUrl": "example_string",
  "databaseType": "example_string"
}
```

---

## 更新 AI 助理

```
PUT /api/v1/chatbots/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| id | 是 | string | A UUID string identifying this chatbot. |

### 請求內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "workflow": "example_string",
  "name": "客服助理",
  "largeLanguageModel": "example_string",
  "rag": "example_string",
  "embeddingModel": "example_string",
  "rerankerModel": "example_string",
  "instructions": "example_string",
  "webhookUrl": "example_string",
  "apiWebChatId": "example_string",
  "updatedAt": "example_string",
  "organization": "example_string",
  "builtInWorkflow": "example_string",
  "replyMode": null,
  "template": "example_string",
  "unanswerableTemplate": "example_string",
  "totalWordsCount": 0,
  "enableChineseConversion": false,
  "outputFormat": null,
  "databaseUrl": "example_string",
  "databaseType": "example_string"
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X PUT "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/" \
  -H "Authorization: Api-Key YOUR_API_KEY"\
```

```javascript
const axios = require('axios');

// 準備請求資料
const data = {}; 

// 準備請求設定
const config = {
  headers: {
    'Authorization': 'Api-Key YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
};

axios.put("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/", data, config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests
import json

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/"
headers = {
    "Authorization": "Api-Key YOUR_API_KEY",
    "Content-Type": "application/json"
}
data = {}

response = requests.put(url, json=data, headers=headers)
try:
    print("回應:", response.json())
except Exception as e:
    print("錯誤:", e)
```

```php
<?php
require 'vendor/autoload.php';

$client = new GuzzleHttpClient();

try {
    $response = $client->put("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/", [
        'headers' => [
            'Authorization' => 'Api-Key YOUR_API_KEY',
            'Content-Type' => 'application/json'
        ],
        'json' => {}
    ]);
    $data = json_decode($response->getBody(), true);
    print_r($data);
} catch (Exception $e) {
    echo '錯誤: ' . $e->getMessage();
}
?>
```


### 回應內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "workflow": "example_string",
  "name": "客服助理",
  "largeLanguageModel": "example_string",
  "rag": "example_string",
  "embeddingModel": "example_string",
  "rerankerModel": "example_string",
  "instructions": "example_string",
  "webhookUrl": "example_string",
  "apiWebChatId": "example_string",
  "updatedAt": "example_string",
  "organization": "example_string",
  "builtInWorkflow": "example_string",
  "replyMode": null,
  "template": "example_string",
  "unanswerableTemplate": "example_string",
  "totalWordsCount": 0,
  "enableChineseConversion": false,
  "outputFormat": null,
  "databaseUrl": "example_string",
  "databaseType": "example_string"
}
```

---

## 部分更新 AI 助理

```
PATCH /api/v1/chatbots/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| id | 是 | string | A UUID string identifying this chatbot. |

### 請求內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "workflow": "example_string",
  "name": "客服助理",
  "largeLanguageModel": "example_string",
  "rag": "example_string",
  "embeddingModel": "example_string",
  "rerankerModel": "example_string",
  "instructions": "example_string",
  "webhookUrl": "example_string",
  "apiWebChatId": "example_string",
  "updatedAt": "example_string",
  "organization": "example_string",
  "builtInWorkflow": "example_string",
  "replyMode": null,
  "template": "example_string",
  "unanswerableTemplate": "example_string",
  "totalWordsCount": 0,
  "enableChineseConversion": false,
  "outputFormat": null,
  "databaseUrl": "example_string",
  "databaseType": "example_string"
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X PATCH "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/" \
  -H "Authorization: Api-Key YOUR_API_KEY"\
```

```javascript
const axios = require('axios');

// 準備請求資料
const data = {}; 

// 準備請求設定
const config = {
  headers: {
    'Authorization': 'Api-Key YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
};

axios.patch("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/", data, config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests
import json

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/"
headers = {
    "Authorization": "Api-Key YOUR_API_KEY",
    "Content-Type": "application/json"
}
data = {}

response = requests.patch(url, json=data, headers=headers)
try:
    print("回應:", response.json())
except Exception as e:
    print("錯誤:", e)
```

```php
<?php
require 'vendor/autoload.php';

$client = new GuzzleHttpClient();

try {
    $response = $client->patch("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/", [
        'headers' => [
            'Authorization' => 'Api-Key YOUR_API_KEY',
            'Content-Type' => 'application/json'
        ],
        'json' => {}
    ]);
    $data = json_decode($response->getBody(), true);
    print_r($data);
} catch (Exception $e) {
    echo '錯誤: ' . $e->getMessage();
}
?>
```


### 回應內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "workflow": "example_string",
  "name": "客服助理",
  "largeLanguageModel": "example_string",
  "rag": "example_string",
  "embeddingModel": "example_string",
  "rerankerModel": "example_string",
  "instructions": "example_string",
  "webhookUrl": "example_string",
  "apiWebChatId": "example_string",
  "updatedAt": "example_string",
  "organization": "example_string",
  "builtInWorkflow": "example_string",
  "replyMode": null,
  "template": "example_string",
  "unanswerableTemplate": "example_string",
  "totalWordsCount": 0,
  "enableChineseConversion": false,
  "outputFormat": null,
  "databaseUrl": "example_string",
  "databaseType": "example_string"
}
```

---

## 刪除 AI 助理

```
DELETE /api/v1/chatbots/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| id | 是 | string | A UUID string identifying this chatbot. |

### 程式碼範例

```shell
# 呼叫 API
curl -X DELETE "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/" \
  -H "Authorization: Api-Key YOUR_API_KEY"\
```

```javascript
const axios = require('axios');

// 準備請求資料
const data = {}; 

// 準備請求設定
const config = {
  headers: {
    'Authorization': 'Api-Key YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
};

axios.delete("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/", data, config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests
import json

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/"
headers = {
    "Authorization": "Api-Key YOUR_API_KEY",
    "Content-Type": "application/json"
}
data = {}

response = requests.delete(url, json=data, headers=headers)
try:
    print("回應:", response.json())
except Exception as e:
    print("錯誤:", e)
```

```php
<?php
require 'vendor/autoload.php';

$client = new GuzzleHttpClient();

try {
    $response = $client->delete("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/", [
        'headers' => [
            'Authorization' => 'Api-Key YOUR_API_KEY',
            'Content-Type' => 'application/json'
        ],
        'json' => {}
    ]);
    $data = json_decode($response->getBody(), true);
    print_r($data);
} catch (Exception $e) {
    echo '錯誤: ' . $e->getMessage();
}
?>
```


### 狀態碼

| 狀態碼 | 說明 |
| --- | --- |
| 204 | No response body |

---
