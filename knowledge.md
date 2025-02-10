# 知識庫管理

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="maiagent-api">MaiAgent API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Documentation of API endpoints of MaiAgent

# Authentication

* API Key (ApiKeyAuth)
    - Parameter Name: **Authorization**, in: header. 

<h1 id="maiagent-api-chatbot-text-nodes">chatbot-text-nodes</h1>

## chatbotTextNodesList

<a id="opIdchatbotTextNodesList"></a>

`GET /api/chatbot-text-nodes/`

<h3 id="chatbottextnodeslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotFileContent|query|string(uuid)|false|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "charactersCount": {
            "type": "integer",
            "readOnly": true,
            "title": "字元數量"
          },
          "hitsCount": {
            "type": "integer",
            "readOnly": true,
            "title": "命中次數"
          },
          "text": {
            "type": "string",
            "readOnly": true,
            "title": "文字"
          },
          "updatedAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "更新時間",
            "pattern": "^\\d{13}$"
          },
          "filename": {
            "type": "string",
            "readOnly": true
          }
        },
        "required": [
          "charactersCount",
          "filename",
          "hitsCount",
          "id",
          "text",
          "updatedAt"
        ]
      }
    }
  }
}
```

<h3 id="chatbottextnodeslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedChatbotTextNodeList](#schemapaginatedchatbottextnodelist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="maiagent-api-parsers">Parsers</h1>

## parsersList

<a id="opIdparsersList"></a>

`GET /api/parsers/`

<h3 id="parserslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "name": {
            "type": "string",
            "maxLength": 255
          },
          "provider": {
            "enum": [
              "maiagent",
              "llama",
              "azure"
            ],
            "type": "string",
            "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
          },
          "priority": {
            "type": "integer",
            "readOnly": true
          }
        },
        "required": [
          "id",
          "name",
          "priority",
          "provider"
        ]
      }
    }
  }
}
```

<h3 id="parserslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedParserList](#schemapaginatedparserlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## parsersRetrieve

<a id="opIdparsersRetrieve"></a>

`GET /api/parsers/{id}/`

<h3 id="parsersretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 解析器.|

> Example responses

> 200 Response

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "maxLength": 255
    },
    "provider": {
      "enum": [
        "maiagent",
        "llama",
        "azure"
      ],
      "type": "string",
      "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
    },
    "priority": {
      "type": "integer",
      "readOnly": true
    }
  },
  "required": [
    "id",
    "name",
    "priority",
    "provider"
  ]
}
```

<h3 id="parsersretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Parser](#schemaparser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## parsersSupportedFileTypesRetrieve

<a id="opIdparsersSupportedFileTypesRetrieve"></a>

`GET /api/parsers/supported-file-types/`

取得所有解析器支援的檔案類型。

> Example responses

> 200 Response

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "maxLength": 255
    },
    "provider": {
      "enum": [
        "maiagent",
        "llama",
        "azure"
      ],
      "type": "string",
      "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
    },
    "priority": {
      "type": "integer",
      "readOnly": true
    }
  },
  "required": [
    "id",
    "name",
    "priority",
    "provider"
  ]
}
```

<h3 id="parserssupportedfiletypesretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Parser](#schemaparser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ParsersList

<a id="opIdv1ParsersList"></a>

`GET /api/v1/parsers/`

<h3 id="v1parserslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "name": {
            "type": "string",
            "maxLength": 255
          },
          "provider": {
            "enum": [
              "maiagent",
              "llama",
              "azure"
            ],
            "type": "string",
            "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
          },
          "priority": {
            "type": "integer",
            "readOnly": true
          }
        },
        "required": [
          "id",
          "name",
          "priority",
          "provider"
        ]
      }
    }
  }
}
```

<h3 id="v1parserslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedParserList](#schemapaginatedparserlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ParsersRetrieve

<a id="opIdv1ParsersRetrieve"></a>

`GET /api/v1/parsers/{id}/`

<h3 id="v1parsersretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 解析器.|

> Example responses

> 200 Response

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "maxLength": 255
    },
    "provider": {
      "enum": [
        "maiagent",
        "llama",
        "azure"
      ],
      "type": "string",
      "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
    },
    "priority": {
      "type": "integer",
      "readOnly": true
    }
  },
  "required": [
    "id",
    "name",
    "priority",
    "provider"
  ]
}
```

<h3 id="v1parsersretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Parser](#schemaparser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ParsersSupportedFileTypesRetrieve

<a id="opIdv1ParsersSupportedFileTypesRetrieve"></a>

`GET /api/v1/parsers/supported-file-types/`

取得所有解析器支援的檔案類型。

> Example responses

> 200 Response

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "maxLength": 255
    },
    "provider": {
      "enum": [
        "maiagent",
        "llama",
        "azure"
      ],
      "type": "string",
      "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
    },
    "priority": {
      "type": "integer",
      "readOnly": true
    }
  },
  "required": [
    "id",
    "name",
    "priority",
    "provider"
  ]
}
```

<h3 id="v1parserssupportedfiletypesretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Parser](#schemaparser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

# Schemas

<h2 id="tocS_AccessTypeEnum">AccessTypeEnum</h2>
<!-- backwards compatibility -->
<a id="schemaaccesstypeenum"></a>
<a id="schema_AccessTypeEnum"></a>
<a id="tocSaccesstypeenum"></a>
<a id="tocsaccesstypeenum"></a>

```json
{
  "enum": [
    "web",
    "admin",
    "api"
  ],
  "type": "string",
  "description": "* `web` - Web Chat\n* `admin` - Admin 問答\n* `api` - API"
}

```

* `web` - Web Chat
* `admin` - Admin 問答
* `api` - API

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[AccessTypeEnum](#schemaaccesstypeenum)|false|none|* `web` - Web Chat<br>* `admin` - Admin 問答<br>* `api` - API|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|web|
|*anonymous*|admin|
|*anonymous*|api|

<h2 id="tocS_Attachment">Attachment</h2>
<!-- backwards compatibility -->
<a id="schemaattachment"></a>
<a id="schema_Attachment"></a>
<a id="tocSattachment"></a>
<a id="tocsattachment"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "type": {
      "allOf": [
        {
          "enum": [
            "image",
            "video",
            "audio",
            "sticker",
            "other"
          ],
          "type": "string",
          "description": "* `image` - Image\n* `video` - Video\n* `audio` - Audio\n* `sticker` - Sticker\n* `other` - Other"
        }
      ],
      "default": "other"
    },
    "filename": {
      "type": "string"
    },
    "file": {
      "type": "string",
      "format": "uri"
    }
  },
  "required": [
    "file",
    "filename",
    "id"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|type|[TypeEnum](#schematypeenum)|false|none|* `image` - Image<br>* `video` - Video<br>* `audio` - Audio<br>* `sticker` - Sticker<br>* `other` - Other|
|filename|string|true|none|none|
|file|string(uri)|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|image|
|type|video|
|type|audio|
|type|sticker|
|type|other|

<h2 id="tocS_AttachmentCreateInput">AttachmentCreateInput</h2>
<!-- backwards compatibility -->
<a id="schemaattachmentcreateinput"></a>
<a id="schema_AttachmentCreateInput"></a>
<a id="tocSattachmentcreateinput"></a>
<a id="tocsattachmentcreateinput"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "type": {
      "allOf": [
        {
          "enum": [
            "image",
            "video",
            "audio",
            "sticker",
            "other"
          ],
          "type": "string",
          "description": "* `image` - Image\n* `video` - Video\n* `audio` - Audio\n* `sticker` - Sticker\n* `other` - Other"
        }
      ],
      "default": "other"
    },
    "filename": {
      "type": "string"
    },
    "file": {
      "type": "string",
      "format": "uri"
    },
    "conversation": {
      "type": "string",
      "format": "uuid",
      "writeOnly": true,
      "nullable": true
    }
  },
  "required": [
    "file",
    "filename",
    "id"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|type|[TypeEnum](#schematypeenum)|false|none|* `image` - Image<br>* `video` - Video<br>* `audio` - Audio<br>* `sticker` - Sticker<br>* `other` - Other|
|filename|string|true|none|none|
|file|string(uri)|true|none|none|
|conversation|string(uuid)¦null|false|write-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|image|
|type|video|
|type|audio|
|type|sticker|
|type|other|

<h2 id="tocS_AuthToken">AuthToken</h2>
<!-- backwards compatibility -->
<a id="schemaauthtoken"></a>
<a id="schema_AuthToken"></a>
<a id="tocSauthtoken"></a>
<a id="tocsauthtoken"></a>

```json
{
  "type": "object",
  "properties": {
    "username": {
      "type": "string",
      "writeOnly": true,
      "title": "使用者名稱"
    },
    "password": {
      "type": "string",
      "writeOnly": true,
      "title": "密碼"
    },
    "token": {
      "type": "string",
      "readOnly": true
    }
  },
  "required": [
    "password",
    "token",
    "username"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|true|write-only|none|
|password|string|true|write-only|none|
|token|string|true|read-only|none|

<h2 id="tocS_AutoReplySchedule">AutoReplySchedule</h2>
<!-- backwards compatibility -->
<a id="schemaautoreplyschedule"></a>
<a id="schema_AutoReplySchedule"></a>
<a id="tocSautoreplyschedule"></a>
<a id="tocsautoreplyschedule"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "weekday": {
      "type": "integer",
      "readOnly": true,
      "title": "星期"
    },
    "isEnabled": {
      "type": "boolean",
      "title": "開啟"
    },
    "timeSlots": {
      "type": "array",
      "items": {
        "type": "array",
        "items": {
          "type": "string",
          "format": "time",
          "title": "Time slots"
        },
        "maxItems": 2
      },
      "nullable": true
    },
    "weekdayName": {
      "type": "string",
      "readOnly": true
    }
  },
  "required": [
    "id",
    "weekday",
    "weekdayName"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|weekday|integer|true|read-only|none|
|isEnabled|boolean|false|none|none|
|timeSlots|[array]¦null|false|none|none|
|» Time slots|string(time)|false|none|none|
|weekdayName|string|true|read-only|none|

<h2 id="tocS_BlankEnum">BlankEnum</h2>
<!-- backwards compatibility -->
<a id="schemablankenum"></a>
<a id="schema_BlankEnum"></a>
<a id="tocSblankenum"></a>
<a id="tocsblankenum"></a>

```json
{
  "enum": [
    ""
  ]
}

```

### Properties

*None*

<h2 id="tocS_BuiltInWorkflow">BuiltInWorkflow</h2>
<!-- backwards compatibility -->
<a id="schemabuiltinworkflow"></a>
<a id="schema_BuiltInWorkflow"></a>
<a id="tocSbuiltinworkflow"></a>
<a id="tocsbuiltinworkflow"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    }
  },
  "required": [
    "id",
    "name"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|

<h2 id="tocS_ChannelTypeEnum">ChannelTypeEnum</h2>
<!-- backwards compatibility -->
<a id="schemachanneltypeenum"></a>
<a id="schema_ChannelTypeEnum"></a>
<a id="tocSchanneltypeenum"></a>
<a id="tocschanneltypeenum"></a>

```json
{
  "enum": [
    "line",
    "telegram",
    "web",
    "messenger"
  ],
  "type": "string",
  "description": "* `line` - LINE\n* `telegram` - Telegram\n* `web` - Web\n* `messenger` - Messenger"
}

```

* `line` - LINE
* `telegram` - Telegram
* `web` - Web
* `messenger` - Messenger

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ChannelTypeEnum](#schemachanneltypeenum)|false|none|* `line` - LINE<br>* `telegram` - Telegram<br>* `web` - Web<br>* `messenger` - Messenger|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|line|
|*anonymous*|telegram|
|*anonymous*|web|
|*anonymous*|messenger|

<h2 id="tocS_Chatbot">Chatbot</h2>
<!-- backwards compatibility -->
<a id="schemachatbot"></a>
<a id="schema_Chatbot"></a>
<a id="tocSchatbot"></a>
<a id="tocschatbot"></a>

```json
{
  "type": "object",
  "description": "Adds nested create feature",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "workflow": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "largeLanguageModel": {
      "type": "string",
      "format": "uuid"
    },
    "rag": {
      "type": "string",
      "format": "uuid"
    },
    "embeddingModel": {
      "type": "string",
      "format": "uuid",
      "nullable": true
    },
    "rerankerModel": {
      "type": "string",
      "format": "uuid",
      "nullable": true
    },
    "instructions": {
      "type": "string",
      "title": "指令"
    },
    "webhookUrl": {
      "type": "string",
      "format": "uri",
      "nullable": true,
      "maxLength": 511
    },
    "apiWebChatId": {
      "type": "string",
      "readOnly": true,
      "nullable": true,
      "title": "API WebChat ID"
    },
    "updatedAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "更新時間",
      "pattern": "^\\d{13}$"
    },
    "organization": {
      "type": "string",
      "format": "uuid"
    },
    "builtInWorkflow": {
      "type": "string",
      "format": "uuid",
      "nullable": true
    },
    "replyMode": {
      "allOf": [
        {
          "enum": [
            "normal",
            "template",
            "hybrid"
          ],
          "type": "string",
          "description": "* `normal` - 正常\n* `template` - 模板\n* `hybrid` - 混合"
        }
      ],
      "title": "回傳模式"
    },
    "template": {
      "type": "string",
      "nullable": true,
      "title": "模板"
    },
    "unanswerableTemplate": {
      "type": "string",
      "nullable": true,
      "title": "無法回答時的模板"
    },
    "totalLlmWordCount": {
      "type": "integer",
      "maximum": 9223372036854776000,
      "minimum": -9223372036854776000,
      "format": "int64",
      "title": "LLM 使用總字數",
      "description": "累積的 LLM 使用總字數"
    },
    "enableChineseConversion": {
      "type": "boolean"
    },
    "outputFormat": {
      "nullable": true
    }
  },
  "required": [
    "apiWebChatId",
    "id",
    "largeLanguageModel",
    "name",
    "rag",
    "updatedAt",
    "workflow"
  ]
}

```

Adds nested create feature

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|workflow|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|largeLanguageModel|string(uuid)|true|none|none|
|rag|string(uuid)|true|none|none|
|embeddingModel|string(uuid)¦null|false|none|none|
|rerankerModel|string(uuid)¦null|false|none|none|
|instructions|string|false|none|none|
|webhookUrl|string(uri)¦null|false|none|none|
|apiWebChatId|string¦null|true|read-only|none|
|updatedAt|string(timestamp)|true|read-only|none|
|organization|string(uuid)|false|none|none|
|builtInWorkflow|string(uuid)¦null|false|none|none|
|replyMode|[ReplyModeEnum](#schemareplymodeenum)|false|none|* `normal` - 正常<br>* `template` - 模板<br>* `hybrid` - 混合|
|template|string¦null|false|none|none|
|unanswerableTemplate|string¦null|false|none|none|
|totalLlmWordCount|integer(int64)|false|none|累積的 LLM 使用總字數|
|enableChineseConversion|boolean|false|none|none|
|outputFormat|any|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|replyMode|normal|
|replyMode|template|
|replyMode|hybrid|

<h2 id="tocS_ChatbotBatchQAFile">ChatbotBatchQAFile</h2>
<!-- backwards compatibility -->
<a id="schemachatbotbatchqafile"></a>
<a id="schema_ChatbotBatchQAFile"></a>
<a id="tocSchatbotbatchqafile"></a>
<a id="tocschatbotbatchqafile"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "file": {
      "type": "string",
      "format": "uri"
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "createdAt",
    "file",
    "id"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|file|string(uri)|true|none|none|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_ChatbotFile">ChatbotFile</h2>
<!-- backwards compatibility -->
<a id="schemachatbotfile"></a>
<a id="schema_ChatbotFile"></a>
<a id="tocSchatbotfile"></a>
<a id="tocschatbotfile"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "filename": {
      "type": "string"
    },
    "file": {
      "type": "string",
      "format": "uri"
    },
    "fileType": {
      "type": "string",
      "readOnly": true,
      "title": "檔案類型"
    },
    "size": {
      "type": "integer",
      "readOnly": true,
      "title": "檔案大小"
    },
    "status": {
      "allOf": [
        {
          "enum": [
            "initial",
            "processing",
            "done",
            "deleting",
            "failed"
          ],
          "type": "string",
          "description": "* `initial` - Initial\n* `processing` - Processing\n* `done` - Done\n* `deleting` - Deleting\n* `failed` - Failed"
        }
      ],
      "readOnly": true,
      "title": "狀態"
    },
    "chatbotFileContent": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "parser": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "name": {
          "type": "string",
          "maxLength": 255
        },
        "provider": {
          "enum": [
            "maiagent",
            "llama",
            "azure"
          ],
          "type": "string",
          "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
        },
        "priority": {
          "type": "integer",
          "readOnly": true
        }
      },
      "required": [
        "id",
        "name",
        "priority",
        "provider"
      ]
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "chatbotFileContent",
    "createdAt",
    "file",
    "fileType",
    "filename",
    "id",
    "parser",
    "size",
    "status"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|filename|string|true|none|none|
|file|string(uri)|true|none|none|
|fileType|string|true|read-only|none|
|size|integer|true|read-only|none|
|status|[StatusBbcEnum](#schemastatusbbcenum)|true|read-only|* `initial` - Initial<br>* `processing` - Processing<br>* `done` - Done<br>* `deleting` - Deleting<br>* `failed` - Failed|
|chatbotFileContent|string(uuid)|true|read-only|none|
|parser|[Parser](#schemaparser)|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» provider|[ProviderEnum](#schemaproviderenum)|true|none|* `maiagent` - MaiAgent<br>* `llama` - Llama<br>* `azure` - Azure|
|» priority|integer|true|read-only|none|
|createdAt|string(timestamp)|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|initial|
|status|processing|
|status|done|
|status|deleting|
|status|failed|
|provider|maiagent|
|provider|llama|
|provider|azure|

<h2 id="tocS_ChatbotFileContent">ChatbotFileContent</h2>
<!-- backwards compatibility -->
<a id="schemachatbotfilecontent"></a>
<a id="schema_ChatbotFileContent"></a>
<a id="tocSchatbotfilecontent"></a>
<a id="tocschatbotfilecontent"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "content": {
      "type": "string",
      "readOnly": true
    },
    "modifiedContent": {
      "type": "string",
      "title": "檔案修改內容"
    },
    "type": {
      "type": "string",
      "readOnly": true
    },
    "updatedAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "更新時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "content",
    "id",
    "type",
    "updatedAt"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|content|string|true|read-only|none|
|modifiedContent|string|false|none|none|
|type|string|true|read-only|none|
|updatedAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_ChatbotFileCreate">ChatbotFileCreate</h2>
<!-- backwards compatibility -->
<a id="schemachatbotfilecreate"></a>
<a id="schema_ChatbotFileCreate"></a>
<a id="tocSchatbotfilecreate"></a>
<a id="tocschatbotfilecreate"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "filename": {
      "type": "string"
    },
    "file": {
      "type": "string",
      "format": "uri"
    },
    "fileType": {
      "type": "string",
      "readOnly": true,
      "title": "檔案類型"
    },
    "size": {
      "type": "integer",
      "readOnly": true,
      "title": "檔案大小"
    },
    "status": {
      "allOf": [
        {
          "enum": [
            "initial",
            "processing",
            "done",
            "deleting",
            "failed"
          ],
          "type": "string",
          "description": "* `initial` - Initial\n* `processing` - Processing\n* `done` - Done\n* `deleting` - Deleting\n* `failed` - Failed"
        }
      ],
      "readOnly": true,
      "title": "狀態"
    },
    "chatbotFileContent": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "parser": {
      "type": "string",
      "format": "uuid"
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "chatbotFileContent",
    "createdAt",
    "file",
    "fileType",
    "filename",
    "id",
    "size",
    "status"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|filename|string|true|none|none|
|file|string(uri)|true|none|none|
|fileType|string|true|read-only|none|
|size|integer|true|read-only|none|
|status|[StatusBbcEnum](#schemastatusbbcenum)|true|read-only|* `initial` - Initial<br>* `processing` - Processing<br>* `done` - Done<br>* `deleting` - Deleting<br>* `failed` - Failed|
|chatbotFileContent|string(uuid)|true|read-only|none|
|parser|string(uuid)|false|none|none|
|createdAt|string(timestamp)|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|initial|
|status|processing|
|status|done|
|status|deleting|
|status|failed|

<h2 id="tocS_ChatbotFileCreateFiles">ChatbotFileCreateFiles</h2>
<!-- backwards compatibility -->
<a id="schemachatbotfilecreatefiles"></a>
<a id="schema_ChatbotFileCreateFiles"></a>
<a id="tocSchatbotfilecreatefiles"></a>
<a id="tocschatbotfilecreatefiles"></a>

```json
{
  "type": "object",
  "properties": {
    "files": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "filename": {
            "type": "string"
          },
          "file": {
            "type": "string",
            "format": "uri"
          },
          "fileType": {
            "type": "string",
            "readOnly": true,
            "title": "檔案類型"
          },
          "size": {
            "type": "integer",
            "readOnly": true,
            "title": "檔案大小"
          },
          "status": {
            "allOf": [
              {
                "enum": [
                  "initial",
                  "processing",
                  "done",
                  "deleting",
                  "failed"
                ],
                "type": "string",
                "description": "* `initial` - Initial\n* `processing` - Processing\n* `done` - Done\n* `deleting` - Deleting\n* `failed` - Failed"
              }
            ],
            "readOnly": true,
            "title": "狀態"
          },
          "chatbotFileContent": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "parser": {
            "type": "string",
            "format": "uuid"
          },
          "createdAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "建立時間",
            "pattern": "^\\d{13}$"
          }
        },
        "required": [
          "chatbotFileContent",
          "createdAt",
          "file",
          "fileType",
          "filename",
          "id",
          "size",
          "status"
        ]
      }
    }
  },
  "required": [
    "files"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|files|[[ChatbotFileCreate](#schemachatbotfilecreate)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» filename|string|true|none|none|
|» file|string(uri)|true|none|none|
|» fileType|string|true|read-only|none|
|» size|integer|true|read-only|none|
|» status|[StatusBbcEnum](#schemastatusbbcenum)|true|read-only|* `initial` - Initial<br>* `processing` - Processing<br>* `done` - Done<br>* `deleting` - Deleting<br>* `failed` - Failed|
|» chatbotFileContent|string(uuid)|true|read-only|none|
|» parser|string(uuid)|false|none|none|
|» createdAt|string(timestamp)|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|initial|
|status|processing|
|status|done|
|status|deleting|
|status|failed|

<h2 id="tocS_ChatbotInstructionRecord">ChatbotInstructionRecord</h2>
<!-- backwards compatibility -->
<a id="schemachatbotinstructionrecord"></a>
<a id="schema_ChatbotInstructionRecord"></a>
<a id="tocSchatbotinstructionrecord"></a>
<a id="tocschatbotinstructionrecord"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "instructions": {
      "type": "string",
      "nullable": true,
      "title": "指令"
    },
    "operatorName": {
      "type": "string",
      "readOnly": true
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "createdAt",
    "id",
    "operatorName"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|instructions|string¦null|false|none|none|
|operatorName|string|true|read-only|none|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_ChatbotList">ChatbotList</h2>
<!-- backwards compatibility -->
<a id="schemachatbotlist"></a>
<a id="schema_ChatbotList"></a>
<a id="tocSchatbotlist"></a>
<a id="tocschatbotlist"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "largeLanguageModel": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "name": {
          "type": "string",
          "title": "名稱",
          "maxLength": 255
        },
        "isDefault": {
          "type": "boolean",
          "title": "是否預設"
        }
      },
      "required": [
        "id",
        "name"
      ]
    },
    "rag": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "name": {
          "type": "string",
          "title": "名稱",
          "maxLength": 255
        },
        "isDefault": {
          "type": "boolean",
          "title": "是否預設"
        },
        "isEmbeddingModelSelectable": {
          "type": "string",
          "readOnly": true
        },
        "isRerankerModelSelectable": {
          "type": "string",
          "readOnly": true
        },
        "isOutputFormatAvailable": {
          "type": "string",
          "readOnly": true
        }
      },
      "required": [
        "id",
        "isEmbeddingModelSelectable",
        "isOutputFormatAvailable",
        "isRerankerModelSelectable",
        "name"
      ]
    },
    "embeddingModel": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "name": {
          "type": "string",
          "title": "名稱",
          "maxLength": 255
        },
        "isDefault": {
          "type": "boolean",
          "title": "是否預設"
        }
      },
      "required": [
        "id",
        "name"
      ]
    },
    "rerankerModel": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "name": {
          "type": "string",
          "title": "名稱",
          "maxLength": 255
        },
        "isDefault": {
          "type": "boolean",
          "title": "是否預設"
        }
      },
      "required": [
        "id",
        "name"
      ]
    },
    "updatedAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "更新時間",
      "pattern": "^\\d{13}$"
    },
    "enableChineseConversion": {
      "type": "boolean",
      "title": "啟用繁體中文轉換"
    }
  },
  "required": [
    "embeddingModel",
    "id",
    "largeLanguageModel",
    "name",
    "rag",
    "rerankerModel",
    "updatedAt"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|largeLanguageModel|[LargeLanguageModel](#schemalargelanguagemodel)|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» isDefault|boolean|false|none|none|
|rag|[Rag](#schemarag)|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» isDefault|boolean|false|none|none|
|» isEmbeddingModelSelectable|string|true|read-only|none|
|» isRerankerModelSelectable|string|true|read-only|none|
|» isOutputFormatAvailable|string|true|read-only|none|
|embeddingModel|[EmbeddingModel](#schemaembeddingmodel)|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» isDefault|boolean|false|none|none|
|rerankerModel|[RerankerModel](#schemarerankermodel)|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» isDefault|boolean|false|none|none|
|updatedAt|string(timestamp)|true|read-only|none|
|enableChineseConversion|boolean|false|none|none|

<h2 id="tocS_ChatbotRecord">ChatbotRecord</h2>
<!-- backwards compatibility -->
<a id="schemachatbotrecord"></a>
<a id="schema_ChatbotRecord"></a>
<a id="tocSchatbotrecord"></a>
<a id="tocschatbotrecord"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "inputMessage": {
      "type": "string",
      "readOnly": true
    },
    "condenseMessage": {
      "type": "string",
      "readOnly": true,
      "title": "Chatbot 修飾輸入訊息",
      "description": "綜合聊天歷史與上下文後，修飾過後的使用者訊息"
    },
    "outputMessage": {
      "type": "string",
      "readOnly": true
    },
    "context": {
      "type": "string",
      "readOnly": true,
      "nullable": true,
      "title": "參考資料"
    },
    "faithfulnessScore": {
      "type": "number",
      "format": "double",
      "readOnly": true,
      "nullable": true,
      "title": "誠實性評分",
      "description": "判斷chatbot回覆是否符合資料庫內容，是否憑空想像"
    },
    "displayFaithfulnessScore": {
      "type": "string",
      "readOnly": true
    },
    "answerRelevancyScore": {
      "type": "number",
      "format": "double",
      "readOnly": true,
      "nullable": true,
      "title": "回答相關性評分",
      "description": "判斷chatbot回覆是否與使用者問題相關"
    },
    "displayAnswerRelevancyScore": {
      "type": "string",
      "readOnly": true
    },
    "contextPrecisionScore": {
      "type": "number",
      "format": "double",
      "readOnly": true,
      "nullable": true,
      "title": "參考資料相關性評分",
      "description": "判斷chatbot回覆是否與參考資料相關"
    },
    "displayContextPrecisionScore": {
      "type": "string",
      "readOnly": true
    },
    "answerCorrectnessScore": {
      "type": "number",
      "format": "double",
      "readOnly": true,
      "nullable": true,
      "title": "回答正確性評分",
      "description": "判斷chatbot回覆是否正確(需要有標準答案)"
    },
    "displayAnswerCorrectnessScore": {
      "type": "string",
      "readOnly": true
    },
    "answerSimilarityScore": {
      "type": "number",
      "format": "double",
      "readOnly": true,
      "nullable": true,
      "title": "回答相似性評分",
      "description": "判斷chatbot回覆是否與標準答案相似"
    },
    "displayAnswerSimilarityScore": {
      "type": "string",
      "readOnly": true
    },
    "contextRecallScore": {
      "type": "number",
      "format": "double",
      "readOnly": true,
      "nullable": true,
      "title": "參考資料召回率評分",
      "description": "判斷chatbot回覆是否能夠從參考資料中召回相關資料"
    },
    "displayContextRecallScore": {
      "type": "string",
      "readOnly": true
    },
    "replyTime": {
      "type": "string",
      "readOnly": true,
      "nullable": true,
      "title": "回覆時間"
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    },
    "error": {
      "type": "string",
      "readOnly": true,
      "nullable": true,
      "title": "錯誤訊息",
      "description": "儲存執行過程中的錯誤訊息"
    }
  },
  "required": [
    "answerCorrectnessScore",
    "answerRelevancyScore",
    "answerSimilarityScore",
    "condenseMessage",
    "context",
    "contextPrecisionScore",
    "contextRecallScore",
    "createdAt",
    "displayAnswerCorrectnessScore",
    "displayAnswerRelevancyScore",
    "displayAnswerSimilarityScore",
    "displayContextPrecisionScore",
    "displayContextRecallScore",
    "displayFaithfulnessScore",
    "error",
    "faithfulnessScore",
    "id",
    "inputMessage",
    "outputMessage",
    "replyTime"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|inputMessage|string|true|read-only|none|
|condenseMessage|string|true|read-only|綜合聊天歷史與上下文後，修飾過後的使用者訊息|
|outputMessage|string|true|read-only|none|
|context|string¦null|true|read-only|none|
|faithfulnessScore|number(double)¦null|true|read-only|判斷chatbot回覆是否符合資料庫內容，是否憑空想像|
|displayFaithfulnessScore|string|true|read-only|none|
|answerRelevancyScore|number(double)¦null|true|read-only|判斷chatbot回覆是否與使用者問題相關|
|displayAnswerRelevancyScore|string|true|read-only|none|
|contextPrecisionScore|number(double)¦null|true|read-only|判斷chatbot回覆是否與參考資料相關|
|displayContextPrecisionScore|string|true|read-only|none|
|answerCorrectnessScore|number(double)¦null|true|read-only|判斷chatbot回覆是否正確(需要有標準答案)|
|displayAnswerCorrectnessScore|string|true|read-only|none|
|answerSimilarityScore|number(double)¦null|true|read-only|判斷chatbot回覆是否與標準答案相似|
|displayAnswerSimilarityScore|string|true|read-only|none|
|contextRecallScore|number(double)¦null|true|read-only|判斷chatbot回覆是否能夠從參考資料中召回相關資料|
|displayContextRecallScore|string|true|read-only|none|
|replyTime|string¦null|true|read-only|none|
|createdAt|string(timestamp)|true|read-only|none|
|error|string¦null|true|read-only|儲存執行過程中的錯誤訊息|

<h2 id="tocS_ChatbotTextNode">ChatbotTextNode</h2>
<!-- backwards compatibility -->
<a id="schemachatbottextnode"></a>
<a id="schema_ChatbotTextNode"></a>
<a id="tocSchatbottextnode"></a>
<a id="tocschatbottextnode"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "charactersCount": {
      "type": "integer",
      "readOnly": true,
      "title": "字元數量"
    },
    "hitsCount": {
      "type": "integer",
      "readOnly": true,
      "title": "命中次數"
    },
    "text": {
      "type": "string",
      "readOnly": true,
      "title": "文字"
    },
    "updatedAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "更新時間",
      "pattern": "^\\d{13}$"
    },
    "filename": {
      "type": "string",
      "readOnly": true
    }
  },
  "required": [
    "charactersCount",
    "filename",
    "hitsCount",
    "id",
    "text",
    "updatedAt"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|charactersCount|integer|true|read-only|none|
|hitsCount|integer|true|read-only|none|
|text|string|true|read-only|none|
|updatedAt|string(timestamp)|true|read-only|none|
|filename|string|true|read-only|none|

<h2 id="tocS_ChatbotUsageStatistic">ChatbotUsageStatistic</h2>
<!-- backwards compatibility -->
<a id="schemachatbotusagestatistic"></a>
<a id="schema_ChatbotUsageStatistic"></a>
<a id="tocSchatbotusagestatistic"></a>
<a id="tocschatbotusagestatistic"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "chatbotId": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "uploadedFilesSizeTotal": {
      "type": "integer",
      "maximum": 2147483647,
      "minimum": -2147483648,
      "title": "總檔案大小"
    },
    "conversationsCount": {
      "type": "integer",
      "maximum": 2147483647,
      "minimum": -2147483648,
      "title": "總對話數"
    }
  },
  "required": [
    "chatbotId",
    "id"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|chatbotId|string(uuid)|true|read-only|none|
|uploadedFilesSizeTotal|integer|false|none|none|
|conversationsCount|integer|false|none|none|

<h2 id="tocS_CitationNode">CitationNode</h2>
<!-- backwards compatibility -->
<a id="schemacitationnode"></a>
<a id="schema_CitationNode"></a>
<a id="tocScitationnode"></a>
<a id="tocscitationnode"></a>

```json
{
  "type": "object",
  "properties": {
    "chatbotTextNode": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "charactersCount": {
          "type": "integer",
          "readOnly": true,
          "title": "字元數量"
        },
        "hitsCount": {
          "type": "integer",
          "readOnly": true,
          "title": "命中次數"
        },
        "text": {
          "type": "string",
          "readOnly": true,
          "title": "文字"
        },
        "updatedAt": {
          "type": "string",
          "format": "timestamp",
          "readOnly": true,
          "title": "更新時間",
          "pattern": "^\\d{13}$"
        },
        "filename": {
          "type": "string",
          "readOnly": true
        }
      },
      "required": [
        "charactersCount",
        "filename",
        "hitsCount",
        "id",
        "text",
        "updatedAt"
      ]
    },
    "score": {
      "type": "number",
      "format": "double"
    },
    "displayScore": {
      "type": "string",
      "readOnly": true
    }
  },
  "required": [
    "chatbotTextNode",
    "displayScore"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|chatbotTextNode|[ChatbotTextNode](#schemachatbottextnode)|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» charactersCount|integer|true|read-only|none|
|» hitsCount|integer|true|read-only|none|
|» text|string|true|read-only|none|
|» updatedAt|string(timestamp)|true|read-only|none|
|» filename|string|true|read-only|none|
|score|number(double)|false|none|none|
|displayScore|string|true|read-only|none|

<h2 id="tocS_Contact">Contact</h2>
<!-- backwards compatibility -->
<a id="schemacontact"></a>
<a id="schema_Contact"></a>
<a id="tocScontact"></a>
<a id="tocscontact"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "姓名",
      "maxLength": 255
    },
    "avatar": {
      "type": "string",
      "format": "uri",
      "title": "大頭貼網址",
      "maxLength": 511
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "createdAt",
    "id",
    "name"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|avatar|string(uri)|false|none|none|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_Conversation">Conversation</h2>
<!-- backwards compatibility -->
<a id="schemaconversation"></a>
<a id="schema_Conversation"></a>
<a id="tocSconversation"></a>
<a id="tocsconversation"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "contact": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "name": {
          "type": "string",
          "title": "姓名",
          "maxLength": 255
        },
        "avatar": {
          "type": "string",
          "format": "uri",
          "title": "大頭貼網址",
          "maxLength": 511
        },
        "createdAt": {
          "type": "string",
          "format": "timestamp",
          "readOnly": true,
          "title": "建立時間",
          "pattern": "^\\d{13}$"
        }
      },
      "required": [
        "createdAt",
        "id",
        "name"
      ]
    },
    "inbox": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "name": {
          "type": "string",
          "title": "名稱",
          "maxLength": 255
        },
        "channelType": {
          "allOf": [
            {
              "enum": [
                "line",
                "telegram",
                "web",
                "messenger"
              ],
              "type": "string",
              "description": "* `line` - LINE\n* `telegram` - Telegram\n* `web` - Web\n* `messenger` - Messenger"
            }
          ],
          "title": "頻道類型"
        },
        "unreadConversationsCount": {
          "type": "integer",
          "maximum": 2147483647,
          "minimum": -2147483648,
          "title": "未讀對話數量"
        }
      },
      "required": [
        "channelType",
        "id",
        "name"
      ]
    },
    "title": {
      "type": "string",
      "readOnly": true,
      "title": "標題"
    },
    "lastMessage": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "conversation": {
          "type": "string",
          "format": "uuid",
          "title": "對話"
        },
        "sender": {
          "type": "object",
          "properties": {
            "id": {
              "type": "integer"
            },
            "name": {
              "type": "string"
            },
            "avatar": {
              "type": "string",
              "format": "uri"
            }
          },
          "required": [
            "avatar",
            "id",
            "name"
          ]
        },
        "type": {
          "type": "string",
          "default": "incoming"
        },
        "content": {
          "type": "string",
          "title": "內容"
        },
        "feedback": {
          "nullable": true,
          "title": "回饋",
          "oneOf": [
            {
              "enum": [
                "like",
                "dislike"
              ],
              "type": "string",
              "description": "* `like` - Like\n* `dislike` - Dislike"
            },
            {
              "enum": [
                ""
              ]
            },
            {
              "enum": [
                null
              ]
            }
          ]
        },
        "createdAt": {
          "type": "string",
          "format": "timestamp",
          "readOnly": true,
          "title": "建立時間",
          "pattern": "^\\d{13}$"
        },
        "attachments": {
          "type": "array",
          "items": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "type": {
                "allOf": [
                  {
                    "enum": [
                      "image",
                      "video",
                      "audio",
                      "sticker",
                      "other"
                    ],
                    "type": "string",
                    "description": "* `image` - Image\n* `video` - Video\n* `audio` - Audio\n* `sticker` - Sticker\n* `other` - Other"
                  }
                ],
                "default": "other"
              },
              "filename": {
                "type": "string"
              },
              "file": {
                "type": "string",
                "format": "uri"
              }
            },
            "required": [
              "file",
              "filename",
              "id"
            ]
          }
        },
        "citations": {
          "type": "array",
          "items": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "filename": {
                "type": "string"
              },
              "file": {
                "type": "string",
                "format": "uri"
              },
              "fileType": {
                "type": "string",
                "readOnly": true,
                "title": "檔案類型"
              },
              "size": {
                "type": "integer",
                "readOnly": true,
                "title": "檔案大小"
              },
              "status": {
                "allOf": [
                  {
                    "enum": [
                      "initial",
                      "processing",
                      "done",
                      "deleting",
                      "failed"
                    ],
                    "type": "string",
                    "description": "* `initial` - Initial\n* `processing` - Processing\n* `done` - Done\n* `deleting` - Deleting\n* `failed` - Failed"
                  }
                ],
                "readOnly": true,
                "title": "狀態"
              },
              "chatbotFileContent": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "parser": {
                "type": "object",
                "properties": {
                  "id": {
                    "type": "string",
                    "format": "uuid",
                    "readOnly": true
                  },
                  "name": {
                    "type": "string",
                    "maxLength": 255
                  },
                  "provider": {
                    "enum": [
                      "maiagent",
                      "llama",
                      "azure"
                    ],
                    "type": "string",
                    "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
                  },
                  "priority": {
                    "type": "integer",
                    "readOnly": true
                  }
                },
                "required": [
                  "id",
                  "name",
                  "priority",
                  "provider"
                ]
              },
              "createdAt": {
                "type": "string",
                "format": "timestamp",
                "readOnly": true,
                "title": "建立時間",
                "pattern": "^\\d{13}$"
              }
            },
            "required": [
              "chatbotFileContent",
              "createdAt",
              "file",
              "fileType",
              "filename",
              "id",
              "parser",
              "size",
              "status"
            ]
          },
          "readOnly": true
        },
        "citationNodes": {
          "type": "array",
          "items": {
            "type": "object",
            "properties": {
              "chatbotTextNode": {
                "type": "object",
                "properties": {
                  "id": {
                    "type": "string",
                    "format": "uuid",
                    "readOnly": true
                  },
                  "charactersCount": {
                    "type": "integer",
                    "readOnly": true,
                    "title": "字元數量"
                  },
                  "hitsCount": {
                    "type": "integer",
                    "readOnly": true,
                    "title": "命中次數"
                  },
                  "text": {
                    "type": "string",
                    "readOnly": true,
                    "title": "文字"
                  },
                  "updatedAt": {
                    "type": "string",
                    "format": "timestamp",
                    "readOnly": true,
                    "title": "更新時間",
                    "pattern": "^\\d{13}$"
                  },
                  "filename": {
                    "type": "string",
                    "readOnly": true
                  }
                },
                "required": [
                  "charactersCount",
                  "filename",
                  "hitsCount",
                  "id",
                  "text",
                  "updatedAt"
                ]
              },
              "score": {
                "type": "number",
                "format": "double"
              },
              "displayScore": {
                "type": "string",
                "readOnly": true
              }
            },
            "required": [
              "chatbotTextNode",
              "displayScore"
            ]
          },
          "readOnly": true
        }
      },
      "required": [
        "citationNodes",
        "citations",
        "conversation",
        "createdAt",
        "id"
      ]
    },
    "lastMessageCreatedAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "最後訊息時間",
      "pattern": "^\\d{13}$"
    },
    "unreadMessagesCount": {
      "type": "integer",
      "readOnly": true,
      "title": "未讀訊息數量"
    },
    "autoReplyEnabled": {
      "type": "boolean",
      "readOnly": true,
      "title": "開啟自動回覆"
    },
    "isAutoReplyNow": {
      "type": "string",
      "readOnly": true
    },
    "lastReadAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "nullable": true,
      "title": "最後查看時間",
      "pattern": "^\\d{13}$"
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    },
    "isGroupChat": {
      "type": "string",
      "readOnly": true
    },
    "enableGroupMention": {
      "type": "string",
      "readOnly": true
    }
  },
  "required": [
    "autoReplyEnabled",
    "contact",
    "createdAt",
    "enableGroupMention",
    "id",
    "inbox",
    "isAutoReplyNow",
    "isGroupChat",
    "lastMessageCreatedAt",
    "lastReadAt",
    "title",
    "unreadMessagesCount"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|contact|[Contact](#schemacontact)|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» avatar|string(uri)|false|none|none|
|» createdAt|string(timestamp)|true|read-only|none|
|inbox|[Inbox](#schemainbox)|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» channelType|[ChannelTypeEnum](#schemachanneltypeenum)|true|none|* `line` - LINE<br>* `telegram` - Telegram<br>* `web` - Web<br>* `messenger` - Messenger|
|» unreadConversationsCount|integer|false|none|none|
|title|string|true|read-only|none|
|lastMessage|[Message](#schemamessage)|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» conversation|string(uuid)|true|none|none|
|» sender|[Sender](#schemasender)|false|none|none|
|»» id|integer|true|none|none|
|»» name|string|true|none|none|
|»» avatar|string(uri)|true|none|none|
|» type|string|false|none|none|
|» content|string|false|none|none|
|» feedback|any|false|none|none|

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[FeedbackEnum](#schemafeedbackenum)|false|none|* `like` - Like<br>* `dislike` - Dislike|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|object|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» createdAt|string(timestamp)|true|read-only|none|
|» attachments|[[Attachment](#schemaattachment)]|false|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» type|[TypeEnum](#schematypeenum)|false|none|* `image` - Image<br>* `video` - Video<br>* `audio` - Audio<br>* `sticker` - Sticker<br>* `other` - Other|
|»» filename|string|true|none|none|
|»» file|string(uri)|true|none|none|
|» citations|[[ChatbotFile](#schemachatbotfile)]|true|read-only|none|
|»» id|string(uuid)|true|read-only|none|
|»» filename|string|true|none|none|
|»» file|string(uri)|true|none|none|
|»» fileType|string|true|read-only|none|
|»» size|integer|true|read-only|none|
|»» status|[StatusBbcEnum](#schemastatusbbcenum)|true|read-only|* `initial` - Initial<br>* `processing` - Processing<br>* `done` - Done<br>* `deleting` - Deleting<br>* `failed` - Failed|
|»» chatbotFileContent|string(uuid)|true|read-only|none|
|»» parser|[Parser](#schemaparser)|true|none|none|
|»»» id|string(uuid)|true|read-only|none|
|»»» name|string|true|none|none|
|»»» provider|[ProviderEnum](#schemaproviderenum)|true|none|* `maiagent` - MaiAgent<br>* `llama` - Llama<br>* `azure` - Azure|
|»»» priority|integer|true|read-only|none|
|»» createdAt|string(timestamp)|true|read-only|none|
|» citationNodes|[[CitationNode](#schemacitationnode)]|true|read-only|none|
|»» chatbotTextNode|[ChatbotTextNode](#schemachatbottextnode)|true|none|none|
|»»» id|string(uuid)|true|read-only|none|
|»»» charactersCount|integer|true|read-only|none|
|»»» hitsCount|integer|true|read-only|none|
|»»» text|string|true|read-only|none|
|»»» updatedAt|string(timestamp)|true|read-only|none|
|»»» filename|string|true|read-only|none|
|»» score|number(double)|false|none|none|
|»» displayScore|string|true|read-only|none|
|lastMessageCreatedAt|string(timestamp)|true|read-only|none|
|unreadMessagesCount|integer|true|read-only|none|
|autoReplyEnabled|boolean|true|read-only|none|
|isAutoReplyNow|string|true|read-only|none|
|lastReadAt|string(timestamp)¦null|true|read-only|none|
|createdAt|string(timestamp)|true|read-only|none|
|isGroupChat|string|true|read-only|none|
|enableGroupMention|string|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|channelType|line|
|channelType|telegram|
|channelType|web|
|channelType|messenger|
|*anonymous*|like|
|*anonymous*|dislike|
|*anonymous*||
|*anonymous*|null|
|type|image|
|type|video|
|type|audio|
|type|sticker|
|type|other|
|status|initial|
|status|processing|
|status|done|
|status|deleting|
|status|failed|
|provider|maiagent|
|provider|llama|
|provider|azure|

<h2 id="tocS_CrawlPage">CrawlPage</h2>
<!-- backwards compatibility -->
<a id="schemacrawlpage"></a>
<a id="schema_CrawlPage"></a>
<a id="tocScrawlpage"></a>
<a id="tocscrawlpage"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "url": {
      "type": "string",
      "format": "uri",
      "title": "網頁網址",
      "maxLength": 511
    },
    "title": {
      "type": "string",
      "nullable": true,
      "title": "網頁標題"
    },
    "status": {
      "allOf": [
        {
          "enum": [
            "pending",
            "processing",
            "done",
            "cancelled"
          ],
          "type": "string",
          "description": "* `pending` - Pending\n* `processing` - Processing\n* `done` - Done\n* `cancelled` - Cancelled"
        }
      ],
      "title": "狀態"
    },
    "isOriginalPage": {
      "type": "boolean",
      "title": "是否為原始頁面"
    }
  },
  "required": [
    "id",
    "url"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|url|string(uri)|true|none|none|
|title|string¦null|false|none|none|
|status|[CrawlPageStatusEnum](#schemacrawlpagestatusenum)|false|none|* `pending` - Pending<br>* `processing` - Processing<br>* `done` - Done<br>* `cancelled` - Cancelled|
|isOriginalPage|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|pending|
|status|processing|
|status|done|
|status|cancelled|

<h2 id="tocS_CrawlPageRequest">CrawlPageRequest</h2>
<!-- backwards compatibility -->
<a id="schemacrawlpagerequest"></a>
<a id="schema_CrawlPageRequest"></a>
<a id="tocScrawlpagerequest"></a>
<a id="tocscrawlpagerequest"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "url": {
      "type": "string",
      "format": "uri",
      "title": "網頁網址",
      "maxLength": 200
    },
    "status": {
      "allOf": [
        {
          "enum": [
            "processing",
            "done",
            "cancelled"
          ],
          "type": "string",
          "description": "* `processing` - Processing\n* `done` - Done\n* `cancelled` - Cancelled"
        }
      ],
      "title": "狀態"
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "createdAt",
    "id",
    "url"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|url|string(uri)|true|none|none|
|status|[Status235Enum](#schemastatus235enum)|false|none|* `processing` - Processing<br>* `done` - Done<br>* `cancelled` - Cancelled|
|createdAt|string(timestamp)|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|processing|
|status|done|
|status|cancelled|

<h2 id="tocS_CrawlPageRequestCreate">CrawlPageRequestCreate</h2>
<!-- backwards compatibility -->
<a id="schemacrawlpagerequestcreate"></a>
<a id="schema_CrawlPageRequestCreate"></a>
<a id="tocScrawlpagerequestcreate"></a>
<a id="tocscrawlpagerequestcreate"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "url": {
      "type": "string",
      "format": "uri",
      "title": "網頁網址",
      "maxLength": 200
    },
    "status": {
      "allOf": [
        {
          "enum": [
            "processing",
            "done",
            "cancelled"
          ],
          "type": "string",
          "description": "* `processing` - Processing\n* `done` - Done\n* `cancelled` - Cancelled"
        }
      ],
      "title": "狀態"
    }
  },
  "required": [
    "id",
    "url"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|url|string(uri)|true|none|none|
|status|[Status235Enum](#schemastatus235enum)|false|none|* `processing` - Processing<br>* `done` - Done<br>* `cancelled` - Cancelled|

#### Enumerated Values

|Property|Value|
|---|---|
|status|processing|
|status|done|
|status|cancelled|

<h2 id="tocS_CrawlPageStatusEnum">CrawlPageStatusEnum</h2>
<!-- backwards compatibility -->
<a id="schemacrawlpagestatusenum"></a>
<a id="schema_CrawlPageStatusEnum"></a>
<a id="tocScrawlpagestatusenum"></a>
<a id="tocscrawlpagestatusenum"></a>

```json
{
  "enum": [
    "pending",
    "processing",
    "done",
    "cancelled"
  ],
  "type": "string",
  "description": "* `pending` - Pending\n* `processing` - Processing\n* `done` - Done\n* `cancelled` - Cancelled"
}

```

* `pending` - Pending
* `processing` - Processing
* `done` - Done
* `cancelled` - Cancelled

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[CrawlPageStatusEnum](#schemacrawlpagestatusenum)|false|none|* `pending` - Pending<br>* `processing` - Processing<br>* `done` - Done<br>* `cancelled` - Cancelled|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|pending|
|*anonymous*|processing|
|*anonymous*|done|
|*anonymous*|cancelled|

<h2 id="tocS_CustomizedRegister">CustomizedRegister</h2>
<!-- backwards compatibility -->
<a id="schemacustomizedregister"></a>
<a id="schema_CustomizedRegister"></a>
<a id="tocScustomizedregister"></a>
<a id="tocscustomizedregister"></a>

```json
{
  "type": "object",
  "description": "透過 get_cleaned_data() 取得表單資料後，\n傳入 AccountAdapter.save_user() 處理自訂欄位並建立使用者。",
  "properties": {
    "username": {
      "type": "string",
      "maxLength": 0,
      "minLength": 1
    },
    "email": {
      "type": "string",
      "format": "email"
    },
    "password1": {
      "type": "string",
      "writeOnly": true
    },
    "password2": {
      "type": "string",
      "writeOnly": true
    },
    "name": {
      "type": "string"
    },
    "company": {
      "type": "string"
    },
    "referralCode": {
      "type": "string"
    }
  },
  "required": [
    "company",
    "email",
    "name",
    "password1",
    "password2",
    "referralCode"
  ]
}

```

透過 get_cleaned_data() 取得表單資料後，
傳入 AccountAdapter.save_user() 處理自訂欄位並建立使用者。

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|false|none|none|
|email|string(email)|true|none|none|
|password1|string|true|write-only|none|
|password2|string|true|write-only|none|
|name|string|true|none|none|
|company|string|true|none|none|
|referralCode|string|true|none|none|

<h2 id="tocS_EmbeddingModel">EmbeddingModel</h2>
<!-- backwards compatibility -->
<a id="schemaembeddingmodel"></a>
<a id="schema_EmbeddingModel"></a>
<a id="tocSembeddingmodel"></a>
<a id="tocsembeddingmodel"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "isDefault": {
      "type": "boolean",
      "title": "是否預設"
    }
  },
  "required": [
    "id",
    "name"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|isDefault|boolean|false|none|none|

<h2 id="tocS_FacebookPage">FacebookPage</h2>
<!-- backwards compatibility -->
<a id="schemafacebookpage"></a>
<a id="schema_FacebookPage"></a>
<a id="tocSfacebookpage"></a>
<a id="tocsfacebookpage"></a>

```json
{
  "type": "object",
  "properties": {
    "pageId": {
      "type": "string",
      "maxLength": 256
    },
    "name": {
      "type": "string",
      "maxLength": 256
    }
  },
  "required": [
    "name",
    "pageId"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pageId|string|true|none|none|
|name|string|true|none|none|

<h2 id="tocS_FacebookSystemUser">FacebookSystemUser</h2>
<!-- backwards compatibility -->
<a id="schemafacebooksystemuser"></a>
<a id="schema_FacebookSystemUser"></a>
<a id="tocSfacebooksystemuser"></a>
<a id="tocsfacebooksystemuser"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "systemUserId": {
      "type": "string",
      "readOnly": true
    }
  },
  "required": [
    "id",
    "systemUserId"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|systemUserId|string|true|read-only|none|

<h2 id="tocS_FacebookSystemUserCreate">FacebookSystemUserCreate</h2>
<!-- backwards compatibility -->
<a id="schemafacebooksystemusercreate"></a>
<a id="schema_FacebookSystemUserCreate"></a>
<a id="tocSfacebooksystemusercreate"></a>
<a id="tocsfacebooksystemusercreate"></a>

```json
{
  "type": "object",
  "properties": {
    "code": {
      "type": "string",
      "maxLength": 500
    }
  },
  "required": [
    "code"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|true|none|none|

<h2 id="tocS_Faq">Faq</h2>
<!-- backwards compatibility -->
<a id="schemafaq"></a>
<a id="schema_Faq"></a>
<a id="tocSfaq"></a>
<a id="tocsfaq"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "question": {
      "type": "string",
      "title": "問題"
    },
    "answer": {
      "type": "string",
      "title": "答案"
    },
    "hitsCount": {
      "type": "integer",
      "readOnly": true,
      "title": "命中次數"
    }
  },
  "required": [
    "answer",
    "hitsCount",
    "id",
    "question"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|question|string|true|none|none|
|answer|string|true|none|none|
|hitsCount|integer|true|read-only|none|

<h2 id="tocS_FaqCreate">FaqCreate</h2>
<!-- backwards compatibility -->
<a id="schemafaqcreate"></a>
<a id="schema_FaqCreate"></a>
<a id="tocSfaqcreate"></a>
<a id="tocsfaqcreate"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "chatbot": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "question": {
      "type": "string",
      "title": "問題"
    },
    "answer": {
      "type": "string",
      "title": "答案"
    }
  },
  "required": [
    "answer",
    "chatbot",
    "id",
    "question"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|chatbot|string(uuid)|true|read-only|none|
|question|string|true|none|none|
|answer|string|true|none|none|

<h2 id="tocS_FeedbackEnum">FeedbackEnum</h2>
<!-- backwards compatibility -->
<a id="schemafeedbackenum"></a>
<a id="schema_FeedbackEnum"></a>
<a id="tocSfeedbackenum"></a>
<a id="tocsfeedbackenum"></a>

```json
{
  "enum": [
    "like",
    "dislike"
  ],
  "type": "string",
  "description": "* `like` - Like\n* `dislike` - Dislike"
}

```

* `like` - Like
* `dislike` - Dislike

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[FeedbackEnum](#schemafeedbackenum)|false|none|* `like` - Like<br>* `dislike` - Dislike|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|like|
|*anonymous*|dislike|

<h2 id="tocS_Group">Group</h2>
<!-- backwards compatibility -->
<a id="schemagroup"></a>
<a id="schema_Group"></a>
<a id="tocSgroup"></a>
<a id="tocsgroup"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "permissions": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "name": {
            "type": "string",
            "title": "名稱",
            "maxLength": 255
          },
          "description": {
            "type": "string",
            "title": "描述"
          }
        },
        "required": [
          "id",
          "name"
        ]
      }
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "createdAt",
    "id",
    "name",
    "permissions"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|permissions|[[Permission](#schemapermission)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» description|string|false|none|none|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_GroupChatbot">GroupChatbot</h2>
<!-- backwards compatibility -->
<a id="schemagroupchatbot"></a>
<a id="schema_GroupChatbot"></a>
<a id="tocSgroupchatbot"></a>
<a id="tocsgroupchatbot"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "group": {
      "type": "string",
      "format": "uuid"
    },
    "chatbot": {
      "type": "object",
      "description": "Adds nested create feature",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "workflow": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "name": {
          "type": "string",
          "title": "名稱",
          "maxLength": 255
        },
        "largeLanguageModel": {
          "type": "string",
          "format": "uuid"
        },
        "rag": {
          "type": "string",
          "format": "uuid"
        },
        "embeddingModel": {
          "type": "string",
          "format": "uuid",
          "nullable": true
        },
        "rerankerModel": {
          "type": "string",
          "format": "uuid",
          "nullable": true
        },
        "instructions": {
          "type": "string",
          "title": "指令"
        },
        "webhookUrl": {
          "type": "string",
          "format": "uri",
          "nullable": true,
          "maxLength": 511
        },
        "apiWebChatId": {
          "type": "string",
          "readOnly": true,
          "nullable": true,
          "title": "API WebChat ID"
        },
        "updatedAt": {
          "type": "string",
          "format": "timestamp",
          "readOnly": true,
          "title": "更新時間",
          "pattern": "^\\d{13}$"
        },
        "organization": {
          "type": "string",
          "format": "uuid"
        },
        "builtInWorkflow": {
          "type": "string",
          "format": "uuid",
          "nullable": true
        },
        "replyMode": {
          "allOf": [
            {
              "enum": [
                "normal",
                "template",
                "hybrid"
              ],
              "type": "string",
              "description": "* `normal` - 正常\n* `template` - 模板\n* `hybrid` - 混合"
            }
          ],
          "title": "回傳模式"
        },
        "template": {
          "type": "string",
          "nullable": true,
          "title": "模板"
        },
        "unanswerableTemplate": {
          "type": "string",
          "nullable": true,
          "title": "無法回答時的模板"
        },
        "totalLlmWordCount": {
          "type": "integer",
          "maximum": 9223372036854776000,
          "minimum": -9223372036854776000,
          "format": "int64",
          "title": "LLM 使用總字數",
          "description": "累積的 LLM 使用總字數"
        },
        "enableChineseConversion": {
          "type": "boolean"
        },
        "outputFormat": {
          "nullable": true
        }
      },
      "required": [
        "apiWebChatId",
        "id",
        "largeLanguageModel",
        "name",
        "rag",
        "updatedAt",
        "workflow"
      ]
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "chatbot",
    "createdAt",
    "group",
    "id"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|group|string(uuid)|true|none|none|
|chatbot|[Chatbot](#schemachatbot)|true|none|Adds nested create feature|
|» id|string(uuid)|true|read-only|none|
|» workflow|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» largeLanguageModel|string(uuid)|true|none|none|
|» rag|string(uuid)|true|none|none|
|» embeddingModel|string(uuid)¦null|false|none|none|
|» rerankerModel|string(uuid)¦null|false|none|none|
|» instructions|string|false|none|none|
|» webhookUrl|string(uri)¦null|false|none|none|
|» apiWebChatId|string¦null|true|read-only|none|
|» updatedAt|string(timestamp)|true|read-only|none|
|» organization|string(uuid)|false|none|none|
|» builtInWorkflow|string(uuid)¦null|false|none|none|
|» replyMode|[ReplyModeEnum](#schemareplymodeenum)|false|none|* `normal` - 正常<br>* `template` - 模板<br>* `hybrid` - 混合|
|» template|string¦null|false|none|none|
|» unanswerableTemplate|string¦null|false|none|none|
|» totalLlmWordCount|integer(int64)|false|none|累積的 LLM 使用總字數|
|» enableChineseConversion|boolean|false|none|none|
|» outputFormat|any|false|none|none|
|createdAt|string(timestamp)|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|replyMode|normal|
|replyMode|template|
|replyMode|hybrid|

<h2 id="tocS_GroupChatbotCreate">GroupChatbotCreate</h2>
<!-- backwards compatibility -->
<a id="schemagroupchatbotcreate"></a>
<a id="schema_GroupChatbotCreate"></a>
<a id="tocSgroupchatbotcreate"></a>
<a id="tocsgroupchatbotcreate"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "group": {
      "type": "string",
      "format": "uuid"
    },
    "chatbot": {
      "type": "string",
      "format": "uuid"
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "chatbot",
    "createdAt",
    "id"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|group|string(uuid)|false|none|none|
|chatbot|string(uuid)|true|none|none|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_GroupCreate">GroupCreate</h2>
<!-- backwards compatibility -->
<a id="schemagroupcreate"></a>
<a id="schema_GroupCreate"></a>
<a id="tocSgroupcreate"></a>
<a id="tocsgroupcreate"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "organization": {
      "type": "string",
      "format": "uuid"
    },
    "permissions": {
      "type": "array",
      "items": {
        "type": "string",
        "format": "uuid"
      }
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "createdAt",
    "id",
    "name",
    "permissions"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|organization|string(uuid)|false|none|none|
|permissions|[string]|true|none|none|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_GroupMember">GroupMember</h2>
<!-- backwards compatibility -->
<a id="schemagroupmember"></a>
<a id="schema_GroupMember"></a>
<a id="tocSgroupmember"></a>
<a id="tocsgroupmember"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "member": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "name": {
          "type": "string",
          "readOnly": true
        },
        "organization": {
          "type": "object",
          "properties": {
            "id": {
              "type": "string",
              "format": "uuid",
              "readOnly": true
            },
            "name": {
              "type": "string",
              "title": "名稱",
              "maxLength": 255
            },
            "owner": {
              "allOf": [
                {
                  "type": "object",
                  "properties": {
                    "id": {
                      "type": "string",
                      "format": "uuid",
                      "readOnly": true
                    },
                    "name": {
                      "type": "string",
                      "title": "真實姓名",
                      "maxLength": 255
                    }
                  },
                  "required": [
                    "id",
                    "name"
                  ]
                }
              ],
              "readOnly": true
            },
            "createdAt": {
              "type": "string",
              "format": "timestamp",
              "readOnly": true,
              "title": "建立時間",
              "pattern": "^\\d{13}$"
            },
            "usageStatistics": {
              "type": "string",
              "readOnly": true
            }
          },
          "required": [
            "createdAt",
            "id",
            "name",
            "owner",
            "usageStatistics"
          ]
        },
        "isOwner": {
          "type": "string",
          "readOnly": true
        },
        "permissions": {
          "type": "string",
          "readOnly": true
        },
        "createdAt": {
          "type": "string",
          "format": "timestamp",
          "readOnly": true,
          "title": "建立時間",
          "pattern": "^\\d{13}$"
        }
      },
      "required": [
        "createdAt",
        "id",
        "isOwner",
        "name",
        "organization",
        "permissions"
      ]
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "createdAt",
    "id",
    "member"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|member|[Member](#schemamember)|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|read-only|none|
|» organization|[Organization](#schemaorganization)|true|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» name|string|true|none|none|
|»» owner|[UserBase](#schemauserbase)|true|read-only|none|
|»»» id|string(uuid)|true|read-only|none|
|»»» name|string|true|none|none|
|»» createdAt|string(timestamp)|true|read-only|none|
|»» usageStatistics|string|true|read-only|none|
|» isOwner|string|true|read-only|none|
|» permissions|string|true|read-only|none|
|» createdAt|string(timestamp)|true|read-only|none|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_GroupMemberCreate">GroupMemberCreate</h2>
<!-- backwards compatibility -->
<a id="schemagroupmembercreate"></a>
<a id="schema_GroupMemberCreate"></a>
<a id="tocSgroupmembercreate"></a>
<a id="tocsgroupmembercreate"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "group": {
      "type": "string",
      "format": "uuid"
    },
    "member": {
      "type": "string",
      "format": "uuid"
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "createdAt",
    "id",
    "member"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|group|string(uuid)|false|none|none|
|member|string(uuid)|true|none|none|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_Inbox">Inbox</h2>
<!-- backwards compatibility -->
<a id="schemainbox"></a>
<a id="schema_Inbox"></a>
<a id="tocSinbox"></a>
<a id="tocsinbox"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "channelType": {
      "allOf": [
        {
          "enum": [
            "line",
            "telegram",
            "web",
            "messenger"
          ],
          "type": "string",
          "description": "* `line` - LINE\n* `telegram` - Telegram\n* `web` - Web\n* `messenger` - Messenger"
        }
      ],
      "title": "頻道類型"
    },
    "unreadConversationsCount": {
      "type": "integer",
      "maximum": 2147483647,
      "minimum": -2147483648,
      "title": "未讀對話數量"
    }
  },
  "required": [
    "channelType",
    "id",
    "name"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|channelType|[ChannelTypeEnum](#schemachanneltypeenum)|true|none|* `line` - LINE<br>* `telegram` - Telegram<br>* `web` - Web<br>* `messenger` - Messenger|
|unreadConversationsCount|integer|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|channelType|line|
|channelType|telegram|
|channelType|web|
|channelType|messenger|

<h2 id="tocS_JWT">JWT</h2>
<!-- backwards compatibility -->
<a id="schemajwt"></a>
<a id="schema_JWT"></a>
<a id="tocSjwt"></a>
<a id="tocsjwt"></a>

```json
{
  "type": "object",
  "description": "Serializer for JWT authentication.",
  "properties": {
    "access": {
      "type": "string"
    },
    "refresh": {
      "type": "string"
    },
    "user": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "avatar": {
          "type": "string",
          "format": "uri",
          "title": "大頭貼"
        },
        "name": {
          "type": "string",
          "title": "真實姓名",
          "maxLength": 255
        },
        "email": {
          "type": "string",
          "format": "email",
          "title": "公司信箱",
          "maxLength": 254
        },
        "company": {
          "type": "string",
          "title": "公司名稱",
          "maxLength": 255
        },
        "invitationCode": {
          "type": "string",
          "title": "邀請碼",
          "pattern": "^[A-Z0-9]+$",
          "maxLength": 31
        },
        "apiKeys": {
          "type": "string",
          "readOnly": true
        },
        "permissions": {
          "type": "string",
          "readOnly": true
        }
      },
      "required": [
        "apiKeys",
        "email",
        "id",
        "invitationCode",
        "name",
        "permissions"
      ]
    }
  },
  "required": [
    "access",
    "refresh",
    "user"
  ]
}

```

Serializer for JWT authentication.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|access|string|true|none|none|
|refresh|string|true|none|none|
|user|[User](#schemauser)|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» avatar|string(uri)|false|none|none|
|» name|string|true|none|none|
|» email|string(email)|true|none|none|
|» company|string|false|none|none|
|» invitationCode|string|true|none|none|
|» apiKeys|string|true|read-only|none|
|» permissions|string|true|read-only|none|

<h2 id="tocS_LargeLanguageModel">LargeLanguageModel</h2>
<!-- backwards compatibility -->
<a id="schemalargelanguagemodel"></a>
<a id="schema_LargeLanguageModel"></a>
<a id="tocSlargelanguagemodel"></a>
<a id="tocslargelanguagemodel"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "isDefault": {
      "type": "boolean",
      "title": "是否預設"
    }
  },
  "required": [
    "id",
    "name"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|isDefault|boolean|false|none|none|

<h2 id="tocS_LineChannel">LineChannel</h2>
<!-- backwards compatibility -->
<a id="schemalinechannel"></a>
<a id="schema_LineChannel"></a>
<a id="tocSlinechannel"></a>
<a id="tocslinechannel"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "channelId": {
      "type": "string"
    },
    "channelSecret": {
      "type": "string"
    },
    "channelAccessToken": {
      "type": "string"
    },
    "webhookUrl": {
      "type": "string",
      "readOnly": true
    },
    "enableGroupMention": {
      "type": "boolean"
    }
  },
  "required": [
    "channelAccessToken",
    "channelId",
    "channelSecret",
    "id",
    "webhookUrl"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|channelId|string|true|none|none|
|channelSecret|string|true|none|none|
|channelAccessToken|string|true|none|none|
|webhookUrl|string|true|read-only|none|
|enableGroupMention|boolean|false|none|none|

<h2 id="tocS_Login">Login</h2>
<!-- backwards compatibility -->
<a id="schemalogin"></a>
<a id="schema_Login"></a>
<a id="tocSlogin"></a>
<a id="tocslogin"></a>

```json
{
  "type": "object",
  "properties": {
    "username": {
      "type": "string"
    },
    "email": {
      "type": "string",
      "format": "email"
    },
    "password": {
      "type": "string"
    }
  },
  "required": [
    "password"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|false|none|none|
|email|string(email)|false|none|none|
|password|string|true|none|none|

<h2 id="tocS_Member">Member</h2>
<!-- backwards compatibility -->
<a id="schemamember"></a>
<a id="schema_Member"></a>
<a id="tocSmember"></a>
<a id="tocsmember"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "readOnly": true
    },
    "organization": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "name": {
          "type": "string",
          "title": "名稱",
          "maxLength": 255
        },
        "owner": {
          "allOf": [
            {
              "type": "object",
              "properties": {
                "id": {
                  "type": "string",
                  "format": "uuid",
                  "readOnly": true
                },
                "name": {
                  "type": "string",
                  "title": "真實姓名",
                  "maxLength": 255
                }
              },
              "required": [
                "id",
                "name"
              ]
            }
          ],
          "readOnly": true
        },
        "createdAt": {
          "type": "string",
          "format": "timestamp",
          "readOnly": true,
          "title": "建立時間",
          "pattern": "^\\d{13}$"
        },
        "usageStatistics": {
          "type": "string",
          "readOnly": true
        }
      },
      "required": [
        "createdAt",
        "id",
        "name",
        "owner",
        "usageStatistics"
      ]
    },
    "isOwner": {
      "type": "string",
      "readOnly": true
    },
    "permissions": {
      "type": "string",
      "readOnly": true
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "createdAt",
    "id",
    "isOwner",
    "name",
    "organization",
    "permissions"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|read-only|none|
|organization|[Organization](#schemaorganization)|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» owner|[UserBase](#schemauserbase)|true|read-only|none|
|»» id|string(uuid)|true|read-only|none|
|»» name|string|true|none|none|
|» createdAt|string(timestamp)|true|read-only|none|
|» usageStatistics|string|true|read-only|none|
|isOwner|string|true|read-only|none|
|permissions|string|true|read-only|none|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_MemberCreate">MemberCreate</h2>
<!-- backwards compatibility -->
<a id="schemamembercreate"></a>
<a id="schema_MemberCreate"></a>
<a id="tocSmembercreate"></a>
<a id="tocsmembercreate"></a>

```json
{
  "type": "object",
  "properties": {
    "email": {
      "type": "string",
      "format": "email",
      "writeOnly": true
    },
    "organization": {
      "type": "string",
      "format": "uuid"
    },
    "isOwner": {
      "type": "string",
      "readOnly": true
    }
  },
  "required": [
    "email",
    "isOwner"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|email|string(email)|true|write-only|none|
|organization|string(uuid)|false|none|none|
|isOwner|string|true|read-only|none|

<h2 id="tocS_Message">Message</h2>
<!-- backwards compatibility -->
<a id="schemamessage"></a>
<a id="schema_Message"></a>
<a id="tocSmessage"></a>
<a id="tocsmessage"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "conversation": {
      "type": "string",
      "format": "uuid",
      "title": "對話"
    },
    "sender": {
      "type": "object",
      "properties": {
        "id": {
          "type": "integer"
        },
        "name": {
          "type": "string"
        },
        "avatar": {
          "type": "string",
          "format": "uri"
        }
      },
      "required": [
        "avatar",
        "id",
        "name"
      ]
    },
    "type": {
      "type": "string",
      "default": "incoming"
    },
    "content": {
      "type": "string",
      "title": "內容"
    },
    "feedback": {
      "nullable": true,
      "title": "回饋",
      "oneOf": [
        {
          "enum": [
            "like",
            "dislike"
          ],
          "type": "string",
          "description": "* `like` - Like\n* `dislike` - Dislike"
        },
        {
          "enum": [
            ""
          ]
        },
        {
          "enum": [
            null
          ]
        }
      ]
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    },
    "attachments": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "type": {
            "allOf": [
              {
                "enum": [
                  "image",
                  "video",
                  "audio",
                  "sticker",
                  "other"
                ],
                "type": "string",
                "description": "* `image` - Image\n* `video` - Video\n* `audio` - Audio\n* `sticker` - Sticker\n* `other` - Other"
              }
            ],
            "default": "other"
          },
          "filename": {
            "type": "string"
          },
          "file": {
            "type": "string",
            "format": "uri"
          }
        },
        "required": [
          "file",
          "filename",
          "id"
        ]
      }
    },
    "citations": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "filename": {
            "type": "string"
          },
          "file": {
            "type": "string",
            "format": "uri"
          },
          "fileType": {
            "type": "string",
            "readOnly": true,
            "title": "檔案類型"
          },
          "size": {
            "type": "integer",
            "readOnly": true,
            "title": "檔案大小"
          },
          "status": {
            "allOf": [
              {
                "enum": [
                  "initial",
                  "processing",
                  "done",
                  "deleting",
                  "failed"
                ],
                "type": "string",
                "description": "* `initial` - Initial\n* `processing` - Processing\n* `done` - Done\n* `deleting` - Deleting\n* `failed` - Failed"
              }
            ],
            "readOnly": true,
            "title": "狀態"
          },
          "chatbotFileContent": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "parser": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "name": {
                "type": "string",
                "maxLength": 255
              },
              "provider": {
                "enum": [
                  "maiagent",
                  "llama",
                  "azure"
                ],
                "type": "string",
                "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
              },
              "priority": {
                "type": "integer",
                "readOnly": true
              }
            },
            "required": [
              "id",
              "name",
              "priority",
              "provider"
            ]
          },
          "createdAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "建立時間",
            "pattern": "^\\d{13}$"
          }
        },
        "required": [
          "chatbotFileContent",
          "createdAt",
          "file",
          "fileType",
          "filename",
          "id",
          "parser",
          "size",
          "status"
        ]
      },
      "readOnly": true
    },
    "citationNodes": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "chatbotTextNode": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "charactersCount": {
                "type": "integer",
                "readOnly": true,
                "title": "字元數量"
              },
              "hitsCount": {
                "type": "integer",
                "readOnly": true,
                "title": "命中次數"
              },
              "text": {
                "type": "string",
                "readOnly": true,
                "title": "文字"
              },
              "updatedAt": {
                "type": "string",
                "format": "timestamp",
                "readOnly": true,
                "title": "更新時間",
                "pattern": "^\\d{13}$"
              },
              "filename": {
                "type": "string",
                "readOnly": true
              }
            },
            "required": [
              "charactersCount",
              "filename",
              "hitsCount",
              "id",
              "text",
              "updatedAt"
            ]
          },
          "score": {
            "type": "number",
            "format": "double"
          },
          "displayScore": {
            "type": "string",
            "readOnly": true
          }
        },
        "required": [
          "chatbotTextNode",
          "displayScore"
        ]
      },
      "readOnly": true
    }
  },
  "required": [
    "citationNodes",
    "citations",
    "conversation",
    "createdAt",
    "id"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|conversation|string(uuid)|true|none|none|
|sender|[Sender](#schemasender)|false|none|none|
|» id|integer|true|none|none|
|» name|string|true|none|none|
|» avatar|string(uri)|true|none|none|
|type|string|false|none|none|
|content|string|false|none|none|
|feedback|any|false|none|none|

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[FeedbackEnum](#schemafeedbackenum)|false|none|* `like` - Like<br>* `dislike` - Dislike|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|createdAt|string(timestamp)|true|read-only|none|
|attachments|[[Attachment](#schemaattachment)]|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» type|[TypeEnum](#schematypeenum)|false|none|* `image` - Image<br>* `video` - Video<br>* `audio` - Audio<br>* `sticker` - Sticker<br>* `other` - Other|
|» filename|string|true|none|none|
|» file|string(uri)|true|none|none|
|citations|[[ChatbotFile](#schemachatbotfile)]|true|read-only|none|
|» id|string(uuid)|true|read-only|none|
|» filename|string|true|none|none|
|» file|string(uri)|true|none|none|
|» fileType|string|true|read-only|none|
|» size|integer|true|read-only|none|
|» status|[StatusBbcEnum](#schemastatusbbcenum)|true|read-only|* `initial` - Initial<br>* `processing` - Processing<br>* `done` - Done<br>* `deleting` - Deleting<br>* `failed` - Failed|
|» chatbotFileContent|string(uuid)|true|read-only|none|
|» parser|[Parser](#schemaparser)|true|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» name|string|true|none|none|
|»» provider|[ProviderEnum](#schemaproviderenum)|true|none|* `maiagent` - MaiAgent<br>* `llama` - Llama<br>* `azure` - Azure|
|»» priority|integer|true|read-only|none|
|» createdAt|string(timestamp)|true|read-only|none|
|citationNodes|[[CitationNode](#schemacitationnode)]|true|read-only|none|
|» chatbotTextNode|[ChatbotTextNode](#schemachatbottextnode)|true|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» charactersCount|integer|true|read-only|none|
|»» hitsCount|integer|true|read-only|none|
|»» text|string|true|read-only|none|
|»» updatedAt|string(timestamp)|true|read-only|none|
|»» filename|string|true|read-only|none|
|» score|number(double)|false|none|none|
|» displayScore|string|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|like|
|*anonymous*|dislike|
|*anonymous*||
|*anonymous*|null|
|type|image|
|type|video|
|type|audio|
|type|sticker|
|type|other|
|status|initial|
|status|processing|
|status|done|
|status|deleting|
|status|failed|
|provider|maiagent|
|provider|llama|
|provider|azure|

<h2 id="tocS_Messenger">Messenger</h2>
<!-- backwards compatibility -->
<a id="schemamessenger"></a>
<a id="schema_Messenger"></a>
<a id="tocSmessenger"></a>
<a id="tocsmessenger"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "pageId": {
      "type": "string",
      "maxLength": 255
    },
    "pageName": {
      "type": "string",
      "readOnly": true
    },
    "facebookSystemUserId": {
      "type": "string",
      "format": "uuid",
      "writeOnly": true
    }
  },
  "required": [
    "facebookSystemUserId",
    "id",
    "pageId",
    "pageName"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|pageId|string|true|none|none|
|pageName|string|true|read-only|none|
|facebookSystemUserId|string(uuid)|true|write-only|none|

<h2 id="tocS_NullEnum">NullEnum</h2>
<!-- backwards compatibility -->
<a id="schemanullenum"></a>
<a id="schema_NullEnum"></a>
<a id="tocSnullenum"></a>
<a id="tocsnullenum"></a>

```json
{
  "enum": [
    null
  ]
}

```

### Properties

*None*

<h2 id="tocS_Organization">Organization</h2>
<!-- backwards compatibility -->
<a id="schemaorganization"></a>
<a id="schema_Organization"></a>
<a id="tocSorganization"></a>
<a id="tocsorganization"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "owner": {
      "allOf": [
        {
          "type": "object",
          "properties": {
            "id": {
              "type": "string",
              "format": "uuid",
              "readOnly": true
            },
            "name": {
              "type": "string",
              "title": "真實姓名",
              "maxLength": 255
            }
          },
          "required": [
            "id",
            "name"
          ]
        }
      ],
      "readOnly": true
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    },
    "usageStatistics": {
      "type": "string",
      "readOnly": true
    }
  },
  "required": [
    "createdAt",
    "id",
    "name",
    "owner",
    "usageStatistics"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|owner|[UserBase](#schemauserbase)|true|read-only|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|createdAt|string(timestamp)|true|read-only|none|
|usageStatistics|string|true|read-only|none|

<h2 id="tocS_OrganizationList">OrganizationList</h2>
<!-- backwards compatibility -->
<a id="schemaorganizationlist"></a>
<a id="schema_OrganizationList"></a>
<a id="tocSorganizationlist"></a>
<a id="tocsorganizationlist"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "owner": {
      "allOf": [
        {
          "type": "object",
          "properties": {
            "id": {
              "type": "string",
              "format": "uuid",
              "readOnly": true
            },
            "name": {
              "type": "string",
              "title": "真實姓名",
              "maxLength": 255
            }
          },
          "required": [
            "id",
            "name"
          ]
        }
      ],
      "readOnly": true
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "createdAt",
    "id",
    "name",
    "owner"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|owner|[UserBase](#schemauserbase)|true|read-only|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_PaginatedAttachmentList">PaginatedAttachmentList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedattachmentlist"></a>
<a id="schema_PaginatedAttachmentList"></a>
<a id="tocSpaginatedattachmentlist"></a>
<a id="tocspaginatedattachmentlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "type": {
            "allOf": [
              {
                "enum": [
                  "image",
                  "video",
                  "audio",
                  "sticker",
                  "other"
                ],
                "type": "string",
                "description": "* `image` - Image\n* `video` - Video\n* `audio` - Audio\n* `sticker` - Sticker\n* `other` - Other"
              }
            ],
            "default": "other"
          },
          "filename": {
            "type": "string"
          },
          "file": {
            "type": "string",
            "format": "uri"
          }
        },
        "required": [
          "file",
          "filename",
          "id"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Attachment](#schemaattachment)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» type|[TypeEnum](#schematypeenum)|false|none|* `image` - Image<br>* `video` - Video<br>* `audio` - Audio<br>* `sticker` - Sticker<br>* `other` - Other|
|» filename|string|true|none|none|
|» file|string(uri)|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|image|
|type|video|
|type|audio|
|type|sticker|
|type|other|

<h2 id="tocS_PaginatedChatbotFileList">PaginatedChatbotFileList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedchatbotfilelist"></a>
<a id="schema_PaginatedChatbotFileList"></a>
<a id="tocSpaginatedchatbotfilelist"></a>
<a id="tocspaginatedchatbotfilelist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "filename": {
            "type": "string"
          },
          "file": {
            "type": "string",
            "format": "uri"
          },
          "fileType": {
            "type": "string",
            "readOnly": true,
            "title": "檔案類型"
          },
          "size": {
            "type": "integer",
            "readOnly": true,
            "title": "檔案大小"
          },
          "status": {
            "allOf": [
              {
                "enum": [
                  "initial",
                  "processing",
                  "done",
                  "deleting",
                  "failed"
                ],
                "type": "string",
                "description": "* `initial` - Initial\n* `processing` - Processing\n* `done` - Done\n* `deleting` - Deleting\n* `failed` - Failed"
              }
            ],
            "readOnly": true,
            "title": "狀態"
          },
          "chatbotFileContent": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "parser": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "name": {
                "type": "string",
                "maxLength": 255
              },
              "provider": {
                "enum": [
                  "maiagent",
                  "llama",
                  "azure"
                ],
                "type": "string",
                "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
              },
              "priority": {
                "type": "integer",
                "readOnly": true
              }
            },
            "required": [
              "id",
              "name",
              "priority",
              "provider"
            ]
          },
          "createdAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "建立時間",
            "pattern": "^\\d{13}$"
          }
        },
        "required": [
          "chatbotFileContent",
          "createdAt",
          "file",
          "fileType",
          "filename",
          "id",
          "parser",
          "size",
          "status"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[ChatbotFile](#schemachatbotfile)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» filename|string|true|none|none|
|» file|string(uri)|true|none|none|
|» fileType|string|true|read-only|none|
|» size|integer|true|read-only|none|
|» status|[StatusBbcEnum](#schemastatusbbcenum)|true|read-only|* `initial` - Initial<br>* `processing` - Processing<br>* `done` - Done<br>* `deleting` - Deleting<br>* `failed` - Failed|
|» chatbotFileContent|string(uuid)|true|read-only|none|
|» parser|[Parser](#schemaparser)|true|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» name|string|true|none|none|
|»» provider|[ProviderEnum](#schemaproviderenum)|true|none|* `maiagent` - MaiAgent<br>* `llama` - Llama<br>* `azure` - Azure|
|»» priority|integer|true|read-only|none|
|» createdAt|string(timestamp)|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|initial|
|status|processing|
|status|done|
|status|deleting|
|status|failed|
|provider|maiagent|
|provider|llama|
|provider|azure|

<h2 id="tocS_PaginatedChatbotInstructionRecordList">PaginatedChatbotInstructionRecordList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedchatbotinstructionrecordlist"></a>
<a id="schema_PaginatedChatbotInstructionRecordList"></a>
<a id="tocSpaginatedchatbotinstructionrecordlist"></a>
<a id="tocspaginatedchatbotinstructionrecordlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "instructions": {
            "type": "string",
            "nullable": true,
            "title": "指令"
          },
          "operatorName": {
            "type": "string",
            "readOnly": true
          },
          "createdAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "建立時間",
            "pattern": "^\\d{13}$"
          }
        },
        "required": [
          "createdAt",
          "id",
          "operatorName"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[ChatbotInstructionRecord](#schemachatbotinstructionrecord)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» instructions|string¦null|false|none|none|
|» operatorName|string|true|read-only|none|
|» createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_PaginatedChatbotListList">PaginatedChatbotListList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedchatbotlistlist"></a>
<a id="schema_PaginatedChatbotListList"></a>
<a id="tocSpaginatedchatbotlistlist"></a>
<a id="tocspaginatedchatbotlistlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "name": {
            "type": "string",
            "title": "名稱",
            "maxLength": 255
          },
          "largeLanguageModel": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "name": {
                "type": "string",
                "title": "名稱",
                "maxLength": 255
              },
              "isDefault": {
                "type": "boolean",
                "title": "是否預設"
              }
            },
            "required": [
              "id",
              "name"
            ]
          },
          "rag": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "name": {
                "type": "string",
                "title": "名稱",
                "maxLength": 255
              },
              "isDefault": {
                "type": "boolean",
                "title": "是否預設"
              },
              "isEmbeddingModelSelectable": {
                "type": "string",
                "readOnly": true
              },
              "isRerankerModelSelectable": {
                "type": "string",
                "readOnly": true
              },
              "isOutputFormatAvailable": {
                "type": "string",
                "readOnly": true
              }
            },
            "required": [
              "id",
              "isEmbeddingModelSelectable",
              "isOutputFormatAvailable",
              "isRerankerModelSelectable",
              "name"
            ]
          },
          "embeddingModel": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "name": {
                "type": "string",
                "title": "名稱",
                "maxLength": 255
              },
              "isDefault": {
                "type": "boolean",
                "title": "是否預設"
              }
            },
            "required": [
              "id",
              "name"
            ]
          },
          "rerankerModel": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "name": {
                "type": "string",
                "title": "名稱",
                "maxLength": 255
              },
              "isDefault": {
                "type": "boolean",
                "title": "是否預設"
              }
            },
            "required": [
              "id",
              "name"
            ]
          },
          "updatedAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "更新時間",
            "pattern": "^\\d{13}$"
          },
          "enableChineseConversion": {
            "type": "boolean",
            "title": "啟用繁體中文轉換"
          }
        },
        "required": [
          "embeddingModel",
          "id",
          "largeLanguageModel",
          "name",
          "rag",
          "rerankerModel",
          "updatedAt"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[ChatbotList](#schemachatbotlist)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» largeLanguageModel|[LargeLanguageModel](#schemalargelanguagemodel)|true|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» name|string|true|none|none|
|»» isDefault|boolean|false|none|none|
|» rag|[Rag](#schemarag)|true|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» name|string|true|none|none|
|»» isDefault|boolean|false|none|none|
|»» isEmbeddingModelSelectable|string|true|read-only|none|
|»» isRerankerModelSelectable|string|true|read-only|none|
|»» isOutputFormatAvailable|string|true|read-only|none|
|» embeddingModel|[EmbeddingModel](#schemaembeddingmodel)|true|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» name|string|true|none|none|
|»» isDefault|boolean|false|none|none|
|» rerankerModel|[RerankerModel](#schemarerankermodel)|true|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» name|string|true|none|none|
|»» isDefault|boolean|false|none|none|
|» updatedAt|string(timestamp)|true|read-only|none|
|» enableChineseConversion|boolean|false|none|none|

<h2 id="tocS_PaginatedChatbotRecordList">PaginatedChatbotRecordList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedchatbotrecordlist"></a>
<a id="schema_PaginatedChatbotRecordList"></a>
<a id="tocSpaginatedchatbotrecordlist"></a>
<a id="tocspaginatedchatbotrecordlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "inputMessage": {
            "type": "string",
            "readOnly": true
          },
          "condenseMessage": {
            "type": "string",
            "readOnly": true,
            "title": "Chatbot 修飾輸入訊息",
            "description": "綜合聊天歷史與上下文後，修飾過後的使用者訊息"
          },
          "outputMessage": {
            "type": "string",
            "readOnly": true
          },
          "context": {
            "type": "string",
            "readOnly": true,
            "nullable": true,
            "title": "參考資料"
          },
          "faithfulnessScore": {
            "type": "number",
            "format": "double",
            "readOnly": true,
            "nullable": true,
            "title": "誠實性評分",
            "description": "判斷chatbot回覆是否符合資料庫內容，是否憑空想像"
          },
          "displayFaithfulnessScore": {
            "type": "string",
            "readOnly": true
          },
          "answerRelevancyScore": {
            "type": "number",
            "format": "double",
            "readOnly": true,
            "nullable": true,
            "title": "回答相關性評分",
            "description": "判斷chatbot回覆是否與使用者問題相關"
          },
          "displayAnswerRelevancyScore": {
            "type": "string",
            "readOnly": true
          },
          "contextPrecisionScore": {
            "type": "number",
            "format": "double",
            "readOnly": true,
            "nullable": true,
            "title": "參考資料相關性評分",
            "description": "判斷chatbot回覆是否與參考資料相關"
          },
          "displayContextPrecisionScore": {
            "type": "string",
            "readOnly": true
          },
          "answerCorrectnessScore": {
            "type": "number",
            "format": "double",
            "readOnly": true,
            "nullable": true,
            "title": "回答正確性評分",
            "description": "判斷chatbot回覆是否正確(需要有標準答案)"
          },
          "displayAnswerCorrectnessScore": {
            "type": "string",
            "readOnly": true
          },
          "answerSimilarityScore": {
            "type": "number",
            "format": "double",
            "readOnly": true,
            "nullable": true,
            "title": "回答相似性評分",
            "description": "判斷chatbot回覆是否與標準答案相似"
          },
          "displayAnswerSimilarityScore": {
            "type": "string",
            "readOnly": true
          },
          "contextRecallScore": {
            "type": "number",
            "format": "double",
            "readOnly": true,
            "nullable": true,
            "title": "參考資料召回率評分",
            "description": "判斷chatbot回覆是否能夠從參考資料中召回相關資料"
          },
          "displayContextRecallScore": {
            "type": "string",
            "readOnly": true
          },
          "replyTime": {
            "type": "string",
            "readOnly": true,
            "nullable": true,
            "title": "回覆時間"
          },
          "createdAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "建立時間",
            "pattern": "^\\d{13}$"
          },
          "error": {
            "type": "string",
            "readOnly": true,
            "nullable": true,
            "title": "錯誤訊息",
            "description": "儲存執行過程中的錯誤訊息"
          }
        },
        "required": [
          "answerCorrectnessScore",
          "answerRelevancyScore",
          "answerSimilarityScore",
          "condenseMessage",
          "context",
          "contextPrecisionScore",
          "contextRecallScore",
          "createdAt",
          "displayAnswerCorrectnessScore",
          "displayAnswerRelevancyScore",
          "displayAnswerSimilarityScore",
          "displayContextPrecisionScore",
          "displayContextRecallScore",
          "displayFaithfulnessScore",
          "error",
          "faithfulnessScore",
          "id",
          "inputMessage",
          "outputMessage",
          "replyTime"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[ChatbotRecord](#schemachatbotrecord)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» inputMessage|string|true|read-only|none|
|» condenseMessage|string|true|read-only|綜合聊天歷史與上下文後，修飾過後的使用者訊息|
|» outputMessage|string|true|read-only|none|
|» context|string¦null|true|read-only|none|
|» faithfulnessScore|number(double)¦null|true|read-only|判斷chatbot回覆是否符合資料庫內容，是否憑空想像|
|» displayFaithfulnessScore|string|true|read-only|none|
|» answerRelevancyScore|number(double)¦null|true|read-only|判斷chatbot回覆是否與使用者問題相關|
|» displayAnswerRelevancyScore|string|true|read-only|none|
|» contextPrecisionScore|number(double)¦null|true|read-only|判斷chatbot回覆是否與參考資料相關|
|» displayContextPrecisionScore|string|true|read-only|none|
|» answerCorrectnessScore|number(double)¦null|true|read-only|判斷chatbot回覆是否正確(需要有標準答案)|
|» displayAnswerCorrectnessScore|string|true|read-only|none|
|» answerSimilarityScore|number(double)¦null|true|read-only|判斷chatbot回覆是否與標準答案相似|
|» displayAnswerSimilarityScore|string|true|read-only|none|
|» contextRecallScore|number(double)¦null|true|read-only|判斷chatbot回覆是否能夠從參考資料中召回相關資料|
|» displayContextRecallScore|string|true|read-only|none|
|» replyTime|string¦null|true|read-only|none|
|» createdAt|string(timestamp)|true|read-only|none|
|» error|string¦null|true|read-only|儲存執行過程中的錯誤訊息|

<h2 id="tocS_PaginatedChatbotTextNodeList">PaginatedChatbotTextNodeList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedchatbottextnodelist"></a>
<a id="schema_PaginatedChatbotTextNodeList"></a>
<a id="tocSpaginatedchatbottextnodelist"></a>
<a id="tocspaginatedchatbottextnodelist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "charactersCount": {
            "type": "integer",
            "readOnly": true,
            "title": "字元數量"
          },
          "hitsCount": {
            "type": "integer",
            "readOnly": true,
            "title": "命中次數"
          },
          "text": {
            "type": "string",
            "readOnly": true,
            "title": "文字"
          },
          "updatedAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "更新時間",
            "pattern": "^\\d{13}$"
          },
          "filename": {
            "type": "string",
            "readOnly": true
          }
        },
        "required": [
          "charactersCount",
          "filename",
          "hitsCount",
          "id",
          "text",
          "updatedAt"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[ChatbotTextNode](#schemachatbottextnode)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» charactersCount|integer|true|read-only|none|
|» hitsCount|integer|true|read-only|none|
|» text|string|true|read-only|none|
|» updatedAt|string(timestamp)|true|read-only|none|
|» filename|string|true|read-only|none|

<h2 id="tocS_PaginatedChatbotUsageStatisticList">PaginatedChatbotUsageStatisticList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedchatbotusagestatisticlist"></a>
<a id="schema_PaginatedChatbotUsageStatisticList"></a>
<a id="tocSpaginatedchatbotusagestatisticlist"></a>
<a id="tocspaginatedchatbotusagestatisticlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "chatbotId": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "uploadedFilesSizeTotal": {
            "type": "integer",
            "maximum": 2147483647,
            "minimum": -2147483648,
            "title": "總檔案大小"
          },
          "conversationsCount": {
            "type": "integer",
            "maximum": 2147483647,
            "minimum": -2147483648,
            "title": "總對話數"
          }
        },
        "required": [
          "chatbotId",
          "id"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[ChatbotUsageStatistic](#schemachatbotusagestatistic)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» chatbotId|string(uuid)|true|read-only|none|
|» uploadedFilesSizeTotal|integer|false|none|none|
|» conversationsCount|integer|false|none|none|

<h2 id="tocS_PaginatedConversationList">PaginatedConversationList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedconversationlist"></a>
<a id="schema_PaginatedConversationList"></a>
<a id="tocSpaginatedconversationlist"></a>
<a id="tocspaginatedconversationlist"></a>

```json
{
  "type": "object",
  "required": [
    "results"
  ],
  "properties": {
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?cursor=cD00ODY%3D\""
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?cursor=cj0xJnA9NDg3"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "contact": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "name": {
                "type": "string",
                "title": "姓名",
                "maxLength": 255
              },
              "avatar": {
                "type": "string",
                "format": "uri",
                "title": "大頭貼網址",
                "maxLength": 511
              },
              "createdAt": {
                "type": "string",
                "format": "timestamp",
                "readOnly": true,
                "title": "建立時間",
                "pattern": "^\\d{13}$"
              }
            },
            "required": [
              "createdAt",
              "id",
              "name"
            ]
          },
          "inbox": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "name": {
                "type": "string",
                "title": "名稱",
                "maxLength": 255
              },
              "channelType": {
                "allOf": [
                  {
                    "enum": [
                      "line",
                      "telegram",
                      "web",
                      "messenger"
                    ],
                    "type": "string",
                    "description": "* `line` - LINE\n* `telegram` - Telegram\n* `web` - Web\n* `messenger` - Messenger"
                  }
                ],
                "title": "頻道類型"
              },
              "unreadConversationsCount": {
                "type": "integer",
                "maximum": 2147483647,
                "minimum": -2147483648,
                "title": "未讀對話數量"
              }
            },
            "required": [
              "channelType",
              "id",
              "name"
            ]
          },
          "title": {
            "type": "string",
            "readOnly": true,
            "title": "標題"
          },
          "lastMessage": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "conversation": {
                "type": "string",
                "format": "uuid",
                "title": "對話"
              },
              "sender": {
                "type": "object",
                "properties": {
                  "id": {
                    "type": "integer"
                  },
                  "name": {
                    "type": "string"
                  },
                  "avatar": {
                    "type": "string",
                    "format": "uri"
                  }
                },
                "required": [
                  "avatar",
                  "id",
                  "name"
                ]
              },
              "type": {
                "type": "string",
                "default": "incoming"
              },
              "content": {
                "type": "string",
                "title": "內容"
              },
              "feedback": {
                "nullable": true,
                "title": "回饋",
                "oneOf": [
                  {
                    "enum": [
                      "like",
                      "dislike"
                    ],
                    "type": "string",
                    "description": "* `like` - Like\n* `dislike` - Dislike"
                  },
                  {
                    "enum": [
                      ""
                    ]
                  },
                  {
                    "enum": [
                      null
                    ]
                  }
                ]
              },
              "createdAt": {
                "type": "string",
                "format": "timestamp",
                "readOnly": true,
                "title": "建立時間",
                "pattern": "^\\d{13}$"
              },
              "attachments": {
                "type": "array",
                "items": {
                  "type": "object",
                  "properties": {
                    "id": {
                      "type": "string",
                      "format": "uuid",
                      "readOnly": true
                    },
                    "type": {
                      "allOf": [
                        {
                          "enum": [
                            "image",
                            "video",
                            "audio",
                            "sticker",
                            "other"
                          ],
                          "type": "string",
                          "description": "* `image` - Image\n* `video` - Video\n* `audio` - Audio\n* `sticker` - Sticker\n* `other` - Other"
                        }
                      ],
                      "default": "other"
                    },
                    "filename": {
                      "type": "string"
                    },
                    "file": {
                      "type": "string",
                      "format": "uri"
                    }
                  },
                  "required": [
                    "file",
                    "filename",
                    "id"
                  ]
                }
              },
              "citations": {
                "type": "array",
                "items": {
                  "type": "object",
                  "properties": {
                    "id": {
                      "type": "string",
                      "format": "uuid",
                      "readOnly": true
                    },
                    "filename": {
                      "type": "string"
                    },
                    "file": {
                      "type": "string",
                      "format": "uri"
                    },
                    "fileType": {
                      "type": "string",
                      "readOnly": true,
                      "title": "檔案類型"
                    },
                    "size": {
                      "type": "integer",
                      "readOnly": true,
                      "title": "檔案大小"
                    },
                    "status": {
                      "allOf": [
                        {
                          "enum": [
                            "initial",
                            "processing",
                            "done",
                            "deleting",
                            "failed"
                          ],
                          "type": "string",
                          "description": "* `initial` - Initial\n* `processing` - Processing\n* `done` - Done\n* `deleting` - Deleting\n* `failed` - Failed"
                        }
                      ],
                      "readOnly": true,
                      "title": "狀態"
                    },
                    "chatbotFileContent": {
                      "type": "string",
                      "format": "uuid",
                      "readOnly": true
                    },
                    "parser": {
                      "type": "object",
                      "properties": {
                        "id": {
                          "type": "string",
                          "format": "uuid",
                          "readOnly": true
                        },
                        "name": {
                          "type": "string",
                          "maxLength": 255
                        },
                        "provider": {
                          "enum": [
                            "maiagent",
                            "llama",
                            "azure"
                          ],
                          "type": "string",
                          "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
                        },
                        "priority": {
                          "type": "integer",
                          "readOnly": true
                        }
                      },
                      "required": [
                        "id",
                        "name",
                        "priority",
                        "provider"
                      ]
                    },
                    "createdAt": {
                      "type": "string",
                      "format": "timestamp",
                      "readOnly": true,
                      "title": "建立時間",
                      "pattern": "^\\d{13}$"
                    }
                  },
                  "required": [
                    "chatbotFileContent",
                    "createdAt",
                    "file",
                    "fileType",
                    "filename",
                    "id",
                    "parser",
                    "size",
                    "status"
                  ]
                },
                "readOnly": true
              },
              "citationNodes": {
                "type": "array",
                "items": {
                  "type": "object",
                  "properties": {
                    "chatbotTextNode": {
                      "type": "object",
                      "properties": {
                        "id": {
                          "type": "string",
                          "format": "uuid",
                          "readOnly": true
                        },
                        "charactersCount": {
                          "type": "integer",
                          "readOnly": true,
                          "title": "字元數量"
                        },
                        "hitsCount": {
                          "type": "integer",
                          "readOnly": true,
                          "title": "命中次數"
                        },
                        "text": {
                          "type": "string",
                          "readOnly": true,
                          "title": "文字"
                        },
                        "updatedAt": {
                          "type": "string",
                          "format": "timestamp",
                          "readOnly": true,
                          "title": "更新時間",
                          "pattern": "^\\d{13}$"
                        },
                        "filename": {
                          "type": "string",
                          "readOnly": true
                        }
                      },
                      "required": [
                        "charactersCount",
                        "filename",
                        "hitsCount",
                        "id",
                        "text",
                        "updatedAt"
                      ]
                    },
                    "score": {
                      "type": "number",
                      "format": "double"
                    },
                    "displayScore": {
                      "type": "string",
                      "readOnly": true
                    }
                  },
                  "required": [
                    "chatbotTextNode",
                    "displayScore"
                  ]
                },
                "readOnly": true
              }
            },
            "required": [
              "citationNodes",
              "citations",
              "conversation",
              "createdAt",
              "id"
            ]
          },
          "lastMessageCreatedAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "最後訊息時間",
            "pattern": "^\\d{13}$"
          },
          "unreadMessagesCount": {
            "type": "integer",
            "readOnly": true,
            "title": "未讀訊息數量"
          },
          "autoReplyEnabled": {
            "type": "boolean",
            "readOnly": true,
            "title": "開啟自動回覆"
          },
          "isAutoReplyNow": {
            "type": "string",
            "readOnly": true
          },
          "lastReadAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "nullable": true,
            "title": "最後查看時間",
            "pattern": "^\\d{13}$"
          },
          "createdAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "建立時間",
            "pattern": "^\\d{13}$"
          },
          "isGroupChat": {
            "type": "string",
            "readOnly": true
          },
          "enableGroupMention": {
            "type": "string",
            "readOnly": true
          }
        },
        "required": [
          "autoReplyEnabled",
          "contact",
          "createdAt",
          "enableGroupMention",
          "id",
          "inbox",
          "isAutoReplyNow",
          "isGroupChat",
          "lastMessageCreatedAt",
          "lastReadAt",
          "title",
          "unreadMessagesCount"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Conversation](#schemaconversation)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» contact|[Contact](#schemacontact)|true|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» name|string|true|none|none|
|»» avatar|string(uri)|false|none|none|
|»» createdAt|string(timestamp)|true|read-only|none|
|» inbox|[Inbox](#schemainbox)|true|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» name|string|true|none|none|
|»» channelType|[ChannelTypeEnum](#schemachanneltypeenum)|true|none|* `line` - LINE<br>* `telegram` - Telegram<br>* `web` - Web<br>* `messenger` - Messenger|
|»» unreadConversationsCount|integer|false|none|none|
|» title|string|true|read-only|none|
|» lastMessage|[Message](#schemamessage)|false|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» conversation|string(uuid)|true|none|none|
|»» sender|[Sender](#schemasender)|false|none|none|
|»»» id|integer|true|none|none|
|»»» name|string|true|none|none|
|»»» avatar|string(uri)|true|none|none|
|»» type|string|false|none|none|
|»» content|string|false|none|none|
|»» feedback|any|false|none|none|

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»» *anonymous*|[FeedbackEnum](#schemafeedbackenum)|false|none|* `like` - Like<br>* `dislike` - Dislike|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»» *anonymous*|string|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»» *anonymous*|object|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» createdAt|string(timestamp)|true|read-only|none|
|»» attachments|[[Attachment](#schemaattachment)]|false|none|none|
|»»» id|string(uuid)|true|read-only|none|
|»»» type|[TypeEnum](#schematypeenum)|false|none|* `image` - Image<br>* `video` - Video<br>* `audio` - Audio<br>* `sticker` - Sticker<br>* `other` - Other|
|»»» filename|string|true|none|none|
|»»» file|string(uri)|true|none|none|
|»» citations|[[ChatbotFile](#schemachatbotfile)]|true|read-only|none|
|»»» id|string(uuid)|true|read-only|none|
|»»» filename|string|true|none|none|
|»»» file|string(uri)|true|none|none|
|»»» fileType|string|true|read-only|none|
|»»» size|integer|true|read-only|none|
|»»» status|[StatusBbcEnum](#schemastatusbbcenum)|true|read-only|* `initial` - Initial<br>* `processing` - Processing<br>* `done` - Done<br>* `deleting` - Deleting<br>* `failed` - Failed|
|»»» chatbotFileContent|string(uuid)|true|read-only|none|
|»»» parser|[Parser](#schemaparser)|true|none|none|
|»»»» id|string(uuid)|true|read-only|none|
|»»»» name|string|true|none|none|
|»»»» provider|[ProviderEnum](#schemaproviderenum)|true|none|* `maiagent` - MaiAgent<br>* `llama` - Llama<br>* `azure` - Azure|
|»»»» priority|integer|true|read-only|none|
|»»» createdAt|string(timestamp)|true|read-only|none|
|»» citationNodes|[[CitationNode](#schemacitationnode)]|true|read-only|none|
|»»» chatbotTextNode|[ChatbotTextNode](#schemachatbottextnode)|true|none|none|
|»»»» id|string(uuid)|true|read-only|none|
|»»»» charactersCount|integer|true|read-only|none|
|»»»» hitsCount|integer|true|read-only|none|
|»»»» text|string|true|read-only|none|
|»»»» updatedAt|string(timestamp)|true|read-only|none|
|»»»» filename|string|true|read-only|none|
|»»» score|number(double)|false|none|none|
|»»» displayScore|string|true|read-only|none|
|» lastMessageCreatedAt|string(timestamp)|true|read-only|none|
|» unreadMessagesCount|integer|true|read-only|none|
|» autoReplyEnabled|boolean|true|read-only|none|
|» isAutoReplyNow|string|true|read-only|none|
|» lastReadAt|string(timestamp)¦null|true|read-only|none|
|» createdAt|string(timestamp)|true|read-only|none|
|» isGroupChat|string|true|read-only|none|
|» enableGroupMention|string|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|channelType|line|
|channelType|telegram|
|channelType|web|
|channelType|messenger|
|*anonymous*|like|
|*anonymous*|dislike|
|*anonymous*||
|*anonymous*|null|
|type|image|
|type|video|
|type|audio|
|type|sticker|
|type|other|
|status|initial|
|status|processing|
|status|done|
|status|deleting|
|status|failed|
|provider|maiagent|
|provider|llama|
|provider|azure|

<h2 id="tocS_PaginatedCrawlPageList">PaginatedCrawlPageList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedcrawlpagelist"></a>
<a id="schema_PaginatedCrawlPageList"></a>
<a id="tocSpaginatedcrawlpagelist"></a>
<a id="tocspaginatedcrawlpagelist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "url": {
            "type": "string",
            "format": "uri",
            "title": "網頁網址",
            "maxLength": 511
          },
          "title": {
            "type": "string",
            "nullable": true,
            "title": "網頁標題"
          },
          "status": {
            "allOf": [
              {
                "enum": [
                  "pending",
                  "processing",
                  "done",
                  "cancelled"
                ],
                "type": "string",
                "description": "* `pending` - Pending\n* `processing` - Processing\n* `done` - Done\n* `cancelled` - Cancelled"
              }
            ],
            "title": "狀態"
          },
          "isOriginalPage": {
            "type": "boolean",
            "title": "是否為原始頁面"
          }
        },
        "required": [
          "id",
          "url"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[CrawlPage](#schemacrawlpage)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» url|string(uri)|true|none|none|
|» title|string¦null|false|none|none|
|» status|[CrawlPageStatusEnum](#schemacrawlpagestatusenum)|false|none|* `pending` - Pending<br>* `processing` - Processing<br>* `done` - Done<br>* `cancelled` - Cancelled|
|» isOriginalPage|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|pending|
|status|processing|
|status|done|
|status|cancelled|

<h2 id="tocS_PaginatedCrawlPageRequestList">PaginatedCrawlPageRequestList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedcrawlpagerequestlist"></a>
<a id="schema_PaginatedCrawlPageRequestList"></a>
<a id="tocSpaginatedcrawlpagerequestlist"></a>
<a id="tocspaginatedcrawlpagerequestlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "url": {
            "type": "string",
            "format": "uri",
            "title": "網頁網址",
            "maxLength": 200
          },
          "status": {
            "allOf": [
              {
                "enum": [
                  "processing",
                  "done",
                  "cancelled"
                ],
                "type": "string",
                "description": "* `processing` - Processing\n* `done` - Done\n* `cancelled` - Cancelled"
              }
            ],
            "title": "狀態"
          },
          "createdAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "建立時間",
            "pattern": "^\\d{13}$"
          }
        },
        "required": [
          "createdAt",
          "id",
          "url"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[CrawlPageRequest](#schemacrawlpagerequest)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» url|string(uri)|true|none|none|
|» status|[Status235Enum](#schemastatus235enum)|false|none|* `processing` - Processing<br>* `done` - Done<br>* `cancelled` - Cancelled|
|» createdAt|string(timestamp)|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|processing|
|status|done|
|status|cancelled|

<h2 id="tocS_PaginatedFacebookSystemUserList">PaginatedFacebookSystemUserList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedfacebooksystemuserlist"></a>
<a id="schema_PaginatedFacebookSystemUserList"></a>
<a id="tocSpaginatedfacebooksystemuserlist"></a>
<a id="tocspaginatedfacebooksystemuserlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "systemUserId": {
            "type": "string",
            "readOnly": true
          }
        },
        "required": [
          "id",
          "systemUserId"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[FacebookSystemUser](#schemafacebooksystemuser)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» systemUserId|string|true|read-only|none|

<h2 id="tocS_PaginatedFaqList">PaginatedFaqList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedfaqlist"></a>
<a id="schema_PaginatedFaqList"></a>
<a id="tocSpaginatedfaqlist"></a>
<a id="tocspaginatedfaqlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "question": {
            "type": "string",
            "title": "問題"
          },
          "answer": {
            "type": "string",
            "title": "答案"
          },
          "hitsCount": {
            "type": "integer",
            "readOnly": true,
            "title": "命中次數"
          }
        },
        "required": [
          "answer",
          "hitsCount",
          "id",
          "question"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Faq](#schemafaq)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» question|string|true|none|none|
|» answer|string|true|none|none|
|» hitsCount|integer|true|read-only|none|

<h2 id="tocS_PaginatedGroupChatbotList">PaginatedGroupChatbotList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedgroupchatbotlist"></a>
<a id="schema_PaginatedGroupChatbotList"></a>
<a id="tocSpaginatedgroupchatbotlist"></a>
<a id="tocspaginatedgroupchatbotlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "group": {
            "type": "string",
            "format": "uuid"
          },
          "chatbot": {
            "type": "object",
            "description": "Adds nested create feature",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "workflow": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "name": {
                "type": "string",
                "title": "名稱",
                "maxLength": 255
              },
              "largeLanguageModel": {
                "type": "string",
                "format": "uuid"
              },
              "rag": {
                "type": "string",
                "format": "uuid"
              },
              "embeddingModel": {
                "type": "string",
                "format": "uuid",
                "nullable": true
              },
              "rerankerModel": {
                "type": "string",
                "format": "uuid",
                "nullable": true
              },
              "instructions": {
                "type": "string",
                "title": "指令"
              },
              "webhookUrl": {
                "type": "string",
                "format": "uri",
                "nullable": true,
                "maxLength": 511
              },
              "apiWebChatId": {
                "type": "string",
                "readOnly": true,
                "nullable": true,
                "title": "API WebChat ID"
              },
              "updatedAt": {
                "type": "string",
                "format": "timestamp",
                "readOnly": true,
                "title": "更新時間",
                "pattern": "^\\d{13}$"
              },
              "organization": {
                "type": "string",
                "format": "uuid"
              },
              "builtInWorkflow": {
                "type": "string",
                "format": "uuid",
                "nullable": true
              },
              "replyMode": {
                "allOf": [
                  {
                    "enum": [
                      "normal",
                      "template",
                      "hybrid"
                    ],
                    "type": "string",
                    "description": "* `normal` - 正常\n* `template` - 模板\n* `hybrid` - 混合"
                  }
                ],
                "title": "回傳模式"
              },
              "template": {
                "type": "string",
                "nullable": true,
                "title": "模板"
              },
              "unanswerableTemplate": {
                "type": "string",
                "nullable": true,
                "title": "無法回答時的模板"
              },
              "totalLlmWordCount": {
                "type": "integer",
                "maximum": 9223372036854776000,
                "minimum": -9223372036854776000,
                "format": "int64",
                "title": "LLM 使用總字數",
                "description": "累積的 LLM 使用總字數"
              },
              "enableChineseConversion": {
                "type": "boolean"
              },
              "outputFormat": {
                "nullable": true
              }
            },
            "required": [
              "apiWebChatId",
              "id",
              "largeLanguageModel",
              "name",
              "rag",
              "updatedAt",
              "workflow"
            ]
          },
          "createdAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "建立時間",
            "pattern": "^\\d{13}$"
          }
        },
        "required": [
          "chatbot",
          "createdAt",
          "group",
          "id"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[GroupChatbot](#schemagroupchatbot)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» group|string(uuid)|true|none|none|
|» chatbot|[Chatbot](#schemachatbot)|true|none|Adds nested create feature|
|»» id|string(uuid)|true|read-only|none|
|»» workflow|string(uuid)|true|read-only|none|
|»» name|string|true|none|none|
|»» largeLanguageModel|string(uuid)|true|none|none|
|»» rag|string(uuid)|true|none|none|
|»» embeddingModel|string(uuid)¦null|false|none|none|
|»» rerankerModel|string(uuid)¦null|false|none|none|
|»» instructions|string|false|none|none|
|»» webhookUrl|string(uri)¦null|false|none|none|
|»» apiWebChatId|string¦null|true|read-only|none|
|»» updatedAt|string(timestamp)|true|read-only|none|
|»» organization|string(uuid)|false|none|none|
|»» builtInWorkflow|string(uuid)¦null|false|none|none|
|»» replyMode|[ReplyModeEnum](#schemareplymodeenum)|false|none|* `normal` - 正常<br>* `template` - 模板<br>* `hybrid` - 混合|
|»» template|string¦null|false|none|none|
|»» unanswerableTemplate|string¦null|false|none|none|
|»» totalLlmWordCount|integer(int64)|false|none|累積的 LLM 使用總字數|
|»» enableChineseConversion|boolean|false|none|none|
|»» outputFormat|any|false|none|none|
|» createdAt|string(timestamp)|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|replyMode|normal|
|replyMode|template|
|replyMode|hybrid|

<h2 id="tocS_PaginatedGroupList">PaginatedGroupList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedgrouplist"></a>
<a id="schema_PaginatedGroupList"></a>
<a id="tocSpaginatedgrouplist"></a>
<a id="tocspaginatedgrouplist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "name": {
            "type": "string",
            "title": "名稱",
            "maxLength": 255
          },
          "permissions": {
            "type": "array",
            "items": {
              "type": "object",
              "properties": {
                "id": {
                  "type": "string",
                  "format": "uuid",
                  "readOnly": true
                },
                "name": {
                  "type": "string",
                  "title": "名稱",
                  "maxLength": 255
                },
                "description": {
                  "type": "string",
                  "title": "描述"
                }
              },
              "required": [
                "id",
                "name"
              ]
            }
          },
          "createdAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "建立時間",
            "pattern": "^\\d{13}$"
          }
        },
        "required": [
          "createdAt",
          "id",
          "name",
          "permissions"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Group](#schemagroup)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» permissions|[[Permission](#schemapermission)]|true|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» name|string|true|none|none|
|»» description|string|false|none|none|
|» createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_PaginatedGroupMemberList">PaginatedGroupMemberList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedgroupmemberlist"></a>
<a id="schema_PaginatedGroupMemberList"></a>
<a id="tocSpaginatedgroupmemberlist"></a>
<a id="tocspaginatedgroupmemberlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "member": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "name": {
                "type": "string",
                "readOnly": true
              },
              "organization": {
                "type": "object",
                "properties": {
                  "id": {
                    "type": "string",
                    "format": "uuid",
                    "readOnly": true
                  },
                  "name": {
                    "type": "string",
                    "title": "名稱",
                    "maxLength": 255
                  },
                  "owner": {
                    "allOf": [
                      {
                        "type": "object",
                        "properties": {
                          "id": {
                            "type": "string",
                            "format": "uuid",
                            "readOnly": true
                          },
                          "name": {
                            "type": "string",
                            "title": "真實姓名",
                            "maxLength": 255
                          }
                        },
                        "required": [
                          "id",
                          "name"
                        ]
                      }
                    ],
                    "readOnly": true
                  },
                  "createdAt": {
                    "type": "string",
                    "format": "timestamp",
                    "readOnly": true,
                    "title": "建立時間",
                    "pattern": "^\\d{13}$"
                  },
                  "usageStatistics": {
                    "type": "string",
                    "readOnly": true
                  }
                },
                "required": [
                  "createdAt",
                  "id",
                  "name",
                  "owner",
                  "usageStatistics"
                ]
              },
              "isOwner": {
                "type": "string",
                "readOnly": true
              },
              "permissions": {
                "type": "string",
                "readOnly": true
              },
              "createdAt": {
                "type": "string",
                "format": "timestamp",
                "readOnly": true,
                "title": "建立時間",
                "pattern": "^\\d{13}$"
              }
            },
            "required": [
              "createdAt",
              "id",
              "isOwner",
              "name",
              "organization",
              "permissions"
            ]
          },
          "createdAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "建立時間",
            "pattern": "^\\d{13}$"
          }
        },
        "required": [
          "createdAt",
          "id",
          "member"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[GroupMember](#schemagroupmember)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» member|[Member](#schemamember)|true|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» name|string|true|read-only|none|
|»» organization|[Organization](#schemaorganization)|true|none|none|
|»»» id|string(uuid)|true|read-only|none|
|»»» name|string|true|none|none|
|»»» owner|[UserBase](#schemauserbase)|true|read-only|none|
|»»»» id|string(uuid)|true|read-only|none|
|»»»» name|string|true|none|none|
|»»» createdAt|string(timestamp)|true|read-only|none|
|»»» usageStatistics|string|true|read-only|none|
|»» isOwner|string|true|read-only|none|
|»» permissions|string|true|read-only|none|
|»» createdAt|string(timestamp)|true|read-only|none|
|» createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_PaginatedInboxList">PaginatedInboxList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedinboxlist"></a>
<a id="schema_PaginatedInboxList"></a>
<a id="tocSpaginatedinboxlist"></a>
<a id="tocspaginatedinboxlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "name": {
            "type": "string",
            "title": "名稱",
            "maxLength": 255
          },
          "channelType": {
            "allOf": [
              {
                "enum": [
                  "line",
                  "telegram",
                  "web",
                  "messenger"
                ],
                "type": "string",
                "description": "* `line` - LINE\n* `telegram` - Telegram\n* `web` - Web\n* `messenger` - Messenger"
              }
            ],
            "title": "頻道類型"
          },
          "unreadConversationsCount": {
            "type": "integer",
            "maximum": 2147483647,
            "minimum": -2147483648,
            "title": "未讀對話數量"
          }
        },
        "required": [
          "channelType",
          "id",
          "name"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Inbox](#schemainbox)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» channelType|[ChannelTypeEnum](#schemachanneltypeenum)|true|none|* `line` - LINE<br>* `telegram` - Telegram<br>* `web` - Web<br>* `messenger` - Messenger|
|» unreadConversationsCount|integer|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|channelType|line|
|channelType|telegram|
|channelType|web|
|channelType|messenger|

<h2 id="tocS_PaginatedMemberList">PaginatedMemberList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedmemberlist"></a>
<a id="schema_PaginatedMemberList"></a>
<a id="tocSpaginatedmemberlist"></a>
<a id="tocspaginatedmemberlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "name": {
            "type": "string",
            "readOnly": true
          },
          "organization": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "name": {
                "type": "string",
                "title": "名稱",
                "maxLength": 255
              },
              "owner": {
                "allOf": [
                  {
                    "type": "object",
                    "properties": {
                      "id": {
                        "type": "string",
                        "format": "uuid",
                        "readOnly": true
                      },
                      "name": {
                        "type": "string",
                        "title": "真實姓名",
                        "maxLength": 255
                      }
                    },
                    "required": [
                      "id",
                      "name"
                    ]
                  }
                ],
                "readOnly": true
              },
              "createdAt": {
                "type": "string",
                "format": "timestamp",
                "readOnly": true,
                "title": "建立時間",
                "pattern": "^\\d{13}$"
              },
              "usageStatistics": {
                "type": "string",
                "readOnly": true
              }
            },
            "required": [
              "createdAt",
              "id",
              "name",
              "owner",
              "usageStatistics"
            ]
          },
          "isOwner": {
            "type": "string",
            "readOnly": true
          },
          "permissions": {
            "type": "string",
            "readOnly": true
          },
          "createdAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "建立時間",
            "pattern": "^\\d{13}$"
          }
        },
        "required": [
          "createdAt",
          "id",
          "isOwner",
          "name",
          "organization",
          "permissions"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Member](#schemamember)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|read-only|none|
|» organization|[Organization](#schemaorganization)|true|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» name|string|true|none|none|
|»» owner|[UserBase](#schemauserbase)|true|read-only|none|
|»»» id|string(uuid)|true|read-only|none|
|»»» name|string|true|none|none|
|»» createdAt|string(timestamp)|true|read-only|none|
|»» usageStatistics|string|true|read-only|none|
|» isOwner|string|true|read-only|none|
|» permissions|string|true|read-only|none|
|» createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_PaginatedMessageList">PaginatedMessageList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedmessagelist"></a>
<a id="schema_PaginatedMessageList"></a>
<a id="tocSpaginatedmessagelist"></a>
<a id="tocspaginatedmessagelist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "conversation": {
            "type": "string",
            "format": "uuid",
            "title": "對話"
          },
          "sender": {
            "type": "object",
            "properties": {
              "id": {
                "type": "integer"
              },
              "name": {
                "type": "string"
              },
              "avatar": {
                "type": "string",
                "format": "uri"
              }
            },
            "required": [
              "avatar",
              "id",
              "name"
            ]
          },
          "type": {
            "type": "string",
            "default": "incoming"
          },
          "content": {
            "type": "string",
            "title": "內容"
          },
          "feedback": {
            "nullable": true,
            "title": "回饋",
            "oneOf": [
              {
                "enum": [
                  "like",
                  "dislike"
                ],
                "type": "string",
                "description": "* `like` - Like\n* `dislike` - Dislike"
              },
              {
                "enum": [
                  ""
                ]
              },
              {
                "enum": [
                  null
                ]
              }
            ]
          },
          "createdAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "建立時間",
            "pattern": "^\\d{13}$"
          },
          "attachments": {
            "type": "array",
            "items": {
              "type": "object",
              "properties": {
                "id": {
                  "type": "string",
                  "format": "uuid",
                  "readOnly": true
                },
                "type": {
                  "allOf": [
                    {
                      "enum": [
                        "image",
                        "video",
                        "audio",
                        "sticker",
                        "other"
                      ],
                      "type": "string",
                      "description": "* `image` - Image\n* `video` - Video\n* `audio` - Audio\n* `sticker` - Sticker\n* `other` - Other"
                    }
                  ],
                  "default": "other"
                },
                "filename": {
                  "type": "string"
                },
                "file": {
                  "type": "string",
                  "format": "uri"
                }
              },
              "required": [
                "file",
                "filename",
                "id"
              ]
            }
          },
          "citations": {
            "type": "array",
            "items": {
              "type": "object",
              "properties": {
                "id": {
                  "type": "string",
                  "format": "uuid",
                  "readOnly": true
                },
                "filename": {
                  "type": "string"
                },
                "file": {
                  "type": "string",
                  "format": "uri"
                },
                "fileType": {
                  "type": "string",
                  "readOnly": true,
                  "title": "檔案類型"
                },
                "size": {
                  "type": "integer",
                  "readOnly": true,
                  "title": "檔案大小"
                },
                "status": {
                  "allOf": [
                    {
                      "enum": [
                        "initial",
                        "processing",
                        "done",
                        "deleting",
                        "failed"
                      ],
                      "type": "string",
                      "description": "* `initial` - Initial\n* `processing` - Processing\n* `done` - Done\n* `deleting` - Deleting\n* `failed` - Failed"
                    }
                  ],
                  "readOnly": true,
                  "title": "狀態"
                },
                "chatbotFileContent": {
                  "type": "string",
                  "format": "uuid",
                  "readOnly": true
                },
                "parser": {
                  "type": "object",
                  "properties": {
                    "id": {
                      "type": "string",
                      "format": "uuid",
                      "readOnly": true
                    },
                    "name": {
                      "type": "string",
                      "maxLength": 255
                    },
                    "provider": {
                      "enum": [
                        "maiagent",
                        "llama",
                        "azure"
                      ],
                      "type": "string",
                      "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
                    },
                    "priority": {
                      "type": "integer",
                      "readOnly": true
                    }
                  },
                  "required": [
                    "id",
                    "name",
                    "priority",
                    "provider"
                  ]
                },
                "createdAt": {
                  "type": "string",
                  "format": "timestamp",
                  "readOnly": true,
                  "title": "建立時間",
                  "pattern": "^\\d{13}$"
                }
              },
              "required": [
                "chatbotFileContent",
                "createdAt",
                "file",
                "fileType",
                "filename",
                "id",
                "parser",
                "size",
                "status"
              ]
            },
            "readOnly": true
          },
          "citationNodes": {
            "type": "array",
            "items": {
              "type": "object",
              "properties": {
                "chatbotTextNode": {
                  "type": "object",
                  "properties": {
                    "id": {
                      "type": "string",
                      "format": "uuid",
                      "readOnly": true
                    },
                    "charactersCount": {
                      "type": "integer",
                      "readOnly": true,
                      "title": "字元數量"
                    },
                    "hitsCount": {
                      "type": "integer",
                      "readOnly": true,
                      "title": "命中次數"
                    },
                    "text": {
                      "type": "string",
                      "readOnly": true,
                      "title": "文字"
                    },
                    "updatedAt": {
                      "type": "string",
                      "format": "timestamp",
                      "readOnly": true,
                      "title": "更新時間",
                      "pattern": "^\\d{13}$"
                    },
                    "filename": {
                      "type": "string",
                      "readOnly": true
                    }
                  },
                  "required": [
                    "charactersCount",
                    "filename",
                    "hitsCount",
                    "id",
                    "text",
                    "updatedAt"
                  ]
                },
                "score": {
                  "type": "number",
                  "format": "double"
                },
                "displayScore": {
                  "type": "string",
                  "readOnly": true
                }
              },
              "required": [
                "chatbotTextNode",
                "displayScore"
              ]
            },
            "readOnly": true
          }
        },
        "required": [
          "citationNodes",
          "citations",
          "conversation",
          "createdAt",
          "id"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Message](#schemamessage)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» conversation|string(uuid)|true|none|none|
|» sender|[Sender](#schemasender)|false|none|none|
|»» id|integer|true|none|none|
|»» name|string|true|none|none|
|»» avatar|string(uri)|true|none|none|
|» type|string|false|none|none|
|» content|string|false|none|none|
|» feedback|any|false|none|none|

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[FeedbackEnum](#schemafeedbackenum)|false|none|* `like` - Like<br>* `dislike` - Dislike|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|object|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» createdAt|string(timestamp)|true|read-only|none|
|» attachments|[[Attachment](#schemaattachment)]|false|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» type|[TypeEnum](#schematypeenum)|false|none|* `image` - Image<br>* `video` - Video<br>* `audio` - Audio<br>* `sticker` - Sticker<br>* `other` - Other|
|»» filename|string|true|none|none|
|»» file|string(uri)|true|none|none|
|» citations|[[ChatbotFile](#schemachatbotfile)]|true|read-only|none|
|»» id|string(uuid)|true|read-only|none|
|»» filename|string|true|none|none|
|»» file|string(uri)|true|none|none|
|»» fileType|string|true|read-only|none|
|»» size|integer|true|read-only|none|
|»» status|[StatusBbcEnum](#schemastatusbbcenum)|true|read-only|* `initial` - Initial<br>* `processing` - Processing<br>* `done` - Done<br>* `deleting` - Deleting<br>* `failed` - Failed|
|»» chatbotFileContent|string(uuid)|true|read-only|none|
|»» parser|[Parser](#schemaparser)|true|none|none|
|»»» id|string(uuid)|true|read-only|none|
|»»» name|string|true|none|none|
|»»» provider|[ProviderEnum](#schemaproviderenum)|true|none|* `maiagent` - MaiAgent<br>* `llama` - Llama<br>* `azure` - Azure|
|»»» priority|integer|true|read-only|none|
|»» createdAt|string(timestamp)|true|read-only|none|
|» citationNodes|[[CitationNode](#schemacitationnode)]|true|read-only|none|
|»» chatbotTextNode|[ChatbotTextNode](#schemachatbottextnode)|true|none|none|
|»»» id|string(uuid)|true|read-only|none|
|»»» charactersCount|integer|true|read-only|none|
|»»» hitsCount|integer|true|read-only|none|
|»»» text|string|true|read-only|none|
|»»» updatedAt|string(timestamp)|true|read-only|none|
|»»» filename|string|true|read-only|none|
|»» score|number(double)|false|none|none|
|»» displayScore|string|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|like|
|*anonymous*|dislike|
|*anonymous*||
|*anonymous*|null|
|type|image|
|type|video|
|type|audio|
|type|sticker|
|type|other|
|status|initial|
|status|processing|
|status|done|
|status|deleting|
|status|failed|
|provider|maiagent|
|provider|llama|
|provider|azure|

<h2 id="tocS_PaginatedOrganizationListList">PaginatedOrganizationListList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedorganizationlistlist"></a>
<a id="schema_PaginatedOrganizationListList"></a>
<a id="tocSpaginatedorganizationlistlist"></a>
<a id="tocspaginatedorganizationlistlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "name": {
            "type": "string",
            "title": "名稱",
            "maxLength": 255
          },
          "owner": {
            "allOf": [
              {
                "type": "object",
                "properties": {
                  "id": {
                    "type": "string",
                    "format": "uuid",
                    "readOnly": true
                  },
                  "name": {
                    "type": "string",
                    "title": "真實姓名",
                    "maxLength": 255
                  }
                },
                "required": [
                  "id",
                  "name"
                ]
              }
            ],
            "readOnly": true
          },
          "createdAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "建立時間",
            "pattern": "^\\d{13}$"
          }
        },
        "required": [
          "createdAt",
          "id",
          "name",
          "owner"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[OrganizationList](#schemaorganizationlist)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» owner|[UserBase](#schemauserbase)|true|read-only|none|
|»» id|string(uuid)|true|read-only|none|
|»» name|string|true|none|none|
|» createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_PaginatedParserList">PaginatedParserList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedparserlist"></a>
<a id="schema_PaginatedParserList"></a>
<a id="tocSpaginatedparserlist"></a>
<a id="tocspaginatedparserlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "name": {
            "type": "string",
            "maxLength": 255
          },
          "provider": {
            "enum": [
              "maiagent",
              "llama",
              "azure"
            ],
            "type": "string",
            "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
          },
          "priority": {
            "type": "integer",
            "readOnly": true
          }
        },
        "required": [
          "id",
          "name",
          "priority",
          "provider"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Parser](#schemaparser)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» provider|[ProviderEnum](#schemaproviderenum)|true|none|* `maiagent` - MaiAgent<br>* `llama` - Llama<br>* `azure` - Azure|
|» priority|integer|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|provider|maiagent|
|provider|llama|
|provider|azure|

<h2 id="tocS_PaginatedPermissionList">PaginatedPermissionList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedpermissionlist"></a>
<a id="schema_PaginatedPermissionList"></a>
<a id="tocSpaginatedpermissionlist"></a>
<a id="tocspaginatedpermissionlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "name": {
            "type": "string",
            "title": "名稱",
            "maxLength": 255
          },
          "description": {
            "type": "string",
            "title": "描述"
          }
        },
        "required": [
          "id",
          "name"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Permission](#schemapermission)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» description|string|false|none|none|

<h2 id="tocS_PaginatedUserList">PaginatedUserList</h2>
<!-- backwards compatibility -->
<a id="schemapaginateduserlist"></a>
<a id="schema_PaginatedUserList"></a>
<a id="tocSpaginateduserlist"></a>
<a id="tocspaginateduserlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "avatar": {
            "type": "string",
            "format": "uri",
            "title": "大頭貼"
          },
          "name": {
            "type": "string",
            "title": "真實姓名",
            "maxLength": 255
          },
          "email": {
            "type": "string",
            "format": "email",
            "title": "公司信箱",
            "maxLength": 254
          },
          "company": {
            "type": "string",
            "title": "公司名稱",
            "maxLength": 255
          },
          "invitationCode": {
            "type": "string",
            "title": "邀請碼",
            "pattern": "^[A-Z0-9]+$",
            "maxLength": 31
          },
          "apiKeys": {
            "type": "string",
            "readOnly": true
          },
          "permissions": {
            "type": "string",
            "readOnly": true
          }
        },
        "required": [
          "apiKeys",
          "email",
          "id",
          "invitationCode",
          "name",
          "permissions"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[User](#schemauser)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» avatar|string(uri)|false|none|none|
|» name|string|true|none|none|
|» email|string(email)|true|none|none|
|» company|string|false|none|none|
|» invitationCode|string|true|none|none|
|» apiKeys|string|true|read-only|none|
|» permissions|string|true|read-only|none|

<h2 id="tocS_PaginatedWebhookRecordList">PaginatedWebhookRecordList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedwebhookrecordlist"></a>
<a id="schema_PaginatedWebhookRecordList"></a>
<a id="tocSpaginatedwebhookrecordlist"></a>
<a id="tocspaginatedwebhookrecordlist"></a>

```json
{
  "type": "object",
  "required": [
    "count",
    "results"
  ],
  "properties": {
    "count": {
      "type": "integer",
      "example": 123
    },
    "next": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=4"
    },
    "previous": {
      "type": "string",
      "nullable": true,
      "format": "uri",
      "example": "http://api.example.org/accounts/?page=2"
    },
    "results": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "chatbot": {
            "type": "object",
            "description": "Adds nested create feature",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "workflow": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "name": {
                "type": "string",
                "title": "名稱",
                "maxLength": 255
              },
              "largeLanguageModel": {
                "type": "string",
                "format": "uuid"
              },
              "rag": {
                "type": "string",
                "format": "uuid"
              },
              "embeddingModel": {
                "type": "string",
                "format": "uuid",
                "nullable": true
              },
              "rerankerModel": {
                "type": "string",
                "format": "uuid",
                "nullable": true
              },
              "instructions": {
                "type": "string",
                "title": "指令"
              },
              "webhookUrl": {
                "type": "string",
                "format": "uri",
                "nullable": true,
                "maxLength": 511
              },
              "apiWebChatId": {
                "type": "string",
                "readOnly": true,
                "nullable": true,
                "title": "API WebChat ID"
              },
              "updatedAt": {
                "type": "string",
                "format": "timestamp",
                "readOnly": true,
                "title": "更新時間",
                "pattern": "^\\d{13}$"
              },
              "organization": {
                "type": "string",
                "format": "uuid"
              },
              "builtInWorkflow": {
                "type": "string",
                "format": "uuid",
                "nullable": true
              },
              "replyMode": {
                "allOf": [
                  {
                    "enum": [
                      "normal",
                      "template",
                      "hybrid"
                    ],
                    "type": "string",
                    "description": "* `normal` - 正常\n* `template` - 模板\n* `hybrid` - 混合"
                  }
                ],
                "title": "回傳模式"
              },
              "template": {
                "type": "string",
                "nullable": true,
                "title": "模板"
              },
              "unanswerableTemplate": {
                "type": "string",
                "nullable": true,
                "title": "無法回答時的模板"
              },
              "totalLlmWordCount": {
                "type": "integer",
                "maximum": 9223372036854776000,
                "minimum": -9223372036854776000,
                "format": "int64",
                "title": "LLM 使用總字數",
                "description": "累積的 LLM 使用總字數"
              },
              "enableChineseConversion": {
                "type": "boolean"
              },
              "outputFormat": {
                "nullable": true
              }
            },
            "required": [
              "apiWebChatId",
              "id",
              "largeLanguageModel",
              "name",
              "rag",
              "updatedAt",
              "workflow"
            ]
          },
          "url": {
            "type": "string"
          },
          "requestBody": {
            "nullable": true
          },
          "response": {
            "type": "string"
          },
          "statusCode": {
            "type": "integer",
            "maximum": 2147483647,
            "minimum": -2147483648,
            "nullable": true
          },
          "createdAt": {
            "type": "string",
            "format": "timestamp",
            "readOnly": true,
            "title": "建立時間",
            "pattern": "^\\d{13}$"
          }
        },
        "required": [
          "chatbot",
          "createdAt",
          "id",
          "url"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[WebhookRecord](#schemawebhookrecord)]|true|none|none|
|» id|string(uuid)|true|read-only|none|
|» chatbot|[Chatbot](#schemachatbot)|true|none|Adds nested create feature|
|»» id|string(uuid)|true|read-only|none|
|»» workflow|string(uuid)|true|read-only|none|
|»» name|string|true|none|none|
|»» largeLanguageModel|string(uuid)|true|none|none|
|»» rag|string(uuid)|true|none|none|
|»» embeddingModel|string(uuid)¦null|false|none|none|
|»» rerankerModel|string(uuid)¦null|false|none|none|
|»» instructions|string|false|none|none|
|»» webhookUrl|string(uri)¦null|false|none|none|
|»» apiWebChatId|string¦null|true|read-only|none|
|»» updatedAt|string(timestamp)|true|read-only|none|
|»» organization|string(uuid)|false|none|none|
|»» builtInWorkflow|string(uuid)¦null|false|none|none|
|»» replyMode|[ReplyModeEnum](#schemareplymodeenum)|false|none|* `normal` - 正常<br>* `template` - 模板<br>* `hybrid` - 混合|
|»» template|string¦null|false|none|none|
|»» unanswerableTemplate|string¦null|false|none|none|
|»» totalLlmWordCount|integer(int64)|false|none|累積的 LLM 使用總字數|
|»» enableChineseConversion|boolean|false|none|none|
|»» outputFormat|any|false|none|none|
|» url|string|true|none|none|
|» requestBody|any|false|none|none|
|» response|string|false|none|none|
|» statusCode|integer¦null|false|none|none|
|» createdAt|string(timestamp)|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|replyMode|normal|
|replyMode|template|
|replyMode|hybrid|

<h2 id="tocS_Parser">Parser</h2>
<!-- backwards compatibility -->
<a id="schemaparser"></a>
<a id="schema_Parser"></a>
<a id="tocSparser"></a>
<a id="tocsparser"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "maxLength": 255
    },
    "provider": {
      "enum": [
        "maiagent",
        "llama",
        "azure"
      ],
      "type": "string",
      "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
    },
    "priority": {
      "type": "integer",
      "readOnly": true
    }
  },
  "required": [
    "id",
    "name",
    "priority",
    "provider"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|provider|[ProviderEnum](#schemaproviderenum)|true|none|* `maiagent` - MaiAgent<br>* `llama` - Llama<br>* `azure` - Azure|
|priority|integer|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|provider|maiagent|
|provider|llama|
|provider|azure|

<h2 id="tocS_PasswordChange">PasswordChange</h2>
<!-- backwards compatibility -->
<a id="schemapasswordchange"></a>
<a id="schema_PasswordChange"></a>
<a id="tocSpasswordchange"></a>
<a id="tocspasswordchange"></a>

```json
{
  "type": "object",
  "properties": {
    "oldPassword": {
      "type": "string",
      "maxLength": 128
    },
    "newPassword1": {
      "type": "string",
      "maxLength": 128
    },
    "newPassword2": {
      "type": "string",
      "maxLength": 128
    }
  },
  "required": [
    "newPassword1",
    "newPassword2",
    "oldPassword"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|oldPassword|string|true|none|none|
|newPassword1|string|true|none|none|
|newPassword2|string|true|none|none|

<h2 id="tocS_PasswordReset">PasswordReset</h2>
<!-- backwards compatibility -->
<a id="schemapasswordreset"></a>
<a id="schema_PasswordReset"></a>
<a id="tocSpasswordreset"></a>
<a id="tocspasswordreset"></a>

```json
{
  "type": "object",
  "description": "Serializer for requesting a password reset e-mail.",
  "properties": {
    "email": {
      "type": "string",
      "format": "email"
    }
  },
  "required": [
    "email"
  ]
}

```

Serializer for requesting a password reset e-mail.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|email|string(email)|true|none|none|

<h2 id="tocS_PasswordResetConfirm">PasswordResetConfirm</h2>
<!-- backwards compatibility -->
<a id="schemapasswordresetconfirm"></a>
<a id="schema_PasswordResetConfirm"></a>
<a id="tocSpasswordresetconfirm"></a>
<a id="tocspasswordresetconfirm"></a>

```json
{
  "type": "object",
  "description": "Serializer for confirming a password reset attempt.",
  "properties": {
    "newPassword1": {
      "type": "string",
      "maxLength": 128
    },
    "newPassword2": {
      "type": "string",
      "maxLength": 128
    },
    "uid": {
      "type": "string"
    },
    "token": {
      "type": "string"
    }
  },
  "required": [
    "newPassword1",
    "newPassword2",
    "token",
    "uid"
  ]
}

```

Serializer for confirming a password reset attempt.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|newPassword1|string|true|none|none|
|newPassword2|string|true|none|none|
|uid|string|true|none|none|
|token|string|true|none|none|

<h2 id="tocS_PatchedAttachment">PatchedAttachment</h2>
<!-- backwards compatibility -->
<a id="schemapatchedattachment"></a>
<a id="schema_PatchedAttachment"></a>
<a id="tocSpatchedattachment"></a>
<a id="tocspatchedattachment"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "type": {
      "allOf": [
        {
          "enum": [
            "image",
            "video",
            "audio",
            "sticker",
            "other"
          ],
          "type": "string",
          "description": "* `image` - Image\n* `video` - Video\n* `audio` - Audio\n* `sticker` - Sticker\n* `other` - Other"
        }
      ],
      "default": "other"
    },
    "filename": {
      "type": "string"
    },
    "file": {
      "type": "string",
      "format": "uri"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|type|[TypeEnum](#schematypeenum)|false|none|* `image` - Image<br>* `video` - Video<br>* `audio` - Audio<br>* `sticker` - Sticker<br>* `other` - Other|
|filename|string|false|none|none|
|file|string(uri)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|image|
|type|video|
|type|audio|
|type|sticker|
|type|other|

<h2 id="tocS_PatchedChatbot">PatchedChatbot</h2>
<!-- backwards compatibility -->
<a id="schemapatchedchatbot"></a>
<a id="schema_PatchedChatbot"></a>
<a id="tocSpatchedchatbot"></a>
<a id="tocspatchedchatbot"></a>

```json
{
  "type": "object",
  "description": "Adds nested create feature",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "workflow": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "largeLanguageModel": {
      "type": "string",
      "format": "uuid"
    },
    "rag": {
      "type": "string",
      "format": "uuid"
    },
    "embeddingModel": {
      "type": "string",
      "format": "uuid",
      "nullable": true
    },
    "rerankerModel": {
      "type": "string",
      "format": "uuid",
      "nullable": true
    },
    "instructions": {
      "type": "string",
      "title": "指令"
    },
    "webhookUrl": {
      "type": "string",
      "format": "uri",
      "nullable": true,
      "maxLength": 511
    },
    "apiWebChatId": {
      "type": "string",
      "readOnly": true,
      "nullable": true,
      "title": "API WebChat ID"
    },
    "updatedAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "更新時間",
      "pattern": "^\\d{13}$"
    },
    "organization": {
      "type": "string",
      "format": "uuid"
    },
    "builtInWorkflow": {
      "type": "string",
      "format": "uuid",
      "nullable": true
    },
    "replyMode": {
      "allOf": [
        {
          "enum": [
            "normal",
            "template",
            "hybrid"
          ],
          "type": "string",
          "description": "* `normal` - 正常\n* `template` - 模板\n* `hybrid` - 混合"
        }
      ],
      "title": "回傳模式"
    },
    "template": {
      "type": "string",
      "nullable": true,
      "title": "模板"
    },
    "unanswerableTemplate": {
      "type": "string",
      "nullable": true,
      "title": "無法回答時的模板"
    },
    "totalLlmWordCount": {
      "type": "integer",
      "maximum": 9223372036854776000,
      "minimum": -9223372036854776000,
      "format": "int64",
      "title": "LLM 使用總字數",
      "description": "累積的 LLM 使用總字數"
    },
    "enableChineseConversion": {
      "type": "boolean"
    },
    "outputFormat": {
      "nullable": true
    }
  }
}

```

Adds nested create feature

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|workflow|string(uuid)|false|read-only|none|
|name|string|false|none|none|
|largeLanguageModel|string(uuid)|false|none|none|
|rag|string(uuid)|false|none|none|
|embeddingModel|string(uuid)¦null|false|none|none|
|rerankerModel|string(uuid)¦null|false|none|none|
|instructions|string|false|none|none|
|webhookUrl|string(uri)¦null|false|none|none|
|apiWebChatId|string¦null|false|read-only|none|
|updatedAt|string(timestamp)|false|read-only|none|
|organization|string(uuid)|false|none|none|
|builtInWorkflow|string(uuid)¦null|false|none|none|
|replyMode|[ReplyModeEnum](#schemareplymodeenum)|false|none|* `normal` - 正常<br>* `template` - 模板<br>* `hybrid` - 混合|
|template|string¦null|false|none|none|
|unanswerableTemplate|string¦null|false|none|none|
|totalLlmWordCount|integer(int64)|false|none|累積的 LLM 使用總字數|
|enableChineseConversion|boolean|false|none|none|
|outputFormat|any|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|replyMode|normal|
|replyMode|template|
|replyMode|hybrid|

<h2 id="tocS_PatchedChatbotFile">PatchedChatbotFile</h2>
<!-- backwards compatibility -->
<a id="schemapatchedchatbotfile"></a>
<a id="schema_PatchedChatbotFile"></a>
<a id="tocSpatchedchatbotfile"></a>
<a id="tocspatchedchatbotfile"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "filename": {
      "type": "string"
    },
    "file": {
      "type": "string",
      "format": "uri"
    },
    "fileType": {
      "type": "string",
      "readOnly": true,
      "title": "檔案類型"
    },
    "size": {
      "type": "integer",
      "readOnly": true,
      "title": "檔案大小"
    },
    "status": {
      "allOf": [
        {
          "enum": [
            "initial",
            "processing",
            "done",
            "deleting",
            "failed"
          ],
          "type": "string",
          "description": "* `initial` - Initial\n* `processing` - Processing\n* `done` - Done\n* `deleting` - Deleting\n* `failed` - Failed"
        }
      ],
      "readOnly": true,
      "title": "狀態"
    },
    "chatbotFileContent": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "parser": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "name": {
          "type": "string",
          "maxLength": 255
        },
        "provider": {
          "enum": [
            "maiagent",
            "llama",
            "azure"
          ],
          "type": "string",
          "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
        },
        "priority": {
          "type": "integer",
          "readOnly": true
        }
      },
      "required": [
        "id",
        "name",
        "priority",
        "provider"
      ]
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|filename|string|false|none|none|
|file|string(uri)|false|none|none|
|fileType|string|false|read-only|none|
|size|integer|false|read-only|none|
|status|[StatusBbcEnum](#schemastatusbbcenum)|false|read-only|* `initial` - Initial<br>* `processing` - Processing<br>* `done` - Done<br>* `deleting` - Deleting<br>* `failed` - Failed|
|chatbotFileContent|string(uuid)|false|read-only|none|
|parser|[Parser](#schemaparser)|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» provider|[ProviderEnum](#schemaproviderenum)|true|none|* `maiagent` - MaiAgent<br>* `llama` - Llama<br>* `azure` - Azure|
|» priority|integer|true|read-only|none|
|createdAt|string(timestamp)|false|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|initial|
|status|processing|
|status|done|
|status|deleting|
|status|failed|
|provider|maiagent|
|provider|llama|
|provider|azure|

<h2 id="tocS_PatchedChatbotFileContent">PatchedChatbotFileContent</h2>
<!-- backwards compatibility -->
<a id="schemapatchedchatbotfilecontent"></a>
<a id="schema_PatchedChatbotFileContent"></a>
<a id="tocSpatchedchatbotfilecontent"></a>
<a id="tocspatchedchatbotfilecontent"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "content": {
      "type": "string",
      "readOnly": true
    },
    "modifiedContent": {
      "type": "string",
      "title": "檔案修改內容"
    },
    "type": {
      "type": "string",
      "readOnly": true
    },
    "updatedAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "更新時間",
      "pattern": "^\\d{13}$"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|content|string|false|read-only|none|
|modifiedContent|string|false|none|none|
|type|string|false|read-only|none|
|updatedAt|string(timestamp)|false|read-only|none|

<h2 id="tocS_PatchedConversation">PatchedConversation</h2>
<!-- backwards compatibility -->
<a id="schemapatchedconversation"></a>
<a id="schema_PatchedConversation"></a>
<a id="tocSpatchedconversation"></a>
<a id="tocspatchedconversation"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "contact": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "name": {
          "type": "string",
          "title": "姓名",
          "maxLength": 255
        },
        "avatar": {
          "type": "string",
          "format": "uri",
          "title": "大頭貼網址",
          "maxLength": 511
        },
        "createdAt": {
          "type": "string",
          "format": "timestamp",
          "readOnly": true,
          "title": "建立時間",
          "pattern": "^\\d{13}$"
        }
      },
      "required": [
        "createdAt",
        "id",
        "name"
      ]
    },
    "inbox": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "name": {
          "type": "string",
          "title": "名稱",
          "maxLength": 255
        },
        "channelType": {
          "allOf": [
            {
              "enum": [
                "line",
                "telegram",
                "web",
                "messenger"
              ],
              "type": "string",
              "description": "* `line` - LINE\n* `telegram` - Telegram\n* `web` - Web\n* `messenger` - Messenger"
            }
          ],
          "title": "頻道類型"
        },
        "unreadConversationsCount": {
          "type": "integer",
          "maximum": 2147483647,
          "minimum": -2147483648,
          "title": "未讀對話數量"
        }
      },
      "required": [
        "channelType",
        "id",
        "name"
      ]
    },
    "title": {
      "type": "string",
      "readOnly": true,
      "title": "標題"
    },
    "lastMessage": {
      "type": "object",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "conversation": {
          "type": "string",
          "format": "uuid",
          "title": "對話"
        },
        "sender": {
          "type": "object",
          "properties": {
            "id": {
              "type": "integer"
            },
            "name": {
              "type": "string"
            },
            "avatar": {
              "type": "string",
              "format": "uri"
            }
          },
          "required": [
            "avatar",
            "id",
            "name"
          ]
        },
        "type": {
          "type": "string",
          "default": "incoming"
        },
        "content": {
          "type": "string",
          "title": "內容"
        },
        "feedback": {
          "nullable": true,
          "title": "回饋",
          "oneOf": [
            {
              "enum": [
                "like",
                "dislike"
              ],
              "type": "string",
              "description": "* `like` - Like\n* `dislike` - Dislike"
            },
            {
              "enum": [
                ""
              ]
            },
            {
              "enum": [
                null
              ]
            }
          ]
        },
        "createdAt": {
          "type": "string",
          "format": "timestamp",
          "readOnly": true,
          "title": "建立時間",
          "pattern": "^\\d{13}$"
        },
        "attachments": {
          "type": "array",
          "items": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "type": {
                "allOf": [
                  {
                    "enum": [
                      "image",
                      "video",
                      "audio",
                      "sticker",
                      "other"
                    ],
                    "type": "string",
                    "description": "* `image` - Image\n* `video` - Video\n* `audio` - Audio\n* `sticker` - Sticker\n* `other` - Other"
                  }
                ],
                "default": "other"
              },
              "filename": {
                "type": "string"
              },
              "file": {
                "type": "string",
                "format": "uri"
              }
            },
            "required": [
              "file",
              "filename",
              "id"
            ]
          }
        },
        "citations": {
          "type": "array",
          "items": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "filename": {
                "type": "string"
              },
              "file": {
                "type": "string",
                "format": "uri"
              },
              "fileType": {
                "type": "string",
                "readOnly": true,
                "title": "檔案類型"
              },
              "size": {
                "type": "integer",
                "readOnly": true,
                "title": "檔案大小"
              },
              "status": {
                "allOf": [
                  {
                    "enum": [
                      "initial",
                      "processing",
                      "done",
                      "deleting",
                      "failed"
                    ],
                    "type": "string",
                    "description": "* `initial` - Initial\n* `processing` - Processing\n* `done` - Done\n* `deleting` - Deleting\n* `failed` - Failed"
                  }
                ],
                "readOnly": true,
                "title": "狀態"
              },
              "chatbotFileContent": {
                "type": "string",
                "format": "uuid",
                "readOnly": true
              },
              "parser": {
                "type": "object",
                "properties": {
                  "id": {
                    "type": "string",
                    "format": "uuid",
                    "readOnly": true
                  },
                  "name": {
                    "type": "string",
                    "maxLength": 255
                  },
                  "provider": {
                    "enum": [
                      "maiagent",
                      "llama",
                      "azure"
                    ],
                    "type": "string",
                    "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
                  },
                  "priority": {
                    "type": "integer",
                    "readOnly": true
                  }
                },
                "required": [
                  "id",
                  "name",
                  "priority",
                  "provider"
                ]
              },
              "createdAt": {
                "type": "string",
                "format": "timestamp",
                "readOnly": true,
                "title": "建立時間",
                "pattern": "^\\d{13}$"
              }
            },
            "required": [
              "chatbotFileContent",
              "createdAt",
              "file",
              "fileType",
              "filename",
              "id",
              "parser",
              "size",
              "status"
            ]
          },
          "readOnly": true
        },
        "citationNodes": {
          "type": "array",
          "items": {
            "type": "object",
            "properties": {
              "chatbotTextNode": {
                "type": "object",
                "properties": {
                  "id": {
                    "type": "string",
                    "format": "uuid",
                    "readOnly": true
                  },
                  "charactersCount": {
                    "type": "integer",
                    "readOnly": true,
                    "title": "字元數量"
                  },
                  "hitsCount": {
                    "type": "integer",
                    "readOnly": true,
                    "title": "命中次數"
                  },
                  "text": {
                    "type": "string",
                    "readOnly": true,
                    "title": "文字"
                  },
                  "updatedAt": {
                    "type": "string",
                    "format": "timestamp",
                    "readOnly": true,
                    "title": "更新時間",
                    "pattern": "^\\d{13}$"
                  },
                  "filename": {
                    "type": "string",
                    "readOnly": true
                  }
                },
                "required": [
                  "charactersCount",
                  "filename",
                  "hitsCount",
                  "id",
                  "text",
                  "updatedAt"
                ]
              },
              "score": {
                "type": "number",
                "format": "double"
              },
              "displayScore": {
                "type": "string",
                "readOnly": true
              }
            },
            "required": [
              "chatbotTextNode",
              "displayScore"
            ]
          },
          "readOnly": true
        }
      },
      "required": [
        "citationNodes",
        "citations",
        "conversation",
        "createdAt",
        "id"
      ]
    },
    "lastMessageCreatedAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "最後訊息時間",
      "pattern": "^\\d{13}$"
    },
    "unreadMessagesCount": {
      "type": "integer",
      "readOnly": true,
      "title": "未讀訊息數量"
    },
    "autoReplyEnabled": {
      "type": "boolean",
      "readOnly": true,
      "title": "開啟自動回覆"
    },
    "isAutoReplyNow": {
      "type": "string",
      "readOnly": true
    },
    "lastReadAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "nullable": true,
      "title": "最後查看時間",
      "pattern": "^\\d{13}$"
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    },
    "isGroupChat": {
      "type": "string",
      "readOnly": true
    },
    "enableGroupMention": {
      "type": "string",
      "readOnly": true
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|contact|[Contact](#schemacontact)|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» avatar|string(uri)|false|none|none|
|» createdAt|string(timestamp)|true|read-only|none|
|inbox|[Inbox](#schemainbox)|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» channelType|[ChannelTypeEnum](#schemachanneltypeenum)|true|none|* `line` - LINE<br>* `telegram` - Telegram<br>* `web` - Web<br>* `messenger` - Messenger|
|» unreadConversationsCount|integer|false|none|none|
|title|string|false|read-only|none|
|lastMessage|[Message](#schemamessage)|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» conversation|string(uuid)|true|none|none|
|» sender|[Sender](#schemasender)|false|none|none|
|»» id|integer|true|none|none|
|»» name|string|true|none|none|
|»» avatar|string(uri)|true|none|none|
|» type|string|false|none|none|
|» content|string|false|none|none|
|» feedback|any|false|none|none|

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[FeedbackEnum](#schemafeedbackenum)|false|none|* `like` - Like<br>* `dislike` - Dislike|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|object|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» createdAt|string(timestamp)|true|read-only|none|
|» attachments|[[Attachment](#schemaattachment)]|false|none|none|
|»» id|string(uuid)|true|read-only|none|
|»» type|[TypeEnum](#schematypeenum)|false|none|* `image` - Image<br>* `video` - Video<br>* `audio` - Audio<br>* `sticker` - Sticker<br>* `other` - Other|
|»» filename|string|true|none|none|
|»» file|string(uri)|true|none|none|
|» citations|[[ChatbotFile](#schemachatbotfile)]|true|read-only|none|
|»» id|string(uuid)|true|read-only|none|
|»» filename|string|true|none|none|
|»» file|string(uri)|true|none|none|
|»» fileType|string|true|read-only|none|
|»» size|integer|true|read-only|none|
|»» status|[StatusBbcEnum](#schemastatusbbcenum)|true|read-only|* `initial` - Initial<br>* `processing` - Processing<br>* `done` - Done<br>* `deleting` - Deleting<br>* `failed` - Failed|
|»» chatbotFileContent|string(uuid)|true|read-only|none|
|»» parser|[Parser](#schemaparser)|true|none|none|
|»»» id|string(uuid)|true|read-only|none|
|»»» name|string|true|none|none|
|»»» provider|[ProviderEnum](#schemaproviderenum)|true|none|* `maiagent` - MaiAgent<br>* `llama` - Llama<br>* `azure` - Azure|
|»»» priority|integer|true|read-only|none|
|»» createdAt|string(timestamp)|true|read-only|none|
|» citationNodes|[[CitationNode](#schemacitationnode)]|true|read-only|none|
|»» chatbotTextNode|[ChatbotTextNode](#schemachatbottextnode)|true|none|none|
|»»» id|string(uuid)|true|read-only|none|
|»»» charactersCount|integer|true|read-only|none|
|»»» hitsCount|integer|true|read-only|none|
|»»» text|string|true|read-only|none|
|»»» updatedAt|string(timestamp)|true|read-only|none|
|»»» filename|string|true|read-only|none|
|»» score|number(double)|false|none|none|
|»» displayScore|string|true|read-only|none|
|lastMessageCreatedAt|string(timestamp)|false|read-only|none|
|unreadMessagesCount|integer|false|read-only|none|
|autoReplyEnabled|boolean|false|read-only|none|
|isAutoReplyNow|string|false|read-only|none|
|lastReadAt|string(timestamp)¦null|false|read-only|none|
|createdAt|string(timestamp)|false|read-only|none|
|isGroupChat|string|false|read-only|none|
|enableGroupMention|string|false|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|channelType|line|
|channelType|telegram|
|channelType|web|
|channelType|messenger|
|*anonymous*|like|
|*anonymous*|dislike|
|*anonymous*||
|*anonymous*|null|
|type|image|
|type|video|
|type|audio|
|type|sticker|
|type|other|
|status|initial|
|status|processing|
|status|done|
|status|deleting|
|status|failed|
|provider|maiagent|
|provider|llama|
|provider|azure|

<h2 id="tocS_PatchedFaq">PatchedFaq</h2>
<!-- backwards compatibility -->
<a id="schemapatchedfaq"></a>
<a id="schema_PatchedFaq"></a>
<a id="tocSpatchedfaq"></a>
<a id="tocspatchedfaq"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "question": {
      "type": "string",
      "title": "問題"
    },
    "answer": {
      "type": "string",
      "title": "答案"
    },
    "hitsCount": {
      "type": "integer",
      "readOnly": true,
      "title": "命中次數"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|question|string|false|none|none|
|answer|string|false|none|none|
|hitsCount|integer|false|read-only|none|

<h2 id="tocS_PatchedGroupCreate">PatchedGroupCreate</h2>
<!-- backwards compatibility -->
<a id="schemapatchedgroupcreate"></a>
<a id="schema_PatchedGroupCreate"></a>
<a id="tocSpatchedgroupcreate"></a>
<a id="tocspatchedgroupcreate"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "organization": {
      "type": "string",
      "format": "uuid"
    },
    "permissions": {
      "type": "array",
      "items": {
        "type": "string",
        "format": "uuid"
      }
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|name|string|false|none|none|
|organization|string(uuid)|false|none|none|
|permissions|[string]|false|none|none|
|createdAt|string(timestamp)|false|read-only|none|

<h2 id="tocS_PatchedInbox">PatchedInbox</h2>
<!-- backwards compatibility -->
<a id="schemapatchedinbox"></a>
<a id="schema_PatchedInbox"></a>
<a id="tocSpatchedinbox"></a>
<a id="tocspatchedinbox"></a>

```json
{
  "type": "object",
  "description": "Adds nested create feature",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "chatbot": {
      "type": "string",
      "format": "uuid"
    },
    "channelType": {
      "allOf": [
        {
          "enum": [
            "line",
            "telegram",
            "web",
            "messenger"
          ],
          "type": "string",
          "description": "* `line` - LINE\n* `telegram` - Telegram\n* `web` - Web\n* `messenger` - Messenger"
        }
      ],
      "title": "頻道類型"
    },
    "channelTypeLabel": {
      "type": "string",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "autoReplySchedules": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string",
            "format": "uuid",
            "readOnly": true
          },
          "weekday": {
            "type": "integer",
            "readOnly": true,
            "title": "星期"
          },
          "isEnabled": {
            "type": "boolean",
            "title": "開啟"
          },
          "timeSlots": {
            "type": "array",
            "items": {
              "type": "array",
              "items": {
                "type": "string",
                "format": "time",
                "title": "Time slots"
              },
              "maxItems": 2
            },
            "nullable": true
          },
          "weekdayName": {
            "type": "string",
            "readOnly": true
          }
        },
        "required": [
          "id",
          "weekday",
          "weekdayName"
        ]
      }
    },
    "unreadConversationsCount": {
      "type": "integer",
      "readOnly": true,
      "title": "未讀對話數量"
    },
    "channel": {
      "type": "string"
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    },
    "updatedAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "更新時間",
      "pattern": "^\\d{13}$"
    },
    "organization": {
      "type": "string",
      "format": "uuid",
      "nullable": true,
      "title": "組織"
    }
  }
}

```

Adds nested create feature

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|chatbot|string(uuid)|false|none|none|
|channelType|[ChannelTypeEnum](#schemachanneltypeenum)|false|none|* `line` - LINE<br>* `telegram` - Telegram<br>* `web` - Web<br>* `messenger` - Messenger|
|channelTypeLabel|string|false|read-only|none|
|name|string|false|none|none|
|autoReplySchedules|[[AutoReplySchedule](#schemaautoreplyschedule)]|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» weekday|integer|true|read-only|none|
|» isEnabled|boolean|false|none|none|
|» timeSlots|[array]¦null|false|none|none|
|»» Time slots|string(time)|false|none|none|
|» weekdayName|string|true|read-only|none|
|unreadConversationsCount|integer|false|read-only|none|
|channel|string|false|none|none|
|createdAt|string(timestamp)|false|read-only|none|
|updatedAt|string(timestamp)|false|read-only|none|
|organization|string(uuid)¦null|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|channelType|line|
|channelType|telegram|
|channelType|web|
|channelType|messenger|

<h2 id="tocS_PatchedLineChannel">PatchedLineChannel</h2>
<!-- backwards compatibility -->
<a id="schemapatchedlinechannel"></a>
<a id="schema_PatchedLineChannel"></a>
<a id="tocSpatchedlinechannel"></a>
<a id="tocspatchedlinechannel"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "channelId": {
      "type": "string"
    },
    "channelSecret": {
      "type": "string"
    },
    "channelAccessToken": {
      "type": "string"
    },
    "webhookUrl": {
      "type": "string",
      "readOnly": true
    },
    "enableGroupMention": {
      "type": "boolean"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|channelId|string|false|none|none|
|channelSecret|string|false|none|none|
|channelAccessToken|string|false|none|none|
|webhookUrl|string|false|read-only|none|
|enableGroupMention|boolean|false|none|none|

<h2 id="tocS_PatchedOrganization">PatchedOrganization</h2>
<!-- backwards compatibility -->
<a id="schemapatchedorganization"></a>
<a id="schema_PatchedOrganization"></a>
<a id="tocSpatchedorganization"></a>
<a id="tocspatchedorganization"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "owner": {
      "allOf": [
        {
          "type": "object",
          "properties": {
            "id": {
              "type": "string",
              "format": "uuid",
              "readOnly": true
            },
            "name": {
              "type": "string",
              "title": "真實姓名",
              "maxLength": 255
            }
          },
          "required": [
            "id",
            "name"
          ]
        }
      ],
      "readOnly": true
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    },
    "usageStatistics": {
      "type": "string",
      "readOnly": true
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|name|string|false|none|none|
|owner|[UserBase](#schemauserbase)|false|read-only|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|createdAt|string(timestamp)|false|read-only|none|
|usageStatistics|string|false|read-only|none|

<h2 id="tocS_PatchedUser">PatchedUser</h2>
<!-- backwards compatibility -->
<a id="schemapatcheduser"></a>
<a id="schema_PatchedUser"></a>
<a id="tocSpatcheduser"></a>
<a id="tocspatcheduser"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "avatar": {
      "type": "string",
      "format": "uri",
      "title": "大頭貼"
    },
    "name": {
      "type": "string",
      "title": "真實姓名",
      "maxLength": 255
    },
    "email": {
      "type": "string",
      "format": "email",
      "title": "公司信箱",
      "maxLength": 254
    },
    "company": {
      "type": "string",
      "title": "公司名稱",
      "maxLength": 255
    },
    "invitationCode": {
      "type": "string",
      "title": "邀請碼",
      "pattern": "^[A-Z0-9]+$",
      "maxLength": 31
    },
    "apiKeys": {
      "type": "string",
      "readOnly": true
    },
    "permissions": {
      "type": "string",
      "readOnly": true
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|avatar|string(uri)|false|none|none|
|name|string|false|none|none|
|email|string(email)|false|none|none|
|company|string|false|none|none|
|invitationCode|string|false|none|none|
|apiKeys|string|false|read-only|none|
|permissions|string|false|read-only|none|

<h2 id="tocS_PatchedWebChatBase">PatchedWebChatBase</h2>
<!-- backwards compatibility -->
<a id="schemapatchedwebchatbase"></a>
<a id="schema_PatchedWebChatBase"></a>
<a id="tocSpatchedwebchatbase"></a>
<a id="tocspatchedwebchatbase"></a>

```json
{
  "type": "object",
  "description": "Adds nested create feature",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "readOnly": true
    },
    "avatar": {
      "type": "string",
      "format": "uri",
      "nullable": true
    },
    "logo": {
      "type": "string",
      "format": "uri",
      "nullable": true
    },
    "description": {
      "type": "string",
      "title": "描述"
    },
    "cover": {
      "type": "string",
      "format": "uri",
      "nullable": true,
      "title": "封面"
    },
    "backUrl": {
      "type": "string",
      "title": "返回網址",
      "maxLength": 255
    },
    "isActive": {
      "type": "boolean",
      "title": "啟用"
    },
    "enableSpeech": {
      "type": "boolean",
      "readOnly": true,
      "title": "啟用語音"
    },
    "displayGreeting": {
      "type": "string",
      "readOnly": true
    },
    "displayConversationStarters": {
      "type": "string",
      "readOnly": true
    },
    "theme": {
      "type": "object",
      "properties": {
        "primaryColor": {
          "type": "string",
          "title": "主要顏色",
          "maxLength": 31
        },
        "dialogColor": {
          "type": "string",
          "title": "對話框顏色",
          "maxLength": 31
        },
        "navbarTextColor": {
          "type": "string",
          "title": "導覽列文字顏色",
          "maxLength": 31
        }
      }
    },
    "enableFileUpload": {
      "type": "boolean",
      "title": "是否允許上傳附件"
    },
    "enableDisplayCitations": {
      "type": "boolean",
      "title": "是否顯示引用"
    },
    "enableShareConversation": {
      "type": "boolean",
      "title": "啟用分享對話"
    },
    "enableLocation": {
      "type": "boolean",
      "title": "啟用定位"
    },
    "enableShowPoweredBy": {
      "type": "boolean",
      "title": "是否顯示技術支持"
    },
    "accessType": {
      "allOf": [
        {
          "enum": [
            "web",
            "admin",
            "api"
          ],
          "type": "string",
          "description": "* `web` - Web Chat\n* `admin` - Admin 問答\n* `api` - API"
        }
      ],
      "readOnly": true,
      "title": "存取類型"
    }
  }
}

```

Adds nested create feature

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|name|string|false|read-only|none|
|avatar|string(uri)¦null|false|none|none|
|logo|string(uri)¦null|false|none|none|
|description|string|false|none|none|
|cover|string(uri)¦null|false|none|none|
|backUrl|string|false|none|none|
|isActive|boolean|false|none|none|
|enableSpeech|boolean|false|read-only|none|
|displayGreeting|string|false|read-only|none|
|displayConversationStarters|string|false|read-only|none|
|theme|[Theme](#schematheme)|false|none|none|
|» primaryColor|string|false|none|none|
|» dialogColor|string|false|none|none|
|» navbarTextColor|string|false|none|none|
|enableFileUpload|boolean|false|none|none|
|enableDisplayCitations|boolean|false|none|none|
|enableShareConversation|boolean|false|none|none|
|enableLocation|boolean|false|none|none|
|enableShowPoweredBy|boolean|false|none|none|
|accessType|[AccessTypeEnum](#schemaaccesstypeenum)|false|read-only|* `web` - Web Chat<br>* `admin` - Admin 問答<br>* `api` - API|

#### Enumerated Values

|Property|Value|
|---|---|
|accessType|web|
|accessType|admin|
|accessType|api|

<h2 id="tocS_PatchedWorkflow">PatchedWorkflow</h2>
<!-- backwards compatibility -->
<a id="schemapatchedworkflow"></a>
<a id="schema_PatchedWorkflow"></a>
<a id="tocSpatchedworkflow"></a>
<a id="tocspatchedworkflow"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "chatbot": {
      "type": "string",
      "format": "uuid"
    },
    "metadata": {}
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|chatbot|string(uuid)|false|none|none|
|metadata|any|false|none|none|

<h2 id="tocS_Permission">Permission</h2>
<!-- backwards compatibility -->
<a id="schemapermission"></a>
<a id="schema_Permission"></a>
<a id="tocSpermission"></a>
<a id="tocspermission"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "description": {
      "type": "string",
      "title": "描述"
    }
  },
  "required": [
    "id",
    "name"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|description|string|false|none|none|

<h2 id="tocS_ProviderEnum">ProviderEnum</h2>
<!-- backwards compatibility -->
<a id="schemaproviderenum"></a>
<a id="schema_ProviderEnum"></a>
<a id="tocSproviderenum"></a>
<a id="tocsproviderenum"></a>

```json
{
  "enum": [
    "maiagent",
    "llama",
    "azure"
  ],
  "type": "string",
  "description": "* `maiagent` - MaiAgent\n* `llama` - Llama\n* `azure` - Azure"
}

```

* `maiagent` - MaiAgent
* `llama` - Llama
* `azure` - Azure

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ProviderEnum](#schemaproviderenum)|false|none|* `maiagent` - MaiAgent<br>* `llama` - Llama<br>* `azure` - Azure|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|maiagent|
|*anonymous*|llama|
|*anonymous*|azure|

<h2 id="tocS_QuietTrackingRecord">QuietTrackingRecord</h2>
<!-- backwards compatibility -->
<a id="schemaquiettrackingrecord"></a>
<a id="schema_QuietTrackingRecord"></a>
<a id="tocSquiettrackingrecord"></a>
<a id="tocsquiettrackingrecord"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "deviceId": {
      "type": "string",
      "title": "裝置 ID",
      "maxLength": 255
    },
    "metadata": {
      "nullable": true
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "createdAt",
    "deviceId",
    "id"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|deviceId|string|true|none|none|
|metadata|any|false|none|none|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_Rag">Rag</h2>
<!-- backwards compatibility -->
<a id="schemarag"></a>
<a id="schema_Rag"></a>
<a id="tocSrag"></a>
<a id="tocsrag"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "isDefault": {
      "type": "boolean",
      "title": "是否預設"
    },
    "isEmbeddingModelSelectable": {
      "type": "string",
      "readOnly": true
    },
    "isRerankerModelSelectable": {
      "type": "string",
      "readOnly": true
    },
    "isOutputFormatAvailable": {
      "type": "string",
      "readOnly": true
    }
  },
  "required": [
    "id",
    "isEmbeddingModelSelectable",
    "isOutputFormatAvailable",
    "isRerankerModelSelectable",
    "name"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|isDefault|boolean|false|none|none|
|isEmbeddingModelSelectable|string|true|read-only|none|
|isRerankerModelSelectable|string|true|read-only|none|
|isOutputFormatAvailable|string|true|read-only|none|

<h2 id="tocS_ReplyModeEnum">ReplyModeEnum</h2>
<!-- backwards compatibility -->
<a id="schemareplymodeenum"></a>
<a id="schema_ReplyModeEnum"></a>
<a id="tocSreplymodeenum"></a>
<a id="tocsreplymodeenum"></a>

```json
{
  "enum": [
    "normal",
    "template",
    "hybrid"
  ],
  "type": "string",
  "description": "* `normal` - 正常\n* `template` - 模板\n* `hybrid` - 混合"
}

```

* `normal` - 正常
* `template` - 模板
* `hybrid` - 混合

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ReplyModeEnum](#schemareplymodeenum)|false|none|* `normal` - 正常<br>* `template` - 模板<br>* `hybrid` - 混合|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|normal|
|*anonymous*|template|
|*anonymous*|hybrid|

<h2 id="tocS_RerankerModel">RerankerModel</h2>
<!-- backwards compatibility -->
<a id="schemarerankermodel"></a>
<a id="schema_RerankerModel"></a>
<a id="tocSrerankermodel"></a>
<a id="tocsrerankermodel"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "名稱",
      "maxLength": 255
    },
    "isDefault": {
      "type": "boolean",
      "title": "是否預設"
    }
  },
  "required": [
    "id",
    "name"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|isDefault|boolean|false|none|none|

<h2 id="tocS_ResendEmailVerification">ResendEmailVerification</h2>
<!-- backwards compatibility -->
<a id="schemaresendemailverification"></a>
<a id="schema_ResendEmailVerification"></a>
<a id="tocSresendemailverification"></a>
<a id="tocsresendemailverification"></a>

```json
{
  "type": "object",
  "properties": {
    "email": {
      "type": "string",
      "format": "email"
    }
  },
  "required": [
    "email"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|email|string(email)|true|none|none|

<h2 id="tocS_RestAuthDetail">RestAuthDetail</h2>
<!-- backwards compatibility -->
<a id="schemarestauthdetail"></a>
<a id="schema_RestAuthDetail"></a>
<a id="tocSrestauthdetail"></a>
<a id="tocsrestauthdetail"></a>

```json
{
  "type": "object",
  "properties": {
    "detail": {
      "type": "string",
      "readOnly": true
    }
  },
  "required": [
    "detail"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|detail|string|true|read-only|none|

<h2 id="tocS_Sender">Sender</h2>
<!-- backwards compatibility -->
<a id="schemasender"></a>
<a id="schema_Sender"></a>
<a id="tocSsender"></a>
<a id="tocssender"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer"
    },
    "name": {
      "type": "string"
    },
    "avatar": {
      "type": "string",
      "format": "uri"
    }
  },
  "required": [
    "avatar",
    "id",
    "name"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|name|string|true|none|none|
|avatar|string(uri)|true|none|none|

<h2 id="tocS_Status235Enum">Status235Enum</h2>
<!-- backwards compatibility -->
<a id="schemastatus235enum"></a>
<a id="schema_Status235Enum"></a>
<a id="tocSstatus235enum"></a>
<a id="tocsstatus235enum"></a>

```json
{
  "enum": [
    "processing",
    "done",
    "cancelled"
  ],
  "type": "string",
  "description": "* `processing` - Processing\n* `done` - Done\n* `cancelled` - Cancelled"
}

```

* `processing` - Processing
* `done` - Done
* `cancelled` - Cancelled

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Status235Enum](#schemastatus235enum)|false|none|* `processing` - Processing<br>* `done` - Done<br>* `cancelled` - Cancelled|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|processing|
|*anonymous*|done|
|*anonymous*|cancelled|

<h2 id="tocS_StatusBbcEnum">StatusBbcEnum</h2>
<!-- backwards compatibility -->
<a id="schemastatusbbcenum"></a>
<a id="schema_StatusBbcEnum"></a>
<a id="tocSstatusbbcenum"></a>
<a id="tocsstatusbbcenum"></a>

```json
{
  "enum": [
    "initial",
    "processing",
    "done",
    "deleting",
    "failed"
  ],
  "type": "string",
  "description": "* `initial` - Initial\n* `processing` - Processing\n* `done` - Done\n* `deleting` - Deleting\n* `failed` - Failed"
}

```

* `initial` - Initial
* `processing` - Processing
* `done` - Done
* `deleting` - Deleting
* `failed` - Failed

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[StatusBbcEnum](#schemastatusbbcenum)|false|none|* `initial` - Initial<br>* `processing` - Processing<br>* `done` - Done<br>* `deleting` - Deleting<br>* `failed` - Failed|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|initial|
|*anonymous*|processing|
|*anonymous*|done|
|*anonymous*|deleting|
|*anonymous*|failed|

<h2 id="tocS_Theme">Theme</h2>
<!-- backwards compatibility -->
<a id="schematheme"></a>
<a id="schema_Theme"></a>
<a id="tocStheme"></a>
<a id="tocstheme"></a>

```json
{
  "type": "object",
  "properties": {
    "primaryColor": {
      "type": "string",
      "title": "主要顏色",
      "maxLength": 31
    },
    "dialogColor": {
      "type": "string",
      "title": "對話框顏色",
      "maxLength": 31
    },
    "navbarTextColor": {
      "type": "string",
      "title": "導覽列文字顏色",
      "maxLength": 31
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|primaryColor|string|false|none|none|
|dialogColor|string|false|none|none|
|navbarTextColor|string|false|none|none|

<h2 id="tocS_TokenRefresh">TokenRefresh</h2>
<!-- backwards compatibility -->
<a id="schematokenrefresh"></a>
<a id="schema_TokenRefresh"></a>
<a id="tocStokenrefresh"></a>
<a id="tocstokenrefresh"></a>

```json
{
  "type": "object",
  "properties": {
    "access": {
      "type": "string",
      "readOnly": true
    },
    "refresh": {
      "type": "string",
      "writeOnly": true
    }
  },
  "required": [
    "access",
    "refresh"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|access|string|true|read-only|none|
|refresh|string|true|write-only|none|

<h2 id="tocS_TokenVerify">TokenVerify</h2>
<!-- backwards compatibility -->
<a id="schematokenverify"></a>
<a id="schema_TokenVerify"></a>
<a id="tocStokenverify"></a>
<a id="tocstokenverify"></a>

```json
{
  "type": "object",
  "properties": {
    "token": {
      "type": "string",
      "writeOnly": true
    }
  },
  "required": [
    "token"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|token|string|true|write-only|none|

<h2 id="tocS_TypeEnum">TypeEnum</h2>
<!-- backwards compatibility -->
<a id="schematypeenum"></a>
<a id="schema_TypeEnum"></a>
<a id="tocStypeenum"></a>
<a id="tocstypeenum"></a>

```json
{
  "enum": [
    "image",
    "video",
    "audio",
    "sticker",
    "other"
  ],
  "type": "string",
  "description": "* `image` - Image\n* `video` - Video\n* `audio` - Audio\n* `sticker` - Sticker\n* `other` - Other"
}

```

* `image` - Image
* `video` - Video
* `audio` - Audio
* `sticker` - Sticker
* `other` - Other

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[TypeEnum](#schematypeenum)|false|none|* `image` - Image<br>* `video` - Video<br>* `audio` - Audio<br>* `sticker` - Sticker<br>* `other` - Other|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|image|
|*anonymous*|video|
|*anonymous*|audio|
|*anonymous*|sticker|
|*anonymous*|other|

<h2 id="tocS_User">User</h2>
<!-- backwards compatibility -->
<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "avatar": {
      "type": "string",
      "format": "uri",
      "title": "大頭貼"
    },
    "name": {
      "type": "string",
      "title": "真實姓名",
      "maxLength": 255
    },
    "email": {
      "type": "string",
      "format": "email",
      "title": "公司信箱",
      "maxLength": 254
    },
    "company": {
      "type": "string",
      "title": "公司名稱",
      "maxLength": 255
    },
    "invitationCode": {
      "type": "string",
      "title": "邀請碼",
      "pattern": "^[A-Z0-9]+$",
      "maxLength": 31
    },
    "apiKeys": {
      "type": "string",
      "readOnly": true
    },
    "permissions": {
      "type": "string",
      "readOnly": true
    }
  },
  "required": [
    "apiKeys",
    "email",
    "id",
    "invitationCode",
    "name",
    "permissions"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|avatar|string(uri)|false|none|none|
|name|string|true|none|none|
|email|string(email)|true|none|none|
|company|string|false|none|none|
|invitationCode|string|true|none|none|
|apiKeys|string|true|read-only|none|
|permissions|string|true|read-only|none|

<h2 id="tocS_UserBase">UserBase</h2>
<!-- backwards compatibility -->
<a id="schemauserbase"></a>
<a id="schema_UserBase"></a>
<a id="tocSuserbase"></a>
<a id="tocsuserbase"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "title": "真實姓名",
      "maxLength": 255
    }
  },
  "required": [
    "id",
    "name"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|

<h2 id="tocS_VerifyEmail">VerifyEmail</h2>
<!-- backwards compatibility -->
<a id="schemaverifyemail"></a>
<a id="schema_VerifyEmail"></a>
<a id="tocSverifyemail"></a>
<a id="tocsverifyemail"></a>

```json
{
  "type": "object",
  "properties": {
    "key": {
      "type": "string",
      "writeOnly": true
    }
  },
  "required": [
    "key"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|key|string|true|write-only|none|

<h2 id="tocS_WebChatBase">WebChatBase</h2>
<!-- backwards compatibility -->
<a id="schemawebchatbase"></a>
<a id="schema_WebChatBase"></a>
<a id="tocSwebchatbase"></a>
<a id="tocswebchatbase"></a>

```json
{
  "type": "object",
  "description": "Adds nested create feature",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "name": {
      "type": "string",
      "readOnly": true
    },
    "avatar": {
      "type": "string",
      "format": "uri",
      "nullable": true
    },
    "logo": {
      "type": "string",
      "format": "uri",
      "nullable": true
    },
    "description": {
      "type": "string",
      "title": "描述"
    },
    "cover": {
      "type": "string",
      "format": "uri",
      "nullable": true,
      "title": "封面"
    },
    "backUrl": {
      "type": "string",
      "title": "返回網址",
      "maxLength": 255
    },
    "isActive": {
      "type": "boolean",
      "title": "啟用"
    },
    "enableSpeech": {
      "type": "boolean",
      "readOnly": true,
      "title": "啟用語音"
    },
    "displayGreeting": {
      "type": "string",
      "readOnly": true
    },
    "displayConversationStarters": {
      "type": "string",
      "readOnly": true
    },
    "theme": {
      "type": "object",
      "properties": {
        "primaryColor": {
          "type": "string",
          "title": "主要顏色",
          "maxLength": 31
        },
        "dialogColor": {
          "type": "string",
          "title": "對話框顏色",
          "maxLength": 31
        },
        "navbarTextColor": {
          "type": "string",
          "title": "導覽列文字顏色",
          "maxLength": 31
        }
      }
    },
    "enableFileUpload": {
      "type": "boolean",
      "title": "是否允許上傳附件"
    },
    "enableDisplayCitations": {
      "type": "boolean",
      "title": "是否顯示引用"
    },
    "enableShareConversation": {
      "type": "boolean",
      "title": "啟用分享對話"
    },
    "enableLocation": {
      "type": "boolean",
      "title": "啟用定位"
    },
    "enableShowPoweredBy": {
      "type": "boolean",
      "title": "是否顯示技術支持"
    },
    "accessType": {
      "allOf": [
        {
          "enum": [
            "web",
            "admin",
            "api"
          ],
          "type": "string",
          "description": "* `web` - Web Chat\n* `admin` - Admin 問答\n* `api` - API"
        }
      ],
      "readOnly": true,
      "title": "存取類型"
    }
  },
  "required": [
    "accessType",
    "displayConversationStarters",
    "displayGreeting",
    "enableSpeech",
    "id",
    "name",
    "theme"
  ]
}

```

Adds nested create feature

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|read-only|none|
|avatar|string(uri)¦null|false|none|none|
|logo|string(uri)¦null|false|none|none|
|description|string|false|none|none|
|cover|string(uri)¦null|false|none|none|
|backUrl|string|false|none|none|
|isActive|boolean|false|none|none|
|enableSpeech|boolean|true|read-only|none|
|displayGreeting|string|true|read-only|none|
|displayConversationStarters|string|true|read-only|none|
|theme|[Theme](#schematheme)|true|none|none|
|» primaryColor|string|false|none|none|
|» dialogColor|string|false|none|none|
|» navbarTextColor|string|false|none|none|
|enableFileUpload|boolean|false|none|none|
|enableDisplayCitations|boolean|false|none|none|
|enableShareConversation|boolean|false|none|none|
|enableLocation|boolean|false|none|none|
|enableShowPoweredBy|boolean|false|none|none|
|accessType|[AccessTypeEnum](#schemaaccesstypeenum)|true|read-only|* `web` - Web Chat<br>* `admin` - Admin 問答<br>* `api` - API|

#### Enumerated Values

|Property|Value|
|---|---|
|accessType|web|
|accessType|admin|
|accessType|api|

<h2 id="tocS_WebChatList">WebChatList</h2>
<!-- backwards compatibility -->
<a id="schemawebchatlist"></a>
<a id="schema_WebChatList"></a>
<a id="tocSwebchatlist"></a>
<a id="tocswebchatlist"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "avatar": {
      "type": "string",
      "format": "uri",
      "nullable": true,
      "title": "大頭貼"
    },
    "name": {
      "type": "string",
      "readOnly": true
    }
  },
  "required": [
    "id",
    "name"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|avatar|string(uri)¦null|false|none|none|
|name|string|true|read-only|none|

<h2 id="tocS_WebhookRecord">WebhookRecord</h2>
<!-- backwards compatibility -->
<a id="schemawebhookrecord"></a>
<a id="schema_WebhookRecord"></a>
<a id="tocSwebhookrecord"></a>
<a id="tocswebhookrecord"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "chatbot": {
      "type": "object",
      "description": "Adds nested create feature",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "workflow": {
          "type": "string",
          "format": "uuid",
          "readOnly": true
        },
        "name": {
          "type": "string",
          "title": "名稱",
          "maxLength": 255
        },
        "largeLanguageModel": {
          "type": "string",
          "format": "uuid"
        },
        "rag": {
          "type": "string",
          "format": "uuid"
        },
        "embeddingModel": {
          "type": "string",
          "format": "uuid",
          "nullable": true
        },
        "rerankerModel": {
          "type": "string",
          "format": "uuid",
          "nullable": true
        },
        "instructions": {
          "type": "string",
          "title": "指令"
        },
        "webhookUrl": {
          "type": "string",
          "format": "uri",
          "nullable": true,
          "maxLength": 511
        },
        "apiWebChatId": {
          "type": "string",
          "readOnly": true,
          "nullable": true,
          "title": "API WebChat ID"
        },
        "updatedAt": {
          "type": "string",
          "format": "timestamp",
          "readOnly": true,
          "title": "更新時間",
          "pattern": "^\\d{13}$"
        },
        "organization": {
          "type": "string",
          "format": "uuid"
        },
        "builtInWorkflow": {
          "type": "string",
          "format": "uuid",
          "nullable": true
        },
        "replyMode": {
          "allOf": [
            {
              "enum": [
                "normal",
                "template",
                "hybrid"
              ],
              "type": "string",
              "description": "* `normal` - 正常\n* `template` - 模板\n* `hybrid` - 混合"
            }
          ],
          "title": "回傳模式"
        },
        "template": {
          "type": "string",
          "nullable": true,
          "title": "模板"
        },
        "unanswerableTemplate": {
          "type": "string",
          "nullable": true,
          "title": "無法回答時的模板"
        },
        "totalLlmWordCount": {
          "type": "integer",
          "maximum": 9223372036854776000,
          "minimum": -9223372036854776000,
          "format": "int64",
          "title": "LLM 使用總字數",
          "description": "累積的 LLM 使用總字數"
        },
        "enableChineseConversion": {
          "type": "boolean"
        },
        "outputFormat": {
          "nullable": true
        }
      },
      "required": [
        "apiWebChatId",
        "id",
        "largeLanguageModel",
        "name",
        "rag",
        "updatedAt",
        "workflow"
      ]
    },
    "url": {
      "type": "string"
    },
    "requestBody": {
      "nullable": true
    },
    "response": {
      "type": "string"
    },
    "statusCode": {
      "type": "integer",
      "maximum": 2147483647,
      "minimum": -2147483648,
      "nullable": true
    },
    "createdAt": {
      "type": "string",
      "format": "timestamp",
      "readOnly": true,
      "title": "建立時間",
      "pattern": "^\\d{13}$"
    }
  },
  "required": [
    "chatbot",
    "createdAt",
    "id",
    "url"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|chatbot|[Chatbot](#schemachatbot)|true|none|Adds nested create feature|
|» id|string(uuid)|true|read-only|none|
|» workflow|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» largeLanguageModel|string(uuid)|true|none|none|
|» rag|string(uuid)|true|none|none|
|» embeddingModel|string(uuid)¦null|false|none|none|
|» rerankerModel|string(uuid)¦null|false|none|none|
|» instructions|string|false|none|none|
|» webhookUrl|string(uri)¦null|false|none|none|
|» apiWebChatId|string¦null|true|read-only|none|
|» updatedAt|string(timestamp)|true|read-only|none|
|» organization|string(uuid)|false|none|none|
|» builtInWorkflow|string(uuid)¦null|false|none|none|
|» replyMode|[ReplyModeEnum](#schemareplymodeenum)|false|none|* `normal` - 正常<br>* `template` - 模板<br>* `hybrid` - 混合|
|» template|string¦null|false|none|none|
|» unanswerableTemplate|string¦null|false|none|none|
|» totalLlmWordCount|integer(int64)|false|none|累積的 LLM 使用總字數|
|» enableChineseConversion|boolean|false|none|none|
|» outputFormat|any|false|none|none|
|url|string|true|none|none|
|requestBody|any|false|none|none|
|response|string|false|none|none|
|statusCode|integer¦null|false|none|none|
|createdAt|string(timestamp)|true|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|replyMode|normal|
|replyMode|template|
|replyMode|hybrid|

<h2 id="tocS_Workflow">Workflow</h2>
<!-- backwards compatibility -->
<a id="schemaworkflow"></a>
<a id="schema_Workflow"></a>
<a id="tocSworkflow"></a>
<a id="tocsworkflow"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string",
      "format": "uuid",
      "readOnly": true
    },
    "chatbot": {
      "type": "string",
      "format": "uuid"
    },
    "metadata": {}
  },
  "required": [
    "chatbot",
    "id"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|chatbot|string(uuid)|true|none|none|
|metadata|any|false|none|none|

