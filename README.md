# JS-1Liners-JS
JavaScript 1 Liners worth noting.

1. Convert Celsius to Fahrenheit

<p>celsiusToFahrenheit allows you to convert a temperature from Celsius to Fahrenheit. It takes a value in 
Celsius as input and uses the formula (Celsius * 9/5) + 32 to perform the conversion.exadecimal representation.</p>
<pre>
const celsiusToFahrenheit = (celsius) => (celsius * 9/5) + 32; celsiusToFahrenheit(30); // Result: 86
</pre>

2. Get Value of a brower Cookie
<p>Retrieve the value of a cookie by accessing with document.cookie.</p>
<pre>
const cookie = name => `; ${document.cookie}`.split(`; ${name}=`).pop().split(';').shift(); 
cookie('_ga'); 
// Result: "GA1.2.1929736587.1601974046" 
</pre>

3. Convert RGB to Hex
<p>rgbToHex enables you to convert RGB (Red, Green, Blue) values to their corresponding hexadecimal representation.</p>
<pre>
const rgbToHex = (r, g, b) => 
"#" + ((1 << 24) + (r << 16) + (g << 8) + b).toString(16).slice(1); 
rgbToHex(0, 51, 255); 
// Result: #0033ff 
</pre>

4. Copy to Clipboard
<p>Easily copy any text to clipboard using navigator.clipboard.writeText.</p>
<pre>
const copyToClipboard = (text) => navigator.clipboard.writeText(text); 
copyToClipboard("Hello World"); 
</pre>

5. Check if Date is Valid
<p>Use the following snippet to check if a given date is valid or not.</p>
<pre>
const isDateValid = (...val) => !Number.isNaN(new Date(...val).valueOf()); 
isDateValid("December 17, 1995 03:24:00"); 
// Result: true 
</pre>

7. Find the day of year
Find which is the day by a given date. 
<pre>
const dayOfYear = (date) => 
Math.floor((date - new Date(date.getFullYear(), 0, 0)) / 1000 / 60 / 60 / 24); 
dayOfYear(new Date()); // Result: 272 
</pre>

7. Capitalise a String
Javascript doesn't have an inbuilt capitalise function, so we can use the following code for the purpose. 
<pre>
const capitalize = str => str.charAt(0).toUpperCase() + str.slice(1) 
capitalize("follow for more") 
// Result: Follow for more 
</pre>

8. Find the number of days between two days
Find the days between 2 given days using the following snippet. 
<pre>
const dayDif = (date1, date2) => Math.ceil(Math.abs(date1.getTime() - date2.getTime()) / 86400000) 
dayDif(new Date("2020-10-21"), new Date("2021-10-22")) 
// Result: 366 
</pre>

9. Clear All Cookies
You can easily clear all cookies stored in a web page by accessing the cookie using document.cookie and clearing it. 
<pre>
const clearCookies = document.cookie.split(';').forEach(cookie => document.cookie = cookie.replace(/^ +/, '').replace(/=.*/, `=;expires=${new Date(0).toUTCString()};path=/`)); 
</pre>

10. Generate Random Hex
You can generate random hex colors with Math.random and padEnd properties. 
<pre>
const randomHex = () => `#${Math.floor(Math.random() * 0xffffff).toString(16).padEnd(6, "0")}`; 
console.log(randomHex()); 
// Result: #92b008 
</pre>

11. Get Query Params from URL
You can easily retrieve query params from a url either by passing window.location or the raw URL goole.com?search=easy&page=3 
<pre>
const getParameters = (URL) => { 
URL = JSON.parse('{"' + decodeURI(URL.split("?")[1]).replace(/"/g, '\\"').replace(/&/g, '","').replace(/=/g, '":"') +'"}'); 
return JSON.stringify(URL); 
}; 
getParameters(window.location) 
// Result: { search : "easy", page : 3 } 
</pre>

12. Log Time from Date
We can log time, in the format hour::minutes::seconds from a given date. 
<pre>
const timeFromDate = date => date.toTimeString().slice(0, 8); 
console.log(timeFromDate(new Date(2021, 0, 10, 17, 30, 0))); 
// Result: "17:30:00" 
</pre>

13. Check if a number is even or odd
A simple JavaScript function named "isEven" determines if a number is even or odd. It takes a "num" as input and returns true if even, false if odd. 
<pre>
const isEven = num => num % 2 === 0; 
console.log(isEven(2)); 
// Result: True 
</pre>

14. Find Average of Numbers
Find the average between multiple numbers using reduce method. 
<pre>
const average = (...args) => args.reduce((a, b) => a + b) / args.length; 
average(1, 2, 3, 4); 
// Result: 2.5 
</pre>

15. Scroll to Top
You can use window.scrollTo(0, 0) method to automatic scroll to top. Set both x and y as 0. 
<pre>
const goToTop = () => window.scrollTo(0, 0); 
goToTop(); 
</pre>

16. Reverse a string
You can easily reverse a string using split, reverse and join methods. 
<pre>
const reverse = str => str.split('').reverse().join(''); 
reverse('hello world'); 
// Result: 'dlrow olleh' 
</pre>

17. Check if array is empty
You can check if an array if empty with this snippet. 
<pre>
const isNotEmpty = arr => Array.isArray(arr) && arr.length > 0; 
isNotEmpty([1, 2, 3]); 
// Result: true 
</pre>

18. Get Selected Text
Get the text the user has select using inbuilt getSelection property. 
<pre>
const getSelectedText = () => window.getSelection().toString(); 
getSelectedText(); 
</pre>

19. Shuffle an Array
Shuffling an array is super easy with sort and random methods. 
<pre>
const shuffleArray = (arr) => arr.sort(() => 0.5 - Math.random()); 
console.log(shuffleArray([1, 2, 3, 4])); 
// Result: [ 1, 4, 3, 2 ] 
</pre>

20. Detect Dark Mode
Check if a user's device is in dark mode with the following code. 
<pre>
const isDarkMode = window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches 
console.log(isDarkMode) // Result: True or False 
</pre>

21. Remove Duplicated from Array
You can easily remove duplicates with Set in JavaScript. Its a life saver. 
<pre>
const removeDuplicates = (arr) => [...new Set(arr)]; 
console.log(removeDuplicates([1, 2, 3, 3, 4, 4, 5, 5, 6])); 
// Result: [ 1, 2, 3, 4, 5, 6 ] 
</pre>

22. Get the Length of a String
getLength efficiently calculates the length of a given string using .length property. 
<pre>
const getLength = (str) => str.length; 
getLength("Hello, world!"); 
// Result: 13 
</pre>

23. Calculate the Area of a Circle
Calculate the area of a circle given its radius. 
<pre>
const calculateCircleArea = (radius) => Math.PI * Math.pow(radius, 2); 
calculateCircleArea(5); 
// Result: 78.53981633974483 
</pre>

24. Check if a Number is Prime
Determine if a given number is a prime number. 
<pre>
const isPrime = (num) => { 
if (num <= 1) return false; 
for (let i = 2; i <= Math.sqrt(num); i++) { 
if (num % i === 0) return false; 
} 
return true; 
}; 
isPrime(13); 
// Result: true 
</pre>

25. Count Occurrences of a Character in a String
<pre>
Count the occurrences of a specific character in a given string. 
const countOccurrences = (str, char) => str.split(char).length - 1; 
countOccurrences("banana", "a"); 
// Result: 3 
</pre>

26. Remove Leading and Trailing Whitespaces
Remove leading and trailing whitespaces from a given string. 
<pre>
const removeWhitespaces = (str) => str.trim(); 
removeWhitespaces(" Hello, world! "); 
// Result: "Hello, world!" 
</pre>

27. Generate a Random Number within a Range
Generate a random integer within a specified range. 
<pre>
const randomInRange = (min, max) => Math.floor(Math.random() * (max - min + 1)) + min; 
randomInRange(1, 10); 
// Result: Random number between 1 and 10 (inclusive) 
</pre>

28. Convert Seconds to HH:MM:SS Format
Convert a given number of seconds into the "hours:minutes:seconds" format. 
<pre>
const secondsToHHMMSS = (seconds) => { 
const pad = (num) => String(num).padStart(2, '0'); 
const hours = Math.floor(seconds / 3600); 
const minutes = Math.floor((seconds % 3600) / 60); 
const secs = seconds % 60; 
return `${pad(hours)}:${pad(minutes)}:${pad(secs)}`; 
}; 
secondsToHHMMSS(3660); // Result: "01:01:00" 
</pre>

29. Get the Last Element of an Array
Retrieve the last element of a given array. 
<pre>
const getLastElement = (arr) => arr[arr.length - 1]; 
getLastElement([1, 2, 3, 4]); 
// Result: 4 
</pre>

30. Sort an Array of Numbers in Ascending Order
Sort a given array of numbers in ascending order. 
<pre>
const sortAscending = (arr) => arr.slice().sort((a, b) => a - b); 
sortAscending([3, 1, 4, 1, 5, 9, 2, 6, 5, 3]); 
// Result: [1, 1, 2, 3, 3, 4, 5, 5, 6, 9] 
</pre>

31. Check if a String is Palindrome
Determine if a given string is a palindrome. 
<pre>
const isPalindrome = (str) => str === str.split('').reverse().join(''); 
isPalindrome("level"); 
// Result: true 
</pre>

32. Calculate Factorial of a Number
Calculate the factorial of a given number. 
<pre>
const factorial = (num) => { 
if (num === 0 || num === 1) return 1; 
return num * factorial(num - 1); 
}; 
factorial(5); 
// Result: 120 
</pre>

33. Sum all Numbers in an Array
Calculate the sum of all numbers in a given array. 
<pre>
const sumArray = (arr) => arr.reduce((acc, val) => acc + val, 0); 
sumArray([1, 2, 3, 4, 5]); 
// Result: 15 
</pre>

34. Find the Maximum Value in an Array
Find the maximum value in a given array of numbers. 
<pre>
const findMax = (arr) => Math.max(...arr); 
findMax([10, 5, 8, 20, 3]); 
// Result: 20 
</pre>

35. Get the Current Date in DD/MM/YYYY Format
Get the current date in the "DD/MM/YYYY" format. 
<pre>
const getCurrentDate = () => { 
const date = new Date(); 
const day = String(date.getDate()).padStart(2, '0'); 
const month = String(date.getMonth() + 1).padStart(2, '0'); 
const year = date.getFullYear(); 
return `${day}/${month}/${year}`; 
}; 
getCurrentDate(); // Result: "02/08/2023" 
</pre>

36. Calculate the Power of a Number
Calculate the result of raising a given base to a specified exponent. 
<pre>
const power = (base, exponent) => Math.pow(base, exponent); 
power(2, 5); // Result: 32 
</pre>

37. Convert String to Number
Convert a given string to a numeric value (float or integer). 
<pre>
const stringToNumber = (str) => parseFloat(str); 
stringToNumber("3.14"); // Result: 3.14 
</pre>

38. Find the First N Fibonacci Numbers
Generate the first N Fibonacci numbers. 
<pre>
const fibonacci = (n) => { 
const result = [0, 1]; 
for (let i = 2; i < n; i++) { 
result.push(result[i - 1] + result[i - 2]); 
} 
return result; 
}; 
fibonacci(8); 
// Result: [0, 1, 1, 2, 3, 5, 8, 13] 
</pre>

39. Count the Number of Words in a String
Count the number of words in a given string. 
<pre>
const countWords = (str) => str.trim().split(/\s+/).length; 
console.log(countWords("Hello world, how are you?")); // Output: 5 
</pre>

40. Reverse an Array
Reverse the elements of a given array. 
<pre>
const reverseArray = (arr) => arr.slice().reverse(); 
console.log(reverseArray([1, 2, 3, 4, 5])); 
// Output: [5, 4, 3, 2, 1] 
</pre>

41. Get the Current Year
Get the current year. 
<pre>
const currentYear = () => new Date().getFullYear(); 
console.log(currentYear()); 
// Output: 2023 (depending on the current year) 
</pre>

42. Generate a Random Number between 1 and 10
Generate a random integer between 1 and 10 (inclusive). 
<pre>
const random1To10 = () => Math.floor(Math.random() * 10) + 1; 
console.log(random1To10()); 
// Output: Random number between 1 and 10 (inclusive) 
</pre>

43. Check if a String is Empty
Check if a given string is empty (contains no characters). 
<pre>
const isEmptyString = (str) => str.trim().length === 0; 
console.log(isEmptyString("")); 
// Output: true 
console.log(isEmptyString("Hello, world!")); 
// Output: false 
</pre>

44. Check if an Object has a Specific Property
Check if an object contains a specific property. 
<pre>
const hasProperty = (obj, prop) => prop in obj; 
const person = { name: "John", age: 30 }; 
console.log(hasProperty(person, "name")); 
// Output: true 
console.log(hasProperty(person, "gender")); 
// Output: false 
</pre>

45. Calculate the Average of Numbers in an Array
Calculate the average of numbers in a given array. 
<pre>
const average = (arr) => arr.reduce((acc, val) => acc + val, 0) / arr.length; 
console.log(average([1, 2, 3, 4, 5])); // Output: 3 
</pre>

46. Check if a Number is a Multiple of 5
Check if a given number is a multiple of 5. 
<pre>
const isMultipleOf5 = (num) => num % 5 === 0; 
console.log(isMultipleOf5(10)); 
// Output: true 
console.log(isMultipleOf5(7)); 
// Output: false 
</pre>

47. Convert Minutes to Seconds
Convert minutes to seconds. 
<pre>
const minsToSecs = (mins) => mins * 60; 
console.log(minsToSecs(5)); // Output: 300 
</pre>

48. Find the Maximum Value in an Array of Objects
Find the maximum value of a specific property in an array of objects. 
<pre>
const findMaxValue = (arr, key) => Math.max(...arr.map(item => item[key])); 
const students = [ 
{ name: "Alice", score: 80 }, 
{ name: "Bob", score: 95 }, 
{ name: "Charlie", score: 70 } 
]; 
console.log(findMaxValue(students, "score")); 
// Output: 95 
</pre>

49. Check if a String starts with a specific character
Check if a given string starts with a specific character. 
<pre>
const startsWithChar = (str, char) => str.startsWith(char); 
console.log(startsWithChar("Hello, world!", "H")); 
// Output: true 
console.log(startsWithChar("Hello, world!", "h")); 
// Output: false 
</pre>

50. Convert a String to Title Case
Convert a given string to title case (capitalize the first letter of each word). 
<pre>
const toTitleCase = (str) => str.replace(/\b\w/g, match => match.toUpperCase()); 
console.log(toTitleCase("hello world")); 
// Output: "Hello World" 
</pre>

51. Check if an Array contains a specific value
Check if a given array contains a specific value. 
<pre>
const containsValue = (arr, value) => arr.includes(value); 
console.log(containsValue([1, 2, 3, 4, 5], 3)); 
// Output: true 
console.log(containsValue([1, 2, 3, 4, 5], 6)); 
// Output: false 
</pre>

52. Convert an Array to a Comma-separated String
Convert a given array to a comma-separated string. 
<pre>
const arrayToCSV = (arr) => arr.join(', '); 
console.log(arrayToCSV([1, 2, 3, 4, 5])); 
// Output: "1, 2, 3, 4, 5" 
</pre>

53. Check if a Year is a Leap Year
Check if a given year is a leap year. 
<pre>
const isLeapYear = (year) => (year % 4 === 0 && year % 100 !== 0) || (year % 400 === 0); 
console.log(isLeapYear(2024)); 
// Output: true 
console.log(isLeapYear(2023)); 
// Output: false 
</pre>

54. Find the Index of an Element in an Array
Find the index of a specific element in a given array. 
<pre>
const findIndex = (arr, element) => arr.indexOf(element); 
const fruits = ["apple", "banana", "orange", "grape"]; 
console.log(findIndex(fruits, "orange")); 
// Output: 2 
</pre>

55. Convert Minutes to Hours and Minutes
Convert a given number of minutes to hours and remaining minutes. 
<pre>
const minsToHoursAndMins = (mins) => { 
const hours = Math.floor(mins / 60); 
const remainingMins = mins % 60; 
return `${hours} hours and ${remainingMins} minutes`; 
}; 
console.log(minsToHoursAndMins(150)); 
// Output: "2 hours and 30 minutes" 
</pre>

56. Check if an Array is Sorted in Ascending Order
Check if a given array is sorted in ascending order. 
<pre>
const isSortedAscending = (arr) => arr.every((el, i) => i === 0 || el >= arr[i - 1]); 
console.log(isSortedAscending([1, 2, 3, 5, 8])); 
// Output: true 
console.log(isSortedAscending([1, 5, 3, 8, 2])); 
// Output: false 
</pre>

57. Remove a Specific Element from an Array
Remove a specific element from a given array. 
<pre>
const removeElement = (arr, element) => arr.filter(el => el !== element); 
console.log(removeElement([1, 2, 3, 4, 5], 3)); 
// Output: [1, 2, 4, 5] 
</pre>

58. Truncate a String to a Given Length
Truncate a given string to a specified maximum length. 
<pre>
const truncateString = (str, maxLength) => str.length > maxLength ? str.slice(0, maxLength) + '...' : str; 
console.log(truncateString("Hello, world!", 5)); 
// Output: "Hello..." 
</pre>

59. Calculate the Exponentiation of a Number
Calculate the exponentiation of a given base raised to a specified exponent. 
<pre>
const exponentiate = (base, exponent) => Math.pow(base, exponent); 
console.log(exponentiate(2, 3)); 
// Output: 8 
</pre>

60. Find the Difference between Two Dates in Days
Find the difference between two dates in days. 
<pre>
const dateDifferenceInDays = (date1, date2) => Math.abs(Math.floor((date2 - date1) / (1000 * 60 * 60 * 24))); 
const startDate = new Date("2023-08-01"); 
const endDate = new Date("2023-08-10"); 
console.log(dateDifferenceInDays(startDate, endDate)); // Output: 9 
</pre>

61. Check if a String is a Valid Email Address
Check if a given string is a valid email address. 
<pre>
const isValidEmail = (email) => /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email); 
console.log(isValidEmail("user@example.com")); 
// Output: true 
console.log(isValidEmail("invalid-email")); 
// Output: false 
</pre>

62. Convert Seconds to Minutes and Seconds
Convert a given number of seconds to minutes and remaining seconds. 
<pre>
const secsToMinsAndSecs = (seconds) => { 
const mins = Math.floor(seconds / 60); 
const remainingSecs = seconds % 60; 
return `${mins} minutes and ${remainingSecs} seconds`; 
}; 
console.log(secsToMinsAndSecs(120)); 
// Output: "2 minutes and 0 seconds" 
</pre>

63. Check if an Object is a Function
Check if a given object is a function. 
<pre>
const isFunction = (obj) => typeof obj === 'function'; 
console.log(isFunction(() => {})); 
// Output: true 
console.log(isFunction({})); 
// Output: false 
</pre>

64. Convert Binary Number to Decimal
Convert a given binary number to its decimal representation. 
<pre>
const binaryToDecimal = (binary) => parseInt(binary, 2); 
console.log(binaryToDecimal("1101")); // Output: 13 
</pre>

65. Check if an Array contains only Unique Values
Check if a given array contains only unique values. 
<pre>
const hasUniqueValues = (arr) => new Set(arr).size === arr.length; 
console.log(hasUniqueValues([1, 2, 3, 4, 5])); 
// Output: true 
console.log(hasUniqueValues([1, 2, 3, 4, 4])); 
// Output: false 
</pre>

66. Get the Day of the Week from a Date
Get the day of the week from a given date. 
<pre>
const getDayOfWeek = (date) => { 
const daysOfWeek = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"]; 
return daysOfWeek[date.getDay()]; 
}; 
console.log(getDayOfWeek(new Date("2023-08-02"))); 
// Output: "Wednesday" 
</pre>

67. Check if a Number is a Power of Two
Check if a given number is a power of two. 
<pre>
const isPowerOfTwo = (num) => (num & (num - 1)) === 0; 
console.log(isPowerOfTwo(16)); 
// Output: true 
console.log(isPowerOfTwo(5)); 
// Output: false 
</pre>

68. Convert Object to Query Parameters String
Convert a given object to a string of query parameters. 
<pre>
const objectToQueryParams = (obj) => Object.entries(obj).map(([key, value]) => `${encodeURIComponent(key)}=${encodeURIComponent(value)}`).join('&'); 
console.log(objectToQueryParams({ search: "hello", page: 1 })); 
// Output: "search=hello&page=1"
</pre>

69. Check if an Array contains an Even Number
Check if a given array contains at least one even number. 
<pre>
const hasEvenNumber = (arr) => arr.some(num => num % 2 === 0); 
console.log(hasEvenNumber([1, 3, 5, 7, 8])); 
// Output: true 
console.log(hasEvenNumber([1, 3, 5, 7, 9])); 
// Output: false 
</pre>

70. Get the Month Name from a Date
Get the name of the month from a given date. 
<pre>
const getMonthName = (date) => { 
const months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"]; 
return months[date.getMonth()]; 
}; 
console.log(getMonthName(new Date("2023-08-02"))); 
// Output: "August" 
</pre>

71. Check if a String is a Palindrome (case-insensitive)
Check if a given string is a palindrome, considering it case-insensitive. 
<pre>
const isPalindromeCaseInsensitive = (str) => str.toLowerCase() === str.toLowerCase().split('').reverse().join(''); 
console.log(isPalindromeCaseInsensitive("LeVel")); 
// Output: true 
console.log(isPalindromeCaseInsensitive("Hello")); 
// Output: false 
</pre>

72. Convert Feet to Meters
Convert a given length in feet to meters. 
<pre>
const feetToMeters = (feet) => feet * 0.3048; 
console.log(feetToMeters(10)); 
// Output: 3.048 
</pre>

73. Check if a Number is a Perfect Square
Check if a given number is a perfect square. 
<pre>
const isPerfectSquare = (num) => Math.sqrt(num) % 1 === 0; 
console.log(isPerfectSquare(16)); 
// Output: true 
console.log(isPerfectSquare(10)); 
// Output: false 
</pre>

74. Check if a String contains only Numbers
Check if a given string contains only numeric characters. 
<pre>
const containsOnlyNumbers = (str) => /^[0-9]+$/.test(str); 
console.log(containsOnlyNumbers("12345")); 
// Output: true 
console.log(containsOnlyNumbers("12a34")); 
// Output: false 
</pre>

75. Get the Current Month (0-based index)
Get the current month as a 0-based index (0 for January, 1 for February, etc.). 
<pre>
const currentMonth = () => new Date().getMonth(); 
console.log(currentMonth()); 
// Output: Current month (0-based index) 

</pre>
76. Calculate the Mean of an Array of Numbers
Calculate the mean (average) of a given array of numbers. 
<pre>
const mean = (arr) => arr.reduce((acc, val) => acc + val, 0) / arr.length; 
console.log(mean([1, 2, 3, 4, 5])); 
// Output: 3 
</pre>

77. Check if a Number is a Prime Number
Check if a given number is a prime number. 
<pre>
const isPrime = (num) => { 
if (num <= 1) return false; 
for (let i = 2; i <= Math.sqrt(num); i++) { 
if (num % i === 0) return false; 
} 
return true; 
}; 
console.log(isPrime(13)); 
// Output: true 
console.log(isPrime(4)); 
// Output: false 
</pre>

78. Get the Last N Elements of an Array
Get the last N elements from a given array. 
<pre>
const lastNElements = (arr, n) => arr.slice(-n); 
console.log(lastNElements([1, 2, 3, 4, 5], 3)); 
// Output: [3, 4, 5] 
</pre>

79. Convert Degrees to Radians
<p>Convert a given angle from degrees to radians.</p>
<pre>
const degToRad = (degrees) => degrees * (Math.PI / 180); 
console.log(degToRad(90)); 
// Output: 1.5707963267948966 
</pre>

80. Check if a String is a Valid URL
Check if a given string is a valid URL. 
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


