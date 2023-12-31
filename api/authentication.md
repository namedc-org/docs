# Authentication

> In order to use our service, you first need to have queries regarding your account. Read [this](./api/info.md).


---

> After that you have your personal token you need to include it in your requests:

<!-- tabs:start -->

#### **Javascript (axios)**

```javascript
const axios = require('axios');

axios.get(`https://api.namedc.org/search?query=${username}`, {
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

fetch(`https://api.namedc.org/search?query=${username}`, {
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

url = f"https://api.namedc.org/search?query={username}"
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
	"id": String,
	"userHistory": [{
		"addedAt": String,
		"User": {
			"accent_color": String,
			"avatar": String,
			"avatar_decoration": String,
			"banner": String,
			"banner_color": String,
			"discriminator": String,
			"display_name": String,
			"flags": Number,
			"global_name": String,
			"id": String,
			"public_flags": Number,
			"username": String
		}
	}],
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
  "id": String,
  "createdAt": String,
  "queries": Number
}
```
<!-- tabs:end -->



