# Frontend Mentor - Single price grid component solution

This is a solution to the [Single price grid component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/single-price-grid-component-5ce41129d0ff452fec5abbbc). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
- [Author](#DexterOhaeri)


## Overview

### The challenge

Users should be able to:

- View the optimal layout for the component depending on their device's screen size
- See a hover state on desktop for the Sign Up call-to-action

### Screenshot

![](./solutions/for_desktop.png) 
![](./solutions/for_mobile_device.png)

### Links

- Solution URL: [Solution URL](https://github.com/MrDexterO/Frontend-Mentor-Challenge-Single-price-grid-component-solution)
- Live Site URL: [Live site](https://mrdextero.github.io/Frontend-Mentor-Challenge-Single-price-grid-component-solution/)

## My process

### Built with

- Semantic HTML5 markup
- CSS3
- CSS custom properties
- Flexbox
- CSS Grid

### What I learned

I learned two major lessons from this challenge.

1. The first one was about making the card to have a rounded corner. This is something i already know and adding
```css
.card {
  border-radius: var(--spacing-xs);
}
```
would have done it. But, I applied the rule and realised it wasn't working. ![](./solutions/border-radius-issue.png) I started troubleshooting and was almost getting frustrated. Then it finally dawned on me that the reason the rule is not showing effect is because I failed to account for one crucial property

```css
.card {
  border-radius: var(--spacing-xs);
  overflow:hidden;  /* Overflow:hidden*/
}
```

2. The second lesson from this challenge was about making the card responsive. I started up first with 2 columns in the "sub-sect" class

```html
<div class="sub-sect">
  <div class="subscription-bloc">
  </div>

   <div class="why-us-bloc">
  </div>
```
using 
```css
.sub-sect {
  display:flex;
  flex-direction:row;
}
```
...but I soon ran into a deadend as the container were not fluid in their responsiveness and this did not look asthetically professional. ![](./solutions/responsive_layout_issue.png)  So, I switched to grid. 

```css
.sub-sect {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(375px, 1fr));
}

```
but the issue persisted. It was until I did this to the child containers

```css
.subscription-bloc,
.why-us-bloc {
     max-width: 375px;
    min-width: 100%;
}
```
That the issue was resolved.

### Continued development

In future projects, I will focus more on getting the best layout to use on a project. It might mean dipping my feat on UI design. The other thing I will like to do is to master the use of grid for pefect responsiveness.

## Author

<!-- - Website - [Dexter Ohaeri](https://www.your-site.com) -->
- Frontend Mentor - [@MrDexterO](https://www.frontendmentor.io/profile/MrDexterO)
- GitHub - [@MrDexterO](https://github.com/MrDexterO)


## Acknowledgments

I acknowledge Frontend mentors for this opportunity to improve on my skills. I learned a lot.

