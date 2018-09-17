https://s3.amazonaws.com/codecademy-content/projects/4/outbox-2/index.html#/outbox


In the view in the <head> element, include angular-route.js as a <script> element.

<script src="https://code.angularjs.org/1.2.28/angular-route.min.js"></script>



In app.js, define the app's routes:

Use app.config() and $routeProvider to set up the routes.
Use .when() to map the URL /outbox to the controller HomeController and the template views/home.html.
Use .when() to map the URL /outbox/:id to the controller EmailController and the template views/email.html.
Otherwise if a user accidentally visits a URL other than the two above, use .otherwise() to redirect to /outbox.
3.
In the view in the main section, add <div ng-view></div>.

4.
View the result by visiting http://localhost:8000 in the browser:

When you visit /outbox, a view is constructed by injecting views/home.html into the <div ng-view></div> in index.html.
Likewise, when you click on an email, a view is constructed by injecting views/email.html into <div ng-view></div>.
5.
In the view, finish the code to display an email. Looking at the format of the data in the email API, display an email's subject, from, datetime, and message. View the result in the browser.