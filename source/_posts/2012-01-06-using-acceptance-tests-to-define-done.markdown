---
layout: post
title: "Using Acceptance Tests To Define Done"
date: 2012-01-06 14:50
comments: true
categories: [Acceptance Critera, ATDD, Agile Testing]
---
(This post was originally posted on [Jim Holmes'](https://twitter.com/ajimholmes) ["31 Days of Testing"](http://frazzleddad.blogspot.com/2011/12/31-days-of-testing-kickoff.html) blog series,
but I thought it served some value here as well.)

Have you ever been on a team and was asked “What is the definition of done?” You respond by saying,
“When all of your automated tests pass, and there are no bugs, then you have satisfied the acceptance
criteria. Done!” Which then is responded to by “Well, how do I define the acceptance criteria?” Good question!

<!-- More -->
### Understanding the Feature

First things first – you have to understand what feature you’ll be building. Building the right product
and building the product right takes communication and collaboration between your product owner and your team.

The reason for all of the collaboration is that we’re trying to build a shared understanding of what needs
to be done and also produce examples that are easy to maintain. There are many ways to work collaboratively
and ultimately, you have to decide what works best for your team.

The team I’m currently on has found that smaller workshops work best for us. Those workshops, otherwise
known as “Three Amigos”, include a business analyst, a developer and a tester who share a similar understanding of the domain.

Lets hypothetically say you’re discussing a shopping cart feature for your site. Start by defining the goals
of this feature. By starting with the goal, you’ll let everyone know why they’re spending their time
on implementing the feature. If you can’t come up with a good reason why, then maybe the product owner is wasting everyone’s time.

We’ve used the Feature Injection template from Chris Matts and Liz Keogh to help us successfully describe why: <br/>
**As a** &lt;type of stakeholder&gt;<br/>
**I want** &lt;a feature&gt;<br/>
**So that** &lt;I can meet some goal&gt;<br/>

Here’s our feature description:<br/>
As an online shopper<br/>
I want to add items to my shopping cart<br/>
So that I can purchase them<br/>

### Determining Acceptance Criteria

Next, your team needs to determine what the system needs to do to meet those goals-the Acceptance Criteria.

In your Three Amigos meeting, be sure to ask questions to clear up assumptions, such as “Are there any
products that cannot be purchased online?” or “Does the shopper need to be authenticated to purchase?”.

Remember, the scope of feature should be high level as we only want to identify what the application needs
to do and not how it’s implemented. Leave that part to the people that know how to design software. It was
determined by the team that the following are in scope:

  - Only authenticated shoppers can add items to the shopping cart.
  - Cannot add refrigerators to shopping cart.
  - Only 25 items can be added.
  - Shopper can remove items from shopping cart.
  - Shopper can change quantity of items after adding it to the cart.

Hey, now we have some acceptance criteria!

### Acceptance Criteria lead to Acceptance Tests

We’ve used communication and collaboration to determine why a feature is necessary and what the system needs
to do to at a high level, so now we can come up with some examples to test our acceptance criteria.

To do this, we’ll write some Cucumber scenarios. We’ve chosen Cucumber for all of the reasons mentioned
in [Tim Wingfield’s post on Day 15](http://frazzleddad.blogspot.com/2011/12/31-days-of-testingday-15-cucumber-is.html).
If you haven’t read it, go back and check it out. It’s an excellent post on the benefits of employing Cucumber.

Here are a few scenarios that were created:
```text
Given the shopper is a guest
When they try to add an item to their shopping cart
Then they will receive the error "Only authenticated shoppers can add items to their shopping cart."
```

```
Given an authenticated shopper
When they click the "Add Item to Cart" button
Then they will have an item in their shopping cart
```

```
Given an authenticated shopper with an item in their shopping cart
When they click the "Remove Item" button
Then that item is no longer in their shopping cart
```

These are only a few of the examples that were developed as part of the Three Amigos meeting.
On our team, the output of the Three Amigos is a Cucumber feature file. We now have a shared understanding
and a definition of done! We can pass on our failing acceptance tests to the Dev team to begin their work. They
will begin by creating failing unit tests and writing enough code to make them pass. Once they are passing, they
can then run the acceptance tests. Once those are passing then the feature is complete. We’re done! Those acceptance
tests will be added to the regression suite to be ran anytime to ensure that the feature remains done. Now the feature
can be demonstrated to the product owner at the next review.

What we’ve just done is taken a trip around the Acceptance Test Driven Development cycle. Just remember,
it’s not about the tools or the technology, but rather the communication and collaboration. Our ultimate goal
is to deliver high quality software that functions as the product owner intended. By including QA in the entire process,
we can eliminate many of the problems that plague us earlier so that they don’t make it to production. Quality
is not just a QA function, it’s a team function.
