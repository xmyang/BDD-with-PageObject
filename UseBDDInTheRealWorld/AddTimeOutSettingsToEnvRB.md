# Add time out settings to env.rb

Open "env.rb" under folder "features/support".

`cd ../support`

![alt text](https://raw.githubusercontent.com/hy1984427/BDD-with-PageObject/master/images/ChangeFolderForEnvRB.png "Go to env.rb")

Then change its content to following:

<pre><code>require 'rubygems'
require 'selenium-webdriver'

Before do
	@driver = Selenium::WebDriver.for :firefox
	@driver.manage.timeouts.implicit_wait = 30
	@driver.manage.timeouts.script_timeout = 30
	@driver.manage.timeouts.page_load = 30
end

After do
	@driver.quit
end
</pre></code>

![alt text](https://raw.githubusercontent.com/hy1984427/BDD-with-PageObject/master/images/EditEnvRB.png "Edit env.rb")
