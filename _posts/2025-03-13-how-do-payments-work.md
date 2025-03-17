---
layout: post
title: How do payments work?
description: Let's look into how payments work and how fintechs make money
date: 2025-03-13 15:01:35 +0300
image: '/images/stripe.svg'
image_caption: 'Lets look at how fintech and payments work [wikimedia.org](https://upload.wikimedia.org/wikipedia/commons/b/ba/Stripe_Logo%2C_revised_2016.svg)'
tags: [Fintech]
---

Most of the ideas for this post came from an excellent book by Ahmed Siddiqui that I recently read called "Anatomy of a Swipe". 
This book goes into the details of modern financial transaction processing from his experience of building [Marqeta](https://www.marqeta.com/).

## Overview

A basic 1000-foot view of the space can be broken out into a few key roles that are filled to various extent by various players:
- Merchant - the kosher food truck you are buying your take from
- POS device - square, toast, merchant one, card readers that allow you to process your transaction. 
- Acquirer / Issuer processor - payment processor, which may or may not be tied into the POS device maker
- Acquiring / Issueing bank - banks of merchant (acquiring) and customer (issueing) banks
- Card network - visa, discover, mastercard etc. These are the networks that connect various banks

Here is a brief overview of the flow:

![card processing flow](/images/card_processing.jpeg)

### Card processing steps
Once a person inserts or taps their card on the reader, they go through the initial authorization step. This goes to the acquirer processor.

Card that start with a 5 are a mastercard card. Card that start with a 4 is a Visa.

There is a few things that happen during authorization:
1. Does this person (still) have an account with the issuing bank?
2. Is this person's card (still) active?
3. Does this person have enough money to complete the transaction?
4. Is this person allowed to shop at this kind of merchant (in case of corporate card)
5. Does the transaction look fraudulent?

The above information eventually gets to an issuer processor (Fiserv or Adyen), and that processor might pass it on to the issuer bank (or fintech in front of the bank).

The fintech will run its own fraud analysis on the transaction:
1. Has the fintech seen other fraud from this merchant?
2. Does this transaction make sense based on what they know about the customer?
3. Is this a physical card (card present) transaction or not? Card not present transactions are usually much riskier.
   1. This is usually where you see a [3d secure](https://docs.stripe.com/payments/3d-secure) auth via a little popup like the one below.
   ![3d secure](/images/3d_secure.png)
4. Ahead of time analysis via vendors like stripe etc, that will analyze user behavior on the site (how their mouse moves
   etc to see if this is a legitimate transaction or not).

If all of the above checks out, the approval message is sent back through the chain to the terminal. And all of these checks need to happen within 3 seconds or so
while the authorization screen is spinning.

Merchant processor and card network each take a percentage of the transaction, this is called `interchange`, the rest of the money goes to the food truck.

The acquirer (food truck's bank) usually charges a flat monthly fee for their services. This fee can change depending on the volume of transactions
the merchant has.

![debit card fees](/images//debit_card_fees.png)

### Regulation
Durbin amendment caps the debit card interchange fees for large banks with over 10 Billion in assets. This rule does not currently apply to credit cards.

Smaller unregulated banks like `Evolve Bank and Trust` are able to charge higher interchange for debit cards, and therefore offer debit card rewards.

FDIC only insures the underlying banks, not the neobank sitting in front of it. So, if Neobank fails and it does not have a banking license, its assets
are not insured by FDIC.



## Varo, Sofi, Chime Model
These neobanks usually sit in front of something like `Evolve`, thogh Varo and SoFi now have their own banking charter.  They are called
`program managers` in the fintech terminology. They market the financial products to their customers, and service them (collections, payments, hardship relief etc).

The key here is what happens when one of these neorbanks go belly up. Since the underlying bank has not failed you might not qualify for FDIC insurance. 
Read more about this [here](https://www.nerdwallet.com/article/banking/what-happens-if-neobank-fails).

These neobanks make money via the interchange for cards that they offer. The also often times are able to offer your paycheck a few days early due to a quick
of ACH. The ACH transaction has to go in 2-3 days before the payroll date, as it takes about that long to clear in ACH. However if you are paid via direct
deposit the chances of that ACH from your employed not coming in (due to insufficient funds or fraud) is really low, so these companies are able to front
you the funds with very little risk.

The underwiring bank gets to get more customer deposits, which they are able to lend out and make interest on and not share it with the neobanks.  They also
don't have to service the underlying cards.  They do however take on 2 types of risk:
1. Chargebacks (if too much fraud happens the bank usually does not fight it and eats the losses)
2. Various outages and complaints from neobank customers sometimes reflect poorly on the reputation of the underlying bank
3. They carry most of the regulatory risk of the products offered, and have to do a lot of due dilligence with the program managers.

## Visa, Mastercard vs Discover Model
Visa and Marstercard are open networks. This means that various issuers can use their network to issue their cards. You might have a card from Barclays bank
which uses mastercard as their rails. This means that when you make a purchase both Barclays and Mastercard get a cut of the transaction. Card networks 
get to charge lower fees, but at the same time do not have to worry about servicing, collections, debt sales, hardship relief etc on the cards themselves.

Discover is both a credit card issuer and a credit card network. This means that discover is something akin to the `program manager` in that they market
their credit card products directly to consumers, and service them. But they also operate their own credit card network (credit card rails), which
means that they do not pay extra fees to via or master card and get to keep more of the interchange fee.  On the flip side, they have a lot less volume
which means that visa and mastercard are able to collect more revenue overall due to higher volume.

Most card issuers and `program managers` deal with only one credit card network (they pick visa or master card). An interesting excepton to this is 
capital one, which actually uses both and varies them depending on the card in question. Likely by using both they get to take on a bit more complexity,
but get to play the two networks against each other to get lower fees.

One of the ways these card networks compete is various benefits they give for free (roadside assitance, lost baggage insurance etc).

Below is a chart of card processor acceptance:
![processor acceptance](/images/merchant_acceptance.webp)

[source](https://www.lendingtree.com/credit-cards/study/credit-cards-most-accepted-worldwide/)

Below is a chart of processor benefits:

![discover vs visa](/images/discover_vs_visa.png)
[source](https://www.lendingtree.com/credit-cards/articles/discover-vs-visa/#:~:text=Discover%20is%20both%20a%20credit,merchants%20and%20credit%20card%20issuers.)

Below is a chart of interchange fees per network:
![interchange fees](/images/interchange_fees.png)
[Source](https://www.valuepenguin.com/credit-card-processing/interchange-fees#:~:text=Interchange%20fees%20vary%20by%20credit,from%201.15%25%20to%203.25%25.)

If you want to dig deeper into debit card interchange fees, there is an excellent breakdown on the federal serve site [here](https://www.federalreserve.gov/paymentsystems/regii-average-interchange-fee.htm).

## Stripe / Square / Toast Model
Stripe charges a flat 2.9% fee per transaction plus 30 cents. As you can see from the chart above, depending on circumstances Stripe might actually
take a loss on processing the transaction through the credit card network.  

There are however additional services that stripe provides for which it does not have to pay a third party:
* Billing - to invoice customers
* Connect - business to business version of invoicing the customers
* Radar - anti fraud system which seeks to weed out bad transactions
* Sigma - data storage system

Stripe is bigger player in the game and is able to negotiate lower interchange fees than most small merchants that are on the platform. This then sets up 
a win win for them and their customers. However they are on the hook for chargeback fees.  To this end stripe has the ability to shut down bad actors
(if they have high chargeback rates or high fraud rates). 

Stripe can also charge their own currency conversion fees, and has the ability to take some money from the top for allowing these services to merchants. 
Again the merchants might have to set that up themselves for an even higher markup, so this sets up a win win for stripe as well.

## Basis theory model
In order to ensure PCI DSS compliance one must have adequate security for their payment method storage information. This is not easy, and payment service
providers like stripe provide this service for you. Essentially they tokenize the credit card details, and only send the card token to the merchant. 

However, if you want to keep credit card data yourself, and not be tied into a merchant provider for it, you can use someone like basis theory, which
is basically a card tokenizer service for a small transaction fee. This is called payment vaulting. Read more about payment vaulting on the basis theory [website](https://blog.basistheory.com/vaulting-payments-cost).

## Plaid Model
Plaid connects user's bank accounts to fintech applications. For the fintech customers plaid simplifies connecting a bank account (they just log into their bank account
via plaid interface, and its connected). 

For the fintech however, it gives a lot more than that:
* On the auth side it gives you a lot of confidence that the user is who they say they are (authentication and KYC)
* A stream of user transactions for connected account (in case of bank account information on customer transactions outside the fintech).
  * This is good for both personal finance management apps (mint) and overall analysis of user behavior (if that is an approved use case legaly).
* Checking bank account balance before initiating an ACH payment from that bank account
  * There is a returned payment fee that gets assessed when ACH payment does not complete, as long as the cost of plaid call is less than that fee, its a win

You can read more about plaid business model on their [blog](https://plaid.com/resources/fintech/how-does-fintech-and-plaid-make-money/).


## Marqueta / Branch model
Charge transaction fees on card transactions made by their customers. So for example, if you are uber eats or door dash, and you want to allow your contractors
to be able to shop for products ordered by your customers, you don't want the contractors to initially buy them with their own money. First of all they might not
have enough, but also you don't want to miss out on the points that can be earned while doing so.

Marquetta allows you to issue specialy cards, that adapt on the fly in terms of what amount can be spent and in what store. Directly alining with the needs of 
the uber eats/ door dash worker. This way the company gets to keep full control over spend, not force the contractor to spend their own money upfront, and gets
various forms of analytics on those types of payments.

Marquetta then earns money on the interchange fees (part of that 1-3% charged for every credit card transaction). This interchange fee needs to be split with the
card network and issuing bank.  

It used to only offer debit cards which earn a lower interchange. To avoid the caps, it only worked with small banks (as described above) to be able to
earn higher fees.

It has recently added credit cards to it's apis, allowing it to earn higher interchange fees.

Here is an approximation of revenue splits:

![revenue splits](/images/marquetta_interchange_rate.png)
[Source](https://lumosbusiness.com/finance-marqeta-ipo/#:~:text=Marqeta%20earns%20the%20majority%20of,usage-based%20pricing%20model).)

## Credit Karma Model
While not stricly a payment processor, Credit Karma does play in the space with the checking account product.  Since they are not a bank, they have a 
banking partner which holds on to the deposits (and they play a similar role as chime). 

However, CK's main business model is referral fees from the credit card and personal loan marketplaces.  If a person adds direct deposit to their CK account
and uses their CK account as their primary account for personal loans for example, CK is able to funnel the money super efficiently by either routing their
loan directly into their CK bank account much faster, or if they are paying down their credit card debt they would be able to send a portion of the money
to relevant cards, and only deposit a portion into the user's bank account. 

Adding direct deposit gives you more benefits for the following reasons:
1. Safer for the bank, they know you are a real person with a real income. So there is way less likelyhood of costly fraud.
2. They are assured that there will always be at least some money on the account on which they can earn some interest.

The checking account is also used for their tax return product, where if they know that you will deposit your refund into your CK bank account, they can be
pretty sure that the money will be there to pay off loan balance etc, which also gives them some amount of business advantage.

They also allow you to receive your government funding earlier as well, like social security benefits, VA benefits, SSI etc via this bank account.

By providing a savings account, credit karma is able to make the difference between the APY they pay you, and what they earn themselves.

This gives CK some flexibility in being able to collect some interest on their deposits (which they will then share with the banking partner).

## Sources
* https://medium.com/wharton-fintech/the-anatomy-of-the-swipe-81517965df29
* https://infostride.com/stripe-business-and-revenue-models/
* https://businessmodelanalyst.com/stripe-business-model/?srsltid=AfmBOopBb1FL0ZuVbx_up3wfLyGM2QzOsgRSbCzulhJOU99fqf55A_18
