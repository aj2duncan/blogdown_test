---
title: "Testing Rmd to md using knitr"
date: "2016-08-06"
slug: "testing-rmd-to-md-using-knitr"
---



I use [Rmarkdown](http://rmarkdown.rstudio.com) a lot. I have recently been preparing lecture notes using it and I wanted to see how easy it would be for me take an Rmarkdown document and create a blog post. 

Firstly, this whole website is built using [Jekyll](https://jekyllrb.com/) which means that I need each of my blog posts to start with the date and then the title. For instance this blog post came from a file named `2016-08-26-Testing-Rmd-to-md-using-knitr.Rmd`. I then need to create a markdown (or html file) of the same name. This is no problem with the R package [knitr](http://yihui.name/knitr/). All we need to do is


{% highlight r %}
knit("2016-08-26-Testing-Rmd-to-md-using-knitr.Rmd")
{% endhighlight %}

and it'll convert to _.md_. For Jekyll this needs to end up in a folder named `_posts` and any figures need to be placed where they can be accessed. To take care of this I put them in my `images` folder.

To do all this automatically I wrote this script which always re-knits all my Rmd blog posts.

{% highlight r %}
# Script to knitr all the Rmd files into md blog posts.
# load package
library(knitr)

# delete all previous figures
file.remove(dir(
  path = "images/figs/",
  full.names = TRUE
))

# set base url for links
opts_knit$set(base.url = '/', base.dir = getwd())
# Setting directory for figures
opts_chunk$set(fig.path = "images/figs/")
opts_chunk$set(fig.cap = "center")

# get all filenames
filenames = list.files("Rmd/", pattern = "*.Rmd")
num_files = length(filenames)

for (i in c(1:num_files)) {
  # split the blog title from the .Rmd file so we can create the .md blog file
  blog_title = unlist(strsplit(filenames[i], "[.]"))[1]
  knit(input = paste("Rmd/", filenames[i], sep = ""),
       output = paste("_posts/", blog_title, ".md", sep = ""))
}
{% endhighlight %}

Just so we can see what plots look like I've included the default demo from an Rmarkdown document.


{% highlight r %}
plot(pressure)
{% endhighlight %}

![center](/images/figs/Test-Rmarkdown-1.png)

