# Scripting Lesson 4 Demo Starter

Run local development using the following:

```
npm install
npm start
```

## Instructions

### Working with Arrays

1. Build an array of at least four friends.
2. Build an array of at least three numbers.
3. Display the name of the third friend in your list of friends in the console.
4. Add the first and second numbers from your list of numbers and display the result in the console.

### Practice with Built-in Objects

1. Use the String object's `.replace()` method to find the `$` in `price` with ` `. Essentially, we want to strip off the `$` by replacing it with an empty string. Show the result in the console. As a hint, generally, `.replace()` works like this:

```js
// Start with a string
var orig_string = "Hello, world.";
// Use .replace to find a substring 
// and replace it with a second string
// Usually helpful to store the result 
// in a variable to use later
var modified_string = orig_string.replace("e", "aaaaa");
// See the result in the console...
console.log(modified_string); 
// Console shows: Haaaaallo, world.
```

2. Use Math's `.floor()` method to round `num` down to the nearest integer. Show the result in the console.

3. Use Number's `.toFixed()` method to format `price` so that it has two `0`'s after the decimal. Show the result in the console.

### Working with Objects

1. Create an object that describes a movie you watched recently including at least three properties.
2. Create an object that describes a product you recently obtained that includes at least two properties and a method. The method doesn't have to have any code in it but should represent some action or process the product can complete.

### Classes of objects

1. Copy and paste the following directly inside the `<script>` tag above the DRE:

```js
function Book(title, author, year_published) {
  
  // Properties
  this.title = title;
  this.author = author;
  this.year_published = year_published;
  this.checked_out = false;
  this.checked_out_to = '';
  
  // Methods
  this.check_out = function(person_name) {
    this.checked_out = true;
    this.checked_out_to = person_name;
    console.log(this.title + " is now checked out to " + this.checked_out_to + ".");
  };
  this.check_in = function() {
    var returned_by = this.checked_out_to;
    this.checked_out = false;
    this.checked_out_to = '';
    console.log(returned_by + " just returned " + this.title + ".");
  };
  
}
```

2. Inside the DRE create three instances of Book, with data for a book you own, and assigning each to a different variable.

3. Display some information about one of the books in the console such as: 

    `[bookTitle] was published in [year_published].`

4. Check one out to your friend Sam. Check another out to your friend Jess. Then check in the one Sam checked out.


### Arrays and objects together

1. Add this property to the list of properties for the Book class:

    ```js
    this.previously_checked_out_to = [];
    ```

    ...and add the following line at the beginning of the definition for the `.check_in()` method:

    ```js
   this.previously_checked_out_to.push(this.checked_out_to);
    ```
2. Check out `book` to one of your friends then check it back in. Repeat this for two more friends. Then log the value of the `previously_checked_out_to` property to the console.

3. Create a new variable, `library` and use it to store `book` and two other new instances of Book. Show the value of `library` in the console.

4. Log the `.length()` of `library` in the console.