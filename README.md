# Poorman's Free Chat GPT

For someone that enjoy the fun of being poor

## Setup
    
### Authentication
#### Step 1
Create `accounts.txt` - A list of accounts separated by new line 

Format:
```
email:password
...
```

#### Step 2:

HAR file pool


  1. Use a chromium-based browser (Chrome, Edge) to open the browser developer tools (F12), switch to the Network tab, and check the **preserve log** option.

  2. Log in (log out first if already login) to `https://chat.openai.com/`, login, pass the Arkose verification step,
  3. Create a new chat and select the GPT-4 model, enter any text, switch to the GPT-3.5 model, and enter any text.

  4. Click the Export HAR button under the Network tab to export the file `chat.openai.com.har` and place it in the `harPool` folder of the same level as this program.

#### Step 3:
Maybe you will need `cookies.json` , create and put it in the root directory of this program

```json
{
        "username": [
            {
                "Name": "__Secure-next-auth.session-token",
                "Value": "After logging into a third-party account on browser，the value of __Secure-next-auth.session-token in cookies",
                "Path": "/",
                "Domain": "",
                "Expires": "0001-01-01T00:00:00Z",
                "MaxAge": 0,
                "Secure": true,
                "HttpOnly": true,
                "SameSite": 2,
                "Unparsed": null
            }
        ]
    }
```

All authenticated access tokens and PUID will store in `access_tokens.json`

### Run
```bash
go build
./freechatgpt
```