# PDF_Scroll_ASCII_Crasher

A PDF that crash Adobe Reader,  just a little discovery that i want to share. 

</BR>

The PDF can be downloaded here: https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/releases/tag/v1

</BR>

<b>ON WORKING!!!!!!!!!!</b>

Like many things, this too, was discovered by accident....

I was intent on creating graphics made entirely of ASCII characters, and in the various steps to make them "marketable," </BR>
one involved converting them from .html to .pdf files.</BR>
Once I opened the pdf to see its contents, I immediately noticed that something was wrong.... </BR>
The pdf was displayed very slowly and if I tried to scroll down the page the program would start to glitch, </BR>
and when I tried to close the pdf the program (Adobe Reader, to be precise) immediately crashed.</BR>
Interesting...</BR>

However, maybe it is a case... </BR>
I try again, same result... </BR>
Mmmm, maybe it's my computer... </BR>
I try again with a laptop, again same result... </BR>
Well it was not my computer.</BR>

And so I accindentally discovered a way to crash Adobe Reader, </BR>
a likely good start to unearth more serious vulnerabilities... </BR>

So I want to share this little discovery with other geeks and researchers,</BR>
so that they can (maybe) get something good out of it.</BR>

In the "PDF" folder you can find the pdf that crashes Adobe Reader.

</BR>

<h2>How to reproduce the issue:</h2>

</BR>

For better understanding I will include all the exact steps I took to create the pdf, </BR>
starting with the .png image i started from. 

</BR>

<b>-1</b> Downlaod this png: 
https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/Hand_pointing_gun_meme.png
</BR>
<b>-2</b> Convert the png to Ascii here (download it as html file): 
https://manytools.org/hacker-tools/convert-images-to-ascii-art/
</BR>
<b>-3</b> Convert the html file to pdf here: https://www.sejda.com/html-to-pdf
</BR>
<b>-4</b> Open the pdf and scroll up and down a couple of times, and try to close the program,</BR>
at this point the application should crash (see video below).

</BR>

<h2>A couple of notes:</h2>

</BR>

<b>-1</b> According to my tests, the glitch resides esclusively in Adobe Reader.
</BR>
In my tests, I tried to use the pdf with the following programs:

</BR>

- Adobe Reader (works)</BR>
- Foxit PDF Reader (doesn't work)</BR>
- Sumatra PDF (doesn't work)</BR>
- Wondershare PDF Element (doesn't work)</BR>

</BR>

<b>-2</b> This technique does not work very well, in the sense that it does not completely crash the system every time. Depending on the target machine, and the circumstances, it can cause major slowdowns in the program, up to and including a total crash. In my tests sometimes it was enough to try to close the pdf, other times I had to do several scrolls up and down (best if you use the middle mouse scroll), other times it happened by doing a few clicks here and there, what is certain is that each time the program has an obvious difficulty loading the data visualization. I would also add that in my opinion it works best when the pdf is opened full screen, but still it can work in other circumstances.

</BR>

<b>-3</b> The technique does work with differents images and formats (see more detailed analysis below).

</BR>

<b>-4</b> The technique does not work with just any Img to ASCII Converter(see more detailed analysis below)..
</BR>
In my tests, I tried to use the pdf with the following converters:

</BR>

- https://manytools.org/hacker-tools/convert-images-to-ascii-art/ </BR>
(works, note that this site supports  conversion from png file to ASCII file in html format) </BR>
- https://www.text-image.com/convert/ascii.html </BR>
(doesn't work, this site doesn't allow direct conversion to html, so it needs two more steps: </BR>
you have to copy the output to text file (odt, txt, etc.) , and then convert it to html file.</BR>

</BR>

<b>-5</b> The technique does not work with just any HTML to PDF Converter (see more detailed analysis below)..
</BR>
In my tests, I tried to use the pdf with the following converters:


</BR>

- https://www.sejda.com/it/html-to-pdf (works)
- https://convertio.co/it/html-pdf/  (doesn't work)

</BR>

<b>-6</b>  This type of attack (if you can call it that) can be easily automated through shortcuts.

</BR>

<b>Adobe Reader Scroll Shortcuts</b>


- Press Ctrl + Shift + H to initiate auto-scroll in Adobe Reader

- Adjust the scroll speed using the up and down arrow keys

- Press the minus key (-) to change the scroll direction

- Press Ctrl + Shift + H to stop auto-scroll

</BR>

<h2>Some reasoning about the Image Files</h2>

</BR>

In my brief tests, I used 3 different images (png, jpg): 

</BR>

- <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/Hand_pointing_gun_meme.png">1</a></BR>
- <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/Hackintosh_Kernel_Panic.jpg">2</a></BR>
- <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/black.jpg">3</a>

</BR>

Initially I started with the image <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/Hand_pointing_gun_meme.png">1</a>, from which my studies started.</BR>
Analyzing the ASCII characters in the image shows that it contains the following characters: </BR>
<b>@ &  # B G J P Y 5 7 ? ! ~ ^ :</b>

</br>

Although I think the trick is more in the html code (also because If you directly convert a document file (odt, txt, etc.) to pdf, the technique doesn't work, it necessarily requires converting to html file as well), I wanted to try different images anyway, to see if there was any correlation between the characters used.</br>
And so I switched to the image <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/Hackintosh_Kernel_Panic.jpg">2</a>.</BR>
Analyzing the ASCII characters in the image shows that it contains the following characters: </BR>
<b>@ * . # ( / , & % </b>

</br>

A simple cross-check shows that the two images use the following characters in common:</BR>
<b>@  #  & </b>

</br>

I then noticed that the img/ASCII converter fills the background (both the black ones and the transparent ones) with the <b>@</b> character.
And so I used the image <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/black.jpg">3</a> image (a high-resolution black background), And I realized that the technique works even using only the <b>@</b> character, so I deduce that it is enough to use only one special character for the whole thing to work.

</BR>

So it's time to try with other characters, let's try with a normal character, for example the <b>a</b>letter.</BR>
Then i replaced (directly from this html file) all the <b>@</b> with the letter <b>a</b>.</BR>
The result was this <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/All%20a%20letters.html">html</a> file,
hich I subsequently converted into this <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/All%20a%20letters.pdf">pdf</a>.</BR>
The technique works this way as well, although I must say that it is more difficult to get the program to start crashing. It follows, then, that the trick works regardless of the character used, but that it works slightly better with special characters, especially when mixed together.

</BR>

As a final thing, at the "font" level, i tried increasing the number of characters (which when converted to html format are contained within <span> tags), to see if i could fatigue the program further, so as to cause increasingly efficient crashes. But if you even try to double the number of characters (and thus "span" tags) by manually editing the html file, when you try to convert it to pdf, the conversion program goes into error, making the last step impossible.</BR>
In any case, I considered analyzing the conversion to html more than anything else, as I think the bulk to understand is there.</BR>
The HTMl files for this test can be viewed <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/PDF_Scroll_Crasher%202X.html">here</a>

</BR>

<h2>Some reasoning about image to ASCII Converters</h2>

</BR>

As mentioned above I used two different image to ASCII converters, and only <a href="https://manytools.org/hacker-tools/convert-images-to-ascii-art/ ">this</a> one worked. In fact, i'm pretty much certain that both would have worked, and that the difference is that <a href="https://www.text-image.com/convert/ascii.html">this</a> converter does not allow downloading the converted file to html format, and so the problem occurs later in the conversion from text file to html.

</BR>

As for the conversion settings, I simply set the output width (in characters) to 200, a.k.a. "the maximum level". 

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/settings-img-2-ascii-max-width.PNG" width="350" title="img-2-asii-settings">
</p>

</BR>

Other converters allow larger widhts, but the one in the converter I used is more than enough to make the trick work.</BR>
Otherwise, there is not much to add here ...

</BR>

<h2>Some reasoning about HTML to PDF Converters</h2>

</BR>

In my tests, I used 2 different HTML to PDF Converters: 

</BR>

- <a href="https://www.sejda.com/it/html-to-pdf">1</a> (works)</BR>
- <a href="https://convertio.co/it/html-pdf/">2</a> (doesn't work)</BR>

</BR>

It is enough to open the two files to notice the huge differences at the graphic level.

</BR>

<img src="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/PDF_Scroll_Crasher_Inside.PNG" alt="" width="400" height="500" />

<p>Conversion by sejda.com (image reduced by 50%)</p>

</BR>

<img src="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/PDF_Scroll_Crasher_inside_converted_by_convertio.PNG" alt="" width="400" height="500" />

<p>Conversion by convertio.co (image reduced by 50%) </p>

</BR>

Apparently the conversion of the convertio.co websitesite, in this case, is pretty lousy... </BR>
As far as the two files are concerned, not much can be said, this is because </BR>
when you look at a PDF file with notepad (or similar) the program automatically converts  </BR>
multi-byte characters to single 8-bit characters. </BR>
But still you can see some differences in the files, in those few "human redeable" parts. 

</BR>

<img src="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/pdf-scroll-crasher-pdf-inside.PNG" />
<p>Inside the PDF converted by sejda.com</p>

</BR>

<img src="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/pdf-scroll-crasher-pdf-inside-by-convertio.PNG" width="577" height="500" />
<p>Inside the PDF converted by convertio.co</p>

</BR>

The two PDF files can be viewed/downloaded here:

</BR>

- <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/PDF/PDF_Scroll_Crasher.pdf">1</a> (works)</BR>
- <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/PDF_Scroll_Crasher_converted_by_convertio.pdf">2</a> (doesn't work)</BR>

</BR>

<h2>Some reasoning about DOC to HTML Converters</h2>

So let us see the differences between the two converters I used in my tests.</BR>
You can see the two HTML files here:

</BR>

- <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/PDF_Scroll_Crasher.html">1</a> (works)</BR>
- <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/HTML_File_II_by_Convertio.html">2</a> (doesn't work) 

</BR>

Let's start by analyzing the file that works for the purpose, which is file <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/PDF_Scroll_Crasher.html">1</a>.</BR>
Basically, the converter inserts each ASCII character inside a "span" tag.</BR>
As you can see from the screenshot below some "span" tags are in error, this is because they contain the & character, which in html language is a special character that is used to create other characters, to make a long story short, in the HTML language to use the term & you use the entity code "&amp", while the & character is used (in combination with others) to display other special characters.</BR>
More info here: https://www.whatsmyip.org/html-characters/ 

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/span--errors.PNG" width="600" title="img-2-asii-settings">
</p>

</BR>

Definitely interesting, but we know from previous tests (done only with the letter @) that it can't be the real answer, although I have to say that files that have these kinds of errors seem to work better, maybe it's good to keep track of them anyway...

</BR>

Taken by curiosity i couldn't resist and immediately edited the html file to create an injection of wrong "span" tags (thanks to the & character), as you can see <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/All%20%26%20char.html">here</a>.</BR>
In addition, it is good to remember that the character & is one of the 3 common characters in the ASCII files I tested (@ # &).</BR>
Then, as usual, converted to <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/All%20%26%20char.pdf">pdf</a>. </BR>
Also works this time, but I didn't notice any particular improvement....

</BR>

Here are the CSS rules that are inserted into the file by this converter:

</BR>

display:inline-block;</BR>
white-space:pre;</BR>
letter-spacing:0;</BR>
line-height:1.4;</BR>
font-family:'Consolas','BitstreamVeraSansMono','CourierNew',Courier,monospace;</BR>
font-size:12px;</BR>
border-width:1px;</BR>
border-style:solid;</BR>
border-color:lightgray;

</BR>

Now let's analyze file <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/HTML_File_II_by_Convertio.html">2</a>. For this file, I had to perform an extra step (as mentioned above), which was to download my ASCII file in TXT format, and then convert it to html here: https://convertio.co/it/txt-html/ </BR>
The HTML file can be viewed <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/HTML_File_II_by_Convertio.html">here</a>.

</BR>

It is noticeable right away that the differences in the code between the two files are several.</BR>
Let's start by saying that it seems to be converted in a much finer way than previously used. </BR>
The CSS rules are much more than that, and there are also very important rules </BR>
(that were not there in the previous one) for displaying the file correctly.</BR>
I'm talking about <b>@media screen</b> and  <b>@media print</b> (line 30, 104). </BR>
The "@media" attribute allows us to set a style sheet for each media on which our page will be displayed.</BR>
The "screen" value is obviously for optimization on different types of screens, while the "print" value is for print optimization.
In addition, this converter adds a set of js functions (from line 190 to 216) , some designed to optimize visualization.</BR>
These facts gives us (probably) the explanation of why this converter is not suitable for this attack.</BR>

</BR>

<h2>Testing other attacks via HTML/CSS</h2>

Having come this far, i'm increasingly certain that the glitch happens because </BR>
of css rules (perhaps because they can be improved?) added during conversion.

</BR>

I was then reminded of the only css attack I know of, which is </BR>
the CSS webkit filter DoS attack created by pwnsdx.

</BR>

More info Here:</BR>
https://github.com/JonnyBanana/safari-ie-reaper.github.io

</BR>

But so how exactly does this kind of attack work? </BR>
In much the same way as found above, here again we have </BR>
(purposely poorly written) css rules that crash a target, in this case a browser.</BR>
The CSS code tries to apply a CSS effect known as backdrop-filter to a series of DIV's.</BR>
Backdrop-filter is a relative new CSS property and works by blurring or color shifting </BR>
to the area behind an element. This is a heavy processing task...</BR>

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/backdrop-filter.PNG">
</p>

</BR>

The attack uses a weakness in the -webkit-backdrop-filter CSS property, </BR>
which uses 3D acceleration to process elements behind them.</BR>
By using nested divs with that property, all graphic resources are quickly </BR>
consumed, and freeze the browser, or in some cases causes kernel panic the OS.</BR>

</BR>

This vulnerability has been, in part, mitigated, but I know for a fact that it </BR>
still works, especially on older machines.

</BR>

And so I immediately attempted an HTML to PDF conversion that contained this attack.

HTML file: <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/css-webkilter-attack.html">here</a></BR>

PDF: <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/css-webkilter-attack.pdf">here</a>

</BR>

But, as you can see from the screenshot below, unfortunately it did not work, this is because </BR>
the file size exceeds the limit of Adobe Reader, which I found out to be 200 x 200 inch.</BR>
More info: <a href="https://community.adobe.com/t5/acrobat-discussions/the-dimensions-of-this-page-are-out-of-range-page-content-might-be-truncated/td-p/9894141">here</a> 

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/dimension-exceed.PNG">
</p>

</BR>

I then attempted to scale the pdf to a size acceptable to Adobe.</BR>
Again I decided to rely on online tools , in particular I used these two:</BR>

- <a href="https://avepdf.com/it/resize-pdf">AvePDF</a>

- <a href="https://www.sodapdf.com/it/ridimensiona-pdf/">SodaPDF</a>

</BR>

As for the first converter, the conversion was successful, and "Adobe's </BR>
size error"  disappeared, but still the attack does not work at all.</BR>
While as for the conversion to SodaPDF, I can say, after several attempts, </BR>
that even after the hypothetical conversion the "Adobe's size error" remains, </BR>
although clearly you can see in the file that there was some resizing work done, </BR>
although it would look pretty scrappy... </BR>


The two (resized) PDf can be viewed here::</BR>

- <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/css-webkilter-attack%20scaled.pdf">AvePDF</a>

- <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/sodapdf-resized.pdf">SodaPDF</a> (download only)

</BR>

In any case, it can be concluded by saying that this type of attack does not work when converted to PDF.

</BR>

<h2>Let's take a step back...</h2>

Since trying a similar attack didn't work, I decided to take a closer look at the css code of the </BR>
file that gave me the most satisfaction, the trick then should be encapsulated in these few lines?</BR>
I don't know, but I decided to play with it a little bit...</BR>
Let's try to analyze the css rules for a moment:</BR>

- <a href="https://www.w3schools.com/csSref/pr_class_display.php">display</a>               The display property specifies the display behavior (the type of rendering box) of an element.
- <a href="">white-space </a>          \\
- <a href="">letter-spacing </a>       \\
- <a href="">line-height</a>           \\
- <a href="">font-family </a>          \\
- <a href="">font-size</a>             \\
- <a href="">border-width </a>         \\
- <a href="">border-style</a>          \\
- <a href="">border-color</a>          \\




</BR>

<h2>ProcMon</h2>


</BR>




</BR></BR></BR></BR>



All the files i used for the tests can be found in the <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/tree/main/CASE%20STUDY">"CASE STUDY"</a> folder.


</BR>






