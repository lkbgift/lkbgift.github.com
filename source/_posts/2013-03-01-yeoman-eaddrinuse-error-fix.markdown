---
layout: post
title: "Yeoman EADDRINUSE error fix"
date: 2013-03-01 11:59
comments: true
categories: Yeoman Development bugfix
---
# Yeoman

I recently fell into the bandwagon of Yeoman. After spending time with Peepcode screencasts to deepen my understanding of jQuery, javascript and MVC frameworks, I decided TDD and Grunt were crucial to m y development process. Having people like Chris Coyer and Paul Irish on my radar made me finally fess up and get Yeoman running locally.

## Getting Running

Issue with running Yeoman is initially my allergic reaction to automated terminal commands. I am not always fond of seeing foreign words run by my command line, but I try my best to understand what they are doing.

Grunt installs itself when you run ``Yo Webapp``. Theres little you need to do to have working scaffolded application with TDD 'infrastructure' in place (aka Mocha, Grunt, JSLint, etc). When you follow the directions from Yeoman.io, its easy to get the web app running

## Problems

I started having problems when I wanted to run ``Grunt server``. When I ran ``Grunt`` alone, the process ran without any problems. For some reason, when I tried to test the server, Grunt would hang up on LiveReload. Specifically, I got this message:

	Running "server" task
	
	Running "clean:server" (clean) task
	
	Running "coffee:dist" (coffee) task
	>> Destination not written because compiled files were empty.
	
	Running "compass:server" (compass) task
	Nothing to compile. If you're trying to start a new project, you have left off the directory argument.
	Run "compass -h" to get help.
	
	Running "livereload-start" task
	... Starting Livereload server on 35729 ...
	
	... Uhoh. Got error listen EADDRINUSE ...
	Error: listen EADDRINUSE
	    at errnoException (net.js:769:11)
	    at Server._listen2 (net.js:909:14)
	    at listen (net.js:936:10)
	    at Server.listen (net.js:985:5)
	    at Server.listen (/Users/lkbogdonoff/sites/portfolio/node_modules/grunt-contrib-livereload/node_modules/tiny-lr/lib/server.js:133:15)
	    at Object.startLRServer (/Users/lkbogdonoff/sites/portfolio/node_modules/grunt-contrib-livereload/lib/utils.js:21:11)
	    at Object.module.exports (/Users/lkbogdonoff/sites/portfolio/node_modules/grunt-contrib-livereload/tasks/livereload.js:44:20)
	    at Object.task.registerTask.thisTask.fn (/Users/lkbogdonoff/sites/portfolio/node_modules/grunt/lib/grunt/task.js:78:16)
	    at Object.Task.start._running (/Users/lkbogdonoff/sites/portfolio/node_modules/grunt/lib/util/task.js:282:30)
	    at Task.runTaskFn (/Users/lkbogdonoff/sites/portfolio/node_modules/grunt/lib/util/task.js:235:24)
	    
I posted a bug report to the Yeoman Github repository [here](https://github.com/yeoman/yeoman/issues/938) and pinged [sindresorhus](https://github.com/sindresorhus). Within a day, another user replied on the Github issue thread explaining he had the same issue. Similarly, Sindre Sorhus also pitched in to help.

## Solution

Eventually, I didn't figure out what would solve the problem. I found a stop-gap measure which lets me continue running ``grunt server`` and have a local copy run without issues. 

In Grunt.js, I needed to remove the line calling ``livereload-start``. I did this by changing the grunt.task.run like this:

    grunt.registerTask('server', function (target) {
        if (target === 'dist') {
            return grunt.task.run(['build', 'open', 'connect:dist:keepalive']);
        }

        grunt.task.run([
            'clean:server',
            'coffee:dist',
            'compass:server',
          //'livereload-start',
            'connect:livereload',
            'open',
            'watch'
        ]);
    });
    
## Reflection 

Even through I had googled portions of the error code in hopes of finding someone with a similar situation, there were no people with my exact situation. As a result, I thought about updating my Gems, Command-Line Tools and various brew packages. The Github issues response time was great. I'll keep trying to get a better understanding of how to use Yeoman. For the time being it works!

