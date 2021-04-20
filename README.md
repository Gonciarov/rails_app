So this is where our game begins. I will try to creat a social media app where:

- we can add new users;
- users can upload pictures and create posts;
- users can comment on posts;
- users can like posts;
- users can make friends with other users.

I will use two different resources here: first is Michael Hartl's book on Ruby on Rails (where he creates a Twitter clone), and another is David Battersby tutorial on Youtube.

To make my life less complicated and to save myself from incompatibilities in future work, I'd like to run all dependencies (gems) exactly as in Hartl's book, as it says: "Important note: For all the Gemfiles in this book, you should use the version numbers listed at gemfiles-4th-ed.railstutorial.org instead of the ones listed below".

Bad news for C4K students is that the full list is available online only. Good news is that I am privileged and will copy it from there for your convenience:

---

source 'https://rubygems.org'

gem 'rails',        '5.1.6'
gem 'puma',         '3.9.1'
gem 'sass-rails',   '5.0.6'
gem 'uglifier',     '3.2.0'
gem 'coffee-rails', '4.2.2'
gem 'jquery-rails', '4.3.1'
gem 'turbolinks',   '5.0.1'
gem 'jbuilder',     '2.7.0'

group :development, :test do
  gem 'sqlite3', '1.3.13'
  gem 'byebug',  '9.0.6', platform: :mri
end

group :development do
  gem 'web-console',           '3.5.1'
  gem 'listen',                '3.1.5'
  gem 'spring',                '2.0.2'
  gem 'spring-watcher-listen', '2.0.1'
end

group :production do
  gem 'pg', '0.20.0'
end

# Windows does not include zoneinfo files, so bundle the tzinfo-data gem
gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw, :jruby]

---

So paste this instead of your current gems list and run 'bundle install --local' in command line.

I got this:

---

You have requested:
  spring = 2.0.2

The bundle currently has spring locked at 2.1.1.
Try running `bundle update spring`

If you are updating multiple gems in your Gemfile at once,
try passing them all to `bundle update`

---

Seems most of gems now switched to necessary versions, but gem 'spring' was prevented from changes by Gemfile.lock. 

Good news is that Gemfile.lock in our case can be altered without risks, as it normally contains a list of Gem versions already being in use by other parts of code. This file has been created automatically by Rails when 'bundle install' or 'bundle update' has been called for the first time, and its aim is to keep fixed gems configuration for all versions of the app. However we have just created our app and have not written a single line of code, so Gemfile.lock can be updated. I have just opened it and changed 'spring' version to 2.0.2. 

Now our app seems to be matching Hartl's book's settings.

Btw if you don't know what gem 'spring' stands for, don't worry: me neither. I will google it later if I really need to know that.
 






