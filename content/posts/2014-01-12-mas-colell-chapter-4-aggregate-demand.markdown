---
author: brian@briancalbrecht.com
comments: true
date: 2014-01-12 19:58:40+00:00
layout: post
link: http://www.econpointofview.com/2014/01/mas-colell-chapter-4-aggregate-demand/
slug: mas-colell-chapter-4-aggregate-demand
title: 'Mas-Colell Chapter 4: Aggregate Demand'
wordpress_id: 639
categories:
- Books
- Economics
- Grad School
tags:
- Aggregate demand
- Demand curve
- Mas-Colell
- MWG
- Weak Axiom
---

![](http://sophosnews.files.wordpress.com/2013/02/angrymob.jpg%3Fw%3D640)

After developing [classical demand](http://econpointofview.com/2013/10/30/mas-colell-chapter-3-classical-demand-theory-part-2/) theory for individuals, it is natural to try to extend this to many consumers. MWG address three possible questions and solutions, which he calls _the econometrician, the positive theorist, _and _the welfare theorist._


## The Econometrician




<blockquote>"The econometrician is interested in the degree to which he can impose a simple structure on aggregate demand functions." (pg 105)</blockquote>


The econometrician has some aggregate data on different variables. He is looking for a simple way to analyze it and knows his classical demand theory. Is there a simple way for him to combine these two ideas?

The first and obvious way to look at aggregate demand requires a simple summation of individual demand. Each consumer has a (Walrasian) demand function, which depends on prices and his wealth. Adding them together results will result in an aggregate demand function for each good in the economy-

<!-- more -->


x(p,w1,....,wN)= ∑xi(p,wi)


Unfortunately, it still depends on **each** individual's wealth. This has not helped.

However, the econometrician does have information on W, the overall wealth. When will the demand for each good, x, only depend on prices and overall wealth? Or, put another way, when will two separate distributions of a certain wealth result in the same aggregate demand function?

This will only happen under very specific situations. We need a demand function when a small decrease in the wealth of one consumer will cause him to eat less apples. With W held constant, that means that someone else has an increase in his wealth. That consumer must increase his consumption of apples **exactly** as much as the first consumer decreased. That means the overall demand only depends on the total wealth. This is pretty unlikely.

The reason for this difficult is that we have asked a lot of the theory. We have said that **any** distribution of wealth must have the same demand, whether egalitarian or dictatorial. Surely, in the real world, **any **distribution is not necessarily possible. What if we restrict the possible distributions and only deal with a smaller set?

It turns out that if some distributional rule determines individual wealth, then we can aggregate. For example, if the government plays some role is redistributing wealth, each individual's wealth depends on the total wealth, or wi(p,W). Now, our simple summation works-


x(p,W)= ∑xi(p,wi(p,W)) or




x(p,W)= ∑xi(p,W)




Aggregate demand only depends on the prices of goods and W. This looks just like chapter three consumer theory. The econometrician can construct a model with demand based on prices and W and find parameters. Yay! for the econometrician.





## The Positive Theorist




<blockquote>"The positive (behavioral) theorist, on the other hand, is interested in the degree to which the positive restrictions of individual demand theory apply in the aggregate. This can be significant for deriving predictions..." (pg 106)</blockquote>


The positive theorist wants to know whether properties of individual demand hold for the aggregate. Specifially, when does our new fancy aggregate demand satisfy the [weak axiom](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&sqi=2&ved=0CC8QygQwAA&url=http%3A%2F%2Fen.wikipedia.org%2Fwiki%2FRevealed_preference%23The_Weak_Axiom_of_Revealed_Preference_.28WARP.29&ei=QqvSUrTPBNP3ygP5-4DgCw&usg=AFQjCNGa848C6F5j-_2hs-5voU5ne4OTPg&bvm=bv.59026428,d.d2k) of revealed preferences (WA)? The WA is almost the cornerstone of [MWG's consumer theory](http://econpointofview.com/2013/09/24/mas-colell-chapter-1-preference-and-choice/#more-169), because it turns logical preferences into a coherent utility function.

Unfortunately, aggregations do not necessarily satisfy the WA. In fact, MWG shows that a simple aggregation of two demand functions does not satisfy the WA. Preferences satisfy the WA if and only if they also follow the law of demand for _compensated price changes_.

**Reminder:** The compensated law of demand says if two bundles, X and Y, are affordable and I always chose Y, I prefer Y. Therefore, given any set of prices and wealth where I chose X, Y must not have been affordable. Otherwise, I would have picked it. The formal version [seems different](http://www.econ.brown.edu/~rvohra/econ205/warp.pdf).

However, the WA is satisfied for an aggregate if every consumer's demand function satisfies an _uncompensated__ law of demand_. If the price of a good goes up, all consumers must consume equal or less, even without a wealth compensation. This is reasonable. It is the way people typically talk about the law of demand. Yet, it is not derived from utility maximization. It needs to be imposed here for aggregation purposes.

With the uncompensated law of demand imposed on all consumers, the aggregated demand function now satisfies the WA.


#### Positive Representative Consumer


MWG defines a positive representative consumer . This "consumer" can be thought of as solving the maximization problem for the total budget set. This is the aggregate demand function.

However, to really solve this problem and draw the welfare implications (which economists love) for the economy, the economist needs to construct a utility function for the representative consumer. Up until now, there have only been budgets and demand functions without any mention of welfare. Now, MWG wants to move into a different territory.


## The Welfare Theorist




<blockquote>"The welfare theorist is interest in the normative implications of aggregate demand. He wants to use the measures of welfare change derived... to evaluate the welfare significance of changes..." (pg 106)</blockquote>


To discuss social welfare, MWG defines a social welfare function. This is someway to aggregate utilities; the result is whatever we call social welfare. It is simply a definition. A few simple examples are the [utilitarian and the Rawlsian welfare functions](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&ved=0CC8QygQwAA&url=http%3A%2F%2Fen.wikipedia.org%2Fwiki%2FSocial_welfare_function%23Cardinal_social_welfare_functions&ei=4ujSUpeiKOXu0gX154CwBA&usg=AFQjCNGAarW9yUUj5tMWW-UhebCVz1ElOw&bvm=bv.59026428,d.d2k). The former is a simple addition of the utilities. The latter takes the lowest utility as the social utility. Therefore, if the representative agent's maximization problem maximizes the social welfare function, however defined, then the agent is a _normative consumer._ The agent is an aggregation of all utilities.

Now the economist can make welfare interpretations. Usually this takes the form of asking whether the "distribution" of wealth maximizes the social welfare function.


## Conclusion


One of the first things every microeconomics textbook or class starts off saying is that the value of a utility function is meaningless. We, economists, construct utility functions so that they are easier. This simplification hopefully allows for better predictions. That is the trade-off. The theory is more removed from real human decisions than an ordinal ranking or a preference relation, but these other two methods are practically difficult.

Chapter four extends this idea to the aggregate. MWG is finding when an aggregation is a meaningful representation of multiple people. The representative agent or aggregate demand function are not real things. They are tools for thinking and if they help in making predictions they _might_ be worth the cost.

Up to third section, MWG has kept everything fairly uncontroversial. They are constructing a predictive theory and looking for better estimates. However, again, their method has run short and they want to reach welfare. To do that, they need to stretch, exposing some holes, and make bold claims.

They take a shortcut with the utility function. They disconnect their theory from its foundations. However, they seem [forget this shortcut](http://econpointofview.com/2014/01/02/well-put-my-friend-13/) when trying to draw normative implications. As I have written before, this is one of the troubles with forgetting the purpose of specific models, just as people can draw the wrong implications from praxeology.
