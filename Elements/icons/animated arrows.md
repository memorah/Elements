Change the number of columns in the product archive
---


```html
<div class="arrow"></div>

``` 
```css
/*animation arrows*/
.arrow {
    width: 40px;
    height: 40px;
    margin: auto;
    position: relative;
	top: 0px;
	z-index: 99 !important;
}

.arrow:before {
    content: '';
    position: absolute;
    top: 5px;
    left: 10px;
    width: 100%;
    height: 100%;
    border-left: 5px solid rgba(255, 255, 255, 0.7);
    border-bottom: 5px solid rgba(255, 255, 255, 0.7);
    transform: translate(5px, 75px) rotate(-45deg);
    animation: arrows 2s linear infinite;
    cursor: default !important;
	z-index: 99 !important;
}

.arrow:after {
    content: '';
    position: absolute;
    top: 0;
    left: 10px;
    width: 100%;
    height: 100%;
    border-left: 5px solid rgba(255, 255, 255, 0.7);
    border-bottom: 5px solid rgba(255, 255, 255, 0.7);
    transform: translate(30px, 0) rotate(-45deg);
    animation: arrows 2s linear infinite -1.5s;
    cursor: default !important;
	z-index: 99 !important;
}

@keyframes arrows
{
    0% {
        border-left: 5px solid transparent;
        border-bottom: 5px solid transparent;
        transform: translate(-15px, -30px) rotate(-45deg);
    }
    10%, 90% {
        border-left: 5px solid transparent;
        border-bottom: 5px solid transparent;
    }
    50% {
        border-left: 5px solid rgba(255, 255, 255, 0.7);
        border-bottom: 5px solid rgba(255, 255, 255, 0.7);
        transform: translate(-15px, 0px) rotate(-45deg);
    }
    100% {
        border-left: 5px solid transparent;
        border-bottom: 5px solid transparent;
        transform: translate(-15px, 30px) rotate(-45deg);
    }
}
```