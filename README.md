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
