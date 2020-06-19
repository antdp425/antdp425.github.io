---
layout: post
title:      "My First Rails App - Gym Hero"
date:       2020-06-19 23:46:10 +0000
permalink:  my_first_rails_app_-_gym_hero
---



Sticking with the ongoing theme of working on projects that have SOME meaning to me, I decided to build a gym management Rails app, being that, as a person who is into fitness, owning or working in a gym was something that I considered quite a bit. Based on the requirements of this project, my app, at the time of submission can do the following.

* Create Classes and Members for a Gym, 
* Create sessions or Scheduled Classes for those particular classes and link them to members and the gym.
* View/Manage those members, classes, and scheduled classes as needed
 
**Models**

The requirements for this app asked us to:

* Include at least one has_many, at least one belongs_to, and at least two has_many :through relationships

* Include a many-to-many relationship implemented with has_many :through associations - with the join table having at least one user submitted attribute

My models looked like this:

*Gym*
* has_many :members
* has_many :gym_classes
* has_many :scheduled_classes

*Member*
* belongs_to :gym
* has_many :scheduled_classes
* has_many :gym_classes, through: :scheduled_classes

*GymClass*
* belongs_to :gym
* has_many :scheduled_classes
* has_many :members, through: :scheduled_classes

*ScheduledClass*
* belongs_to :gym
* belongs_to :member
* belongs_to :gym_class

The idea here with ScheduledClass was that it could almost act as an "appointment" which could then me queried and group as needed in my app.

i struggled a lot in the beginning to figure out the best way to structure the models, but after building out the app a bit, I feel pretty good with what I put together.

**Validations**

Trust me this isn't as boring as it sounds. Aside from the usual basics of presence and uniqueness options for an attribute, I made great use of *validates_uniqueness_of*. This was really handy when I was creating sessions -- it essentially allowed me to make sure that whenever (stay with me here.. ) i created a new session time for a class, regardless of including a user or not, it would validate that it was unique not only for that gym class, but also for that member.. all in one line which was pretty sweet to do, thanks to it allowing you to pass in a scope. It looked something like this:

*models/scheduled_class.rb*
`validates_uniqueness_of :time, scope: [:gym_class_id, :member_id]`

**Scope Methods**

For my project, I was also asked to make a class level scope method, at first this seemed pretty intimidating but i ended up using it quite a bit and kind of fell in love with it. At the end of the day it essentially acts as another method in your application except it looks a bit nicer and istantly lets you know what you're getting. Also, scope methods return objects, not arrays...like Rubys .find method, which in OOP land.. is pretty sweet when you want to work with results of a query.

**It wasn't all fun and games**

For one reason or another, while it felt like I learned a lot in this section and I had a lot of fun implementing each part, this is the project that also beat me up the most and took me the most time to complete quite honestly. I'm not sure if its because it was one of the first apps I've worked on that had four seperate models to worry about, or because I started psyching myself out prior to the project even starting. Never the less, I'm really proud of what I put together and I hope to be able to add some sweet features to it somewhere down the line. On to Javascript!

You can view my project [here](https://github.com/antdp425/gym-hero) .
