Download Link: https://assignmentchef.com/product/solved-ece404-homework-2-data-encryption-standard
<br>
The goal in this homework is to help you understand the implementation of the DES (Data Encryption Standard).

Problem 1

Write a Perl or a Python script that implements the full DES. Refer to Lecture 3 on the course website as it outlines the key steps to DES. Your algorithm must produce encryption/decryption results using an encryption key.

<strong>Program Requirements</strong>

Your script for Problem 1 should have the following command-line syntax:

DES_text.py -e message.txt key.txt encrypted.txt DES_text.py -d encrypted.txt key.txt decrypted.txt

An explanation of this syntax is as follows:

For encryption (indicated with -e), your script should read the input text from a file called message.txt (or whatever the name of the command-line argument after -e is). The next argument key.txt is the file containing the 64-bit DES encryption key in <strong>text string </strong>format. The encrypted output should be saved in <strong>hexstring </strong>format

to a file with the name of the final argument, in this case a file called encrypted.txt.

For decryption (indicated with the -d argument), the input hexstring file is specified with argument after the -d argument, in this case encrypted.txt. The next argument specifies the file containing the DES decryption key (keep in mind the key used for both encryption and decryption should be the same). The decrypted output should be saved to a file with the name specified by the last argument, in this case decrypted.txt.

You are encouraged to use the starter file that is a part of the gzipped archive for Lecture 3 at your instructor’s Lecture Notes website. This starter file includes all the permutation “tables” you need for the homework. In addition to this starter file, the gzipped archive also includes a script for generating the round key, a script for showing the permutation of the encryption key, a script demonstrating the substitution step, and a .txt file with the eight S-box tables.

The plaintext bit size is not necessarily divisible by the DES block size. For the sake of this assignment, your program can pad the last block with zeros if this is the case.

<h2>Problem 2</h2>

As you will soon learn in lecture 9, block ciphers such as DES should not be used in the manner used in problem 1 – directly encrypting the data in independent blocks (known as electronic code book mode). Because each block of data is encrypted independently, overall patterns in the data may still be obvious if used to encrypt an image, for example. This is not readily apparent when encrypting text like in Problem 1.

Therefore your job in problem 2 is to write a script that takes an image in PPM format, uses DES to encrypt the image data (<strong><u>NOT </u></strong>the PPM header) with a key contained in a text file, and then combine the encrypted image with a PPM header (you can use the original image’s header) so you can write it as a readable PPM file. The result should be the encrypted image viewable as a PPM file.

<strong>Program Requirements</strong>

The call syntax for your program is similar to Problem 2:

DES_image.py image.ppm key.txt encrypted.txt

Here image.ppm is the input image you will encrypt, key.txt is the key you will use for encryption, and image enc.ppm is the name of the .ppm file you will write the encrypted image to. You may use parts of your script from problem 1 for this, though you probably won’t use all of it as text may be read differently than image data. Keep in mind you are not required to implement image decryption for Problem 2.

A “.ppm” image file consists of a header and the actual image data. The header occupies the first 3 lines of the file, and the rest is the image data (pixel values) that you want to encrypt. For those interested in a more general approach, descriptions of the PPM header can be found at:

<ul>

 <li>http://netpbm.sourceforge.net/doc/ppm.html</li>

 <li>http://paulbourke.net/dataformats/ppm/</li>

</ul>

<h2>Text and Image to be Used for the Submitted Output</h2>

The text and image to be used can be found in the Homework section at the course website at https://engineering.purdue.edu/ece404/homework.htm

The text is from a wired.com article discussing the Meltdown and Spectre vulnerabilities (it starts with “Earlier this week…”). The image is a PPM of a helicopter.

For debugging purposes, we have also have posted to the homework section a file named first round.txt containing the left and right halves of the first plaintext block after the first Feistel round for the text file mentioned above.