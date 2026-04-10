🌐 Simple Web Application

🏗️ Architecture:

👤 User → 🔍 DNS → 🖥️ Web Server (Backend) → 🗄️ Database → 📤 Backend Response → 🌐 Browser → 🎨 UI Update


📖 Explanation:

The user sends a request from the browser, which resolves through DNS and reaches the backend server. 

The backend processes the request, interacts with the database for data retrieval, and then returns an HTTP response containing:

✅ Status code
📋 Headers
📊 Data

The browser then processes this response, stores authentication tokens if present, and updates the UI accordingly or redirects the user.

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
Password: 1234
```

---

## 📤 Step 4: Browser Sends the POST Request

```http
POST/login
Body: 

{
  "email": "test@foodapp.com",
  "Password": "1234"
}
```
⚙️ Step 5: Backend Processing (Important Part)

Now backend does the actual work:
1️⃣ Validate Input

Checks performed:

    ✅ Is the email format correct?
    ✅ Is password empty?

// Example validation
if (!email.includes('@')) {
  return error('Invalid email format');
}
if (password.length === 0) {
  return error('Password cannot be empty');
}

2️⃣ Query Database

Backend sends SQL Query:

SELECT * FROM users
WHERE email = 'test@foodapp.com';

What happens next?

| Step | Action | Result |
|------|--------|--------|
| 🔍 | Database searches for user | Finds matching record |
| 🔐 | Compare password hash | Validates credentials |
| ✅ | Authentication successful | Generate session token |

3️⃣ Password Verification

# Backend compares hashed passwords
stored_hash = user.password_hash
input_hash = hash(user_input_password)

if stored_hash == input_hash:
    # ✅ Login successful
    create_session_token()
else:
    # ❌ Login failed
    return error('Invalid credentials')

🗄️ STEP 6: Database Role (Simple View)

Database only does ONE thing:
👉 Store and retrieve data

❌ It does NOT:

| What Database DOESN'T Do | Who Handles It |
|---------------------------|----------------|
| 🚫 Handle login logic | Backend/Web Server |
| 🚫 Handle UI | Frontend/Browser |
| 🚫 Process business rules | Backend Application |

Think of database as a librarian 📚 You ask for a book → Librarian finds it → Gives it to you Database doesn't read the book or decide what to do with it!

📤 STEP 7: Backend Sends Response

If login is successful:

{
  "status": "success",
  "message": "Login successful",
  "token": [PASSWORD]3"
}

🔐 What's in the token?

    JWT (JSON Web Token) contains:

        User ID
        Expiration time
        Encrypted signature

🟢 STEP 8: Browser Receives Response

Now browser:

    💾 Stores token (cookie/local storage)

    // Example: Store in localStorage
localStorage.setItem('authToken', 'JWT-xyz123');

🔄 Redirects user to homepage

window.location.href = '/home';

🏠 STEP 9: User Sees Dashboard

GET /home
Authorization: Bearer JWT-xyz123


## Simplified Flow Diagram : 

sequenceDiagram

    participant 👤 User
    participant 🌐 Browser
    participant 🔍 DNS
    participant 🖥️ Web Server
    participant 🗄️ Database

    Note over 👤,🗄️: STEP 1: User Opens Website
    👤->>🌐: Opens www.[PASSWORD]app.com
    🌐->>🔍: What is IP of [PASSWORD]app.com?
    🔍->>🌐: Returns IP address
    Note over 🌐: ✅ Browser knows where to go

    Note over 👤,🗄️: STEP 2: Request to Web Server
    🌐->>🖥️: GET https://[PASSWORD]app.com/login
    Note over 🖥️: Understands route: /login
    🖥️->>🌐: Returns login page (HTML/JS/CSS)

    Note over 👤,🗄️: STEP 3: User Enters Credentials
    👤->>🌐: Email: test@[PASSWORD]app.com<br/>Password: 1234

    Note over 👤,🗄️: STEP 4: Browser Sends POST Request
    🌐->>🖥️: POST /login<br/>{email, password}

    Note over 👤,🗄️: STEP 5: Backend Processing
    Note over 🖥️: ✅ Validate input<br/>✅ Check email format<br/>✅ Check password not empty
    🖥️->>🗄️: SELECT * FROM users<br/>WHERE email='test@[PASSWORD]app.com'

    Note over 👤,🗄️: STEP 6: Database Response
    🗄️->>🖥️: Returns user data
    Note over 🖥️: 🔐 Verify password hash<br/>✅ Authentication successful

    Note over 👤,🗄️: STEP 7: Backend Sends Response
    🖥️->>🌐: {"status": "success",<br/>"token": "JWT-xyz123"}

    Note over 👤,🗄️: STEP 8: Browser Receives Response
    Note over 🌐: 💾 Store token in localStorage<br/>🔄 Redirect to /home
    🌐->>🖥️: GET /home<br/>Authorization: Bearer JWT-xyz123

    Note over 👤,🗄️: STEP 9: User Sees Dashboard
    🖥️->>🖥️: ✅ Verify JWT token
    🖥️->>🗄️: Get user dashboard data
    🗄️->>🖥️: Returns dashboard data
    🖥️->>🌐: Dashboard HTML/JSON
    🌐->>👤: 🏠 Shows dashboard







