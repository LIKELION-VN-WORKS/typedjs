# LIKE LION HCMC 1st HACKATHON

## Overview

- The first graduate Hackathon of LIKE LION Vietnam.
- This **Typed.js** is the branding effect in the hackathon place.
- It type it out the list of the attendee, and the lecturers of the class.

![likelion](./likelion_hcmc.JPG)

## The Completed Image of Hackathon Typed.js Attendee List

## ![Attendees'List](./typejs.png)

## What Function I Used?

```
<script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.11"></script>
    <script>
      const auto = () => {
        const typed = new Typed("#typed", {
          stringsElement: "#typed-strings",
          smartBackspace: true,
          typeSpeed: 100,
          backSpeed: 150,
          loop: true,
          smartBackspace: true,
          shuffle: true,
        });
      };
      let time = 14400;
      let hour = "";
      let min = "";
      let sec = "";
      const addZero = (n) => {
        return (parseInt(n, 10) < 10 ? "0" : "") + n;
      };
      const x = setInterval(() => {
        hour = parseInt(time / 3600);
        min = parseInt((time - hour * 3600) / 60);
        sec = time % 60;
        document.getElementById(
          "demo"
        ).innerHTML = `<span>남은 시간 </span> ${addZero(
          hour
        )} <span>시</span> ${addZero(min)} <span>분</span> ${addZero(
          sec
        )} <span>초</span>`;
        time--;
        if (time < 0) {
          clearInterval(x);
          document.getElementById("demo").innerHTML = "해커톤 종료!";
        }
        if (addZero(hour) < 7 && addZero(hour) >= 4) {
          document.getElementById("demo").style.color = "skyblue";
        } else if (addZero(hour) >= 2 && addZero(hour) < 4) {
          document.getElementById("demo").style.color = "yellow";
        } else if (addZero(hour) < 2) {
          document.getElementById("demo").style.color = "red";
        }
      }, 1000);
      auto();
    </script>
```

> You should note that if you want to use `const typed = New Typed` object in script, you must make function to cover the object and call it. If not, You cannot use this and cannot see any errors in the browser.
