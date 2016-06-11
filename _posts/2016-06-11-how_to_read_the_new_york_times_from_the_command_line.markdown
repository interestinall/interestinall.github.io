---
layout: post
title:  "How to Read the New York Times from the Command Line"
date:   2016-06-11 16:06:37 +0000
---


First [download](https://rubygems.org/gems/nytimes_cli) the nytimes_cli gem. Or just go to the terminal and type `gem install nytimes_cli` then run `nytimes_cli`. You should see a screen like this:

![nytimes_cli](http://i.imgur.com/vyzav4K.png?2)

Type `man` for a list of commands or the number of the article you would like to read. 

It's that simple.

## How the Nytimes_cli Gem Works

The nytimes_cli is a web scraper. It targets specific sections of the html/css on [nytimes.com](http://nytimes.com) and pulls back information like article titles, article content, and author names, using [mechanize](https://github.com/sparklemotion/mechanize), and stores it in arrays and hashes. This information is then iterated through and transformed into article objects and printed to the console where you read it. You can have a look at the source code [here](https://github.com/interestinall/nytimes_cli/).

## Development Challenges

I started out using [open-uri](http://ruby-doc.org/stdlib-2.1.0/libdoc/open-uri/rdoc/OpenURI.html) and [nokogiri](https://github.com/sparklemotion/nokogiri). This combination worked fine to scrape the front page of [nytimes.com](http://nytimes.com), but when I wanted to navigate from the front page to the individual article, I came upon some troubles, chief among which was handling cookies. Indivudal pages on the site serve up cookies and if your program can't do anything with them, the page only serves up subscription information -- not the actual article you are looking for. So after a bit of googling I found out about [mechanize](https://github.com/sparklemotion/mechanize). Mechanize is a really powerful gem that does a lot more than what I used it for, but where it really helped me was dealing with cookies, which it does automatically.

The other main challenge I had was that people were getting all sorts of errors when they downloaded the gem in its first few versions. The errors were kind of cryptic but all centered around certain files not being found, although there were files where the program was looking. In the end, these problems turned out to be related to gem dependencies. Since I had all of the dependecies downloaded locally, everything worked great for me. But by not forcing the dependencies on the gem itself, it allowed others to download the gem and try to run it without all of the other code it needs to work. Again google helped me. It turns out you add rutime dependencies like so `spec.add_runtime_dependency 'example', '~> 1.1', '>= 1.1.4'`. Once I added the two runtime dependencies, it forced their download and the program worked out of the box for others as well.



## Take Away
Despite the many small frustrations, and thanks to the [learn.co ](https://learn.co) community's valuable insights, I built and published my first gem. It's an awesome feeling! Now I have the ability and confidence to make other gems that I've been daydreaming of. The only trouble is deciding which one to start first :)








