#  Simple Web Application # 

## Architecture : 

User -> DNS -> Web Server ( Backend ) -> Database -> Backend Response -> Browser -> UI update

## Explaination : 

The user sends a request from the browser, which resolves through DNS and reaches the backend server. The backend processes the request, interacts with the database for data retrieval, and then returns an HTTP response containing status code, headers, and data. The browser then processes this response, stores authentication tokens if present, and updates the UI accordingly or redirects the user.

## Example : 

Let see what happen when we try to access a Website : wwww.foodapp.com

Step 1: User Opens a Website

what happens ? 

1. DNS lookup

Brwoser ask : what is the IP of foodapp.com?

DNS returns the IP. 

Now Browser know where to go. 

Step 2 : 





