Top 10 is creating an AngularJS app to chart popular TV shows. 

https://s3.amazonaws.com/codecademy-content/projects/4/top-10/index.html

Create a new module named Top10App, and then attach it to the <body> element.


Visit shows.json. It's a JSON object containing an array of TV shows. Let's fetch this data and display it in the app.

Create a service named shows for getting this data. In a file named js/services/shows.js, create a new service named shows that gets data from the shows API. Include this new JavaScript file in the view as a new script element.


In the controller, use the shows service to load data from the server into the $scope.shows property. Then attach the controller to the <div class="main"> element.

Create a directive named tvShow:

Make a new file js/directives/tvShow.js. In it, create the new directive named tvShow.
Use scope to specify that we'll pass information into this directive through an attribute named info.
Use templateUrl to tell this directive to use the js/directives/tvShow.html file.

Include this new JavaScript file in the view as a <script> element.

In the directive's template js/directives/tvShow.html, display each TV show's details. Looking at the format of the data in the shows API, display each show's series_img, series, genre, run_start, and description.

Finish the view display each item in the shows array. Under the .rank div, use the <tv-show> directive to display the details of each show. Pass in each show into the <tv-show> directive's info element.