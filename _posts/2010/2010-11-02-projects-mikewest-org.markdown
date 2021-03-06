---
layout: post
title:  projects.mikewest.org
tags:
    - projects
    - opensource
    - webdevelopment
    - webdev
    - documentation
    - bestpractice
    - vimroom
    - pyplaceholder
    - staticgettext
    - i18n
    - l10n
    - jslint
    - hudson

Teaser:
    One question you're almost certainly not asking yourself is "What's Mike
    West been up to?"  That's a shame, really, as I've got some projects
    floating around that I'm proud of, and that I'd like to share with you.
    Moreover, I'd like to point out the project documentation pages
    that I've put together as a meta-project; I think it's worth your time
    to take a look.
---
"What _has_ Mike West been up to recently?"  This is one question that you almost certainly haven't been asking yourself recently.  That's a shame, really, as I've got a few small projects floating around that I think you might be interested in paying attention to.

If you'll indulge me, I'll run through them in no particular order:

*   [VimRoom][] is a Vim plugin that replicates the best features of [WriteRoom][] in my favorite editor.  I do most of my writing (code and otherwise) in Vim, as the keyboard shortcuts I've [painstakingly assembled][vimrc] are hardwired into my fingers (and, I suppose, because I'm a huge nerd).  Combined with [iTerm2][]'s brilliant fullscreen mode, VimRoom offers a great way to shut out the myriad distractions floating around my iMac, and focus on actually getting words onto the screen: I'm pretty pleased with how it's turned out, and I hope it might be useful for others.

[vimroom]:    http://projects.mikewest.org/vimroom/
[WriteRoom]:  http://www.hogbaysoftware.com/products/writeroom
[vimrc]:      http://github.com/mikewest/homedir/blob/master/.vimrc
[iTerm2]:     http://sites.google.com/site/iterm2home/

*   [`static_gettext`][sg] is a (tiny) internationalization framework that makes it possible to generate arbitrary localizations of static source documents.  Dynamic frameworks like Django or Rails have good systems in place to deal with the tough problems of removing hard-coded strings from source code and templates.  Less complex, static websites aren't going away, however, and `static_gettext` has solved the problem for me nicely, generating industry-standard `*.po` files that can be easily handed off to translators.  The framework is currently seeing active use on the [HTML5 Boilerplate][html5en] site for the [German translation][html5de] (which I helped out with), and a few other localizations [are in the pipe][html5trans].

[sg]:         http://projects.mikewest.org/static_gettext/
[html5en]:    http://html5boilerplate.com/
[html5de]:    http://de.html5boilerplate.com/
[html5trans]: http://github.com/nimbupani/html5boilerplate-site/issues#issue/3

*   [JSLint Utils][jslintu] is a command-line wrapper for JSLint that makes it possible to quickly lint your JavaScript and CSS files via the magic of either Node.js (fast!) or Rhino (not so fast!).  Lint results can be output as XUnit-style XML files, making it possible to cleanly integrate into a variety of continuous integration systems ([Hudson][], for example), meaning that you don't even have to think about it: you just get friendly emails after every commit you screw up.  It's a lifesaver!

[jslintu]:  http://projects.mikewest.org/jslint_utils/
[Hudson]:   http://hudson-ci.org/

*   [PyPlaceholder][] is a command-line Python script that generates placeholder PNGs for use in... well... wherever you might use placeholder PNGs.  It's made my life a little simpler while putting together mockups, and it has a few tiny features that I didn't see on any of the surprisingly numerous alternatives.  I've additionally wrapped it up in a [Flask][] application, [`flask-pyplaceholder`][fpyp], to generate images on the fly via [placeholder.mikewest.org][pmo].

[PyPlaceholder]:  http://projects.mikewest.org/pyplaceholder/
[Flask]:          http://flask.pocoo.org/
[fpyp]:           http://github.com/mikewest/flask-pyplaceholder
[pmo]:            http://placeholder.mikewest.org/

*   [Send To Instapaper][sti] is a stunningly well-named Chrome extension that has no purpose other than to replicate the standard Instapaper-bookmarklet functionality with two small additions: it adds a keyboard shortcut, and it's streamlined, clean, and pretty.

[sti]:  https://chrome.google.com/extensions/detail/liamajdghafnpofaconeimppimbdbhgi/

And now, the point...
---------------------

I read Jesper's [Doc Robot][doc] this morning, and found myself nodding vigorously.  I disagree about the inherent valuelessness of _all_ autogenerated documentation (as I've also been doing a good bit of work on Ryan Tomayko's [Rocco][], which autogenerates lovely documentation if you do the work of coding in a literate fashion), but I think he makes a great point about the way we generally treat documentation as an afterthought.  I'd like to share the solution I've come up with for my code.

[Rocco]: http://github.com/rtomayko/rocco

You'll notice that these projects that I've linked to above all have landing pages that more or less clearly explain what the project is, how it works, and what your next steps might be, should you be interested enough to want to try it out for yourself.  Each of those landing pages also has a clear changelog, and an RSS feed that you can subscribe to, should you be interested in keeping yourself up to date.  There's even an [RSS feed for the site][projectsrss], in case you'd just like to have a good handle on what it is that I'm up to.

I think this is the bare minimum a project needs to offer in order to begin to serve an audience.  I've put together [projects.mikewest.org][projects] in order to have a clear place to put any and all documentation I generate for the projects I'd like to present to the public.  The ever so clever [Tim Huegdon][timmah] has put together a similar project listing with good documentation, and I'd like to encourage _you_ to do so as well.

GitHub pages makes the process of putting together a basic website hassle-free, and you can take a look at the [project page repository][mikewest] to see how I've bent Jekyll to the task of generating RSS feeds and embedded changelogs.  It's not rocket science, but it took a bit of experimenting that you can spare yourself.  Use the repo as a template.  There's nothing there I wouldn't gladly share.

[doc]:          http://waffle.wootest.net/2010/11/01/doc-robot/
[projects]:     http://projects.mikewest.org/
[projectsrss]:  http://projects.mikewest.org/atom.xml
[mikewest]:     http://github.com/mikewest/mikewest.github.com/
[timmah]:       http://projects.timhuegdon.com
