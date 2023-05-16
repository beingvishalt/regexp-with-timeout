# regexp-with-timeout
- This package is created to solve the issue of backtracking in regex.
- There are some package also on npm, but either they reduces performance or they are not for commonjs environment.
- This package is created for commonJs environment.
## Follow below steps to use this package:
#### 1) Install npm package:
 ```javascript
 npm install regexp-with-timeout
 ```
 #### 2) Import this package in your project/file:
```javascript
const regExp = require('regexp-with-timeout')({limit: maxWaitTimeForRegex}); //maxWaitTimeForRegex is time limit to regex
```
#### 3) Wrap calling to test method of this package in try catch block:
```javascript
   let isValidActionStatement = false;
   try {
     isValidActionStatement = await regExp.test(regexInString,flags,string);
   } catch (exception) {
    //write your code in case of regex backtrack (timeout) issue occurs
   }
   //after successful test of regex write your code here
```
## Notes:
- Time limit is in second.
- Default time limit is 1 sec.
- Pass regex to function in the format of string, eg- '[a-z]*'
- Pass flags in the form of string, eg- 'g'.
