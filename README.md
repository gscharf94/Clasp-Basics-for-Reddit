"# Clasp-Basics-for-Reddit" 

I know a lot of people on the subreddit are beginners and maybe don't even know about Clasp, so I figured I'd make a small tutorial to help people get familiarized with Clasp so they can be more productive. Personally, I hate using the Google editor. The auto-indent screws me up and I hate not having the auto-complete feature that editors like VS Code or Sublime give me.

NOTE: I suggest everybody here download one of those two, with VS Code being the currently superior editor. Although some people feel strongly about Microsoft, so Sublime Text is fine too. 

## Step 1, Download Node.js and Clasp

First, you will need to install Node.js on your PC. This is essentially an interpreter for Javascript. In other terms, it allows you to run Javascript code on your system without needing a browser. It's very useful and there are *a lot* of different libraries you can install with node. Clasp is one of those.

* [Download Node.js from here](https://nodejs.org/en/)

Once you have node.js installed, you can double check to if you have it installed by opening your command line (on windows you can hit Windows Key + R, then type "cmd" and press enter) and then typing in node. If installed properly, you should get an output like this

![command line node](/images/1.PNG)

From here, you can exit node by typing in ```.exit``` and you should be back to your command line. From here, to install clasp you type in 


```npm install @google/clasp -g```

This will install clasp globally on your system. You should see some text fly by on your terminal and bam, you now have clasp installed. For more info on clasp, you can go to [Google's page about it.](https://developers.google.com/apps-script/guides/clasp)

Once installed, you will want to type in

```clasp login```

which will open a webpage in your default web browser for you to sign into your Google account. Then you will need to give clasp permissions to edit your GAS scripts. Once logged in, you don't need to do this again as it is global.

## Step 2, creating a new project

I'm going to assume people aren't familiar with git, which is a similar application, so I'll try to explain everything. First, let's create a new project. Create a new folder wherever you want, I'm going to go with "test-project". Copy paste the path to the folder by selecting the address bar in File Explorer

![address bar](/images/2.png)

Then go back to the command line and type in ```cd your/path/here```

![cd](/images/3.PNG)

This will set your active directory to your project folder. You will need to always do this other clasp will not know where your project is. The way clasp works, is it looks for a file called 

```.clasp.json``` in the active directory

This is a file that looks like this:

```
{"scriptId":"1KxcBCi2xJJL3tAW7CUoL4PrNeAD65ACLq0bIek37RglsGIMR_9XBwzK"}
```

Each of your GAS projects has a script id, much like each of your files and folders in drive. To see the script id, you can go open your script in the web browser and look at the URL bar. 

Anyhow, to create a new project you type in

```clasp create nameOfProject```

We will create a new project called "test-project"

![create project](/images/4.PNG)

Clasp will give you some options, and we will select "stand alone" for this example. This will create two files in our directory

![two files](/images/5.PNG)

The .clasp.json file holds our script ID so clasp knows where to pull and push information from and the other has some other info like time zone and the runtime version (that is outside the bounds for this tutorial)

Now that we have created a project, we can do a quick "clasp pull" and it will pull in the file "Code.js" with our default starter code

Now we can open up our "Code.js" in VS Code or Sublime and edit it with our editor. Let's add in some test code.

![test code](/images/6.PNG)

We save the file and then go back to our command line and type in "clasp push" and it will automatically push to the project and if we then type "clasp open" we will see that our changes have been made in Google's system

![push](/images/7.png)

![open](/images/8.PNG)


## Cloning a project that already exists

Ok, so it's pretty simple. First, get the script ID by opening the script editor up in a web browser and finding it in the URL. Next, create a text file called ".clasp.json" in the directory you want the code to be copied into. Then in that file copy paste this text, replacing the "SCRIPTID" with your actual script id.

```
{"scriptId":"SCRIPTID"}
```

Then, with a command line set to that same directory, just type in "clasp pull". All the files from your GAS project will be downloaded into that directory, and whenever you type in "clasp push" the same file will be updated.

## final notes

If there are any things people wanna change feel free to let me know this was written by me in like 20 minutes so hopefully there aren't too many mistakes. It may seem a little overwhelming for poeple new to this stuff, but it will make your coding a lot more enjoyable because the online editor just doesn't cut it, at least in my opinion.

Also, pushing to github with git works in a similar way as this, and that's a good habit to get into with your coding projects, as you can track the changse over time in your project. So I would suggest people look into that. If you learn clasp, git is just learning a couple commands that do the same thing. Instead of "clasp create", you do "git init" or instead of "clasp push" you do "git push origin master". Same thing, different commands. 