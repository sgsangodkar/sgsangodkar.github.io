---
layout: post
title:  "Jekyll Docs"
date:   2023-07-16 19:13:10 +0900
category: jekyll docs
---
# Welcome

**Hello world**, this are some important guides for creating jekyll website.

I hope you like it!

To add an image, place in image in assets folder in the root directory [not inside assets subfolder folder present in _site folder].

![Hello World](/assets/hello-world.png)

# Displaying an index of posts
<ul>
  {% for post in site.posts %}
    <li>
        <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>



{% for tag in site.categories %}
  <h3>{{ tag[0] }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}

For more information about Jekyll posts, chekout the official [Jekyll posts documentation][Jekyll-posts-documentation].

# Collections
Collections are helpful to group related content.

# Writing Latex in Jekyll posts
To include LaTeX equations in a Jekyll blog post, you can use MathJax, which is a JavaScript library that renders mathematical equations on web pages. 

Here's how you can set it up:

1. Include MathJax in your Jekyll blog's layout or template file. You can do this by adding the following code in the <head> section of your layout file or the specific page where you want to display equations: <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>. This code includes the MathJax library from a Content Delivery Network (CDN). It's recommended to use a CDN for optimal performance, but you can also download MathJax and include it locally if desired.

2. Configure MathJax to recognize and render LaTeX equations. Create a configuration file called _config.yml in the root directory of your Jekyll project if it doesn't exist already. Add the following lines to the file:

{% highlight ruby %}
markdown: kramdown
kramdown:
  math_engine: mathjax
{% endhighlight %}

This configuration tells Jekyll to use the Kramdown Markdown engine with MathJax as the math rendering engine.

3. Now you can write LaTeX equations in your blog posts using the appropriate syntax. Surround your equations with $$ or \( and \) for inline equations, and with \[ and \] for displayed equations.

[Jekyll-posts-documentation]: https://jekyllrb.com/docs/posts/
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-collection]: https://ben.balter.com/2015/02/20/jekyll-collections/