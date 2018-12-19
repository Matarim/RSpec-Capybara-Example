# README

For this Test Suite I&#39;ve added a few gems that I take advantage of when manipulating the browser, and making sure it acts as expected when running through the tests.  Below I will outline Key functions commonly used that will assist in further development of this Test Suite.  At the end of this Test Suite I will also include documentation and commands if you needed to setup a Test Suite from scratch in use for other projects.  The sites I have listed are good references if you are having trouble making a selection or manipulating the Web App/Page.

## Capybara Cheat Sheet: ([https://devhints.io/capybara](https://devhints.io/capybara), [http://cheatrags.com/capybara](http://cheatrags.com/capybara))
1. click\_link(&quot;ID, Name, Class, Title etc…&quot;)

2. click\_button(&quot;ID, Name, Class, Title etc…&quot;)

3. page.find, \_link, \_by\_id, \_field, \_button

4. visit &#39;/&#39;

5. check(&quot; &quot;), uncheck(&quot; &quot;)  #used for checkboxes

## Rspec Cheat Sheet: ([http://cheatrags.com/rspec-matchers](http://cheatrags.com/rspec-matchers))

1. .to include (works for arrays and strings)

2. .to be true, \_nil, \_falsey, \_truthy

3. .to start\_with(&#39; &#39;)

4. expect(page)

## Faker Cheat Sheet: ([https://devhints.io/ffaker](https://devhints.io/ffaker),[https://gist.github.com/mikekovacevic/8919216](https://gist.github.com/mikekovacevic/8919216))

1. Faker::Internet.email, .safe_email, .user_name

2. Faker::Lorem.paragraph, .paragraphs, .sentence, .sentences

3. Faker::Name.first_name, .last_name, .name

4. Faker::PhoneNumber.phone_number

## Test Framework setup:

For running this you will need to pull the Repo where you can access it from a command window. You will need to have Ruby either globally installed on your machine, or inside the directory once you&#39;ve pulled the Repo down.  The link for Ruby is [here](https://www.ruby-lang.org/en/documentation/installation/).

Another tool that you should have is Bundler.  To install bundler go into the directory for the project in a command window and type: gem install bundler.  After installing bundler run.  Bundle install inside that same command window.

If starting a new project you would open a command window then change into the directory of that project and then can run the following commands to setup the outline.
1. rails new
2. rails generate rspec:init (This makes a spec_helper file instead of the rails_helper. If you are building this test suite inside a project you would use 'install' instead of 'init')
3. bundle install (Run this every time you would make changes to your gemfile)

Next you need to require gems inside of your spec_helper.  For the project presented I used Capybara, Faker, Rspec, Selenium-Webdriver, Capybara-screenshot, and Chromedriver-helper. You should require the necessary to run before the tests above the "RSpec.configure do |config|" portion inside of spec_helper. 

## Running Test Suite:

Once everything is installed and you&#39;ve moved into the directory of the project you will need to setup Selenium-Webdriver for chrome.  To do this simply type chromedriver-helper inside the command window.  This will install the chrome driver for Selenium-Webdriver, and also start the instance that you will use to host the server instance.

To run the test suite open a new command window into the directory of the project then run: bundle exec rspec.  If you want to be selective of which spec file you run, you can run bundle exec rspec full\_path\_and\_file\_name.

Below is a breakdown of the different sections of the website that the framework tests. The tests run on Selenium webdriver for visibility.  Ideally for future development tests would be run using a headless browser like the deprecated PhantomJS or HeadlessChrome.  Failures are currently captured with screenshots saved directly into your directory.  In these tests I use Capybara/Rspec because it gives me the flexibility of using gems to aide in E2E tests as well as when built into the project is easily configured for integration tests.

## Tasks tested:
1. Global fields
2. Menu Content
3. Sign in link
4. Creating a new user
5. Email Validation
6. Form input
7. New User sign in
8. Home page
9. Landing page
10. Page Slider options w/ confirmed redirect
11. Sign in
12. Existing User
