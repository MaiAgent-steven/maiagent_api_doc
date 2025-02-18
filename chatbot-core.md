# 組織與成員管理

## 取得組織列表

```
GET /api/v1/organizations/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| page | 否 | integer | A page number within the paginated result set. |
| pageSize | 否 | integer | Number of results to return per page. |

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/organizations/" \
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

axios.get("https://api.maiagent.com/api/v1/organizations/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/organizations/"
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
    $response = $client->get("https://api.maiagent.com/api/v1/organizations/", [
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
      "owner": null,
      "createdAt": "2024-02-18T13:45:30.000Z"
    }
  ]
}
```

---

## 建立新的組織

```
POST /api/v1/organizations/
```

### 請求內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "name": "客服助理",
  "owner": null,
  "createdAt": "2024-02-18T13:45:30.000Z",
  "usageStatistics": "example_string",
  "organizationPlan": "example_string"
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X POST "https://api.maiagent.com/api/v1/organizations/" \
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

axios.post("https://api.maiagent.com/api/v1/organizations/", data, config)
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

url = "https://api.maiagent.com/api/v1/organizations/"
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
    $response = $client->post("https://api.maiagent.com/api/v1/organizations/", [
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
  "name": "客服助理",
  "owner": null,
  "createdAt": "2024-02-18T13:45:30.000Z",
  "usageStatistics": "example_string",
  "organizationPlan": "example_string"
}
```

---

## /api/v1/organizations/{organizationPk}/members/

```
GET /api/v1/organizations/{organizationPk}/members/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| organizationPk | 是 | string |  |
| page | 否 | integer | A page number within the paginated result set. |
| pageSize | 否 | integer | Number of results to return per page. |

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/" \
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

axios.get("https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/"
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
    $response = $client->get("https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/", [
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
      "email": "example_string",
      "organization": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "name": "客服助理",
        "owner": null,
        "createdAt": "2024-02-18T13:45:30.000Z",
        "usageStatistics": "example_string",
        "organizationPlan": "example_string"
      },
      "isOwner": "example_string",
      "permissions": "example_string",
      "createdAt": "2024-02-18T13:45:30.000Z"
    }
  ]
}
```

---

## /api/v1/organizations/{organizationPk}/members/

```
POST /api/v1/organizations/{organizationPk}/members/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| organizationPk | 是 | string |  |

### 請求內容

```json
{
  "email": "example_string",
  "organization": "example_string",
  "isOwner": "example_string"
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X POST "https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/" \
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

axios.post("https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/", data, config)
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

url = "https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/"
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
    $response = $client->post("https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/", [
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
  "email": "example_string",
  "organization": "example_string",
  "isOwner": "example_string"
}
```

---

## /api/v1/organizations/{organizationPk}/members/{id}/

```
GET /api/v1/organizations/{organizationPk}/members/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| id | 是 | string | A UUID string identifying this 成員. |
| organizationPk | 是 | string |  |

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/550e8400-e29b-41d4-a716-446655440000/" \
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

axios.get("https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/550e8400-e29b-41d4-a716-446655440000/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/550e8400-e29b-41d4-a716-446655440000/"
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
    $response = $client->get("https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/550e8400-e29b-41d4-a716-446655440000/", [
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
  "name": "客服助理",
  "email": "example_string",
  "organization": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "name": "客服助理",
    "owner": null,
    "createdAt": "2024-02-18T13:45:30.000Z",
    "usageStatistics": "example_string",
    "organizationPlan": "example_string"
  },
  "isOwner": "example_string",
  "permissions": "example_string",
  "createdAt": "2024-02-18T13:45:30.000Z"
}
```

---

## /api/v1/organizations/{organizationPk}/members/{id}/

```
DELETE /api/v1/organizations/{organizationPk}/members/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| id | 是 | string | A UUID string identifying this 成員. |
| organizationPk | 是 | string |  |

### 程式碼範例

```shell
# 呼叫 API
curl -X DELETE "https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/550e8400-e29b-41d4-a716-446655440000/" \
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

axios.delete("https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/550e8400-e29b-41d4-a716-446655440000/", data, config)
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

url = "https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/550e8400-e29b-41d4-a716-446655440000/"
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
    $response = $client->delete("https://api.maiagent.com/api/v1/organizations/{organizationPk}/members/550e8400-e29b-41d4-a716-446655440000/", [
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

## 取得特定組織的詳細資訊

```
GET /api/v1/organizations/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| id | 是 | string | A UUID string identifying this 組織. |

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/organizations/550e8400-e29b-41d4-a716-446655440000/" \
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

axios.get("https://api.maiagent.com/api/v1/organizations/550e8400-e29b-41d4-a716-446655440000/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/organizations/550e8400-e29b-41d4-a716-446655440000/"
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
    $response = $client->get("https://api.maiagent.com/api/v1/organizations/550e8400-e29b-41d4-a716-446655440000/", [
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
  "name": "客服助理",
  "owner": null,
  "createdAt": "2024-02-18T13:45:30.000Z",
  "usageStatistics": "example_string",
  "organizationPlan": "example_string"
}
```

---

## 更新組織資訊

```
PUT /api/v1/organizations/{id}/
```

### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| id | 是 | string | A UUID string identifying this 組織. |

### 請求內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "name": "客服助理",
  "owner": null,
  "createdAt": "2024-02-18T13:45:30.000Z",
  "usageStatistics": "example_string",
  "organizationPlan": "example_string"
}
```

### 程式碼範例

```shell
# 呼叫 API
curl -X PUT "https://api.maiagent.com/api/v1/organizations/550e8400-e29b-41d4-a716-446655440000/" \
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

axios.put("https://api.maiagent.com/api/v1/organizations/550e8400-e29b-41d4-a716-446655440000/", data, config)
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

url = "https://api.maiagent.com/api/v1/organizations/550e8400-e29b-41d4-a716-446655440000/"
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
    $response = $client->put("https://api.maiagent.com/api/v1/organizations/550e8400-e29b-41d4-a716-446655440000/", [
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
  "name": "客服助理",
  "owner": null,
  "createdAt": "2024-02-18T13:45:30.000Z",
  "usageStatistics": "example_string",
  "organizationPlan": "example_string"
}
```

---
