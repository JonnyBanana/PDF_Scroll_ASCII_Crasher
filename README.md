# PDF_Scroll_ASCII_Crasher

A PDF that crash Adobe Reader,  just a little discovery that i want to share.



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

And so I accindentally discovered a way to crash Adobe Reader, </BR>
a likely good start to unearth more serious vulnerabilities... </BR>

So I want to share this little discovery with other geeks and researchers,</BR>
so that they can (maybe) get something good out of it.</BR>

In the "PDF" folder you can find the pdf that crashes Adobe Reader.

</BR>


<b>How to reproduce the issue:</b>

</BR>

For better understanding I will include all the exact steps I took to create the pdf, starting with the .png image </BR>
i started from. If you want you can skip some steps (read below).

</BR>

<b>-1</b> Downlaod this png: https://github.com/JonnyBanana/PDF_Scroll_ASCII_Crasher/blob/main/CASE%20STUDY/Hand_pointing_gun_meme.png
</BR>
<b>-2</b> Convert the png to Ascii here (download it as html file): https://manytools.org/hacker-tools/convert-images-to-ascii-art/
</BR>
<b>-3</b> Convert the html file to pdf here: https://www.sejda.com/html-to-pdf
</BR>
<b>-4</b> open the pdf and scroll up and down a couple of times, at this point the application should crash (see video below).

</BR>




Adobe Reader Scroll Shortcuts


-Press Ctrl + Shift + H to initiate auto-scroll in Adobe Reader

-Adjust the scroll speed using the up and down arrow keys

-Press the minus key (-) to change the scroll direction

-Press Ctrl + Shift + H to stop auto-scroll

