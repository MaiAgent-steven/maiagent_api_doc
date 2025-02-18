<!-- Generator: Widdershins v4.0.1 -->

<h1 id="maiagent-api">MaiAgent API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Documentation of API endpoints of MaiAgent

# Authentication

* API Key (ApiKeyAuth)
    - Parameter Name: **Authorization**, in: header. 

<h1 id="maiagent-api-allowed-file-types">allowed-file-types</h1>

## allowedFileTypesRetrieve

<a id="opIdallowedFileTypesRetrieve"></a>

`GET /api/allowed-file-types/`

<h3 id="allowedfiletypesretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

<h1 id="maiagent-api-attachments">attachments</h1>

## attachmentsList

<a id="opIdattachmentsList"></a>

`GET /api/attachments/`

<h3 id="attachmentslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "type": "other",
      "filename": "string",
      "file": "http://example.com"
    }
  ]
}
```

<h3 id="attachmentslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedAttachmentList](#schemapaginatedattachmentlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## attachmentsCreate

<a id="opIdattachmentsCreate"></a>

`POST /api/attachments/`

> Body parameter

```json
{
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="attachmentscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Attachment](#schemaattachment)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="attachmentscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Attachment](#schemaattachment)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## attachmentsRetrieve

<a id="opIdattachmentsRetrieve"></a>

`GET /api/attachments/{id}/`

<h3 id="attachmentsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this attachment.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="attachmentsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Attachment](#schemaattachment)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## attachmentsUpdate

<a id="opIdattachmentsUpdate"></a>

`PUT /api/attachments/{id}/`

> Body parameter

```json
{
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="attachmentsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this attachment.|
|body|body|[Attachment](#schemaattachment)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="attachmentsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Attachment](#schemaattachment)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## attachmentsPartialUpdate

<a id="opIdattachmentsPartialUpdate"></a>

`PATCH /api/attachments/{id}/`

> Body parameter

```json
{
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="attachmentspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this attachment.|
|body|body|[PatchedAttachment](#schemapatchedattachment)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="attachmentspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Attachment](#schemaattachment)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## attachmentsDestroy

<a id="opIdattachmentsDestroy"></a>

`DELETE /api/attachments/{id}/`

<h3 id="attachmentsdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this attachment.|

<h3 id="attachmentsdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="maiagent-api-auth-token">auth-token</h1>

## authTokenCreate

<a id="opIdauthTokenCreate"></a>

`POST /api/auth-token/`

> Body parameter

```json
{
  "username": "string",
  "password": "string"
}
```

```yaml
username: string
password: string

```

<h3 id="authtokencreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AuthToken](#schemaauthtoken)|true|none|

> Example responses

> 200 Response

```json
{
  "token": "string"
}
```

<h3 id="authtokencreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[AuthToken](#schemaauthtoken)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="maiagent-api-auth">auth</h1>

## authKeycloakLoginCreate

<a id="opIdauthKeycloakLoginCreate"></a>

`POST /api/auth/keycloak/login/`

> Body parameter

```json
{
  "serverUrl": "http://example.com",
  "realm": "string",
  "clientId": "string",
  "accessToken": "string",
  "refreshToken": "string"
}
```

<h3 id="authkeycloaklogincreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Keycloak](#schemakeycloak)|true|none|

> Example responses

> 200 Response

```json
{
  "serverUrl": "http://example.com",
  "realm": "string",
  "clientId": "string",
  "accessToken": "string",
  "refreshToken": "string"
}
```

<h3 id="authkeycloaklogincreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Keycloak](#schemakeycloak)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## authKeycloakLogoutCreate

<a id="opIdauthKeycloakLogoutCreate"></a>

`POST /api/auth/keycloak/logout/`

> Body parameter

```json
{
  "serverUrl": "http://example.com",
  "realm": "string",
  "clientId": "string",
  "accessToken": "string",
  "refreshToken": "string"
}
```

<h3 id="authkeycloaklogoutcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Keycloak](#schemakeycloak)|true|none|

> Example responses

> 200 Response

```json
{
  "serverUrl": "http://example.com",
  "realm": "string",
  "clientId": "string",
  "accessToken": "string",
  "refreshToken": "string"
}
```

<h3 id="authkeycloaklogoutcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Keycloak](#schemakeycloak)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## authLoginCreate

<a id="opIdauthLoginCreate"></a>

`POST /api/auth/login/`

Check the credentials and return the REST Token
if the credentials are valid and authenticated.
Calls Django Auth login method to register User ID
in Django session framework

Accept the following POST parameters: username, password
Return the REST Framework Token Object's key.

> Body parameter

```json
{
  "username": "string",
  "email": "user@example.com",
  "password": "string"
}
```

<h3 id="authlogincreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Login](#schemalogin)|true|none|

> Example responses

> 200 Response

```json
{
  "access": "string",
  "refresh": "string",
  "user": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "avatar": "http://example.com",
    "name": "string",
    "email": "user@example.com",
    "company": "string",
    "invitationCode": "string",
    "apiKeys": "string",
    "permissions": "string"
  }
}
```

<h3 id="authlogincreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[JWT](#schemajwt)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## authLogoutCreate

<a id="opIdauthLogoutCreate"></a>

`POST /api/auth/logout/`

Calls Django logout method and delete the Token object
assigned to the current User object.

Accepts/Returns nothing.

> Example responses

> 200 Response

```json
{
  "detail": "string"
}
```

<h3 id="authlogoutcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RestAuthDetail](#schemarestauthdetail)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## authPasswordChangeCreate

<a id="opIdauthPasswordChangeCreate"></a>

`POST /api/auth/password/change/`

Calls Django Auth SetPasswordForm save method.

Accepts the following POST parameters: new_password1, new_password2
Returns the success/fail message.

> Body parameter

```json
{
  "oldPassword": "string",
  "newPassword1": "string",
  "newPassword2": "string"
}
```

<h3 id="authpasswordchangecreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PasswordChange](#schemapasswordchange)|true|none|

> Example responses

> 200 Response

```json
{
  "detail": "string"
}
```

<h3 id="authpasswordchangecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RestAuthDetail](#schemarestauthdetail)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## authPasswordResetCreate

<a id="opIdauthPasswordResetCreate"></a>

`POST /api/auth/password/reset/`

Calls Django Auth PasswordResetForm save method.

Accepts the following POST parameters: email
Returns the success/fail message.

> Body parameter

```json
{
  "email": "user@example.com"
}
```

<h3 id="authpasswordresetcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PasswordReset](#schemapasswordreset)|true|none|

> Example responses

> 200 Response

```json
{
  "detail": "string"
}
```

<h3 id="authpasswordresetcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RestAuthDetail](#schemarestauthdetail)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## authPasswordResetConfirmCreate

<a id="opIdauthPasswordResetConfirmCreate"></a>

`POST /api/auth/password/reset/confirm/`

Password reset e-mail link is confirmed, therefore
this resets the user's password.

Accepts the following POST parameters: token, uid,
    new_password1, new_password2
Returns the success/fail message.

> Body parameter

```json
{
  "newPassword1": "string",
  "newPassword2": "string",
  "uid": "string",
  "token": "string"
}
```

<h3 id="authpasswordresetconfirmcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PasswordResetConfirm](#schemapasswordresetconfirm)|true|none|

> Example responses

> 200 Response

```json
{
  "detail": "string"
}
```

<h3 id="authpasswordresetconfirmcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RestAuthDetail](#schemarestauthdetail)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## authRegistrationCreate

<a id="opIdauthRegistrationCreate"></a>

`POST /api/auth/registration/`

Registers a new user.

Accepts the following POST parameters: username, email, password1, password2.

> Body parameter

```json
{
  "username": "string",
  "email": "user@example.com",
  "password1": "string",
  "password2": "string",
  "name": "string",
  "company": "string",
  "referralCode": "string"
}
```

<h3 id="authregistrationcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CustomizedRegister](#schemacustomizedregister)|true|none|

> Example responses

> 201 Response

```json
{
  "detail": "string"
}
```

<h3 id="authregistrationcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[RestAuthDetail](#schemarestauthdetail)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## authRegistrationResendEmailCreate

<a id="opIdauthRegistrationResendEmailCreate"></a>

`POST /api/auth/registration/resend-email/`

Resends another email to an unverified email.

Accepts the following POST parameter: email.

> Body parameter

```json
{
  "email": "user@example.com"
}
```

<h3 id="authregistrationresendemailcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ResendEmailVerification](#schemaresendemailverification)|true|none|

> Example responses

> 201 Response

```json
{
  "detail": "string"
}
```

<h3 id="authregistrationresendemailcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[RestAuthDetail](#schemarestauthdetail)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## authRegistrationVerifyEmailCreate

<a id="opIdauthRegistrationVerifyEmailCreate"></a>

`POST /api/auth/registration/verify-email/`

Verifies the email associated with the provided key.

Accepts the following POST parameter: key.

> Body parameter

```json
{
  "key": "string"
}
```

<h3 id="authregistrationverifyemailcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[VerifyEmail](#schemaverifyemail)|true|none|

> Example responses

> 200 Response

```json
{
  "detail": "string"
}
```

<h3 id="authregistrationverifyemailcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RestAuthDetail](#schemarestauthdetail)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## authTokenRefreshCreate

<a id="opIdauthTokenRefreshCreate"></a>

`POST /api/auth/token/refresh/`

Takes a refresh type JSON web token and returns an access type JSON web
token if the refresh token is valid.

> Body parameter

```json
{
  "refresh": "string"
}
```

<h3 id="authtokenrefreshcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TokenRefresh](#schematokenrefresh)|true|none|

> Example responses

> 200 Response

```json
{
  "access": "string"
}
```

<h3 id="authtokenrefreshcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[TokenRefresh](#schematokenrefresh)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## authTokenVerifyCreate

<a id="opIdauthTokenVerifyCreate"></a>

`POST /api/auth/token/verify/`

Takes a token and indicates if it is valid.  This view provides no
information about a token's fitness for a particular use.

> Body parameter

```json
{
  "token": "string"
}
```

<h3 id="authtokenverifycreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TokenVerify](#schematokenverify)|true|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="authtokenverifycreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[TokenVerify](#schematokenverify)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## authUserRetrieve

<a id="opIdauthUserRetrieve"></a>

`GET /api/auth/user/`

Reads and updates UserModel fields
Accepts GET, PUT, PATCH methods.

Default accepted fields: username, first_name, last_name
Default display fields: pk, username, email, first_name, last_name
Read-only fields: pk, email

Returns UserModel fields.

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="authuserretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## authUserUpdate

<a id="opIdauthUserUpdate"></a>

`PUT /api/auth/user/`

Reads and updates UserModel fields
Accepts GET, PUT, PATCH methods.

Default accepted fields: username, first_name, last_name
Default display fields: pk, username, email, first_name, last_name
Read-only fields: pk, email

Returns UserModel fields.

> Body parameter

```json
{
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string"
}
```

<h3 id="authuserupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[User](#schemauser)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="authuserupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## authUserPartialUpdate

<a id="opIdauthUserPartialUpdate"></a>

`PATCH /api/auth/user/`

Reads and updates UserModel fields
Accepts GET, PUT, PATCH methods.

Default accepted fields: username, first_name, last_name
Default display fields: pk, username, email, first_name, last_name
Read-only fields: pk, email

Returns UserModel fields.

> Body parameter

```json
{
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string"
}
```

<h3 id="authuserpartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PatchedUser](#schemapatcheduser)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="authuserpartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="maiagent-api-built-in-workflows">built-in-workflows</h1>

## builtInWorkflowsList

<a id="opIdbuiltInWorkflowsList"></a>

`GET /api/built-in-workflows/`

> Example responses

> 200 Response

```json
[
  {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string"
  }
]
```

<h3 id="builtinworkflowslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="builtinworkflowslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[BuiltInWorkflow](#schemabuiltinworkflow)]|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="maiagent-api-chatbots">Chatbots</h1>

## chatbotFileContentsRetrieve

<a id="opIdchatbotFileContentsRetrieve"></a>

`GET /api/chatbot-file-contents/{id}/`

<h3 id="chatbotfilecontentsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案內容.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "content": "string",
  "modifiedContent": "string",
  "type": "string",
  "updatedAt": "string"
}
```

<h3 id="chatbotfilecontentsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFileContent](#schemachatbotfilecontent)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotFileContentsUpdate

<a id="opIdchatbotFileContentsUpdate"></a>

`PUT /api/chatbot-file-contents/{id}/`

> Body parameter

```json
{
  "modifiedContent": "string"
}
```

<h3 id="chatbotfilecontentsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案內容.|
|body|body|[ChatbotFileContent](#schemachatbotfilecontent)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "content": "string",
  "modifiedContent": "string",
  "type": "string",
  "updatedAt": "string"
}
```

<h3 id="chatbotfilecontentsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFileContent](#schemachatbotfilecontent)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotFileContentsPartialUpdate

<a id="opIdchatbotFileContentsPartialUpdate"></a>

`PATCH /api/chatbot-file-contents/{id}/`

> Body parameter

```json
{
  "modifiedContent": "string"
}
```

<h3 id="chatbotfilecontentspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案內容.|
|body|body|[PatchedChatbotFileContent](#schemapatchedchatbotfilecontent)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "content": "string",
  "modifiedContent": "string",
  "type": "string",
  "updatedAt": "string"
}
```

<h3 id="chatbotfilecontentspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFileContent](#schemachatbotfilecontent)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotSettingsList

<a id="opIdchatbotSettingsList"></a>

`GET /api/chatbot-settings/`

用於返回以 RAG 為主的 chatbot 設定列表。
每個 RAG 會包含與其相容的 LLMs。

> Example responses

> 200 Response

```json
[
  {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "llms": "string",
    "isDefault": true,
    "isSearchSelectable": "string",
    "isWorkflowSelectable": "string",
    "isRerankerModelSelectable": "string",
    "isEmbeddingModelSelectable": "string"
  }
]
```

<h3 id="chatbotsettingslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="chatbotsettingslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[ChatbotSetting](#schemachatbotsetting)]|false|none|[用於返回以 RAG 為主的 chatbot 設定]|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» llms|string|true|read-only|none|
|» isDefault|boolean|false|none|none|
|» isSearchSelectable|string|true|read-only|none|
|» isWorkflowSelectable|string|true|read-only|none|
|» isRerankerModelSelectable|string|true|read-only|none|
|» isEmbeddingModelSelectable|string|true|read-only|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsList

<a id="opIdchatbotsList"></a>

`GET /api/chatbots/`

<h3 id="chatbotslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "largeLanguageModel": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string"
      },
      "rag": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string"
      },
      "embeddingModel": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "isDefault": true
      },
      "rerankerModel": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "isDefault": true
      },
      "updatedAt": "string",
      "enableChineseConversion": true
    }
  ]
}
```

<h3 id="chatbotslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedChatbotListList](#schemapaginatedchatbotlistlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsCreate

<a id="opIdchatbotsCreate"></a>

`POST /api/chatbots/`

> Body parameter

```json
{
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="chatbotscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Chatbot](#schemachatbot)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="chatbotscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Chatbot](#schemachatbot)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsCrawlPageRequestsList

<a id="opIdchatbotsCrawlPageRequestsList"></a>

`GET /api/chatbots/{chatbotPk}/crawl-page-requests/`

<h3 id="chatbotscrawlpagerequestslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "url": "http://example.com",
      "status": "processing",
      "createdAt": "string"
    }
  ]
}
```

<h3 id="chatbotscrawlpagerequestslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedCrawlPageRequestList](#schemapaginatedcrawlpagerequestlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsCrawlPageRequestsCreate

<a id="opIdchatbotsCrawlPageRequestsCreate"></a>

`POST /api/chatbots/{chatbotPk}/crawl-page-requests/`

> Body parameter

```json
{
  "url": "http://example.com",
  "status": "processing"
}
```

<h3 id="chatbotscrawlpagerequestscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|body|body|[CrawlPageRequestCreate](#schemacrawlpagerequestcreate)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "url": "http://example.com",
  "status": "processing"
}
```

<h3 id="chatbotscrawlpagerequestscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[CrawlPageRequestCreate](#schemacrawlpagerequestcreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsCrawlPageRequestsCrawlPagesList

<a id="opIdchatbotsCrawlPageRequestsCrawlPagesList"></a>

`GET /api/chatbots/{chatbotPk}/crawl-page-requests/{crawlPageRequestPk}/crawl-pages/`

<h3 id="chatbotscrawlpagerequestscrawlpageslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string|true|none|
|crawlPageRequestPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "url": "http://example.com",
      "title": "string",
      "status": "pending",
      "isOriginalPage": true
    }
  ]
}
```

<h3 id="chatbotscrawlpagerequestscrawlpageslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedCrawlPageList](#schemapaginatedcrawlpagelist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsCrawlPageRequestsCrawlPagesImportFileCreate

<a id="opIdchatbotsCrawlPageRequestsCrawlPagesImportFileCreate"></a>

`POST /api/chatbots/{chatbotPk}/crawl-page-requests/{crawlPageRequestPk}/crawl-pages/{id}/import-file/`

將爬取的網頁內容匯入為聊天機器人檔案。

此方法會檢查爬取頁面的狀態，如果頁面不是正在處理中的狀態，
則會啟動非同步任務將網頁內容轉換為聊天機器人可用的檔案格式。

Args:
    request (HttpRequest): HTTP 請求物件
    *args: 可變位置參數
    **kwargs: 可變關鍵字參數，包含爬取頁面的識別碼

Returns:
    Response: 包含更新後的爬取頁面序列化資料的回應

Raises:
    ValidationError: 當爬取頁面已在處理中時拋出

> Body parameter

```json
{
  "url": "http://example.com",
  "title": "string",
  "status": "pending",
  "isOriginalPage": true
}
```

<h3 id="chatbotscrawlpagerequestscrawlpagesimportfilecreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string|true|none|
|crawlPageRequestPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this 爬取網頁.|
|body|body|[CrawlPage](#schemacrawlpage)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "url": "http://example.com",
  "title": "string",
  "status": "pending",
  "isOriginalPage": true
}
```

<h3 id="chatbotscrawlpagerequestscrawlpagesimportfilecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[CrawlPage](#schemacrawlpage)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsFaqsList

<a id="opIdchatbotsFaqsList"></a>

`GET /api/chatbots/{chatbotPk}/faqs/`

<h3 id="chatbotsfaqslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "question": "string",
      "answer": "string",
      "hitsCount": 0
    }
  ]
}
```

<h3 id="chatbotsfaqslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedFaqList](#schemapaginatedfaqlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsFaqsCreate

<a id="opIdchatbotsFaqsCreate"></a>

`POST /api/chatbots/{chatbotPk}/faqs/`

> Body parameter

```json
{
  "question": "string",
  "answer": "string"
}
```

<h3 id="chatbotsfaqscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|body|body|[FaqCreate](#schemafaqcreate)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "question": "string",
  "answer": "string"
}
```

<h3 id="chatbotsfaqscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[FaqCreate](#schemafaqcreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsFaqsRetrieve

<a id="opIdchatbotsFaqsRetrieve"></a>

`GET /api/chatbots/{chatbotPk}/faqs/{id}/`

<h3 id="chatbotsfaqsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this FAQ.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "question": "string",
  "answer": "string",
  "hitsCount": 0
}
```

<h3 id="chatbotsfaqsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Faq](#schemafaq)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsFaqsUpdate

<a id="opIdchatbotsFaqsUpdate"></a>

`PUT /api/chatbots/{chatbotPk}/faqs/{id}/`

> Body parameter

```json
{
  "question": "string",
  "answer": "string"
}
```

<h3 id="chatbotsfaqsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this FAQ.|
|body|body|[Faq](#schemafaq)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "question": "string",
  "answer": "string",
  "hitsCount": 0
}
```

<h3 id="chatbotsfaqsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Faq](#schemafaq)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsFaqsPartialUpdate

<a id="opIdchatbotsFaqsPartialUpdate"></a>

`PATCH /api/chatbots/{chatbotPk}/faqs/{id}/`

> Body parameter

```json
{
  "question": "string",
  "answer": "string"
}
```

<h3 id="chatbotsfaqspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this FAQ.|
|body|body|[PatchedFaq](#schemapatchedfaq)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "question": "string",
  "answer": "string",
  "hitsCount": 0
}
```

<h3 id="chatbotsfaqspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Faq](#schemafaq)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsFaqsDestroy

<a id="opIdchatbotsFaqsDestroy"></a>

`DELETE /api/chatbots/{chatbotPk}/faqs/{id}/`

<h3 id="chatbotsfaqsdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this FAQ.|

<h3 id="chatbotsfaqsdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsFaqsBatchDeleteCreate

<a id="opIdchatbotsFaqsBatchDeleteCreate"></a>

`POST /api/chatbots/{chatbotPk}/faqs/batch-delete/`

批量刪除指定的 FAQ

> Body parameter

```json
{
  "question": "string",
  "answer": "string"
}
```

<h3 id="chatbotsfaqsbatchdeletecreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|body|body|[Faq](#schemafaq)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "question": "string",
  "answer": "string",
  "hitsCount": 0
}
```

<h3 id="chatbotsfaqsbatchdeletecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Faq](#schemafaq)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsInstructionRecordsList

<a id="opIdchatbotsInstructionRecordsList"></a>

`GET /api/chatbots/{chatbotPk}/instruction-records/`

<h3 id="chatbotsinstructionrecordslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "instructions": "string",
      "operatorName": "string",
      "createdAt": "string"
    }
  ]
}
```

<h3 id="chatbotsinstructionrecordslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedChatbotInstructionRecordList](#schemapaginatedchatbotinstructionrecordlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsRecordsList

<a id="opIdchatbotsRecordsList"></a>

`GET /api/chatbots/{chatbotPk}/records/`

<h3 id="chatbotsrecordslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "inputMessage": "string",
      "condenseMessage": "string",
      "outputMessage": "string",
      "context": "string",
      "faithfulnessScore": 0.1,
      "displayFaithfulnessScore": "string",
      "answerRelevancyScore": 0.1,
      "displayAnswerRelevancyScore": "string",
      "contextPrecisionScore": 0.1,
      "displayContextPrecisionScore": "string",
      "answerCorrectnessScore": 0.1,
      "displayAnswerCorrectnessScore": "string",
      "answerSimilarityScore": 0.1,
      "displayAnswerSimilarityScore": "string",
      "contextRecallScore": 0.1,
      "displayContextRecallScore": "string",
      "replyTime": "string",
      "createdAt": "string",
      "error": "string"
    }
  ]
}
```

<h3 id="chatbotsrecordslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedChatbotRecordList](#schemapaginatedchatbotrecordlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsRecordsExportExcelRetrieve

<a id="opIdchatbotsRecordsExportExcelRetrieve"></a>

`GET /api/chatbots/{chatbotPk}/records/export-excel/`

匯出所有聊天記錄到Excel檔案。

此action方法會獲取與特定chatbot相關的所有聊天記錄，
並將其匯出為Excel檔案。匯出的檔案包含以下欄位：
- ID：記錄編號
- 用戶輸入訊息：原始輸入內容
- 修飾輸入訊息：經過處理的輸入內容
- 型態：表示訊息是對話中的'New'還是'Follow'
- 參考資料：系統參考的相關資料
- 輸出訊息：機器人的回應內容
- 誠實性評分：回答的誠實度評分
- 回答相關性評分：回答與問題的相關程度評分
- 回答正確性評分：回答的正確程度評分
- 回答相似性評分：回答與標準答案的相似程度評分
- 參考資料相關性評分：回覆與參考資料的相關程度評分
- 參考資料召回率評分：回覆是否能夠從參考資料中召回相關資料
- 回覆花費時間：回覆的花費時間
- 建立時間：記錄建立的時間

<h3 id="chatbotsrecordsexportexcelretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "inputMessage": "string",
  "condenseMessage": "string",
  "outputMessage": "string",
  "context": "string",
  "faithfulnessScore": 0.1,
  "displayFaithfulnessScore": "string",
  "answerRelevancyScore": 0.1,
  "displayAnswerRelevancyScore": "string",
  "contextPrecisionScore": 0.1,
  "displayContextPrecisionScore": "string",
  "answerCorrectnessScore": 0.1,
  "displayAnswerCorrectnessScore": "string",
  "answerSimilarityScore": 0.1,
  "displayAnswerSimilarityScore": "string",
  "contextRecallScore": 0.1,
  "displayContextRecallScore": "string",
  "replyTime": "string",
  "createdAt": "string",
  "error": "string"
}
```

<h3 id="chatbotsrecordsexportexcelretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotRecord](#schemachatbotrecord)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsWebhookRecordsList

<a id="opIdchatbotsWebhookRecordsList"></a>

`GET /api/chatbots/{chatbotPk}/webhook-records/`

<h3 id="chatbotswebhookrecordslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "chatbot": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
        "name": "string",
        "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
        "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
        "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
        "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
        "instructions": "string",
        "webhookUrl": "http://example.com",
        "apiWebChatId": "string",
        "updatedAt": "string",
        "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
        "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
        "replyMode": "normal",
        "template": "string",
        "unanswerableTemplate": "string",
        "totalWordsCount": -9223372036854776000,
        "enableChineseConversion": true,
        "outputFormat": null,
        "databaseUrl": "string",
        "databaseType": "string"
      },
      "url": "string",
      "requestBody": null,
      "response": "string",
      "statusCode": -2147483648,
      "createdAt": "string"
    }
  ]
}
```

<h3 id="chatbotswebhookrecordslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedWebhookRecordList](#schemapaginatedwebhookrecordlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsRetrieve

<a id="opIdchatbotsRetrieve"></a>

`GET /api/chatbots/{id}/`

<h3 id="chatbotsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this chatbot.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="chatbotsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Chatbot](#schemachatbot)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## chatbotsUpdate

<a id="opIdchatbotsUpdate"></a>

`PUT /api/chatbots/{id}/`

> Body parameter

```json
{
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="chatbotsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this chatbot.|
|body|body|[Chatbot](#schemachatbot)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="chatbotsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Chatbot](#schemachatbot)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsPartialUpdate

<a id="opIdchatbotsPartialUpdate"></a>

`PATCH /api/chatbots/{id}/`

> Body parameter

```json
{
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="chatbotspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this chatbot.|
|body|body|[PatchedChatbot](#schemapatchedchatbot)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="chatbotspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Chatbot](#schemachatbot)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsDestroy

<a id="opIdchatbotsDestroy"></a>

`DELETE /api/chatbots/{id}/`

<h3 id="chatbotsdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this chatbot.|

<h3 id="chatbotsdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsCheckTableFileOrFaqExistRetrieve

<a id="opIdchatbotsCheckTableFileOrFaqExistRetrieve"></a>

`GET /api/chatbots/{id}/check-table-file-or-faq-exist/`

知識管理查詢。

<h3 id="chatbotschecktablefileorfaqexistretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this chatbot.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="chatbotschecktablefileorfaqexistretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Chatbot](#schemachatbot)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsInitializeKnowledgeManagementTemplateRetrieve

<a id="opIdchatbotsInitializeKnowledgeManagementTemplateRetrieve"></a>

`GET /api/chatbots/{id}/initialize-knowledge-management-template/`

初始化知識管理。

<h3 id="chatbotsinitializeknowledgemanagementtemplateretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this chatbot.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="chatbotsinitializeknowledgemanagementtemplateretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Chatbot](#schemachatbot)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsSearchCreate

<a id="opIdchatbotsSearchCreate"></a>

`POST /api/chatbots/{id}/search/`

搜尋 chatbot 的知識庫內容

> Body parameter

```json
{
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="chatbotssearchcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this chatbot.|
|body|body|[Chatbot](#schemachatbot)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="chatbotssearchcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Chatbot](#schemachatbot)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## embeddingModelsList

<a id="opIdembeddingModelsList"></a>

`GET /api/embedding-models/`

> Example responses

> 200 Response

```json
[
  {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "isDefault": true
  }
]
```

<h3 id="embeddingmodelslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="embeddingmodelslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[EmbeddingModel](#schemaembeddingmodel)]|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» isDefault|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## rerankerModelsList

<a id="opIdrerankerModelsList"></a>

`GET /api/reranker-models/`

> Example responses

> 200 Response

```json
[
  {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "isDefault": true
  }
]
```

<h3 id="rerankermodelslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="rerankermodelslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[RerankerModel](#schemarerankermodel)]|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» isDefault|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotFileContentsRetrieve

<a id="opIdv1ChatbotFileContentsRetrieve"></a>

`GET /api/v1/chatbot-file-contents/{id}/`

<h3 id="v1chatbotfilecontentsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案內容.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "content": "string",
  "modifiedContent": "string",
  "type": "string",
  "updatedAt": "string"
}
```

<h3 id="v1chatbotfilecontentsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFileContent](#schemachatbotfilecontent)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotFileContentsUpdate

<a id="opIdv1ChatbotFileContentsUpdate"></a>

`PUT /api/v1/chatbot-file-contents/{id}/`

> Body parameter

```json
{
  "modifiedContent": "string"
}
```

<h3 id="v1chatbotfilecontentsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案內容.|
|body|body|[ChatbotFileContent](#schemachatbotfilecontent)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "content": "string",
  "modifiedContent": "string",
  "type": "string",
  "updatedAt": "string"
}
```

<h3 id="v1chatbotfilecontentsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFileContent](#schemachatbotfilecontent)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotFileContentsPartialUpdate

<a id="opIdv1ChatbotFileContentsPartialUpdate"></a>

`PATCH /api/v1/chatbot-file-contents/{id}/`

> Body parameter

```json
{
  "modifiedContent": "string"
}
```

<h3 id="v1chatbotfilecontentspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案內容.|
|body|body|[PatchedChatbotFileContent](#schemapatchedchatbotfilecontent)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "content": "string",
  "modifiedContent": "string",
  "type": "string",
  "updatedAt": "string"
}
```

<h3 id="v1chatbotfilecontentspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFileContent](#schemachatbotfilecontent)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotSettingsList

<a id="opIdv1ChatbotSettingsList"></a>

`GET /api/v1/chatbot-settings/`

用於返回以 RAG 為主的 chatbot 設定列表。
每個 RAG 會包含與其相容的 LLMs。

> Example responses

> 200 Response

```json
[
  {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "llms": "string",
    "isDefault": true,
    "isSearchSelectable": "string",
    "isWorkflowSelectable": "string",
    "isRerankerModelSelectable": "string",
    "isEmbeddingModelSelectable": "string"
  }
]
```

<h3 id="v1chatbotsettingslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="v1chatbotsettingslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[ChatbotSetting](#schemachatbotsetting)]|false|none|[用於返回以 RAG 為主的 chatbot 設定]|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» llms|string|true|read-only|none|
|» isDefault|boolean|false|none|none|
|» isSearchSelectable|string|true|read-only|none|
|» isWorkflowSelectable|string|true|read-only|none|
|» isRerankerModelSelectable|string|true|read-only|none|
|» isEmbeddingModelSelectable|string|true|read-only|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsList

<a id="opIdv1ChatbotsList"></a>

`GET /api/v1/chatbots/`

<h3 id="v1chatbotslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "largeLanguageModel": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string"
      },
      "rag": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string"
      },
      "embeddingModel": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "isDefault": true
      },
      "rerankerModel": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "isDefault": true
      },
      "updatedAt": "string",
      "enableChineseConversion": true
    }
  ]
}
```

<h3 id="v1chatbotslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedChatbotListList](#schemapaginatedchatbotlistlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsCreate

<a id="opIdv1ChatbotsCreate"></a>

`POST /api/v1/chatbots/`

> Body parameter

```json
{
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="v1chatbotscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Chatbot](#schemachatbot)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="v1chatbotscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Chatbot](#schemachatbot)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsCrawlPageRequestsList

<a id="opIdv1ChatbotsCrawlPageRequestsList"></a>

`GET /api/v1/chatbots/{chatbotPk}/crawl-page-requests/`

<h3 id="v1chatbotscrawlpagerequestslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "url": "http://example.com",
      "status": "processing",
      "createdAt": "string"
    }
  ]
}
```

<h3 id="v1chatbotscrawlpagerequestslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedCrawlPageRequestList](#schemapaginatedcrawlpagerequestlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsCrawlPageRequestsCreate

<a id="opIdv1ChatbotsCrawlPageRequestsCreate"></a>

`POST /api/v1/chatbots/{chatbotPk}/crawl-page-requests/`

> Body parameter

```json
{
  "url": "http://example.com",
  "status": "processing"
}
```

<h3 id="v1chatbotscrawlpagerequestscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|body|body|[CrawlPageRequestCreate](#schemacrawlpagerequestcreate)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "url": "http://example.com",
  "status": "processing"
}
```

<h3 id="v1chatbotscrawlpagerequestscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[CrawlPageRequestCreate](#schemacrawlpagerequestcreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsCrawlPageRequestsCrawlPagesList

<a id="opIdv1ChatbotsCrawlPageRequestsCrawlPagesList"></a>

`GET /api/v1/chatbots/{chatbotPk}/crawl-page-requests/{crawlPageRequestPk}/crawl-pages/`

<h3 id="v1chatbotscrawlpagerequestscrawlpageslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string|true|none|
|crawlPageRequestPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "url": "http://example.com",
      "title": "string",
      "status": "pending",
      "isOriginalPage": true
    }
  ]
}
```

<h3 id="v1chatbotscrawlpagerequestscrawlpageslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedCrawlPageList](#schemapaginatedcrawlpagelist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsCrawlPageRequestsCrawlPagesImportFileCreate

<a id="opIdv1ChatbotsCrawlPageRequestsCrawlPagesImportFileCreate"></a>

`POST /api/v1/chatbots/{chatbotPk}/crawl-page-requests/{crawlPageRequestPk}/crawl-pages/{id}/import-file/`

將爬取的網頁內容匯入為聊天機器人檔案。

此方法會檢查爬取頁面的狀態，如果頁面不是正在處理中的狀態，
則會啟動非同步任務將網頁內容轉換為聊天機器人可用的檔案格式。

Args:
    request (HttpRequest): HTTP 請求物件
    *args: 可變位置參數
    **kwargs: 可變關鍵字參數，包含爬取頁面的識別碼

Returns:
    Response: 包含更新後的爬取頁面序列化資料的回應

Raises:
    ValidationError: 當爬取頁面已在處理中時拋出

> Body parameter

```json
{
  "url": "http://example.com",
  "title": "string",
  "status": "pending",
  "isOriginalPage": true
}
```

<h3 id="v1chatbotscrawlpagerequestscrawlpagesimportfilecreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string|true|none|
|crawlPageRequestPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this 爬取網頁.|
|body|body|[CrawlPage](#schemacrawlpage)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "url": "http://example.com",
  "title": "string",
  "status": "pending",
  "isOriginalPage": true
}
```

<h3 id="v1chatbotscrawlpagerequestscrawlpagesimportfilecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[CrawlPage](#schemacrawlpage)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsFaqsList

<a id="opIdv1ChatbotsFaqsList"></a>

`GET /api/v1/chatbots/{chatbotPk}/faqs/`

<h3 id="v1chatbotsfaqslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "question": "string",
      "answer": "string",
      "hitsCount": 0
    }
  ]
}
```

<h3 id="v1chatbotsfaqslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedFaqList](#schemapaginatedfaqlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsFaqsCreate

<a id="opIdv1ChatbotsFaqsCreate"></a>

`POST /api/v1/chatbots/{chatbotPk}/faqs/`

> Body parameter

```json
{
  "question": "string",
  "answer": "string"
}
```

<h3 id="v1chatbotsfaqscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|body|body|[FaqCreate](#schemafaqcreate)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "question": "string",
  "answer": "string"
}
```

<h3 id="v1chatbotsfaqscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[FaqCreate](#schemafaqcreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsFaqsRetrieve

<a id="opIdv1ChatbotsFaqsRetrieve"></a>

`GET /api/v1/chatbots/{chatbotPk}/faqs/{id}/`

<h3 id="v1chatbotsfaqsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this FAQ.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "question": "string",
  "answer": "string",
  "hitsCount": 0
}
```

<h3 id="v1chatbotsfaqsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Faq](#schemafaq)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsFaqsUpdate

<a id="opIdv1ChatbotsFaqsUpdate"></a>

`PUT /api/v1/chatbots/{chatbotPk}/faqs/{id}/`

> Body parameter

```json
{
  "question": "string",
  "answer": "string"
}
```

<h3 id="v1chatbotsfaqsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this FAQ.|
|body|body|[Faq](#schemafaq)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "question": "string",
  "answer": "string",
  "hitsCount": 0
}
```

<h3 id="v1chatbotsfaqsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Faq](#schemafaq)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsFaqsPartialUpdate

<a id="opIdv1ChatbotsFaqsPartialUpdate"></a>

`PATCH /api/v1/chatbots/{chatbotPk}/faqs/{id}/`

> Body parameter

```json
{
  "question": "string",
  "answer": "string"
}
```

<h3 id="v1chatbotsfaqspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this FAQ.|
|body|body|[PatchedFaq](#schemapatchedfaq)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "question": "string",
  "answer": "string",
  "hitsCount": 0
}
```

<h3 id="v1chatbotsfaqspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Faq](#schemafaq)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsFaqsDestroy

<a id="opIdv1ChatbotsFaqsDestroy"></a>

`DELETE /api/v1/chatbots/{chatbotPk}/faqs/{id}/`

<h3 id="v1chatbotsfaqsdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this FAQ.|

<h3 id="v1chatbotsfaqsdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsFaqsBatchDeleteCreate

<a id="opIdv1ChatbotsFaqsBatchDeleteCreate"></a>

`POST /api/v1/chatbots/{chatbotPk}/faqs/batch-delete/`

批量刪除指定的 FAQ

> Body parameter

```json
{
  "question": "string",
  "answer": "string"
}
```

<h3 id="v1chatbotsfaqsbatchdeletecreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|body|body|[Faq](#schemafaq)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "question": "string",
  "answer": "string",
  "hitsCount": 0
}
```

<h3 id="v1chatbotsfaqsbatchdeletecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Faq](#schemafaq)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsInstructionRecordsList

<a id="opIdv1ChatbotsInstructionRecordsList"></a>

`GET /api/v1/chatbots/{chatbotPk}/instruction-records/`

<h3 id="v1chatbotsinstructionrecordslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "instructions": "string",
      "operatorName": "string",
      "createdAt": "string"
    }
  ]
}
```

<h3 id="v1chatbotsinstructionrecordslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedChatbotInstructionRecordList](#schemapaginatedchatbotinstructionrecordlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsRecordsList

<a id="opIdv1ChatbotsRecordsList"></a>

`GET /api/v1/chatbots/{chatbotPk}/records/`

<h3 id="v1chatbotsrecordslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "inputMessage": "string",
      "condenseMessage": "string",
      "outputMessage": "string",
      "context": "string",
      "faithfulnessScore": 0.1,
      "displayFaithfulnessScore": "string",
      "answerRelevancyScore": 0.1,
      "displayAnswerRelevancyScore": "string",
      "contextPrecisionScore": 0.1,
      "displayContextPrecisionScore": "string",
      "answerCorrectnessScore": 0.1,
      "displayAnswerCorrectnessScore": "string",
      "answerSimilarityScore": 0.1,
      "displayAnswerSimilarityScore": "string",
      "contextRecallScore": 0.1,
      "displayContextRecallScore": "string",
      "replyTime": "string",
      "createdAt": "string",
      "error": "string"
    }
  ]
}
```

<h3 id="v1chatbotsrecordslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedChatbotRecordList](#schemapaginatedchatbotrecordlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsRecordsExportExcelRetrieve

<a id="opIdv1ChatbotsRecordsExportExcelRetrieve"></a>

`GET /api/v1/chatbots/{chatbotPk}/records/export-excel/`

匯出所有聊天記錄到Excel檔案。

此action方法會獲取與特定chatbot相關的所有聊天記錄，
並將其匯出為Excel檔案。匯出的檔案包含以下欄位：
- ID：記錄編號
- 用戶輸入訊息：原始輸入內容
- 修飾輸入訊息：經過處理的輸入內容
- 型態：表示訊息是對話中的'New'還是'Follow'
- 參考資料：系統參考的相關資料
- 輸出訊息：機器人的回應內容
- 誠實性評分：回答的誠實度評分
- 回答相關性評分：回答與問題的相關程度評分
- 回答正確性評分：回答的正確程度評分
- 回答相似性評分：回答與標準答案的相似程度評分
- 參考資料相關性評分：回覆與參考資料的相關程度評分
- 參考資料召回率評分：回覆是否能夠從參考資料中召回相關資料
- 回覆花費時間：回覆的花費時間
- 建立時間：記錄建立的時間

<h3 id="v1chatbotsrecordsexportexcelretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "inputMessage": "string",
  "condenseMessage": "string",
  "outputMessage": "string",
  "context": "string",
  "faithfulnessScore": 0.1,
  "displayFaithfulnessScore": "string",
  "answerRelevancyScore": 0.1,
  "displayAnswerRelevancyScore": "string",
  "contextPrecisionScore": 0.1,
  "displayContextPrecisionScore": "string",
  "answerCorrectnessScore": 0.1,
  "displayAnswerCorrectnessScore": "string",
  "answerSimilarityScore": 0.1,
  "displayAnswerSimilarityScore": "string",
  "contextRecallScore": 0.1,
  "displayContextRecallScore": "string",
  "replyTime": "string",
  "createdAt": "string",
  "error": "string"
}
```

<h3 id="v1chatbotsrecordsexportexcelretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotRecord](#schemachatbotrecord)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsWebhookRecordsList

<a id="opIdv1ChatbotsWebhookRecordsList"></a>

`GET /api/v1/chatbots/{chatbotPk}/webhook-records/`

<h3 id="v1chatbotswebhookrecordslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "chatbot": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
        "name": "string",
        "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
        "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
        "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
        "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
        "instructions": "string",
        "webhookUrl": "http://example.com",
        "apiWebChatId": "string",
        "updatedAt": "string",
        "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
        "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
        "replyMode": "normal",
        "template": "string",
        "unanswerableTemplate": "string",
        "totalWordsCount": -9223372036854776000,
        "enableChineseConversion": true,
        "outputFormat": null,
        "databaseUrl": "string",
        "databaseType": "string"
      },
      "url": "string",
      "requestBody": null,
      "response": "string",
      "statusCode": -2147483648,
      "createdAt": "string"
    }
  ]
}
```

<h3 id="v1chatbotswebhookrecordslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedWebhookRecordList](#schemapaginatedwebhookrecordlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsRetrieve

<a id="opIdv1ChatbotsRetrieve"></a>

`GET /api/v1/chatbots/{id}/`

<h3 id="v1chatbotsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this chatbot.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="v1chatbotsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Chatbot](#schemachatbot)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1ChatbotsUpdate

<a id="opIdv1ChatbotsUpdate"></a>

`PUT /api/v1/chatbots/{id}/`

> Body parameter

```json
{
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="v1chatbotsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this chatbot.|
|body|body|[Chatbot](#schemachatbot)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="v1chatbotsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Chatbot](#schemachatbot)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsPartialUpdate

<a id="opIdv1ChatbotsPartialUpdate"></a>

`PATCH /api/v1/chatbots/{id}/`

> Body parameter

```json
{
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="v1chatbotspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this chatbot.|
|body|body|[PatchedChatbot](#schemapatchedchatbot)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="v1chatbotspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Chatbot](#schemachatbot)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsDestroy

<a id="opIdv1ChatbotsDestroy"></a>

`DELETE /api/v1/chatbots/{id}/`

<h3 id="v1chatbotsdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this chatbot.|

<h3 id="v1chatbotsdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsCheckTableFileOrFaqExistRetrieve

<a id="opIdv1ChatbotsCheckTableFileOrFaqExistRetrieve"></a>

`GET /api/v1/chatbots/{id}/check-table-file-or-faq-exist/`

知識管理查詢。

<h3 id="v1chatbotschecktablefileorfaqexistretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this chatbot.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="v1chatbotschecktablefileorfaqexistretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Chatbot](#schemachatbot)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsInitializeKnowledgeManagementTemplateRetrieve

<a id="opIdv1ChatbotsInitializeKnowledgeManagementTemplateRetrieve"></a>

`GET /api/v1/chatbots/{id}/initialize-knowledge-management-template/`

初始化知識管理。

<h3 id="v1chatbotsinitializeknowledgemanagementtemplateretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this chatbot.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="v1chatbotsinitializeknowledgemanagementtemplateretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Chatbot](#schemachatbot)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsSearchCreate

<a id="opIdv1ChatbotsSearchCreate"></a>

`POST /api/v1/chatbots/{id}/search/`

搜尋 chatbot 的知識庫內容

> Body parameter

```json
{
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="v1chatbotssearchcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this chatbot.|
|body|body|[Chatbot](#schemachatbot)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
}
```

<h3 id="v1chatbotssearchcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Chatbot](#schemachatbot)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1EmbeddingModelsList

<a id="opIdv1EmbeddingModelsList"></a>

`GET /api/v1/embedding-models/`

> Example responses

> 200 Response

```json
[
  {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "isDefault": true
  }
]
```

<h3 id="v1embeddingmodelslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="v1embeddingmodelslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[EmbeddingModel](#schemaembeddingmodel)]|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» isDefault|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1RerankerModelsList

<a id="opIdv1RerankerModelsList"></a>

`GET /api/v1/reranker-models/`

> Example responses

> 200 Response

```json
[
  {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "isDefault": true
  }
]
```

<h3 id="v1rerankermodelslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="v1rerankermodelslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[RerankerModel](#schemarerankermodel)]|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|
|» isDefault|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1WebChatsBatchQasCreate

<a id="opIdv1WebChatsBatchQasCreate"></a>

`POST /api/v1/web-chats/{webchatPk}/batch-qas/`

> Body parameter

```json
{
  "file": "http://example.com"
}
```

<h3 id="v1webchatsbatchqascreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|webchatPk|path|string(uuid)|true|none|
|body|body|[ChatbotBatchQAFile](#schemachatbotbatchqafile)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "file": "http://example.com",
  "createdAt": "string"
}
```

<h3 id="v1webchatsbatchqascreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[ChatbotBatchQAFile](#schemachatbotbatchqafile)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1WebChatsBatchQasExportExcelRetrieve

<a id="opIdv1WebChatsBatchQasExportExcelRetrieve"></a>

`GET /api/v1/web-chats/{webchatPk}/batch-qas/{id}/export-excel/`

匯出聊天機器人紀錄至 Excel 檔案。

此操作方法會取得與特定批次問答檔案相關的聊天機器人紀錄，
並將其匯出為 Excel 檔案。匯出的檔案包含以下欄位：
- 問題: 使用者訊息內容
- 型態: 表示訊息是對話中的「新對話」或「後續對話」
- 回覆: 機器人回應內容

<h3 id="v1webchatsbatchqasexportexcelretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 批次問答檔案.|
|webchatPk|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "file": "http://example.com",
  "createdAt": "string"
}
```

<h3 id="v1webchatsbatchqasexportexcelretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotBatchQAFile](#schemachatbotbatchqafile)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## webChatsBatchQasCreate

<a id="opIdwebChatsBatchQasCreate"></a>

`POST /api/web-chats/{webchatPk}/batch-qas/`

> Body parameter

```json
{
  "file": "http://example.com"
}
```

<h3 id="webchatsbatchqascreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|webchatPk|path|string(uuid)|true|none|
|body|body|[ChatbotBatchQAFile](#schemachatbotbatchqafile)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "file": "http://example.com",
  "createdAt": "string"
}
```

<h3 id="webchatsbatchqascreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[ChatbotBatchQAFile](#schemachatbotbatchqafile)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## webChatsBatchQasExportExcelRetrieve

<a id="opIdwebChatsBatchQasExportExcelRetrieve"></a>

`GET /api/web-chats/{webchatPk}/batch-qas/{id}/export-excel/`

匯出聊天機器人紀錄至 Excel 檔案。

此操作方法會取得與特定批次問答檔案相關的聊天機器人紀錄，
並將其匯出為 Excel 檔案。匯出的檔案包含以下欄位：
- 問題: 使用者訊息內容
- 型態: 表示訊息是對話中的「新對話」或「後續對話」
- 回覆: 機器人回應內容

<h3 id="webchatsbatchqasexportexcelretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 批次問答檔案.|
|webchatPk|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "file": "http://example.com",
  "createdAt": "string"
}
```

<h3 id="webchatsbatchqasexportexcelretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotBatchQAFile](#schemachatbotbatchqafile)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

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
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "charactersCount": 0,
      "hitsCount": 0,
      "text": "string",
      "updatedAt": "string",
      "filename": "string"
    }
  ]
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

<h1 id="maiagent-api-chats">Chats</h1>

## chatbotsCompletionsCreate

<a id="opIdchatbotsCompletionsCreate"></a>

`POST /api/chatbots/{chatbotId}/completions/`

整合對話建立和串流回應的 API。

<h3 id="chatbotscompletionscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotId|path|string(uuid)|true|none|

<h3 id="chatbotscompletionscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsInstructionRecordsMessagesList

<a id="opIdchatbotsInstructionRecordsMessagesList"></a>

`GET /api/chatbots/{chatbotPk}/instruction-records/{instructionRecordPk}/messages/`

<h3 id="chatbotsinstructionrecordsmessageslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string|true|none|
|instructionRecordPk|path|string|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
      "sender": {
        "id": 0,
        "name": "string",
        "avatar": "http://example.com"
      },
      "type": "incoming",
      "content": "string",
      "feedback": "like",
      "createdAt": "string",
      "attachments": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "type": "other",
          "filename": "string",
          "file": "http://example.com"
        }
      ],
      "citations": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "filename": "string",
          "file": "http://example.com",
          "fileType": "string",
          "size": 0,
          "status": "initial",
          "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
          "parser": {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "name": "string",
            "provider": "maiagent",
            "priority": 0
          },
          "createdAt": "string"
        }
      ],
      "citationNodes": [
        {
          "chatbotTextNode": {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "charactersCount": 0,
            "hitsCount": 0,
            "text": "string",
            "updatedAt": "string",
            "filename": "string"
          },
          "score": 0.1,
          "displayScore": "string"
        }
      ]
    }
  ]
}
```

<h3 id="chatbotsinstructionrecordsmessageslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedMessageList](#schemapaginatedmessagelist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## conversationsList

<a id="opIdconversationsList"></a>

`GET /api/conversations/`

<h3 id="conversationslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|cursor|query|string|false|The pagination cursor value.|
|inbox|query|string(uuid)|false|none|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "next": "http://api.example.org/accounts/?cursor=cD00ODY%3D\"",
  "previous": "http://api.example.org/accounts/?cursor=cj0xJnA9NDg3",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "contact": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "avatar": "http://example.com",
        "createdAt": "string"
      },
      "inbox": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "channelType": "line",
        "unreadConversationsCount": -2147483648
      },
      "title": "string",
      "lastMessage": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
        "sender": {
          "id": 0,
          "name": "string",
          "avatar": "http://example.com"
        },
        "type": "incoming",
        "content": "string",
        "feedback": "like",
        "createdAt": "string",
        "attachments": [
          {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "type": "other",
            "filename": "string",
            "file": "http://example.com"
          }
        ],
        "citations": [
          {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "filename": "string",
            "file": "http://example.com",
            "fileType": "string",
            "size": 0,
            "status": "initial",
            "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
            "parser": {
              "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
              "name": "string",
              "provider": "maiagent",
              "priority": 0
            },
            "createdAt": "string"
          }
        ],
        "citationNodes": [
          {
            "chatbotTextNode": {
              "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
              "charactersCount": 0,
              "hitsCount": 0,
              "text": "string",
              "updatedAt": "string",
              "filename": "string"
            },
            "score": 0.1,
            "displayScore": "string"
          }
        ]
      },
      "lastMessageCreatedAt": "string",
      "unreadMessagesCount": 0,
      "autoReplyEnabled": true,
      "isAutoReplyNow": "string",
      "lastReadAt": "string",
      "createdAt": "string",
      "isGroupChat": "string",
      "enableGroupMention": "string"
    }
  ]
}
```

<h3 id="conversationslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedConversationList](#schemapaginatedconversationlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## conversationsCreate

<a id="opIdconversationsCreate"></a>

`POST /api/conversations/`

> Body parameter

```json
{
  "contact": {
    "name": "string",
    "avatar": "http://example.com"
  },
  "inbox": {
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "lastMessage": {
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "attachments": [
      {
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ]
  }
}
```

<h3 id="conversationscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Conversation](#schemaconversation)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "contact": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "avatar": "http://example.com",
    "createdAt": "string"
  },
  "inbox": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "title": "string",
  "lastMessage": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "createdAt": "string",
    "attachments": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ],
    "citations": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "filename": "string",
        "file": "http://example.com",
        "fileType": "string",
        "size": 0,
        "status": "initial",
        "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
        "parser": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "provider": "maiagent",
          "priority": 0
        },
        "createdAt": "string"
      }
    ],
    "citationNodes": [
      {
        "chatbotTextNode": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "charactersCount": 0,
          "hitsCount": 0,
          "text": "string",
          "updatedAt": "string",
          "filename": "string"
        },
        "score": 0.1,
        "displayScore": "string"
      }
    ]
  },
  "lastMessageCreatedAt": "string",
  "unreadMessagesCount": 0,
  "autoReplyEnabled": true,
  "isAutoReplyNow": "string",
  "lastReadAt": "string",
  "createdAt": "string",
  "isGroupChat": "string",
  "enableGroupMention": "string"
}
```

<h3 id="conversationscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Conversation](#schemaconversation)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## conversationsRetrieve

<a id="opIdconversationsRetrieve"></a>

`GET /api/conversations/{id}/`

<h3 id="conversationsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 對話.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "contact": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "avatar": "http://example.com",
    "createdAt": "string"
  },
  "inbox": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "title": "string",
  "lastMessage": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "createdAt": "string",
    "attachments": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ],
    "citations": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "filename": "string",
        "file": "http://example.com",
        "fileType": "string",
        "size": 0,
        "status": "initial",
        "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
        "parser": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "provider": "maiagent",
          "priority": 0
        },
        "createdAt": "string"
      }
    ],
    "citationNodes": [
      {
        "chatbotTextNode": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "charactersCount": 0,
          "hitsCount": 0,
          "text": "string",
          "updatedAt": "string",
          "filename": "string"
        },
        "score": 0.1,
        "displayScore": "string"
      }
    ]
  },
  "lastMessageCreatedAt": "string",
  "unreadMessagesCount": 0,
  "autoReplyEnabled": true,
  "isAutoReplyNow": "string",
  "lastReadAt": "string",
  "createdAt": "string",
  "isGroupChat": "string",
  "enableGroupMention": "string"
}
```

<h3 id="conversationsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Conversation](#schemaconversation)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## conversationsUpdateAutoReplyPartialUpdate

<a id="opIdconversationsUpdateAutoReplyPartialUpdate"></a>

`PATCH /api/conversations/{id}/update-auto-reply/`

> Body parameter

```json
{
  "contact": {
    "name": "string",
    "avatar": "http://example.com"
  },
  "inbox": {
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "lastMessage": {
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "attachments": [
      {
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ]
  }
}
```

<h3 id="conversationsupdateautoreplypartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 對話.|
|body|body|[PatchedConversation](#schemapatchedconversation)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "contact": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "avatar": "http://example.com",
    "createdAt": "string"
  },
  "inbox": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "title": "string",
  "lastMessage": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "createdAt": "string",
    "attachments": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ],
    "citations": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "filename": "string",
        "file": "http://example.com",
        "fileType": "string",
        "size": 0,
        "status": "initial",
        "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
        "parser": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "provider": "maiagent",
          "priority": 0
        },
        "createdAt": "string"
      }
    ],
    "citationNodes": [
      {
        "chatbotTextNode": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "charactersCount": 0,
          "hitsCount": 0,
          "text": "string",
          "updatedAt": "string",
          "filename": "string"
        },
        "score": 0.1,
        "displayScore": "string"
      }
    ]
  },
  "lastMessageCreatedAt": "string",
  "unreadMessagesCount": 0,
  "autoReplyEnabled": true,
  "isAutoReplyNow": "string",
  "lastReadAt": "string",
  "createdAt": "string",
  "isGroupChat": "string",
  "enableGroupMention": "string"
}
```

<h3 id="conversationsupdateautoreplypartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Conversation](#schemaconversation)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## conversationsUpdateEnableGroupMentionPartialUpdate

<a id="opIdconversationsUpdateEnableGroupMentionPartialUpdate"></a>

`PATCH /api/conversations/{id}/update-enable-group-mention/`

> Body parameter

```json
{
  "contact": {
    "name": "string",
    "avatar": "http://example.com"
  },
  "inbox": {
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "lastMessage": {
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "attachments": [
      {
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ]
  }
}
```

<h3 id="conversationsupdateenablegroupmentionpartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 對話.|
|body|body|[PatchedConversation](#schemapatchedconversation)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "contact": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "avatar": "http://example.com",
    "createdAt": "string"
  },
  "inbox": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "title": "string",
  "lastMessage": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "createdAt": "string",
    "attachments": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ],
    "citations": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "filename": "string",
        "file": "http://example.com",
        "fileType": "string",
        "size": 0,
        "status": "initial",
        "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
        "parser": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "provider": "maiagent",
          "priority": 0
        },
        "createdAt": "string"
      }
    ],
    "citationNodes": [
      {
        "chatbotTextNode": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "charactersCount": 0,
          "hitsCount": 0,
          "text": "string",
          "updatedAt": "string",
          "filename": "string"
        },
        "score": 0.1,
        "displayScore": "string"
      }
    ]
  },
  "lastMessageCreatedAt": "string",
  "unreadMessagesCount": 0,
  "autoReplyEnabled": true,
  "isAutoReplyNow": "string",
  "lastReadAt": "string",
  "createdAt": "string",
  "isGroupChat": "string",
  "enableGroupMention": "string"
}
```

<h3 id="conversationsupdateenablegroupmentionpartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Conversation](#schemaconversation)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## generateCopilotMessageCreate

<a id="opIdgenerateCopilotMessageCreate"></a>

`POST /api/generate-copilot-message/`

<h3 id="generatecopilotmessagecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## inboxesList

<a id="opIdinboxesList"></a>

`GET /api/inboxes/`

<h3 id="inboxeslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|channelType|query|string|false|* `line` - LINE|
|chatbot|query|string(uuid)|false|none|
|ordering|query|string|false|Which field to use when ordering the results.|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

#### Detailed descriptions

**channelType**: * `line` - LINE
* `telegram` - Telegram
* `web` - Web
* `messenger` - Messenger

#### Enumerated Values

|Parameter|Value|
|---|---|
|channelType|line|
|channelType|messenger|
|channelType|telegram|
|channelType|web|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "channelType": "line",
      "unreadConversationsCount": -2147483648
    }
  ]
}
```

<h3 id="inboxeslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedInboxList](#schemapaginatedinboxlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## inboxesCreate

<a id="opIdinboxesCreate"></a>

`POST /api/inboxes/`

> Body parameter

```json
{
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="inboxescreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Inbox](#schemainbox)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="inboxescreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Inbox](#schemainbox)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## inboxesRetrieve

<a id="opIdinboxesRetrieve"></a>

`GET /api/inboxes/{id}/`

<h3 id="inboxesretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 收件匣.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="inboxesretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Inbox](#schemainbox)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## inboxesUpdate

<a id="opIdinboxesUpdate"></a>

`PUT /api/inboxes/{id}/`

> Body parameter

```json
{
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="inboxesupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 收件匣.|
|body|body|[Inbox](#schemainbox)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="inboxesupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Inbox](#schemainbox)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## inboxesPartialUpdate

<a id="opIdinboxesPartialUpdate"></a>

`PATCH /api/inboxes/{id}/`

> Body parameter

```json
{
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "channelType": "line",
  "name": "string",
  "autoReplySchedules": [
    {
      "isEnabled": true,
      "timeSlots": [
        [
          "14:15:22Z"
        ]
      ]
    }
  ],
  "channel": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387"
}
```

<h3 id="inboxespartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 收件匣.|
|body|body|[PatchedInbox](#schemapatchedinbox)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="inboxespartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Inbox](#schemainbox)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## inboxesDestroy

<a id="opIdinboxesDestroy"></a>

`DELETE /api/inboxes/{id}/`

<h3 id="inboxesdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 收件匣.|

<h3 id="inboxesdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## inboxesUpdateAllEnableGroupMentionCreate

<a id="opIdinboxesUpdateAllEnableGroupMentionCreate"></a>

`POST /api/inboxes/{id}/update-all-enable-group-mention/`

更新全部 Line 群組提及功能狀態。

Args:
    request: HTTP request 物件
    pk: inbox primary key

Returns:
    Response: 更新成功回應

> Body parameter

```json
{
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="inboxesupdateallenablegroupmentioncreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 收件匣.|
|body|body|[Inbox](#schemainbox)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="inboxesupdateallenablegroupmentioncreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Inbox](#schemainbox)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## messagesList

<a id="opIdmessagesList"></a>

`GET /api/messages/`

<h3 id="messageslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|conversation|query|string(uuid)|false|none|
|cursor|query|string|false|The pagination cursor value.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
      "sender": {
        "id": 0,
        "name": "string",
        "avatar": "http://example.com"
      },
      "type": "incoming",
      "content": "string",
      "feedback": "like",
      "createdAt": "string",
      "attachments": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "type": "other",
          "filename": "string",
          "file": "http://example.com"
        }
      ],
      "citations": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "filename": "string",
          "file": "http://example.com",
          "fileType": "string",
          "size": 0,
          "status": "initial",
          "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
          "parser": {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "name": "string",
            "provider": "maiagent",
            "priority": 0
          },
          "createdAt": "string"
        }
      ],
      "citationNodes": [
        {
          "chatbotTextNode": {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "charactersCount": 0,
            "hitsCount": 0,
            "text": "string",
            "updatedAt": "string",
            "filename": "string"
          },
          "score": 0.1,
          "displayScore": "string"
        }
      ]
    }
  ]
}
```

<h3 id="messageslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedMessageList](#schemapaginatedmessagelist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## messagesCreate

<a id="opIdmessagesCreate"></a>

`POST /api/messages/`

> Body parameter

```json
{
  "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
  "sender": {
    "id": 0,
    "name": "string",
    "avatar": "http://example.com"
  },
  "type": "incoming",
  "content": "string",
  "feedback": "like",
  "attachments": [
    {
      "type": "other",
      "filename": "string",
      "file": "http://example.com"
    }
  ]
}
```

<h3 id="messagescreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Message](#schemamessage)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
  "sender": {
    "id": 0,
    "name": "string",
    "avatar": "http://example.com"
  },
  "type": "incoming",
  "content": "string",
  "feedback": "like",
  "createdAt": "string",
  "attachments": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "type": "other",
      "filename": "string",
      "file": "http://example.com"
    }
  ],
  "citations": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "filename": "string",
      "file": "http://example.com",
      "fileType": "string",
      "size": 0,
      "status": "initial",
      "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
      "parser": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "provider": "maiagent",
        "priority": 0
      },
      "createdAt": "string"
    }
  ],
  "citationNodes": [
    {
      "chatbotTextNode": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "charactersCount": 0,
        "hitsCount": 0,
        "text": "string",
        "updatedAt": "string",
        "filename": "string"
      },
      "score": 0.1,
      "displayScore": "string"
    }
  ]
}
```

<h3 id="messagescreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Message](#schemamessage)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## messagesRetrieve

<a id="opIdmessagesRetrieve"></a>

`GET /api/messages/{id}/`

<h3 id="messagesretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 訊息.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
  "sender": {
    "id": 0,
    "name": "string",
    "avatar": "http://example.com"
  },
  "type": "incoming",
  "content": "string",
  "feedback": "like",
  "createdAt": "string",
  "attachments": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "type": "other",
      "filename": "string",
      "file": "http://example.com"
    }
  ],
  "citations": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "filename": "string",
      "file": "http://example.com",
      "fileType": "string",
      "size": 0,
      "status": "initial",
      "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
      "parser": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "provider": "maiagent",
        "priority": 0
      },
      "createdAt": "string"
    }
  ],
  "citationNodes": [
    {
      "chatbotTextNode": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "charactersCount": 0,
        "hitsCount": 0,
        "text": "string",
        "updatedAt": "string",
        "filename": "string"
      },
      "score": 0.1,
      "displayScore": "string"
    }
  ]
}
```

<h3 id="messagesretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Message](#schemamessage)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## messagesOutgoingCreate

<a id="opIdmessagesOutgoingCreate"></a>

`POST /api/messages/outgoing/`

> Body parameter

```json
{
  "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
  "sender": {
    "id": 0,
    "name": "string",
    "avatar": "http://example.com"
  },
  "type": "incoming",
  "content": "string",
  "feedback": "like",
  "attachments": [
    {
      "type": "other",
      "filename": "string",
      "file": "http://example.com"
    }
  ]
}
```

<h3 id="messagesoutgoingcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Message](#schemamessage)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
  "sender": {
    "id": 0,
    "name": "string",
    "avatar": "http://example.com"
  },
  "type": "incoming",
  "content": "string",
  "feedback": "like",
  "createdAt": "string",
  "attachments": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "type": "other",
      "filename": "string",
      "file": "http://example.com"
    }
  ],
  "citations": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "filename": "string",
      "file": "http://example.com",
      "fileType": "string",
      "size": 0,
      "status": "initial",
      "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
      "parser": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "provider": "maiagent",
        "priority": 0
      },
      "createdAt": "string"
    }
  ],
  "citationNodes": [
    {
      "chatbotTextNode": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "charactersCount": 0,
        "hitsCount": 0,
        "text": "string",
        "updatedAt": "string",
        "filename": "string"
      },
      "score": 0.1,
      "displayScore": "string"
    }
  ]
}
```

<h3 id="messagesoutgoingcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Message](#schemamessage)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsCompletionsCreate

<a id="opIdv1ChatbotsCompletionsCreate"></a>

`POST /api/v1/chatbots/{chatbotId}/completions/`

整合對話建立和串流回應的 API。

<h3 id="v1chatbotscompletionscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotId|path|string(uuid)|true|none|

<h3 id="v1chatbotscompletionscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsInstructionRecordsMessagesList

<a id="opIdv1ChatbotsInstructionRecordsMessagesList"></a>

`GET /api/v1/chatbots/{chatbotPk}/instruction-records/{instructionRecordPk}/messages/`

<h3 id="v1chatbotsinstructionrecordsmessageslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string|true|none|
|instructionRecordPk|path|string|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
      "sender": {
        "id": 0,
        "name": "string",
        "avatar": "http://example.com"
      },
      "type": "incoming",
      "content": "string",
      "feedback": "like",
      "createdAt": "string",
      "attachments": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "type": "other",
          "filename": "string",
          "file": "http://example.com"
        }
      ],
      "citations": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "filename": "string",
          "file": "http://example.com",
          "fileType": "string",
          "size": 0,
          "status": "initial",
          "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
          "parser": {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "name": "string",
            "provider": "maiagent",
            "priority": 0
          },
          "createdAt": "string"
        }
      ],
      "citationNodes": [
        {
          "chatbotTextNode": {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "charactersCount": 0,
            "hitsCount": 0,
            "text": "string",
            "updatedAt": "string",
            "filename": "string"
          },
          "score": 0.1,
          "displayScore": "string"
        }
      ]
    }
  ]
}
```

<h3 id="v1chatbotsinstructionrecordsmessageslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedMessageList](#schemapaginatedmessagelist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ConversationsList

<a id="opIdv1ConversationsList"></a>

`GET /api/v1/conversations/`

<h3 id="v1conversationslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|cursor|query|string|false|The pagination cursor value.|
|inbox|query|string(uuid)|false|none|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "next": "http://api.example.org/accounts/?cursor=cD00ODY%3D\"",
  "previous": "http://api.example.org/accounts/?cursor=cj0xJnA9NDg3",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "contact": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "avatar": "http://example.com",
        "createdAt": "string"
      },
      "inbox": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "channelType": "line",
        "unreadConversationsCount": -2147483648
      },
      "title": "string",
      "lastMessage": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
        "sender": {
          "id": 0,
          "name": "string",
          "avatar": "http://example.com"
        },
        "type": "incoming",
        "content": "string",
        "feedback": "like",
        "createdAt": "string",
        "attachments": [
          {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "type": "other",
            "filename": "string",
            "file": "http://example.com"
          }
        ],
        "citations": [
          {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "filename": "string",
            "file": "http://example.com",
            "fileType": "string",
            "size": 0,
            "status": "initial",
            "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
            "parser": {
              "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
              "name": "string",
              "provider": "maiagent",
              "priority": 0
            },
            "createdAt": "string"
          }
        ],
        "citationNodes": [
          {
            "chatbotTextNode": {
              "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
              "charactersCount": 0,
              "hitsCount": 0,
              "text": "string",
              "updatedAt": "string",
              "filename": "string"
            },
            "score": 0.1,
            "displayScore": "string"
          }
        ]
      },
      "lastMessageCreatedAt": "string",
      "unreadMessagesCount": 0,
      "autoReplyEnabled": true,
      "isAutoReplyNow": "string",
      "lastReadAt": "string",
      "createdAt": "string",
      "isGroupChat": "string",
      "enableGroupMention": "string"
    }
  ]
}
```

<h3 id="v1conversationslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedConversationList](#schemapaginatedconversationlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ConversationsCreate

<a id="opIdv1ConversationsCreate"></a>

`POST /api/v1/conversations/`

> Body parameter

```json
{
  "contact": {
    "name": "string",
    "avatar": "http://example.com"
  },
  "inbox": {
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "lastMessage": {
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "attachments": [
      {
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ]
  }
}
```

<h3 id="v1conversationscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Conversation](#schemaconversation)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "contact": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "avatar": "http://example.com",
    "createdAt": "string"
  },
  "inbox": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "title": "string",
  "lastMessage": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "createdAt": "string",
    "attachments": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ],
    "citations": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "filename": "string",
        "file": "http://example.com",
        "fileType": "string",
        "size": 0,
        "status": "initial",
        "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
        "parser": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "provider": "maiagent",
          "priority": 0
        },
        "createdAt": "string"
      }
    ],
    "citationNodes": [
      {
        "chatbotTextNode": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "charactersCount": 0,
          "hitsCount": 0,
          "text": "string",
          "updatedAt": "string",
          "filename": "string"
        },
        "score": 0.1,
        "displayScore": "string"
      }
    ]
  },
  "lastMessageCreatedAt": "string",
  "unreadMessagesCount": 0,
  "autoReplyEnabled": true,
  "isAutoReplyNow": "string",
  "lastReadAt": "string",
  "createdAt": "string",
  "isGroupChat": "string",
  "enableGroupMention": "string"
}
```

<h3 id="v1conversationscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Conversation](#schemaconversation)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1ConversationsRetrieve

<a id="opIdv1ConversationsRetrieve"></a>

`GET /api/v1/conversations/{id}/`

<h3 id="v1conversationsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 對話.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "contact": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "avatar": "http://example.com",
    "createdAt": "string"
  },
  "inbox": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "title": "string",
  "lastMessage": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "createdAt": "string",
    "attachments": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ],
    "citations": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "filename": "string",
        "file": "http://example.com",
        "fileType": "string",
        "size": 0,
        "status": "initial",
        "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
        "parser": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "provider": "maiagent",
          "priority": 0
        },
        "createdAt": "string"
      }
    ],
    "citationNodes": [
      {
        "chatbotTextNode": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "charactersCount": 0,
          "hitsCount": 0,
          "text": "string",
          "updatedAt": "string",
          "filename": "string"
        },
        "score": 0.1,
        "displayScore": "string"
      }
    ]
  },
  "lastMessageCreatedAt": "string",
  "unreadMessagesCount": 0,
  "autoReplyEnabled": true,
  "isAutoReplyNow": "string",
  "lastReadAt": "string",
  "createdAt": "string",
  "isGroupChat": "string",
  "enableGroupMention": "string"
}
```

<h3 id="v1conversationsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Conversation](#schemaconversation)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1ConversationsUpdateAutoReplyPartialUpdate

<a id="opIdv1ConversationsUpdateAutoReplyPartialUpdate"></a>

`PATCH /api/v1/conversations/{id}/update-auto-reply/`

> Body parameter

```json
{
  "contact": {
    "name": "string",
    "avatar": "http://example.com"
  },
  "inbox": {
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "lastMessage": {
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "attachments": [
      {
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ]
  }
}
```

<h3 id="v1conversationsupdateautoreplypartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 對話.|
|body|body|[PatchedConversation](#schemapatchedconversation)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "contact": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "avatar": "http://example.com",
    "createdAt": "string"
  },
  "inbox": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "title": "string",
  "lastMessage": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "createdAt": "string",
    "attachments": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ],
    "citations": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "filename": "string",
        "file": "http://example.com",
        "fileType": "string",
        "size": 0,
        "status": "initial",
        "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
        "parser": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "provider": "maiagent",
          "priority": 0
        },
        "createdAt": "string"
      }
    ],
    "citationNodes": [
      {
        "chatbotTextNode": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "charactersCount": 0,
          "hitsCount": 0,
          "text": "string",
          "updatedAt": "string",
          "filename": "string"
        },
        "score": 0.1,
        "displayScore": "string"
      }
    ]
  },
  "lastMessageCreatedAt": "string",
  "unreadMessagesCount": 0,
  "autoReplyEnabled": true,
  "isAutoReplyNow": "string",
  "lastReadAt": "string",
  "createdAt": "string",
  "isGroupChat": "string",
  "enableGroupMention": "string"
}
```

<h3 id="v1conversationsupdateautoreplypartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Conversation](#schemaconversation)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ConversationsUpdateEnableGroupMentionPartialUpdate

<a id="opIdv1ConversationsUpdateEnableGroupMentionPartialUpdate"></a>

`PATCH /api/v1/conversations/{id}/update-enable-group-mention/`

> Body parameter

```json
{
  "contact": {
    "name": "string",
    "avatar": "http://example.com"
  },
  "inbox": {
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "lastMessage": {
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "attachments": [
      {
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ]
  }
}
```

<h3 id="v1conversationsupdateenablegroupmentionpartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 對話.|
|body|body|[PatchedConversation](#schemapatchedconversation)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "contact": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "avatar": "http://example.com",
    "createdAt": "string"
  },
  "inbox": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "title": "string",
  "lastMessage": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "createdAt": "string",
    "attachments": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ],
    "citations": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "filename": "string",
        "file": "http://example.com",
        "fileType": "string",
        "size": 0,
        "status": "initial",
        "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
        "parser": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "provider": "maiagent",
          "priority": 0
        },
        "createdAt": "string"
      }
    ],
    "citationNodes": [
      {
        "chatbotTextNode": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "charactersCount": 0,
          "hitsCount": 0,
          "text": "string",
          "updatedAt": "string",
          "filename": "string"
        },
        "score": 0.1,
        "displayScore": "string"
      }
    ]
  },
  "lastMessageCreatedAt": "string",
  "unreadMessagesCount": 0,
  "autoReplyEnabled": true,
  "isAutoReplyNow": "string",
  "lastReadAt": "string",
  "createdAt": "string",
  "isGroupChat": "string",
  "enableGroupMention": "string"
}
```

<h3 id="v1conversationsupdateenablegroupmentionpartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Conversation](#schemaconversation)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1GenerateCopilotMessageCreate

<a id="opIdv1GenerateCopilotMessageCreate"></a>

`POST /api/v1/generate-copilot-message/`

<h3 id="v1generatecopilotmessagecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1InboxesList

<a id="opIdv1InboxesList"></a>

`GET /api/v1/inboxes/`

<h3 id="v1inboxeslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|channelType|query|string|false|* `line` - LINE|
|chatbot|query|string(uuid)|false|none|
|ordering|query|string|false|Which field to use when ordering the results.|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

#### Detailed descriptions

**channelType**: * `line` - LINE
* `telegram` - Telegram
* `web` - Web
* `messenger` - Messenger

#### Enumerated Values

|Parameter|Value|
|---|---|
|channelType|line|
|channelType|messenger|
|channelType|telegram|
|channelType|web|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "channelType": "line",
      "unreadConversationsCount": -2147483648
    }
  ]
}
```

<h3 id="v1inboxeslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedInboxList](#schemapaginatedinboxlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1InboxesCreate

<a id="opIdv1InboxesCreate"></a>

`POST /api/v1/inboxes/`

> Body parameter

```json
{
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="v1inboxescreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Inbox](#schemainbox)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="v1inboxescreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Inbox](#schemainbox)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1InboxesRetrieve

<a id="opIdv1InboxesRetrieve"></a>

`GET /api/v1/inboxes/{id}/`

<h3 id="v1inboxesretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 收件匣.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="v1inboxesretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Inbox](#schemainbox)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1InboxesUpdate

<a id="opIdv1InboxesUpdate"></a>

`PUT /api/v1/inboxes/{id}/`

> Body parameter

```json
{
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="v1inboxesupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 收件匣.|
|body|body|[Inbox](#schemainbox)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="v1inboxesupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Inbox](#schemainbox)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1InboxesPartialUpdate

<a id="opIdv1InboxesPartialUpdate"></a>

`PATCH /api/v1/inboxes/{id}/`

> Body parameter

```json
{
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "channelType": "line",
  "name": "string",
  "autoReplySchedules": [
    {
      "isEnabled": true,
      "timeSlots": [
        [
          "14:15:22Z"
        ]
      ]
    }
  ],
  "channel": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387"
}
```

<h3 id="v1inboxespartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 收件匣.|
|body|body|[PatchedInbox](#schemapatchedinbox)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="v1inboxespartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Inbox](#schemainbox)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1InboxesDestroy

<a id="opIdv1InboxesDestroy"></a>

`DELETE /api/v1/inboxes/{id}/`

<h3 id="v1inboxesdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 收件匣.|

<h3 id="v1inboxesdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1InboxesUpdateAllEnableGroupMentionCreate

<a id="opIdv1InboxesUpdateAllEnableGroupMentionCreate"></a>

`POST /api/v1/inboxes/{id}/update-all-enable-group-mention/`

更新全部 Line 群組提及功能狀態。

Args:
    request: HTTP request 物件
    pk: inbox primary key

Returns:
    Response: 更新成功回應

> Body parameter

```json
{
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="v1inboxesupdateallenablegroupmentioncreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 收件匣.|
|body|body|[Inbox](#schemainbox)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}
```

<h3 id="v1inboxesupdateallenablegroupmentioncreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Inbox](#schemainbox)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1MessagesList

<a id="opIdv1MessagesList"></a>

`GET /api/v1/messages/`

<h3 id="v1messageslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|conversation|query|string(uuid)|false|none|
|cursor|query|string|false|The pagination cursor value.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
      "sender": {
        "id": 0,
        "name": "string",
        "avatar": "http://example.com"
      },
      "type": "incoming",
      "content": "string",
      "feedback": "like",
      "createdAt": "string",
      "attachments": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "type": "other",
          "filename": "string",
          "file": "http://example.com"
        }
      ],
      "citations": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "filename": "string",
          "file": "http://example.com",
          "fileType": "string",
          "size": 0,
          "status": "initial",
          "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
          "parser": {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "name": "string",
            "provider": "maiagent",
            "priority": 0
          },
          "createdAt": "string"
        }
      ],
      "citationNodes": [
        {
          "chatbotTextNode": {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "charactersCount": 0,
            "hitsCount": 0,
            "text": "string",
            "updatedAt": "string",
            "filename": "string"
          },
          "score": 0.1,
          "displayScore": "string"
        }
      ]
    }
  ]
}
```

<h3 id="v1messageslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedMessageList](#schemapaginatedmessagelist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1MessagesCreate

<a id="opIdv1MessagesCreate"></a>

`POST /api/v1/messages/`

> Body parameter

```json
{
  "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
  "sender": {
    "id": 0,
    "name": "string",
    "avatar": "http://example.com"
  },
  "type": "incoming",
  "content": "string",
  "feedback": "like",
  "attachments": [
    {
      "type": "other",
      "filename": "string",
      "file": "http://example.com"
    }
  ]
}
```

<h3 id="v1messagescreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Message](#schemamessage)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
  "sender": {
    "id": 0,
    "name": "string",
    "avatar": "http://example.com"
  },
  "type": "incoming",
  "content": "string",
  "feedback": "like",
  "createdAt": "string",
  "attachments": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "type": "other",
      "filename": "string",
      "file": "http://example.com"
    }
  ],
  "citations": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "filename": "string",
      "file": "http://example.com",
      "fileType": "string",
      "size": 0,
      "status": "initial",
      "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
      "parser": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "provider": "maiagent",
        "priority": 0
      },
      "createdAt": "string"
    }
  ],
  "citationNodes": [
    {
      "chatbotTextNode": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "charactersCount": 0,
        "hitsCount": 0,
        "text": "string",
        "updatedAt": "string",
        "filename": "string"
      },
      "score": 0.1,
      "displayScore": "string"
    }
  ]
}
```

<h3 id="v1messagescreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Message](#schemamessage)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1MessagesRetrieve

<a id="opIdv1MessagesRetrieve"></a>

`GET /api/v1/messages/{id}/`

<h3 id="v1messagesretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 訊息.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
  "sender": {
    "id": 0,
    "name": "string",
    "avatar": "http://example.com"
  },
  "type": "incoming",
  "content": "string",
  "feedback": "like",
  "createdAt": "string",
  "attachments": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "type": "other",
      "filename": "string",
      "file": "http://example.com"
    }
  ],
  "citations": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "filename": "string",
      "file": "http://example.com",
      "fileType": "string",
      "size": 0,
      "status": "initial",
      "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
      "parser": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "provider": "maiagent",
        "priority": 0
      },
      "createdAt": "string"
    }
  ],
  "citationNodes": [
    {
      "chatbotTextNode": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "charactersCount": 0,
        "hitsCount": 0,
        "text": "string",
        "updatedAt": "string",
        "filename": "string"
      },
      "score": 0.1,
      "displayScore": "string"
    }
  ]
}
```

<h3 id="v1messagesretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Message](#schemamessage)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1MessagesOutgoingCreate

<a id="opIdv1MessagesOutgoingCreate"></a>

`POST /api/v1/messages/outgoing/`

> Body parameter

```json
{
  "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
  "sender": {
    "id": 0,
    "name": "string",
    "avatar": "http://example.com"
  },
  "type": "incoming",
  "content": "string",
  "feedback": "like",
  "attachments": [
    {
      "type": "other",
      "filename": "string",
      "file": "http://example.com"
    }
  ]
}
```

<h3 id="v1messagesoutgoingcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Message](#schemamessage)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
  "sender": {
    "id": 0,
    "name": "string",
    "avatar": "http://example.com"
  },
  "type": "incoming",
  "content": "string",
  "feedback": "like",
  "createdAt": "string",
  "attachments": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "type": "other",
      "filename": "string",
      "file": "http://example.com"
    }
  ],
  "citations": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "filename": "string",
      "file": "http://example.com",
      "fileType": "string",
      "size": 0,
      "status": "initial",
      "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
      "parser": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "provider": "maiagent",
        "priority": 0
      },
      "createdAt": "string"
    }
  ],
  "citationNodes": [
    {
      "chatbotTextNode": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "charactersCount": 0,
        "hitsCount": 0,
        "text": "string",
        "updatedAt": "string",
        "filename": "string"
      },
      "score": 0.1,
      "displayScore": "string"
    }
  ]
}
```

<h3 id="v1messagesoutgoingcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Message](#schemamessage)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="maiagent-api-chatbots">chatbots</h1>

## chatbotsFilesList

<a id="opIdchatbotsFilesList"></a>

`GET /api/chatbots/{chatbotPk}/files/`

<h3 id="chatbotsfileslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "filename": "string",
      "file": "http://example.com",
      "fileType": "string",
      "size": 0,
      "status": "initial",
      "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
      "parser": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "provider": "maiagent",
        "priority": 0
      },
      "createdAt": "string"
    }
  ]
}
```

<h3 id="chatbotsfileslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedChatbotFileList](#schemapaginatedchatbotfilelist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsFilesCreate

<a id="opIdchatbotsFilesCreate"></a>

`POST /api/chatbots/{chatbotPk}/files/`

> Body parameter

```json
{
  "files": [
    {
      "filename": "string",
      "file": "http://example.com",
      "parser": "87c5228b-83f7-4c51-ab10-39b9269cb177"
    }
  ]
}
```

<h3 id="chatbotsfilescreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|body|body|[ChatbotFileCreateFiles](#schemachatbotfilecreatefiles)|true|none|

> Example responses

> 201 Response

```json
{
  "files": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "filename": "string",
      "file": "http://example.com",
      "fileType": "string",
      "size": 0,
      "status": "initial",
      "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
      "parser": "87c5228b-83f7-4c51-ab10-39b9269cb177",
      "createdAt": "string"
    }
  ]
}
```

<h3 id="chatbotsfilescreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[ChatbotFileCreateFiles](#schemachatbotfilecreatefiles)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsFilesRetrieve

<a id="opIdchatbotsFilesRetrieve"></a>

`GET /api/chatbots/{chatbotPk}/files/{id}/`

<h3 id="chatbotsfilesretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "filename": "string",
  "file": "http://example.com",
  "fileType": "string",
  "size": 0,
  "status": "initial",
  "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
  "parser": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "provider": "maiagent",
    "priority": 0
  },
  "createdAt": "string"
}
```

<h3 id="chatbotsfilesretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFile](#schemachatbotfile)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsFilesUpdate

<a id="opIdchatbotsFilesUpdate"></a>

`PUT /api/chatbots/{chatbotPk}/files/{id}/`

> Body parameter

```json
{
  "filename": "string",
  "file": "http://example.com",
  "parser": "87c5228b-83f7-4c51-ab10-39b9269cb177"
}
```

<h3 id="chatbotsfilesupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案.|
|body|body|[ChatbotFileCreate](#schemachatbotfilecreate)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "filename": "string",
  "file": "http://example.com",
  "fileType": "string",
  "size": 0,
  "status": "initial",
  "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
  "parser": "87c5228b-83f7-4c51-ab10-39b9269cb177",
  "createdAt": "string"
}
```

<h3 id="chatbotsfilesupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFileCreate](#schemachatbotfilecreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsFilesPartialUpdate

<a id="opIdchatbotsFilesPartialUpdate"></a>

`PATCH /api/chatbots/{chatbotPk}/files/{id}/`

> Body parameter

```json
{
  "filename": "string",
  "file": "http://example.com",
  "parser": {
    "name": "string",
    "provider": "maiagent"
  }
}
```

<h3 id="chatbotsfilespartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案.|
|body|body|[PatchedChatbotFile](#schemapatchedchatbotfile)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "filename": "string",
  "file": "http://example.com",
  "fileType": "string",
  "size": 0,
  "status": "initial",
  "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
  "parser": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "provider": "maiagent",
    "priority": 0
  },
  "createdAt": "string"
}
```

<h3 id="chatbotsfilespartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFile](#schemachatbotfile)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsFilesDestroy

<a id="opIdchatbotsFilesDestroy"></a>

`DELETE /api/chatbots/{chatbotPk}/files/{id}/`

<h3 id="chatbotsfilesdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案.|

<h3 id="chatbotsfilesdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsFilesLatestFailedReasonRetrieve

<a id="opIdchatbotsFilesLatestFailedReasonRetrieve"></a>

`GET /api/chatbots/{chatbotPk}/files/{id}/latest-failed-reason/`

獲取指定 Chatbot 檔案的最新失敗原因。

<h3 id="chatbotsfileslatestfailedreasonretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "filename": "string",
  "file": "http://example.com",
  "fileType": "string",
  "size": 0,
  "status": "initial",
  "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
  "parser": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "provider": "maiagent",
    "priority": 0
  },
  "createdAt": "string"
}
```

<h3 id="chatbotsfileslatestfailedreasonretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFile](#schemachatbotfile)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsFilesBatchDeleteCreate

<a id="opIdchatbotsFilesBatchDeleteCreate"></a>

`POST /api/chatbots/{chatbotPk}/files/batch-delete/`

批次刪除多個指定的 chatbot file

payload:
{
    "ids": ["file_id_1", "file_id_2", "file_id_3"]
}

> Body parameter

```json
{
  "filename": "string",
  "file": "http://example.com",
  "parser": {
    "name": "string",
    "provider": "maiagent"
  }
}
```

<h3 id="chatbotsfilesbatchdeletecreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|body|body|[ChatbotFile](#schemachatbotfile)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "filename": "string",
  "file": "http://example.com",
  "fileType": "string",
  "size": 0,
  "status": "initial",
  "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
  "parser": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "provider": "maiagent",
    "priority": 0
  },
  "createdAt": "string"
}
```

<h3 id="chatbotsfilesbatchdeletecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFile](#schemachatbotfile)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsLlmUsageStatisticsRetrieve

<a id="opIdchatbotsLlmUsageStatisticsRetrieve"></a>

`GET /api/chatbots/{chatbotPk}/llm-usage-statistics/`

統一的列表視圖，根據請求參數返回不同的數據：

time_granularity=day/month：返回指定時間區間的每日/每月統計
- start_date
- end_date

<h3 id="chatbotsllmusagestatisticsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string|true|none|

<h3 id="chatbotsllmusagestatisticsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsStatisticsRetrieve

<a id="opIdchatbotsStatisticsRetrieve"></a>

`GET /api/chatbots/{chatbotPk}/statistics/`

<h3 id="chatbotsstatisticsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string|true|none|

<h3 id="chatbotsstatisticsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## chatbotsUsageStatisticsList

<a id="opIdchatbotsUsageStatisticsList"></a>

`GET /api/chatbots/{chatbotPk}/usage-statistics/`

<h3 id="chatbotsusagestatisticslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "chatbotId": "964783cd-c648-4628-8262-55dac3831d8f",
      "uploadedFilesSizeTotal": -2147483648,
      "conversationsCount": -2147483648
    }
  ]
}
```

<h3 id="chatbotsusagestatisticslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedChatbotUsageStatisticList](#schemapaginatedchatbotusagestatisticlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="maiagent-api-conversations">conversations</h1>

## conversationsAttachmentsCreate

<a id="opIdconversationsAttachmentsCreate"></a>

`POST /api/conversations/{conversationPk}/attachments/`

> Body parameter

```json
{
  "type": "other",
  "filename": "string",
  "file": "http://example.com",
  "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa"
}
```

<h3 id="conversationsattachmentscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|conversationPk|path|string|true|none|
|body|body|[AttachmentCreateInput](#schemaattachmentcreateinput)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="conversationsattachmentscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[AttachmentCreateInput](#schemaattachmentcreateinput)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

<h1 id="maiagent-api-database-examples">database-examples</h1>

## databaseExamplesList

<a id="opIddatabaseExamplesList"></a>

`GET /api/database-examples/`

提供資料庫連線字串範例的 API

> Example responses

> 200 Response

```json
[
  {
    "databaseType": "postgresql",
    "databaseTypeExample": "string",
    "isActive": true
  }
]
```

<h3 id="databaseexampleslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="databaseexampleslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[DatabaseExample](#schemadatabaseexample)]|false|none|none|
|» databaseType|[DatabaseTypeEnum](#schemadatabasetypeenum)|false|none|資料庫類型選項<br><br>* `postgresql` - PostgreSQL<br>* `mysql` - MySQL|
|» databaseTypeExample|string|true|none|例如：postgresql://db_user:db_password@db_ip:dp_port/db_name|
|» isActive|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|databaseType|postgresql|
|databaseType|mysql|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## databaseExamplesRetrieve

<a id="opIddatabaseExamplesRetrieve"></a>

`GET /api/database-examples/{id}/`

提供資料庫連線字串範例的 API

<h3 id="databaseexamplesretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 資料庫連線範例.|

> Example responses

> 200 Response

```json
{
  "databaseType": "postgresql",
  "databaseTypeExample": "string",
  "isActive": true
}
```

<h3 id="databaseexamplesretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[DatabaseExample](#schemadatabaseexample)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="maiagent-api-platforms">Platforms</h1>

## facebookSystemUserList

<a id="opIdfacebookSystemUserList"></a>

`GET /api/facebook-system-user/`

<h3 id="facebooksystemuserlist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "systemUserId": "string"
    }
  ]
}
```

<h3 id="facebooksystemuserlist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedFacebookSystemUserList](#schemapaginatedfacebooksystemuserlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## facebookSystemUserCreate

<a id="opIdfacebookSystemUserCreate"></a>

`POST /api/facebook-system-user/`

> Body parameter

```json
{
  "code": "string"
}
```

<h3 id="facebooksystemusercreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[FacebookSystemUserCreate](#schemafacebooksystemusercreate)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "systemUserId": "string"
}
```

<h3 id="facebooksystemusercreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[FacebookSystemUser](#schemafacebooksystemuser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## facebookSystemUserPagesList

<a id="opIdfacebookSystemUserPagesList"></a>

`GET /api/facebook-system-user/{facebookSystemUserPk}/pages/`

<h3 id="facebooksystemuserpageslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|facebookSystemUserPk|path|string|true|none|

> Example responses

> 200 Response

```json
[
  {
    "pageId": "string",
    "name": "string"
  }
]
```

<h3 id="facebooksystemuserpageslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="facebooksystemuserpageslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[FacebookPage](#schemafacebookpage)]|false|none|none|
|» pageId|string|true|none|none|
|» name|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## lineChannelCreate

<a id="opIdlineChannelCreate"></a>

`POST /api/line-channel/`

> Body parameter

```json
{
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "enableGroupMention": true
}
```

<h3 id="linechannelcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[LineChannel](#schemalinechannel)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "webhookUrl": "string",
  "enableGroupMention": true
}
```

<h3 id="linechannelcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[LineChannel](#schemalinechannel)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## lineChannelRetrieve

<a id="opIdlineChannelRetrieve"></a>

`GET /api/line-channel/{id}/`

<h3 id="linechannelretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this line channel.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "webhookUrl": "string",
  "enableGroupMention": true
}
```

<h3 id="linechannelretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[LineChannel](#schemalinechannel)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## lineChannelUpdate

<a id="opIdlineChannelUpdate"></a>

`PUT /api/line-channel/{id}/`

> Body parameter

```json
{
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "enableGroupMention": true
}
```

<h3 id="linechannelupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this line channel.|
|body|body|[LineChannel](#schemalinechannel)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "webhookUrl": "string",
  "enableGroupMention": true
}
```

<h3 id="linechannelupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[LineChannel](#schemalinechannel)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## lineChannelPartialUpdate

<a id="opIdlineChannelPartialUpdate"></a>

`PATCH /api/line-channel/{id}/`

> Body parameter

```json
{
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "enableGroupMention": true
}
```

<h3 id="linechannelpartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this line channel.|
|body|body|[PatchedLineChannel](#schemapatchedlinechannel)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "webhookUrl": "string",
  "enableGroupMention": true
}
```

<h3 id="linechannelpartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[LineChannel](#schemalinechannel)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## messengerRetrieve

<a id="opIdmessengerRetrieve"></a>

`GET /api/messenger/{id}/`

<h3 id="messengerretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this messenger.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "pageId": "string",
  "pageName": "string"
}
```

<h3 id="messengerretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Messenger](#schemamessenger)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1FacebookSystemUserList

<a id="opIdv1FacebookSystemUserList"></a>

`GET /api/v1/facebook-system-user/`

<h3 id="v1facebooksystemuserlist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "systemUserId": "string"
    }
  ]
}
```

<h3 id="v1facebooksystemuserlist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedFacebookSystemUserList](#schemapaginatedfacebooksystemuserlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1FacebookSystemUserCreate

<a id="opIdv1FacebookSystemUserCreate"></a>

`POST /api/v1/facebook-system-user/`

> Body parameter

```json
{
  "code": "string"
}
```

<h3 id="v1facebooksystemusercreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[FacebookSystemUserCreate](#schemafacebooksystemusercreate)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "systemUserId": "string"
}
```

<h3 id="v1facebooksystemusercreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[FacebookSystemUser](#schemafacebooksystemuser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1FacebookSystemUserPagesList

<a id="opIdv1FacebookSystemUserPagesList"></a>

`GET /api/v1/facebook-system-user/{facebookSystemUserPk}/pages/`

<h3 id="v1facebooksystemuserpageslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|facebookSystemUserPk|path|string|true|none|

> Example responses

> 200 Response

```json
[
  {
    "pageId": "string",
    "name": "string"
  }
]
```

<h3 id="v1facebooksystemuserpageslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="v1facebooksystemuserpageslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[FacebookPage](#schemafacebookpage)]|false|none|none|
|» pageId|string|true|none|none|
|» name|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1LineChannelCreate

<a id="opIdv1LineChannelCreate"></a>

`POST /api/v1/line-channel/`

> Body parameter

```json
{
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "enableGroupMention": true
}
```

<h3 id="v1linechannelcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[LineChannel](#schemalinechannel)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "webhookUrl": "string",
  "enableGroupMention": true
}
```

<h3 id="v1linechannelcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[LineChannel](#schemalinechannel)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1LineChannelRetrieve

<a id="opIdv1LineChannelRetrieve"></a>

`GET /api/v1/line-channel/{id}/`

<h3 id="v1linechannelretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this line channel.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "webhookUrl": "string",
  "enableGroupMention": true
}
```

<h3 id="v1linechannelretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[LineChannel](#schemalinechannel)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1LineChannelUpdate

<a id="opIdv1LineChannelUpdate"></a>

`PUT /api/v1/line-channel/{id}/`

> Body parameter

```json
{
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "enableGroupMention": true
}
```

<h3 id="v1linechannelupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this line channel.|
|body|body|[LineChannel](#schemalinechannel)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "webhookUrl": "string",
  "enableGroupMention": true
}
```

<h3 id="v1linechannelupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[LineChannel](#schemalinechannel)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1LineChannelPartialUpdate

<a id="opIdv1LineChannelPartialUpdate"></a>

`PATCH /api/v1/line-channel/{id}/`

> Body parameter

```json
{
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "enableGroupMention": true
}
```

<h3 id="v1linechannelpartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this line channel.|
|body|body|[PatchedLineChannel](#schemapatchedlinechannel)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "webhookUrl": "string",
  "enableGroupMention": true
}
```

<h3 id="v1linechannelpartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[LineChannel](#schemalinechannel)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1MessengerRetrieve

<a id="opIdv1MessengerRetrieve"></a>

`GET /api/v1/messenger/{id}/`

<h3 id="v1messengerretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this messenger.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "pageId": "string",
  "pageName": "string"
}
```

<h3 id="v1messengerretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Messenger](#schemamessenger)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1WebChatsList

<a id="opIdv1WebChatsList"></a>

`GET /api/v1/web-chats/`

> Example responses

> 200 Response

```json
[
  {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "avatar": "http://example.com",
    "name": "string"
  }
]
```

<h3 id="v1webchatslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="v1webchatslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[WebChatList](#schemawebchatlist)]|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» avatar|string(uri)¦null|false|none|none|
|» name|string|true|read-only|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1WebChatsCreate

<a id="opIdv1WebChatsCreate"></a>

`POST /api/v1/web-chats/`

> Body parameter

```json
{
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true
}
```

<h3 id="v1webchatscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[WebChatBase](#schemawebchatbase)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "enableSpeech": true,
  "displayGreeting": "string",
  "displayConversationStarters": "string",
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true,
  "accessType": "web"
}
```

<h3 id="v1webchatscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[WebChatBase](#schemawebchatbase)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1WebChatsRetrieve

<a id="opIdv1WebChatsRetrieve"></a>

`GET /api/v1/web-chats/{id}/`

<h3 id="v1webchatsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this web chat.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "enableSpeech": true,
  "displayGreeting": "string",
  "displayConversationStarters": "string",
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true,
  "accessType": "web"
}
```

<h3 id="v1webchatsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[WebChatBase](#schemawebchatbase)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1WebChatsUpdate

<a id="opIdv1WebChatsUpdate"></a>

`PUT /api/v1/web-chats/{id}/`

> Body parameter

```json
{
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true
}
```

<h3 id="v1webchatsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this web chat.|
|body|body|[WebChatBase](#schemawebchatbase)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "enableSpeech": true,
  "displayGreeting": "string",
  "displayConversationStarters": "string",
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true,
  "accessType": "web"
}
```

<h3 id="v1webchatsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[WebChatBase](#schemawebchatbase)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1WebChatsPartialUpdate

<a id="opIdv1WebChatsPartialUpdate"></a>

`PATCH /api/v1/web-chats/{id}/`

> Body parameter

```json
{
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true
}
```

<h3 id="v1webchatspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this web chat.|
|body|body|[PatchedWebChatBase](#schemapatchedwebchatbase)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "enableSpeech": true,
  "displayGreeting": "string",
  "displayConversationStarters": "string",
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true,
  "accessType": "web"
}
```

<h3 id="v1webchatspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[WebChatBase](#schemawebchatbase)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## webChatsList

<a id="opIdwebChatsList"></a>

`GET /api/web-chats/`

> Example responses

> 200 Response

```json
[
  {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "avatar": "http://example.com",
    "name": "string"
  }
]
```

<h3 id="webchatslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="webchatslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[WebChatList](#schemawebchatlist)]|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» avatar|string(uri)¦null|false|none|none|
|» name|string|true|read-only|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## webChatsCreate

<a id="opIdwebChatsCreate"></a>

`POST /api/web-chats/`

> Body parameter

```json
{
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true
}
```

<h3 id="webchatscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[WebChatBase](#schemawebchatbase)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "enableSpeech": true,
  "displayGreeting": "string",
  "displayConversationStarters": "string",
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true,
  "accessType": "web"
}
```

<h3 id="webchatscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[WebChatBase](#schemawebchatbase)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## webChatsRetrieve

<a id="opIdwebChatsRetrieve"></a>

`GET /api/web-chats/{id}/`

<h3 id="webchatsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this web chat.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "enableSpeech": true,
  "displayGreeting": "string",
  "displayConversationStarters": "string",
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true,
  "accessType": "web"
}
```

<h3 id="webchatsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[WebChatBase](#schemawebchatbase)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## webChatsUpdate

<a id="opIdwebChatsUpdate"></a>

`PUT /api/web-chats/{id}/`

> Body parameter

```json
{
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true
}
```

<h3 id="webchatsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this web chat.|
|body|body|[WebChatBase](#schemawebchatbase)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "enableSpeech": true,
  "displayGreeting": "string",
  "displayConversationStarters": "string",
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true,
  "accessType": "web"
}
```

<h3 id="webchatsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[WebChatBase](#schemawebchatbase)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## webChatsPartialUpdate

<a id="opIdwebChatsPartialUpdate"></a>

`PATCH /api/web-chats/{id}/`

> Body parameter

```json
{
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true
}
```

<h3 id="webchatspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this web chat.|
|body|body|[PatchedWebChatBase](#schemapatchedwebchatbase)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "enableSpeech": true,
  "displayGreeting": "string",
  "displayConversationStarters": "string",
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true,
  "accessType": "web"
}
```

<h3 id="webchatspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[WebChatBase](#schemawebchatbase)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="maiagent-api-organizations">organizations</h1>

## organizationsList

<a id="opIdorganizationsList"></a>

`GET /api/organizations/`

<h3 id="organizationslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "owner": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string"
      },
      "createdAt": "string"
    }
  ]
}
```

<h3 id="organizationslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedOrganizationListList](#schemapaginatedorganizationlistlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsCreate

<a id="opIdorganizationsCreate"></a>

`POST /api/organizations/`

> Body parameter

```json
{
  "name": "string"
}
```

<h3 id="organizationscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Organization](#schemaorganization)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "owner": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string"
  },
  "createdAt": "string",
  "usageStatistics": "string",
  "organizationPlan": "string"
}
```

<h3 id="organizationscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Organization](#schemaorganization)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsGroupsList

<a id="opIdorganizationsGroupsList"></a>

`GET /api/organizations/{organizationPk}/groups/`

<h3 id="organizationsgroupslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|organizationPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "permissions": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "description": "string"
        }
      ],
      "createdAt": "string"
    }
  ]
}
```

<h3 id="organizationsgroupslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedGroupList](#schemapaginatedgrouplist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsGroupsCreate

<a id="opIdorganizationsGroupsCreate"></a>

`POST /api/organizations/{organizationPk}/groups/`

> Body parameter

```json
{
  "name": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "permissions": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ]
}
```

<h3 id="organizationsgroupscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|organizationPk|path|string(uuid)|true|none|
|body|body|[GroupCreate](#schemagroupcreate)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "permissions": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ],
  "createdAt": "string"
}
```

<h3 id="organizationsgroupscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[GroupCreate](#schemagroupcreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsGroupsGroupChatbotsList

<a id="opIdorganizationsGroupsGroupChatbotsList"></a>

`GET /api/organizations/{organizationPk}/groups/{groupPk}/group-chatbots/`

<h3 id="organizationsgroupsgroupchatbotslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|organizationPk|path|string|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "group": "fbd899a6-8a66-4f51-a95d-68668de198ae",
      "chatbot": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
        "name": "string",
        "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
        "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
        "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
        "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
        "instructions": "string",
        "webhookUrl": "http://example.com",
        "apiWebChatId": "string",
        "updatedAt": "string",
        "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
        "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
        "replyMode": "normal",
        "template": "string",
        "unanswerableTemplate": "string",
        "totalWordsCount": -9223372036854776000,
        "enableChineseConversion": true,
        "outputFormat": null,
        "databaseUrl": "string",
        "databaseType": "string"
      },
      "createdAt": "string"
    }
  ]
}
```

<h3 id="organizationsgroupsgroupchatbotslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedGroupChatbotList](#schemapaginatedgroupchatbotlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsGroupsGroupChatbotsCreate

<a id="opIdorganizationsGroupsGroupChatbotsCreate"></a>

`POST /api/organizations/{organizationPk}/groups/{groupPk}/group-chatbots/`

> Body parameter

```json
{
  "group": "fbd899a6-8a66-4f51-a95d-68668de198ae",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133"
}
```

<h3 id="organizationsgroupsgroupchatbotscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|organizationPk|path|string|true|none|
|body|body|[GroupChatbotCreate](#schemagroupchatbotcreate)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "group": "fbd899a6-8a66-4f51-a95d-68668de198ae",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "createdAt": "string"
}
```

<h3 id="organizationsgroupsgroupchatbotscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[GroupChatbotCreate](#schemagroupchatbotcreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsGroupsGroupChatbotsDestroy

<a id="opIdorganizationsGroupsGroupChatbotsDestroy"></a>

`DELETE /api/organizations/{organizationPk}/groups/{groupPk}/group-chatbots/{id}/`

<h3 id="organizationsgroupsgroupchatbotsdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this 群組 AI 助理.|
|organizationPk|path|string|true|none|

<h3 id="organizationsgroupsgroupchatbotsdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsGroupsGroupChatbotsBulkCreateCreate

<a id="opIdorganizationsGroupsGroupChatbotsBulkCreateCreate"></a>

`POST /api/organizations/{organizationPk}/groups/{groupPk}/group-chatbots/bulk-create/`

<h3 id="organizationsgroupsgroupchatbotsbulkcreatecreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|organizationPk|path|string|true|none|

<h3 id="organizationsgroupsgroupchatbotsbulkcreatecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsGroupsGroupMembersList

<a id="opIdorganizationsGroupsGroupMembersList"></a>

`GET /api/organizations/{organizationPk}/groups/{groupPk}/group-members/`

<h3 id="organizationsgroupsgroupmemberslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|organizationPk|path|string|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "member": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "email": "string",
        "organization": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "owner": {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "name": "string"
          },
          "createdAt": "string",
          "usageStatistics": "string",
          "organizationPlan": "string"
        },
        "isOwner": "string",
        "permissions": "string",
        "createdAt": "string"
      },
      "createdAt": "string"
    }
  ]
}
```

<h3 id="organizationsgroupsgroupmemberslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedGroupMemberList](#schemapaginatedgroupmemberlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsGroupsGroupMembersCreate

<a id="opIdorganizationsGroupsGroupMembersCreate"></a>

`POST /api/organizations/{organizationPk}/groups/{groupPk}/group-members/`

> Body parameter

```json
{
  "group": "fbd899a6-8a66-4f51-a95d-68668de198ae",
  "member": "98a5fc57-9089-44da-9515-4171e2d1c593"
}
```

<h3 id="organizationsgroupsgroupmemberscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|organizationPk|path|string|true|none|
|body|body|[GroupMemberCreate](#schemagroupmembercreate)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "group": "fbd899a6-8a66-4f51-a95d-68668de198ae",
  "member": "98a5fc57-9089-44da-9515-4171e2d1c593",
  "createdAt": "string"
}
```

<h3 id="organizationsgroupsgroupmemberscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[GroupMemberCreate](#schemagroupmembercreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsGroupsGroupMembersRetrieve

<a id="opIdorganizationsGroupsGroupMembersRetrieve"></a>

`GET /api/organizations/{organizationPk}/groups/{groupPk}/group-members/{id}/`

<h3 id="organizationsgroupsgroupmembersretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this 群組成員.|
|organizationPk|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "member": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "email": "string",
    "organization": {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "owner": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string"
      },
      "createdAt": "string",
      "usageStatistics": "string",
      "organizationPlan": "string"
    },
    "isOwner": "string",
    "permissions": "string",
    "createdAt": "string"
  },
  "createdAt": "string"
}
```

<h3 id="organizationsgroupsgroupmembersretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[GroupMember](#schemagroupmember)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsGroupsGroupMembersDestroy

<a id="opIdorganizationsGroupsGroupMembersDestroy"></a>

`DELETE /api/organizations/{organizationPk}/groups/{groupPk}/group-members/{id}/`

<h3 id="organizationsgroupsgroupmembersdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this 群組成員.|
|organizationPk|path|string|true|none|

<h3 id="organizationsgroupsgroupmembersdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsGroupsGroupMembersBulkCreateCreate

<a id="opIdorganizationsGroupsGroupMembersBulkCreateCreate"></a>

`POST /api/organizations/{organizationPk}/groups/{groupPk}/group-members/bulk-create/`

<h3 id="organizationsgroupsgroupmembersbulkcreatecreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|organizationPk|path|string|true|none|

<h3 id="organizationsgroupsgroupmembersbulkcreatecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsGroupsRetrieve

<a id="opIdorganizationsGroupsRetrieve"></a>

`GET /api/organizations/{organizationPk}/groups/{id}/`

<h3 id="organizationsgroupsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 群組.|
|organizationPk|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "permissions": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "description": "string"
    }
  ],
  "createdAt": "string"
}
```

<h3 id="organizationsgroupsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Group](#schemagroup)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsGroupsUpdate

<a id="opIdorganizationsGroupsUpdate"></a>

`PUT /api/organizations/{organizationPk}/groups/{id}/`

> Body parameter

```json
{
  "name": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "permissions": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ]
}
```

<h3 id="organizationsgroupsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 群組.|
|organizationPk|path|string(uuid)|true|none|
|body|body|[GroupCreate](#schemagroupcreate)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "permissions": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ],
  "createdAt": "string"
}
```

<h3 id="organizationsgroupsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[GroupCreate](#schemagroupcreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsGroupsPartialUpdate

<a id="opIdorganizationsGroupsPartialUpdate"></a>

`PATCH /api/organizations/{organizationPk}/groups/{id}/`

> Body parameter

```json
{
  "name": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "permissions": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ]
}
```

<h3 id="organizationsgroupspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 群組.|
|organizationPk|path|string(uuid)|true|none|
|body|body|[PatchedGroupCreate](#schemapatchedgroupcreate)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "permissions": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ],
  "createdAt": "string"
}
```

<h3 id="organizationsgroupspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[GroupCreate](#schemagroupcreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsGroupsDestroy

<a id="opIdorganizationsGroupsDestroy"></a>

`DELETE /api/organizations/{organizationPk}/groups/{id}/`

<h3 id="organizationsgroupsdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 群組.|
|organizationPk|path|string(uuid)|true|none|

<h3 id="organizationsgroupsdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsMembersList

<a id="opIdorganizationsMembersList"></a>

`GET /api/organizations/{organizationPk}/members/`

<h3 id="organizationsmemberslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|organizationPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "email": "string",
      "organization": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "owner": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string"
        },
        "createdAt": "string",
        "usageStatistics": "string",
        "organizationPlan": "string"
      },
      "isOwner": "string",
      "permissions": "string",
      "createdAt": "string"
    }
  ]
}
```

<h3 id="organizationsmemberslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedMemberList](#schemapaginatedmemberlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsMembersCreate

<a id="opIdorganizationsMembersCreate"></a>

`POST /api/organizations/{organizationPk}/members/`

> Body parameter

```json
{
  "email": "user@example.com",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387"
}
```

<h3 id="organizationsmemberscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|organizationPk|path|string(uuid)|true|none|
|body|body|[MemberCreate](#schemamembercreate)|true|none|

> Example responses

> 201 Response

```json
{
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "isOwner": "string"
}
```

<h3 id="organizationsmemberscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[MemberCreate](#schemamembercreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsMembersRetrieve

<a id="opIdorganizationsMembersRetrieve"></a>

`GET /api/organizations/{organizationPk}/members/{id}/`

<h3 id="organizationsmembersretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 成員.|
|organizationPk|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "email": "string",
  "organization": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "owner": {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string"
    },
    "createdAt": "string",
    "usageStatistics": "string",
    "organizationPlan": "string"
  },
  "isOwner": "string",
  "permissions": "string",
  "createdAt": "string"
}
```

<h3 id="organizationsmembersretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Member](#schemamember)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsMembersDestroy

<a id="opIdorganizationsMembersDestroy"></a>

`DELETE /api/organizations/{organizationPk}/members/{id}/`

<h3 id="organizationsmembersdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 成員.|
|organizationPk|path|string(uuid)|true|none|

<h3 id="organizationsmembersdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsRetrieve

<a id="opIdorganizationsRetrieve"></a>

`GET /api/organizations/{id}/`

<h3 id="organizationsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 組織.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "owner": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string"
  },
  "createdAt": "string",
  "usageStatistics": "string",
  "organizationPlan": "string"
}
```

<h3 id="organizationsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Organization](#schemaorganization)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsUpdate

<a id="opIdorganizationsUpdate"></a>

`PUT /api/organizations/{id}/`

> Body parameter

```json
{
  "name": "string"
}
```

<h3 id="organizationsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 組織.|
|body|body|[Organization](#schemaorganization)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "owner": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string"
  },
  "createdAt": "string",
  "usageStatistics": "string",
  "organizationPlan": "string"
}
```

<h3 id="organizationsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Organization](#schemaorganization)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## organizationsPartialUpdate

<a id="opIdorganizationsPartialUpdate"></a>

`PATCH /api/organizations/{id}/`

> Body parameter

```json
{
  "name": "string"
}
```

<h3 id="organizationspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 組織.|
|body|body|[PatchedOrganization](#schemapatchedorganization)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "owner": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string"
  },
  "createdAt": "string",
  "usageStatistics": "string",
  "organizationPlan": "string"
}
```

<h3 id="organizationspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Organization](#schemaorganization)|

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
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "provider": "maiagent",
      "priority": 0
    }
  ]
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "provider": "maiagent",
  "priority": 0
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "provider": "maiagent",
  "priority": 0
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
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "provider": "maiagent",
      "priority": 0
    }
  ]
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "provider": "maiagent",
  "priority": 0
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "provider": "maiagent",
  "priority": 0
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

<h1 id="maiagent-api-permissions">permissions</h1>

## permissionsList

<a id="opIdpermissionsList"></a>

`GET /api/permissions/`

<h3 id="permissionslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "description": "string"
    }
  ]
}
```

<h3 id="permissionslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedPermissionList](#schemapaginatedpermissionlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="maiagent-api-projects">projects</h1>

## projectsQuietTrackingRecordsList

<a id="opIdprojectsQuietTrackingRecordsList"></a>

`GET /api/projects/quiet-tracking-records/`

<h3 id="projectsquiettrackingrecordslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|deviceId|query|string|false|none|

> Example responses

> 200 Response

```json
[
  {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "deviceId": "string",
    "metadata": null,
    "createdAt": "string"
  }
]
```

<h3 id="projectsquiettrackingrecordslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="projectsquiettrackingrecordslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[QuietTrackingRecord](#schemaquiettrackingrecord)]|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» deviceId|string|true|none|none|
|» metadata|any|false|none|none|
|» createdAt|string(timestamp)|true|read-only|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## projectsQuietTrackingRecordsCreate

<a id="opIdprojectsQuietTrackingRecordsCreate"></a>

`POST /api/projects/quiet-tracking-records/`

> Body parameter

```json
{
  "deviceId": "string",
  "metadata": null
}
```

<h3 id="projectsquiettrackingrecordscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[QuietTrackingRecord](#schemaquiettrackingrecord)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "deviceId": "string",
  "metadata": null,
  "createdAt": "string"
}
```

<h3 id="projectsquiettrackingrecordscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[QuietTrackingRecord](#schemaquiettrackingrecord)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

<h1 id="maiagent-api-rebuild-web-chat-pages">rebuild-web-chat-pages</h1>

## rebuildWebChatPagesCreate

<a id="opIdrebuildWebChatPagesCreate"></a>

`POST /api/rebuild-web-chat-pages/`

<h3 id="rebuildwebchatpagescreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="maiagent-api-schema">schema</h1>

## schemaRetrieve

<a id="opIdschemaRetrieve"></a>

`GET /api/schema/`

OpenApi3 schema for this API. Format can be selected via content negotiation.

- YAML: application/vnd.oai.openapi
- JSON: application/vnd.oai.openapi+json

<h3 id="schemaretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|format|query|string|false|none|
|lang|query|string|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|format|json|
|format|yaml|
|lang|af|
|lang|ar|
|lang|ar-dz|
|lang|ast|
|lang|az|
|lang|be|
|lang|bg|
|lang|bn|
|lang|br|
|lang|bs|
|lang|ca|
|lang|ckb|
|lang|cs|
|lang|cy|
|lang|da|
|lang|de|
|lang|dsb|
|lang|el|
|lang|en|
|lang|en-au|
|lang|en-gb|
|lang|eo|
|lang|es|
|lang|es-ar|
|lang|es-co|
|lang|es-mx|
|lang|es-ni|
|lang|es-ve|
|lang|et|
|lang|eu|
|lang|fa|
|lang|fi|
|lang|fr|
|lang|fy|
|lang|ga|
|lang|gd|
|lang|gl|
|lang|he|
|lang|hi|
|lang|hr|
|lang|hsb|
|lang|hu|
|lang|hy|
|lang|ia|
|lang|id|
|lang|ig|
|lang|io|
|lang|is|
|lang|it|
|lang|ja|
|lang|ka|
|lang|kab|
|lang|kk|
|lang|km|
|lang|kn|
|lang|ko|
|lang|ky|
|lang|lb|
|lang|lt|
|lang|lv|
|lang|mk|
|lang|ml|
|lang|mn|
|lang|mr|
|lang|ms|
|lang|my|
|lang|nb|
|lang|ne|
|lang|nl|
|lang|nn|
|lang|os|
|lang|pa|
|lang|pl|
|lang|pt|
|lang|pt-br|
|lang|ro|
|lang|ru|
|lang|sk|
|lang|sl|
|lang|sq|
|lang|sr|
|lang|sr-latn|
|lang|sv|
|lang|sw|
|lang|ta|
|lang|te|
|lang|tg|
|lang|th|
|lang|tk|
|lang|tr|
|lang|tt|
|lang|udm|
|lang|ug|
|lang|uk|
|lang|ur|
|lang|uz|
|lang|vi|
|lang|zh-hans|
|lang|zh-hant|

> Example responses

> 200 Response

```json
{
  "property1": null,
  "property2": null
}
```

<h3 id="schemaretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="schemaretrieve-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» **additionalProperties**|any|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

<h1 id="maiagent-api-ailabs">Ailabs</h1>

## speechesAilabsTokenCreate

<a id="opIdspeechesAilabsTokenCreate"></a>

`POST /api/speeches/ailabs/token/`

<h3 id="speechesailabstokencreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1SpeechesAilabsTokenCreate

<a id="opIdv1SpeechesAilabsTokenCreate"></a>

`POST /api/v1/speeches/ailabs/token/`

<h3 id="v1speechesailabstokencreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

<h1 id="maiagent-api-speeches">Speeches</h1>

## speechesAzureTokenCreate

<a id="opIdspeechesAzureTokenCreate"></a>

`POST /api/speeches/azure/token/`

<h3 id="speechesazuretokencreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## speechesTextToSpeechCreate

<a id="opIdspeechesTextToSpeechCreate"></a>

`POST /api/speeches/text-to-speech/`

<h3 id="speechestexttospeechcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1SpeechesAzureTokenCreate

<a id="opIdv1SpeechesAzureTokenCreate"></a>

`POST /api/v1/speeches/azure/token/`

<h3 id="v1speechesazuretokencreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1SpeechesTextToSpeechCreate

<a id="opIdv1SpeechesTextToSpeechCreate"></a>

`POST /api/v1/speeches/text-to-speech/`

<h3 id="v1speechestexttospeechcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

<h1 id="maiagent-api-upload-presigned-url">upload-presigned-url</h1>

## uploadPresignedUrlCreate

<a id="opIduploadPresignedUrlCreate"></a>

`POST /api/upload-presigned-url/`

> Body parameter

```json
{
  "modelName": "string",
  "fieldName": "string",
  "filename": "string",
  "fileSize": 0
}
```

<h3 id="uploadpresignedurlcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UploadPresignedUrl](#schemauploadpresignedurl)|true|none|

> Example responses

> 200 Response

```json
{
  "modelName": "string",
  "fieldName": "string",
  "filename": "string",
  "fileSize": 0
}
```

<h3 id="uploadpresignedurlcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[UploadPresignedUrl](#schemauploadpresignedurl)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

<h1 id="maiagent-api-users">users</h1>

## usersList

<a id="opIdusersList"></a>

`GET /api/users/`

<h3 id="userslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "avatar": "http://example.com",
      "name": "string",
      "email": "user@example.com",
      "company": "string",
      "invitationCode": "string",
      "apiKeys": "string",
      "permissions": "string"
    }
  ]
}
```

<h3 id="userslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedUserList](#schemapaginateduserlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## usersRetrieve

<a id="opIdusersRetrieve"></a>

`GET /api/users/{id}/`

<h3 id="usersretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 使用者.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="usersretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## usersUpdate

<a id="opIdusersUpdate"></a>

`PUT /api/users/{id}/`

> Body parameter

```json
{
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string"
}
```

<h3 id="usersupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 使用者.|
|body|body|[User](#schemauser)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="usersupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## usersPartialUpdate

<a id="opIdusersPartialUpdate"></a>

`PATCH /api/users/{id}/`

> Body parameter

```json
{
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string"
}
```

<h3 id="userspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 使用者.|
|body|body|[PatchedUser](#schemapatcheduser)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="userspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## usersCurrentRetrieve

<a id="opIdusersCurrentRetrieve"></a>

`GET /api/users/current/`

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="userscurrentretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## usersCurrentUpdate

<a id="opIdusersCurrentUpdate"></a>

`PUT /api/users/current/`

> Body parameter

```json
{
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string"
}
```

<h3 id="userscurrentupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[User](#schemauser)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="userscurrentupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## usersCurrentPartialUpdate

<a id="opIdusersCurrentPartialUpdate"></a>

`PATCH /api/users/current/`

> Body parameter

```json
{
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string"
}
```

<h3 id="userscurrentpartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PatchedUser](#schemapatcheduser)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="userscurrentpartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="maiagent-api-v1">v1</h1>

## v1AllowedFileTypesRetrieve

<a id="opIdv1AllowedFileTypesRetrieve"></a>

`GET /api/v1/allowed-file-types/`

<h3 id="v1allowedfiletypesretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1AttachmentsList

<a id="opIdv1AttachmentsList"></a>

`GET /api/v1/attachments/`

<h3 id="v1attachmentslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "type": "other",
      "filename": "string",
      "file": "http://example.com"
    }
  ]
}
```

<h3 id="v1attachmentslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedAttachmentList](#schemapaginatedattachmentlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1AttachmentsCreate

<a id="opIdv1AttachmentsCreate"></a>

`POST /api/v1/attachments/`

> Body parameter

```json
{
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="v1attachmentscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Attachment](#schemaattachment)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="v1attachmentscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Attachment](#schemaattachment)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1AttachmentsRetrieve

<a id="opIdv1AttachmentsRetrieve"></a>

`GET /api/v1/attachments/{id}/`

<h3 id="v1attachmentsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this attachment.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="v1attachmentsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Attachment](#schemaattachment)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1AttachmentsUpdate

<a id="opIdv1AttachmentsUpdate"></a>

`PUT /api/v1/attachments/{id}/`

> Body parameter

```json
{
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="v1attachmentsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this attachment.|
|body|body|[Attachment](#schemaattachment)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="v1attachmentsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Attachment](#schemaattachment)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1AttachmentsPartialUpdate

<a id="opIdv1AttachmentsPartialUpdate"></a>

`PATCH /api/v1/attachments/{id}/`

> Body parameter

```json
{
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="v1attachmentspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this attachment.|
|body|body|[PatchedAttachment](#schemapatchedattachment)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="v1attachmentspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Attachment](#schemaattachment)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1AttachmentsDestroy

<a id="opIdv1AttachmentsDestroy"></a>

`DELETE /api/v1/attachments/{id}/`

<h3 id="v1attachmentsdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this attachment.|

<h3 id="v1attachmentsdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1AuthTokenCreate

<a id="opIdv1AuthTokenCreate"></a>

`POST /api/v1/auth-token/`

> Body parameter

```json
{
  "username": "string",
  "password": "string"
}
```

```yaml
username: string
password: string

```

<h3 id="v1authtokencreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AuthToken](#schemaauthtoken)|true|none|

> Example responses

> 200 Response

```json
{
  "token": "string"
}
```

<h3 id="v1authtokencreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[AuthToken](#schemaauthtoken)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1AuthKeycloakLoginCreate

<a id="opIdv1AuthKeycloakLoginCreate"></a>

`POST /api/v1/auth/keycloak/login/`

> Body parameter

```json
{
  "serverUrl": "http://example.com",
  "realm": "string",
  "clientId": "string",
  "accessToken": "string",
  "refreshToken": "string"
}
```

<h3 id="v1authkeycloaklogincreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Keycloak](#schemakeycloak)|true|none|

> Example responses

> 200 Response

```json
{
  "serverUrl": "http://example.com",
  "realm": "string",
  "clientId": "string",
  "accessToken": "string",
  "refreshToken": "string"
}
```

<h3 id="v1authkeycloaklogincreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Keycloak](#schemakeycloak)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1AuthKeycloakLogoutCreate

<a id="opIdv1AuthKeycloakLogoutCreate"></a>

`POST /api/v1/auth/keycloak/logout/`

> Body parameter

```json
{
  "serverUrl": "http://example.com",
  "realm": "string",
  "clientId": "string",
  "accessToken": "string",
  "refreshToken": "string"
}
```

<h3 id="v1authkeycloaklogoutcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Keycloak](#schemakeycloak)|true|none|

> Example responses

> 200 Response

```json
{
  "serverUrl": "http://example.com",
  "realm": "string",
  "clientId": "string",
  "accessToken": "string",
  "refreshToken": "string"
}
```

<h3 id="v1authkeycloaklogoutcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Keycloak](#schemakeycloak)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1AuthLoginCreate

<a id="opIdv1AuthLoginCreate"></a>

`POST /api/v1/auth/login/`

Check the credentials and return the REST Token
if the credentials are valid and authenticated.
Calls Django Auth login method to register User ID
in Django session framework

Accept the following POST parameters: username, password
Return the REST Framework Token Object's key.

> Body parameter

```json
{
  "username": "string",
  "email": "user@example.com",
  "password": "string"
}
```

<h3 id="v1authlogincreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Login](#schemalogin)|true|none|

> Example responses

> 200 Response

```json
{
  "access": "string",
  "refresh": "string",
  "user": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "avatar": "http://example.com",
    "name": "string",
    "email": "user@example.com",
    "company": "string",
    "invitationCode": "string",
    "apiKeys": "string",
    "permissions": "string"
  }
}
```

<h3 id="v1authlogincreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[JWT](#schemajwt)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1AuthLogoutCreate

<a id="opIdv1AuthLogoutCreate"></a>

`POST /api/v1/auth/logout/`

Calls Django logout method and delete the Token object
assigned to the current User object.

Accepts/Returns nothing.

> Example responses

> 200 Response

```json
{
  "detail": "string"
}
```

<h3 id="v1authlogoutcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RestAuthDetail](#schemarestauthdetail)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1AuthPasswordChangeCreate

<a id="opIdv1AuthPasswordChangeCreate"></a>

`POST /api/v1/auth/password/change/`

Calls Django Auth SetPasswordForm save method.

Accepts the following POST parameters: new_password1, new_password2
Returns the success/fail message.

> Body parameter

```json
{
  "oldPassword": "string",
  "newPassword1": "string",
  "newPassword2": "string"
}
```

<h3 id="v1authpasswordchangecreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PasswordChange](#schemapasswordchange)|true|none|

> Example responses

> 200 Response

```json
{
  "detail": "string"
}
```

<h3 id="v1authpasswordchangecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RestAuthDetail](#schemarestauthdetail)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1AuthPasswordResetCreate

<a id="opIdv1AuthPasswordResetCreate"></a>

`POST /api/v1/auth/password/reset/`

Calls Django Auth PasswordResetForm save method.

Accepts the following POST parameters: email
Returns the success/fail message.

> Body parameter

```json
{
  "email": "user@example.com"
}
```

<h3 id="v1authpasswordresetcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PasswordReset](#schemapasswordreset)|true|none|

> Example responses

> 200 Response

```json
{
  "detail": "string"
}
```

<h3 id="v1authpasswordresetcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RestAuthDetail](#schemarestauthdetail)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1AuthPasswordResetConfirmCreate

<a id="opIdv1AuthPasswordResetConfirmCreate"></a>

`POST /api/v1/auth/password/reset/confirm/`

Password reset e-mail link is confirmed, therefore
this resets the user's password.

Accepts the following POST parameters: token, uid,
    new_password1, new_password2
Returns the success/fail message.

> Body parameter

```json
{
  "newPassword1": "string",
  "newPassword2": "string",
  "uid": "string",
  "token": "string"
}
```

<h3 id="v1authpasswordresetconfirmcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PasswordResetConfirm](#schemapasswordresetconfirm)|true|none|

> Example responses

> 200 Response

```json
{
  "detail": "string"
}
```

<h3 id="v1authpasswordresetconfirmcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RestAuthDetail](#schemarestauthdetail)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1AuthRegistrationCreate

<a id="opIdv1AuthRegistrationCreate"></a>

`POST /api/v1/auth/registration/`

Registers a new user.

Accepts the following POST parameters: username, email, password1, password2.

> Body parameter

```json
{
  "username": "string",
  "email": "user@example.com",
  "password1": "string",
  "password2": "string",
  "name": "string",
  "company": "string",
  "referralCode": "string"
}
```

<h3 id="v1authregistrationcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CustomizedRegister](#schemacustomizedregister)|true|none|

> Example responses

> 201 Response

```json
{
  "detail": "string"
}
```

<h3 id="v1authregistrationcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[RestAuthDetail](#schemarestauthdetail)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1AuthRegistrationResendEmailCreate

<a id="opIdv1AuthRegistrationResendEmailCreate"></a>

`POST /api/v1/auth/registration/resend-email/`

Resends another email to an unverified email.

Accepts the following POST parameter: email.

> Body parameter

```json
{
  "email": "user@example.com"
}
```

<h3 id="v1authregistrationresendemailcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ResendEmailVerification](#schemaresendemailverification)|true|none|

> Example responses

> 201 Response

```json
{
  "detail": "string"
}
```

<h3 id="v1authregistrationresendemailcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[RestAuthDetail](#schemarestauthdetail)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1AuthRegistrationVerifyEmailCreate

<a id="opIdv1AuthRegistrationVerifyEmailCreate"></a>

`POST /api/v1/auth/registration/verify-email/`

Verifies the email associated with the provided key.

Accepts the following POST parameter: key.

> Body parameter

```json
{
  "key": "string"
}
```

<h3 id="v1authregistrationverifyemailcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[VerifyEmail](#schemaverifyemail)|true|none|

> Example responses

> 200 Response

```json
{
  "detail": "string"
}
```

<h3 id="v1authregistrationverifyemailcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RestAuthDetail](#schemarestauthdetail)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1AuthTokenRefreshCreate

<a id="opIdv1AuthTokenRefreshCreate"></a>

`POST /api/v1/auth/token/refresh/`

Takes a refresh type JSON web token and returns an access type JSON web
token if the refresh token is valid.

> Body parameter

```json
{
  "refresh": "string"
}
```

<h3 id="v1authtokenrefreshcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TokenRefresh](#schematokenrefresh)|true|none|

> Example responses

> 200 Response

```json
{
  "access": "string"
}
```

<h3 id="v1authtokenrefreshcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[TokenRefresh](#schematokenrefresh)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1AuthTokenVerifyCreate

<a id="opIdv1AuthTokenVerifyCreate"></a>

`POST /api/v1/auth/token/verify/`

Takes a token and indicates if it is valid.  This view provides no
information about a token's fitness for a particular use.

> Body parameter

```json
{
  "token": "string"
}
```

<h3 id="v1authtokenverifycreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TokenVerify](#schematokenverify)|true|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="v1authtokenverifycreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[TokenVerify](#schematokenverify)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1AuthUserRetrieve

<a id="opIdv1AuthUserRetrieve"></a>

`GET /api/v1/auth/user/`

Reads and updates UserModel fields
Accepts GET, PUT, PATCH methods.

Default accepted fields: username, first_name, last_name
Default display fields: pk, username, email, first_name, last_name
Read-only fields: pk, email

Returns UserModel fields.

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="v1authuserretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1AuthUserUpdate

<a id="opIdv1AuthUserUpdate"></a>

`PUT /api/v1/auth/user/`

Reads and updates UserModel fields
Accepts GET, PUT, PATCH methods.

Default accepted fields: username, first_name, last_name
Default display fields: pk, username, email, first_name, last_name
Read-only fields: pk, email

Returns UserModel fields.

> Body parameter

```json
{
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string"
}
```

<h3 id="v1authuserupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[User](#schemauser)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="v1authuserupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1AuthUserPartialUpdate

<a id="opIdv1AuthUserPartialUpdate"></a>

`PATCH /api/v1/auth/user/`

Reads and updates UserModel fields
Accepts GET, PUT, PATCH methods.

Default accepted fields: username, first_name, last_name
Default display fields: pk, username, email, first_name, last_name
Read-only fields: pk, email

Returns UserModel fields.

> Body parameter

```json
{
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string"
}
```

<h3 id="v1authuserpartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PatchedUser](#schemapatcheduser)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="v1authuserpartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1BuiltInWorkflowsList

<a id="opIdv1BuiltInWorkflowsList"></a>

`GET /api/v1/built-in-workflows/`

> Example responses

> 200 Response

```json
[
  {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string"
  }
]
```

<h3 id="v1builtinworkflowslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="v1builtinworkflowslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[BuiltInWorkflow](#schemabuiltinworkflow)]|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» name|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotTextNodesList

<a id="opIdv1ChatbotTextNodesList"></a>

`GET /api/v1/chatbot-text-nodes/`

<h3 id="v1chatbottextnodeslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotFileContent|query|string(uuid)|false|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "charactersCount": 0,
      "hitsCount": 0,
      "text": "string",
      "updatedAt": "string",
      "filename": "string"
    }
  ]
}
```

<h3 id="v1chatbottextnodeslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedChatbotTextNodeList](#schemapaginatedchatbottextnodelist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsFilesList

<a id="opIdv1ChatbotsFilesList"></a>

`GET /api/v1/chatbots/{chatbotPk}/files/`

<h3 id="v1chatbotsfileslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "filename": "string",
      "file": "http://example.com",
      "fileType": "string",
      "size": 0,
      "status": "initial",
      "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
      "parser": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "provider": "maiagent",
        "priority": 0
      },
      "createdAt": "string"
    }
  ]
}
```

<h3 id="v1chatbotsfileslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedChatbotFileList](#schemapaginatedchatbotfilelist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsFilesCreate

<a id="opIdv1ChatbotsFilesCreate"></a>

`POST /api/v1/chatbots/{chatbotPk}/files/`

> Body parameter

```json
{
  "files": [
    {
      "filename": "string",
      "file": "http://example.com",
      "parser": "87c5228b-83f7-4c51-ab10-39b9269cb177"
    }
  ]
}
```

<h3 id="v1chatbotsfilescreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|body|body|[ChatbotFileCreateFiles](#schemachatbotfilecreatefiles)|true|none|

> Example responses

> 201 Response

```json
{
  "files": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "filename": "string",
      "file": "http://example.com",
      "fileType": "string",
      "size": 0,
      "status": "initial",
      "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
      "parser": "87c5228b-83f7-4c51-ab10-39b9269cb177",
      "createdAt": "string"
    }
  ]
}
```

<h3 id="v1chatbotsfilescreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[ChatbotFileCreateFiles](#schemachatbotfilecreatefiles)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsFilesRetrieve

<a id="opIdv1ChatbotsFilesRetrieve"></a>

`GET /api/v1/chatbots/{chatbotPk}/files/{id}/`

<h3 id="v1chatbotsfilesretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "filename": "string",
  "file": "http://example.com",
  "fileType": "string",
  "size": 0,
  "status": "initial",
  "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
  "parser": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "provider": "maiagent",
    "priority": 0
  },
  "createdAt": "string"
}
```

<h3 id="v1chatbotsfilesretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFile](#schemachatbotfile)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsFilesUpdate

<a id="opIdv1ChatbotsFilesUpdate"></a>

`PUT /api/v1/chatbots/{chatbotPk}/files/{id}/`

> Body parameter

```json
{
  "filename": "string",
  "file": "http://example.com",
  "parser": "87c5228b-83f7-4c51-ab10-39b9269cb177"
}
```

<h3 id="v1chatbotsfilesupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案.|
|body|body|[ChatbotFileCreate](#schemachatbotfilecreate)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "filename": "string",
  "file": "http://example.com",
  "fileType": "string",
  "size": 0,
  "status": "initial",
  "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
  "parser": "87c5228b-83f7-4c51-ab10-39b9269cb177",
  "createdAt": "string"
}
```

<h3 id="v1chatbotsfilesupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFileCreate](#schemachatbotfilecreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsFilesPartialUpdate

<a id="opIdv1ChatbotsFilesPartialUpdate"></a>

`PATCH /api/v1/chatbots/{chatbotPk}/files/{id}/`

> Body parameter

```json
{
  "filename": "string",
  "file": "http://example.com",
  "parser": {
    "name": "string",
    "provider": "maiagent"
  }
}
```

<h3 id="v1chatbotsfilespartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案.|
|body|body|[PatchedChatbotFile](#schemapatchedchatbotfile)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "filename": "string",
  "file": "http://example.com",
  "fileType": "string",
  "size": 0,
  "status": "initial",
  "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
  "parser": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "provider": "maiagent",
    "priority": 0
  },
  "createdAt": "string"
}
```

<h3 id="v1chatbotsfilespartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFile](#schemachatbotfile)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsFilesDestroy

<a id="opIdv1ChatbotsFilesDestroy"></a>

`DELETE /api/v1/chatbots/{chatbotPk}/files/{id}/`

<h3 id="v1chatbotsfilesdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案.|

<h3 id="v1chatbotsfilesdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsFilesLatestFailedReasonRetrieve

<a id="opIdv1ChatbotsFilesLatestFailedReasonRetrieve"></a>

`GET /api/v1/chatbots/{chatbotPk}/files/{id}/latest-failed-reason/`

獲取指定 Chatbot 檔案的最新失敗原因。

<h3 id="v1chatbotsfileslatestfailedreasonretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this Chatbot 檔案.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "filename": "string",
  "file": "http://example.com",
  "fileType": "string",
  "size": 0,
  "status": "initial",
  "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
  "parser": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "provider": "maiagent",
    "priority": 0
  },
  "createdAt": "string"
}
```

<h3 id="v1chatbotsfileslatestfailedreasonretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFile](#schemachatbotfile)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsFilesBatchDeleteCreate

<a id="opIdv1ChatbotsFilesBatchDeleteCreate"></a>

`POST /api/v1/chatbots/{chatbotPk}/files/batch-delete/`

批次刪除多個指定的 chatbot file

payload:
{
    "ids": ["file_id_1", "file_id_2", "file_id_3"]
}

> Body parameter

```json
{
  "filename": "string",
  "file": "http://example.com",
  "parser": {
    "name": "string",
    "provider": "maiagent"
  }
}
```

<h3 id="v1chatbotsfilesbatchdeletecreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|body|body|[ChatbotFile](#schemachatbotfile)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "filename": "string",
  "file": "http://example.com",
  "fileType": "string",
  "size": 0,
  "status": "initial",
  "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
  "parser": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "provider": "maiagent",
    "priority": 0
  },
  "createdAt": "string"
}
```

<h3 id="v1chatbotsfilesbatchdeletecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ChatbotFile](#schemachatbotfile)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsLlmUsageStatisticsRetrieve

<a id="opIdv1ChatbotsLlmUsageStatisticsRetrieve"></a>

`GET /api/v1/chatbots/{chatbotPk}/llm-usage-statistics/`

統一的列表視圖，根據請求參數返回不同的數據：

time_granularity=day/month：返回指定時間區間的每日/每月統計
- start_date
- end_date

<h3 id="v1chatbotsllmusagestatisticsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string|true|none|

<h3 id="v1chatbotsllmusagestatisticsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsStatisticsRetrieve

<a id="opIdv1ChatbotsStatisticsRetrieve"></a>

`GET /api/v1/chatbots/{chatbotPk}/statistics/`

<h3 id="v1chatbotsstatisticsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string|true|none|

<h3 id="v1chatbotsstatisticsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ChatbotsUsageStatisticsList

<a id="opIdv1ChatbotsUsageStatisticsList"></a>

`GET /api/v1/chatbots/{chatbotPk}/usage-statistics/`

<h3 id="v1chatbotsusagestatisticslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chatbotPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "chatbotId": "964783cd-c648-4628-8262-55dac3831d8f",
      "uploadedFilesSizeTotal": -2147483648,
      "conversationsCount": -2147483648
    }
  ]
}
```

<h3 id="v1chatbotsusagestatisticslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedChatbotUsageStatisticList](#schemapaginatedchatbotusagestatisticlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ConversationsAttachmentsCreate

<a id="opIdv1ConversationsAttachmentsCreate"></a>

`POST /api/v1/conversations/{conversationPk}/attachments/`

> Body parameter

```json
{
  "type": "other",
  "filename": "string",
  "file": "http://example.com",
  "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa"
}
```

<h3 id="v1conversationsattachmentscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|conversationPk|path|string|true|none|
|body|body|[AttachmentCreateInput](#schemaattachmentcreateinput)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}
```

<h3 id="v1conversationsattachmentscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[AttachmentCreateInput](#schemaattachmentcreateinput)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1DatabaseExamplesList

<a id="opIdv1DatabaseExamplesList"></a>

`GET /api/v1/database-examples/`

提供資料庫連線字串範例的 API

> Example responses

> 200 Response

```json
[
  {
    "databaseType": "postgresql",
    "databaseTypeExample": "string",
    "isActive": true
  }
]
```

<h3 id="v1databaseexampleslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="v1databaseexampleslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[DatabaseExample](#schemadatabaseexample)]|false|none|none|
|» databaseType|[DatabaseTypeEnum](#schemadatabasetypeenum)|false|none|資料庫類型選項<br><br>* `postgresql` - PostgreSQL<br>* `mysql` - MySQL|
|» databaseTypeExample|string|true|none|例如：postgresql://db_user:db_password@db_ip:dp_port/db_name|
|» isActive|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|databaseType|postgresql|
|databaseType|mysql|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1DatabaseExamplesRetrieve

<a id="opIdv1DatabaseExamplesRetrieve"></a>

`GET /api/v1/database-examples/{id}/`

提供資料庫連線字串範例的 API

<h3 id="v1databaseexamplesretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 資料庫連線範例.|

> Example responses

> 200 Response

```json
{
  "databaseType": "postgresql",
  "databaseTypeExample": "string",
  "isActive": true
}
```

<h3 id="v1databaseexamplesretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[DatabaseExample](#schemadatabaseexample)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsList

<a id="opIdv1OrganizationsList"></a>

`GET /api/v1/organizations/`

<h3 id="v1organizationslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "owner": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string"
      },
      "createdAt": "string"
    }
  ]
}
```

<h3 id="v1organizationslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedOrganizationListList](#schemapaginatedorganizationlistlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsCreate

<a id="opIdv1OrganizationsCreate"></a>

`POST /api/v1/organizations/`

> Body parameter

```json
{
  "name": "string"
}
```

<h3 id="v1organizationscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Organization](#schemaorganization)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "owner": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string"
  },
  "createdAt": "string",
  "usageStatistics": "string",
  "organizationPlan": "string"
}
```

<h3 id="v1organizationscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Organization](#schemaorganization)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsGroupsList

<a id="opIdv1OrganizationsGroupsList"></a>

`GET /api/v1/organizations/{organizationPk}/groups/`

<h3 id="v1organizationsgroupslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|organizationPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "permissions": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "description": "string"
        }
      ],
      "createdAt": "string"
    }
  ]
}
```

<h3 id="v1organizationsgroupslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedGroupList](#schemapaginatedgrouplist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsGroupsCreate

<a id="opIdv1OrganizationsGroupsCreate"></a>

`POST /api/v1/organizations/{organizationPk}/groups/`

> Body parameter

```json
{
  "name": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "permissions": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ]
}
```

<h3 id="v1organizationsgroupscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|organizationPk|path|string(uuid)|true|none|
|body|body|[GroupCreate](#schemagroupcreate)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "permissions": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ],
  "createdAt": "string"
}
```

<h3 id="v1organizationsgroupscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[GroupCreate](#schemagroupcreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsGroupsGroupChatbotsList

<a id="opIdv1OrganizationsGroupsGroupChatbotsList"></a>

`GET /api/v1/organizations/{organizationPk}/groups/{groupPk}/group-chatbots/`

<h3 id="v1organizationsgroupsgroupchatbotslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|organizationPk|path|string|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "group": "fbd899a6-8a66-4f51-a95d-68668de198ae",
      "chatbot": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
        "name": "string",
        "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
        "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
        "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
        "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
        "instructions": "string",
        "webhookUrl": "http://example.com",
        "apiWebChatId": "string",
        "updatedAt": "string",
        "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
        "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
        "replyMode": "normal",
        "template": "string",
        "unanswerableTemplate": "string",
        "totalWordsCount": -9223372036854776000,
        "enableChineseConversion": true,
        "outputFormat": null,
        "databaseUrl": "string",
        "databaseType": "string"
      },
      "createdAt": "string"
    }
  ]
}
```

<h3 id="v1organizationsgroupsgroupchatbotslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedGroupChatbotList](#schemapaginatedgroupchatbotlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsGroupsGroupChatbotsCreate

<a id="opIdv1OrganizationsGroupsGroupChatbotsCreate"></a>

`POST /api/v1/organizations/{organizationPk}/groups/{groupPk}/group-chatbots/`

> Body parameter

```json
{
  "group": "fbd899a6-8a66-4f51-a95d-68668de198ae",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133"
}
```

<h3 id="v1organizationsgroupsgroupchatbotscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|organizationPk|path|string|true|none|
|body|body|[GroupChatbotCreate](#schemagroupchatbotcreate)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "group": "fbd899a6-8a66-4f51-a95d-68668de198ae",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "createdAt": "string"
}
```

<h3 id="v1organizationsgroupsgroupchatbotscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[GroupChatbotCreate](#schemagroupchatbotcreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsGroupsGroupChatbotsDestroy

<a id="opIdv1OrganizationsGroupsGroupChatbotsDestroy"></a>

`DELETE /api/v1/organizations/{organizationPk}/groups/{groupPk}/group-chatbots/{id}/`

<h3 id="v1organizationsgroupsgroupchatbotsdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this 群組 AI 助理.|
|organizationPk|path|string|true|none|

<h3 id="v1organizationsgroupsgroupchatbotsdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsGroupsGroupChatbotsBulkCreateCreate

<a id="opIdv1OrganizationsGroupsGroupChatbotsBulkCreateCreate"></a>

`POST /api/v1/organizations/{organizationPk}/groups/{groupPk}/group-chatbots/bulk-create/`

<h3 id="v1organizationsgroupsgroupchatbotsbulkcreatecreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|organizationPk|path|string|true|none|

<h3 id="v1organizationsgroupsgroupchatbotsbulkcreatecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsGroupsGroupMembersList

<a id="opIdv1OrganizationsGroupsGroupMembersList"></a>

`GET /api/v1/organizations/{organizationPk}/groups/{groupPk}/group-members/`

<h3 id="v1organizationsgroupsgroupmemberslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|organizationPk|path|string|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "member": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "email": "string",
        "organization": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "owner": {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "name": "string"
          },
          "createdAt": "string",
          "usageStatistics": "string",
          "organizationPlan": "string"
        },
        "isOwner": "string",
        "permissions": "string",
        "createdAt": "string"
      },
      "createdAt": "string"
    }
  ]
}
```

<h3 id="v1organizationsgroupsgroupmemberslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedGroupMemberList](#schemapaginatedgroupmemberlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsGroupsGroupMembersCreate

<a id="opIdv1OrganizationsGroupsGroupMembersCreate"></a>

`POST /api/v1/organizations/{organizationPk}/groups/{groupPk}/group-members/`

> Body parameter

```json
{
  "group": "fbd899a6-8a66-4f51-a95d-68668de198ae",
  "member": "98a5fc57-9089-44da-9515-4171e2d1c593"
}
```

<h3 id="v1organizationsgroupsgroupmemberscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|organizationPk|path|string|true|none|
|body|body|[GroupMemberCreate](#schemagroupmembercreate)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "group": "fbd899a6-8a66-4f51-a95d-68668de198ae",
  "member": "98a5fc57-9089-44da-9515-4171e2d1c593",
  "createdAt": "string"
}
```

<h3 id="v1organizationsgroupsgroupmemberscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[GroupMemberCreate](#schemagroupmembercreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsGroupsGroupMembersRetrieve

<a id="opIdv1OrganizationsGroupsGroupMembersRetrieve"></a>

`GET /api/v1/organizations/{organizationPk}/groups/{groupPk}/group-members/{id}/`

<h3 id="v1organizationsgroupsgroupmembersretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this 群組成員.|
|organizationPk|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "member": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "email": "string",
    "organization": {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "owner": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string"
      },
      "createdAt": "string",
      "usageStatistics": "string",
      "organizationPlan": "string"
    },
    "isOwner": "string",
    "permissions": "string",
    "createdAt": "string"
  },
  "createdAt": "string"
}
```

<h3 id="v1organizationsgroupsgroupmembersretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[GroupMember](#schemagroupmember)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsGroupsGroupMembersDestroy

<a id="opIdv1OrganizationsGroupsGroupMembersDestroy"></a>

`DELETE /api/v1/organizations/{organizationPk}/groups/{groupPk}/group-members/{id}/`

<h3 id="v1organizationsgroupsgroupmembersdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|id|path|string(uuid)|true|A UUID string identifying this 群組成員.|
|organizationPk|path|string|true|none|

<h3 id="v1organizationsgroupsgroupmembersdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsGroupsGroupMembersBulkCreateCreate

<a id="opIdv1OrganizationsGroupsGroupMembersBulkCreateCreate"></a>

`POST /api/v1/organizations/{organizationPk}/groups/{groupPk}/group-members/bulk-create/`

<h3 id="v1organizationsgroupsgroupmembersbulkcreatecreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|groupPk|path|string(uuid)|true|none|
|organizationPk|path|string|true|none|

<h3 id="v1organizationsgroupsgroupmembersbulkcreatecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsGroupsRetrieve

<a id="opIdv1OrganizationsGroupsRetrieve"></a>

`GET /api/v1/organizations/{organizationPk}/groups/{id}/`

<h3 id="v1organizationsgroupsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 群組.|
|organizationPk|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "permissions": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "description": "string"
    }
  ],
  "createdAt": "string"
}
```

<h3 id="v1organizationsgroupsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Group](#schemagroup)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsGroupsUpdate

<a id="opIdv1OrganizationsGroupsUpdate"></a>

`PUT /api/v1/organizations/{organizationPk}/groups/{id}/`

> Body parameter

```json
{
  "name": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "permissions": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ]
}
```

<h3 id="v1organizationsgroupsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 群組.|
|organizationPk|path|string(uuid)|true|none|
|body|body|[GroupCreate](#schemagroupcreate)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "permissions": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ],
  "createdAt": "string"
}
```

<h3 id="v1organizationsgroupsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[GroupCreate](#schemagroupcreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsGroupsPartialUpdate

<a id="opIdv1OrganizationsGroupsPartialUpdate"></a>

`PATCH /api/v1/organizations/{organizationPk}/groups/{id}/`

> Body parameter

```json
{
  "name": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "permissions": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ]
}
```

<h3 id="v1organizationsgroupspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 群組.|
|organizationPk|path|string(uuid)|true|none|
|body|body|[PatchedGroupCreate](#schemapatchedgroupcreate)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "permissions": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ],
  "createdAt": "string"
}
```

<h3 id="v1organizationsgroupspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[GroupCreate](#schemagroupcreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsGroupsDestroy

<a id="opIdv1OrganizationsGroupsDestroy"></a>

`DELETE /api/v1/organizations/{organizationPk}/groups/{id}/`

<h3 id="v1organizationsgroupsdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 群組.|
|organizationPk|path|string(uuid)|true|none|

<h3 id="v1organizationsgroupsdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsMembersList

<a id="opIdv1OrganizationsMembersList"></a>

`GET /api/v1/organizations/{organizationPk}/members/`

<h3 id="v1organizationsmemberslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|organizationPk|path|string(uuid)|true|none|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "email": "string",
      "organization": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "owner": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string"
        },
        "createdAt": "string",
        "usageStatistics": "string",
        "organizationPlan": "string"
      },
      "isOwner": "string",
      "permissions": "string",
      "createdAt": "string"
    }
  ]
}
```

<h3 id="v1organizationsmemberslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedMemberList](#schemapaginatedmemberlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsMembersCreate

<a id="opIdv1OrganizationsMembersCreate"></a>

`POST /api/v1/organizations/{organizationPk}/members/`

> Body parameter

```json
{
  "email": "user@example.com",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387"
}
```

<h3 id="v1organizationsmemberscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|organizationPk|path|string(uuid)|true|none|
|body|body|[MemberCreate](#schemamembercreate)|true|none|

> Example responses

> 201 Response

```json
{
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "isOwner": "string"
}
```

<h3 id="v1organizationsmemberscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[MemberCreate](#schemamembercreate)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsMembersRetrieve

<a id="opIdv1OrganizationsMembersRetrieve"></a>

`GET /api/v1/organizations/{organizationPk}/members/{id}/`

<h3 id="v1organizationsmembersretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 成員.|
|organizationPk|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "email": "string",
  "organization": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "owner": {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string"
    },
    "createdAt": "string",
    "usageStatistics": "string",
    "organizationPlan": "string"
  },
  "isOwner": "string",
  "permissions": "string",
  "createdAt": "string"
}
```

<h3 id="v1organizationsmembersretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Member](#schemamember)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsMembersDestroy

<a id="opIdv1OrganizationsMembersDestroy"></a>

`DELETE /api/v1/organizations/{organizationPk}/members/{id}/`

<h3 id="v1organizationsmembersdestroy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 成員.|
|organizationPk|path|string(uuid)|true|none|

<h3 id="v1organizationsmembersdestroy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsRetrieve

<a id="opIdv1OrganizationsRetrieve"></a>

`GET /api/v1/organizations/{id}/`

<h3 id="v1organizationsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 組織.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "owner": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string"
  },
  "createdAt": "string",
  "usageStatistics": "string",
  "organizationPlan": "string"
}
```

<h3 id="v1organizationsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Organization](#schemaorganization)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsUpdate

<a id="opIdv1OrganizationsUpdate"></a>

`PUT /api/v1/organizations/{id}/`

> Body parameter

```json
{
  "name": "string"
}
```

<h3 id="v1organizationsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 組織.|
|body|body|[Organization](#schemaorganization)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "owner": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string"
  },
  "createdAt": "string",
  "usageStatistics": "string",
  "organizationPlan": "string"
}
```

<h3 id="v1organizationsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Organization](#schemaorganization)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1OrganizationsPartialUpdate

<a id="opIdv1OrganizationsPartialUpdate"></a>

`PATCH /api/v1/organizations/{id}/`

> Body parameter

```json
{
  "name": "string"
}
```

<h3 id="v1organizationspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 組織.|
|body|body|[PatchedOrganization](#schemapatchedorganization)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "owner": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string"
  },
  "createdAt": "string",
  "usageStatistics": "string",
  "organizationPlan": "string"
}
```

<h3 id="v1organizationspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Organization](#schemaorganization)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1PermissionsList

<a id="opIdv1PermissionsList"></a>

`GET /api/v1/permissions/`

<h3 id="v1permissionslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "description": "string"
    }
  ]
}
```

<h3 id="v1permissionslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedPermissionList](#schemapaginatedpermissionlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1ProjectsQuietTrackingRecordsList

<a id="opIdv1ProjectsQuietTrackingRecordsList"></a>

`GET /api/v1/projects/quiet-tracking-records/`

<h3 id="v1projectsquiettrackingrecordslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|deviceId|query|string|false|none|

> Example responses

> 200 Response

```json
[
  {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "deviceId": "string",
    "metadata": null,
    "createdAt": "string"
  }
]
```

<h3 id="v1projectsquiettrackingrecordslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="v1projectsquiettrackingrecordslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[QuietTrackingRecord](#schemaquiettrackingrecord)]|false|none|none|
|» id|string(uuid)|true|read-only|none|
|» deviceId|string|true|none|none|
|» metadata|any|false|none|none|
|» createdAt|string(timestamp)|true|read-only|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1ProjectsQuietTrackingRecordsCreate

<a id="opIdv1ProjectsQuietTrackingRecordsCreate"></a>

`POST /api/v1/projects/quiet-tracking-records/`

> Body parameter

```json
{
  "deviceId": "string",
  "metadata": null
}
```

<h3 id="v1projectsquiettrackingrecordscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[QuietTrackingRecord](#schemaquiettrackingrecord)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "deviceId": "string",
  "metadata": null,
  "createdAt": "string"
}
```

<h3 id="v1projectsquiettrackingrecordscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[QuietTrackingRecord](#schemaquiettrackingrecord)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1RebuildWebChatPagesCreate

<a id="opIdv1RebuildWebChatPagesCreate"></a>

`POST /api/v1/rebuild-web-chat-pages/`

<h3 id="v1rebuildwebchatpagescreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1SchemaRetrieve

<a id="opIdv1SchemaRetrieve"></a>

`GET /api/v1/schema/`

OpenApi3 schema for this API. Format can be selected via content negotiation.

- YAML: application/vnd.oai.openapi
- JSON: application/vnd.oai.openapi+json

<h3 id="v1schemaretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|format|query|string|false|none|
|lang|query|string|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|format|json|
|format|yaml|
|lang|af|
|lang|ar|
|lang|ar-dz|
|lang|ast|
|lang|az|
|lang|be|
|lang|bg|
|lang|bn|
|lang|br|
|lang|bs|
|lang|ca|
|lang|ckb|
|lang|cs|
|lang|cy|
|lang|da|
|lang|de|
|lang|dsb|
|lang|el|
|lang|en|
|lang|en-au|
|lang|en-gb|
|lang|eo|
|lang|es|
|lang|es-ar|
|lang|es-co|
|lang|es-mx|
|lang|es-ni|
|lang|es-ve|
|lang|et|
|lang|eu|
|lang|fa|
|lang|fi|
|lang|fr|
|lang|fy|
|lang|ga|
|lang|gd|
|lang|gl|
|lang|he|
|lang|hi|
|lang|hr|
|lang|hsb|
|lang|hu|
|lang|hy|
|lang|ia|
|lang|id|
|lang|ig|
|lang|io|
|lang|is|
|lang|it|
|lang|ja|
|lang|ka|
|lang|kab|
|lang|kk|
|lang|km|
|lang|kn|
|lang|ko|
|lang|ky|
|lang|lb|
|lang|lt|
|lang|lv|
|lang|mk|
|lang|ml|
|lang|mn|
|lang|mr|
|lang|ms|
|lang|my|
|lang|nb|
|lang|ne|
|lang|nl|
|lang|nn|
|lang|os|
|lang|pa|
|lang|pl|
|lang|pt|
|lang|pt-br|
|lang|ro|
|lang|ru|
|lang|sk|
|lang|sl|
|lang|sq|
|lang|sr|
|lang|sr-latn|
|lang|sv|
|lang|sw|
|lang|ta|
|lang|te|
|lang|tg|
|lang|th|
|lang|tk|
|lang|tr|
|lang|tt|
|lang|udm|
|lang|ug|
|lang|uk|
|lang|ur|
|lang|uz|
|lang|vi|
|lang|zh-hans|
|lang|zh-hant|

> Example responses

> 200 Response

```json
{
  "property1": null,
  "property2": null
}
```

<h3 id="v1schemaretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="v1schemaretrieve-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» **additionalProperties**|any|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1UploadPresignedUrlCreate

<a id="opIdv1UploadPresignedUrlCreate"></a>

`POST /api/v1/upload-presigned-url/`

> Body parameter

```json
{
  "modelName": "string",
  "fieldName": "string",
  "filename": "string",
  "fileSize": 0
}
```

<h3 id="v1uploadpresignedurlcreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UploadPresignedUrl](#schemauploadpresignedurl)|true|none|

> Example responses

> 200 Response

```json
{
  "modelName": "string",
  "fieldName": "string",
  "filename": "string",
  "fileSize": 0
}
```

<h3 id="v1uploadpresignedurlcreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[UploadPresignedUrl](#schemauploadpresignedurl)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1UsersList

<a id="opIdv1UsersList"></a>

`GET /api/v1/users/`

<h3 id="v1userslist-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|A page number within the paginated result set.|
|pageSize|query|integer|false|Number of results to return per page.|

> Example responses

> 200 Response

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "avatar": "http://example.com",
      "name": "string",
      "email": "user@example.com",
      "company": "string",
      "invitationCode": "string",
      "apiKeys": "string",
      "permissions": "string"
    }
  ]
}
```

<h3 id="v1userslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PaginatedUserList](#schemapaginateduserlist)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1UsersRetrieve

<a id="opIdv1UsersRetrieve"></a>

`GET /api/v1/users/{id}/`

<h3 id="v1usersretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 使用者.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="v1usersretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1UsersUpdate

<a id="opIdv1UsersUpdate"></a>

`PUT /api/v1/users/{id}/`

> Body parameter

```json
{
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string"
}
```

<h3 id="v1usersupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 使用者.|
|body|body|[User](#schemauser)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="v1usersupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1UsersPartialUpdate

<a id="opIdv1UsersPartialUpdate"></a>

`PATCH /api/v1/users/{id}/`

> Body parameter

```json
{
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string"
}
```

<h3 id="v1userspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 使用者.|
|body|body|[PatchedUser](#schemapatcheduser)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="v1userspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1UsersCurrentRetrieve

<a id="opIdv1UsersCurrentRetrieve"></a>

`GET /api/v1/users/current/`

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="v1userscurrentretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1UsersCurrentUpdate

<a id="opIdv1UsersCurrentUpdate"></a>

`PUT /api/v1/users/current/`

> Body parameter

```json
{
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string"
}
```

<h3 id="v1userscurrentupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[User](#schemauser)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="v1userscurrentupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1UsersCurrentPartialUpdate

<a id="opIdv1UsersCurrentPartialUpdate"></a>

`PATCH /api/v1/users/current/`

> Body parameter

```json
{
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string"
}
```

<h3 id="v1userscurrentpartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PatchedUser](#schemapatcheduser)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
}
```

<h3 id="v1userscurrentpartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="maiagent-api-webhooks">Webhooks</h1>

## v1WebhooksLineCreate

<a id="opIdv1WebhooksLineCreate"></a>

`POST /api/v1/webhooks/line/{lineChannelId}/`

<h3 id="v1webhookslinecreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|lineChannelId|path|string|true|none|

<h3 id="v1webhookslinecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1WebhooksMessengerRetrieve

<a id="opIdv1WebhooksMessengerRetrieve"></a>

`GET /api/v1/webhooks/messenger/`

<h3 id="v1webhooksmessengerretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hub.challenge|query|string|false|none|
|hub.mode|query|string|false|none|
|hub.verifyToken|query|string|false|none|

<h3 id="v1webhooksmessengerretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## v1WebhooksMessengerCreate

<a id="opIdv1WebhooksMessengerCreate"></a>

`POST /api/v1/webhooks/messenger/`

<h3 id="v1webhooksmessengercreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## webhooksLineCreate

<a id="opIdwebhooksLineCreate"></a>

`POST /api/webhooks/line/{lineChannelId}/`

<h3 id="webhookslinecreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|lineChannelId|path|string|true|none|

<h3 id="webhookslinecreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## webhooksMessengerRetrieve

<a id="opIdwebhooksMessengerRetrieve"></a>

`GET /api/webhooks/messenger/`

<h3 id="webhooksmessengerretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hub.challenge|query|string|false|none|
|hub.mode|query|string|false|none|
|hub.verifyToken|query|string|false|none|

<h3 id="webhooksmessengerretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## webhooksMessengerCreate

<a id="opIdwebhooksMessengerCreate"></a>

`POST /api/webhooks/messenger/`

<h3 id="webhooksmessengercreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|No response body|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

<h1 id="maiagent-api-workflows">Workflows</h1>

## v1WorkflowsCreate

<a id="opIdv1WorkflowsCreate"></a>

`POST /api/v1/workflows/`

> Body parameter

```json
{
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
}
```

<h3 id="v1workflowscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Workflow](#schemaworkflow)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
}
```

<h3 id="v1workflowscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Workflow](#schemaworkflow)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1WorkflowsRetrieve

<a id="opIdv1WorkflowsRetrieve"></a>

`GET /api/v1/workflows/{id}/`

<h3 id="v1workflowsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 工作流.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
}
```

<h3 id="v1workflowsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Workflow](#schemaworkflow)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1WorkflowsUpdate

<a id="opIdv1WorkflowsUpdate"></a>

`PUT /api/v1/workflows/{id}/`

> Body parameter

```json
{
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
}
```

<h3 id="v1workflowsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 工作流.|
|body|body|[Workflow](#schemaworkflow)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
}
```

<h3 id="v1workflowsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Workflow](#schemaworkflow)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## v1WorkflowsPartialUpdate

<a id="opIdv1WorkflowsPartialUpdate"></a>

`PATCH /api/v1/workflows/{id}/`

> Body parameter

```json
{
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
}
```

<h3 id="v1workflowspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 工作流.|
|body|body|[PatchedWorkflow](#schemapatchedworkflow)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
}
```

<h3 id="v1workflowspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Workflow](#schemaworkflow)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## workflowsCreate

<a id="opIdworkflowsCreate"></a>

`POST /api/workflows/`

> Body parameter

```json
{
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
}
```

<h3 id="workflowscreate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Workflow](#schemaworkflow)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
}
```

<h3 id="workflowscreate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Workflow](#schemaworkflow)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## workflowsRetrieve

<a id="opIdworkflowsRetrieve"></a>

`GET /api/workflows/{id}/`

<h3 id="workflowsretrieve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 工作流.|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
}
```

<h3 id="workflowsretrieve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Workflow](#schemaworkflow)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## workflowsUpdate

<a id="opIdworkflowsUpdate"></a>

`PUT /api/workflows/{id}/`

> Body parameter

```json
{
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
}
```

<h3 id="workflowsupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 工作流.|
|body|body|[Workflow](#schemaworkflow)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
}
```

<h3 id="workflowsupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Workflow](#schemaworkflow)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## workflowsPartialUpdate

<a id="opIdworkflowsPartialUpdate"></a>

`PATCH /api/workflows/{id}/`

> Body parameter

```json
{
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
}
```

<h3 id="workflowspartialupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|A UUID string identifying this 工作流.|
|body|body|[PatchedWorkflow](#schemapatchedworkflow)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
}
```

<h3 id="workflowspartialupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Workflow](#schemaworkflow)|

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
"web"

```

* `web` - Web Chat
* `admin` - Admin 問答
* `api` - API

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|* `web` - Web Chat<br>* `admin` - Admin 問答<br>* `api` - API|

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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|type|[TypeEnum](#schematypeenum)|false|none|* `image` - Image<br>* `video` - Video<br>* `audio` - Audio<br>* `sticker` - Sticker<br>* `other` - Other|
|filename|string|true|none|none|
|file|string(uri)|true|none|none|

<h2 id="tocS_AttachmentCreateInput">AttachmentCreateInput</h2>
<!-- backwards compatibility -->
<a id="schemaattachmentcreateinput"></a>
<a id="schema_AttachmentCreateInput"></a>
<a id="tocSattachmentcreateinput"></a>
<a id="tocsattachmentcreateinput"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "type": "other",
  "filename": "string",
  "file": "http://example.com",
  "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa"
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

<h2 id="tocS_AuthToken">AuthToken</h2>
<!-- backwards compatibility -->
<a id="schemaauthtoken"></a>
<a id="schema_AuthToken"></a>
<a id="tocSauthtoken"></a>
<a id="tocsauthtoken"></a>

```json
{
  "username": "string",
  "password": "string",
  "token": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "weekday": 0,
  "isEnabled": true,
  "timeSlots": [
    [
      "14:15:22Z"
    ]
  ],
  "weekdayName": "string"
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
""

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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string"
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
"line"

```

* `line` - LINE
* `telegram` - Telegram
* `web` - Web
* `messenger` - Messenger

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|* `line` - LINE<br>* `telegram` - Telegram<br>* `web` - Web<br>* `messenger` - Messenger|

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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
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
|replyMode|[ReplyModeEnum](#schemareplymodeenum)|false|none|* `normal` - 正常<br>* `template` - 模板<br>* `hybrid` - 混合<br>* `text_to_sql` - text to sql<br>* `workflow` - 工作流|
|template|string¦null|false|none|none|
|unanswerableTemplate|string¦null|false|none|none|
|totalWordsCount|integer(int64)|false|none|累積的使用總字數|
|enableChineseConversion|boolean|false|none|none|
|outputFormat|any|false|none|none|
|databaseUrl|string¦null|false|none|none|
|databaseType|string¦null|false|none|none|

<h2 id="tocS_ChatbotBatchQAFile">ChatbotBatchQAFile</h2>
<!-- backwards compatibility -->
<a id="schemachatbotbatchqafile"></a>
<a id="schema_ChatbotBatchQAFile"></a>
<a id="tocSchatbotbatchqafile"></a>
<a id="tocschatbotbatchqafile"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "file": "http://example.com",
  "createdAt": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "filename": "string",
  "file": "http://example.com",
  "fileType": "string",
  "size": 0,
  "status": "initial",
  "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
  "parser": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "provider": "maiagent",
    "priority": 0
  },
  "createdAt": "string"
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
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_ChatbotFileContent">ChatbotFileContent</h2>
<!-- backwards compatibility -->
<a id="schemachatbotfilecontent"></a>
<a id="schema_ChatbotFileContent"></a>
<a id="tocSchatbotfilecontent"></a>
<a id="tocschatbotfilecontent"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "content": "string",
  "modifiedContent": "string",
  "type": "string",
  "updatedAt": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "filename": "string",
  "file": "http://example.com",
  "fileType": "string",
  "size": 0,
  "status": "initial",
  "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
  "parser": "87c5228b-83f7-4c51-ab10-39b9269cb177",
  "createdAt": "string"
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

<h2 id="tocS_ChatbotFileCreateFiles">ChatbotFileCreateFiles</h2>
<!-- backwards compatibility -->
<a id="schemachatbotfilecreatefiles"></a>
<a id="schema_ChatbotFileCreateFiles"></a>
<a id="tocSchatbotfilecreatefiles"></a>
<a id="tocschatbotfilecreatefiles"></a>

```json
{
  "files": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "filename": "string",
      "file": "http://example.com",
      "fileType": "string",
      "size": 0,
      "status": "initial",
      "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
      "parser": "87c5228b-83f7-4c51-ab10-39b9269cb177",
      "createdAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|files|[[ChatbotFileCreate](#schemachatbotfilecreate)]|true|none|none|

<h2 id="tocS_ChatbotInstructionRecord">ChatbotInstructionRecord</h2>
<!-- backwards compatibility -->
<a id="schemachatbotinstructionrecord"></a>
<a id="schema_ChatbotInstructionRecord"></a>
<a id="tocSchatbotinstructionrecord"></a>
<a id="tocschatbotinstructionrecord"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "instructions": "string",
  "operatorName": "string",
  "createdAt": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "largeLanguageModel": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string"
  },
  "rag": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string"
  },
  "embeddingModel": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "isDefault": true
  },
  "rerankerModel": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "isDefault": true
  },
  "updatedAt": "string",
  "enableChineseConversion": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|largeLanguageModel|[LargeLanguageModel](#schemalargelanguagemodel)|true|none|none|
|rag|[Rag](#schemarag)|true|none|none|
|embeddingModel|[EmbeddingModel](#schemaembeddingmodel)|true|none|none|
|rerankerModel|[RerankerModel](#schemarerankermodel)|true|none|none|
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "inputMessage": "string",
  "condenseMessage": "string",
  "outputMessage": "string",
  "context": "string",
  "faithfulnessScore": 0.1,
  "displayFaithfulnessScore": "string",
  "answerRelevancyScore": 0.1,
  "displayAnswerRelevancyScore": "string",
  "contextPrecisionScore": 0.1,
  "displayContextPrecisionScore": "string",
  "answerCorrectnessScore": 0.1,
  "displayAnswerCorrectnessScore": "string",
  "answerSimilarityScore": 0.1,
  "displayAnswerSimilarityScore": "string",
  "contextRecallScore": 0.1,
  "displayContextRecallScore": "string",
  "replyTime": "string",
  "createdAt": "string",
  "error": "string"
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

<h2 id="tocS_ChatbotSetting">ChatbotSetting</h2>
<!-- backwards compatibility -->
<a id="schemachatbotsetting"></a>
<a id="schema_ChatbotSetting"></a>
<a id="tocSchatbotsetting"></a>
<a id="tocschatbotsetting"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "llms": "string",
  "isDefault": true,
  "isSearchSelectable": "string",
  "isWorkflowSelectable": "string",
  "isRerankerModelSelectable": "string",
  "isEmbeddingModelSelectable": "string"
}

```

用於返回以 RAG 為主的 chatbot 設定

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|llms|string|true|read-only|none|
|isDefault|boolean|false|none|none|
|isSearchSelectable|string|true|read-only|none|
|isWorkflowSelectable|string|true|read-only|none|
|isRerankerModelSelectable|string|true|read-only|none|
|isEmbeddingModelSelectable|string|true|read-only|none|

<h2 id="tocS_ChatbotTextNode">ChatbotTextNode</h2>
<!-- backwards compatibility -->
<a id="schemachatbottextnode"></a>
<a id="schema_ChatbotTextNode"></a>
<a id="tocSchatbottextnode"></a>
<a id="tocschatbottextnode"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "charactersCount": 0,
  "hitsCount": 0,
  "text": "string",
  "updatedAt": "string",
  "filename": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbotId": "964783cd-c648-4628-8262-55dac3831d8f",
  "uploadedFilesSizeTotal": -2147483648,
  "conversationsCount": -2147483648
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
  "chatbotTextNode": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "charactersCount": 0,
    "hitsCount": 0,
    "text": "string",
    "updatedAt": "string",
    "filename": "string"
  },
  "score": 0.1,
  "displayScore": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|chatbotTextNode|[ChatbotTextNode](#schemachatbottextnode)|true|none|none|
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "avatar": "http://example.com",
  "createdAt": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "contact": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "avatar": "http://example.com",
    "createdAt": "string"
  },
  "inbox": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "title": "string",
  "lastMessage": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "createdAt": "string",
    "attachments": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ],
    "citations": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "filename": "string",
        "file": "http://example.com",
        "fileType": "string",
        "size": 0,
        "status": "initial",
        "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
        "parser": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "provider": "maiagent",
          "priority": 0
        },
        "createdAt": "string"
      }
    ],
    "citationNodes": [
      {
        "chatbotTextNode": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "charactersCount": 0,
          "hitsCount": 0,
          "text": "string",
          "updatedAt": "string",
          "filename": "string"
        },
        "score": 0.1,
        "displayScore": "string"
      }
    ]
  },
  "lastMessageCreatedAt": "string",
  "unreadMessagesCount": 0,
  "autoReplyEnabled": true,
  "isAutoReplyNow": "string",
  "lastReadAt": "string",
  "createdAt": "string",
  "isGroupChat": "string",
  "enableGroupMention": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|contact|[Contact](#schemacontact)|true|none|none|
|inbox|[Inbox](#schemainbox)|true|none|none|
|title|string|true|read-only|none|
|lastMessage|[Message](#schemamessage)|false|none|none|
|lastMessageCreatedAt|string(timestamp)|true|read-only|none|
|unreadMessagesCount|integer|true|read-only|none|
|autoReplyEnabled|boolean|true|read-only|none|
|isAutoReplyNow|string|true|read-only|none|
|lastReadAt|string(timestamp)¦null|true|read-only|none|
|createdAt|string(timestamp)|true|read-only|none|
|isGroupChat|string|true|read-only|none|
|enableGroupMention|string|true|read-only|none|

<h2 id="tocS_CrawlPage">CrawlPage</h2>
<!-- backwards compatibility -->
<a id="schemacrawlpage"></a>
<a id="schema_CrawlPage"></a>
<a id="tocScrawlpage"></a>
<a id="tocscrawlpage"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "url": "http://example.com",
  "title": "string",
  "status": "pending",
  "isOriginalPage": true
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

<h2 id="tocS_CrawlPageRequest">CrawlPageRequest</h2>
<!-- backwards compatibility -->
<a id="schemacrawlpagerequest"></a>
<a id="schema_CrawlPageRequest"></a>
<a id="tocScrawlpagerequest"></a>
<a id="tocscrawlpagerequest"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "url": "http://example.com",
  "status": "processing",
  "createdAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|url|string(uri)|true|none|none|
|status|[Status235Enum](#schemastatus235enum)|false|none|* `processing` - Processing<br>* `done` - Done<br>* `cancelled` - Cancelled|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_CrawlPageRequestCreate">CrawlPageRequestCreate</h2>
<!-- backwards compatibility -->
<a id="schemacrawlpagerequestcreate"></a>
<a id="schema_CrawlPageRequestCreate"></a>
<a id="tocScrawlpagerequestcreate"></a>
<a id="tocscrawlpagerequestcreate"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "url": "http://example.com",
  "status": "processing"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|url|string(uri)|true|none|none|
|status|[Status235Enum](#schemastatus235enum)|false|none|* `processing` - Processing<br>* `done` - Done<br>* `cancelled` - Cancelled|

<h2 id="tocS_CrawlPageStatusEnum">CrawlPageStatusEnum</h2>
<!-- backwards compatibility -->
<a id="schemacrawlpagestatusenum"></a>
<a id="schema_CrawlPageStatusEnum"></a>
<a id="tocScrawlpagestatusenum"></a>
<a id="tocscrawlpagestatusenum"></a>

```json
"pending"

```

* `pending` - Pending
* `processing` - Processing
* `done` - Done
* `cancelled` - Cancelled

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|* `pending` - Pending<br>* `processing` - Processing<br>* `done` - Done<br>* `cancelled` - Cancelled|

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
  "username": "string",
  "email": "user@example.com",
  "password1": "string",
  "password2": "string",
  "name": "string",
  "company": "string",
  "referralCode": "string"
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

<h2 id="tocS_DatabaseExample">DatabaseExample</h2>
<!-- backwards compatibility -->
<a id="schemadatabaseexample"></a>
<a id="schema_DatabaseExample"></a>
<a id="tocSdatabaseexample"></a>
<a id="tocsdatabaseexample"></a>

```json
{
  "databaseType": "postgresql",
  "databaseTypeExample": "string",
  "isActive": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|databaseType|[DatabaseTypeEnum](#schemadatabasetypeenum)|false|none|資料庫類型選項<br><br>* `postgresql` - PostgreSQL<br>* `mysql` - MySQL|
|databaseTypeExample|string|true|none|例如：postgresql://db_user:db_password@db_ip:dp_port/db_name|
|isActive|boolean|false|none|none|

<h2 id="tocS_DatabaseTypeEnum">DatabaseTypeEnum</h2>
<!-- backwards compatibility -->
<a id="schemadatabasetypeenum"></a>
<a id="schema_DatabaseTypeEnum"></a>
<a id="tocSdatabasetypeenum"></a>
<a id="tocsdatabasetypeenum"></a>

```json
"postgresql"

```

* `postgresql` - PostgreSQL
* `mysql` - MySQL

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|* `postgresql` - PostgreSQL<br>* `mysql` - MySQL|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|postgresql|
|*anonymous*|mysql|

<h2 id="tocS_EmbeddingModel">EmbeddingModel</h2>
<!-- backwards compatibility -->
<a id="schemaembeddingmodel"></a>
<a id="schema_EmbeddingModel"></a>
<a id="tocSembeddingmodel"></a>
<a id="tocsembeddingmodel"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "isDefault": true
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
  "pageId": "string",
  "name": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "systemUserId": "string"
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
  "code": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "question": "string",
  "answer": "string",
  "hitsCount": 0
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "question": "string",
  "answer": "string"
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
"like"

```

* `like` - Like
* `dislike` - Dislike

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|* `like` - Like<br>* `dislike` - Dislike|

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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "permissions": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "description": "string"
    }
  ],
  "createdAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|permissions|[[Permission](#schemapermission)]|true|none|none|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_GroupChatbot">GroupChatbot</h2>
<!-- backwards compatibility -->
<a id="schemagroupchatbot"></a>
<a id="schema_GroupChatbot"></a>
<a id="tocSgroupchatbot"></a>
<a id="tocsgroupchatbot"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "group": "fbd899a6-8a66-4f51-a95d-68668de198ae",
  "chatbot": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
    "name": "string",
    "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
    "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
    "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
    "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
    "instructions": "string",
    "webhookUrl": "http://example.com",
    "apiWebChatId": "string",
    "updatedAt": "string",
    "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
    "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
    "replyMode": "normal",
    "template": "string",
    "unanswerableTemplate": "string",
    "totalWordsCount": -9223372036854776000,
    "enableChineseConversion": true,
    "outputFormat": null,
    "databaseUrl": "string",
    "databaseType": "string"
  },
  "createdAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|group|string(uuid)|true|none|none|
|chatbot|[Chatbot](#schemachatbot)|true|none|Adds nested create feature|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_GroupChatbotCreate">GroupChatbotCreate</h2>
<!-- backwards compatibility -->
<a id="schemagroupchatbotcreate"></a>
<a id="schema_GroupChatbotCreate"></a>
<a id="tocSgroupchatbotcreate"></a>
<a id="tocsgroupchatbotcreate"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "group": "fbd899a6-8a66-4f51-a95d-68668de198ae",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "createdAt": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "permissions": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ],
  "createdAt": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "member": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "email": "string",
    "organization": {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "owner": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string"
      },
      "createdAt": "string",
      "usageStatistics": "string",
      "organizationPlan": "string"
    },
    "isOwner": "string",
    "permissions": "string",
    "createdAt": "string"
  },
  "createdAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|member|[Member](#schemamember)|true|none|none|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_GroupMemberCreate">GroupMemberCreate</h2>
<!-- backwards compatibility -->
<a id="schemagroupmembercreate"></a>
<a id="schema_GroupMemberCreate"></a>
<a id="tocSgroupmembercreate"></a>
<a id="tocsgroupmembercreate"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "group": "fbd899a6-8a66-4f51-a95d-68668de198ae",
  "member": "98a5fc57-9089-44da-9515-4171e2d1c593",
  "createdAt": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "channelType": "line",
  "unreadConversationsCount": -2147483648
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|channelType|[ChannelTypeEnum](#schemachanneltypeenum)|true|none|* `line` - LINE<br>* `telegram` - Telegram<br>* `web` - Web<br>* `messenger` - Messenger|
|unreadConversationsCount|integer|false|none|none|

<h2 id="tocS_JWT">JWT</h2>
<!-- backwards compatibility -->
<a id="schemajwt"></a>
<a id="schema_JWT"></a>
<a id="tocSjwt"></a>
<a id="tocsjwt"></a>

```json
{
  "access": "string",
  "refresh": "string",
  "user": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "avatar": "http://example.com",
    "name": "string",
    "email": "user@example.com",
    "company": "string",
    "invitationCode": "string",
    "apiKeys": "string",
    "permissions": "string"
  }
}

```

Serializer for JWT authentication.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|access|string|true|none|none|
|refresh|string|true|none|none|
|user|[User](#schemauser)|true|none|none|

<h2 id="tocS_Keycloak">Keycloak</h2>
<!-- backwards compatibility -->
<a id="schemakeycloak"></a>
<a id="schema_Keycloak"></a>
<a id="tocSkeycloak"></a>
<a id="tocskeycloak"></a>

```json
{
  "serverUrl": "http://example.com",
  "realm": "string",
  "clientId": "string",
  "accessToken": "string",
  "refreshToken": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|serverUrl|string(uri)|true|none|none|
|realm|string|true|none|none|
|clientId|string|true|none|none|
|accessToken|string|true|none|none|
|refreshToken|string|true|none|none|

<h2 id="tocS_LargeLanguageModel">LargeLanguageModel</h2>
<!-- backwards compatibility -->
<a id="schemalargelanguagemodel"></a>
<a id="schema_LargeLanguageModel"></a>
<a id="tocSlargelanguagemodel"></a>
<a id="tocslargelanguagemodel"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|

<h2 id="tocS_LineChannel">LineChannel</h2>
<!-- backwards compatibility -->
<a id="schemalinechannel"></a>
<a id="schema_LineChannel"></a>
<a id="tocSlinechannel"></a>
<a id="tocslinechannel"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "webhookUrl": "string",
  "enableGroupMention": true
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
  "username": "string",
  "email": "user@example.com",
  "password": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "email": "string",
  "organization": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "owner": {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string"
    },
    "createdAt": "string",
    "usageStatistics": "string",
    "organizationPlan": "string"
  },
  "isOwner": "string",
  "permissions": "string",
  "createdAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|read-only|none|
|email|string|true|read-only|none|
|organization|[Organization](#schemaorganization)|true|none|none|
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
  "email": "user@example.com",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "isOwner": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
  "sender": {
    "id": 0,
    "name": "string",
    "avatar": "http://example.com"
  },
  "type": "incoming",
  "content": "string",
  "feedback": "like",
  "createdAt": "string",
  "attachments": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "type": "other",
      "filename": "string",
      "file": "http://example.com"
    }
  ],
  "citations": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "filename": "string",
      "file": "http://example.com",
      "fileType": "string",
      "size": 0,
      "status": "initial",
      "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
      "parser": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "provider": "maiagent",
        "priority": 0
      },
      "createdAt": "string"
    }
  ],
  "citationNodes": [
    {
      "chatbotTextNode": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "charactersCount": 0,
        "hitsCount": 0,
        "text": "string",
        "updatedAt": "string",
        "filename": "string"
      },
      "score": 0.1,
      "displayScore": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|conversation|string(uuid)|true|none|none|
|sender|[Sender](#schemasender)|false|none|none|
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
|» *anonymous*|[BlankEnum](#schemablankenum)|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[NullEnum](#schemanullenum)|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|createdAt|string(timestamp)|true|read-only|none|
|attachments|[[Attachment](#schemaattachment)]|false|none|none|
|citations|[[ChatbotFile](#schemachatbotfile)]|true|read-only|none|
|citationNodes|[[CitationNode](#schemacitationnode)]|true|read-only|none|

<h2 id="tocS_Messenger">Messenger</h2>
<!-- backwards compatibility -->
<a id="schemamessenger"></a>
<a id="schema_Messenger"></a>
<a id="tocSmessenger"></a>
<a id="tocsmessenger"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "pageId": "string",
  "pageName": "string",
  "facebookSystemUserId": "222f0e00-e37f-4fdd-9d33-56607d98cb2e"
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
null

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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "owner": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string"
  },
  "createdAt": "string",
  "usageStatistics": "string",
  "organizationPlan": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|owner|[UserBase](#schemauserbase)|true|read-only|none|
|createdAt|string(timestamp)|true|read-only|none|
|usageStatistics|string|true|read-only|none|
|organizationPlan|string|true|read-only|none|

<h2 id="tocS_OrganizationList">OrganizationList</h2>
<!-- backwards compatibility -->
<a id="schemaorganizationlist"></a>
<a id="schema_OrganizationList"></a>
<a id="tocSorganizationlist"></a>
<a id="tocsorganizationlist"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "owner": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string"
  },
  "createdAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|owner|[UserBase](#schemauserbase)|true|read-only|none|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_PaginatedAttachmentList">PaginatedAttachmentList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedattachmentlist"></a>
<a id="schema_PaginatedAttachmentList"></a>
<a id="tocSpaginatedattachmentlist"></a>
<a id="tocspaginatedattachmentlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "type": "other",
      "filename": "string",
      "file": "http://example.com"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Attachment](#schemaattachment)]|true|none|none|

<h2 id="tocS_PaginatedChatbotFileList">PaginatedChatbotFileList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedchatbotfilelist"></a>
<a id="schema_PaginatedChatbotFileList"></a>
<a id="tocSpaginatedchatbotfilelist"></a>
<a id="tocspaginatedchatbotfilelist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "filename": "string",
      "file": "http://example.com",
      "fileType": "string",
      "size": 0,
      "status": "initial",
      "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
      "parser": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "provider": "maiagent",
        "priority": 0
      },
      "createdAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[ChatbotFile](#schemachatbotfile)]|true|none|none|

<h2 id="tocS_PaginatedChatbotInstructionRecordList">PaginatedChatbotInstructionRecordList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedchatbotinstructionrecordlist"></a>
<a id="schema_PaginatedChatbotInstructionRecordList"></a>
<a id="tocSpaginatedchatbotinstructionrecordlist"></a>
<a id="tocspaginatedchatbotinstructionrecordlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "instructions": "string",
      "operatorName": "string",
      "createdAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[ChatbotInstructionRecord](#schemachatbotinstructionrecord)]|true|none|none|

<h2 id="tocS_PaginatedChatbotListList">PaginatedChatbotListList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedchatbotlistlist"></a>
<a id="schema_PaginatedChatbotListList"></a>
<a id="tocSpaginatedchatbotlistlist"></a>
<a id="tocspaginatedchatbotlistlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "largeLanguageModel": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string"
      },
      "rag": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string"
      },
      "embeddingModel": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "isDefault": true
      },
      "rerankerModel": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "isDefault": true
      },
      "updatedAt": "string",
      "enableChineseConversion": true
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[ChatbotList](#schemachatbotlist)]|true|none|none|

<h2 id="tocS_PaginatedChatbotRecordList">PaginatedChatbotRecordList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedchatbotrecordlist"></a>
<a id="schema_PaginatedChatbotRecordList"></a>
<a id="tocSpaginatedchatbotrecordlist"></a>
<a id="tocspaginatedchatbotrecordlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "inputMessage": "string",
      "condenseMessage": "string",
      "outputMessage": "string",
      "context": "string",
      "faithfulnessScore": 0.1,
      "displayFaithfulnessScore": "string",
      "answerRelevancyScore": 0.1,
      "displayAnswerRelevancyScore": "string",
      "contextPrecisionScore": 0.1,
      "displayContextPrecisionScore": "string",
      "answerCorrectnessScore": 0.1,
      "displayAnswerCorrectnessScore": "string",
      "answerSimilarityScore": 0.1,
      "displayAnswerSimilarityScore": "string",
      "contextRecallScore": 0.1,
      "displayContextRecallScore": "string",
      "replyTime": "string",
      "createdAt": "string",
      "error": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[ChatbotRecord](#schemachatbotrecord)]|true|none|none|

<h2 id="tocS_PaginatedChatbotTextNodeList">PaginatedChatbotTextNodeList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedchatbottextnodelist"></a>
<a id="schema_PaginatedChatbotTextNodeList"></a>
<a id="tocSpaginatedchatbottextnodelist"></a>
<a id="tocspaginatedchatbottextnodelist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "charactersCount": 0,
      "hitsCount": 0,
      "text": "string",
      "updatedAt": "string",
      "filename": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[ChatbotTextNode](#schemachatbottextnode)]|true|none|none|

<h2 id="tocS_PaginatedChatbotUsageStatisticList">PaginatedChatbotUsageStatisticList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedchatbotusagestatisticlist"></a>
<a id="schema_PaginatedChatbotUsageStatisticList"></a>
<a id="tocSpaginatedchatbotusagestatisticlist"></a>
<a id="tocspaginatedchatbotusagestatisticlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "chatbotId": "964783cd-c648-4628-8262-55dac3831d8f",
      "uploadedFilesSizeTotal": -2147483648,
      "conversationsCount": -2147483648
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[ChatbotUsageStatistic](#schemachatbotusagestatistic)]|true|none|none|

<h2 id="tocS_PaginatedConversationList">PaginatedConversationList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedconversationlist"></a>
<a id="schema_PaginatedConversationList"></a>
<a id="tocSpaginatedconversationlist"></a>
<a id="tocspaginatedconversationlist"></a>

```json
{
  "next": "http://api.example.org/accounts/?cursor=cD00ODY%3D\"",
  "previous": "http://api.example.org/accounts/?cursor=cj0xJnA9NDg3",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "contact": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "avatar": "http://example.com",
        "createdAt": "string"
      },
      "inbox": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "channelType": "line",
        "unreadConversationsCount": -2147483648
      },
      "title": "string",
      "lastMessage": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
        "sender": {
          "id": 0,
          "name": "string",
          "avatar": "http://example.com"
        },
        "type": "incoming",
        "content": "string",
        "feedback": "like",
        "createdAt": "string",
        "attachments": [
          {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "type": "other",
            "filename": "string",
            "file": "http://example.com"
          }
        ],
        "citations": [
          {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "filename": "string",
            "file": "http://example.com",
            "fileType": "string",
            "size": 0,
            "status": "initial",
            "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
            "parser": {
              "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
              "name": "string",
              "provider": "maiagent",
              "priority": 0
            },
            "createdAt": "string"
          }
        ],
        "citationNodes": [
          {
            "chatbotTextNode": {
              "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
              "charactersCount": 0,
              "hitsCount": 0,
              "text": "string",
              "updatedAt": "string",
              "filename": "string"
            },
            "score": 0.1,
            "displayScore": "string"
          }
        ]
      },
      "lastMessageCreatedAt": "string",
      "unreadMessagesCount": 0,
      "autoReplyEnabled": true,
      "isAutoReplyNow": "string",
      "lastReadAt": "string",
      "createdAt": "string",
      "isGroupChat": "string",
      "enableGroupMention": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Conversation](#schemaconversation)]|true|none|none|

<h2 id="tocS_PaginatedCrawlPageList">PaginatedCrawlPageList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedcrawlpagelist"></a>
<a id="schema_PaginatedCrawlPageList"></a>
<a id="tocSpaginatedcrawlpagelist"></a>
<a id="tocspaginatedcrawlpagelist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "url": "http://example.com",
      "title": "string",
      "status": "pending",
      "isOriginalPage": true
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[CrawlPage](#schemacrawlpage)]|true|none|none|

<h2 id="tocS_PaginatedCrawlPageRequestList">PaginatedCrawlPageRequestList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedcrawlpagerequestlist"></a>
<a id="schema_PaginatedCrawlPageRequestList"></a>
<a id="tocSpaginatedcrawlpagerequestlist"></a>
<a id="tocspaginatedcrawlpagerequestlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "url": "http://example.com",
      "status": "processing",
      "createdAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[CrawlPageRequest](#schemacrawlpagerequest)]|true|none|none|

<h2 id="tocS_PaginatedFacebookSystemUserList">PaginatedFacebookSystemUserList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedfacebooksystemuserlist"></a>
<a id="schema_PaginatedFacebookSystemUserList"></a>
<a id="tocSpaginatedfacebooksystemuserlist"></a>
<a id="tocspaginatedfacebooksystemuserlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "systemUserId": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[FacebookSystemUser](#schemafacebooksystemuser)]|true|none|none|

<h2 id="tocS_PaginatedFaqList">PaginatedFaqList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedfaqlist"></a>
<a id="schema_PaginatedFaqList"></a>
<a id="tocSpaginatedfaqlist"></a>
<a id="tocspaginatedfaqlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "question": "string",
      "answer": "string",
      "hitsCount": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Faq](#schemafaq)]|true|none|none|

<h2 id="tocS_PaginatedGroupChatbotList">PaginatedGroupChatbotList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedgroupchatbotlist"></a>
<a id="schema_PaginatedGroupChatbotList"></a>
<a id="tocSpaginatedgroupchatbotlist"></a>
<a id="tocspaginatedgroupchatbotlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "group": "fbd899a6-8a66-4f51-a95d-68668de198ae",
      "chatbot": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
        "name": "string",
        "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
        "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
        "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
        "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
        "instructions": "string",
        "webhookUrl": "http://example.com",
        "apiWebChatId": "string",
        "updatedAt": "string",
        "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
        "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
        "replyMode": "normal",
        "template": "string",
        "unanswerableTemplate": "string",
        "totalWordsCount": -9223372036854776000,
        "enableChineseConversion": true,
        "outputFormat": null,
        "databaseUrl": "string",
        "databaseType": "string"
      },
      "createdAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[GroupChatbot](#schemagroupchatbot)]|true|none|none|

<h2 id="tocS_PaginatedGroupList">PaginatedGroupList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedgrouplist"></a>
<a id="schema_PaginatedGroupList"></a>
<a id="tocSpaginatedgrouplist"></a>
<a id="tocspaginatedgrouplist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "permissions": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "description": "string"
        }
      ],
      "createdAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Group](#schemagroup)]|true|none|none|

<h2 id="tocS_PaginatedGroupMemberList">PaginatedGroupMemberList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedgroupmemberlist"></a>
<a id="schema_PaginatedGroupMemberList"></a>
<a id="tocSpaginatedgroupmemberlist"></a>
<a id="tocspaginatedgroupmemberlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "member": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "email": "string",
        "organization": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "owner": {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "name": "string"
          },
          "createdAt": "string",
          "usageStatistics": "string",
          "organizationPlan": "string"
        },
        "isOwner": "string",
        "permissions": "string",
        "createdAt": "string"
      },
      "createdAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[GroupMember](#schemagroupmember)]|true|none|none|

<h2 id="tocS_PaginatedInboxList">PaginatedInboxList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedinboxlist"></a>
<a id="schema_PaginatedInboxList"></a>
<a id="tocSpaginatedinboxlist"></a>
<a id="tocspaginatedinboxlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "channelType": "line",
      "unreadConversationsCount": -2147483648
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Inbox](#schemainbox)]|true|none|none|

<h2 id="tocS_PaginatedMemberList">PaginatedMemberList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedmemberlist"></a>
<a id="schema_PaginatedMemberList"></a>
<a id="tocSpaginatedmemberlist"></a>
<a id="tocspaginatedmemberlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "email": "string",
      "organization": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "owner": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string"
        },
        "createdAt": "string",
        "usageStatistics": "string",
        "organizationPlan": "string"
      },
      "isOwner": "string",
      "permissions": "string",
      "createdAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Member](#schemamember)]|true|none|none|

<h2 id="tocS_PaginatedMessageList">PaginatedMessageList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedmessagelist"></a>
<a id="schema_PaginatedMessageList"></a>
<a id="tocSpaginatedmessagelist"></a>
<a id="tocspaginatedmessagelist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
      "sender": {
        "id": 0,
        "name": "string",
        "avatar": "http://example.com"
      },
      "type": "incoming",
      "content": "string",
      "feedback": "like",
      "createdAt": "string",
      "attachments": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "type": "other",
          "filename": "string",
          "file": "http://example.com"
        }
      ],
      "citations": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "filename": "string",
          "file": "http://example.com",
          "fileType": "string",
          "size": 0,
          "status": "initial",
          "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
          "parser": {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "name": "string",
            "provider": "maiagent",
            "priority": 0
          },
          "createdAt": "string"
        }
      ],
      "citationNodes": [
        {
          "chatbotTextNode": {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "charactersCount": 0,
            "hitsCount": 0,
            "text": "string",
            "updatedAt": "string",
            "filename": "string"
          },
          "score": 0.1,
          "displayScore": "string"
        }
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Message](#schemamessage)]|true|none|none|

<h2 id="tocS_PaginatedOrganizationListList">PaginatedOrganizationListList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedorganizationlistlist"></a>
<a id="schema_PaginatedOrganizationListList"></a>
<a id="tocSpaginatedorganizationlistlist"></a>
<a id="tocspaginatedorganizationlistlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "owner": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string"
      },
      "createdAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[OrganizationList](#schemaorganizationlist)]|true|none|none|

<h2 id="tocS_PaginatedParserList">PaginatedParserList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedparserlist"></a>
<a id="schema_PaginatedParserList"></a>
<a id="tocSpaginatedparserlist"></a>
<a id="tocspaginatedparserlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "provider": "maiagent",
      "priority": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Parser](#schemaparser)]|true|none|none|

<h2 id="tocS_PaginatedPermissionList">PaginatedPermissionList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedpermissionlist"></a>
<a id="schema_PaginatedPermissionList"></a>
<a id="tocSpaginatedpermissionlist"></a>
<a id="tocspaginatedpermissionlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "description": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[Permission](#schemapermission)]|true|none|none|

<h2 id="tocS_PaginatedUserList">PaginatedUserList</h2>
<!-- backwards compatibility -->
<a id="schemapaginateduserlist"></a>
<a id="schema_PaginatedUserList"></a>
<a id="tocSpaginateduserlist"></a>
<a id="tocspaginateduserlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "avatar": "http://example.com",
      "name": "string",
      "email": "user@example.com",
      "company": "string",
      "invitationCode": "string",
      "apiKeys": "string",
      "permissions": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[User](#schemauser)]|true|none|none|

<h2 id="tocS_PaginatedWebhookRecordList">PaginatedWebhookRecordList</h2>
<!-- backwards compatibility -->
<a id="schemapaginatedwebhookrecordlist"></a>
<a id="schema_PaginatedWebhookRecordList"></a>
<a id="tocSpaginatedwebhookrecordlist"></a>
<a id="tocspaginatedwebhookrecordlist"></a>

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?page=4",
  "previous": "http://api.example.org/accounts/?page=2",
  "results": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "chatbot": {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
        "name": "string",
        "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
        "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
        "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
        "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
        "instructions": "string",
        "webhookUrl": "http://example.com",
        "apiWebChatId": "string",
        "updatedAt": "string",
        "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
        "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
        "replyMode": "normal",
        "template": "string",
        "unanswerableTemplate": "string",
        "totalWordsCount": -9223372036854776000,
        "enableChineseConversion": true,
        "outputFormat": null,
        "databaseUrl": "string",
        "databaseType": "string"
      },
      "url": "string",
      "requestBody": null,
      "response": "string",
      "statusCode": -2147483648,
      "createdAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|true|none|none|
|next|string(uri)¦null|false|none|none|
|previous|string(uri)¦null|false|none|none|
|results|[[WebhookRecord](#schemawebhookrecord)]|true|none|none|

<h2 id="tocS_Parser">Parser</h2>
<!-- backwards compatibility -->
<a id="schemaparser"></a>
<a id="schema_Parser"></a>
<a id="tocSparser"></a>
<a id="tocsparser"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "provider": "maiagent",
  "priority": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|
|provider|[ProviderEnum](#schemaproviderenum)|true|none|* `maiagent` - MaiAgent<br>* `llama` - Llama<br>* `azure` - Azure|
|priority|integer|true|read-only|none|

<h2 id="tocS_PasswordChange">PasswordChange</h2>
<!-- backwards compatibility -->
<a id="schemapasswordchange"></a>
<a id="schema_PasswordChange"></a>
<a id="tocSpasswordchange"></a>
<a id="tocspasswordchange"></a>

```json
{
  "oldPassword": "string",
  "newPassword1": "string",
  "newPassword2": "string"
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
  "email": "user@example.com"
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
  "newPassword1": "string",
  "newPassword2": "string",
  "uid": "string",
  "token": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "type": "other",
  "filename": "string",
  "file": "http://example.com"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|type|[TypeEnum](#schematypeenum)|false|none|* `image` - Image<br>* `video` - Video<br>* `audio` - Audio<br>* `sticker` - Sticker<br>* `other` - Other|
|filename|string|false|none|none|
|file|string(uri)|false|none|none|

<h2 id="tocS_PatchedChatbot">PatchedChatbot</h2>
<!-- backwards compatibility -->
<a id="schemapatchedchatbot"></a>
<a id="schema_PatchedChatbot"></a>
<a id="tocSpatchedchatbot"></a>
<a id="tocspatchedchatbot"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
  "name": "string",
  "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
  "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
  "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
  "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
  "instructions": "string",
  "webhookUrl": "http://example.com",
  "apiWebChatId": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
  "replyMode": "normal",
  "template": "string",
  "unanswerableTemplate": "string",
  "totalWordsCount": -9223372036854776000,
  "enableChineseConversion": true,
  "outputFormat": null,
  "databaseUrl": "string",
  "databaseType": "string"
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
|replyMode|[ReplyModeEnum](#schemareplymodeenum)|false|none|* `normal` - 正常<br>* `template` - 模板<br>* `hybrid` - 混合<br>* `text_to_sql` - text to sql<br>* `workflow` - 工作流|
|template|string¦null|false|none|none|
|unanswerableTemplate|string¦null|false|none|none|
|totalWordsCount|integer(int64)|false|none|累積的使用總字數|
|enableChineseConversion|boolean|false|none|none|
|outputFormat|any|false|none|none|
|databaseUrl|string¦null|false|none|none|
|databaseType|string¦null|false|none|none|

<h2 id="tocS_PatchedChatbotFile">PatchedChatbotFile</h2>
<!-- backwards compatibility -->
<a id="schemapatchedchatbotfile"></a>
<a id="schema_PatchedChatbotFile"></a>
<a id="tocSpatchedchatbotfile"></a>
<a id="tocspatchedchatbotfile"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "filename": "string",
  "file": "http://example.com",
  "fileType": "string",
  "size": 0,
  "status": "initial",
  "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
  "parser": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "provider": "maiagent",
    "priority": 0
  },
  "createdAt": "string"
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
|createdAt|string(timestamp)|false|read-only|none|

<h2 id="tocS_PatchedChatbotFileContent">PatchedChatbotFileContent</h2>
<!-- backwards compatibility -->
<a id="schemapatchedchatbotfilecontent"></a>
<a id="schema_PatchedChatbotFileContent"></a>
<a id="tocSpatchedchatbotfilecontent"></a>
<a id="tocspatchedchatbotfilecontent"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "content": "string",
  "modifiedContent": "string",
  "type": "string",
  "updatedAt": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "contact": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "avatar": "http://example.com",
    "createdAt": "string"
  },
  "inbox": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "channelType": "line",
    "unreadConversationsCount": -2147483648
  },
  "title": "string",
  "lastMessage": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "conversation": "a2d9c3ee-03b3-403a-b1c2-42b286bec1aa",
    "sender": {
      "id": 0,
      "name": "string",
      "avatar": "http://example.com"
    },
    "type": "incoming",
    "content": "string",
    "feedback": "like",
    "createdAt": "string",
    "attachments": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "type": "other",
        "filename": "string",
        "file": "http://example.com"
      }
    ],
    "citations": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "filename": "string",
        "file": "http://example.com",
        "fileType": "string",
        "size": 0,
        "status": "initial",
        "chatbotFileContent": "97f16dcb-1331-4a72-9002-e2865ea21c13",
        "parser": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "name": "string",
          "provider": "maiagent",
          "priority": 0
        },
        "createdAt": "string"
      }
    ],
    "citationNodes": [
      {
        "chatbotTextNode": {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "charactersCount": 0,
          "hitsCount": 0,
          "text": "string",
          "updatedAt": "string",
          "filename": "string"
        },
        "score": 0.1,
        "displayScore": "string"
      }
    ]
  },
  "lastMessageCreatedAt": "string",
  "unreadMessagesCount": 0,
  "autoReplyEnabled": true,
  "isAutoReplyNow": "string",
  "lastReadAt": "string",
  "createdAt": "string",
  "isGroupChat": "string",
  "enableGroupMention": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|contact|[Contact](#schemacontact)|false|none|none|
|inbox|[Inbox](#schemainbox)|false|none|none|
|title|string|false|read-only|none|
|lastMessage|[Message](#schemamessage)|false|none|none|
|lastMessageCreatedAt|string(timestamp)|false|read-only|none|
|unreadMessagesCount|integer|false|read-only|none|
|autoReplyEnabled|boolean|false|read-only|none|
|isAutoReplyNow|string|false|read-only|none|
|lastReadAt|string(timestamp)¦null|false|read-only|none|
|createdAt|string(timestamp)|false|read-only|none|
|isGroupChat|string|false|read-only|none|
|enableGroupMention|string|false|read-only|none|

<h2 id="tocS_PatchedFaq">PatchedFaq</h2>
<!-- backwards compatibility -->
<a id="schemapatchedfaq"></a>
<a id="schema_PatchedFaq"></a>
<a id="tocSpatchedfaq"></a>
<a id="tocspatchedfaq"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "question": "string",
  "answer": "string",
  "hitsCount": 0
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
  "permissions": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ],
  "createdAt": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "channelType": "line",
  "channelTypeLabel": "string",
  "name": "string",
  "autoReplySchedules": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "weekday": 0,
      "isEnabled": true,
      "timeSlots": [
        [
          "14:15:22Z"
        ]
      ],
      "weekdayName": "string"
    }
  ],
  "unreadConversationsCount": 0,
  "channel": "string",
  "createdAt": "string",
  "updatedAt": "string",
  "organization": "452c1a86-a0af-475b-b03f-724878b0f387"
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
|unreadConversationsCount|integer|false|read-only|none|
|channel|string|false|none|none|
|createdAt|string(timestamp)|false|read-only|none|
|updatedAt|string(timestamp)|false|read-only|none|
|organization|string(uuid)¦null|false|none|none|

<h2 id="tocS_PatchedLineChannel">PatchedLineChannel</h2>
<!-- backwards compatibility -->
<a id="schemapatchedlinechannel"></a>
<a id="schema_PatchedLineChannel"></a>
<a id="tocSpatchedlinechannel"></a>
<a id="tocspatchedlinechannel"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "channelId": "string",
  "channelSecret": "string",
  "channelAccessToken": "string",
  "webhookUrl": "string",
  "enableGroupMention": true
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "owner": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string"
  },
  "createdAt": "string",
  "usageStatistics": "string",
  "organizationPlan": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|none|
|name|string|false|none|none|
|owner|[UserBase](#schemauserbase)|false|read-only|none|
|createdAt|string(timestamp)|false|read-only|none|
|usageStatistics|string|false|read-only|none|
|organizationPlan|string|false|read-only|none|

<h2 id="tocS_PatchedUser">PatchedUser</h2>
<!-- backwards compatibility -->
<a id="schemapatcheduser"></a>
<a id="schema_PatchedUser"></a>
<a id="tocSpatcheduser"></a>
<a id="tocspatcheduser"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "enableSpeech": true,
  "displayGreeting": "string",
  "displayConversationStarters": "string",
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true,
  "accessType": "web"
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
|enableFileUpload|boolean|false|none|none|
|enableDisplayCitations|boolean|false|none|none|
|enableShareConversation|boolean|false|none|none|
|enableLocation|boolean|false|none|none|
|enableShowPoweredBy|boolean|false|none|none|
|accessType|[AccessTypeEnum](#schemaaccesstypeenum)|false|read-only|* `web` - Web Chat<br>* `admin` - Admin 問答<br>* `api` - API|

<h2 id="tocS_PatchedWorkflow">PatchedWorkflow</h2>
<!-- backwards compatibility -->
<a id="schemapatchedworkflow"></a>
<a id="schema_PatchedWorkflow"></a>
<a id="tocSpatchedworkflow"></a>
<a id="tocspatchedworkflow"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "description": "string"
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
"maiagent"

```

* `maiagent` - MaiAgent
* `llama` - Llama
* `azure` - Azure

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|* `maiagent` - MaiAgent<br>* `llama` - Llama<br>* `azure` - Azure|

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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "deviceId": "string",
  "metadata": null,
  "createdAt": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|name|string|true|none|none|

<h2 id="tocS_ReplyModeEnum">ReplyModeEnum</h2>
<!-- backwards compatibility -->
<a id="schemareplymodeenum"></a>
<a id="schema_ReplyModeEnum"></a>
<a id="tocSreplymodeenum"></a>
<a id="tocsreplymodeenum"></a>

```json
"normal"

```

* `normal` - 正常
* `template` - 模板
* `hybrid` - 混合
* `text_to_sql` - text to sql
* `workflow` - 工作流

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|* `normal` - 正常<br>* `template` - 模板<br>* `hybrid` - 混合<br>* `text_to_sql` - text to sql<br>* `workflow` - 工作流|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|normal|
|*anonymous*|template|
|*anonymous*|hybrid|
|*anonymous*|text_to_sql|
|*anonymous*|workflow|

<h2 id="tocS_RerankerModel">RerankerModel</h2>
<!-- backwards compatibility -->
<a id="schemarerankermodel"></a>
<a id="schema_RerankerModel"></a>
<a id="tocSrerankermodel"></a>
<a id="tocsrerankermodel"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "isDefault": true
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
  "email": "user@example.com"
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
  "detail": "string"
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
  "id": 0,
  "name": "string",
  "avatar": "http://example.com"
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
"processing"

```

* `processing` - Processing
* `done` - Done
* `cancelled` - Cancelled

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|* `processing` - Processing<br>* `done` - Done<br>* `cancelled` - Cancelled|

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
"initial"

```

* `initial` - Initial
* `processing` - Processing
* `done` - Done
* `deleting` - Deleting
* `failed` - Failed

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|* `initial` - Initial<br>* `processing` - Processing<br>* `done` - Done<br>* `deleting` - Deleting<br>* `failed` - Failed|

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
  "primaryColor": "string",
  "dialogColor": "string",
  "navbarTextColor": "string"
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
  "access": "string",
  "refresh": "string"
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
  "token": "string"
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
"image"

```

* `image` - Image
* `video` - Video
* `audio` - Audio
* `sticker` - Sticker
* `other` - Other

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|* `image` - Image<br>* `video` - Video<br>* `audio` - Audio<br>* `sticker` - Sticker<br>* `other` - Other|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|image|
|*anonymous*|video|
|*anonymous*|audio|
|*anonymous*|sticker|
|*anonymous*|other|

<h2 id="tocS_UploadPresignedUrl">UploadPresignedUrl</h2>
<!-- backwards compatibility -->
<a id="schemauploadpresignedurl"></a>
<a id="schema_UploadPresignedUrl"></a>
<a id="tocSuploadpresignedurl"></a>
<a id="tocsuploadpresignedurl"></a>

```json
{
  "modelName": "string",
  "fieldName": "string",
  "filename": "string",
  "fileSize": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|modelName|string|true|none|none|
|fieldName|string|true|none|none|
|filename|string|true|none|none|
|fileSize|integer|true|none|none|

<h2 id="tocS_User">User</h2>
<!-- backwards compatibility -->
<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string",
  "email": "user@example.com",
  "company": "string",
  "invitationCode": "string",
  "apiKeys": "string",
  "permissions": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string"
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
  "key": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "avatar": "http://example.com",
  "logo": "http://example.com",
  "description": "string",
  "cover": "http://example.com",
  "backUrl": "string",
  "isActive": true,
  "enableSpeech": true,
  "displayGreeting": "string",
  "displayConversationStarters": "string",
  "theme": {
    "primaryColor": "string",
    "dialogColor": "string",
    "navbarTextColor": "string"
  },
  "enableFileUpload": true,
  "enableDisplayCitations": true,
  "enableShareConversation": true,
  "enableLocation": true,
  "enableShowPoweredBy": true,
  "accessType": "web"
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
|enableFileUpload|boolean|false|none|none|
|enableDisplayCitations|boolean|false|none|none|
|enableShareConversation|boolean|false|none|none|
|enableLocation|boolean|false|none|none|
|enableShowPoweredBy|boolean|false|none|none|
|accessType|[AccessTypeEnum](#schemaaccesstypeenum)|true|read-only|* `web` - Web Chat<br>* `admin` - Admin 問答<br>* `api` - API|

<h2 id="tocS_WebChatList">WebChatList</h2>
<!-- backwards compatibility -->
<a id="schemawebchatlist"></a>
<a id="schema_WebChatList"></a>
<a id="tocSwebchatlist"></a>
<a id="tocswebchatlist"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "avatar": "http://example.com",
  "name": "string"
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
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbot": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "workflow": "b64ad92b-f157-48fc-9389-00fc30e61bbf",
    "name": "string",
    "largeLanguageModel": "1d7a9c59-3060-4642-b31a-c38d1ec65892",
    "rag": "bbbfee98-505b-4c45-b988-d3bc800c2ff2",
    "embeddingModel": "5727a487-297b-46e2-a890-9f8b84fe2406",
    "rerankerModel": "f4c9d1cf-eb35-4428-b28f-75c580eea279",
    "instructions": "string",
    "webhookUrl": "http://example.com",
    "apiWebChatId": "string",
    "updatedAt": "string",
    "organization": "452c1a86-a0af-475b-b03f-724878b0f387",
    "builtInWorkflow": "e54b4ea1-1ddf-4187-82a3-fb59ca2b8684",
    "replyMode": "normal",
    "template": "string",
    "unanswerableTemplate": "string",
    "totalWordsCount": -9223372036854776000,
    "enableChineseConversion": true,
    "outputFormat": null,
    "databaseUrl": "string",
    "databaseType": "string"
  },
  "url": "string",
  "requestBody": null,
  "response": "string",
  "statusCode": -2147483648,
  "createdAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|chatbot|[Chatbot](#schemachatbot)|true|none|Adds nested create feature|
|url|string|true|none|none|
|requestBody|any|false|none|none|
|response|string|false|none|none|
|statusCode|integer¦null|false|none|none|
|createdAt|string(timestamp)|true|read-only|none|

<h2 id="tocS_Workflow">Workflow</h2>
<!-- backwards compatibility -->
<a id="schemaworkflow"></a>
<a id="schema_Workflow"></a>
<a id="tocSworkflow"></a>
<a id="tocsworkflow"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "chatbot": "e5c2613a-d13c-42ef-9725-6d0a42f21133",
  "metadata": null
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|read-only|none|
|chatbot|string(uuid)|true|none|none|
|metadata|any|false|none|none|

