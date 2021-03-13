title: ExamView and Amazon S3
---

These instructions are for TCS teachers who wish to create tests in ExamView that they
can send directly to their students to take online.

## Requirements

 - Internet access
 - A PC or Mac (instructions written on a PC)
 - ExamView Test Builder

## Request a site

Email help@tbcnh.on.spiceworks.com to request a TCS test hosting website. Include your name and the classes that you teach. You will receive an Access Key ID and a Secret Access Key. These are your username and password. Keep them safe and don\'t forget them!

## Setup

 - Download and install WinSCP, accepting all the default settings in the installation.
 - Run WinSCP
 - Select Amazon S3 from the File Protocol dropdown.
 - Enter the Access Key ID and Secret Access Key that were provided to you.
 - Choose Save if you want to save these for later use.
 - Login.
 - If it worked, you should see two folders on the right called tbcnh and tcs-classwork.

## Create a test

 - Create a test in ExamView Test Builder
 - Go to File/Export/HTML.
 - Enter a title for the test. For example, Chapter 10 Test.
 - Choose Export as test.
 - Enter your name and school email address.
 - Click OK
 - Create a new folder for your test.
 - Open the folder your just created.
 - Save the test as index.html

## Upload a test

 - Start WinSCP
 - Select Amazon S3 from the File Protocol dropdown.
 - Enter the Access Key ID and Secret Key that were provided to you.
 - Choose Save if you want to save these for later use (less secure, more convenient).
 - Login
 - On the left, browse to the folder containing your test files.
 - On the right, browse to tcs-classwork/*yourname*/*class*.
 - Create a folder for the appropriate chapter. For example: 10 for Chapter 10.
 - Create a test folder inside the chapter folder.
 - Copy index.html and the index_files folder into the test folder.
 - Choose OK.

## Send the link to your students

 - The prefix of your link is: http://tcs-classwork.s3-website-us-east-1.amazonaws.com/
 - Form the suffix of the link by combining your username, class, chapter and test like this:  
   *username*/*class*/*chapter*/test  
   For example: gfeindel/physics/10/test
 - Combine the prefix and suffix to form the test link:  
   http://tcs-classwork.s3-website-us-east-1.amazonaws.com/*username*/*class*/*chapter*/test  
   For example: http://tcs-classwork.s3-website-us-east-1.amazonaws.com/gfeindel/physics/10/test
 - Send this link to your students.

## Tips

 - Keep all folder and file names lowercase. Don\'t use spaces.
 - Organize files on your PC using the same class\chapter\test structure.
 - Create all your quizzes and tests at once, organized by class\chapter\... and use the Synchronize button in WinSCP to copy all at once.



