** Simple Web Application ** 

## Architecture : 

User -> DNS -> Web Server ( Backend ) -> Database -> Backend Response -> Browser -> UI update

## Explaination : 

The user sends a request from the browser, which resolves through DNS and reaches the backend server. The backend processes the request, interacts with the database for data retrieval, and then returns an HTTP response containing status code, headers, and data. The browser then processes this response, stores authentication tokens if present, and updates the UI accordingly or redirects the user.

## Example : 


