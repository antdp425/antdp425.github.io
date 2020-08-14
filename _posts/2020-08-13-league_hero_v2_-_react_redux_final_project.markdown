---
layout: post
title:      "League Hero v2 - React/Redux Final Project"
date:       2020-08-14 01:17:37 +0000
permalink:  league_hero_v2_-_react_redux_final_project
---


As I've mentioned in my previous blogs -- I truly believe that any project that you work on in Flatiron School should be based on something that you are genuinely interested in. I've said it before and I'll say it again, you will gain so much more out of the projects by doing it on something you have a genuine interest in. So with that being said, my final project for Flatiron School was essentially a rebuild / version 2 of my Javscript project -- League Hero -- an app where (as of now) soccer league runners or coordinators can keep tabs on all of their leagues, except this time it was obviously built with React and Redux.

I wanted to rebuild this app because it was something that I could see myself working on after graduation. I wanted to have a solid React project to continue to grow and build my skills with after Flatiron School.

This project really pushes you do connect the dots with all of the material that you cover in this section -- you cover a massive topic like Redux in such a short amount of time, and yet it is a crucial part of your final project.

When I first started the project, while I knew how most of the app would work, it was really overwhleming just because I had to think about not only local state in my app, but all global state - and make sure that everything was always equal (both on the front end and back end).

As of now the app is pretty simple - you can only create leagues and teams that are associated with created leagues. While I wait for my assessment I hope to build out a few more features, like having players on teams for example.

One of the biggest things in this project that almost slipped under my nose, was the fact that, when deleting a league, all of the associated teams are deleted with it (jn the backend at least). So before I realized this, there were a few left over teams on the front end, that realistically didnt exist in the backend.  I needed to make use of useEffect to essentially refetch the teams when the Redux state changed, specifically when the leagues and teams from the global state (Redux) changed.

I still cant believe how fast these five months went, even midst a global pandemic. I am extremely proud of myself, but also my cohort mates for getting through the entire curriculum -- we came a really long way, especially considering a lof of us were completely new to backend technologies.

A big shout out and thank you to my cohort lead Nancy Noyes, who always went above and beyond what was expected of her.

