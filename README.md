# Indeed Scraper

### What is it?
- API that allows flexible job searching.
- Uses Node.js for server-side operations.
- Uses Promises to handle asynchronous control flow.

### Why use it?
- Allows your web app to get job posting data from Indeed.
- You don't have to deal with Indeed's cluttered interface.

### How to use it?
```javascript
// Require our module.
var IndeedService = require('../indeed-service.js')();

// Get initial Indeed data using IndeedService.query().
IndeedService.query('Javascript', 'Toronto', '100')
.then(function(data) {
    // Do something with data ...
    console.log(data.jobList);

})
.catch(function(err) {
    console.log('Error: ' + err);
});
```

### What does the data look like?
Look at the table to see the different kinds of data available.
| name | datatype | description |
|------|----------|-------------|
| salaryList | array | List of links to job searches sorted by salary ($50,000+, $70,000+, etc.) |
| jobTypeList | array | " " " sorted by job type (SALARY, CONTRACT, HOURLY, etc.)|
| locationList | array | " " " sorted by location (Toronto, Newmarket, Richmond Hill, etc.) |
| companyList | array | " " " sorted by company |
| titleList | array | " " " sorted by job title (Senior Web Developer, Junior Dev, C Developer, etc.) |
| jobList | array | List of all main job postings [JSON format] |

`jobList` is a list of objects. Here is a table of what is available in each object.
| name | datatype | description |
|------|----------|-------------|
| href | string | A complete URL to the Canadian job posting |
| isSponsored | boolean | Indicates whether the posting is Sponsored. Sponsored ads are seen first/last |
| companyName | string | Company name of job posting |
| location | string | Geographical location of job |
| salary | string | Indicates salary/hourly wage |
| summary | string | Short summary of the job posting |
