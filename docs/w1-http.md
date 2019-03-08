class: center, middle

# WBMA, Ionic HTTP Client

## 1/2019

---

Study [React crash course](https://www.youtube.com/watch?v=sBws8MSXN7A) from 1:25:55 to 1:38:23

# Fetching data with HTTP Client, Task A

1. Continue last exercise. Create a new branch `http-a` with git and checkout it (`git checkout -b http-a`).
1. Save [test.json](./assets/test.json) into 'public' folder of your project.
1. In App.js, use fetch or axios to load test.json
1. First log the data using `console.log()`
1. Then print the data to the table made in last exercise

---

# Fetching data with HTTP Client, Task B

1. Continue last exercise. Create a new git branch `http-b` and use it.
1. Modify the app so that you fetch the data from the media API instead of test.json
    - [Documentation](http://media.mw.metropolia.fi/wbma/docs/)
    - base url: http://media.mw.metropolia.fi/wbma/
    - Media files location: http://media.mw.metropolia.fi/wbma/uploads/
1. First log the data using ```console.log()```
    - Note that '/media' endpoint doesn't give you thumbnails. You need to do a second request to '/media/:id' to get also thumbnails.
        - Study Promise.all [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all) and [here](http://promise-nuggets.github.io/articles/14-map-in-parallel.html)
        - example: 
        ```javascript
        // 2nd fetch:
        Promise.all(array.map(item => {
            return fetch(url + item.id).
                then(response => {
                  return response.json();
                });
          })).then(items => {
            console.log(items);
            // save items to state
          });
        ```
1. Then print the data to the table