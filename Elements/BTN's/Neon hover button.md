Neon hover button
---


```html
<a href="#" class="neon-btn">
<span></span>
<span></span>
<span></span>
<span></span>
BUTTON -
</a>
``` 


```css
./* --- neon button --- */
a.neon-btn {
	font-family: "Roboto", Arial, Tahoma, sans-serif;
	font-size: 40px;
	overflow: hidden;
	transition: 0.2s;
	padding: 15px 17px;
	color:#fff;
	display: inline-block;
	position:relative;
	border-radius: 3px;
	line-height: 1em;
}
a.neon-btn:hover {
	color: #38144f;
	text-decoration: none;
	background: #fff;
	box-shadow: 0 0 10px #fff, 0 0 40px #fff, 0 0 80px #fff;
	transition-delay: 1s;
}
a.neon-btn span {
	display: block;
	position: absolute;
}
a.neon-btn span:nth-child(1) {
	top: 0;
	left: -100%;
	width: 100%;
	height: 2px;
	background: linear-gradient(90deg,transparent,#fff);
}
a.neon-btn:hover span:nth-child(1) {
	left: 100%;
	transition: 1s;
}
a.neon-btn span:nth-child(3) {
	bottom: 0;
	right: -100%;
	width: 100%;
	height: 2px;
	background: linear-gradient(270deg,transparent,#fff);
}
a.neon-btn:hover span:nth-child(3) {
	right: 100%;
	transition: 1s;
	transition-delay: 0.5s;
}
a.neon-btn span:nth-child(2) {
	top: -100%;
	right: 0;
	width: 2px;
	height: 100%;
	background: linear-gradient(180deg,transparent,#fff);
}
a.neon-btn:hover span:nth-child(2) {
	top: 100%;
	transition: 1s;
	transition-delay: 0.25s;
}
a.neon-btn span:nth-child(4) {
	bottom: -100%;
	left: 0;
	width: 2px;
	height: 100%;
	background: linear-gradient(360deg,transparent,#fff);
}
a.neon-btn:hover span:nth-child(4) {
	bottom: 100%;
	transition: 1s;
	transition-delay: 0.75s;
}
```