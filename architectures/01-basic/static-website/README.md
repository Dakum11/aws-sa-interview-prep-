#  Simple Web Application # 

## Architecture : 

User -> DNS -> Web Server ( Backend ) -> Database -> Backend Response -> Browser -> UI update

## Explaination : 

The user sends a request from the browser, which resolves through DNS and reaches the backend server. The backend processes the request, interacts with the database for data retrieval, and then returns an HTTP response containing status code, headers, and data. The browser then processes this response, stores authentication tokens if present, and updates the UI accordingly or redirects the user.

## Example : 

Let see what happen when we try to access a Website : wwww.foodapp.com

### Step 1 : User Opens a Website ### 

what happens ? 

#### 1. DNS lookup ####

Brwoser ask : what is the IP of foodapp.com?

DNS returns the IP. 

Now Browser know where to go. 


### Step 2 : Request goes to the Web Server ###

Browser sends a request : 

Get https://foodapp.com/login 

The request goes the Web Server ( Backend Application ) Python , java or Node.js

What happens in Web Server ? 

Web Server recieves request and 

#### 1 : Understand Route ####

./login page requested 

#### 2 : Sends HTML Page back or API reponse. #### 

If it's a simple website : It will send the login page ( HTML /JS/CSS)

if it's a modern app : It will semd api response only

### Step 3 : User enter the login details

Plain text 

Email  : test@foodapp.com 
Password : 1234

### Step 4: Browser sends the POST request 







