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


<b>-5</b> The technique does not work with just any HTML to PDF Converter(see more detailed analysis below)..
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
The technique works this way as well, although I must say that it is more difficult to get the program to start crashing. It follows, then, that the trick works regardless of the character used, but that it works slightly better with special characters, especially when mixed together.</BR>
In any case, I considered analyzing the conversion to html more than anything else, as I think the bulk to understand is there.

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





All the files I used for the tests can be found in the <a href="https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/tree/main/CASE%20STUDY">"CASE STUDY"</a> folder.


</BR>

I didn't even notify Adobe, first of all because they don't pay for their bug bounty program, not that I wanted money for that crap, but I don't appreciate that company policy.</BR>
I would much rather have others enjoy it too.

</BR>



