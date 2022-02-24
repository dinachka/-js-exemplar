# -js-exemplar
# JS Developer Coding Exemplar

## Instructions
This coding exemplar is designed to highlight your skills and areas of expertise with the JS language in general. 

Please complete the following questions to the best of your ability. If you are unable to solve a question, please indicate as such. You should feel free to use any online resources to solve these questions; after all, we expect that our developers will use their problem-solving skills at work! Some questions are intended to be difficult, while others are meant to be easy or obvious. Please post your answers in a Gist, using Markdown format, and send the link for review.

This exercise should take approximately one hour to complete.

Good luck!

## Question 1
You've been tasked with identifying a string that contains the word "superman" (case insensitive). You've written the following code:
```js
function validateString(str) {
    if (!str.toLowerCase().indexOf('superman')) {
        throw new Error('String does not contain superman');
    }    
}
```

QA has come to you and said that this works great for strings like "I love superman", but an exception is generated for strings like "Superman is awesome!", which should not happen. Explain why this occurs, and show how you would solve this issue (you must use `indexOf()` in your answer).

## Question 2
You're given a sorted index array that contains no keys. The array contains only integers, and your task is to identify whether or not the integer you're looking for is in the array. Write a function that searches for the integer and returns true or false based on whether the integer is present. Describe how you arrived at your solution.

## Question 3
Write a function that takes a phone number in any form and formats it using a delimiter supplied by the developer. The delimiter is optional; if one is not supplied, use a dash (-). Your function should accept a phone number in any format (e.g. 123-456-7890, (123) 456-7890, 1234567890, etc) and format it according to the 3-3-4 US block standard, using the delimiter specified. Assume foreign phone numbers and country codes are out of scope.

*Note:* This question CAN be solved using a regular expression, but one is not REQUIRED as a solution. Focus instead on cleanliness and effectiveness of the code, and take into account phone numbers that may not pass a sanity check.

## Question 4
Write a complete set of unit tests for the following code:

```js

function fizzBuzz(start = 1, stop = 100)
{
    let result = '';
    
    if (stop < start || start < 0 || stop < 0) {
        throw new Error('Invalid arguments');
    }
    
    for (let i = start; i <= stop; i++) {
        if (i % 3 === 0 && i % 5 === 0) {
            result += 'FizzBuzz';
            continue;
        }
        
        if (i % 3 === 0) {
            result += 'Fizz';
            continue;
        }
        
        if (i % 5 === 0) {
            result += 'Buzz';
            continue;
        }
        
        result += i;
    }
    
    return result;
}
```

## Question 5
I have an array of file names:

```js
const files = [
    '/src/common/api.js',
    '/src/common/preferences.js',
    '/src/styles/main.css',
    '/src/styles/base/_base.scss',
    '/src/assets/apple-touch-icon-57.png',
];
```

Below is a mixed list of specific file names, as well as file paths, that should be excluded. For example, ALL files under a file path should be excluded, but if the value is an actual file name, only that specific file should be excluded. 

```js
const exclude = [
    '/src/styles/',
    '/src/assets/apple-touch-icon-57.png',
];
```

For example, you'll want to exclude the styles directory (and all files in it), but ONLY the `apple-touch-icon-57.png` file.

Devise a method for applying the exclusion list against the file list WITHOUT nested `forEach()` loops.


## Question 6

There are two tables in Postgres database:
user(id integer, email varchar(256), first_name varchar(256), last_name varchar(256));
payment(id integer, user_id integer, amount integer, successful boolean, created_at timestamp with time zone);

Write database queries:
1. to select emails for users, which have successful payments
2. to select emails for users, which have only unsuccessful payments
3. to select count and sum of successful payments for each user
4. to select last(by creation date) 5 payments for each user

What constraints need these tables for data consistency?

## Question 7

There is array of objects

```js
const queryResult = [
  { userId: 1, firstName: 'john', lastName: 'doe', bookId: 1, bookTitle: 'don quixote'},
  { userId: 1, firstName: 'john', lastName: 'doe', bookId: 3, bookTitle: 'robinson crusoe'},
  { userId: 1, firstName: 'john', lastName: 'doe', bookId: 4, bookTitle: 'gulliver\'s travels'},
  { userId: 1, firstName: 'john', lastName: 'doe', bookId: 5, bookTitle: 'frankenstein'},
  { userId: 1, firstName: 'john', lastName: 'doe', bookId: 6, bookTitle: 'the count of monte cristo'},

  { userId: 2, firstName: 'richard', lastName: 'roe', bookId: 2, bookTitle: 'pilgrim\'s progress'},
  { userId: 2, firstName: 'richard', lastName: 'roe', bookId: 6, bookTitle: 'the count of monte cristo'},


  { userId: 3, firstName: 'john', lastName: 'smith', bookId: 1, bookTitle: 'don quixote'},
  { userId: 3, firstName: 'john', lastName: 'smith', bookId: 2, bookTitle: 'pilgrim\'s progress'},
  { userId: 3, firstName: 'john', lastName: 'smith', bookId: 5, bookTitle: 'frankenstein'},
  { userId: 3, firstName: 'john', lastName: 'smith', bookId: 7, bookTitle: 'jane eyre'},
];
```

How to map it to
```js
const mappedResult = [{
  id: 1,
  firstName: "John",
  lastName: "Doe",
  books: [
      {
        id: 1,
        title: "Don Quixote"
      },
      {
        id: 3,
        title: "Robinson Crusoe"
      },
      {
        id: 4,
        title: "Gulliver's Travels"
      },
      {
        id: 5,
        title: "Frankenstein"
      },
      {
        id: 6,
        title: "The Count Of Monte Cristo"
      }
    ]
}, {
    id: 2,
    firstName: "Richard",
    lastName: "Roe",
    books: [
      {
        id: 2,
        title: "Pilgrim's Progress"
      },
      {
        id: 6,
        title: "The Count Of Monte Cristo"
      }
    ]
}, {
  id: 3,
  firstName: "John",
  lastName: "Smith",
  books: [
      {
        id: 1,
        title: "Don Quixote"
      },
      {
        id: 2,
        title: "Pilgrim's Progress"
      },
      {
        id: 5,
        title: "Frankenstein"
      },
      {
        id: 7,
        title: "Jane Eyre"
      }
    ]
}];
```
?
Notice: You can use lodash in this task.

## Question 8

Write a function that determines if a given argument is array-like, in the sense that it is iterable.

```js
isIterable(null); // false
isIterable('hello world'); // true
isIterable(document.querySelectorAll('.error-message')); // true
```
