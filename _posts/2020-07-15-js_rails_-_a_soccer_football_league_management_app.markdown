---
layout: post
title:      "JS/Rails - A (soccer/football) League Management App "
date:       2020-07-15 18:39:34 +0000
permalink:  js_rails_-_a_soccer_football_league_management_app
---


What a rollercoaster of a module. The curriculum really takes you on a ride for the first week, especially if you're new/haven't touched JS in a while. You essentially get thrown into the deep end to learn how to swim, but its well worth it in my opinion.

As I've said in previous blogs, I feel its super important to have projects that revolve around your interests or just something you care about fixing, improving, etc. I will say this now and will say this to any new student thinking about enrolling in Flatiron School - **work on projects you care about, you will get so much more out of it.** My project for this module is a simple League Management App. At this point its mainly meant to be used for soccer/football league coordinators, but I think I'd like to expand it into other sports somewhere down the line. At the time of this blog post - the app simply lets you create leagues and create teams for those leagues.

While it was not my first JS rodeo, it was definitely my first "using a Rails backend WITH a JS frontend to perform CRUD actions" rodeo. Coming to Flatiron with previous programming knowledge made me worry a bit.. worry that I'd just be relearning a lot of it, but I was totally wrong. This was not a compex project, but it opened my eyes to how some sites truly work.

As far as the app itself:
- League has many teams
- League attributes: Name, Format(5v5,7v7,11v11, etc), Start Date, End Date
- Team attributes: Name, Manager Email, Manager Phone

One part about this project that I really enjoyed using was the active_model_serializer (AMS). Your Rails API allows you to filter out the bits that you want your routes to spit out (I like to think of serializer as an insideout version of x_params that you'd use to whitelst your data when writing to the DB), but it honestly gets messy pretty quickly. The AMS gem allows you to generate a serializer class for your models and pretty painlessly allows you to filter/add relationships in the blink of an eye. Back in your controller, simply render json-ing your instance of the model will return your newly serialized API data.

Coming over to JS after a few months in Ruby/Rails felt like it would be pretty challenging, but you quickly realize that regardless of the language you can only do so many things with a coding language, its just a matter of getting the right syntax (and google searches).

