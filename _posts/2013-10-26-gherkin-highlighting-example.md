---
layout: post
title: "Gherkin syntax highlighting example"
description: ""
category: ""
tags: []
---
{% include JB/setup %}


<pre><code class="language-gherkin">
Story: Returns go to stock

# some comments
In order to keep track of stock
As a store owner
I want to add items back to stock when they're returned # comments

	  #comments

Scenario Outline: Refunded items should be 'returned to stock'
Given a customer previously bought a black sweater from me
And I currently have three black sweaters left in stock
When he returns the sweater for a refund
Then I should have four black sweaters in stock

Scenario 2: Replaced items should be returned to stock
Given that a customer buys a blue garment
And I have two blue garments in stock
And three black garments in stock.
When he returns the garment for a replacement in black,
Then I should have three blue garments in stock
And two black garments in stock
</code></pre>