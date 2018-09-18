https://s3.amazonaws.com/codecademy-content/projects/4/reader/index.html#/books

1.
In the view inside the <head> element, include angular-route.js as a new <script> element.

2.
In app.js, inject ngRoute into the module's dependency array so that routing is available for the app to use.

3.
In app.js, define the app's routes:

Use app.config() and $routeProvider to set up the routes.
Map the URL /books to the controller BookshelfController and the template views/bookshelf.html.
Otherwise, redirect to /books.
4.
Create a service named books for getting data from the books API. Create the service in a new file named js/services/books.js. Include this new JavaScript file in the view as a script element.

The books API is a JSON object containing an array of books. Here's how a single book is represented in this array:
{ "title": "Metamorphosis", "cover": "img/metamorphosis.jpg", "author": "Franz Kafka", "description": "Gregor Samsa turns into a large insect-like creature.", "chapters": [ { "title": "I", "paragraphs": ["paragraph 1", "paragraph 2"] }, { "title": "II", "paragraphs": ["paragraph 1", "paragraph 2", "paragraph 3", "paragraph 4"] }, { "title": "III", "paragraphs": ["paragraph 1", "paragraph 2", "paragraph 3"] } ] }
Each book has a title, cover, author, description, and array of chapters. Each chapter has a title and array of paragraphs.

5.
Set up the controller BookshelfController and the template views/bookshelf.html:

In the controller BookshelfController, use the books service to load data from the server into the $scope.myBooks.
Finish the template views/bookshelf.html so that it displays each book.
Notice in views/bookshelf.html, we're using <a href="#/books/{{ $index }}"> to create a URL for each book. The $index gives the index of a book in the myBooks array. This means the URL of the first book is #/books/0, the URL of the second book is #/books/1, and so forth.
6.
In the view in the main section, add <div ng-view></div>.

7.
View the result by visiting http://localhost:8000 in the browser. When you visit /books, a view is constructed by injecting views/bookshelf.html into the <div ng-view></div> in index.html.

8.
When a user clicks on a book, she should go to the book's description. Let's set this up next, following the same sequence of steps from above:

In app.js, add another route. Map the URL /books/:bookId to the controller BookController and the template views/book.html.
In BookController, use the books service to load a single book into the $scope.book property. To do this, use the books service to fetch an array of books from the server, and then use $routeParams.bookId to access the specific book by its index. Store the specific book into $scope.book.
Remember we can use Angular's $routeParams to retrieve bookId from the URL by using $routeParams.bookId.
Finish the template in views/book.html to display a book's description. Looking at the format of the data in books API given above, display a book's cover, title, author, and description.
View the result in the browser. When you click on a book, a view is constructed by injecting views/book.html into the <div ng-view></div> in index.html.
9.
When a user clicks on the Read button, she should go to the book's first chapter. From there, she can use the Next and Back buttons to read the book. Let's set this up next, following the same sequence of steps from above:

In app.js, add another route. Map the URL /books/:bookId/chapters/:chapterId to the controller ChapterController and the template views/chapter.html.
In ChapterController, use the books service to load a single chapter into the $scope.chapter property. To do this, in line 4 first get a specific book from the books API by using its index, just as you did in BookController. Store the specific book into $scope.book.
Under it, access the array of chapters inside $scope.book, and get a specific chapter in the array by using its index $routeParams.chapterId. Store the specific chapter into $scope.chapter.
Finish the template in views/chapter.html to display a chapter. Looking at the format of the data in books API given above, display the book title, book author, chapter title, and chapter paragraphs.
View the result in the browser. When you click on the Read button, a view is constructed by injecting views/chapter.html into the <div ng-view></div> in index.html. When you click on the Next and Back buttons, you navigate from chapter to chapter.


https://www.youtube.com/watch?v=vvPPo6nyWvo