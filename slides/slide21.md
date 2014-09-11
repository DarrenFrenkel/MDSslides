## 5.3 How it comes together

![Django Basic Request Response Structure](static/basic-request-response.png)

- The browser via HTTP makes a request to your server, using your input URL as a resource.
- The server then looks for a matching URL in your urlconfigs file (urls.py).
- The matched URL then calls a function or a class in the views.py file.
- The view then displays a response to the browser.