# 對話與訊息

## 產生對話回應

```
POST /api/v1/chatbots/{chatbotId}/completions/
```

### 程式碼範例

```shell
# 呼叫 API
curl -X POST "https://api.maiagent.com/api/v1/chatbots/{chatbotId}/completions/" \
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

axios.post("https://api.maiagent.com/api/v1/chatbots/{chatbotId}/completions/", data, config)
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

url = "https://api.maiagent.com/api/v1/chatbots/{chatbotId}/completions/"
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
    $response = $client->post("https://api.maiagent.com/api/v1/chatbots/{chatbotId}/completions/", [
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


### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| chatbotId | 是 | string |  |

### 狀態碼

| 狀態碼 | 說明 |
| --- | --- |
| 200 | No response body |

---

## 取得對話記錄

```
GET /api/v1/chatbots/{chatbotPk}/records/
```

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/records/" \
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

axios.get("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/records/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/records/"
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
    $response = $client->get("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/records/", [
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


### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| chatbotPk | 是 | string | A UUID string identifying this Chatbot ID |
| page | 否 | integer | A page number within the paginated result set. |
| pageSize | 否 | integer | Number of results to return per page. |

### 回應內容

```json
{
  "count": 0,
  "next": "example_string",
  "previous": "example_string",
  "results": [
    {
      "id": "550e8400-e29b-41d4-a716-446655440000",
      "inputMessage": "example_string",
      "condenseMessage": "example_string",
      "outputMessage": "example_string",
      "context": "example_string",
      "faithfulnessScore": 0,
      "displayFaithfulnessScore": "example_string",
      "answerRelevancyScore": 0,
      "displayAnswerRelevancyScore": "example_string",
      "contextPrecisionScore": 0,
      "displayContextPrecisionScore": "example_string",
      "answerCorrectnessScore": 0,
      "displayAnswerCorrectnessScore": "example_string",
      "answerSimilarityScore": 0,
      "displayAnswerSimilarityScore": "example_string",
      "contextRecallScore": 0,
      "displayContextRecallScore": "example_string",
      "replyTime": "example_string",
      "createdAt": "2024-02-18T13:45:30.000Z",
      "error": "example_string"
    }
  ]
}
```

---

## 匯出對話記錄

```
GET /api/v1/chatbots/{chatbotPk}/records/export-excel/
```

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/records/export-excel/" \
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

axios.get("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/records/export-excel/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/records/export-excel/"
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
    $response = $client->get("https://api.maiagent.com/api/v1/chatbots/550e8400-e29b-41d4-a716-446655440000/records/export-excel/", [
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


### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| chatbotPk | 是 | string | A UUID string identifying this Chatbot ID |

### 回應內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "inputMessage": "example_string",
  "condenseMessage": "example_string",
  "outputMessage": "example_string",
  "context": "example_string",
  "faithfulnessScore": 0,
  "displayFaithfulnessScore": "example_string",
  "answerRelevancyScore": 0,
  "displayAnswerRelevancyScore": "example_string",
  "contextPrecisionScore": 0,
  "displayContextPrecisionScore": "example_string",
  "answerCorrectnessScore": 0,
  "displayAnswerCorrectnessScore": "example_string",
  "answerSimilarityScore": 0,
  "displayAnswerSimilarityScore": "example_string",
  "contextRecallScore": 0,
  "displayContextRecallScore": "example_string",
  "replyTime": "example_string",
  "createdAt": "2024-02-18T13:45:30.000Z",
  "error": "example_string"
}
```

---

## 取得對話列表

```
GET /api/v1/conversations/
```

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/conversations/" \
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

axios.get("https://api.maiagent.com/api/v1/conversations/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/conversations/"
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
    $response = $client->get("https://api.maiagent.com/api/v1/conversations/", [
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


### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| cursor | 否 | string | The pagination cursor value. |
| inbox | 否 | string |  |
| pageSize | 否 | integer | Number of results to return per page. |

### 回應內容

```json
{
  "next": "example_string",
  "previous": "example_string",
  "results": [
    {
      "id": "550e8400-e29b-41d4-a716-446655440000",
      "contact": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "name": "客服助理",
        "avatar": "example_string",
        "createdAt": "2024-02-18T13:45:30.000Z"
      },
      "inbox": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "name": "客服助理",
        "channelType": null,
        "unreadConversationsCount": 0
      },
      "title": "example_string",
      "lastMessage": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "conversation": "example_string",
        "sender": {
          "id": "550e8400-e29b-41d4-a716-446655440000",
          "name": "客服助理",
          "avatar": "example_string"
        },
        "type": "example_string",
        "content": "example_string",
        "feedback": null,
        "createdAt": "2024-02-18T13:45:30.000Z",
        "attachments": [
          {
            "id": "550e8400-e29b-41d4-a716-446655440000",
            "type": null,
            "filename": "example.pdf",
            "file": "example.pdf"
          }
        ],
        "citations": [
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
        ],
        "citationNodes": [
          {
            "chatbotTextNode": {
              "id": "550e8400-e29b-41d4-a716-446655440000",
              "charactersCount": 0,
              "hitsCount": 42,
              "text": "example_string",
              "updatedAt": "example_string",
              "filename": "example.pdf"
            },
            "score": 0,
            "displayScore": "example_string"
          }
        ]
      },
      "lastMessageCreatedAt": "example_string",
      "unreadMessagesCount": 0,
      "autoReplyEnabled": false,
      "isAutoReplyNow": "example_string",
      "lastReadAt": "example_string",
      "createdAt": "2024-02-18T13:45:30.000Z",
      "isGroupChat": "example_string",
      "enableGroupMention": "example_string"
    }
  ]
}
```

---

## 建立對話

```
POST /api/v1/conversations/
```

### 程式碼範例

```shell
# 呼叫 API
curl -X POST "https://api.maiagent.com/api/v1/conversations/" \
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

axios.post("https://api.maiagent.com/api/v1/conversations/", data, config)
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

url = "https://api.maiagent.com/api/v1/conversations/"
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
    $response = $client->post("https://api.maiagent.com/api/v1/conversations/", [
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


### 請求內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "contact": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "name": "客服助理",
    "avatar": "example_string",
    "createdAt": "2024-02-18T13:45:30.000Z"
  },
  "inbox": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "name": "客服助理",
    "channelType": null,
    "unreadConversationsCount": 0
  },
  "title": "example_string",
  "lastMessage": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "conversation": "example_string",
    "sender": {
      "id": "550e8400-e29b-41d4-a716-446655440000",
      "name": "客服助理",
      "avatar": "example_string"
    },
    "type": "example_string",
    "content": "example_string",
    "feedback": null,
    "createdAt": "2024-02-18T13:45:30.000Z",
    "attachments": [
      {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "type": null,
        "filename": "example.pdf",
        "file": "example.pdf"
      }
    ],
    "citations": [
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
    ],
    "citationNodes": [
      {
        "chatbotTextNode": {
          "id": "550e8400-e29b-41d4-a716-446655440000",
          "charactersCount": 0,
          "hitsCount": 42,
          "text": "example_string",
          "updatedAt": "example_string",
          "filename": "example.pdf"
        },
        "score": 0,
        "displayScore": "example_string"
      }
    ]
  },
  "lastMessageCreatedAt": "example_string",
  "unreadMessagesCount": 0,
  "autoReplyEnabled": false,
  "isAutoReplyNow": "example_string",
  "lastReadAt": "example_string",
  "createdAt": "2024-02-18T13:45:30.000Z",
  "isGroupChat": "example_string",
  "enableGroupMention": "example_string"
}
```

### 回應內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "contact": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "name": "客服助理",
    "avatar": "example_string",
    "createdAt": "2024-02-18T13:45:30.000Z"
  },
  "inbox": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "name": "客服助理",
    "channelType": null,
    "unreadConversationsCount": 0
  },
  "title": "example_string",
  "lastMessage": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "conversation": "example_string",
    "sender": {
      "id": "550e8400-e29b-41d4-a716-446655440000",
      "name": "客服助理",
      "avatar": "example_string"
    },
    "type": "example_string",
    "content": "example_string",
    "feedback": null,
    "createdAt": "2024-02-18T13:45:30.000Z",
    "attachments": [
      {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "type": null,
        "filename": "example.pdf",
        "file": "example.pdf"
      }
    ],
    "citations": [
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
    ],
    "citationNodes": [
      {
        "chatbotTextNode": {
          "id": "550e8400-e29b-41d4-a716-446655440000",
          "charactersCount": 0,
          "hitsCount": 42,
          "text": "example_string",
          "updatedAt": "example_string",
          "filename": "example.pdf"
        },
        "score": 0,
        "displayScore": "example_string"
      }
    ]
  },
  "lastMessageCreatedAt": "example_string",
  "unreadMessagesCount": 0,
  "autoReplyEnabled": false,
  "isAutoReplyNow": "example_string",
  "lastReadAt": "example_string",
  "createdAt": "2024-02-18T13:45:30.000Z",
  "isGroupChat": "example_string",
  "enableGroupMention": "example_string"
}
```

---

## 取得特定對話

```
GET /api/v1/conversations/{id}/
```

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/conversations/550e8400-e29b-41d4-a716-446655440000/" \
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

axios.get("https://api.maiagent.com/api/v1/conversations/550e8400-e29b-41d4-a716-446655440000/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/conversations/550e8400-e29b-41d4-a716-446655440000/"
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
    $response = $client->get("https://api.maiagent.com/api/v1/conversations/550e8400-e29b-41d4-a716-446655440000/", [
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


### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| id | 是 | string | A UUID string identifying this 對話. |

### 回應內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "contact": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "name": "客服助理",
    "avatar": "example_string",
    "createdAt": "2024-02-18T13:45:30.000Z"
  },
  "inbox": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "name": "客服助理",
    "channelType": null,
    "unreadConversationsCount": 0
  },
  "title": "example_string",
  "lastMessage": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "conversation": "example_string",
    "sender": {
      "id": "550e8400-e29b-41d4-a716-446655440000",
      "name": "客服助理",
      "avatar": "example_string"
    },
    "type": "example_string",
    "content": "example_string",
    "feedback": null,
    "createdAt": "2024-02-18T13:45:30.000Z",
    "attachments": [
      {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "type": null,
        "filename": "example.pdf",
        "file": "example.pdf"
      }
    ],
    "citations": [
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
    ],
    "citationNodes": [
      {
        "chatbotTextNode": {
          "id": "550e8400-e29b-41d4-a716-446655440000",
          "charactersCount": 0,
          "hitsCount": 42,
          "text": "example_string",
          "updatedAt": "example_string",
          "filename": "example.pdf"
        },
        "score": 0,
        "displayScore": "example_string"
      }
    ]
  },
  "lastMessageCreatedAt": "example_string",
  "unreadMessagesCount": 0,
  "autoReplyEnabled": false,
  "isAutoReplyNow": "example_string",
  "lastReadAt": "example_string",
  "createdAt": "2024-02-18T13:45:30.000Z",
  "isGroupChat": "example_string",
  "enableGroupMention": "example_string"
}
```

---

## 取得訊息列表

```
GET /api/v1/messages/
```

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/messages/" \
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

axios.get("https://api.maiagent.com/api/v1/messages/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/messages/"
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
    $response = $client->get("https://api.maiagent.com/api/v1/messages/", [
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


### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| conversation | 否 | string |  |
| cursor | 否 | string | The pagination cursor value. |
| pageSize | 否 | integer | Number of results to return per page. |

### 回應內容

```json
{
  "count": 0,
  "next": "example_string",
  "previous": "example_string",
  "results": [
    {
      "id": "550e8400-e29b-41d4-a716-446655440000",
      "conversation": "example_string",
      "sender": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "name": "客服助理",
        "avatar": "example_string"
      },
      "type": "example_string",
      "content": "example_string",
      "feedback": null,
      "createdAt": "2024-02-18T13:45:30.000Z",
      "attachments": [
        {
          "id": "550e8400-e29b-41d4-a716-446655440000",
          "type": null,
          "filename": "example.pdf",
          "file": "example.pdf"
        }
      ],
      "citations": [
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
      ],
      "citationNodes": [
        {
          "chatbotTextNode": {
            "id": "550e8400-e29b-41d4-a716-446655440000",
            "charactersCount": 0,
            "hitsCount": 42,
            "text": "example_string",
            "updatedAt": "example_string",
            "filename": "example.pdf"
          },
          "score": 0,
          "displayScore": "example_string"
        }
      ]
    }
  ]
}
```

---

## 發送訊息

```
POST /api/v1/messages/
```

### 程式碼範例

```shell
# 呼叫 API
curl -X POST "https://api.maiagent.com/api/v1/messages/" \
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

axios.post("https://api.maiagent.com/api/v1/messages/", data, config)
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

url = "https://api.maiagent.com/api/v1/messages/"
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
    $response = $client->post("https://api.maiagent.com/api/v1/messages/", [
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


### 請求內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "conversation": "example_string",
  "sender": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "name": "客服助理",
    "avatar": "example_string"
  },
  "type": "example_string",
  "content": "example_string",
  "feedback": null,
  "createdAt": "2024-02-18T13:45:30.000Z",
  "attachments": [
    {
      "id": "550e8400-e29b-41d4-a716-446655440000",
      "type": null,
      "filename": "example.pdf",
      "file": "example.pdf"
    }
  ],
  "citations": [
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
  ],
  "citationNodes": [
    {
      "chatbotTextNode": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "charactersCount": 0,
        "hitsCount": 42,
        "text": "example_string",
        "updatedAt": "example_string",
        "filename": "example.pdf"
      },
      "score": 0,
      "displayScore": "example_string"
    }
  ]
}
```

### 回應內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "conversation": "example_string",
  "sender": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "name": "客服助理",
    "avatar": "example_string"
  },
  "type": "example_string",
  "content": "example_string",
  "feedback": null,
  "createdAt": "2024-02-18T13:45:30.000Z",
  "attachments": [
    {
      "id": "550e8400-e29b-41d4-a716-446655440000",
      "type": null,
      "filename": "example.pdf",
      "file": "example.pdf"
    }
  ],
  "citations": [
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
  ],
  "citationNodes": [
    {
      "chatbotTextNode": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "charactersCount": 0,
        "hitsCount": 42,
        "text": "example_string",
        "updatedAt": "example_string",
        "filename": "example.pdf"
      },
      "score": 0,
      "displayScore": "example_string"
    }
  ]
}
```

---

## 取得特定訊息

```
GET /api/v1/messages/{id}/
```

### 程式碼範例

```shell
# 呼叫 API
curl -X GET "https://api.maiagent.com/api/v1/messages/550e8400-e29b-41d4-a716-446655440000/" \
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

axios.get("https://api.maiagent.com/api/v1/messages/550e8400-e29b-41d4-a716-446655440000/", config)
  .then(response => {
    console.log('回應:', response.data);
  })
  .catch(error => {
    console.error('錯誤:', error.response?.data || error.message);
  });
```

```python
import requests

url = "https://api.maiagent.com/api/v1/messages/550e8400-e29b-41d4-a716-446655440000/"
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
    $response = $client->get("https://api.maiagent.com/api/v1/messages/550e8400-e29b-41d4-a716-446655440000/", [
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


### 參數

| 參數名稱 | 必填 | 類型 | 說明 |
| --- | --- | --- | --- |
| id | 是 | string | A UUID string identifying this 訊息. |

### 回應內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "conversation": "example_string",
  "sender": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "name": "客服助理",
    "avatar": "example_string"
  },
  "type": "example_string",
  "content": "example_string",
  "feedback": null,
  "createdAt": "2024-02-18T13:45:30.000Z",
  "attachments": [
    {
      "id": "550e8400-e29b-41d4-a716-446655440000",
      "type": null,
      "filename": "example.pdf",
      "file": "example.pdf"
    }
  ],
  "citations": [
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
  ],
  "citationNodes": [
    {
      "chatbotTextNode": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "charactersCount": 0,
        "hitsCount": 42,
        "text": "example_string",
        "updatedAt": "example_string",
        "filename": "example.pdf"
      },
      "score": 0,
      "displayScore": "example_string"
    }
  ]
}
```

---

## 發送外發訊息

```
POST /api/v1/messages/outgoing/
```

### 程式碼範例

```shell
# 呼叫 API
curl -X POST "https://api.maiagent.com/api/v1/messages/outgoing/" \
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

axios.post("https://api.maiagent.com/api/v1/messages/outgoing/", data, config)
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

url = "https://api.maiagent.com/api/v1/messages/outgoing/"
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
    $response = $client->post("https://api.maiagent.com/api/v1/messages/outgoing/", [
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


### 請求內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "conversation": "example_string",
  "sender": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "name": "客服助理",
    "avatar": "example_string"
  },
  "type": "example_string",
  "content": "example_string",
  "feedback": null,
  "createdAt": "2024-02-18T13:45:30.000Z",
  "attachments": [
    {
      "id": "550e8400-e29b-41d4-a716-446655440000",
      "type": null,
      "filename": "example.pdf",
      "file": "example.pdf"
    }
  ],
  "citations": [
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
  ],
  "citationNodes": [
    {
      "chatbotTextNode": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "charactersCount": 0,
        "hitsCount": 42,
        "text": "example_string",
        "updatedAt": "example_string",
        "filename": "example.pdf"
      },
      "score": 0,
      "displayScore": "example_string"
    }
  ]
}
```

### 回應內容

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "conversation": "example_string",
  "sender": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "name": "客服助理",
    "avatar": "example_string"
  },
  "type": "example_string",
  "content": "example_string",
  "feedback": null,
  "createdAt": "2024-02-18T13:45:30.000Z",
  "attachments": [
    {
      "id": "550e8400-e29b-41d4-a716-446655440000",
      "type": null,
      "filename": "example.pdf",
      "file": "example.pdf"
    }
  ],
  "citations": [
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
  ],
  "citationNodes": [
    {
      "chatbotTextNode": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "charactersCount": 0,
        "hitsCount": 42,
        "text": "example_string",
        "updatedAt": "example_string",
        "filename": "example.pdf"
      },
      "score": 0,
      "displayScore": "example_string"
    }
  ]
}
```

---
