---
layout: post
title:      "CLI Data Gem Portfolio Project - Charity Roulette"
date:       2019-07-14 10:55:29 -0400
permalink:  cli_data_gem_portfolio_project_-_charity_roulette
---


About a week ago, I began working on my final project for the Object Oriented Ruby section of the Flatiron School curriculum. A majority of the time spent on the project was spent attempting to come up with an idea for the project, as I have trouble coming up with projects oftentimes that are pracitcal, and that I also find interesting. I decided to go with something that meant a lot to me, with the idea of providing a program that encourages charitable donations. Upon having a basic premise down, I began navigating the website https://www.charitynavigator.org, which grouped charities by categories such as Animals, Arts, Culture, Humanities, and Human and Civil Rights. 

Upon seeing this, I came up with an idea that was to function as a sort of roulette for charities, with the program assigning the user a random charity based on their choice of category, and then assigning them a random dollar amount from their inputted range, so that no one would be persuaded to spend any more money than they were comfortable with. I then separated this idea into two parts, the first being scraping the website to navigate from a category, through a subcategory, to an individual randomized charity, and the second part being a random dollar generator that takes a user input.

I immediately began watching some of the resource videos, like Avi Flombaum's Daily Deals video, which was incredibly helpful in building the gem, and the recorded lectures from Enoch Griffith on web scraping. These were instrumental in me completing the project, as they created a sort of framework that I could take inspiration from as I generated my own ideas and methods. 

I began with the CLI, or the command line interface of the project which starts with a welcome to my gem, and then a list of the initial categories scraped from the website. In order to scrape these categories, I used the nokogiri gem, and inspected the sites HTML until I found exactly what I was looking for, the name of the category. The code to scrape these categories looked something like this:

`    def self.scrape_categories
        doc = Nokogiri::HTML(open("https://www.charitynavigator.org/index.cfm?bay=content.view&cpid=4529"))
        doc.search(".category.clearfix.list-url-discover div.cat-box").each do |div| 
        category = self.new
        category.name = div.search("h3").text
        category.url = "https://www.charitynavigator.org/#{div.search("a").attr("href").value}"
        category.save
        end
    end`
		
This code created the process by which a category was created, named, and assigned a URL. The "save" method above was used to save the name and url information in an array called @@all_cat, while the iterator ".each" was used to iterate over each "div" in the HTML, so as to separate each name as a separate category, rather than combining them all into one object. Once this was scraped, I had to find a way for the user to view this information, so in the CLI file I wrote a code that takes the @@all_cat array and iterates over each, giving each one an index and listing them out for the user. From here a menu method was created which takes a user input to choose a category from the list, provided that input is an adequate integer. 

A similar method was used to scrape the subcategories, and then the charities and both were saved into their own arrays @@all_sub and @@all_char, however the @@all_char array only saved the names of the charities, rather than the name, the object ID, and the URL. A method was created called charity_assigner within the CLI, which used the ".sample" iterator method to take a random index from the @@all_char array, and assign a random charity to the user. 

Now that this process was completed, the remainder of the project, creating the random dollar amount generator, was incredibly easy by comparison. Within the CLI, I created minimum_value and maximum_value methods, which prompted a user to input an integer value. Provided an integer was inputted, and that the maximum value was not less than the minimum value inputted, the range method would be called which puts a random number between the two values chosen. After this has been done, the CLI runs the goodbye method, which puts "Thank you for playing, go out and make a difference!"

I had a lot of fun throughout the process of designing and improving this project. Though it was my first experience with creating something from nothing in my coding experience, I now know that this is something I genuinely enjoy doing, and the autonomy of the project ensured that I was only working on something that I genuinely wanted to explore. I look forward to continuing to code, and improving my coding methods as I grow through this course!
