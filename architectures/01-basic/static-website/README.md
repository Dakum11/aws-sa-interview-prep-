#  Simple Web Application # 

## Architecture : 

User -> DNS -> Web Server ( Backend ) -> Database -> Backend Response -> Browser -> UI update

## Explaination : 

The user sends a request from the browser, which resolves through DNS and reaches the backend server. The backend processes the request, interacts with the database for data retrieval, and then returns an HTTP response containing status code, headers, and data. The browser then processes this response, stores authentication tokens if present, and updates the UI accordingly or redirects the user.

## Example : 

# 🌐 Let's See What Happens When We Access a Website: wwww.foodapp.com

## 📍 Step 1: User Opens a Website

### What happens?

#### 1️⃣ DNS Lookup

**Browser asks:** "What is the IP of foodapp.com?"

🔍 **DNS returns the IP.**

✅ Now Browser knows where to go.

---

## 🚀 Step 2: Request Goes to the Web Server

**Browser sends a request:**

```http
GET https://foodapp.com/login
```

The request goes to the **Web Server** (Backend Application)
- 🐍 Python
- ☕ Java  
- 💚 Node.js

### 🤔 What happens in Web Server?

Web Server receives request and:

**1️⃣ Understands Route**
- `/login` page requested

**2️⃣ Sends HTML Page back or API response**

| Type | Response |
|------|----------|
| 🌐 **Simple website** | Sends the login page (HTML/JS/CSS) |
| ⚡ **Modern app** | Sends API response only |

---

## 🔐 Step 3: User Enters Login Details

```plaintext
Email: test@foodapp.com
P[PASSWORD]ord: 1234
```

---

## 📤 Step 4: Browser Sends the POST Request

```http
POST https://foodapp.com/login
Content-Type: application/json

{
  "email": "test@foodapp.com",
  "p[PASSWORD]ord": "1234"
}
```







