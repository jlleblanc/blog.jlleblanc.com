---
title: 'Project in review: Truffle'
---

A little over a year ago, I decided to start an open source project called [Truffle](https://truffle.jlleblanc.com). I searched NPM and the name "truffle" was available, but I didn't reserve it because I didn't have any code to show for it yet. Unfortunately for me, blockchain developers got a hold of the package name and it's now serving as tooling for Ethereum. By the time I realized this, I had already started calling my project Truffle and had told all of my friends about it. I decided to stick with the name and figure out NPM later.

It's just as well that I didn't, because I've realized that while I had a lot of plans for making software around Truffle, I never had time to do anything more than make a reader for my own site. However, it did not all go to waste. Creating Truffle gave me a sandbox for trying out new ideas and libraries.

I started off thinking I would build a general purpose reader that could read any JSON file off the web and present all of the fields as nicely formatted HTML. The biggest issue with this approach was that modern browsers generally (and thankfully) don't generally allow you to load arbitrary JavaScript files at runtime that don't come from your own domain. I could have worked around this by introducing a server side component, but that defeated my goal of never having to maintain a server for Truffle. CORS would have been a contender for working around this as well, except that it's incredibly difficult to work with even when you have access to all of the servers. I also considered building a browser plugin, but never really got around to doing that.

So I decided to continue building a reader, albeit one that would only read the JSON file from my own site. My initial thought was "I could whip this up in some old school jQuery in an hour or so." I tried dusting off those jQuery skills, then quickly realized I was going to be better served by a more modern framework. React was popular and seemed to be dominant, but this was also the moment where Facebook had added a distasteful clause about patents to React's license. I had heard a lot of good things about Vue, so I decided to give it a shot.

Vue was really good about letting me graudally use it in place of the awkward jQuery templating I was doing. However, I got to a point where I realized it was going to be faster to just start with a fresh Vue project. I finished the first iteration of the reader with Vue and had something presentable enough to share with friends.

Despite having something mostly working, I was running into some issues where Vue was not behaving consistently and I couldn't figure out why. The syntax mimicked some of the portions of Angular I wasn't as fond of (e.g., add attribute X to get Y behavior.) Overall, the learning curve was a bit steep, partially due to a major version bump that often left me wondering if I was doing the right thing.

Facebook removed the patents clause from React and so I took another look. I found [Gatsby](https://www.gatsbyjs.org): a static-site CMS built in React. This proved to be just what I need: something simple enough that it doubled as a example, while being complete enough to deploy as a finished website. I rewrote my reader once again, managing to preserve my URLs and fix all of the quirks I encountered in the Vue version. Looking back, my issues with Vue may have had more to do with not being as familiar with these component-oriented frameworks. If I had time, I might go back and see if I could get better results with Vue after all.

I had a lot of plans for Truffle and for finding ways of getting people involved in the project. Ultimately though, what I discovered with writing Truffle was a fun and different way of writing content. Instead of spending mental energy on finding a way to express a thought in paragraph form, I could start with a comment and then add the portions of the subject afterwards. For example:

```
{
  "Comment": "Sometimes Netflix's content is unsettlingly targeted!",
	"TV show": "Tidying Up With Marie Kondo",
	"Enneagram type": 1
}
```

Beyond a style of writing, I've concluded Truffle is just a hobby for me. Much in the same way some guys do model trains in their garages, I like firing up my terminal and playing around with some JSON. If you want to have a look, [head on over](https://truffle.jlleblanc.com), but mind the dust and crazy glue!