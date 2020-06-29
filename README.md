# Stock-Trading-using-Reinforcment-Learning

<b>Problem Statement</b>
<br/>
Creating a reinforcement learning training by usually when people think about applying machine learning
to the stock market they usually think about it in terms of predicting the value of a stock which includes
even just the direction like whether it will go up tomorrow or down tomorrow.
Of course that information by itself doesn't do anything physically.
You still need to sit down at your computer and make a trade.
If we're talking about automated high frequency trading then that's a different story.
Even so let's say your model predicts that the stocks you are looking at will go up tomorrow.
Does that mean you'll make a trade.
Maybe.
But what if you're busy and you forget.
Or what if you believe it's going to go up only slightly and then decrease rapidly then probably you
don't want to buy that stock.
This is the key difference between a traditional supervised and unsupervised learning versus reinforcement
learning supervised learning only makes a prediction.
It doesn't actually take any action based on that prediction.
I can predict tomorrow's stock price but I still have to choose whether I will act on that information
or not.
Reinforcement learning on the other hand not only makes predictions but also takes actions in the environment
that you provide.
So in this section of the chorus we are going to study how a reinforcement learning algorithm might
take such actions in a stock trading environment
let's just go over a rough outline of how this is going to work.

Currently you probably just think of stock prices as a simple time series data set at this time it has
this value at the next time it has this other value and so on.
That sounds more appropriate for a recurrent neural network rather than reinforcement learning.
So what makes this a reinforcement learning problem.
Well it's a matter of perspective.
Imagine let's say you're hooked up to a stock trading API using this API you can call functions which
do real world financial transactions.
So if I call the BI function person the argument gee oh gee and 10 that means I'm going to buy 10 shares
of Google stock.
If each share is worth fifty dollars that means five hundred dollars is going to be deducted from my
bank account and instead I will now own it 10 shares of Google
let's say I call the cell function and I pass in the argument AAPL with the number five.
That means I just sold five shares of Apple stock.
If one share of Apple is worth thirty dollars then I will now receive one hundred fifty dollars in my
bank account and I will own five less shares of Apple stock than I did before.
Importantly you can see that the act of calling these functions is an action you might think of your
state as information such as recent stock prices.
How much cash you have to buy my stocks.
How many shares of each stock you own the values of those stocks and so on.
The environment is the actual stock market.
It's inherently random because you can't really predict what's going to happen to tomorrow's stock price
but your actions affect the environment.
In other words these are all the ingredients we need to specify our problem as a reinforcement learning
problem.
We can perform actions such as buy and sell in the environment and our state is made up of information
about various stocks in our own portfolio and the environment is the stock market itself.
The reward is some function of the money we made or lost
something useful to try.
Which is probably something many of you have done already is to think about how you yourself are a reinforcement
learning agent.
When you are looking at a stock and trying to decide whether or not to purchase some shares you generally
want to follow the rule buy low sell high.
So for example here we can see a dip in value.
This would be a really good time to buy.
And here we see a peak.
This would be a really good time to sell well.
Only if you need the money.
Hopefully you are investing in something where the general trend is always going up.
So if you don't need the money then the best thing to do is just let it sit and continue to increase
in value.
Of course the problem is that in the real world you are trying to make these decisions without knowledge of the future.
How do you know if the most recent price is a dip or a peak.
In fact we do not.
And so perhaps this is a job best left for the machines.

<b>Model Details</b>
This model uses the stock prices data of the three companies motorola, apple, Starbucks.
And trade over them by predicting the future stcok prices.
This will take the the data store in the csv file and try to predict the upcoming prices of the stock and based uplon the prices it will take the actions i.e. to sell the stock or purchase the stock.

<b>Running the Project</b><br/>
To install dependancies
<br/>
pip install requirnment.txt

To train the model
<br/>
python rl_traders.py -m train

To test the model
<br/>
python rl_traders.py -m test

To see the graphical represantation of the rewards we wil be getting after trading
<br/>
python plot_rl_rewards.py
