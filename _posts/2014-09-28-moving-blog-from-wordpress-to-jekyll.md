---
layout: post
title: Moving Blog from WordPress to Jekyll
---
# Why Ditch WordPress?
I've been moving around my blog to many different places. I've used Posterous before it closes, Tumblr, WordPress.com and self-hosted WordPress. Moving a blog is not easy. I have to backup all the posts and assets, and formating doesn't migrate perfectly every time. But to me it's also fun at the same time. Specially when new tools come out, I enjoy to try them.

However, the main reason I moved from self-hosted WordPress to Jekyll this time was because my hosting service was close to expire, and the price I had to pay to extend was too high. Most of the hosting service(e.g. GoDaddy) provide a discount price at the first contract, but when you extend it the price goes up so high. Just like cable services in U.S.

# Why Jekyll? And what is it?
Then I stumbled upon [GitHub Pages](https://pages.github.com), and I found out that I could use a open source tool called [Jekyll](http://jekyllrb.com) with the GitHub Pages. First of all, it was free! It was not easy as WordPress to setup, but I was challenged as a developer.
I couldn't use PHP nor MySQL on GitHub Pages, but Jekyll supports all the blog features without them. Jekyll uses many of the new technologies such as [SASS](http://sass-lang.com), [Markdown](http://daringfireball.net/projects/markdown/) and [Mustache](http://mustache.github.io), and I was willing to try them.

# GitHub
I kind of fell in love with [GitHub](https://github.com) while I was working on their service. I love how they embrace the open source community and their passion about details. If you know how to program and willing to share your works, GitHub is a free playground for you. For example, I can just make anything for my personal website with HTML and Javascript, and push to GitHub Pages without any restriction of storage, as long as you open them to public.

# Migrating Posts
I used [WordPress.com import method](http://import.jekyllrb.com/docs/wordpressdotcom/) instead of [Self-Hosted WordPress](http://import.jekyllrb.com/docs/wordpress/). Because after a few research, it seemed to use Self-Hosted method you need a full access to your hosting server. I was not sure if that'll work for me, so I just went with more certain way. I exported my blog data using export tool in the WordPress dashboard, and imported them to Jekyll. All images were import to the asset folder, but post files were not perfect. Meta data in each post didn't look pretty on the default Jekyll theme, so I had to modify each post. I changed all of them from HTML to Mardown format. I didn't have a lot of posts, so it didn't take that long.

# Design
I had my own WordPress theme design, but I create a new design for the Jekyll. I modified the default theme of Jekyll, and made it as simple as I could. SASS made it so easy to work with CSS.

# Responsiveness
These days making a website responsive so that it can look fine on the mobile devices is a must. Fortunately the default Jekyll theme had all the option for responsiveness so I just had to modify a few things.

# Custom Domain
I have my own domain(seanchoe.com), and I would like to use it for my new blog for sure. However, I couldn't use a URL like seanchoe.com/blog because Jekyll only works on the root URL on GitHub Pages. There are two ways to make a GitHub Page. One is "user or organization site" which you can only make one per an account, and the other is "project site". my user site URL for GitHub Page is seanchoe.github.io, and I could connect it to seanchoe.com. However, I couldn't make a subdirectory on the user page for Jekyll blog because like I said, Jekyll only works on the root directory. So I made a new project site by creating a new project on GitHub called "blog" and created a branch named "gh-pages".

To connect a custom domain to a GitHub Page, you have to create a file named "CNAME" on the root directory of GitHub Page and add one line with the URL you want to use. In my case it was "blog.seanchoe.com". Then I went to the domain management service's website(I use [hover.com](https://www.hover.com)), and added a A record pointing to seanchoe.github.io. And it just worked. I didn't have any content on seanchoe.com yet, so I just added a domain forwarding from seanchoe.com to blog.seanchoe.com.

# Comments
You can add commenting feature to Jekyll using [Disqus](https://disqus.com) easily, but I just didn't want to add comments to my blog. I'd like to keep it simple.

# Search and Sitemap
You need a special treatment to add a search feature on Jekyll blog. We can use plugins like [Jekyll + indextank](https://github.com/PascalW/jekyll_indextank) or [Jekyll + lunr.js](https://github.com/slashdotdash/jekyll-lunr-js-search), or you can add a embed custom search. I added a [Google Custom Search](https://www.google.com/cse/all) snippet. You can even customize the style of the search box. To let Google to search all the posts in your blog, you need to submit a sitemap to [Google Webmaster Tool](https://www.google.com/webmasters/tools/home?hl=en). You can easily generate a sitemap file using [this trick](https://help.github.com/articles/sitemaps-for-github-pages). One more benefit of doing this is that people can also search your blog contents on Google.

**Update:** I changed Google Custom Search to Jekyll + lunr.js. Because the sitemap.xml was not reflected in real-time, so the search didn't work as expected. However, there was a problem. You [cannot use](http://jekyllrb.com/docs/plugins/) Jekyll plugin on GitHub Pages. To solve the problem, you have to install the plugin when you test on the local server, then copy the search.json file from "_site" folder to the root folder before you sync to GitHub.

# A Downside
WordPress has it's own mobile app which let you write posts even when you're not with your laptop. But with Jekyll, as far as I know, the only way you can write a post so far is to create a file and push it to GitHub using a laptop.

# Conclusion
All of this process took me approximately 3 days. It was not bad at all. I also learned many things. And after all, I saved a lot of money.
