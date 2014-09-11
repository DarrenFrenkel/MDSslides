### Consuming an HTTP Request and Sending a Response

* The HttpRequest argument gets passed into the request parameter of the view function.
* The HttpRequest instance has multiple properties associated with it. One is `method` which returns the HTTP method (GET, HEAD, POST, PUT, DELETE, OPTIONS, TRACE).
* We then could send our response back to our browser using the Django builtin function `HttpResponse`
