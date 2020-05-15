---
layout: post
title:      "My First Sinatra Project -- Kiddo Care"
date:       2020-05-15 23:27:03 +0000
permalink:  my_first_sinatra_project_--_kiddo_care
---


	For my Sinatra project I decided to start working on a project that I’d been thinking about for awhile now -- that being, an all-in-one solution for Childcare Management. The idea came to because I’ve seen my mom use pretty outdated and lackluster Childcare Management software and figured it would be a perfect starter Sinatra project. Obviously this is a very watered down version of what I hope to eventually build it out to, but nevertheless -- that is what I decided to build for my Sinatra Project.
	Even though I did have some programming experience before coming to Flatiron, most of this stuff in the Sinatra section was pretty new to me, as I had never worked with databases or worked on a MVC (Model, View, Controller) app before, and because of that I was pretty nervous and overwhelmed when I took a peek at the section. That being said, once I dove in, I felt pretty comfortable going through the material.
As you work through the material you quickly realize just how powerful both Sinatra and ActiveRecord are (as well as the Bcrypt gem.). Sinatra is a framework  that allows us to quickly and painlessly create MVC apps (with help from Active Record of course). From within Sinatra, we get access to things like routes,which allow us to quickly create HTTP requests, params, which allow us to quickly retrieve and use data that is passed through forms that users submit (as well as the URL), and layouts/templates, which allows us to easily create a full blown site in a short amount of time. When you make your layouts and templates, Sinatra just knows where to look for them when you call to render them, its actually pretty neat.
	While Sinatra is the pretty face, Active Record really works its magic in the background, along with Bcrypt. As far as Bcrypt, it allows you to create secure passwords in a matter of seconds, you simply add the gem to your app, add a password_digest to your appropriate table, add ‘has_secure_password’ to your model and you’re set -- it just works with Active Record seamlessly. Bcrypt take the password, hashes it, and salts it, which makes it extremely difficult to unhash and figure out what the password actually is. When you include ‘has_secure_password’ your ‘:password’ attribute will automatically receive validations from Active Record. At this point you simply need to add the rest of the validations via Active Record, which to be honesty, I thought would be way more difficult than it was. I must’ve taken care of all of my validations within a few minutes. Something that felt really magical about the entire process was that, if an object fails to create, save, or update, Active Record just generates the error messages for you -- which allows you to quickly show those errors to the user.
As far as my actual app -- at the time that I’m writing this blog, the app is pretty bare bones, as it only allows the user to sign up, add children, and add employees. Once a user creates those things, they can edit and delete them as they please. My model was set up as follows:

* Users have many children and have many employees
* Children belong to a user
* Employees belong to a user 

	As far as design, I ended up using Boostrap as I knew that for myself it would be the quickest and most painless way to spruce the project up a bit, since I’ve used Bootstrap in the past. The design definitely needs to be tweaked and optimized a bit more but for this project, I felt that it was good enough.
	Overall, I feel like I learned a ton in this section and I look forward to seeing what kind of magic Rails provides me.

