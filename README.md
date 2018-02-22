# Date-Finder
Compatibility-based "DateFinder" application survey with 10 questions. Each answer is on a scale of 1 to 5 based on how much the user agrees or disagrees with a question.

![Screenshot](burger.png)

### Prerequisites

```
npm install express
npm install path
npm install body-parser
```

### htmlRoutes.js

Includes: 
   * A GET Route to `/survey` which should display the survey page.
   * A default, catch-all route that leads to `home.html` which displays the home page. 

### apiRoutes.js

Includes: 
   * A GET route with the url `/api/friends`. This will be used to display a JSON of all possible friends.
   * A POST routes `/api/friends`. This will be used to handle incoming survey results. This route will also be used to handle the compatibility logic. 
   
### dates.js

- Contains an array of objects containing the possible matches

## Function

- The app determine the user's most compatible friend using the following as a guide: 
      
     * Convert each user's results into a simple array of numbers (ex: `[5, 1, 4, 4, 5, 1, 2, 5, 4, 1]`).
     * With that done, compare the difference between current user's scores against those from other users, question by question. Add          up the differences to calculate the `totalDifference`.
     * Example: 
        * User 1: `[5, 1, 4, 4, 5, 1, 2, 5, 4, 1]`
        * User 2: `[3, 2, 6, 4, 5, 1, 2, 5, 4, 1]`
        * Total Difference: **2 + 1 + 2 =** **_5_**
        * Remember to use the absolute value of the differences. Put another way: no negative solutions! Your app should calculate both           `5-3` and `3-5` as `2`, and so on. 
        * The closest match will be the user with the least amount of difference.

- display the result as a modal pop-up.

## Built With

* [VSCode](http://www.dropwizard.io/1.0.2/docs/) - Code Editor
* [Node](https://nodejs.org/en/) - Application runtime environment that allows you to write server-side applications in JavaScript
* [MySQL](https://www.mysql.com/products/workbench/) - Back-End Database
* [Express](https://expressjs.com/) - Node.js framework
* [Handlebars](https://handlebarsjs.com/) - Semantic Templating

## Authors

* **Christopher Bermudez** - *Homework From* - 2017-2018 UCF Coding Bootcamp

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
