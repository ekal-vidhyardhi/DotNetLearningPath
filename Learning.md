# ASP.NET Core Authentication with JWT and Angular - Part1
https://www.youtube.com/watch?v=vlRqxCpCKGU
## DESCRIPTION:
In this video, we are going to learn how to implement JWT authentication inside the ASP.NET Core Web API project.

▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬
LINKS MENTIONED IN THE VIDEO:
To visit the whole article, mentioned in the video
►► https://code-maze.com/authentication-aspnetcore-jwt-1/

For the Configuration article, you can visit:
►► https://code-maze.com/net-core-web-development-part1/
▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬
VIDEO SUMMARY:
Securing a web application is one of the most important jobs to do and usually one of the hardest things to pull off. That said, in this video, we are going to learn how to implement authentication in ASP.Net Core application using the JSON web tokens. Also, in the next video, we are going to cover the usage of JSON Web Tokens in Angular application consuming our API.

So, as you can see, we are creating a mini-series for this topic.

If you prefer reading about it, and also if you want to download the source code, feel free to visit the article on the Code Maze Blog site. The link is in the description below.

Before we get into the implementation of authentication and authorization, let’s have a quick look at the big picture. There is an application with a login form. A user enters the username, password and presses the login button. After pressing the login button, the application sends di user’s data to the server’s API endpoint.web authentication big picture when the server validates provided credentials and confirms that di user is valid, it’s going to send an encoded JWT to the client. JSON web token is basically a JavaScript object containing some attributes of the logged-in user. It can contain a username, user subject, user roles, or some other useful information.

At the client-side, we store the JWT in the browser’s local storage to remember di user’s login session. We may also use the information from the JWT to enhance the security of our application as well.

Now, let’s talk a bit more about the Json web token.

JSON web tokens enable a secure way to transmit data between two parties in the form of a JSON object. It’s an open standard and it’s a popular mechanism for web authentication. In our case, we are going to use JSON web tokens to securely transfer a user’s data between the client and the server.

JSON web tokens consist of three basic parts: the header, payload, and the signature
# ASP.NET Core Authentication with JWT and Angular - Part2
https://www.youtube.com/watch?v=NSQHiIAP7Z8

## DESCRIPTION:
In this video, we are going to learn how to implement JWT authentication inside the Angular project and also to enable Role-Based authorization with ASP.NET Core and Angular.

▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬
LINKS MENTIONED IN THE VIDEO:
To visit the whole article, mentioned in the video
►► https://code-maze.com/authentication-...
For the previous video visit:
►► https://www.youtube.com/watch?v=vlRqx...
For the CORS article, you can visit:
►► https://code-maze.com/enabling-cors-i...
For the Refresh Token article visit:
►►https://code-maze.com/using-refresh-t...
To visit our site:
►► https://code-maze.com/

▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬
MORE CODE MAZE STUFF?
And you can check out our Merch here:
►► https://www.redbubble.com/people/vpec...

▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬
FOLLOW US ON SOCIAL MEDIA!
►► https://twitter.com/CodeMazeBlog
►► https://www.facebook.com/CodeMazeBlog

▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬
VIDEO SUMMARY:
By default, you can’t send an AJAX request over HTTP to servers on a different origin due to browser’s security concerns. The HTTP protocol is not a secure protocol as it sends the requests in the plain text (at least HTTP v1 does) and anyone can potentially use a web proxy software to intercept modify the request.

On the other hand, the HTTPS protocol is a secure way to transfer information, and some browsers by default allow requests to cross-origin servers on HTTPS.

So, what can we do?

We need to configure the server to receive cross-origin requests. By default, the ASP.NET Core application will reject any request coming from the cross-origin clients. To enable CORS in .NET Core Web API, we need to implement a middleware in the Configure method of the Startup class.

Let’s open the webapplication-start project (you may find it in here) and add the code to the ConfigureServices method to configure the CORS policy.

We have created the Angular starter application (available for download from here) which contains all the necessary code (basic Angular components, the routes, and basic form validation) we need for this post. With this project, it is going to be much easier for us to follow along with this post, because we can focus only on the parts important for the JWT authentication. To find out in detail how to work with Angular, visit our Angular Series.

Let’s download the starter Angular application, so we could easily follow all the coding parts.

To implement the login, we are going to create the login method in the LoginComponent. Inside the login method, we are going to collect the username and the password from the login form. When a user presses the login button, we are going to collect the user’s credentials with the Angular event binding.

Implementing the logout function is very simple. It’s similar to losing the identity card. If we don’t have the card, we are not able to access the secretly protected resources. To log out the user, we are simply going to delete the token stored in the local storage which is the only key to access protected resources.

If we don’t have the token, the server simply doesn’t know our identity and it’s going to reject our calls to the protected resources. To implement log out we are going to create the logout method in the HomeComponent. Inside the logout method, we are going to remove the token from the local storage and that’s all.
Once we have the credentials, we are going to send them to the server via the HTTP POST request to the login endpoint. The server is going to validate the data. If the username and password are valid, the server will issue a JSON web token and send it back to the browser.
