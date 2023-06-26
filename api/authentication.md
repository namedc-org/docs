# Authentication

> In order to use our service, you first need to have queries regarding your account. Read [this](./api/info.md).


---

> After that you have your personal token you need to include it in your requests:

<!-- tabs:start -->

#### **Javascript (axios)**

```javascript
const axios = require('axios');

axios.get(`https://api.namedc.org/search?q=${username}`, {
    headers: {
        Authorization: `Bearer ${token}`
    }
}).then(response => {
    console.log(response.data)
})
.catch(error => {
    console.error(error);
})


```

#### **Javascript (node-fetch)**

```javascript
const fetch = require('node-fetch');

fetch(`https://api.namedc.org/search?q=${username}`, {
    headers: {
      Authorization: `Bearer ${token}`
    }
  }).then(response => 
  response.json()
  ).then(data => {
    console.log(data);
  }).catch(error => {
    console.error(error);
  });
```

#### **Python (requets)**

```python
import requests

username = 'your_username'
token = 'your_token'

url = f"https://api.namedc.org/search?q={username}"
headers = {
    'Authorization': f'Bearer {token}'
}

response = requests.get(url, headers=headers)

if response.status_code == 200:
    data = response.json()
    print(data)
else:
    print(f"Request failed with status code {response.status_code}")
    print(response.text)
```

#### **Output (200)**

> The output should return:

```json
{
	"name": "username",
	"history": [
		{
			"userid": "user_id",
			"addedAt": "added_time",
		}
	],
	"__v": 40
}
```

<!-- tabs:end -->

> We are planning soon to release API wrappers in different language, if you would like to contribute you will be listed here with a credit.

---

### Checkin connection

> We provide an endpoint to check the connection and it outputs the query count too.

<!-- tabs:start -->

#### **Javascript (axios)**

```javascript
const axios = require('axios');

axios.get(`https://api.namedc.org/account`, {
    headers: {
        Authorization: `Bearer ${token}`
    }
}).then(response => {
    console.log(response.data)
})
.catch(error => {
    console.error(error);
})


```

#### **Javascript (node-fetch)**

```javascript
const fetch = require('node-fetch');

fetch(`https://api.namedc.org/account`, {
    headers: {
      Authorization: `Bearer ${token}`
    }
  }).then(response => 
  response.json()
  ).then(data => {
    console.log(data);
  }).catch(error => {
    console.error(error);
  });
```

#### **Python (requets)**

```python
import requests

username = 'your_username'
token = 'your_token'

url = f"https://api.namedc.org/account"
headers = {
    'Authorization': f'Bearer {token}'
}

response = requests.get(url, headers=headers)

if response.status_code == 200:
    data = response.json()
    print(data)
else:
    print(f"Request failed with status code {response.status_code}")
    print(response.text)
```

#### **Output (200)**

> The output should return:

```json
{
	"queries": 993,
	"__v": 0
}
```
<!-- tabs:end -->



