#Static Sites, Git, and git-ftp

When hosting a static website you must upload your files individually to your server. This task can become time consuming as you add to the site. It can also be easy to forget what changes you have made and which files you need to reupload. What if you could have git style version control with your host? Well you can with a community project called git-ftp. Most hosting services allow for some type of ftp; you will need to ensure your host has this and set up an ftp server for your site (this differs depending on the service you use; read up on the docs from your hosting provider). Having version control will allow you to not have to reupload large files or remember what files need to be uploaded which can be helpful.

git-ftp is [here](https://github.com/git-ftp/git-ftp)

Follow the instructions in the repo to get git-ftp installed and set up on your machine. Once you have that set up you can resume this tutorial.

Note: I was going to try this with the student web server provided by CofC but I could not ever get connected to the ftp server. If you are able to connect to the server this should work in theory, but since I have a hosting provider I decided to not get caught up troubleshooting the student web server.

To begin we need to initialize git-ftp. We will do this by typing `git-ftp init -u YOUR_FTP_USERNAME -P YOUR_FTP_ADDRESS`

The options that are being used here are `-u` which is the username for your ftp server, and `-P` which is an "interactive" password. The interactive just means that you are going to have to type your password into the console after you run the command. There will be no indication that you are typing a password, but that is for security.

As an example let's say we set up an ftp server called example.com with a user named test and a password of simple. The above command would look like this `git-ftp init -u test -P example.com` and after running that command you would type simple in as the password and hit enter.

Any subsequent updates you have for the site you would use `git-ftp push -u YOUR_FTP_USERNAME -P YOUR_FTP_ADDRESS`. Make some changes to the index.html file and give it a try.

Keep in mind that when you push to your ftp server you are not pushing to github. There are ways around this but they are more in depth and out of scope for what we are wanting to accomplish here. Feel free to experiment and find solutions that best fit your project needs.