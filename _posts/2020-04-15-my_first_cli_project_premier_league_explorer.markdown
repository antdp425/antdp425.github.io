---
layout: post
title:      "My First CLI Project: Premier League Explorer"
date:       2020-04-16 01:19:53 +0000
permalink:  my_first_cli_project_premier_league_explorer
---



 Ever since I signed up for Flatiron School and heard about the project for Module 1, I began writing a list of ideas as they came to me during my first couple of weeks in the program while working on labs. I had about 5 to 6 different ideas but ultimately I ended up choosing to do something about soccer, something that I am extremely passionate about (and miss dearly due to COVID-19). I strongly believe that working on projects that pertain to your interests allows you to get the most out of your projects, as you will know about your interests better than most people, which will allow you to not only care more about the project,  but will help you get more out of it as well, since you will be particular in terms of what data you want and how it should be formatted. There were a few sections of my project that I thought would be worth sharing.
	The goal of my project was to create a quick way to view information and stats about teams in the English Premier League. I was able to accomplish this with the FootyStats API, which, even on the free tier, gave me more data than I knew what to do with. Once I got my API set up, it was time to create my objects.
 As most of us would have done, I created my Team class, created a bunch of attr_accessors, and created my standard initialize method -- which took in a number of different arguments about the team instance I was about to create. I knew that there was a better way of doing this via [mass assignment](https://learn.co/tracks/online-software-engineering-structured/object-oriented-ruby/metaprogramming/mass-assignment-and-metaprogramming), but I was honestly a bit intimidated by it, so I chose the long way / ugly way. After a quick project review with my cohort lead, I was able to turn this:
```
   def initialize (name:, founded:, position:, wins:, draws:, losses:, g_scored:, g_conceded:, matches_played:, website:, goal_difference:, points:)
      @name = name 
      @founded = founded
      @position = position
      @wins = wins
      @draws = draws
      @losses = losses
      @g_scored = g_conceded
      @g_conceded = g_conceded
      @matches_played = matches_played
      @website = website
      @goal_difference = goal_difference
      @points = points
      save
   end
```
..into this:
```
   def initialize (team_hash)
      team_hash.each{|k,v| self.send("#{k}=",v)}
      save
   end
```

 I think we all know which one is prettier.
 I mentioned that I wanted to display team stats and their current position in the table. This meant I was going to have to do some serious formatting if I wanted to have my CLI project to look somewhat presentable. I originally tried to use the .center method on my strings, but in all honestly, it was such a massive headache and did not seem worth using. I ended up using an amazing gem called terminal-table which not only allowed me to easily format my stats into a clean table format, but it allowed me to do it quickly and painlessly. 
	Overall, I would say that after just one project, the project portion of Flatiron School truly does seem to be a hidden gem (as my cohort lead would say), as it forces you to really think about all of the labs you’ve worked on in a particular module and put them to use so that you can not only meet all project requirements, but build a one of a kind project for your portfolio. As someone who has had a tiny bit of programming experience, this project was not too challenging, but nevertheless I still learned a ton. 

If you are interested in playing with or contributing to my project you can find it in the Github repo posted below.

https://github.com/antdp425/premier_league_explorer

