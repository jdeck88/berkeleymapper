# Introduction #

Suppose you want a title bar for BerkeleyMapper.  You can do this by making an iframe.


# Details #

The following code shows one way to control an iframe so it consumes the available height/width of the webpage:



&lt;head&gt;




&lt;script&gt;


function pageY(elem) {
> return elem.offsetParent ? (elem.offsetTop + pageY(elem.offsetParent)) : elem.offsetTop;
}
function pageX(elem) {
> return elem.offsetParent ? (elem.offsetLeft + pageX(elem.offsetParent)) : elem.offsetLeft;
}

var buffer = 20; //scroll bar buffer
function resizeIframe() {
> var height = document.documentElement.clientHeight;
> var width = document.documentElement.clientWidth;
> height -= pageY(document.getElementById('ifm'))+ buffer ;
> width -= pageX(document.getElementById('ifm'))+ buffer ;
> height = (height < 0) ? 0 : height;
> width = (width < 0) ? 0 : width;
> document.getElementById('ifm').style.width = width + 'px';
> document.getElementById('ifm').style.height= height + 'px';
}
//document.getElementById('ifm').onload=resizeIframe;
window.onresize = resizeIframe;


&lt;/script&gt;




&lt;/head&gt;





&lt;body onload=resizeIframe();&gt;


> A web-page Title Bar
> <br>
<blockquote>And other web-page text...<br>
<br>
<br>
<iframe id="ifm" src="http://bnhmmapstest.berkeley.edu/index.html?tabfile=http://amphibiaweb.org/tmpfiles/187253&configfile=http://amphibiaweb.org/tmpfiles/bm_config_414856.xml&ViewResults=tab&sourcename=AmphibiaWeb+Species+Map:+Bufo+americanus&amphibiaweb=true&label=1&opacity=0.50"><br>
<br>
<br>
<br>
</iframe><br>
<br>
<br>
<br>
<br>
Unknown end tag for </body><br>
<br>