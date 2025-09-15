# Vite PWA plugin

---

### Some terminology

**Authentication:**

Authentication is the process of verifying the identity of a user, system, or entity attempting to access a web
application or API. It answers the question, "Who are you?" and ensures that the entity trying to access the system is
who they claim to be. Here are some common authentication methods:

1. **Username and Password:** This is the most traditional form of authentication, where users provide a username and a
   secret password to prove their identity. However, it can be susceptible to security risks like password leaks and
   brute force attacks.

2. **Multi-Factor Authentication (MFA):** MFA adds an extra layer of security by requiring users to provide multiple
   forms of identification, such as a password and a one-time code sent to their mobile device.

3. **OAuth and OpenID Connect:** These are popular authentication protocols used for single sign-on (SSO) and user
   authentication in modern web applications. They allow users to log in using their existing accounts on platforms like
   Google, Facebook, or Microsoft.

**Authorization:**

Authorization is the process of determining what actions a user or entity is allowed to perform within a web application
or API after they have been authenticated. It answers the question, "What are you allowed to do?" Authorization ensures
that users only have access to the resources and functionalities they are permitted to use. Common authorization methods
include:

1. **Role-Based Access Control (RBAC):** RBAC assigns specific roles (e.g., admin, user, guest) to users, and these
   roles determine what actions they can take within the application or API.

2. **Attribute-Based Access Control (ABAC):** ABAC evaluates user attributes, environmental factors, and policies to
   make dynamic access control decisions. For example, it might allow a user to access certain data only if they are in
   a specific location.

3. **Token-Based Access:** In REST APIs, tokens (such as JSON Web Tokens or JWTs) are often used for authorization. A
   user receives a token upon successful authentication, and this token contains information about their permissions and
   access rights.

Authentication verifies the identity of users or entities, while authorization determines what actions they
are allowed to perform once authenticated. These two security measures work together to protect web applications and
REST APIs from unauthorized access and ensure the security and privacy of data and resources.

---

**Handling Different Content Types in Web Apps**

Content types refer to the format and structure in which data is sent and received between a client (such as a web browser) and a server (where your web application or API resides). Two common content types you'll frequently encounter are form data and JSON payloads.

**Handling Form Data:**

1. **HTML Forms:** In web applications, HTML forms are commonly used to collect user input. When a user submits a form, the data is typically sent to the server using the HTTP GET or POST method. Server-side code (e.g., PHP, Python, or Node.js) processes the form data and responds accordingly.

2. **Content-Type: application/x-www-form-urlencoded:** This is a common content type for form data submissions. Data is sent as key-value pairs in the request body, with each pair separated by an ampersand (&). Servers can parse this data to access user input:
   ```text
   https://example.com/search?title=The+Great+Gatsby&author=F.+Scott+Fitzgerald
   ```
   - https://example.com/search is the base URL of the search page. 
   - ? indicates the start of the query string. ¨
   - title=The+Great+Gatsby is a parameter where title is the key, and The+Great+Gatsby is the value. The + character is used to represent spaces in URL-encoded strings. 
   - & separates multiple parameters. 
   - author=F.+Scott+Fitzgerald is another parameter for the author. 
   - On the server-side, you can extract and process these parameters to perform the book search using the values provided in the query string.


**Handling JSON Payloads:**

1. **Content-Type: application/json:** When sending JSON data, the Content-Type header is set to "application/json." Servers must be configured to parse JSON data from incoming requests and validate it accordingly.

---

### localStorage

`localStorage` is a client-side storage mechanism that allows you to store key-value pairs in a web browser. It manages and persists data on the user's device, enabling a better user experience and improving the performance of web applications.

**Key Concepts of `localStorage`:**

1. **Client-Side Storage:** Unlike server-side storage, which involves storing data on a web server, `localStorage` operates on the user's device (typically in the web browser). This means that data stored in `localStorage` is available even after the user closes their browser or navigates away from the website.

2. **Key-Value Pairs:** `localStorage` stores data in the form of key-value pairs, similar to a dictionary or associative array. Each piece of data (value) is associated with a unique key that you can use to retrieve it.

3. **Data Size Limitations:** While `localStorage` is a useful tool, it's important to note that it has size limitations, typically around 5-10 MB per domain, depending on the browser. This makes it suitable for storing relatively small amounts of data, such as user preferences or cached data.

**Basic `localStorage` Usage:**

```javascript
// Storing data in localStorage
localStorage.setItem('username', 'JohnDoe');

// Retrieving data from localStorage
const username = localStorage.getItem('username');

// Removing data from localStorage
localStorage.removeItem('username');
```

---

## Assignment

The goal is to make a simple PWA app where you can log in to the Restaurant App and upload an avatar and change your
email.

1. Use [Postman](https://www.postman.com/downloads/) to create an account to the [Restaurant API](https://media1.edu.metropolia.fi/restaurant/#api-User-CreateUser)
   - Copy the ethereal url from the response (`https://ethereal.email/message/XXYYZZ`) to your browser to activate the account.
2. Use Postman to test that your account works. Try to [update userdata](https://media1.edu.metropolia.fi/restaurant/#api-User-UpdateCurrentUser) and [upload an avatar](https://media1.edu.metropolia.fi/restaurant/#api-User-UploadAvatar) for the user.
3. [Download the starter files](https://github.com/ilkkamtk/vite-pwa-starter) and fill in the TODO:s in the .ts-files
4. App should be able to log in a user, update userdata and upload avatar image.
5. When the app works, add [Vite PWA Plugin](https://vite-pwa-org.netlify.app/) to add PWA functionality.
   - Follow the [getting started guide](https://vite-pwa-org.netlify.app/guide/) to add basic PWA functionality
   - Example webmanifest is in the `public/icons` folder

