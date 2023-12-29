Go to this web site.
```https://codedamn.com/news/javascript/javascript-cors-error-handling```

4. Using CORS-anywhere
CORS-anywhere is a public proxy server that adds the necessary CORS headers to the responses it forwards. By making requests through CORS-anywhere, you can bypass the CORS restrictions enforced by the browser.

To use CORS-anywhere, simply prefix your target URL with the CORS-anywhere URL:

```
const targetUrl = 'http://example.com/data';
const proxyUrl = 'https://cors-anywhere.herokuapp.com/';

fetch(proxyUrl + targetUrl)
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));

```
Note: Using a public proxy like CORS-anywhere is not recommended for production applications due to security and reliability concerns. Consider setting up your own proxy server or using a more secure alternative like a reverse proxy.
