---
layout: post
title:      "How I learned through my sidecar/notes."
date:       2019-05-29 17:57:19 +0000
permalink:  how_i_learned_through_my_sidecar_notes
---

I'm a fulltime student at the flatiron school's online full stack software engineering course. I'm writing about my third school project, a full stack (ruby on) rails app. I created a recording studio recording session scheduler. The app was built using html,css, bootstrap, rails, a few gems( see below), and of course ruby. 

During my previous two projects I needed to restart (rebuilding my app from scratch) at least twice for different reasons that are 100% not embarrassing, trust me. The restart process involves me retracing my steps to hopefully get to the point where I think something went wrong, and hopefully I fix the issue.  It's kinda like time travel. I wanted to decrease the time that I'd spend restarting/rebuilding my app from scratch. I decided to use a digital document/note to keep track of my progress. I called it a sidecar (made-up name). Here are three ways that my sidecar helped.

`#all gems used
gem 'pry'
gem 'devise'
gem 'omniauth-github'
gem 'database_cleaner'`

I used the devise gem to setup Oauth login with github. Initially I created all 4 models with devise. That was a bad idea, so I needed a restart. Then I realized that the model that I used devise on had issues with restful routes. So I needed a restart and create  separate model for devise and Oauth. About 3 or 4 restarts later I had a pretty good idea about how not to create a model using devise. Tracking my progress set off a chain of events. 


`#chain of events
I decreased the time it took me to restart app. 
I enjoyed the restarting process more.
I was more more willing to restart 
I learned more each time I restarted` 

Between restarts I had issues with seeding to sqlite3 (the database) and later a dropdown menu on my new.html.erb page. I documented both issues in my sidecar. I figured that I might run into the same issues after my next restart (and I did). After trying them out in my app I also saved code snippets that with notes about how and why each code snippet did or did not work in my code. When I had an issue I could go back to the sidecar to review the pros and cons of the code that I had already tried. I usually have a ton of commented out code to clean up afterward a project but I had less due to this strategy. 

I extended my sidecar with my handheld whiteboard. For example, I used the board to create a quick chart of models and restful routes that needed to be created. I took a picture of the chart and imported it into my notes. Then I used the chart to confirm that the routes existed, had proper controller actions/logic, model associations, etc.  The whiteboard notes helped me take a break from the computer screen and work out more abstract theories like what I should expect from a nested route and if it would fulfill a certain project requirement.

I enjoyed this project. GOing from back-end to full stack is a fun process. It can be overwhelming though. I learned a great way for me to be more adventurous while also maintining my organization. 
