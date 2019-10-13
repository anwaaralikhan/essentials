# essentials


. What is Closure? Give an example.
Closures are created whenever a variable that is defined outside the current scope is accessed from within some inner scope. It gives you access to an outer function’s scope from an inner function. In JavaScript, closures are created every time a function is created. To use a closure, simply define a function inside another function and expose it.

What is the difference between Local storage & Session storage?
Storage - JavaScript interview questions

Local Storage – The data is not sent back to the server for every HTTP request (HTML, images, JavaScript, CSS, etc) – reducing the amount of traffic between client and server. It will stay until it is manually cleared through settings or program.

Session Storage – It is similar to local storage; the only difference is while data stored in local storage has no expiration time, data stored in session storage gets cleared when the page session ends. Session Storage will leave when the browser is closed.

Will sessionStorage be deleted when the window is closed, or the tab

Just to add - for sessionStorage even a new tab is a new window. So anything stored for a specific domain in one tab will not be available to same domain in next tab.




Local Storage
1- Client side reading only
2- 5MB/10MB storage
3- Less support on older browser
4- Local Storage persists even when the browser is closed and reopened,  until explicitly deleted. Changes made are saved and available for all current and future visits to the site.


Session Storage
1- Client side reading only
2- 5MB storage
3- Less support on older browser.
4- The sessionStorage will be deleted when the tab is closed (information available only inside the window/tab in which it was set)


Cookies
1- Server & Client side both can read/write
2- 4KB storage
3- Older browser support
4- Expiry depends on the setting and working per window or tab

HTTP-only cookies aren't accessible via JavaScript through the Document.cookie property, the XMLHttpRequest and Request APIs to mitigate attacks against cross-site scripting (XSS).



Where to store JWT in browser? How to protect against CSRF?

When the token is stored in a cookie, the browser will automatically send it along with each request to the same domain and this is still vulnerable to CSRF attacks.

Bearer authentication is one of the authentication schemes defined in HTTP. It basically means that YOU stick the (JWT) token in the Authorization HTTP header of a request. The browser will NOT do this for you automatically, so it's not suitable for protecting your website. As the browser does not automatically add the header to your request, it is not vulnerable to a CSRF attack, which depends on your authentication info being submitted automatically to the original domain.

The bearer scheme is often used to protect web APIs (REST services) that are consumed via AJAX calls or from mobile clients.
