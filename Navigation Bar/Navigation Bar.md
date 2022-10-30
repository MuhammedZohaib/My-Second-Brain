Navigation Bar Is an essential part of any website here we'll look how we can make a responsive navbar. We'll also try to crack the logic behind a navigation bar like how it is coded and how it works.

## Simple Structure of a NavBar in Html

```html
	<header>
		<img src=""> !--Logo--!
		<nav>
			<ul>
				<li>
				<a href= "#">Home</a>
				</li>
				<li>
				<a href= "#">Products</a>
				</li>
				<li>
				<a href= "#">Contact</a>
				</li>
				<li>
				<a href= "#">About Us</a>
				</li>
				<li>
				<a href= "#">Login</a>
				</li>
			<ul>
		</nav>
	</header>
```



## Styling In CSS:
If there is scrolling on our html document then we must want 
```CSS
position:Fixed
```
On our navigation bar so it stick to the top and available for access despite of the scrolling.
we'll also try to use min() function for padding so it'll choose the minimum of two available paddings in min() function.
```CSS
padding: min(30vh, 10rem), 2em; 
```
For making our navigation responsive we must use media queries.
We'll use max-width media query at `560px` or `35em` So when the mobile view will be limited to max screen size of `560px` or `35em`.
For desktop view we'll also use a min-width media at `768px`.
we'll be using two media queries just for navigation rest of the body will be same like mobile view first and add new media query for desktop view.
Also we'll use aria-labels to apply conditions and use the attribute selector in the CSS and `setAttribute` in JavaScript for manipulation.

we'll add an image in the button tag and enclose the the whole button in a div then make a nav tag in that div and give it two classes one is for styling with display none and other is for toggling it with JavaScript.
we'll select the attribute src of the image and set it to close icon using condition that if the nav has class show in it's class list.

## JavaScript Logic

```JS
	const button = document.querySelector("#button");
	const nav = document.querySelector(".navigation");
	const list = nav.classList;
	const open = document.querySelector("#open");
	
	button.addEventListener("click", ()=>{
    list.toggle("show-nav");
    if(nav.classList.contains('show-nav')){
        open.setAttribute('src', './images/icon-close.svg');
    }
    else{
        open.setAttribute('src', './images/icon-hamburger.svg');
    }
	
	});
```
