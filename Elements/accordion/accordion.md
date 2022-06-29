accordion
---

html
```html
<div id="accordion" class="accordion-container">
<article class="content-entry">
<div class="article-title">
<div class="article-body">
<h4 class=""><i></i>the<span style="color: #0052ff;">starter.</span><span class="cena">280 €<span class="cena-obdobie">/mesiac</span></span></h4>
<h5>základný balík pre nenáročného užívateľa</h5>
</div>
</div>
<div class="accordion-content">

</div>
<!--/.accordion-content-->

</article></div>

``` 
style
```css
/*-- CENNIK --*/
.accordion-container {
		position: relative;
		width: 100%;
		/*border: 1px solid #0079c1;*/
		border-top: none;
		outline: 0;
		/*cursor: pointer;*/
  
}
.article-body {
  padding:30px 2.8em 1.8em;
  border-top: 5px solid #0052ff;
  transition: all .5s;
}
.article-body:hover {
  cursor: pointer !important;
  border-top: 10px solid #0052ff;
  padding:25px 2.8em 1.8em;
}

.accordion-container .article-title h4 {
		display: block;
		position: relative;
		margin: 0;
		/*padding: 1.5em 2.2em 0;*/
		
		font-size: 1.4em;
		font-weight: 800;
		color: #000;
		cursor: pointer;
 
  font-family: 'Lufga - ExtraBold',Helvetica,Arial,Lucida,sans-serif;
}

.accordion-container .article-title:hover,
.accordion-container .article-title:active,
.accordion-container .content-entry.open .article-title, .content-entry {
		background-color: #fff;
		/*color: white;*/
}

.accordion-container .article-title:hover i:before,
.accordion-container .article-title:hover i:active,
.accordion-container .content-entry.open i
{
		color: white;

}
 
.content-entry {
  font-family: 'Poppins',Helvetica,Arial,Lucida,sans-serif;
  padding: 0;
  
}

.accordion-container .content-entry i {
    font-family: 'Poppins',Helvetica,Arial,Lucida,sans-serif;
		position: absolute;
    top: 50%;
    left: -70px;
    transform: translate(0, -50%);
    font-weight: 300;
    font-size: 1.625em;
    color: #ffffff;
    display: block;
    width: 50px;
    height: 50px;
    background: #0052ff;
    border-radius: 50%;
    font-style: normal;
  border: 1px solid #0052ff;
  transition: font-weight .3s;
}
.article-body:hover i {
  font-weight: 600 !important;
}
.accordion-container .content-entry.open i {
  background: #fff;
   
}
.content-entry h5 {
  width: 60%;
}
.cena {
  float: right;
  font-size: 1.7em;
  
}
.cena-obdobie {
  color:#0052ff;
  font-size: .5em;
  font-weight: 300 !important;
}

.accordion-container .content-entry i:before {
		content: "+";
  position: absolute;
   left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
}

.accordion-container .content-entry.open i:before {
		content: "\2212";
  color: #0052ff;
}

.accordion-content {
		display: none;
  background: #fff;
 font-family: 'Poppins',Helvetica,Arial,Lucida,sans-serif;
    font-size: .8em;
    line-height: 1.3em;
    margin-top: 15px;
      padding: 0 2em 1em;
}
```
script
```js
$(function() {
		var Accordion = function(el, multiple) {
				this.el = el || {};
				this.multiple = multiple || false;

				var links = this.el.find('.article-title');
				links.on('click', {
						el: this.el,
						multiple: this.multiple
				}, this.dropdown)
		}

		Accordion.prototype.dropdown = function(e) {
				var $el = e.data.el;
				$this = $(this),
						$next = $this.next();

				$next.slideToggle();
				$this.parent().toggleClass('open');

				if (!e.data.multiple) {
						$el.find('.accordion-content').not($next).slideUp().parent().removeClass('open');
				};
		}
		var accordion = new Accordion($('.accordion-container'), false);
});
```