---
layout: post
title:      "Waves: A CLI Project to find local beaches"
date:       2019-11-14 20:25:06 -0500
permalink:  waves_a_cli_project_to_find_local_beaches
---


The first project with Flat Iron School is to create a CLI Program that scrapes data from another site.

These are the Project Requirements:

1. Provide a CLI

2. Your CLI application must provide access to data from a web page.

3. The data provided must go at least one level deep. A "level" is where a user can make a choice and then get detailed information about their choice. Some examples are below:
    - Movies opening soon - Enter your zip code and receive a list of movies and their details.
    - Libraries near you - Enter your zip code and receive a list of libraries and their details.
    - Programming meetups near you - Choose from an events list and receive details.
    - News reader - List articles and read an article of your choosing.

4. Your CLI application should not be too similiar to the Ruby final projects (Music Library CLI, Tic-Tac-Toe with AI, Student Scraper). Also, please refrain from using Kickstarter as that was used for the scraping 'code along'.

5.  Use good OO design patterns. You should be creating a collection of objects, not hashes, to store your data. Pro Tip:  Avoid scraping data more than once per web page - utilize objects you have already created. It will speed up your program

The first thing I had to do was set up the files and the depository. This was probably the toughest part about the whole project, just getting started. I think the only reason why is because in my head it was going to be really hard. So that's really the first step, get your head in the game, you got this!

Once you're in your sandbox, you can set up your files quickly by typing in "bundle gem *project name*". Mine was "Waves." Sidenote, I spent wayyyy too long trying to come up with a project name, it really doesn't matter what you name it! But "Waves" is cute,no? It takes in your zipcode and provides a list of beaches in your area.

Then you'll go to github and set up your repository. Then you go back to your sandbox and push over your files. There's four commands to remember for this step.

1. "git status": This command will list the files that are saved in green and those that are not in red.
2. "git add ." : If you have red, you'll want to save those. This command does that.
3. "git commit -m "*insert message*"" : this is commit, it's going to make a message that details what are your changes.
4.  "git push origin master" : This one actually pushes everything over to github.

You'll have these memorrized in no time, you do it literally every five minutes. Especially if your using the sandbox in Learn.co, because it crashes! If it crashes there is no way to recover, you will have to do it again.

The next thing I did was do some psuedocode to figure out how this was going to run. 

I figured I'd need 3 files: CLI for the CLI code, Beach for the beach objects and Scraper for the scraping.

I also set up the environment to require all the correct gems, like pry for coding, and nokogiri for scraping. Then you'll also want to require (relative) all the files needed to run your program.

Once I had everything I wanted to do settled, I decided to start with the CLI. I set up a welcome message and a fetch method to get the list of beaches from the scraper.

Then I went over to scraper. This actually took a long time because I couldn't find a website a website that was going to be fun to scrape. Originally I thought google.maps but that site's code makes it really hard to code. I ended up going with yelp! I spent some time looking at the website code and figured I'd be able to get every thing I needed, plus ratings which google maps does not provide. 

Then I hit a hiccup. When I ran the code to test the program, I found out yelp doesn't allow scraping. I then changed my method over to API. Learned how to do that from Juan's handy dandy video tutorial. 

The main difference is with scraping, you have to go hunting in the website code. While in API's, you get this hashlike file you have to navigate through called "json". Its like a hash of arrays, and arrays of hashes. I was able to itterate over the array within the hash to find all the qualities (name, address, rating) I wanted each beach object to have.

Then I set up my beach objects with its attributes. I just initialized with all the qualities and had the API method create beach objects as I iterated through the json. I also set up an @@all variable and shoveled new instances in upon initialization.

This took alot less time than scraping, I like API's.

Then I had to actually create the list. For this I iterated through Beach.all. I used "each.with_index" starting with 1, to do this so I could provide a numbered list. This was everything in the API method.

After this in the program, I wanted to ask the user which beach the wanted the address and rating of. So I put that into the CLI and grabbed that number to run a new method.

In this method, I saved the number minus one to become the index. Then I plugged that into the Beach.all array and returned those features in a sentence.

Here I also coded in a question for the user. I provided 3 options. One to get info about another beach on the list, Two to enter a new zipcode or anything else to exit. This is basically the end of the program. I just set a conditional. If the answer was one I called the same method over, if it was two, I returned to the beginning of the program, and if it was anything else, I provided a goodbye message and exited the program.











