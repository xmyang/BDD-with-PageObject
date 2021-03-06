# Add tags to different scenarios to run them separately

To run the original buying book and the data driven scenario separately, we need to add tags to them:

<pre><code>Feature:
In order to purchase it later
As a consumer
I want to add a book to my shopping cart

@single
Scenario: Consumer can add a book to shopping cart
	Given I open "http://www.amazon.com"
	When I search for "The Lean Startup"
	And I open the first book
	And I add the first book to shopping cart
	Then I should see the book in my shopping cart

@multiple
Scenario Outline: Consumer can add a book to shopping cart
    Given I open "http://www.amazon.com/"
    When I search for "<book>"
    And I open the first book
	And I add the first book to shopping cart
	Then I should see the book in my shopping cart
	Examples:
	| book             |
	| The Lean Startup |
	| Steve Jobs       |
</pre></code>

![alt text](https://raw.githubusercontent.com/hy1984427/BDD-with-PageObject/master/images/BuyBookFeatureFileWithTags.png "Add tags to scenarios in buy_book.feature")
