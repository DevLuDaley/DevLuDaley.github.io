---
layout: post
title:      "My first CLI, what I broke and how I fixed it"
date:       2019-03-17 21:26:23 +0000
permalink:  my_first_cli_what_i_broke_and_how_i_fixed_it
---


**Dad joke**

I figured my Knicks have been getting scraped (losing) all season… what’s another one?
Here’s the repo to ruby CLI gem project.

I wasn’t sure about what I wanted to create. After 1 month of coding bootcamp  I wanted something that I could build, celebrate, break, then repeat. I watched 3 or 4 videos suggested by my school plus about 5 or so others along the way. My plan was to review OO progrramming and consume a fair amount of CLI info and ideas in the week leading up to my project.  

**I had a plan, I promise**

My plan was to scrape Espn's New York Knicks roster webpage (http://www.espn.com/nba/team/roster/_/name/ny).
Then create tags (to be used as Player attribute values) for my player class including but not limited to name, height, and url.
Scraping was pretty straight forward. I used Nokogiri to scrape Espn. 

I used pry debugger whenever I got stuck trying to find a node. I used appended the syntax below to the end of each node to locate the data that I needed:

```
“children” => value of a type of nested node
 “attr” => value of  a type of nested node
“.values” => returns all values of nested nodes
“.size”  => returns how many elements a node contains, if any.
" [0]" => returns the value of the first element. 
"[-1]" => returns the value of the last element.
```

**Displaying player attributes**

Initially I thought that displaying the Knicks roster then displaying attributes of the player selected was enough to complete my assignment. I figured I’d find something else to build on top of that to make it more robust after making sure that the project requirements were met.
I soon learned that I needed to do a second scrape and return information from that second scrape to the user.

My goal was to have the program return 2nd scrape data based on the player selected.
I spoke with my cohort lead and attended a few study sessions to talk with my peers and bring some fresh ideas to the issue. 

I settled on two choices. (Knowing ruby I probably had 42 choices available.) 

    1- When the user selects a player include “more” as an option for the user to see additional details about the player they were already viewing. 

    2- When the user selects a player, cue the second scrape and add attributes from the second scrape to the attributes that already exist from the first scrape.

Due to time constraints I thought that option #2 would be most efficient and scalable, based on my current skillset. 

**Second scrape**

I did my second scrape on the player/stats page (see below) believing that to be the player_url page from scrape #1.
I was scraping the wrong site, which led to my player class' statistics(attribute values) being misaligned. 

To better explain the above, take Knicks player Kadeem Allen. 
Kadeem's player_url variable (the  site Nokogiri was pointing to):
```
#=> http://www.espn.com/nba/player/_/id/3134880
Kadeem's player-stats page url( the  site that I accidentally scraped)
#=> http://www.espn.com/nba/player/stats/_/id/3134880/kadeem-allen
```

I found the error and decided to scrape the player_url page that I already had access to from my first scrape rather than to find a way change the player_url variable to point to their player-stats page.

**Version Control or lack thereof**

Something weird happened with my version history causing my program to behave unexpectedly and I couldn't return to a previous state.
This mistake was different from the others. I had a local copy of my document but the remote copy on github hadn’t been handled appropriately. 
I used my dry erase board to draw a roadmap for the rest of my program and the issues that I needed to resolve. I used rubber ducky debugging principles to help me organize my thoughts. Writing out my plan helped me feel closer to completion. 

With my new roadmap I was able to schedule the completion of my app. I wanted to feel more comfortable with github so I took a break to read and watch a few videos on github, terminal, and/or vscode. I like the github features in vscode but I felt that I should know the terminal commands. So I learned a few handy git commands:

```
git status => to see current changes
git checkout file_name => switch from current branch to a different branch 
git branch -m new_file => rename local branch on local system (use while in branch yo want to rename)
git push origin :old_file new_file  => delete old remote branch and push new local new_file to github

```

**Back on the horse**

With my new plan in hand. I tacked my first issue.
My players were displaying incorrect attributes. 
I reviewed the player attribute values in my program with the source data on Espn. 
I tried many times. Then I called on rubber duck debugging again. I don’t have duck but I have a small Budhist monk named Budha. 

Role play dialogue:
    Budha: What do you want to accomplish?
     
    Me: I want the data in my app to be accurate already!

    Budha: Yea, of course you do, but more specifically…what do you want to accomplish?

    Me: <deep breath + exhale with a hint of frustration> I want to add 3 more attributes to my player class from this 2nd scrape page but that isn’t working…wait a minute….

It worked. Talking to Budha helped me realize, that I needed 3 more attributes. 
I already had lots of attributes from the first scrape.
I didn’t need to retrieve a specific attribute. I just needed three. 
I reviewed the player url page and found that some of the stats(potential attributes) were visible in more than one location. I scraped the other locations and the data was now consistent.  Problem solved! Woo hoo!

**Conditional statement**

Now it was time to tackle the minor bug that I’d been shelving until I knew that my project would require it.

Some players had no salary or no college while most had both and no one was mising both.
I needed conditional statements to support all possibilities since teams change and the Knicks are hopefully big buyers in the free agent market this off-season.
I tried a few option before I psuedo-coded my solution.

Conditional
Salary
College
#1
Salary[exists]
College[exists]

#2
Salary [exists]
College [does not exist]

#3
Salary [[does not exist]]
College [exists]

#4
Salary [does not exist]
College [does not exist]

Using gems to give the app more visual structure.
I used artii to make a little logo that someone from a different class suggested.
I found colorize to add color to the logo and the text of my program. 

**Final thoughts**

Overall I had a great time creating my project.
Over the past month I’ve gained a great deal of confidence in developing solutuions to structured problems. 
This project allowed me to become more comfortable with solving the kind of unstructured problems that exist in the real world world. 
