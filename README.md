<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h1>JS-1Liners-JS</h1>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>JavaScript 1 Liners worth noting</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="1">1. Convert Celsius to Fahrenheit</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>celsiusToFahrenheit allows you to convert a temperature from Celsius to Fahrenheit. 
It takes a value in Celsius as input and uses the formula (Celsius * 9/5) + 32 to 
perform the conversion.exadecimal representation.</p>
<pre>
const celsiusToFahrenheit = (celsius) => (celsius * 9/5) + 32;

celsiusToFahrenheit(30); // Result: 86
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="2">2. Get Value of a browser Cookie</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Retrieve the value of a cookie by accessing with document.cookie.</p>
<pre>
const cookie = name => `; ${document.cookie}`.split(`; ${name}=`).pop().split(';').shift(); 

cookie('_ga');  // Result: "GA1.2.1929736587.1601974046" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="3">3. Convert RGB to Hex</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>rgbToHex enables you to convert RGB (Red, Green, Blue) values to their corresponding 
hexadecimal representation.</p>
<pre>
const rgbToHex = (r, g, b) => 
  "#" + ((1 << 24) + (r << 16) + (g << 8) + b).toString(16).slice(1); 

rgbToHex(0, 51, 255);  // Result: #0033ff 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="5">4. Copy to Clipboard</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Easily copy any text to clipboard using navigator.clipboard.writeText.</p>
<pre>
const copyToClipboard = (text) => navigator.clipboard.writeText(text); 

copyToClipboard("Hello World"); 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="5">5. Check if Date is Valid</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Use the following snippet to check if a given date is valid or not.</p>
<pre>
const isDateValid = (...val) => !Number.isNaN(new Date(...val).valueOf()); 
isDateValid("December 17, 1995 03:24:00");  // Result: true 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="6">6. Find the day of year</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find which is the day by a given date.</p>
<pre>
const dayOfYear = (date) => 
  Math.floor((date - new Date(date.getFullYear(), 0, 0)) / 1000 / 60 / 60 / 24); 

dayOfYear(new Date()); // Result: 272
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="7">7. Capitalize a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Javascript doesn't have an inbuilt capitalize function, so we can use the following 
code for the purpose.</p>
<pre>
const capitalize = str => str.charAt(0).toUpperCase() + str.slice(1) 

capitalize("follow for more")  // Result: Follow for more 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="8">8. Find the number of days between two days</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the days between 2 given days using the following snippet.</p>
<pre>
const dayDif = (date1, date2) => Math.ceil(Math.abs(date1.getTime() - date2.getTime()) / 86400000) 

dayDif(new Date("2020-10-21"), new Date("2021-10-22"))  // Result: 366 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="9">9. Clear All Cookies</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>You can easily clear all cookies stored in a web page by accessing the cookie using 
document.cookie and clearing it.</p>
<pre>
const clearCookies = document.cookie.split(';').forEach(cookie => 
  document.cookie = cookie.replace(/^ +/, '').replace(/=.*/, 
  `=;expires=${new Date(0).toUTCString()};path=/`)); 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="10">10. Generate Random Hex</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>You can generate random hex colors with Math.random and padEnd properties.</p>
<pre>
const randomHex = () => `#${Math.floor(Math.random() * 0xffffff).toString(16).padEnd(6, "0")}`; 

console.log(randomHex());  // Result: #92b008 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="11">11. Get Query Params from URL</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>You can easily retrieve query params from a url either by passing window.location or 
the raw URL goole.com?search=easy&page=3.</p>
<pre>
const getParameters = (URL) => { 
  URL = JSON.parse('{"' + decodeURI(URL.split("?")[1]).replace(/"/g, '\\"').replace(/&/g, '","').replace(/=/g, '":"') +'"}');
  return JSON.stringify(URL); 
}; 

getParameters(window.location)  // Result: { search : "easy", page : 3 } 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="12">12. Log Time from Date</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>We can log time, in the format hour::minutes::seconds from a given date.</p>
<pre>
const timeFromDate = date => date.toTimeString().slice(0, 8); 

console.log(timeFromDate(new Date(2021, 0, 10, 17, 30, 0)));  // Result: "17:30:00" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="13">13. Check if a number is even or odd</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>A simple JavaScript function named "isEven" determines if a number is even or odd. It 
takes a "num" as input and returns true if even, false if odd.</p>
<pre>
const isEven = num => num % 2 === 0; 

console.log(isEven(2));  // Result: True 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="14">14. Find Average of Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the average between multiple numbers using reduce method.</p>
<pre>
const average = (...args) => args.reduce((a, b) => a + b) / args.length; 

average(1, 2, 3, 4);  // Result: 2.5 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="15">15. Scroll to Top</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>You can use window.scrollTo(0, 0) method to automatic scroll to top. Set both x and y as 0.</p>
<pre>
const goToTop = () => window.scrollTo(0, 0); 

goToTop(); 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="16">16. Reverse a string</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>You can easily reverse a string using split, reverse and join methods.</p>
<pre>
const reverse = str => str.split('').reverse().join(''); 

reverse('hello world');  // Result: 'dlrow olleh' 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="17">17. Check if array is empty</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>You can check if an array if empty with this snippet.</p>
<pre>
const isNotEmpty = arr => Array.isArray(arr) && arr.length > 0; 

isNotEmpty([1, 2, 3]);  // Result: true 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="18">18. Get Selected Text</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Get the text the user has select using inbuilt getSelection property.</p>
<pre>
const getSelectedText = () => window.getSelection().toString(); 

getSelectedText(); 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="19">19. Shuffle an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Shuffling an array is super easy with sort and random methods.</p>
<pre>
const shuffleArray = (arr) => arr.sort(() => 0.5 - Math.random()); 

console.log(shuffleArray([1, 2, 3, 4]));  // Result: [ 1, 4, 3, 2 ] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="20">20. Detect Dark Mode</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a user's device is in dark mode with the following code.</p>
<pre>
const isDarkMode = window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches 

console.log(isDarkMode) // Result: True or False 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="21">21. Remove Duplicated from Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>You can easily remove duplicates with Set in JavaScript. Its a life saver.</p>
<pre>
const removeDuplicates = (arr) => [...new Set(arr)]; 

console.log(removeDuplicates([1, 2, 3, 3, 4, 4, 5, 5, 6]));  // Result: [ 1, 2, 3, 4, 5, 6 ]
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="22">22. Get the Length of a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>getLength efficiently calculates the length of a given string using .length property.</p>
<pre>
const getLength = (str) => str.length; 

getLength("Hello, world!");  // Result: 13 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="23">23. Calculate the Area of a Circle</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the area of a circle given its radius.</p>
<pre>
const calculateCircleArea = (radius) => Math.PI * Math.pow(radius, 2); 

calculateCircleArea(5);  // Result: 78.53981633974483 
</pre>

<h4 id="24">24. Check if a Number is Prime</h4>
<p>Determine if a given number is a prime number.</p>
<pre>
const isPrime = (num) => { 
  if (num <= 1) return false; 
  for (let i = 2; i <= Math.sqrt(num); i++) { 
    if (num % i === 0) return false; 
  } 
  return true; 
}; 

isPrime(13);  // Result: true
</pre>

<h4 id="25">25. Count Occurrences of a Character in a String</h4>
<pre>
Count the occurrences of a specific character in a given string. 
const countOccurrences = (str, char) => str.split(char).length - 1; 

countOccurrences("banana", "a");  // Result: 3
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="26">26. Remove Leading and Trailing Whitespaces</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Remove leading and trailing whitespaces from a given string.</p>
<pre>
const removeWhitespaces = (str) => str.trim(); 

removeWhitespaces(" Hello, world! ");  // Result: "Hello, world!"
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="27">27. Generate a Random Number within a Range</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Generate a random integer within a specified range.</p>
<pre>
const randomInRange = (min, max) => Math.floor(Math.random() * (max - min + 1)) + min; 

randomInRange(1, 10);  // Result: Random number between 1 and 10 (inclusive)
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="28">28. Convert Seconds to HH:MM:SS Format</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Convert a given number of seconds into the "hours:minutes:seconds" format.</p>
<pre>
const secondsToHHMMSS = (seconds) => { 
  const pad = (num) => String(num).padStart(2, '0'); 
  const hours = Math.floor(seconds / 3600); 
  const minutes = Math.floor((seconds % 3600) / 60); 
  const secs = seconds % 60;
  return `${pad(hours)}:${pad(minutes)}:${pad(secs)}`; 
}; 

secondsToHHMMSS(3660);  // Result: "01:01:00"
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="29">29. Get the Last Element of an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Retrieve the last element of a given array.</p>
<pre>
const getLastElement = (arr) => arr[arr.length - 1]; 

getLastElement([1, 2, 3, 4]);  // Result: 4 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="30">30. Sort an Array of Numbers in Ascending Order</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Sort a given array of numbers in ascending order.</p>
<pre>
const sortAscending = (arr) => arr.slice().sort((a, b) => a - b); 

sortAscending([3, 1, 4, 1, 5, 9, 2, 6, 5, 3]);  // Result: [1, 1, 2, 3, 3, 4, 5, 5, 6, 9]
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="31">31. Check if a String is Palindrome</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Determine if a given string is a palindrome.</p>
<pre>
const isPalindrome = (str) => str === str.split('').reverse().join(''); 

isPalindrome("level");  // Result: true
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="32">32. Calculate Factorial of a Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the factorial of a given number.</p>
<pre>
const factorial = (num) => { 
  if (num === 0 || num === 1) return 1; 
  return num * factorial(num - 1); 
}; 

factorial(5);  // Result: 120
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="33">33. Sum all Numbers in an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the sum of all numbers in a given array.</p>
<pre>
const sumArray = (arr) => arr.reduce((acc, val) => acc + val, 0);

sumArray([1, 2, 3, 4, 5]);  // Result: 15
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="34">34. Find the Maximum Value in an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the maximum value in a given array of numbers.</p>
<pre>
const findMax = (arr) => Math.max(...arr); 

findMax([10, 5, 8, 20, 3]);  // Result: 20
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="35">35. Get the Current Date in DD/MM/YYYY Format</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Get the current date in the "DD/MM/YYYY" format.</p>
<pre>
const getCurrentDate = () => { 
  const date = new Date(); 
  const day = String(date.getDate()).padStart(2, '0'); 
  const month = String(date.getMonth() + 1).padStart(2, '0'); 
  const year = date.getFullYear(); 
  return `${day}/${month}/${year}`; 
}; 

getCurrentDate();  // Result: "02/08/2023"
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="36">36. Calculate the Power of a Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the result of raising a given base to a specified exponent.</p>
<pre>
const power = (base, exponent) => Math.pow(base, exponent); 

power(2, 5);  // Result: 32
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="37">37. Convert String to Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Convert a given string to a numeric value (float or integer).</p>
<pre>
const stringToNumber = (str) => parseFloat(str); 

stringToNumber("3.14");  // Result: 3.14
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="38">38. Find the First N Fibonacci Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Generate the first N Fibonacci numbers.</p>
<pre>
const fibonacci = (n) => { 
  const result = [0, 1]; 
  for (let i = 2; i < n; i++) { 
    result.push(result[i - 1] + result[i - 2]); 
  } 
  return result; 
}; 

fibonacci(8);  // Result: [0, 1, 1, 2, 3, 5, 8, 13]
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="39">39. Count the Number of Words in a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Count the number of words in a given string.</p>
<pre>
const countWords = (str) => str.trim().split(/\s+/).length;

console.log(countWords("Hello world, how are you?"));  // Output: 5
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="40">40. Reverse an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Reverse the elements of a given array.</p>
<pre>
const reverseArray = (arr) => arr.slice().reverse(); 

console.log(reverseArray([1, 2, 3, 4, 5]));  // Output: [5, 4, 3, 2, 1] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="41">41. Get the Current Year</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Get the current year.</p>
<pre>
const currentYear = () => new Date().getFullYear();

console.log(currentYear());  // Output: 2023 (depending on the current year)
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="42">42. Generate a Random Number between 1 and 10</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Generate a random integer between 1 and 10 (inclusive).</p>
<pre>
const random1To10 = () => Math.floor(Math.random() * 10) + 1;

console.log(random1To10());  // Output: Random number between 1 and 10 (inclusive)
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="43">43. Check if a String is Empty</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given string is empty (contains no characters).</p>
<pre>
const isEmptyString = (str) => str.trim().length === 0;

console.log(isEmptyString(""));  // Output: true
console.log(isEmptyString("Hello, world!"));  // Output: false
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="44">44. Check if an Object has a Specific Property</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if an object contains a specific property.</p>
<pre>
const hasProperty = (obj, prop) => prop in obj;
const person = { name: "John", age: 30 };

console.log(hasProperty(person, "name"));  // Output: true
console.log(hasProperty(person, "gender")); // Output: false
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="45">45. Calculate the Average of Numbers in an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the average of numbers in a given array.</p>
<pre>
const average = (arr) => arr.reduce((acc, val) => acc + val, 0) / arr.length;

console.log(average([1, 2, 3, 4, 5]));  // Output: 3
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="46">46. Check if a Number is a Multiple of 5</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a multiple of 5.</p>
<pre>
const isMultipleOf5 = (num) => num % 5 === 0;

console.log(isMultipleOf5(10));  // Output: true
console.log(isMultipleOf5(7));  // Output: false
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="47">47. Convert Minutes to Seconds</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Convert minutes to seconds.</p>
<pre>
const minsToSecs = (mins) => mins * 60;

console.log(minsToSecs(5));  // Output: 300
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="48">48. Find the Maximum Value in an Array of Objects</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the maximum value of a specific property in an array of objects.</p>
<pre>
const findMaxValue = (arr, key) => Math.max(...arr.map(item => item[key]));

const students = [
  { name: "Alice", score: 80 },
  { name: "Bob", score: 95 },
  { name: "Charlie", score: 70 }
];

console.log(findMaxValue(students, "score"));  // Output: 95
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="49">49. Check if a String starts with a specific character</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given string starts with a specific character.</p>
<pre>
const startsWithChar = (str, char) => str.startsWith(char);

console.log(startsWithChar("Hello, world!", "H"));  // Output: true
console.log(startsWithChar("Hello, world!", "h"));  // Output: false
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="50">50. Convert a String to Title Case</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Convert a given string to title case (capitalize the first letter of each word).</p>
<pre>
const toTitleCase = (str) => str.replace(/\b\w/g, match => match.toUpperCase());

console.log(toTitleCase("hello world"));  // Output: "Hello World"
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="51">51. Check if an Array contains a specific value</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given array contains a specific value.</p>
<pre>
const containsValue = (arr, value) => arr.includes(value);

console.log(containsValue([1, 2, 3, 4, 5], 3));  // Output: true
console.log(containsValue([1, 2, 3, 4, 5], 6));  // Output: false
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="52">52. Convert an Array to a Comma-separated String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Convert a given array to a comma-separated string.</p>
<pre>
const arrayToCSV = (arr) => arr.join(', ');

console.log(arrayToCSV([1, 2, 3, 4, 5]));  // Output: "1, 2, 3, 4, 5"
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="53">53. Check if a Year is a Leap Year</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given year is a leap year.</p>
<pre>
const isLeapYear = (year) => (year % 4 === 0 && year % 100 !== 0) || (year % 400 === 0);

console.log(isLeapYear(2024));  // Output: true
console.log(isLeapYear(2023));  // Output: false
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="54">54. Find the Index of an Element in an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the index of a specific element in a given array.</p>
<pre>
const findIndex = (arr, element) => arr.indexOf(element);
const fruits = ["apple", "banana", "orange", "grape"];

console.log(findIndex(fruits, "orange"));  // Output: 2
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="55">55. Convert Minutes to Hours and Minutes</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Convert a given number of minutes to hours and remaining minutes.</p>
<pre>
const minsToHoursAndMins = (mins) => {
  const hours = Math.floor(mins / 60);
  const remainingMins = mins % 60;
  return `${hours} hours and ${remainingMins} minutes`;
}; 

console.log(minsToHoursAndMins(150));  // Output: "2 hours and 30 minutes"
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="56">56. Check if an Array is Sorted in Ascending Order</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given array is sorted in ascending order.</p>
<pre>
const isSortedAscending = (arr) => arr.every((el, i) => i === 0 || el >= arr[i - 1]);

console.log(isSortedAscending([1, 2, 3, 5, 8]));  // Output: true
console.log(isSortedAscending([1, 5, 3, 8, 2]));  // Output: false
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="57">57. Remove a Specific Element from an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Remove a specific element from a given array.</p>
<pre>
const removeElement = (arr, element) => arr.filter(el => el !== element);

console.log(removeElement([1, 2, 3, 4, 5], 3));  // Output: [1, 2, 4, 5]
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="58">58. Truncate a String to a Given Length</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Truncate a given string to a specified maximum length.</p>
<pre>
const truncateString = (str, maxLength) =>
  str.length > maxLength ? str.slice(0, maxLength) + '...' : str;

console.log(truncateString("Hello, world!", 5));  // Output: "Hello..."
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="59">59. Calculate the Exponentiation of a Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the exponentiation of a given base raised to a specified exponent.</p>
<pre>
const exponentiate = (base, exponent) => Math.pow(base, exponent);

console.log(exponentiate(2, 3));  // Output: 8
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="60">60. Find the Difference between Two Dates in Days</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the difference between two dates in days.</p>
<pre>
const dateDifferenceInDays = (date1, date2) =>
  Math.abs(Math.floor((date2 - date1) / (1000 * 60 * 60 * 24)));
const startDate = new Date("2023-08-01");
const endDate = new Date("2023-08-10");

console.log(dateDifferenceInDays(startDate, endDate)); // Output: 9
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="61">61. Check if a String is a Valid Email Address</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given string is a valid email address.</p>
<pre>
const isValidEmail = (email) => /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);

console.log(isValidEmail("user@example.com"));  // Output: true
console.log(isValidEmail("invalid-email"));  // Output: false
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="62">62. Convert Seconds to Minutes and Seconds</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Convert a given number of seconds to minutes and remaining seconds.</p>
<pre>
const secsToMinsAndSecs = (seconds) => { 
  const mins = Math.floor(seconds / 60);
  const remainingSecs = seconds % 60;
  return `${mins} minutes and ${remainingSecs} seconds`;
};

console.log(secsToMinsAndSecs(120));  // Output: "2 minutes and 0 seconds"
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="63">63. Check if an Object is a Function</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given object is a function.</p>
<pre>
const isFunction = (obj) => typeof obj === 'function';

console.log(isFunction(() => {}));  // Output: true
console.log(isFunction({}));  // Output: false
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="64">64. Convert Binary Number to Decimal</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Convert a given binary number to its decimal representation.</p>
<pre>
const binaryToDecimal = (binary) => parseInt(binary, 2);

console.log(binaryToDecimal("1101"));  // Output: 13
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="65">65. Check if an Array contains only Unique Values</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given array contains only unique values.</p>
<pre>
const hasUniqueValues = (arr) => new Set(arr).size === arr.length; 

console.log(hasUniqueValues([1, 2, 3, 4, 5]));  // Output: true 
console.log(hasUniqueValues([1, 2, 3, 4, 4]));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="66">66. Get the Day of the Week from a Date</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Get the day of the week from a given date.</p>
<pre>
const getDayOfWeek = (date) => { 
const daysOfWeek = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"]; 
return daysOfWeek[date.getDay()]; 
}; 

console.log(getDayOfWeek(new Date("2023-08-02")));  // Output: "Wednesday" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="67">67. Check if a Number is a Power of Two</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a power of two.</p>
<pre>
const isPowerOfTwo = (num) => (num & (num - 1)) === 0; 

console.log(isPowerOfTwo(16));  // Output: true 
console.log(isPowerOfTwo(5));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="68">68. Convert Object to Query Parameters String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Convert a given object to a string of query parameters.</p>
<pre>
const objectToQueryParams = (obj) => Object.entries(obj).map(([key, value]) => `${encodeURIComponent(key)}=${encodeURIComponent(value)}`).join('&'); 

console.log(objectToQueryParams({ search: "hello", page: 1 }));  // Output: "search=hello&page=1"
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="69">69. Check if an Array contains an Even Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given array contains at least one even number.</p>
<pre>
const hasEvenNumber = (arr) => arr.some(num => num % 2 === 0); 

console.log(hasEvenNumber([1, 3, 5, 7, 8]));  // Output: true 
console.log(hasEvenNumber([1, 3, 5, 7, 9]));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="70">70. Get the Month Name from a Date</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Get the name of the month from a given date.</p>
<pre>
const getMonthName = (date) => { 
const months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"]; 
return months[date.getMonth()]; 
}; 

console.log(getMonthName(new Date("2023-08-02")));  // Output: "August" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="71">71. Check if a String is a Palindrome (case-insensitive)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given string is a palindrome, considering it case-insensitive.</p>
<pre>
const isPalindromeCaseInsensitive = (str) => str.toLowerCase() === str.toLowerCase().split('').reverse().join(''); 

console.log(isPalindromeCaseInsensitive("LeVel"));  // Output: true 
console.log(isPalindromeCaseInsensitive("Hello"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="72">72. Convert Feet to Meters</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Convert a given length in feet to meters.</p>
<pre>
const feetToMeters = (feet) => feet * 0.3048; 

console.log(feetToMeters(10));  // Output: 3.048 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="73">73. Check if a Number is a Perfect Square</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a perfect square.</p>
<pre>
const isPerfectSquare = (num) => Math.sqrt(num) % 1 === 0; 

console.log(isPerfectSquare(16));  // Output: true 
console.log(isPerfectSquare(10));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="74">74. Check if a String contains only Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given string contains only numeric characters.</p>
<pre>
const containsOnlyNumbers = (str) => /^[0-9]+$/.test(str); 

console.log(containsOnlyNumbers("12345"));  // Output: true 
console.log(containsOnlyNumbers("12a34"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="75">75. Get the Current Month (0-based index)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Get the current month as a 0-based index (0 for January, 1 for February, etc.).</p>
<pre>
const currentMonth = () => new Date().getMonth();

console.log(currentMonth());  // Output: Current month (0-based index) 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="76">76. Calculate the Mean of an Array of Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the mean (average) of a given array of numbers.</p>
<pre>
const mean = (arr) => arr.reduce((acc, val) => acc + val, 0) / arr.length; 

console.log(mean([1, 2, 3, 4, 5]));  // Output: 3 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="77">77. Check if a Number is a Prime Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a prime number.</p>
<pre>
const isPrime = (num) => {
  if (num <= 1) return false; 
  for (let i = 2; i <= Math.sqrt(num); i++) { 
    if (num % i === 0) return false;
  } 
  return true; 
}; 

console.log(isPrime(13));  // Output: true 
console.log(isPrime(4));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="78">78. Get the Last N Elements of an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Get the last N elements from a given array.</p>
<pre>
const lastNElements = (arr, n) => arr.slice(-n);

console.log(lastNElements([1, 2, 3, 4, 5], 3));  // Output: [3, 4, 5] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="79">79. Convert Degrees to Radians</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Convert a given angle from degrees to radians.</p>
<pre>
const degToRad = (degrees) => degrees * (Math.PI / 180); 

console.log(degToRad(90));  // Output: 1.5707963267948966 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="80">80. Check if a String is a Valid URL</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given string is a valid URL.</p>
<pre>
const isValidURL = (url) => { 
  try { 
    new URL(url); 
    return true; 
  } catch (error) { 
    return false; 
  } 
};
console.log(isValidURL("https://www.example.com")); // Output: true 
console.log(isValidURL("invalid-url"));             // Output: false 
</pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="81">81. Find the Intersection of Two Arrays</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the common elements (intersection) between two arrays.</p>
<pre>
const intersection = (arr1, arr2) => arr1.filter(val => arr2.includes(val)); 
console.log(intersection([1, 2, 3], [2, 3, 4]));  // Output: [2, 3] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="82">82. Convert Days to Years, Months, and Days</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Convert a given number of days to years, months, and remaining days.</p>
<pre>
const daysToYearsMonthsDays = (days) => { 
const years = Math.floor(days / 365); 
const remainingDays = days % 365; 
const months = Math.floor(remainingDays / 30); 
const remainingDaysInMonth = remainingDays % 30; 
return `${years} years, ${months} months, and ${remainingDaysInMonth} days`; 
}; 
console.log(daysToYearsMonthsDays(1000));  // Output: "2 years, 8 months, and 20 days"
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="83">83. Check if an Object is Empty (no own properties)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given object has no own properties (i.e., it is empty).</p>
<pre>
const isEmptyObject = (obj) => Object.keys(obj).length === 0; 
console.log(isEmptyObject({}));  // Output: true 
console.log(isEmptyObject({ name: "John", age: 30 }));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="84">84. Calculate the Factorial of a Number (recursive)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the factorial of a given number using a recursive function.</p>
<pre>
const factorial = (num) => { 
  if (num === 0 || num === 1) return 1; 
    return num * factorial(num - 1); 
}; 
console.log(factorial(5));  // Output: 120 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="85">85. Remove Whitespace from a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Remove all whitespace characters from a given string.</p>
<pre>
const removeWhitespace = (str) => str.replace(/\s/g, ''); 
console.log(removeWhitespace(" Hello, world! "));  // Output: "Hello,world!" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="86">86. Find the Difference between Two Arrays</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the elements that are present in the first array but not in the second array.</p>
<pre>
const difference = (arr1, arr2) => arr1.filter(val => !arr2.includes(val)); 
console.log(difference([1, 2, 3], [2, 3, 4]));  // Output: [1] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="87">87. Check if a Number is a Fibonacci Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a Fibonacci number.</p>
<pre>
const isFibonacci = (num) => isPerfectSquare(5 * num * num + 4) || isPerfectSquare(5 * num * num - 4); 
console.log(isFibonacci(5));  // Output: true 
console.log(isFibonacci(6));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="88">88. Convert Hours to Minutes</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Convert a given number of hours to minutes.</p>
<pre>
const hoursToMinutes = (hours) => hours * 60; 
console.log(hoursToMinutes(2));  // Output: 120 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="89">89. Get the First N Elements of an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Get the first N elements from the beginning of an array.</p>
<pre>
const firstNElements = (arr, n) => arr.slice(0, n); 
console.log(firstNElements([1, 2, 3, 4, 5], 3));  // Output: [1, 2, 3] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="90">90. Check if a Number is Odd</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Get the first N elements from the beginning of an array.</p>
<pre>
const isOdd = (num) => num % 2 !== 0; 
console.log(isOdd(5));  // Output: true 
console.log(isOdd(4));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="91">91. Calculate the Standard Deviation of an Array of Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the standard deviation of an array of numbers.</p>
<pre>
const standardDeviation = (arr) => { 
  const avg = mean(arr); 
  const squaredDiffs = arr.map(num => Math.pow(num - avg, 2)); 
  const variance = mean(squaredDiffs); 
  return Math.sqrt(variance); 
}; 
console.log(standardDeviation([1, 2, 3, 4, 5]));  // Output: 1.4142135623730951 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="92">92. Check if a String ends with a specific Substring</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a string ends with a specific substring.</p>
<pre>
const endsWithSubstring = (str, subStr) => str.endsWith(subStr); 
console.log(endsWithSubstring("Hello, world!", "world!"));  // Output: true 
console.log(endsWithSubstring("Hello, world!", "Hello"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="93">93. Calculate the Sum of Squares of an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the sum of squares of an array of numbers.</p>
<pre>
const sumOfSquares = (arr) => arr.reduce((acc, val) => acc + val ** 2, 0); 
console.log(sumOfSquares([1, 2, 3, 4, 5]));  // Output: 55 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="94">94. Check if a String is a Palindrome (case-sensitive)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a string is a palindrome, considering case sensitivity.</p>
<pre>
const isPalindromeCaseSensitive = (str) => str === str.split('').reverse().join(''); 
console.log(isPalindromeCaseSensitive("level"));  // Output: true 
console.log(isPalindromeCaseSensitive("Hello"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="95">95. Generate an Array of Random Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Generate an array of random numbers.</p>
<pre>
const randomArray = (length) => Array.from({ length }, () => Math.floor(Math.random() * 100)); 
console.log(randomArray(5));  // Output: Array with 5 random numbers, e.g., [23, 45, 67, 11, 88]
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="96">96. Calculate the Greatest Common Divisor (GCD) of Two Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the Greatest Common Divisor (GCD) of two numbers.</p>
<pre>
const gcd = (num1, num2) => { 
  while (num2 !== 0) { 
    let temp = num2; 
    num2 = num1 % num2; 
    num1 = temp; 
  } 
  return num1;
}; 
console.log(gcd(48, 18));  // Output: 6
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="97">97. Convert Seconds to Hours, Minutes, and Seconds</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Convert seconds to hours, minutes, and seconds.</p>
<pre>
const secsToHoursMinsSecs = (seconds) => { 
  const hours = Math.floor(seconds / 3600); 
  const remainingSeconds = seconds % 3600; 
  const minutes = Math.floor(remainingSeconds / 60); 
  const remainingSecs = remainingSeconds % 60; 
  return `${hours} hours, ${minutes} minutes, and ${remainingSecs} seconds`; 
}; 
console.log(secsToHoursMinsSecs(7320));  // Output: "2 hours, 2 minutes, and 0 seconds"
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="98">98. Calculate the LCM of Two Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the Least Common Multiple (LCM) of two numbers.</p>
<pre>
const lcm = (num1, num2) => (num1 * num2) / gcd(num1, num2); 
console.log(lcm(6, 8));  // Output: 24
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="99">99. Find the Longest Word in a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the longest word in a string.</p>
<pre>
const findLongestWord = (str) => str.split(' ').reduce((longest, word) 
  => word.length > longest.length ? word : longest, ''); 
console.log(findLongestWord("Hello, how are you doing?"));  // Output: "doing?" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="100">100. Count the Occurrences of a Character in a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Count the occurrences of a character in a string.</p>
<pre>
const countOccurrences = (str, char) => str.split(char).length - 1; 
console.log(countOccurrences("hello world", "l"));  // Output: 3 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="101">101. Find the Median of an Array of Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the median of an array of numbers.</p>
<pre>
const median = (arr) => { 
  const sorted = arr.sort((a, b) => a - b); 
  const mid = Math.floor(sorted.length / 2); 
  return sorted.length % 2 === 0 ? (sorted[mid - 1] + sorted[mid]) / 2 : sorted[mid]; 
}; 
console.log(median([1, 3, 5, 7, 9]));  // Output: 5
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="102">102. Remove Duplicates from a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Remove duplicate characters from a string.</p>
<pre>
const removeDuplicatesFromString = (str) => [...new Set(str.split(''))].join(''); 
console.log(removeDuplicatesFromString("hello"));  // Output: "helo" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="103">103. Find the Mode of an Array of Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the mode, the most frequently occurring number(s), from an array of numbers. 
It identifies the number(s) with the highest frequency and returns them in an array.</p>
<pre>
const mode = (arr) => { 
  const frequency = {}; 
  arr.forEach(num => frequency[num] = (frequency[num] || 0) + 1); 
  const maxFrequency = Math.max(...Object.values(frequency)); 
  return Object.keys(frequency).filter(num => frequency[num] === maxFrequency).map(Number); 
}; 
console.log(mode([1, 2, 2, 3, 3, 3, 4, 4, 4, 4]));  // Output: [4] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="104">104. Check if a Number is a Harshad Number (Niven Number)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>A Harshad number, also known as a Niven number, is an integer divisible by the sum of its 
digits. The isHarshadNumber function determines whether a given number meets this criterion. 
It calculates the sum of the digits of the number, and then checks if the number itself is 
divisible by this sum.</p>
<pre>
const isHarshadNumber = (num) => num % [...String(num)].reduce((sum, digit) => sum + Number(digit), 0) === 0; 
console.log(isHarshadNumber(18));  // Output: true 
console.log(isHarshadNumber(21));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="105">105. Convert Binary Number to Decimal (without parseInt)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This function performs the conversion of a binary number to its equivalent decimal 
representation, all without utilizing the parseInt function. The process involves 
splitting the binary number's digits, reversing them, and using a reduce operation 
to calculate the decimal value by considering each digit's position and value.</p>
<pre>
const binaryToDecimalWithoutParseInt = (binary) => binary.split('').reverse().reduce((dec, bit, index) => dec + bit * (2 ** index), 0); 
console.log(binaryToDecimalWithoutParseInt("1101"));  // Output: 13 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="106">106. Check if an Array is Sorted in Descending Order</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This function determines if an array is sorted in descending order. It iterates through 
the array and verifies that each element is either greater than or equal to the preceding 
element, ensuring a descending order.</p>
<pre>
const isSortedDescending = (arr) => arr.every((el, i) => i === 0 || el <= arr[i - 1]); 
console.log(isSortedDescending([5, 4, 3, 2, 1]));  // Output: true 
console.log(isSortedDescending([1, 5, 3, 8, 2]));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="107">107. Find the Average of Even Numbers in an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This function computes the average of even numbers present in an array. It first filters 
out the even numbers from the array, then calculates the sum of these even numbers, and 
finally divides the sum by the count of even numbers to obtain the average.</p>
<pre>
const averageOfEvenNumbers = (arr) => { 
  const evenNumbers = arr.filter(num => num % 2 === 0); 
  return evenNumbers.reduce((sum, num) => sum + num, 0) / evenNumbers.length; 
}; 
console.log(averageOfEvenNumbers([1, 2, 3, 4, 5, 6, 7, 8, 9, 10]));  // Output: 6 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="108">108. Capitalize the First Letter of Each Word in a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This function transforms a string by capitalizing the first letter of each word within 
it. It employs a regular expression to locate the first character of each word (defined 
as a word boundary followed by a letter), and then replaces it with its uppercase version.</p>
<pre>
const capitalizeWords = (str) => str.replace(/\b\w/g, char => char.toUpperCase()); 
console.log(capitalizeWords("hello world"));  // Output: "Hello World" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="109">109. Check if an Array is a Subset of Another Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isSubset function determines if one array is a subset of another array. It 
achieves this by verifying that every element in the first array (arr1) is present in 
the second array (arr2).</p>
<pre>
const isSubset = (arr1, arr2) => arr1.every(item => arr2.includes(item)); 
console.log(isSubset([1, 2, 3], [2, 3, 4, 5, 6]));  // Output: false 
console.log(isSubset([1, 2, 3], [2, 3, 1, 5, 6]));  // Output: true 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="110">110. Find the Minimum and Maximum Numbers in an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The minMax function calculates both the minimum and maximum values within an array. 
It achieves this by employing the Math.min and Math.max functions alongside the 
spread operator to extract the elements' values from the input array. The function 
returns an object containing both the minimum and maximum values.</p>
<pre>
const minMax = (arr) => ({ 
  min: Math.min(...arr), 
  max: Math.max(...arr) 
}); 
console.log(minMax([10, 5, 25, 3, 15]));  // Output: { min: 3, max: 25 } 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="111">111. Check if a Number is a Narcissistic Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isNarcissisticNumber function evaluates whether a given number is a narcissistic number.</p>
<pre>
const isNarcissisticNumber = (num) => { 
  const digits = [...String(num)].map(Number); 
  const numDigits = digits.length; 
  const sumOfPowers = digits.reduce((sum, digit) => sum + Math.pow(digit, numDigits), 0); 
  return sumOfPowers === num; 
}; 
console.log(isNarcissisticNumber(153));  // Output: true 
console.log(isNarcissisticNumber(370));  // Output: true 
console.log(isNarcissisticNumber(123));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="112">112. Remove Null and Undefined Values from an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The removeNullAndUndefined function eliminates null and undefined values from an array by 
utilizing the filter method. It returns a new array containing only the non-null and 
non-undefined elements.</p>
<pre>
const removeNullAndUndefined = (arr) => arr.filter(item => item !== null && item !== undefined); 
console.log(removeNullAndUndefined([1, null, 2, 3, undefined, 4, null]));  // Output: [1, 2, 3, 4] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="113">113. Reverse the Order of Words in a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The reverseWords function takes a string as input and returns a new string where the order 
of words has been reversed.</p>
<pre>
const reverseWords = (str) => str.split(' ').reverse().join(' '); 
console.log(reverseWords("Hello, world!"));  // Output: "world! Hello," 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="114">114. Calculate the Sum of Cubes of an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The sumOfCubes function computes the sum of the cubes of all numbers in an array. It 
employs the reduce method to iterate through the array, accumulating the sum of cubes 
by raising each value to the power of 3 and adding it to the accumulator.</p>
<pre>
const sumOfCubes = (arr) => arr.reduce((acc, val) => acc + val ** 3, 0); 
console.log(sumOfCubes([1, 2, 3, 4, 5]));  // Output: 225 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="115">115. Shuffle the Characters of a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The shuffleString function rearranges the characters of a given string in a random 
order. It does so by first splitting the string into an array of characters, then 
using the sort method with a random comparison function. Finally, the shuffled 
characters are rejoined to form a new string.</p>
<pre>
const shuffleString = (str) => str.split('').sort(() => 0.5 - Math.random()).join(''); 
console.log(shuffleString("hello"));  // Output: Randomly shuffled string, e.g., "olelh" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="116">116. Find the Nth Fibonacci Number (recursive)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The fibonacci function calculates the Nth Fibonacci number using a recursive approach. 
It determines the Fibonacci number by summing the previous two Fibonacci numbers until 
it reaches the base cases of 0 and 1.</p>
<pre>
const fibonacci = (n) => (n <= 1 ? n : fibonacci(n - 1) + fibonacci(n - 2)); 
console.log(fibonacci(7));  // Output: 13 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="117">117. Count the Words in a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The countWords function determines the number of words in a given string. It accomplishes 
this by splitting the string using a regular expression that matches one or more whitespace 
characters, and then counting the resulting array's length.</p>
<pre>
const countWords = (str) => str.split(/\s+/).length; 
console.log(countWords("Hello, how are you doing?"));  // Output: 5 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="118">118. Check if a Number is a Triangular Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isTriangularNumber function determines whether a given number is a triangular number.</p>
<pre>
const isTriangularNumber = (num) => { 
  let n = 0; 
  let sum = 0; 
  while (sum < num) { 
    n++; 
    sum += n; 
  } 
  return sum === num; 
}; 
console.log(isTriangularNumber(10));  // Output: true 
console.log(isTriangularNumber(15));  // Output: true 
console.log(isTriangularNumber(7));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="119">119. Calculate the Perimeter of a Rectangle</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The rectanglePerimeter function calculates the perimeter of a rectangle by summing 
twice the width and twice the height of the rectangle.</p>
<pre>
const rectanglePerimeter = (width, height) => 2 * (width + height); 
console.log(rectanglePerimeter(5, 10));  // Output: 30 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="120">120. Find the Longest Common Prefix in an Array of Strings</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The longestCommonPrefix function finds the longest common prefix among an array of 
strings. It starts by assuming the first string in the array as the initial common prefix.</p>
<pre>
const longestCommonPrefix = (strs) => { 
  if (strs.length === 0) return ''; 
  let prefix = strs[0]; 
  for (let i = 1; i < strs.length; i++) { 
    while (!strs[i].startsWith(prefix)) { 
      prefix = prefix.slice(0, prefix.length - 1); 
    } 
  } 
  return prefix; 
}; 
console.log(longestCommonPrefix(['apple', 'apricot', 'appetizer']));  // Output: "app" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="121">121. Get the ASCII Value of a Character</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The getASCIIValue function retrieves the ASCII value of a given character. It employs 
the charCodeAt method, which returns the ASCII code of the character at the specified 
index (0 in this case).</p>
<pre>
const getASCIIValue = (char) => char.charCodeAt(0); 
console.log(getASCIIValue('A'));  // Output: 65 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="122">122. Find the First Non-Repeated Character in a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The firstNonRepeatedChar function identifies the first non-repeated character within 
a given string. It accomplishes this by iterating through the string, building a 
character count object, and then using the find method to locate the first character 
with a count of 1.</p>
<pre>
const firstNonRepeatedChar = (str) => { 
  const charCount = {}; 
  for (const char of str) { 
    charCount[char] = (charCount[char] || 0) + 1; 
  } 
  return str.split('').find((char) => charCount[char] === 1); 
}; 
console.log(firstNonRepeatedChar('abacabad'));  // Output: "c" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="123">123. Sort an Array of Objects by a Property Value</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The sortByProperty function arranges an array of objects based on a specified property's 
value. It employs the sort method with a custom comparison function that compares the 
property values of two objects.</p>
<pre>
const sortByProperty = (arr, prop) => arr.sort((a, b) => a[prop] - b[prop]); 
const people = [ 
  { name: 'Alice', age: 25 }, 
  { name: 'Bob', age: 20 }, 
  { name: 'Charlie', age: 30 } 
]; 
console.log(sortByProperty(people, 'age'));  // Output: [{ name: 'Bob', age: 20 }, { name: 'Alice', age: 25 }, { name: 'Charlie', age: 30 }] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="124">124. Calculate the Exponential of a Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The exponential function calculates the result of raising a given base to a specified 
exponent using the exponentiation operator (**).</p>
<pre>
const exponential = (base, exponent) => base ** exponent; 
console.log(exponential(2, 3));  // Output: 8 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="125">125. Check if a String is an Anagram of Another String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isAnagram function determines whether two given strings are anagrams of each 
other. An anagram is a word or phrase formed by rearranging the letters of another, 
using all the original letters exactly once.</p>
<pre>
const isAnagram = (str1, str2) => str1.split('').sort().join('') === str2.split('').sort().join(''); 
console.log(isAnagram('listen', 'silent'));  // Output: true 
console.log(isAnagram('hello', 'world'));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="126">126. Find the Factors of a Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The factors function calculates and returns an array of all the factors of a given 
number. Factors are the positive integers that evenly divide the input number.</p>
<pre>
const factors = (num) => { 
  const result = []; 
  for (let i = 1; i <= num; i++) { 
    if (num % i === 0) { 
      result.push(i); 
    } 
  } 
  return result; 
}; 
console.log(factors(12));  // Output: [1, 2, 3, 4, 6, 12] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="127">127. Check if a Number is a Neon Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isNeonNumber function determines whether a given number is a neon number. A neon 
number is a number where the sum of the digits of its square is equal to the number itself.</p>
<pre>
const isNeonNumber = (num) => { 
  const squared = num ** 2; 
  const digitSum = [...String(squared)].map(Number).reduce((sum, digit) => sum + digit, 0); 
  return squared === digitSum; 
}; 
console.log(isNeonNumber(9));  // Output: true 
console.log(isNeonNumber(12));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="128">128. Find the Power Set of a Set</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The powerSet function generates the power set of a given set, which includes all possible 
subsets of the set, including the empty set and the set itself.</p>
<pre>
const powerSet = (set) => { 
  const result = [[]]; 
  for (const item of set) { 
    const subsets = result.map((subset) => [...subset, item]); 
    result.push(...subsets); 
  } 
  return result; 
}; 
console.log(powerSet([1, 2, 3]));  // Output: [ [], [1], [2], [3], [1, 2], [1, 3], [2, 3], [1, 2, 3] ] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="129">129. Check if a Number is a Disarium Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isDisariumNumber function determines whether a given number is a disarium number.</p>
<pre>
const isDisariumNumber = (num) => { 
  const digits = [...String(num)].map(Number); 
  const sumOfPowers = digits.reduce((sum, digit, index) => sum + digit ** (index + 1), 0); 
  return sumOfPowers === num; 
}; 
console.log(isDisariumNumber(89));  // Output: true 
console.log(isDisariumNumber(135));  // Output: true 
console.log(isDisariumNumber(23));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="130">130. Remove Vowels from a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The removeVowels function eliminates all vowels (both uppercase and lowercase) from a 
given string using the replace method along with a regular expression.</p>
<pre>
const removeVowels = (str) => str.replace(/[aeiouAEIOU]/g, ''); 
console.log(removeVowels("Hello, World!"));  // Output: "Hll, Wrld!" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="131">131. Generate an Array of Consecutive Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The consecutiveNumbers function generates an array of consecutive numbers within a 
specified range.</p>
<pre>
const consecutiveNumbers = (start, end) => Array.from({ length: end - start + 1 }, (_, i) => start + i); 
console.log(consecutiveNumbers(1, 5));  // Output: [1, 2, 3, 4, 5] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="132">132. Check if a Number is a Pronic Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isPronicNumber function determines whether a given number is a pronic number (also 
known as an oblong number or rectangular number).</p>
<pre>
const isPronicNumber = (num) => { 
  const n = Math.floor(Math.sqrt(num)); 
  return n * (n + 1) === num; 
}; 
console.log(isPronicNumber(6));  // Output: true 
console.log(isPronicNumber(20));  // Output: true 
console.log(isPronicNumber(7));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="133">133. Check if a String is a Pangram</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isPangram function checks whether a given string is a pangram, which is a sentence 
that contains every letter of the alphabet at least once.</p>
<pre>
const isPangram = (str) => { 
  const letters = new Set(str.toLowerCase().match(/[a-z]/g)); 
  return letters.size === 26; 
}; 
console.log(isPangram("The quick brown fox jumps over the lazy dog"));  // Output: true 
console.log(isPangram("Hello, World!"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="134">134. Reverse the Order of Words in a Sentence</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The reverseSentence function reverses the order of words in a given sentence.</p>
<pre>
const reverseSentence = (sentence) => sentence.split(' ').reverse().join(' '); 
console.log(reverseSentence("Hello, how are you doing?"));  // Output: "doing? you are how Hello," 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="135">135. Calculate the Hypotenuse of a Right-Angled Triangle</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The binaryToDecimalWithParseInt function converts a binary number to a decimal number 
using the built-in parseInt function with the base parameter set to 2.</p>
<pre>
const binaryToDecimalWithParseInt = (binary) => parseInt(binary, 2); 
console.log(binaryToDecimalWithParseInt("1101"));  // Output: 13 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="136">136. Find the Average of Odd Numbers in an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The averageOfOddNumbers function calculates the average of odd numbers within a 
given array. It does so by filtering the odd numbers from the array, then computing 
their sum and dividing by the count of odd numbers.</p>
<pre>
const averageOfOddNumbers = (arr) => { 
  const oddNumbers = arr.filter(num => num % 2 !== 0); 
  return oddNumbers.reduce((sum, num) => sum + num, 0) / oddNumbers.length; 
}; 
console.log(averageOfOddNumbers([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])); // Output: 5 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="137">137. Count the Letters in a String (case-insensitive)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The countLetters function calculates the count of each letter in a given string, 
considering both uppercase and lowercase versions as the same letter.</p>
<pre>
const countLetters = (str) => { 
  const letters = str.toLowerCase().match(/[a-z]/g); 
  const letterCount = {}; 
  for (const letter of letters) { 
    letterCount[letter] = (letterCount[letter] || 0) + 1; 
  } 
  return letterCount; 
}; 
console.log(countLetters("Hello, World!"));  // Output: { h: 1, e: 1, l: 3, o: 2, w: 1, r: 1, d: 1 } 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="138">138. Convert Seconds to Days, Hours, Minutes, and Seconds</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The secsToDaysHoursMinsSecs function converts a given number of seconds into days, 
hours, minutes, and remaining seconds.</p>
<pre>
const secsToDaysHoursMinsSecs = (seconds) => { 
  const days = Math.floor(seconds / 86400); 
  seconds %= 86400; 
  const hours = Math.floor(seconds / 3600); 
  seconds %= 3600; 
  const minutes = Math.floor(seconds / 60); 
  const remainingSecs = seconds % 60; 
  return `${days} days, ${hours} hours, ${minutes} minutes, and ${remainingSecs} seconds`; 
}; 
console.log(secsToDaysHoursMinsSecs(100000));  // Output: "1 days, 3 hours, 46 minutes, and 40 seconds" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="139">139. Check if a Number is a Prime Factor of Another Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isPrimeFactor function checks if a given number is a prime factor of another number.</p>
<pre>
const isPrimeFactor = (num, factor) => num % factor === 0 && isPrime(factor); 
console.log(isPrimeFactor(20, 2));  // Output: true 
console.log(isPrimeFactor(20, 3));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="140">140. Find the Largest Prime Factor of a Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The largestPrimeFactor function calculates the largest prime factor of a given number.</p>
<pre>
const largestPrimeFactor = (num) => { 
  let factor = 2; 
  while (factor <= num) { 
    if (num % factor === 0) { 
      num /= factor; 
    } else { 
    factor++; 
    } 
  } 
  return factor; 
}; 
console.log(largestPrimeFactor(48));  // Output: 3 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="141">141. Check if a Number is a Pronic Square</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isPronicSquare function checks if a given number is a pronic square.</p>
<pre>
const isPronicSquare = (num) => Number.isInteger(Math.sqrt(num)); 
console.log(isPronicSquare(6));  // Output: true 
console.log(isPronicSquare(20));  // Output: false 
console.log(isPronicSquare(21));  // Output: true 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="142">142. Find the Sum of the Digits of a Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The sumOfDigits function calculates the sum of the digits of a given number.</p>
<pre>
const sumOfDigits = (num) => [...String(num)].reduce((sum, digit) => sum + Number(digit), 0); 
console.log(sumOfDigits(12345));  // Output: 15 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="143">143. Calculate the Median of an Array of Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The median function calculates the median of an array of numbers. The median is the 
middle value of a dataset when it is ordered.</p>
<pre>
const median = (arr) => { 
  const sorted = arr.sort((a, b) => a - b); 
  const mid = Math.floor(sorted.length / 2); 
  return sorted.length % 2 === 0 ? (sorted[mid - 1] + sorted[mid]) / 2 : sorted[mid]; 
}; 
console.log(median([1, 3, 5, 7, 9]));  // Output: 5 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="144">144. Find the Greatest Common Divisor (GCD) of Two Numbers (Recursive)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The gcd function calculates the greatest common divisor (GCD) of two given numbers 
using a recursive approach.</p>
<pre>
const gcd = (num1, num2) => (num2 === 0 ? num1 : gcd(num2, num1 % num2)); 
console.log(gcd(48, 18));  // Output: 6 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="145">145. Check if a Number is a Happy Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isHappyNumber function checks if a given number is a "happy number" or not. A 
happy number is a number where the sequence of repeatedly summing the squares of 
its digits eventually reaches the number 1.</p>
<pre>
const isHappyNumber = (num) => { 
  const seen = new Set(); 
  while (num !== 1 && !seen.has(num)) { 
    seen.add(num); 
    num = [...String(num)].reduce((sum, digit) => sum + digit ** 2, 0); 
  } 
  return num === 1; 
}; 
console.log(isHappyNumber(19));  // Output: true 
console.log(isHappyNumber(4));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="146">146. Find the First N Prime Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The firstNPrimes function generates an array of the first n prime numbers.</p>
<pre>
const isPrime = (num) => { 
  if (num <= 1) return false; 
  for (let i = 2; i <= Math.sqrt(num); i++) { 
    if (num % i === 0) return false; 
  } 
  return true; 
}; 
const firstNPrimes = (n) => { 
  const primes = []; 
  let num = 2; 
  while (primes.length < n) { 
    if (isPrime(num)) primes.push(num); 
      num++; 
  } 
  return primes; 
}; 
console.log(firstNPrimes(5));  // Output: [2, 3, 5, 7, 11] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="147">147. Calculate the Volume of a Sphere
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The sphereVolume function calculates the volume of a sphere given its radius. It uses 
the formula (4/3) * π * r^3, where r is the radius of the sphere.</p>
<pre>
const sphereVolume = (radius) => (4 / 3) * Math.PI * radius ** 3; 
console.log(sphereVolume(5));  // Output: 523.5987755982989 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="148">148. Find the Longest Word in a Sentence</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The longestWord function determines the longest word in a given sentence. It does this 
by splitting the sentence into words using spaces as separators and then using the 
reduce method to compare the length of each word and keep track of the longest one.</p>
<pre>
const longestWord = (sentence) => sentence.split(' ').reduce((longest, word) 
  => (word.length > longest.length ? word : longest), ''); 
console.log(longestWord("The quick brown fox jumped over the lazy dog"));  // Output: "jumped" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="149">149. Check if a Number is an Armstrong Number (Narcissistic Number)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isArmstrongNumber function checks if a number is an Armstrong number, also known as a 
narcissistic number.</p>
<pre>
const isArmstrongNumber = (num) => { 
  const digits = [...String(num)].map(Number); 
  const numDigits = digits.length; 
  const sumOfPowers = digits.reduce((sum, digit) => sum + digit ** numDigits, 0); 
  return sumOfPowers === num; 
}; 
console.log(isArmstrongNumber(153));  // Output: true 
console.log(isArmstrongNumber(370));  // Output: true 
console.log(isArmstrongNumber(123));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="150">150. Find the Length of the Longest Word in a Sentence</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The longestWordLength function calculates the length of the longest word in a given 
sentence. It splits the sentence into words using spaces as separators, and then uses 
the reduce method to find the maximum length among all the words.</p>
<pre>
const longestWordLength = (sentence) => sentence.split(' ').reduce((longest, word) 
  => Math.max(longest, word.length), 0); 
console.log(longestWordLength("The quick brown fox jumped over the lazy dog"));  // Output: 6 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="151">151. Check if a Number is a Strong Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isStrongNumber function checks if a number is a strong number. A strong number is a 
number whose sum of factorials of its digits is equal to the number itself.</p>
<pre>
const factorial = (num) => (num === 0 ? 1 : num * factorial(num - 1)); 
const isStrongNumber = (num) => { 
  const sumOfFactorials = [...String(num)].reduce((sum, digit) => sum + factorial(Number(digit)), 0); 
  return sumOfFactorials === num; 
}; 
console.log(isStrongNumber(145));  // Output: true 
console.log(isStrongNumber(123));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="152">152. Reverse the Order of an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The reverseArray function reverses the order of elements in an array using the reverse method.</p>
<pre>
const reverseArray = (arr) => arr.reverse(); 
console.log(reverseArray([1, 2, 3, 4, 5]));  // Output: [5, 4, 3, 2, 1] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="153">153. Find the Area of a Rectangle</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The rectangleArea function calculates the area of a rectangle given its length and width 
using the formula: length * width.</p>
<pre>
const rectangleArea = (length, width) => length * width; 
console.log(rectangleArea(5, 10));  // Output: 50 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="154">154. Calculate the Sum of Even Numbers in an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The sumOfEvenNumbers function calculates the sum of even numbers within an array. It 
first filters the array to keep only the even numbers, and then uses the reduce method 
to compute their sum.</p>
<pre>
const sumOfEvenNumbers = (arr) => arr.filter(num => num % 2 === 0).reduce((sum, num) => sum + num, 0); 
console.log(sumOfEvenNumbers([1, 2, 3, 4, 5, 6, 7, 8, 9, 10]));  // Output: 30 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="155">155. Find the Greatest Common Divisor (GCD) of Two Numbers (Iterative)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The gcdIterative function calculates the greatest common divisor (GCD) of two numbers 
using an iterative approach. It employs the Euclidean algorithm to iteratively find 
the GCD.</p>
<pre>
const gcdIterative = (num1, num2) => { 
  while (num2 !== 0) { 
    const temp = num2; 
    num2 = num1 % num2; 
    num1 = temp; 
  } 
  return num1; 
}; 
console.log(gcdIterative(48, 18));  // Output: 6 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="156">156. Calculate the Volume of a Cylinder</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The cylinderVolume function calculates the volume of a cylinder using the formula: π * radius^2 * height.</p>
<pre>
const cylinderVolume = (radius, height) => Math.PI * radius ** 2 * height; 
console.log(cylinderVolume(5, 10));  // Output: 785.3981633974483 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="157">157. Check if a Number is a Smith Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isSmithNumber function checks whether a given number is a Smith number.</p>
<pre>
const sumOfDigits = (num) => [...String(num)].reduce((sum, digit) => sum + Number(digit), 0); 
const sumOfPrimeFactors = (num) => { 
  let factor = 2; 
  let sum = 0; 
  while (num > 1) { 
    if (num % factor === 0) { 
      sum += sumOfDigits(factor); 
      num /= factor; 
    } else { 
      factor++; 
    } 
  } 
  return sum; 
}; 
const isSmithNumber = (num) => sumOfDigits(num) === sumOfPrimeFactors(num); 
console.log(isSmithNumber(666));  // Output: true 
console.log(isSmithNumber(378));  // Output: true 
console.log(isSmithNumber(123));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="158">158. Convert Decimal Number to Octal</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The decimalToOctal function converts a decimal (base 10) number to its octal (base 8) 
representation using the .toString() method with the base argument set to 8.</p>
<pre>
const decimalToOctal = (num) => num.toString(8); 
console.log(decimalToOctal(27));  // Output: "33" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="159">159. Find the LCM of Two Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The lcm function calculates the least common multiple (LCM) of two given numbers using 
the formula: (num1 * num2) / gcd(num1, num2).</p>
<pre>
const lcm = (num1, num2) => (num1 * num2) / gcd(num1, num2); 
console.log(lcm(24, 36));  // Output: 72 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="160">160. Check if a String is a Valid Phone Number (North American Format)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isValidPhoneNumber function checks whether a given string is a valid phone number 
in the North American format "XXX-XXX-XXXX", where X represents a digit.</p>
<pre>
const isValidPhoneNumber = (phone) => /^\d{3}-\d{3}-\d{4}$/.test(phone); 
console.log(isValidPhoneNumber("555-123-4567"));  // Output: true 
console.log(isValidPhoneNumber("123-4567"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="161">161. Find the Sum of the First N Natural Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The sumOfNaturals function calculates the sum of the first N natural numbers using the 
formula: (n * (n + 1)) / 2.</p>
<pre>
const sumOfNaturals = (n) => (n * (n + 1)) / 2; 
console.log(sumOfNaturals(10));  // Output: 55 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="162">162. Check if a Number is a Perfect Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isPerfectNumber function checks whether a given number is a perfect number. A 
perfect number is a positive integer that is equal to the sum of its proper divisors 
(excluding itself).</p>
<pre>
const isPerfectNumber = (num) => { 
  let sum = 0; 
  for (let i = 1; i <= num / 2; i++) { 
    if (num % i === 0) sum += i; 
  } 
  return sum === num; 
}; 
console.log(isPerfectNumber(28));  // Output: true 
console.log(isPerfectNumber(12));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="163">163. Find the Factors of a Number (excluding 1 and the number itself)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The factors function calculates the factors of a given number, excluding 1 and the 
number itself. It iterates through the numbers from 2 up to one less than the given 
number, checking if the given number is divisible by each of those numbers.</p>
<pre>
const factors = (num) => { 
  const result = []; 
  for (let i = 2; i < num; i++) { 
    if (num % i === 0) result.push(i); 
  } 
  return result; 
}; 
console.log(factors(12));  // Output: [2, 3, 4, 6] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="164">164. Calculate the Area of a Triangle given the Base and Height</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The triangleArea function calculates the area of a triangle using the formula: 0.5 
* base * height.</p>
<pre>
const triangleArea = (base, height) => 0.5 * base * height; 
console.log(triangleArea(5, 10));  // Output: 25 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="165">165. Check if a String is a Valid Social Security Number (SSN)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isValidSSN function checks whether a given string is a valid Social Security Number 
(SSN) in the format "XXX-XX-XXXX", where X represents a digit.</p>
<pre>
const isValidSSN = (ssn) => /^\d{3}-\d{2}-\d{4}$/.test(ssn); 
console.log(isValidSSN("123-45-6789"));  // Output: true 
console.log(isValidSSN("123-45-678"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="166">166. Generate an Array of Random Numbers within a Range</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The randomArrayInRange function generates an array of random numbers within a specified 
range and of a specified length. It uses the Array.from method with a mapping function 
to create the desired array.</p>
<pre>
const randomArrayInRange = (min, max, length) => Array.from({ length }, () 
  => Math.floor(Math.random() * (max - min + 1)) + min); 
console.log(randomArrayInRange(1, 100, 5));  // Output: [34, 87, 19, 56, 72] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="167">167. Check if a Number is a Magic Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isMagicNumber function checks whether a given number is a magic number. A magic 
number is a number that eventually reaches the value 1 when the sum of its digits is 
repeatedly calculated.</p>
<pre>
const isMagicNumber = (num) => { 
  let sum = 0; 
  while (num > 0) { 
    sum += num % 10; 
    num = Math.floor(num / 10); 
  } 
  return sum === 1; 
}; 
console.log(isMagicNumber(19));  // Output: true 
console.log(isMagicNumber(123));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="168">168. Check if a String is a Valid IPv4 Address</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isValidIPv4 function checks whether a given string represents a valid IPv4 address.</p>
<pre>
const isValidIPv4 = (ip) => /^(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$/.test(ip); 
console.log(isValidIPv4("192.168.1.1"));  // Output: true 
console.log(isValidIPv4("256.0.0.1"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="169">169. Convert Decimal Number to Hexadecimal</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The decimalToHex function converts a decimal (base 10) number to its equivalent hexadecimal 
(base 16) representation using the built-in toString method with a radix of 16.</p>
<pre>
const decimalToHex = (num) => num.toString(16); 
console.log(decimalToHex(255));  // Output: "ff" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="170">170. Check if a String is a Valid Date (YYYY-MM-DD Format)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isValidDate function checks whether a given string is a valid date in the format "YYYY-MM-DD".</p>
<pre>
const isValidDate = (date) => /^\d{4}-\d{2}-\d{2}$/.test(date); 
console.log(isValidDate("2023-08-02"));  // Output: true 
console.log(isValidDate("02-08-2023"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="171">171. Find the Smallest Common Multiple of an Array of Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>In this code, the gcd function calculates the greatest common divisor using the Euclidean 
algorithm. The lcmArray function then calculates the least common multiple (LCM) of an 
array of numbers by reducing the array and applying the formula (lcm * num) / gcd(lcm, num).</p>
<pre>
const lcmArray = (arr) => arr.reduce((lcm, num) => (lcm * num) / gcd(lcm, num)); 
console.log(lcmArray([2, 3, 4, 5]));  // Output: 60 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="172">172. Check if a String is a Valid Password (At least 8 characters, with a digit and 
special character) The isValidPassword function uses a regular expression to validate 
a password. The regular expression requires that the password contains at least one 
letter ([A-Za-z]), one digit (\d), and one special character ([@$!%*?&]).</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
const isValidPassword = (password) => /^(?=.*[A-Za-z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$/.test(password); 
console.log(isValidPassword("P@ssw0rd"));  // Output: true 
console.log(isValidPassword("password123"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="173">173. Find the Nth Fibonacci Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The fibonacci function calculates the Nth Fibonacci number using an iterative approach.</p>
<pre>
const fibonacci = (n) => { 
  if (n === 1) return 0; 
  if (n === 2) return 1; 
  let prev1 = 0; 
  let prev2 = 1; 
  let result; 
  for (let i = 3; i <= n; i++) { 
    result = prev1 + prev2; 
    prev1 = prev2; 
    prev2 = result; 
  } 
  return result; 
}; 
console.log(fibonacci(7)); // Output: 8 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="174">174. Check if a Number is a Deficient Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isDeficientNumber function determines whether a given number is a deficient number.</p>
<pre>
const isDeficientNumber = (num) => num > sumOfProperDivisors(num); 
console.log(isDeficientNumber(10));  // Output: true 
console.log(isDeficientNumber(28));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="175">175. Calculate the Distance between Two Points in 2D</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The distanceBetweenPoints function calculates the Euclidean distance between two points 
in a 2D plane. Given the coordinates of two points (x1, y1) and (x2, y2), it uses the 
formula sqrt((x2 - x1)^2 + (y2 - y1)^2) to compute the distance between them.</p>
<pre>
const distanceBetweenPoints = (x1, y1, x2, y2) => Math.sqrt((x2 - x1) ** 2 + (y2 - y1) ** 2); 
console.log(distanceBetweenPoints(0, 0, 3, 4));  // Output: 5 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="176">176. Check if a Number is an Abundant Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isAbundantNumber function determines whether a given number is an abundant number.</p>
<pre>
const isAbundantNumber = (num) => num < sumOfProperDivisors(num); 
console.log(isAbundantNumber(12));  // Output: true 
console.log(isAbundantNumber(28));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="177">177. Calculate the Volume of a Cube</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The cubeVolume function calculates the volume of a cube based on its side length. The 
formula for the volume of a cube is side^3, where side is the length of one side of 
the cube.</p>
<pre>
const cubeVolume = (side) => side ** 3; 
console.log(cubeVolume(5));  // Output: 125 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="178">178. Check if a String is a Valid Credit Card Number (Visa, MasterCard, Discover, American Express)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isValidCreditCard function uses a regular expression to validate a credit card number.</p>
<pre>
const isValidCreditCard = (card) => /^(?:4[0-9]{12}(?:[0-9]{3})?|5[1-5][0-9]{14}|6(?:011|5[0-9][0-9])[0-9]{12}|3[47][0-9]{13})$/.test(card); 
console.log(isValidCreditCard("4012-3456-7890-1234"));  // Output: true 
console.log(isValidCreditCard("1234-5678-9012-3456"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="179">179. Calculate the Perimeter of a Triangle</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The trianglePerimeter function calculates the perimeter of a triangle given its three 
side lengths. It simply adds up the lengths of all three sides and returns the result 
as the perimeter of the triangle.</p>
<pre>
const trianglePerimeter = (side1, side2, side3) => side1 + side2 + side3; 
console.log(trianglePerimeter(5, 10, 7));  // Output: 22 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="180">180. Check if a Number is a Vampire Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isVampireNumber function checks if a given number is a vampire number.</p>
<pre>
const isVampireNumber = (num) => { 
  const numStr = String(num); 
  const numLen = numStr.length; 
  const numDigits = [...numStr]; 
  const numFactors = getFactors(num); 
  for (const factor1 of numFactors) { 
    const factor2 = num / factor1; 
    if (factor1 % 10 === 0 && factor2 % 10 === 0) continue; 
    const factorStr = String(factor1) + String(factor2); 
    if (factorStr.length === numLen && areAnagrams(numDigits, [...factorStr])) { 
      return true; 
    } 
  } 
  return false; 
}; 
console.log(isVampireNumber(1260)); // Output: true 
console.log(isVampireNumber(1250)); // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="181">181. Find the Sum of Digits Raised to the Power of their Respective Position</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>sumOfDigitsRaisedToPower calculates the sum of digits raised to the power of their respective positions.</p>
<pre>
const sumOfDigitsRaisedToPower = (num) => { 
  const digits = [...String(num)].map(Number); 
  return digits.reduce((sum, digit, index) => sum + digit ** (index + 1), 0); 
}; 
console.log(sumOfDigitsRaisedToPower(12345));  // Output: 115 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="182">182. Check if a Number is a Duck Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isDuckNumber function checks whether a given number is a duck number. A duck number 
is a number that contains the digit "0" but does not start with "0".</p>
<pre>
const isDuckNumber = (num) => String(num).includes('0') && String(num)[0] !== '0'; 
console.log(isDuckNumber(1023));  // Output: true 
console.log(isDuckNumber(12345));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="183">183. Generate a Random Password</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The randomPassword function generates a random password of the specified length.</p>
<pre>
const randomPassword = (length) => Array.from({ length }, () 
  => Math.random().toString(36).charAt(2)).join(''); 
console.log(randomPassword(8));  // Output: "3klS0p9x" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="184">184. Calculate the Area of a Trapezoid</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The trapezoidArea function calculates the area of a trapezoid using the formula: 0.5 
* (base1 + base2) * height.</p>
<pre>
const trapezoidArea = (base1, base2, height) => 0.5 * (base1 + base2) * height; 
console.log(trapezoidArea(4, 8, 6));  // Output: 36 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="185">185. Check if a Number is a Kaprekar Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isKaprekarNumber function checks if a given number is a Kaprekar number.</p>
<pre>
const isKaprekarNumber = (num) => { 
  const square = num ** 2; 
  const squareStr = String(square); 
  const numStr = String(num);   
  const left = Number(squareStr.slice(0, numStr.length)); 
  const right = Number(squareStr.slice(-numStr.length)); 
  return left + right === num; 
}; 
console.log(isKaprekarNumber(9));  // Output: true 
console.log(isKaprekarNumber(297));  // Output: true 
console.log(isKaprekarNumber(45));   // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="186">186. Calculate the Volume of a Cone</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The coneVolume function calculates the volume of a cone using its base radius and height. 
It applies the formula for the volume of a cone: V = (1/3) * π * r² * h, where r is the 
radius of the base and h is the height of the cone.</p>
<pre>
const coneVolume = (radius, height) => (1 / 3) * Math.PI * radius ** 2 * height; 
console.log(coneVolume(5, 10));  // Output: 261.79938779914943 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="187">187. Check if a String is a Valid US Phone Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isValidUSPhoneNumber function uses a regular expression to validate US phone numbers.</p>
<pre>
const isValidUSPhoneNumber = (phone) => /^(?:(?:\+1\s?)?(?:\(?\d{3}\)?[\s.-]?)?\d{3}[\s.-]?\d{4})$/.test(phone); 
console.log(isValidUSPhoneNumber("+1 (123) 456-7890"));  // Output: true 
console.log(isValidUSPhoneNumber("123-456-7890"));  // Output: true 
console.log(isValidUSPhoneNumber("1-800-ABC-DEFG"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="188">188. Find the Sum of Digits Raised to the Power of their Respective Position (Up to 1000)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The sumOfDigitsRaisedToPowerUpToThousand function calculates the sum of numbers where 
each digit raised to the power of its respective position is equal to the number itself.</p>
<pre>
const sumOfDigitsRaisedToPowerUpToThousand = () => { 
  let sum = 0; 
  for (let i = 1; i <= 1000; i++) { 
    if (sumOfDigitsRaisedToPower(i) === i) { 
      sum += i; 
    } 
  } 
  return sum; 
}; 
console.log(sumOfDigitsRaisedToPowerUpToThousand());  // Output: 443839 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="189">189. Check if a Number is a Carol Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isCarolNumber function checks if a given number is a Carol number.</p>
<pre>
const isCarolNumber = (num) => { 
  const carolPrime = (2 ** num) - 1; 
  return isPrime(num) && isPerfectSquare(carolPrime); 
}; 
console.log(isCarolNumber(7));  // Output: true 
console.log(isCarolNumber(47));  // Output: true 
console.log(isCarolNumber(6));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="190">190. Check if a Number is a Catalan Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isCatalanNumber function checks if a given number is a Catalan number. It first 
ensures that the input number is a non-negative integer.</p>
<pre>
const isCatalanNumber = (num) => num >= 0 && Number.isInteger(num) && num 
  === ((factorial(2 * num)) / (factorial(num + 1) * factorial(num))); 
console.log(isCatalanNumber(5));  // Output: true 
console.log(isCatalanNumber(10));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="191">191. Calculate the Volume of a Cuboid</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The cuboidVolume function calculates the volume of a cuboid given its length, width, and height.</p>
<pre>
const cuboidVolume = (length, width, height) => length * width * height; 
console.log(cuboidVolume(5, 10, 8));  // Output: 400 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="192">192. Check if a Number is a Dudeney Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The isDudeneyNumber function checks if a number is a Dudeney number.</p>
<pre>
const isDudeneyNumber = (num) => num === sumOfDigitsCube(num); 
console.log(isDudeneyNumber(512));  // Output: true 
console.log(isDudeneyNumber(64));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="193">193. Generate a Random Color (Hexadecimal Format)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Generate a random color in hexadecimal format (#RRGGBB).</p>
<pre>
const randomColorHex = () => `#${Math.floor(Math.random() * 16777215).toString(16)}`; 
console.log(randomColorHex());  // Output: "#92b008" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="194">194. Calculate the Area of a Circle Sector</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the area of a circle sector given the radius and the central angle in degrees.</p>
<pre>
const circleSectorArea = (radius, angle) => (angle / 360) * Math.PI * radius ** 2; 
console.log(circleSectorArea(5, 90));  // Output: 11.780972450961725 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="195">195. Calculate the Area of a Regular Polygon</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the area of a regular polygon given the side length and the number of sides.</p>
<pre>
const regularPolygonArea = (sideLength, numOfSides) => (numOfSides * sideLength ** 2) 
  / (4 * Math.tan(Math.PI / numOfSides)); 
console.log(regularPolygonArea(5, 6));  // Output: 64.9519052838329 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="196">196. Remove Duplicates from Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Remove duplicates from an array while preserving the order of the elements.</p>
<pre>
const removeDuplicates = (arr) => [...new Set(arr)]; 
console.log(removeDuplicates([1, 2, 3, 3, 4, 4, 5, 5, 6])); // Output: [ 1, 2, 3, 4, 5, 6 ] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="197">197. Calculate the Area of an Ellipse</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the area of an ellipse using its semi-major axis length (a) and semi-minor axis length (b).</p>
<pre>
const ellipseArea = (a, b) => Math.PI * a * b; 
console.log(ellipseArea(5, 10));  // Output: 157.07963267948966 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="198">198. Check if a Number is a Leyland Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a Leyland number.</p>
<pre>
const isLeylandNumber = (num) => { 
  let found = false; 
  for (let x = 2; x <= Math.floor(Math.pow(num, 1 / 3)) && !found; x++) { 
    for (let y = x + 1; x * y <= num && !found; y++) { 
      if (Math.pow(x, y) + Math.pow(y, x) === num) { 
        found = true; 
      } 
    } 
  } 
  return found; 
}; 
console.log(isLeylandNumber(17));  // Output: true 
console.log(isLeylandNumber(30));  // Output: true 
console.log(isLeylandNumber(100));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="199">199. Generate a Random UUID</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Generate a random Universally Unique Identifier (UUID).</p>
<pre>
const randomUUID = () => { 
  return "xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx".replace(/[xy]/g, function(c) { 
    const r = Math.random() * 16 | 0; 
    const v = c === "x" ? r : (r & 0x3 | 0x8); 
    return v.toString(16); 
  }); 
}; 
console.log(randomUUID());  // Output: "a0f768f5-6bf2-4f6b-a512-c9121ea1b44a" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="200">200. Check if a String is a Valid IPv6 Address</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given string represents a valid IPv6 address.</p>
<pre>
const isValidIPv6 = (ip) => /^([0-9a-fA-F]{1,4}:){7}[0-9a-fA-F]{1,4}$/.test(ip); 
console.log(isValidIPv6("2001:0db8:85a3:0000:0000:8a2e:0370:7334"));  // Output: true 
console.log(isValidIPv6("2001:0db8:85a3::8a2e:0370:7334"));  // Output: true 
console.log(isValidIPv6("256.0.0.0"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="201">201. Calculate the Area of a Parallelogram</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the area of a parallelogram using the given base and height.</p>
<pre>
const parallelogramArea = (base, height) => base * height; 
console.log(parallelogramArea(5, 10));  // Output: 50 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="202">202. Check if a String is a Valid MAC Address</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given string is a valid MAC address.</p>
<pre>
const isValidMACAddress = (mac) => /^([0-9A-Fa-f]{2}[:-]){5}([0-9A-Fa-f]{2})$/.test(mac); 
console.log(isValidMACAddress("00:1A:2B:3C:4D:5E"));  // Output: true 
console.log(isValidMACAddress("00:1A:2B:3C:4D"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="203">203. Convert RGB to HSL (Hue, Saturation, Lightness)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Convert an RGB color value to its corresponding HSL representation (Hue, Saturation, Lightness).</p>
<pre>
const rgbToHSL = (r, g, b) => { 
  [r, g, b] = [r, g, b].map(val => val / 255); 
  const [max, min] = [Math.max(r, g, b), Math.min(r, g, b)]; 
  let h = (max !== min) ? ((max === r ? g - b : (max === g ? b - r : r - g)) / (max - min) 
    + (max === g ? 2 : (max === b ? 4 : 0))) / 6 : 0; 
  let s = (max !== min) ? (l => l > 0.5 ? (max - min) / (2 - max - min) : (max - min) / (max + min))(l) : 0; 
  let l = (max + min) / 2; 
  return { h: Math.round(h * 360), s: Math.round(s * 100), l: Math.round(l * 100) }; 
}; 
console.log(rgbToHSL(255, 0, 0)); // Output: { h: 0, s: 100, l: 50 } 
console.log(rgbToHSL(0, 255, 0)); // Output: { h: 120, s: 100, l: 50 } 
console.log(rgbToHSL(0, 0, 255)); // Output: { h: 240, s: 100, l: 50 } 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="204">204. Check if a Number is a Pandigital Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a pandigital number.</p>
<pre>
const isPandigitalNumber = (num) => { 
  const numStr = String(num); 
  const digits = new Set(numStr); 
  return digits.size === numStr.length && !digits.has('0') && digits.size === Math.max(...numStr) - '0'; 
}; 
console.log(isPandigitalNumber(123456789));  // Output: true 
console.log(isPandigitalNumber(987654321));  // Output: true 
console.log(isPandigitalNumber(1023456789));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="205">205. Calculate the Sum of Proper Divisors of a Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the sum of proper divisors of a given number.</p>
<pre>
const sumOfProperDivisors = (num) => { 
  let sum = 0; 
  for (let i = 1; i <= Math.sqrt(num); i++) { 
    if (num % i === 0) { 
      sum += i; 
      if (num / i !== i) { 
        sum += num / i; 
      } 
    } 
  } 
  return sum - num; 
}; 
console.log(sumOfProperDivisors(28));  // Output: 28 
console.log(sumOfProperDivisors(12));  // Output: 16 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="206">206. Find the Least Common Multiple (LCM) of an Array of Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the least common multiple (LCM) of an array of numbers.</p>
<pre>
const lcmArray = (arr) => arr.reduce((lcm, num) => lcm * num / gcdArray(arr), 1); 
console.log(lcmArray([2, 3, 4]));  // Output: 12 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="20">207. Calculate the Sum of Squares of First n Natural Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the sum of the squares of the first n natural numbers.</p>
<pre>
const sumOfSquares = (n) => (n * (n + 1) * (2 * n + 1)) / 6; 
console.log(sumOfSquares(5));  // Output: 55 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="208">208. Check if a Number is a Powerful Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a powerful number.</p>
<pre>
const isPowerfulNumber = (num) => { 
  const factors = primeFactors(num); 
  return new Set(factors).size === factors.length; 
}; 
console.log(isPowerfulNumber(16));  // Output: true 
console.log(isPowerfulNumber(36));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="209">209. Find the Product of Digits of a Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the product of the digits of a given number.</p>
<pre>
const productOfDigits = (num) => [...String(num)].reduce((product, digit) => product * Number(digit), 1); 
console.log(productOfDigits(12345));  // Output: 120 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="210">210. Check if a Number is a Practical Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a practical number.</p>
<pre>
const isPracticalNumber = (num) => { 
  const factors = primeFactors(num); 
  for (let i = 2; i <= factors.length; i++) { 
    if (sumOfArray(combinations(factors, i)) !== num) { 
      return false; 
    } 
  } 
  return true; 
}; 
console.log(isPracticalNumber(6));  // Output: true 
console.log(isPracticalNumber(12));  // Output: true 
console.log(isPracticalNumber(14));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="211">211. Calculate the Sum of Cubes of First n Natural Numbers</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the sum of the cubes of the first n natural numbers.</p>
<pre>
const sumOfCubes = (n) => Math.pow((n * (n + 1)) / 2, 2); 
console.log(sumOfCubes(5));  // Output: 225 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="212">212. Check if a Number is a Strange Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a strange number.</p>
<pre>
const isStrangeNumber = (num) => { 
  const factors = primeFactors(num); 
  return factors.every((factor) => sumOfDigits(factor) === sumOfDigits(num)); 
}; 

console.log(isStrangeNumber(18));  // Output: true 
console.log(isStrangeNumber(22));  // Output: true 
console.log(isStrangeNumber(20));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="213">213. Check if a Number is a Tau Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a Tau number.</p>
<pre>
const isTauNumber = (num) => { 
  const factors = primeFactors(num); 
  return factors.some((factor) => sumOfDigits(factor) === sumOfDigits(num)); 
}; 

console.log(isTauNumber(15));  // Output: true 
console.log(isTauNumber(9));  // Output: true 
console.log(isTauNumber(25));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="214">214. Generate a Random Alphanumeric String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Generate a random alphanumeric string of a given length.</p>
<pre>
const randomAlphanumericString = (length) => { 
  const characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789'; 
  let result = ''; 
  for (let i = 0; i < length; i++) { 
    result += characters.charAt(Math.floor(Math.random() * characters.length)); 
  } 
  return result; 
};

console.log(randomAlphanumericString(8));  // Output: "Yw83XmLb" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="215">215. Calculate the Area of a Regular Hexagon</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the area of a regular hexagon using its side length.</p>
const regularHexagonArea = (sideLength) => (3 * Math.sqrt(3) * sideLength ** 2) / 2; 

console.log(regularHexagonArea(5));  // Output: 64.9519052838329 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="216">216. Calculate the Sum of Divisors of a Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the sum of divisors of a given number.</p>
<pre>
const sumOfDivisors = (num) => sumOfArray(divisors(num)); 

console.log(sumOfDivisors(28));  // Output: 56 
console.log(sumOfDivisors(12));  // Output: 28 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="217">217. Check if a Number is a Zeisel Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a Zeisel number.</p>
<pre>
const isZeiselNumber = (num) => { 
  const factors = primeFactors(num); 
  return factors.every((factor) => isPrime(factor + 1)); 
}; 

console.log(isZeiselNumber(1050));  // Output: true 
console.log(isZeiselNumber(10));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="218">218. Check if a Number is a Reversible Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a reversible number.</p>
<pre>
const isReversibleNumber = (num) => { 
  const reversedNum = Number(String(num).split('').reverse().join('')); 
  return num + reversedNum === sumOfDigits(num); 
}; 
console.log(isReversibleNumber(36));  // Output: true 
console.log(isReversibleNumber(45));  // Output: true 
console.log(isReversibleNumber(10));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="219">219. Calculate the Circumference of a Circle</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the circumference of a circle using its radius.</p>
<pre>
const circleCircumference = (radius) => 2 * Math.PI * radius; 
console.log(circleCircumference(5));  // Output: 31.41592653589793 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="220">220. Find the Shortest Word in a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the shortest word in a given string.</p>
<pre>
const shortestWord = (str) => str.split(' ').reduce((shortest, word) 
  => (word.length < shortest.length ? word : shortest), ''); 
console.log(shortestWord("This is a test sentence"));  // Output: "a" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="221">221. Find the Longest Word Length in a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the length of the longest word in a given string.</p>
<pre>
const longestWordLength = (str) => Math.max(...str.split(' ').map(word => word.length)); 
console.log(longestWordLength("This is a test sentence")); // Output: 8 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="222">222. Find the Sum of Proper Divisors of a Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the sum of the proper divisors of a given number.</p>
<pre>
const sumOfProperDivisors = (num) => sumOfArray(divisors(num)) - num; 
console.log(sumOfProperDivisors(28));  // Output: 28 
console.log(sumOfProperDivisors(12));  // Output: 16 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="223">223. Check if a Number is a Unitary Perfect Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a unitary perfect number.</p>
<pre>
const isUnitaryPerfectNumber = (num) => num === sumOfUnitaryDivisors(num); 
console.log(isUnitaryPerfectNumber(18));  // Output: true 
console.log(isUnitaryPerfectNumber(28));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="224">224. Calculate the Perimeter of a Regular Polygon</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the perimeter of a regular polygon using its side length and the number of sides.</p>
<pre>
const regularPolygonPerimeter = (sideLength, numSides) => sideLength * numSides; 
console.log(regularPolygonPerimeter(5, 6));  // Output: 30 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="225">225. Calculate the Area of an Equilateral Triangle</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the area of an equilateral triangle using its side length.</p>
<pre>
const equilateralTriangleArea = (sideLength) => (Math.sqrt(3) * sideLength ** 2) / 4; 
console.log(equilateralTriangleArea(5));  // Output: 10.825317547305486 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="226">226. Check if a Number is a Harshad Smith Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is both a Harshad number and a Smith number.</p>
<pre>
const isHarshadSmithNumber = (num) => isHarshadNumber(num) && isSmithNumber(num); 
console.log(isHarshadSmithNumber(22));  // Output: true 
console.log(isHarshadSmithNumber(10));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="227">227. Check if a Number is a Perfect Power</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a perfect power.</p>
<pre>
const isPerfectPower = (num) => { 
  for (let i = 2; i * i <= num; i++) { 
    let power = 2; 
    let result = i * i; 
    while (result <= num) { 
      if (result === num) { 
        return true; 
      } 
      result *= i; 
      power++; 
    } 
  }
  return false; 
}; 

console.log(isPerfectPower(64));   // Output: true 
console.log(isPerfectPower(25));   // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="228">228. Calculate the Sum of Digits Raised to Their Own Power</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the sum of digits raised to their own power for a given number and power.</p>
<pre>
const sumOfDigitsToPower = (num, power) => sumOfDigitsRaisedToPower(num, power); 

console.log(sumOfDigitsToPower(123, 3));  // Output: 36 
console.log(sumOfDigitsToPower(4150, 5));  // Output: 4150 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="229">229. Check if a Number is a Dudeney Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a Dudeney number.</p>
<pre>
const isDudeneyNumber = (num) => Math.cbrt(num) === sumOfDigits(num); 

console.log(isDudeneyNumber(512));  // Output: true 
console.log(isDudeneyNumber(27));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="230">230. Calculate the Area of a Regular Pentagon</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the area of a regular pentagon using its side length.</p>
<pre>
const regularPentagonArea = (sideLength) => (1 / 4) * Math.sqrt(5 * (5 + 2 * Math.sqrt(5))) * sideLength ** 2; 
console.log(regularPentagonArea(5));  // Output: 43.01193501472417 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="231">231. Calculate the Volume of a Pyramid</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the volume of a pyramid using its base area and height.</p>
<pre>
const pyramidVolume = (baseArea, height) => (1 / 3) * baseArea * height; 
console.log(pyramidVolume(25, 10));  // Output: 83.33333333333333 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="232">232. Check if a Number is a Wedderburn-Etherington Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a Wedderburn-Etherington number.</p>
<pre>
const isWedderburnEtheringtonNumber = (num) => { 
  const primes = primeFactors(num); 
  const factorials = primes.map((prime) => factorial(prime - 1)); 
  return factorials.reduce((product, factorial) => product * factorial, 1) === factorial(num); 
}; 
console.log(isWedderburnEtheringtonNumber(6));   // Output: true 
console.log(isWedderburnEtheringtonNumber(12));   // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="233">233. Calculate the Surface Area of a Cube</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the surface area of a cube using its side length.</p>
<pre>
const cubeSurfaceArea = (sideLength) => 6 * sideLength ** 2; 
console.log(cubeSurfaceArea(5));  // Output: 150 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="234">234. Check if a Number is a Pluperfect Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a pluperfect number.</p>
<pre>
const isPluperfectNumber = (num) => num === sumOfDivisors(sumOfDivisors(num)) - num; 
console.log(isPluperfectNumber(28));  // Output: true 
console.log(isPluperfectNumber(20));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="235">235. Calculate the Area of a Regular Octagon</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the area of a regular octagon using its side length.</p>
<pre>
const regularOctagonArea = (sideLength) => 2 * (1 + Math.sqrt(2)) * sideLength ** 2; 
console.log(regularOctagonArea(5));  // Output: 86.60254037844387 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="236">236. Check if a Number is a Repunit Number</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a repunit number.</p>
<pre>
const isRepunitNumber = num => /^1+$/.test(num.toString()); 
console.log(isRepunitNumber(111)); // Output: true 
console.log(isRepunitNumber(11)); // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="237">237. Calculate the Volume of a Ellipsoid</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the volume of an ellipsoid using its semi-axes lengths.</p>
<pre>
const ellipsoidVolume = (a, b, c) => (4 / 3) * Math.PI * a * b * c; 
console.log(ellipsoidVolume(5, 3, 2));  // Output: 125.66370614359172 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="238">238. Check if a String is a Valid URL (Alternative Approach)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given string is a valid URL using an alternative approach.</p>
<pre>
const isValidURLAlt = (url) => /^(ftp|http|https):\/\/[^ "]+$/.test(url); 
console.log(isValidURLAlt("https://www.example.com"));  // Output: true 
console.log(isValidURLAlt("invalid url"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="239">239. Check if a String is a Valid Tax Identification Number (TIN)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given string is a valid Tax Identification Number (TIN).</p>
<pre>
const isValidTIN = (tin) => /^[A-Z]{2}\d{6}[A-Z\d]{2}$/.test(tin); 
console.log(isValidTIN("AB123456CD"));  // Output: true 
console.log(isValidTIN("invalid tin"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="240">240. Check if a String is a Valid ISBN (International Standard Book Number)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given string is a valid International Standard Book Number (ISBN).</p>
<pre>
const isValidISBN = (isbn) => /^(?:\d{9}[\dX]|(?:\d{3}-){2}\d{1}[\dX])$/.test(isbn);  
console.log(isValidISBN("123456789"));  // Output: true 
console.log(isValidISBN("invalid isbn"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="241">241. Check if a String is a Valid IP Address</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given string is a valid IP address.</p>
<pre>
const isValidIPAddress = (ip) => /^((25[0-5]|2[0-4]\d|[0-1]?\d{1,2})\.){3}(25[0-5]|2[0-4]\d|[0-1]?\d{1,2})$/.test(ip); 
console.log(isValidIPAddress("192.168.1.1"));  // Output: true 
console.log(isValidIPAddress("invalid ip"));  // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="242">242. Reverse a String (Using Recursion)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Reverse a string using a recursive approach.</p>
<pre>
const reverseStringRecursive = str => str === '' ? '' : reverseStringRecursive(str.substr(1)) 
  + str.charAt(0); 
console.log(reverseStringRecursive('hello')); // Output: 'olleh' 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="243">243. Count the Occurrences of Each Element in an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Count the occurrences of each element in a given array and return the counts in an object.</p>
<pre>
const countOccurrences = arr => arr.reduce((acc, curr) => (acc[curr] = (acc[curr] || 0) + 1, acc), {}); 
console.log(countOccurrences([1, 2, 1, 3, 2, 4, 1])); // Output: { '1': 3, '2': 2, '3': 1, '4': 1 } 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="244">244. Check if Two Arrays are Equal (Shallow Comparison)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if two arrays are equal through a shallow comparison of their elements.</p>
<pre>
const arraysAreEqual = (arr1, arr2) => arr1.length === arr2.length && arr1.every((val, index) 
  => val === arr2[index]); 
console.log(arraysAreEqual([1, 2, 3], [1, 2, 3])); // Output: true 
console.log(arraysAreEqual([1, 2, 3], [1, 2, 4])); // Output: false 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="245">245. Find the Minimum Value in an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Find the minimum value in a given array of numbers.</p>
<pre>
const findMinValue = arr => Math.min(...arr); 
console.log(findMinValue([2, 7, 1, 9, 4])); // Output: 1 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="246">246. Flatten an Array of Nested Arrays (Using concat)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Flatten an array of nested arrays using the concat method.</p>
<pre>
const flattenArray = arr => [].concat(...arr); 
console.log(flattenArray([[1, 2], [3, 4], [5, 6]])); // Output: [1, 2, 3, 4, 5, 6] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="247">247. Find the Average of Numbers in an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the average of numbers in a given array.</p>
<pre>
const findAverage = arr => arr.reduce((sum, num) => sum + num, 0) / arr.length; 
console.log(findAverage([1, 2, 3, 4, 5])); // Output: 3 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="248">248. Sum the Squares of Numbers in an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Calculate the sum of the squares of numbers in a given array.</p>
<pre>
const sumSquares = arr => arr.reduce((sum, num) => sum + num ** 2, 0); 
console.log(sumSquares([1, 2, 3, 4, 5])); // Output: 55 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="249">249. Check if a String is a Palindrome (Ignoring Non-Alphanumeric Characters)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given string is a palindrome, ignoring non-alphanumeric characters and 
considering case-insensitivity.</p>
<pre>
const isPalindromeIgnoringNonAlphaNumeric = str => { 
const cleanedStr = str.replace(/[^a-zA-Z0-9]/g, '').toLowerCase(); 
return cleanedStr === cleanedStr.split('').reverse().join(''); 
}; 
console.log(isPalindromeIgnoringNonAlphaNumeric("A man, a plan, a canal, Panama!")); // Output: true 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="250">250. Shuffle an Array (Using Fisher-Yates Algorithm)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Shuffle the elements of an array using the Fisher-Yates shuffle algorithm. 
<pre>
const shuffleArrayFisherYates = arr => { 
for (let i = arr.length - 1; i > 0; i--) { 
const j = Math.floor(Math.random() * (i + 1)); 
[arr[i], arr[j]] = [arr[j], arr[i]]; 
} 
return arr; 
}; 
console.log(shuffleArrayFisherYates([1, 2, 3, 4, 5])); // Output: [3, 1, 4, 2, 5] (randomly shuffled) 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="251">251. Sort an Array of Objects by a Specific Property</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Sort an array of objects based on a specific property value. 
<pre>
const sortByProperty = (arr, prop) => arr.sort((a, b) => a[prop] - b[prop]); 
const data = [{ name: 'Alice', age: 25 }, { name: 'Bob', age: 20 }, { name: 'Carol', age: 30 }]; 
console.log(sortByProperty(data, 'age'));  // Output: [{ name: 'Bob', age: 20 }, { name: 'Alice', age: 25 }, { name: 'Carol', age: 30 }] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="252">252. Reverse Words in a Sentence</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Reverse words in a sentence. 
<pre>
const originalSentence = "Hello world, how are you?"; 
const reversedSentence = reverseWords(originalSentence); 
console.log(reversedSentence); // Output: "you? are how world, Hello" 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="253">253. Find the Median of Numbers in an Array</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Find the median value of numbers in a given array. 
<pre>
const findMedian = arr => { 
const sortedArr = arr.sort((a, b) => a - b); 
const middle = Math.floor(sortedArr.length / 2); 
return sortedArr.length % 2 === 0 ? (sortedArr[middle - 1] + sortedArr[middle]) / 2 : sortedArr[middle]; 
}; 
console.log(findMedian([1, 3, 2, 4, 5])); // Output: 3 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="254">254. Count the Vowels in a String</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Count the number of vowels in a given string. 
<pre>
const countVowels = str => (str.match(/[aeiou]/gi) || []).length; 
console.log(countVowels('Hello, how are you?')); // Output: 7 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="255">255. Check if a Number is a Tribonacci Number (Alternative Approach)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given number is a Tribonacci number using an alternative approach.</p>
<pre>
const isTribonacciNumberAlt = num => [0, 0, 1].concat([...Array(num)]).slice(3).map((_, i, arr)
  => arr[i - 3] + arr[i - 2] + arr[i - 1]).includes(num);

console.log(isTribonacciNumberAlt(21));  // Output: true
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="256">256. Calculate the Fibonacci Sequence (Up to N Terms)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Generate the Fibonacci sequence up to a given number of terms n. 
<pre>
const fibonacciSequence = n => [...Array(n)].reduce((fibSeq, _, i) 
  => fibSeq.concat(i > 1 ? fibSeq[i - 1] + fibSeq[i - 2] : i), [0, 1]); 
console.log(fibonacciSequence(10));  // Output: [0, 1, 1, 2, 3, 5, 8, 13, 21, 34] 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="257">257. Find the ASCII Value of a Character</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Get the ASCII value of a given character.</p>
<pre>
const getAsciiValue = char => char.charCodeAt(0);
console.log(getAsciiValue('A')); // Output: 65
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="258">258. Check if a String is an Isogram (No Repeating Characters)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Check if a given string is an isogram, meaning it has no repeating characters (case-insensitive).</p>
<pre>
const isIsogram = str => new Set(str.toLowerCase()).size === str.length;

console.log(isIsogram('hello'));  // Output: false
console.log(isIsogram('world'));  // Output: true
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="259">259. Calculate the Hamming Distance of Two Strings (Equal Length)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Calculate the Hamming distance between two equal-length strings, which is the count of 
differing characters at corresponding positions. 
<pre>
const hammingDistance = (str1, str2) => [...str1].reduce((distance, char, i) => distance 
  + (char !== str2[i]), 0); 
console.log(hammingDistance('karolin', 'kathrin')); // Output: 3 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="260">260. Calculate the Distance between Two Points in a 2D Plane</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Calculate the Euclidean distance between two points in a 2D plane using the Pythagorean theorem. 
<pre>
const calculateDistance = ([x1, y1], [x2, y2]) => Math.sqrt((x2 - x1) ** 2 + (y2 - y1) ** 2); 
console.log(calculateDistance([0, 0], [3, 4]));  // Output: 5 (Pythagorean triple: 3^2 + 4^2 = 5^2) 
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4 id="261">261. Check if a String is a Positive Number (No Sign or Decimal Allowed)</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Check if a given string represents a positive integer without any sign or decimal point. 
<pre>
const isPositiveNumber = str => /^[0-9]+$/.test(str); 
console.log(isPositiveNumber('123'));  // Output: true 
console.log(isPositiveNumber('-123'));  // Output: false 
</pre>
