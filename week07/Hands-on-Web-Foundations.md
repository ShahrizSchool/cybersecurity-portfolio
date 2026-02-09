# Week 7 — Web Foundations (HTTP & Sessions)

## Objective
The goal of this week was to understand how web authentication works at a network level by observing HTTP requests and responses before and after login. Instead of relying only on theory, I focused on using browser developer tools to see how login flows behave in real websites.

## Environment
- Browser: Google Chrome  
- Tool Used: Chrome DevTools (Network tab)  

**Practice Websites:**
- `testphp.vulnweb.com` (minimal test site)
- A real-world work website (screenshots not included for privacy)

## Observations on a Minimal Website (`testphp.vulnweb.com`)

### Before Login
Before logging in, the website generated a very small number of network requests:
- A total of 4 requests
- Mostly GET requests for:
  - `login.php`
  - `style.css`
  - `logo.gif`

At this stage, the browser was only requesting static content required to load the login page. There was no indication that the server was treating the user as authenticated.

### Login Action
When submitting the login form:
- The browser sent a POST request to `userinfo.php`
- The request method was POST, initiated by the client (me)
- The content type was `application/x-www-form-urlencoded`, indicating standard form data submission
- The server responded with a 302 Found status code

This redirect indicated that the server processed the login request and instructed the browser to load a new page.

### After Login
Immediately following the POST request:
- A GET request to `login.php` occurred
- This request returned a 200 OK response
- The page loaded successfully, confirming access to authenticated content

Even though the number of requests stayed low, the flow changed:
- Login involved more than one request
- Authentication was confirmed through redirects and subsequent server behavior, not just the POST response itself

## Observations on a Real-World Website
To better understand how this works on a more complex site, I repeated the same process on my work website.

### Before Login
- Approximately 19 network requests
- Primarily related to loading the sign-in page
- No access to authenticated endpoints

### After Login
- The number of requests increased to 58
- Login involved:
  - A POST request from the client with a 302 Found response
  - One or more follow-up GET requests
  - A request to an internal endpoint (e.g., `Employee`) returned a 200 OK, which appeared to confirm successful authentication

After login, the website began loading additional pages and resources, suggesting that the server now recognized the client as logged in. Navigating to different areas continued to work without re-authenticating, indicating that login state was being maintained across requests.

## Key Takeaways
- Logging in is not a single request, but a sequence of requests and responses
- Authentication is confirmed by server behavior after login, not just the login submission itself
- POST requests are commonly used to send login credentials, followed by redirects
- Minimal websites make authentication flows easier to observe
- Modern websites generate significantly more background traffic, which makes isolating login behavior more difficult
- Comparing before vs after login traffic is the most effective way to understand authentication at the network level

## Reflection
Using a minimal site helped me clearly see the structure of a login flow. When applying the same approach to a real-world website, the process was more complex, but the underlying behavior was similar. This exercise showed why analyzing authentication on modern web applications is challenging and why observing patterns and changes in network traffic is more useful than focusing on individual requests.
