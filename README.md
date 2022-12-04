# PDF_Scroll_ASCII_Crasher

A PDF that crash Adobe Reader,  just a little discovery that i want to share. 

</BR>

The PDF can be downloaded here: https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/releases/tag/v1

</BR>

And here some of other optimized versions:

</BR>

https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/border/1000px-font100px%20-%20let-spacing%20-100cm.pdf</BR>

https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/border/red-line%20line-eight%201000px.pdf</BR>

https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/border/1000px-font100px%20-%20let-bwidth%20-10000px%20.pdf

</BR>

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
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/backdrop-filter.PNG" width="600">
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
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/dimension-exceed.PNG" width="600">
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
- <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/white-space">white-space </a>    The white-space CSS property sets how <a href="https://developer.mozilla.org/en-US/docs/Glossary/Whitespace">white space</a> inside an element is handled.      
- <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing">letter-spacing </a>  The letter-spacing CSS property sets the horizontal spacing behavior between text characters.     
- <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/line-height">line-height</a>   The line-height CSS property sets the height of a line box. It's commonly used to set the distance between lines of text.       
- <a href="https://www.w3schools.com/cssref/pr_font_font-family.php">font-family </a> The font-family property specifies the font for an element.         
- <a href="https://www.w3schools.com/cssreF/pr_font_font-size.php">font-size</a>   The font-size property sets the size of a font.           
- <a href="https://www.w3schools.com/css/css_border.asp">border-width </a>    The CSS border-width properties allow you to specify  width of an element's border.     
- <a href="https://www.w3schools.com/css/css_border.asp">border-style</a>     The CSS border-style properties allow you to specify  style of an element's border    
- <a href="https://www.w3schools.com/css/css_border.asp">border-color</a>     The CSS border-color properties allow you to specify  color of an element's border    

</BR>

I start by eliminating a couple of css properties that surely can't make a difference, </BR>
namely font-family and border-color (probably border-style should also be aliminated, </BR>
but since some borders are made of ASCII characters, for example the one made of dots, </BR>
i decided to keep it, for now). That leaves us with these lines of codeThat leaves us </BR> 
with these lines of code:

</BR>

display:inline-block;</BR>
white-space:pre;</BR>
letter-spacing:0;</BR>
line-height:1.4;</BR>
font-size:12px;</BR>
border-width:1px;</BR>
border-style:solid;</BR>

</BR>

The <b>display</b> propiety accepts lots of values, in this case </BR>
the css rules use the <a href="https://www.w3schools.com/css/css_inline-block.asp">in-line block</a> value. </BR>
So I tried playing with the propieties a little bit by </BR>
changing some of them, which </BR> i thought were more relevant, to see what happened.</BR>
<a href="https://www.w3schools.com/csSref/playdemo.php?filename=playcss_display&preval=list-item">Here</a> you can try a demo to better understand how the "display" propiety works.</BR>
The display propiety has so many values available, I have tried most of them:

</BR>

- <b>inline-block</b> (Is the main rule that I had previously used)
- <b>inline</b> (works, It would also seem to be a little better than the propiety block)
- <b>block</b> (also works)
- <b>flex</b> (this is interesting, it triggers a file truncation error, but it still works!)
- <b>grid</b> (impossible to convert to pdf, I made several attempts)
- <b>inline-flex</b> (same error as "flex", also works)
- <b>inline-grid</b> (same erros as "grid")
- <b>inline-table</b> (same error as "flex", but it seems to work in a weaker way)
- <b>list-item</b> (also works)
- <b>run-in</b> (also works)
- <b>table</b> (same error as "flex", also works)
- <b>table-caption</b> (also works)
- <b>table-column-group</b> (dont work, blank pdf)
- <b>table-header-group</b> (also works, same error as "flex")
- <b>table-footer-group</b> (also works, same error as "flex")
- <b>table-row-group</b> (same error as "flex", also works)
- <b>table-cell</b> (same error as "flex", also works)
- <b>table-column</b> (same error as "flex", also works)
- <b>table-row</b> (same error as "flex", also works)
- <b>none</b> (untested, as useless for the purpose)
- <b>initial</b> (also works)
- <b>inherit</b> (interesting, also works well even when the pdf has the screen resized)

</BR>

These attempts led me to discover another small glitch, specifically using the <b>flex</b> and <b>inherit</b> values.

</BR>

- flex =     Displays an element as a block-level flex container
- inherit =  Inherits this property from its parent element

</BR>

In particular, both of these values, in addition to crashing the application, </BR>
sometimes left the Adobe window open in a crash (black screen).

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/css-display/flex%20adobe%20hidden%20process.PNG" width="750" >
</p>

</BR>

Also, as you can see the process is not detected by the Windows task manager,</BR> 
which would then appear to be already finished.

</BR>

Then I used <a href="https://learn.microsoft.com/en-us/sysinternals/downloads/procmon">Process Monitor</a> to better visualize the process, while running the glitch.

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/css-display/processnotfind-flex-procmon.PNG" width="750">
</p>

The process(es) shows up on ProcMon, but if you try to access it the program tells us </BR>
that it is unable to locate associted event in the visible items, this makes me assume </BR>
that the process has been killed, but for some reason the glitch persists, sounds interesting... </BR>
In any case at the moment I'm more interested in finding a combination of CSS/HTML rules that </BR>
will optimize the crash, in case I'll come back later to analyze the processes. </BR>

</BR>

The inherit attribute, in addition to the glitch I just mentioned, has also been shown to work</BR>
well with the resized Adobe Reader window, which is why I decided to use this rule in subsequent tests,</BR>
to see if mixing it with other rules I can find the deadly combination I am looking for.

</BR>

All the pdf's of the tests I did with this propiety can be found <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/tree/main/CASE%20STUDY/css-display">here</a>.

</BR>

The <b>white-space</b> propiety accepts 6 differents values: </BR>
<b>normal</b>, <b>nowrap</b>, <b>pre</b>, <b>pre-wrap</b>, <b>pre-line</b>, and <b>break-spaces</b>. 

</BR>

I exclude the <b>normal</b> value because it is irrelevant,</BR>
and also the <b>pre</b> value, because it was the one that had been used before.</BR>
and try to see what happens with the others. </BR>
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/white-space">Here</a> you can try a demo to better understand how the "white-space" propiety works.

</BR>

- <b>nowrap</b> (it gives truncation error, but works)
- <b>pre-wrap</b> (It seems to work more effectively)
- <b>pre-line</b> (It seems to work more effectively)
- <b>break-spaces</b> (also works)

</BR>

The <b>nowrap</b> value is the first file in my tests that goes into </BR>
truncation error, but still manages to crash the application, </BR>
however other than that I have not noticed any particular improvement.</BR>
While using the <b>pre-wrap</b> and <b>pre-line</b> values, i noticed that they seem </BR>
to work more effectively than the previous ones, especially the <b>pre-wrap</b> value.</BR>
With the two values named above, one immediately notices an increase in Adobe's difficulty </BR>
in displaying the file, in fact in my tests it often took only a slight scroll to make it crash, </BR>
and sometimes even just opening the file and trying to close it.

</BR>

But then why would they seem to work better? </BR>
If we analyze the table below, we see that <b>pre</b> values preserve lines </BR>
(that's how they manage not to go into truncation error, while those that collapse send Adobe into error).</BR>
The <b>pre</b> and <b>pre-wrap</b> values also preserve spaces and tabs ,perhaps that is why <b>pre-wrap</b> seems </BR>
to work better than <b>pre-line</b>. I will therefore use the <b>pre-wrap</b> value in future tests.

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/white%20space/white-spaces-table.PNG" width="500">
</p>

</BR>

Actually this attribute also has global variables, but I have not tested them at the moment, </BR>
as i am satisfied with the <b>pre-wrap</b> value, and then i have already invested enough time so...

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/white%20space/gbval.PNG">
</p>

</BR>

All the pdf's of the tests I did with this propiety can be found <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/tree/main/CASE%20STUDY/white%20space">here</a>.

</BR>

The <b>letter-spacing</b> propiety accepts 3 differents  types of values:</BR>
Keyword Values, Lenght Values, and Global Values.

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/letter-spacing %26 font-size/ValTypes.PNG">
</p>

</BR>

Initially I tested all the combinations with the Keyboard & Global values, but I didn't notice </BR>
any particular improvement, so I played around a bit with the Lenght Values.</BR>
I then began to do several tests with letter spacings in both pixels and percentages </BR>
(both positive and negative numbers), initially priming the pixel measurements, </BR>
because they turn out to beless responsive than those expressed in %, at least in HTML, </BR>
as far as Adobe is concerned I intend to find out... Also, I mixed different fonts measurements(in px) </BR>
to see what was going on, and got some interesting results (although I haven't yet gotten what I'm looking for). 

</BR>

I really made many attempts which you can see here:</BR>
https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/tree/main/CASE%20STUDY/letter-spacing%20%26%20font-size

</BR>

I really tried everything: inserting tiny fonts and multiplying divs (but I had conversion problems), </BR>
mixing wrong rules, with negative numbers, so that fonts overlapped, etc. </BR>
However, a couple of interesting glitches came out.

</BR>

For example with this mix of rules:</BR>

display:inherit;</BR>
white-space:pre-wrap;</BR>
letter-spacing:-1px;</BR>
line-height:1.4;</BR>
font-size:1px;</BR>
border-width:1px;</BR>
border-style:solid;

</BR>

The result is shown in the gif below:

</BR>

<p>
  <img src="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/letter-spacing %26 font-size/glitch--red%20.gif?raw=true" width="750">
</p>

</BR>

As you can see the program immediately goes into glitch, displaying a red line that </BR>
automatically scrolls down, this allows the attack to always work even without mouse intervention!</BR>
In my tests it was always enough to wait a few seconds, and the crash happens simply by trying to close the application.</BR>
It also sometimes goes into a kind of loop, and starts over again with the red line scroll.</BR>
And so I was able to optimize the attachment a bit, although I would like more...

</BR>

This PDF can be found here:</BR>
https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/letter-spacing%20%26%20font-size/-1px-fontsize1px.pdf

</BR>

Also trying with this mix of rules:</BR>

display:inherit;</BR>
white-space:pre-wrap;</BR>
letter-spacing:1000px;</BR>
line-height:1.4;</BR>
font-size:100px;</BR>
border-width:1px;</BR>
border-style:solid;

</BR>

The previously recounted glitch recurred (black screen , persistent, process closed), </BR>
and clicking with the mouse to try to close the program I noticed that it opened a folder located </BR>
exactly down there. This gave me connfirmation of what I suspected, which was that the process </BR>
was closed, but the screen persisted even after closing the program, as a graphical glitch.

</BR>

<p>
  <img src="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/letter-spacing %26 font-size/1000px-100px--glitch.gif?raw=true" width="750">
</p>

</BR>

In subsequent tests I will use these two rule mixes, </BR>
mixing them further with other rules, and let's see what happens...

</BR>

We then turn to the <b>line-height</b> property, that accept a lot of values types.

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/line-height/line-height%20values.PNG" width="750">
</p>

</BR>

Fortunately, there is an inadvisable type of values in this propiety, namely em (%) values, which create character overlap.

</BR>

<p>
  <img src="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/line-height/line-height-em-glitch.PNG" width="750">
</p>

</BR>

More info here: https://developer.mozilla.org/en-US/docs/Web/CSS/line-height 

</BR>

And so, because I have already invested a lot of s time in testing, I decided to opt to play exclusively with % values. </BR>
The result, however, did not enhance the glitches, so I moved on, but I will still keep the em measures in this propiety,  </BR>
since it is well known that one should not use them...

</BR>

All the pdf's of the tests I did with this propiety can be found <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/tree/main/CASE%20STUDY/line-height">here</a>.

</BR>

All that remains then is to play around a bit with the <b>border-width</b> & <b>border-style</b> attributes.

</BR>

The <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-width">border-width</a> atibute accepts a lots of values:

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/border/border-width-values.PNG" width="555">
</p>

</BR>

Since there are so many possibilities for now I will focus on playing on measurements in px , in em, and in cm.

</BR>

So I made several attempts, which can be seen here: </BR>
https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/tree/main/CASE%20STUDY/border

</BR>

Several graphic glitches have come out, and it is interesting to see </BR>
how with each change the graphic result is very different.</BR>
Here are some examples of the strangest ones:

</BR>
__________________________________________________________________________________

</BR></BR>

<p>
  <img src="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/border/1.gif" width="555">
</p>

</BR>

https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/border/1000px-font100px%20-%20let-spacing%20-100cm.pdf

</BR></BR>
__________________________________________________________________________________

</BR></BR>

<p>
  <img src="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/border/2.gif" width="555">
</p>

</BR>

https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/border/red-line%20line-eight%201000px.pdf

</BR></BR>
__________________________________________________________________________________

</BR></BR>

<p>
  <img src="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/border/3.gif" width="555">
</p>

</BR>

https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/border/1000px-font100px%20-%20let-bwidth%20-10000px%20.pdf

</BR></BR>
__________________________________________________________________________________

</BR>

However, apart from a lot of different graphic effects, i have not noticed any improvements over previous vesions, </BR>
the attack works (almost)all the time, and if you leave the pdf open for a few seconds the chances of success </BR>
rise to almost 100%. But unfortunately i have not yet achieved the effect i am looking for (instant crash of the app, </BR>
or better yet kernel panic of the system).

</BR>

So I decide not to go further down this road, as there are too many possibilities to test, </BR>
better to study Adobe's defense systems a bit more.  As you can easily imagine Adobe uses a sandbox to open files, </BR>
and examine them in a protected environment. But what else?

</BR>

<h2>Security in Acrobat and PDFs</h2>

</BR>

The info I was looking for can be found here: https://helpx.adobe.com/acrobat/using/overview-security-acrobat-pdfs.html

</BR>

As you can see Adobe uses several protection techniques, this one is particularly interesting for the purpose: </BR>
https://helpx.adobe.com/acrobat/using/protected-view-feature-pdfs-windows.html#protected_view_feature_for_pdfs_windows_only

</BR>

As you might imagine several "sandbox" measures are used. , which are turned on by default, but can still be turned off manually (or by script).

</BR>

<p>
  <img src="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/sec/sec-settings.PNG" width="777">
</p>

Sandbox protections enabled by default

</BR>

Unfortunately, even after deactivating the sanbox protections I did not get , even this time, the desired result.

</BR>

<p>
  <img src="[https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/sec/sanbox-adobe-deactivated.PNG](https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/sec/sanbox-adobe-deactivated.PNG)" width="777">
</p>

Sandbox protections deactivated

</BR>

The only other security policy that I found interesting for the purpose is protection to javascript scripts:</BR>
https://helpx.adobe.com/acrobat/using/javascripts-pdfs-security-risk.html#javascripts_in_pdfs_as_a_security_risk

</BR>

Adobe also has the "Enhanced security settings" enabled by default:
https://helpx.adobe.com/acrobat/using/enhanced-security-setting-pdfs.html#enhanced_security_setting_for_pdfs</BR>

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/sec/Enhanced%20security%20settings.PNG" width="777">
</p>

Enhanced security setting enabled by default

</BR>

Adobe's website states:</BR>

PDFs have evolved from static pages to complex documents with features such as interactive forms, multimedia content, scripting, and other capabilities. These features leave PDFs vulnerable to malicious scripts or actions that can damage your computer or steal data. Enhanced security lets you protect your computer against these threats by blocking or selectively permitting actions for trusted locations and files.

</BR>

When enhanced security is enabled and a PDF tries to complete a restricted action from an untrusted location or file, a security warning appears. The type of warning depends on the action and your version of Acrobat or Reader. (See Security warnings.)

</BR>

However, it must be said that by default I was not getting any  security warning.</BR> 

</BR>

But still I decide to disable this protection as well, and also add the files i use for testing to the list of safe files.

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/sec/enchanced-sec-deactivated.PNG" width="555">
</p>

Enhanced security setting deactivated

</BR>

After this last move, security warnings appear, and the attack is a bit mitigated, </BR>
but not completely, and also the opening of the file occurs much more slowly, line by line, </BR>
thus making the attack less effective, but it's still work.

</BR>

The only interesting thing for the purpose left is javascript protection:</BR>
https://helpx.adobe.com/acrobat/using/javascripts-pdfs-security-risk.html#javascripts_in_pdfs_as_a_security_risk

</BR>

One could easily create a JavaScript script that loops over a visualization of a carefully selected </BR>
set of ascii characters (section "Some reasoning about the Image Files"").</BR>
But frankly, programming in javascript is pretty lousy for me.... </BR>
Besides, i've already spent a lot of time on boring tests and i don't feel like getting bored again.</BR>
It may be that i will do it in the future, maybe...

</BR>


<h2>A very brief process analysis</h2>

</BR>

First of all, as you can see, Adobe has created a temp file in the \AppData\local\Temp\acrord32_sbx\ folder.
And it reads the information from that file, I think it's sandbox protection. </BR>

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/sec/procmon.PNG" width="777">
</p>

</BR>

<p>
  <img src="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/sec/setposition-readfile-procmon.PNG" width="777">
</p>

</BR>

An example of Adobe's temp file can be seen here:</BR>
https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/sec/A9sl8bw3_40h7ca_62o.tmp

</BR>

But of course the content of the file is unreadable.

</BR>

I then applied some filters, to see at the registry and process level how Adobe behaves.

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/sec/adobeprocess.PNG" width="777">
</p>

As you can see it initially opens the registry key <b>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\Shell\Associations\UrlAssociations\http\UserChoice</b>.

</BR>

This path contains information about the default application used to open URL addresses of type "http". For example, </BR>
if you click on an "http" link in a document or on a Web site, the operating system will use the application specified</BR>
in this registry key to open the link. Changing this registry key may allow you to choose a different application</BR>
to open "http" links instead of the default one.For example, the Windows default browser settings are in this path.</BR>
The \Prodig subfolder contains information about the default application used to open URL addresses of type "http". For example, </BR>
if you click on an "http" link in a document or on a Web site, the operating system will use the application specified </BR>
in this registry key to open the link. Changing this registry key may allow you to choose a different application to open </BR>
"http" links instead of the default one.

</BR>

After that, set a set of keys in the path <b>HKEY_CURRENT_USER\Control Panel\Cursors\CursorBaseSize</b>

</BR>

The registry key you mentioned, <b>\HKEY_CURRENT_USER\Control Panel\Cursors</b> </BR>
contains information about the mouse cursor configuration for the current user. </BR>
For example, this registry key might contain information about the size and type of mouse cursor that will be used, </BR>
as well as on the position of the cursor on the screen.

</BR>

I think that the Adobe Reader program uses the registry key <b>\HKEY_CURRENT_USER\Control Panel\Cursors\CursorBaseSize</b> </BR>
to store information about the mouse cursor size used by the user. </BR>
This information could be used by the program to ensure that the mouse cursor is displayed correctly when using the program</BR>
In fact having used so many ASCII characters I have dozens of such queries open.</BR>
So it would be interesting to play a little bit with this specific registry key and see what happens...</BR>

</BR>

Another thing I went to see is how Adobe launches pdf files, and apparently it does it with the following command: 

</BR>

<b>"C:\Program Files (x86)\Adobe\Acrobat Reader DC\Reader\AcroRd32.exe" --type=renderer /prefetch:1  "PATH_TO_PDF\file.pdf" </b>

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/sec/adobe-start-command.PNG" width="777">
</p>

</BR>

Adobe uses the <b>"--type=renderer"</b> and <b>"/prefetch:1"</b> command options to open pdf files.

</BR>

It is likely that the Adobe Reader program uses the <b>"--type=renderer"</b> option to initiate a rendering process to display the contents</BR>
of a PDF file. In this way, the program can ensure that the content of the PDF file is displayed correctly and optimally for the user. </BR>
The <b>"/prefetch:1"</b> option could be used to start loading the content of the PDF file before the user actually opens it, in order to </BR>
reduce loading time and provide a better viewing experience. In general, using these options allows the Adobe Reader program to </BR>
efficiently handle PDF files and provide a good viewing experience for the user.

</BR>

I then tried to launch the pdf by completely eliminating the two options:

</BR>

<b>start "C:\Program Files (x86)\Adobe\Acrobat Reader DC\Reader\AcroRd32.exe" "%USERPROFILE%\Desktop\Scroll_ASCII_Crasher.pdf"</b>

</BR>

But it didn't work, this is probably because calling the file <b>C:\Program Files (x86)\Adobe\Acrobat Reader DC\Reader\AcroRd32.exe</b> </BR>
via start command probably still reproduces the two options dubbed above, since you have to call the Adobe executable, </BR>
which will still open the pdf again with the two options.

</BR>

I then did some testing with the --type option

</BR>

Here are some of the values supported by the <b>--type" option</b>:

</BR>

--type=renderer": starts a rendering process.</BR>
--type=gpu-process": starts a GPU process</BR>
--type=utility": starts a utility process</BR>
--type=zygote": starts a zygote process "--type=ppapi": starts a pp process</BR>
--type=browser": starts the main browser process</BR>
--type=gpu-broker": starts a GPU broker process</BR>
--type=crashpad-handler": starts an error-handling process</BR>
--type=nacl-loader": starts a loading process for Native Client</BR>
--type=service-manager": starts a service management process</BR>
--type=network": starts a network process</BR>
--type=ppapi-broker": starts a broker process for Pepper</BR>
--type=ppapi-flash": starts a Pepper flash process</BR>
--type=extension": starts an extension process</BR>
--type=profile-import": starts a profile import process</BR>
--type=service": starts a service process.</BR>
--type=audio-service": starts an audio service process</BR>
--type=cdm": starts a digital content management process</BR>
--type=gpu-sandbox": starts a GPU sandbox process</BR>
--type=in-process-gpu": starts an embedded GPU process</BR>
--type=installer": starts an installation process</BR>
--type=network-service": starts a network service process</BR>
--type=oobe": starts an initial configuration process</BR>
--type=profile-resetter": starts a profile resetting process</BR>
--type=renderer-sandbox": starts a rendering sandbox process</BR>
--type=sandboxed-process": starts a sandbox process</BR>
--type=snapshot-service": starts a snapshot service process</BR>
--type=speech-service": starts a speech recognition service process</BR>
--type=tracing": starts a tracing process</BR>
--type=viz-service": starts a visualization service process.

</BR>

I've only tried a few, but you'd have to do some attempts in the future, there's to say that not all of them </BR>
are accepted as Adobe commands, but as already mentioned I did just a couple of attempts to see what happened.

</BR>

While the /prefetch: option does not accept any parameter (at least from what they say on Google, confirmed later by GPT Chat), </BR>
or rather it only accepts the path to the file to be launched, but no numeric parameters, neither true nor false (1 & 0), </BR>
so it is very strange that it has parameter 1, it could be an error...

</BR>

The last interesting thing I noticed were a number of BUFFER OVERFLOWS, on different dll: ntdl.dll, KernelBase.dll, kernel32.dll, and more.

</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/sec/bof.PNG" width="777">
</p>


</BR>

<p>
  <img src="https://raw.githubusercontent.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/main/CASE%20STUDY/sec/bof%20dll.PNG" width="777">
</p>

</BR>

In fact, with a simple google search you can find several examples of buffer overflows to Adobe dlls.

</BR>

Some Examples:

</BR>

https://vulners.com/saint/SAINT:87E25D27930DA4EC4B02D093DE63B91E </BR>

https://support.ixiacom.com/strikes/exploits/clientside/cve_2014_8457_adobe_reader_rectangle_bo.xml

</BR>

I will return in the future to analyze the dlls that I have pinned precedently.

</BR>

<h2>Final Conclusions.</h2>

</BR>

In the end I wasn't able to optimize the attack to the extent they hope, but I learned several interesting things and that's enough...</BR>

Anyway, I posted this study here on Github more for me than anything else (to remember the steps, etc.), </BR>
and then because maybe someone can find interesting insights to do something good with it.</BR>

If I have time I will come back to it in the future, especially on the dlls, and process analysis.

</BR>

All the files i used for the tests can be found in the <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/tree/main/CASE%20STUDY">"CASE STUDY"</a> folder.


</BR>






