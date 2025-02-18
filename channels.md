# 附件與檔案管理

## 取得附件列表

```
GET /api/attachments/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| page | 否 | integer | A page number within the paginated result set. |
| pageSize | 否 | integer | Number of results to return per page. |

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/attachments/" \
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

axios.get("https://api.maiagent.com/api/attachments/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/attachments/"
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
    $response = $client->get("https://api.maiagent.com/api/attachments/", [
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
      "type": null,
      "filename": "example.pdf",
      "file": "example.pdf"
    }
  ]
}
```

---

## 建立新附件

```
POST /api/attachments/
```

### 請求內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "type": null,
  "filename": "example.pdf",
  "file": "example.pdf"
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X POST "https://api.maiagent.com/api/attachments/" \
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

axios.post("https://api.maiagent.com/api/attachments/", data, config)
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

url = "https://api.maiagent.com/api/attachments/"
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
    $response = $client->post("https://api.maiagent.com/api/attachments/", [
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
  "type": null,
  "filename": "example.pdf",
  "file": "example.pdf"
}
```

---

## 取得指定附件內容

```
GET /api/attachments/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| id | 是 | string | A UUID string identifying this attachment. |

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/" \
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

axios.get("https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/"
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
    $response = $client->get("https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/", [
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
  "type": null,
  "filename": "example.pdf",
  "file": "example.pdf"
}
```

---

## 更新附件資訊

```
PUT /api/attachments/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| id | 是 | string | A UUID string identifying this attachment. |

### 請求內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "type": null,
  "filename": "example.pdf",
  "file": "example.pdf"
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X PUT "https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/" \
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

axios.put("https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/", data, config)
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

url = "https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/"
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
    $response = $client->put("https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/", [
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
  "type": null,
  "filename": "example.pdf",
  "file": "example.pdf"
}
```

---

## 部分更新附件資料

```
PATCH /api/attachments/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| id | 是 | string | A UUID string identifying this attachment. |

### 請求內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "type": null,
  "filename": "example.pdf",
  "file": "example.pdf"
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X PATCH "https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/" \
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

axios.patch("https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/", data, config)
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

url = "https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/"
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
    $response = $client->patch("https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/", [
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
  "type": null,
  "filename": "example.pdf",
  "file": "example.pdf"
}
```

---

## 刪除附件

```
DELETE /api/attachments/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| id | 是 | string | A UUID string identifying this attachment. |

### 程式碼範例

```shell
# 呼叫 API
curl -X DELETE "https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/" \
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

axios.delete("https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/", data, config)
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

url = "https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/"
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
    $response = $client->delete("https://api.maiagent.com/api/attachments/550e8400-e29b-41d4-a716-446655440000/", [
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

## 取得檔案上傳用的預簽署 URL

```
POST /api/v1/upload-presigned-url/
```

### 請求內容

```json
{
  "modelName": "example_string",
  "fieldName": "example_string",
  "filename": "example.pdf",
  "fileSize": 0
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X POST "https://api.maiagent.com/api/v1/upload-presigned-url/" \
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

axios.post("https://api.maiagent.com/api/v1/upload-presigned-url/", data, config)
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

url = "https://api.maiagent.com/api/v1/upload-presigned-url/"
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
    $response = $client->post("https://api.maiagent.com/api/v1/upload-presigned-url/", [
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
  "modelName": "example_string",
  "fieldName": "example_string",
  "filename": "example.pdf",
  "fileSize": 0
}
```

---
