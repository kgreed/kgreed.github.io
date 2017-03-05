---
layout: post
category: code,Github-pages
---
When I heard about GitHub pages, I wanted to give it a try
![Websites for you and your projects](http://i.imgur.com/LuBKVqC.gif)

but without dissapearing down a rabbit hole.

I am so pleased to say I have it working, without needing to install Jekyll on my machine or even fumble with git command lines.

I found the instructions at[https://pages.github.com/](https://pages.github.com/ "GitHub Pages") somewhat confusing.

The draw card phrase "*Hosted directly from your GitHub repository. Just edit, push, and your changes are live.*"  gave me the idea that I need not actually install anything local to my computer. And indeed this is actually the case.  

I was able to create my user repository, _config.yml, add a url and even choose a theme without too much drama, but the next piece led me awry....



Why then did step 3 ask "What git client are you using?"

It just so happens that I use Source Tree, which was not an available option.  Thus I selected "A terminal", ignored the git clone instructions and used Source Tree to clone my repository to my local drive.

The instructions stop with the creation of a index.html containing the word "Hello World"

I pushed, and lo, there was an extremely boring "hello world" text displaying on my website.

What happened to the lovely layout I viewed when picking the theme ?

Scrolling down the beautiful instructions page I see 

![Now that you're up and running, here are a few things you should know](http://i.imgur.com/m87vjxD.gif)

What, I need to learn how to set up Jekyll? Surely a rabbit hole there.... smelling Linux as a Windows user..

I turned to Stack Overflow for help, determined to get by without actually installing Jekyll.

I switched to using index.md because, hey, Markdown has less cognitive load.

The next important piece of wisdom was to add some YAML Front matter to the top of my index.md

    ---
    layout: default
    ---

    Hello, world!


Now at least I had something looking like the theme as advertised in the theme chooser.  However my repository name was displaying where the title should have been.
More turning to Stack Overflow, ah, so I need to customise the default.html.   What? I dont have a default.html.  
It turns out that I need to go to the site repository for my theme, copy the _layouts\default.html and then edit my _config.yml to set the title.

    theme: jekyll-theme-tactile
    title: Cognitive Load
    description: Kirsten Greed's blog. Journeys in focus,code and community
    show_downloads: false

Lovely!

And for my first blog?

A bit more experimenting and I discover that if I muck up the html in default.html, GitHub kindly emails me a "Page Build Failure" message.

    {% for post in site.posts %}   
       <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
       <p><small><strong>{{ post.date | date: "%B %e, %Y" }}</strong> . {{ post.category }} .</small></p>
    {% endfor %}

I set up a separate post.html in the _layouts folder, and create my first post in the _posts folder.
Carefully following the nameing convention, and adding YAML Front matter to hook up the right layout

    ---
    layout: post
    category: code,Github-pages
    ---

One more bit of confussion, the video at [https://pages.github.com/](https://pages.github.com/ "GitHub Pages")  mentions an Automatic Page Generator.

However this is discontinued because of 
[https://help.github.com/articles/creating-a-github-pages-site-with-the-jekyll-theme-chooser/](https://help.github.com/articles/creating-a-github-pages-site-with-the-jekyll-theme-chooser/ "Theme chooser")

 






 