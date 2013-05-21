---
layout: post
title: "Deploying WordPress with Capistrano symlink issue fix"
date: 2013-03-04 12:22
comments: true
categories: Capistrano WordPress Deployment Symlink themefm
---
# Fix from "[Tutorial: Deploying WordPress with Capistrano](http://theme.fm/2011/08/tutorial-deploying-wordpress-with-capistrano-2082/)" by [Konstantin Kovshenin](http://theme.fm/author/kovshenin/)
I was using the three blog posts by [Konstantin Kovshenin](http://theme.fm/author/kovshenin/) about using Capistrano with WordPress. The blog post tutorials were written in 2011. 

I kept having issues with the symlink code used in the post. The code looks like this:

	namespace :myproject do
	    task :symlink, :roles => :app do
	        run "ln -nfs #{shared_path}/uploads #{release_path}/application/wp-content/uploads"
	    end
	end
	
	after "deploy:symlink", "myproject:symlink" 
	
##Problem: Tasks not being executed on ``cap deploy``
Not having a Ruby background, I couldn't easily debug the situation. To keep it short, every time I ``cap deploy`` the commands in the ``:myproject`` would not execute.

I believe the newest Capistrano no longer uses the ``"deploy:symlink"`` as a valid trigger. Therefore, the snippet originally provided was not working.

##Solution: Change trigger

It's not a fancy outcome, but I changed the line:
	
	after "deploy:symlink", "myproject:symlink"
	
to

	after "deploy", "myproject:symlink"
	
Now my symlink is run correctly and I am able to see my tasks run when I ``cap deploy``.

**This is a fix to issues I found in Tutorial: Deploying WordPress with Capistrano](http://theme.fm/2011/08/tutorial-deploying-wordpress-with-capistrano-2082/)**
