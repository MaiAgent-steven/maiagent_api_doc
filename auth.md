# 知識庫

## 取得 FAQ 列表

```
GET /api/v1/chatbots/{chatbotPk}/faqs/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| chatbotPk | 是 | string | A UUID string identifying this Chatbot ID |
| page | 否 | integer | A page number within the paginated result set. |
| pageSize | 否 | integer | Number of results to return per page. |

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/" \
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

axios.get("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/"
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
    $response = $client->get("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/", [
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
      "question": "如何重置密碼？",
      "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。",
      "hitsCount": 42
    }
  ]
}
```

---

## 新增 FAQ

```
POST /api/v1/chatbots/{chatbotPk}/faqs/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| chatbotPk | 是 | string | A UUID string identifying this Chatbot ID |

### 請求內容

```json
{
  "question": "常見問題範例",
  "answer": "這是一個範例答案"
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X POST "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/" \
  -H "Authorization: Api-Key YOUR_API_KEY"\ \
  -H "Content-Type: application/json" \
  -d '{\n  "question": "如何重置密碼？",\n  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。"\n}'
```

```javascript
const axios = require('axios');

// 準備請求資料
const data = {
  "question": "如何重置密碼？",
  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。"
}; 

// 準備請求設定
const config = {
  headers: {
    'Authorization': 'Api-Key YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
};

axios.post("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/", data, config)
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

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/"
headers = {
    "Authorization": "Api-Key YOUR_API_KEY",
    "Content-Type": "application/json"
}
data = {
  "question": "如何重置密碼？",
  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。"
}

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
    $response = $client->post("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/", [
        'headers' => [
            'Authorization' => 'Api-Key YOUR_API_KEY',
            'Content-Type' => 'application/json'
        ],
        'json' => {
  "question": "如何重置密碼？",
  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。"
}
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
  "chatbot": "example_string",
  "question": "如何重置密碼？",
  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。"
}
```

---

## 取得特定 FAQ

```
GET /api/v1/chatbots/{chatbotPk}/faqs/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| chatbotPk | 是 | string | A UUID string identifying this Chatbot ID |
| id | 是 | string | A UUID string identifying this FAQ. |

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/550e8400-e29b-41d4-a716-446655440000/" \
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

axios.get("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/550e8400-e29b-41d4-a716-446655440000/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/550e8400-e29b-41d4-a716-446655440000/"
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
    $response = $client->get("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/550e8400-e29b-41d4-a716-446655440000/", [
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
  "question": "如何重置密碼？",
  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。",
  "hitsCount": 42
}
```

---

## 更新 FAQ

```
PUT /api/v1/chatbots/{chatbotPk}/faqs/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| chatbotPk | 是 | string | A UUID string identifying this Chatbot ID |
| id | 是 | string | A UUID string identifying this FAQ. |

### 請求內容

```json
{
  "question": "常見問題範例",
  "answer": "這是一個範例答案"
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X PUT "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/550e8400-e29b-41d4-a716-446655440000/" \
  -H "Authorization: Api-Key YOUR_API_KEY"\ \
  -H "Content-Type: application/json" \
  -d '{\n  "question": "如何重置密碼？",\n  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。"\n}'
```

```javascript
const axios = require('axios');

// 準備請求資料
const data = {
  "question": "如何重置密碼？",
  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。"
}; 

// 準備請求設定
const config = {
  headers: {
    'Authorization': 'Api-Key YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
};

axios.put("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/550e8400-e29b-41d4-a716-446655440000/", data, config)
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

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/550e8400-e29b-41d4-a716-446655440000/"
headers = {
    "Authorization": "Api-Key YOUR_API_KEY",
    "Content-Type": "application/json"
}
data = {
  "question": "如何重置密碼？",
  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。"
}

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
    $response = $client->put("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/550e8400-e29b-41d4-a716-446655440000/", [
        'headers' => [
            'Authorization' => 'Api-Key YOUR_API_KEY',
            'Content-Type' => 'application/json'
        ],
        'json' => {
  "question": "如何重置密碼？",
  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。"
}
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
  "question": "如何重置密碼？",
  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。",
  "hitsCount": 42
}
```

---

## 刪除 FAQ

```
DELETE /api/v1/chatbots/{chatbotPk}/faqs/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| chatbotPk | 是 | string | A UUID string identifying this Chatbot ID |
| id | 是 | string | A UUID string identifying this FAQ. |

### 程式碼範例

```shell
# 呼叫 API
curl -X DELETE "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/550e8400-e29b-41d4-a716-446655440000/" \
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

axios.delete("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/550e8400-e29b-41d4-a716-446655440000/", data, config)
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

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/550e8400-e29b-41d4-a716-446655440000/"
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
    $response = $client->delete("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/550e8400-e29b-41d4-a716-446655440000/", [
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

## 批次刪除 FAQ

```
POST /api/v1/chatbots/{chatbotPk}/faqs/batch-delete/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| chatbotPk | 是 | string | A UUID string identifying this Chatbot ID |

### 請求內容

```json
{
  "ids": [
    "file_id_1",
    "file_id_2",
    "file_id_3"
  ]
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X POST "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/batch-delete/" \
  -H "Authorization: Api-Key YOUR_API_KEY"\ \
  -H "Content-Type: application/json" \
  -d '{\n  "question": "如何重置密碼？",\n  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。"\n}'
```

```javascript
const axios = require('axios');

// 準備請求資料
const data = {
  "question": "如何重置密碼？",
  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。"
}; 

// 準備請求設定
const config = {
  headers: {
    'Authorization': 'Api-Key YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
};

axios.post("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/batch-delete/", data, config)
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

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/batch-delete/"
headers = {
    "Authorization": "Api-Key YOUR_API_KEY",
    "Content-Type": "application/json"
}
data = {
  "question": "如何重置密碼？",
  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。"
}

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
    $response = $client->post("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/faqs/batch-delete/", [
        'headers' => [
            'Authorization' => 'Api-Key YOUR_API_KEY',
            'Content-Type' => 'application/json'
        ],
        'json' => {
  "question": "如何重置密碼？",
  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。"
}
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
  "question": "如何重置密碼？",
  "answer": "您可以點擊登入頁面的「忘記密碼」連結來重置密碼。",
  "hitsCount": 42
}
```

---

## 取得知識庫文件列表

```
GET /api/v1/chatbots/{chatbotPk}/files/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| chatbotPk | 是 | string | A UUID string identifying this Chatbot ID |
| page | 否 | integer | A page number within the paginated result set. |
| pageSize | 否 | integer | Number of results to return per page. |

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/" \
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

axios.get("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/"
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
    $response = $client->get("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/", [
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
      "filename": "example.pdf",
      "file": "example.pdf",
      "fileType": "example_string",
      "size": 0,
      "status": null,
      "chatbotFileContent": "example_string",
      "parser": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "name": "客服助理",
        "provider": "example_string",
        "priority": 0
      },
      "createdAt": "2024-02-18T13:45:30.000Z"
    }
  ]
}
```

---

## 上傳新文件到知識庫

```
POST /api/v1/chatbots/{chatbotPk}/files/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| chatbotPk | 是 | string | A UUID string identifying this Chatbot ID |

### 請求內容

```json
{
  "files": [
    {
      "file": "media/chatbots/chatbot-file/example.pdf",
      "filename": "example.pdf",
      "parser": ""
    }
  ]
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X POST "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/" \
  -H "Authorization: Api-Key YOUR_API_KEY"\ \
  -H "Content-Type: application/json" \
  -d '{\n  "filename": "example.pdf",\n  "file": "https://example.com/path/to/file.pdf"\n}'
```

```javascript
const axios = require('axios');

// 準備請求資料
const data = {
  "filename": "example.pdf",
  "file": "https://example.com/path/to/file.pdf"
}; 

// 準備請求設定
const config = {
  headers: {
    'Authorization': 'Api-Key YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
};

axios.post("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/", data, config)
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

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/"
headers = {
    "Authorization": "Api-Key YOUR_API_KEY",
    "Content-Type": "application/json"
}
data = {
  "filename": "example.pdf",
  "file": "https://example.com/path/to/file.pdf"
}

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
    $response = $client->post("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/", [
        'headers' => [
            'Authorization' => 'Api-Key YOUR_API_KEY',
            'Content-Type' => 'application/json'
        ],
        'json' => {
  "filename": "example.pdf",
  "file": "https://example.com/path/to/file.pdf"
}
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
  "files": [
    {
      "id": "550e8400-e29b-41d4-a716-446655440000",
      "filename": "example.pdf",
      "file": "example.pdf",
      "fileType": "example_string",
      "size": 0,
      "status": null,
      "chatbotFileContent": "example_string",
      "parser": "example_string",
      "createdAt": "2024-02-18T13:45:30.000Z"
    }
  ]
}
```

---

## 取得知識庫內特定文件

```
GET /api/v1/chatbots/{chatbotPk}/files/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| chatbotPk | 是 | string | A UUID string identifying this Chatbot ID |
| id | 是 | string | A UUID string identifying this Chatbot 檔案. |

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/550e8400-e29b-41d4-a716-446655440000/" \
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

axios.get("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/550e8400-e29b-41d4-a716-446655440000/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/550e8400-e29b-41d4-a716-446655440000/"
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
    $response = $client->get("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/550e8400-e29b-41d4-a716-446655440000/", [
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
  "filename": "example.pdf",
  "file": "example.pdf",
  "fileType": "example_string",
  "size": 0,
  "status": null,
  "chatbotFileContent": "example_string",
  "parser": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "name": "客服助理",
    "provider": "example_string",
    "priority": 0
  },
  "createdAt": "2024-02-18T13:45:30.000Z"
}
```

---

## 更新知識庫內特定文件

```
PUT /api/v1/chatbots/{chatbotPk}/files/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| chatbotPk | 是 | string | A UUID string identifying this Chatbot ID |
| id | 是 | string | A UUID string identifying this Chatbot 檔案. |

### 請求內容

```json
{
  "file": "media/chatbots/chatbot-file/example.pdf",
  "filename": "example.pdf",
  "parser": ""
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X PUT "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/550e8400-e29b-41d4-a716-446655440000/" \
  -H "Authorization: Api-Key YOUR_API_KEY"\ \
  -H "Content-Type: application/json" \
  -d '{\n  "filename": "example.pdf",\n  "file": "https://example.com/path/to/file.pdf"\n}'
```

```javascript
const axios = require('axios');

// 準備請求資料
const data = {
  "filename": "example.pdf",
  "file": "https://example.com/path/to/file.pdf"
}; 

// 準備請求設定
const config = {
  headers: {
    'Authorization': 'Api-Key YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
};

axios.put("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/550e8400-e29b-41d4-a716-446655440000/", data, config)
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

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/550e8400-e29b-41d4-a716-446655440000/"
headers = {
    "Authorization": "Api-Key YOUR_API_KEY",
    "Content-Type": "application/json"
}
data = {
  "filename": "example.pdf",
  "file": "https://example.com/path/to/file.pdf"
}

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
    $response = $client->put("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/550e8400-e29b-41d4-a716-446655440000/", [
        'headers' => [
            'Authorization' => 'Api-Key YOUR_API_KEY',
            'Content-Type' => 'application/json'
        ],
        'json' => {
  "filename": "example.pdf",
  "file": "https://example.com/path/to/file.pdf"
}
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
  "filename": "example.pdf",
  "file": "example.pdf",
  "fileType": "example_string",
  "size": 0,
  "status": null,
  "chatbotFileContent": "example_string",
  "parser": "example_string",
  "createdAt": "2024-02-18T13:45:30.000Z"
}
```

---

## 刪除知識庫內特定文件

```
DELETE /api/v1/chatbots/{chatbotPk}/files/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| chatbotPk | 是 | string | A UUID string identifying this Chatbot ID |
| id | 是 | string | A UUID string identifying this Chatbot 檔案. |

### 程式碼範例

```shell
# 呼叫 API
curl -X DELETE "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/550e8400-e29b-41d4-a716-446655440000/" \
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

axios.delete("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/550e8400-e29b-41d4-a716-446655440000/", data, config)
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

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/550e8400-e29b-41d4-a716-446655440000/"
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
    $response = $client->delete("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/550e8400-e29b-41d4-a716-446655440000/", [
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

## 批次刪除知識庫文件

```
POST /api/v1/chatbots/{chatbotPk}/files/batch-delete/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| chatbotPk | 是 | string | A UUID string identifying this Chatbot ID |

### 請求內容

```json
{
  "ids": [
    "file_id_1",
    "file_id_2",
    "file_id_3"
  ]
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X POST "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/batch-delete/" \
  -H "Authorization: Api-Key YOUR_API_KEY"\ \
  -H "Content-Type: application/json" \
  -d '{\n  "filename": "example.pdf",\n  "file": "https://example.com/path/to/file.pdf"\n}'
```

```javascript
const axios = require('axios');

// 準備請求資料
const data = {
  "filename": "example.pdf",
  "file": "https://example.com/path/to/file.pdf"
}; 

// 準備請求設定
const config = {
  headers: {
    'Authorization': 'Api-Key YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
};

axios.post("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/batch-delete/", data, config)
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

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/batch-delete/"
headers = {
    "Authorization": "Api-Key YOUR_API_KEY",
    "Content-Type": "application/json"
}
data = {
  "filename": "example.pdf",
  "file": "https://example.com/path/to/file.pdf"
}

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
    $response = $client->post("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/files/batch-delete/", [
        'headers' => [
            'Authorization' => 'Api-Key YOUR_API_KEY',
            'Content-Type' => 'application/json'
        ],
        'json' => {
  "filename": "example.pdf",
  "file": "https://example.com/path/to/file.pdf"
}
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
  "filename": "example.pdf",
  "file": "example.pdf",
  "fileType": "example_string",
  "size": 0,
  "status": null,
  "chatbotFileContent": "example_string",
  "parser": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "name": "客服助理",
    "provider": "example_string",
    "priority": 0
  },
  "createdAt": "2024-02-18T13:45:30.000Z"
}
```

---

## 搜尋測試

```
POST /api/v1/chatbots/{id}/search/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| id | 是 | string | A UUID string identifying this chatbot. |

### 請求內容

```json
{
  "query": "搜尋關鍵字",
  "topK": 10
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X POST "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/search/" \
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

axios.post("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/search/", data, config)
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

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/search/"
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
    $response = $client->post("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/search/", [
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
