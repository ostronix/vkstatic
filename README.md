<p align='center'>
<a href="https://www.npmjs.com/package/vkstatic"><img src="https://img.shields.io/npm/v/vkstatic.svg?style=flat-square" alt="NPM version"></a>
</p>

<p align='center'><img src='https://img.shields.io/badge/code%20style-standard-brightgreen.svg'></img></p>
<p align='center'><img src='https://img.shields.io/npm/dt/vkstatic.svg'></img></p>

## 📦 Installation

> **[Node.js](https://nodejs.org/) 12.20.0 or newer is required**

- **Using `Yarn`** (recommended)
  ```shell
  yarn add vkstatic
  ```
- **Using `npm`**
  ```shell
  npm i vkstatic
  ```
- **Using `pnpm`**
  ```shell
  pnpm add vkstatic
  ```

## 📄 Object `VK`

**TOKEN** - ``TOKEN USER / GROUP``

**GROUPID** - ``GROUPID``

**V** - ``VERSION``

**USER** - ``USER TYPE | DEFAULT: AGENT``

**APITYPE** - ``APITYPE | TYPE``

# 📄 Usage `methods`

## 💡 `Method #1`

```javascript
import { VK, Method } from 'vkstatic'
import { config } from 'unicode-parsed'

config ('.parsed')

const params = {
   token: process.parse.TOKEN,
   groupId: process.parse.GROUPID
}

const vk = new VK ({
...params
})

const method = async () => {
const response = await vk.api
.usage ('users.get', { user_ids: 1 })

return response
}

method ()
```

## 💡 `Method #2`

```javascript
import { VK, Method } from 'vkstatic'
import { config } from 'unicode-parsed'

config ('.parsed')

const params = {
   token: process.parse.TOKEN,
   groupId: process.parse.GROUPID
}

const vk = new VK ({
...params
})

const method = async () => {
const response = await new Method
.use ("users.get", { user_ids: 1 })

return response
}

method ()
```

## 💾 `Method #3`

```javascript
import { VK, Method, execute } from 'vkstatic'
import { config } from 'unicode-parsed'

config ('.parsed')

const params = {
   token: process.parse.TOKEN,
   groupId: process.parse.GROUPID
}

const vk = new VK ({
...params
})

const api = async () => await execute ('users.get', { user_ids: 1 })

api ()
```

# 📄 Usage `event`

## 🖥 `Method #1`

```javascript
import { VK, Method } from 'vkstatic'
import { config } from 'unicode-parsed'

config ('.parsed')

const params = {
   token: process.parse.TOKEN,
   groupId: process.parse.GROUPID
}

const vk = new VK ({
...params
})

const event = async () => {
await vk.event (response => {
      response.send ("Привет!")
})
}

event () 
```

## 📄 `Method #2`
```javascript
import { VK, Method } from 'vkstatic'
import { config } from 'unicode-parsed'

config ('.parsed')

const params = {
   token: process.parse.TOKEN,
   groupId: process.parse.GROUPID
}

const vk = new VK ({
...params
})

const method = new Method ()

const event = async () => {
await method.event (response => {
      response.send ("Привет!")
})
}

event ()
```

## ✅ `Check` ``event``
```javascript
import { VK, Method } from 'vkstatic'
import { config } from 'unicode-parsed'

config ('.parsed')

const params = {
   token: process.parse.TOKEN,
   groupId: process.parse.GROUPID
}

const vk = new VK ({
...params
})

const method = new Method ()

const eventCheck = async () => {
await method.event (response => {
      if (response.event.event_type == 'message_new') {
      return response.send ('Привет!')
      }
})
}

eventCheck ()
```

# 💡 `Functions`

```javascript
import { getToken } from 'vkstatic'
import { config } from 'unicode-parsed'

config ('.parsed')

const cute_token = getToken (process.parse.URL_TOKEN)

console
.debug (cute_token)
```

# ⏰ Create Command 

```javascript
import { VK, Method } from 'vkstatic'

const params = {
      token: process.parse.TOKEN,
      groupId: process.intige.GROUPID
}

const vk = new VK ({
...params
})

const command = async () => {
await new Method ()
.event (response => {

       const cmd = "привет"
       
       if (response.text == cmd) {
       response.send ('Привет!')
      return response.edit ('Здравствуйте!')
       }
})
}

command ()
```

# 📄 Search `Method`

```javascript
import { MethodSearch } from 'vkstatic'

const method = MethodSearch ("donut")

console
.debug (method) // true
```

# 🤖 Easy Bot

```javascript
import { VK, Method } from 'vkstatic'
import { config } from 'unicode-parsed'

config ('.parsed')

const params = {
   token: process.parse.TOKEN,
   groupId: process.parse.GROUPID
}

const vk = new VK ({
...params
})

const commands = [
{
     command: "/start",
     answer: "⭐ Привет! Рад видеть тебя в данном боте!"
}
]

const bot = async () => {
await new Method ()
.event (response => {
     if (response.event.event_type == 'message_new') {
        return commands.filter (manager => manager.command == response.text)
        .map (function (types) {
           return response.send (types.answer)
        })
     }
     
bot ()
```

# 🍥 Check `attachments`

```javascript
import { VK, Method } from 'vkstatic'
import { config } from 'unicode-parsed'

config ('.parsed')

const params = {
   token: process.parse.TOKEN,
   groupId: process.parse.GROUPID
}

const vk = new VK ({
...params
})

const response = async () => {
await new Method ()
.event (response => {
if (response.event.event_type == 'message_new' && response.attachments [0].type == 'photo') {
return response.send ('Это фото!')
}
})
}

response ()
```

# 📄 Check `attachments`

```javascript
import { VK, Method } from 'vkstatic'
import { config } from 'unicode-parsed'

config ('.parsed')

const params = {
   token: process.parse.TOKEN,
   groupId: process.parse.GROUPID
}

const vk = new VK ({
...params
})

const check = function (type) {
    return type.toString ()
    .replace ('photo', 'фото')
    .replace ('video', 'видео')
}

const response = async () => {
await new Method ()
.event (method => {

if (method.event.event_type == 'message_new' && method.attachment) {
return method.send ("Это " + check (method.attachments [0].type))
}
})

response ()
```
