---
title: "My first react project: Pomodoro Timer"
description: "From Concept to Code: How I Built My First React Project - A Pomodoro Timer"
date: 2024-07-21
categories: [Programming, Projects]
tags: [React, Javascript, Projects, Learning, Coding]
author: Swagatika
image:
  path: "https://res.cloudinary.com/dduot1vgo/image/upload/v1756474994/pomodoro_woi9em.png"
  alt: Pomodoro Timer
---

In this blog post, I will share my journey of building a Pomodoro Timer using React, detailing the experiences, challenges, and key learnings that shaped my first React project.

## Introduction

### How I Got Started

While learning React from [Chai Aur Code by Hitesh Choudhary](https://www.youtube.com/watch?v=lI7IIOWM0Mo&list=PLu71SKxNbfoDqgPchmvIsL4hTnJIrtige&index=5), where he taught about hooks through a project involving count up and down functionality, I decided it was time to create my own project to solidify my understanding. Inspired by the concept of avoiding "tutorial hell," I aimed to apply what I had learned by building a practical application without relying on step-by-step guides or tutorials.

To achieve this, I watched various videos discussing the pitfalls of tutorial dependency and the benefits of hands-on practice. I resolved to learn new concepts from videos and then implement key ideas into small projects independently. This approach would not only enhance my coding skills but also allow me to build a portfolio of projects to showcase my abilities.

### Why a Pomodoro Timer?

I've been using the [Pomodoro Technique](https://todoist.com/productivity-methods/pomodoro-technique) for over five years, and it has significantly boosted my productivity, efficiency, and focus. The method involves working in short, focused intervals, typically 25 minutes, followed by a brief break. This cycle helps maintain high levels of concentration and prevents burnout.

In my early days of using the Pomodoro Technique, I discovered a simple [Pomodoro website](https://pomofocus.io/) that effectively implemented this concept. This inspired me to create my own version using the React and JavaScript skills I had acquired. Building a Pomodoro Timer seemed like the perfect project to apply what I'd learned and create something practical and beneficial for everyday use.

## Building the Pomodoro Timer

![to do list](https://res.cloudinary.com/dduot1vgo/image/upload/v1756474993/pomodoro_to_do_list_yfvkur.jpg){: .right w="200"}

### How I Laid the Groundwork

According to the 10/90 rule, investing the first 10% of your time in planning and organizing can save you up to 90% of the time during execution. I find this approach highly efficient, as it helps me visualize the project’s functionality and determine which concepts to implement. I began by breaking down the project into manageable features and organizing them by priority. I sketched a simple structure on paper to better visualize the project. By planning everything out before writing a single line of code, I ensured a clear and focused development process.

### Features

Here are the main features I aimed to implement in the Pomodoro Timer project:

1. **Countdown Timer**: _A basic countdown timer to track work and break intervals._
2. **Start/Pause/Restart Functionality**: _Controls to manage the timer’s operation._
3. **Three Types of Pomodoro Timers**: _Options to customize the work and break intervals._
4. **Dynamic Background Color**: _Change the background color between focus and break states._
5. **Completion Bell**: _A sound alert that rings when the timer completes._
6. **Automatic State Change**: _Switch the timer’s state automatically upon completion._
7. **State Change Handling**: _Restart the timer if the type or state changes while it’s running._
8. **Button Hover Feature**: _Implementing hover effects for buttons (which proved challenging; I'll explain the solution later in the blog)._
9. **Hosting Live on GitHub**: _Making the Pomodoro Timer accessible online by hosting it on GitHub._

### Concepts I Used in It

The concepts I made use of in this project include:

1. **React Hooks**: _Utilized useState and useRef for state management and referencing elements._
2. **JavaScript Map**: _Rendered three similar buttons dynamically without creating each one manually._
3. **React Components**: _Created components to render the three type-changing buttons._
4. **SetInterval**: _Implemented the timer logic using setInterval instead of useEffect, writing the logic independently without referring to other code._

### Issues I Faced While Building It

I worked on the project section by section, starting with the basic UI, then adding functionalities, and finally enhancing the design with background color changes and aesthetic improvements.

The two main challenges I encountered were writing the countdown timer code and implementing hover functionality for buttons that change color based on the focus and break states. I'll explain the concepts I learned from the documentation and blogs that helped me overcome these issues.

The best part was relying on my own logic rather than using ChatGPT for the coding process. While ChatGPT is a great tool for automating tasks and clarifying code, it's essential to understand the underlying logic and develop coding skills independently, especially at the beginning stage.

## Challenges

### Logic for Countdown Timer

I wanted to create the timer logic from scratch, using what I knew about React and JavaScript without looking up solutions online. I had two ideas: using the useEffect hook or the setInterval function. I read some documentation on React hooks and setInterval, then started experimenting. After lots of trial and error, I finally wrote a timer that worked the way I wanted. Here’s what I used:

1. [**useRef Hook**](https://react.dev/reference/react/useRef#referencing-a-value-with-a-ref): _To store the interval so I could clear it later._
2. [**useState Hook**](https://react.dev/reference/react/useState#resetting-state-with-a-key): _To keep track of the timer and access the previous state._
3. **[setInterval()](https://www.w3schools.com/jsref/met_win_setinterval.asp) and [clearInterval()](https://www.w3schools.com/jsref/met_win_clearinterval.asp)**: _To repeatedly run a function and stop it when needed._

Here is the code snippet:

```javascript
const timerCountDown = useRef(null);
const state = useState("Start");
const [timer, setTimer] = useState({
  min: 25,
  sec: 0,
});
function handleTimer() {
  if (state == "Start") {
    setState("CountDown");
    timerCountdown.current = setInterval(() => {
      setTimer((prevTime) => {
        let min = prevTime.min;
        let sec = prevTime.sec;
        if (min === 0 && sec === 0) {
          clearInterval(timerCountdown.current);
          //Ring the bell
          //Change Focus to Break and Vice a Versa
          setState("Stopped");
        } else if (sec === 0) {
          return {
            min: min - 1,
            sec: 59,
          };
        } else {
          return {
            ...prevTime,
            sec: sec - 1,
          };
        }
      });
    }, 1000);
  } else if (state == "Countdown") {
    setState("Pause");
    clearInterval(timerCountdown.current);
  }
}

// Call this function when you click on start/pause
```

### Using CSS Variable Change the Hover Color

In the Pomodoro Timer project, I aimed to implement dynamic color changes for different states (focus and break). For focus time, I set the background color to red, and for break time, I used light blue. This approach was straightforward and worked well.

```react
<div style = { {
	backgroundColor: timerState == "Focus"? 'red' : 'blue'
	} }>
{/* Content */}
</div>
```

However, when it came to implementing hover functionalities for my buttons, I hit a roadblock. Inline styles alone couldn't achieve the dynamic hover effects I wanted. I spent an entire day trying various solutions, reading blogs, and exploring suggestions on Stack Overflow and Reddit, but none of them worked.

Finally, I came across a [blog post](https://css-tricks.com/want-to-write-a-hover-effect-with-inline-css-use-css-variables/) _(Check out the blog, it was the real savior)_ that explained the use of CSS variables, which addressed my exact problem. The post offered a simple solution: using CSS variables to manage dynamic styling.

Here's how I applied this solution:

1. **Define CSS Variables**: _I set up CSS variables for the background and hover colors in the CSS file._
2. **Apply Variables in Inline Styles**: _Used these variables in the component's inline styles to update colors based on the current state._
3. **Update Variables Dynamically**: _Changed the CSS variables depending on whether the timer was in focus or break mode._

Here is the code snippet:

```react
<button
	id = "focusButton"
	style = { {
	"--btn-color": "#40C7E2",
	"--btn-hover-color": "#80D9EB"
	} }
>
Focus
</button>
```

```css
#focusButton {
  background-color: var(--btn-color);
}
#focusButton:hover {
  background-color: var(--btn-hover-color);
}
```

### Challenges in GitHub Hosting

I tried to host my React project on GitHub, but it wasn’t working at all. Initially, after following the standard procedure, I could get the website live. However, when I made any changes to the code, they didn’t reflect on the hosted site. The project worked perfectly on my local server, but once hosted, the page was completely blank.

Realizing there was an issue, I followed the documentation to host a dummy project, which worked. But again, any changes made to the project didn’t show up on the live site. I ended up creating and deleting over 20 repositories, and even tried hosting on Netlify, but nothing seemed to work.

I spent nearly three days trying to solve this problem, dedicating all my waking hours to reading blogs, articles, and troubleshooting guides. Despite my efforts, I couldn’t find a solution. Eventually, I gave up, made my final changes, and created the repository to host on GitHub. Although it’s live now, the problem of not reflecting updates persists.

If anyone knows how to solve this issue, please let me know in the comments section.

## Conclusion

I’m someone who can't stop working on a project until it’s completely finished. This drove me to spend all my waking hours over five days on this small project. While it may not have been the most efficient approach, it taught me valuable lessons about working more effectively in the future.

Despite its simplicity and seemingly insignificant functionalities, this project was a huge learning experience. I used what I learned to build something practical that I, as a big fan of the Pomodoro concept, can use. I’m eager to take on more complex projects in the future and share my journey and insights through blog posts.

## Project Showcase

You can check out the live version of my Pomodoro Timer and explore the code on GitHub using the links below:

- Live Project: [Pomodoro Timer Live](https://swag3009.github.io/pomo_timer/)
- GitHub Repository: [Pomodoro Timer Code](https://github.com/Swag3009/pomo_timer)

Here's a video demonstration of the project:
{% include embed/video.html src = 'https://res.cloudinary.com/dduot1vgo/video/upload/v1756474999/pomodoro_r5jjda.webm' %}
