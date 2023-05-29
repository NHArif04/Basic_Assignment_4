# Basic_Assignment_4
>## Index.html
```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Digital Clock</title>
    <link rel="stylesheet" type="text/css" href="styles.css" />
  </head>
  <body>
    <div id="clock"></div>

    <script src="script.js"></script>
  </body>
</html>

```
<br>

>## script.js
```JavaScript
const clockElement = document.getElementById('clock');

function updateClock() {
    const currentTime = new Date();

    let hours = currentTime.getHours();
    let minutes = currentTime.getMinutes();
    let seconds = currentTime.getSeconds();

    hours = hours < 10 ? '0' + hours : hours;
    minutes = minutes < 10 ? '0' + minutes : minutes;
    seconds = seconds < 10 ? '0' + seconds : seconds;

    clockElement.textContent = hours + ':' + minutes + ':' + seconds;
}

updateClock();

setInterval(updateClock, 1000);

```
<br>

>## styles.css
```CSS
#clock {
    font-size: 48px;
    font-weight: bold;
    text-align: center;
    margin-top: 50px;
  } 
```
<br>

## ***Note***
* Here's a brief description of how the JavaScript functionality is implemented in the provided code:

* The *updateClock()* function is defined to update the clock's display. It retrieves the clock element from the HTML using document.getElementById('clock').

* Inside the *updateClock()* function, the current time is obtained using the Date() object. The getHours(), getMinutes(), and getSeconds() methods are used to retrieve the hours, minutes, and seconds from the current time.

* Leading zeros are added to the hours, minutes, and seconds if necessary using a ternary operator. This ensures that each segment of the time is displayed with two digits (e.g., 02 instead of 2).

* The formatted time string is created by concatenating the hours, minutes, and seconds together with colons separating them.

* The textContent property of the clock element is updated with the formatted time string, effectively displaying the time in the clock.

* The *updateClock()* function is called initially to initialize the clock's display with the current time.

* The setInterval() function is used to call the *updateClock()* function every second (1000 milliseconds). This ensures that the clock is updated continuously to reflect the current time.