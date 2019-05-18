---
title: Rethinking referral codes
description: Or, 🍕💯🚀
date: 2016-06-07
permalink: /2016/rethinking-referral-codes
---

Our heads are filled with memorized sequences of letters and numbers. Passwords, social security numbers, anniversaries, phone numbers, Twitter handles… Some of those are important; others, not so much.

Do you know what comes dead last on that list though? Referral codes.

Whether you know it or not, you probably have in excess of a dozen referral codes spread across the services you use. How many of them do you actually remember? One, maybe two?

The fact of the matter is that referral codes are boring and hard to remember. That's problematic since it means there's a lot of extra friction to referring your friends to services you like. That's not only annoying for you, it's also bad for the company; it's a lose, lose.

When it came time to build a referral program for [Penny](https://www.pennyapp.io/), we decided to re-think things a bit.

First, the problem:

> Most people don't remember their referral codes for most services.

Next, the solution:

> Emoji.

Problem solved 😉

Okay, obviously there's a lot more to it than that. Before we get to our solution, let's take a look at some existing solutions to this problem.

#### First or Last Name + Next Available Number - `MITCH974264`

<span class="grid">
  <span class="grid-item">
    ![A screenshot of Lyft's referral code](/assets/images/lyft-referral-code.png)
  </span>
  <span class="grid-item">
    ![A screenshot of Sprig's referral code](/assets/images/sprig-referral-code.png)
  </span>
</span>
<span class="subtitle">Lyft and Sprig: great services, but those codes are 😖</span>

This is among the most common type of "friendly" referral code. It's more memorable than a random code, but if your name is "Alex" and you're on a popular service where there are tens of thousands of other Alex's, you're out of luck. Even if your name is not all that common, remembering more than a couple random digits is tricky, especially if you have other codes with a similar format but different numbers.

This method also doesn't work well for short or hard to type names like JJ or 妀. On the malicious front, you leave yourself open to internet trolls that set their first name to swear words because that's what trolls do. I doubt most companies want people promoting referral codes with profanity in them.

#### First _and_ Last Name + Next Available Number - `MITCHELLLEE14`

By using the person's first and last name, you greatly cut down on the number of collisions. Unfortunately, full names can be long and tricky to spell, making the referral code entry process tedious and prone to errors. That's further complicated if you only use the first `N` characters of the name.

The same logic applies to using part of the email address in the code, with the added downside of leaking the person's email address. Probably not the best idea.

#### Unique Word Combinations - `CAT LOCK TREE`

Now we're starting to get creative. This takes a page out of a [popular XKCD comic](https://xkcd.com/936/). It turns out that a few random words are often easier to remember than alphanumeric strings because our mind has an incredible ability to make stories out of them. "The cat found a lock while climbing a tree." Done.

Sadly, this method suffers from two drawbacks. First, it can get lengthy. That's problematic both for the person entering in the referral code, and for the presentation of the code to the user (i.e. it takes up a lot of screen and/or URL space). Second, you need to be very careful selecting your random word list lest you accidentally generate a culturally distasteful series of words. During our experimentation, we ran into a lot of issues with that.

#### Random - `QFJXKO`

Here's my actual Uber referral code. I mean, because who actually cares about the customer experience?

<span class="center">
![A screenshot of Uber's referral code](/assets/images/uber-referral-code.png)
</span>
<span class="subtitle">Is that a 0 or an O? 😑</span>

To be fair, some of these companies expect you to exclusively copy and paste the code; others encourage you to share links that your friends need to follow to sign up. Suffice it to say that those are neither foolproof nor mutually exclusive approaches. You can rely on both of those techniques while also having something that's pleasant on the eyes and conducive to all varieties of sharing.

We went back and forth for arguably way too long on the relative merits of each system. Then this happened:

<span class="center">
  ![A Slack message about emoji referral codes](/assets/images/slack-message.png)
</span>
<span class="subtitle">The _aha_ moment.</span>

Now before you get all judgey judgey and make assumptions about my mental health, hear me out.

The key requirement of a referral code is that it's unique. Having unique referral codes mean you need a lot of entropy (i.e. a lot of possible combinations). All of the examples above make use of a limited character set — in most case: 26 characters and 10 digits. That means that to get lots of possible combinations, you need a lot of characters.

Let's look at an illustrative example: say that after removing visually similar characters like l, I and 1, you're left with 30 characters (that assumes case insensitivity, which you should do unless you enjoy causing your users great frustration). Even if you use a completely random code, you'd need at least six or seven characters to get to a reasonable level of entropy (30^6 ≈ 729 million). If you incorporate names, which overlap significantly more than random characters, you need way more characters to get there.

In contrast:

> In total there are 2823 emojis in the Unicode Standard.  -  [Emojipedia](http://emojipedia.org/faq/)

If you string together three emoji, you'll end up with over 22 _billion_ possible codes. If you bump that to four, you'll be over 63 _trillion_.

Clearly, we don't want to make use of all 2823 emoji. For one, there are a lot of visually similar emoji. Exhibit A: 😁 and 😬. But even if we curate a list of 100 easily recognizable, commonly used emoji, that's way better than our set of 30 alphanumeric characters — we get to our desired level of entropy much, much faster.

Moreover, there are a lot of other benefits:

*   They're ubiquitous. Emoji usage is growing at an amazingly (frighteningly?) fast pace. [Just ask Instagram](https://instagram-engineering.com/emojineering-part-1-machine-learning-for-emoji-trendsmachine-learning-for-emoji-trends-7f5f9cb979ad).
*   They're universal. Everyone speaks emoji, so internationalization is not an issue.
*   They're short. You'll never need more than four emoji to get the entropy you need.
*   They're memorable. The image of the emoji `🚀` is reinforced by both the word for the emoji `rocket` and the emotion it invokes: speed, excitement, future.
*   They're fun. When is the last time you got excited about your referral code?

The icing on the cake? Emoji fit perfectly with our brand.

<span class="center">
  ![A screenshot of a Penny emoji referral code](/assets/images/penny-referral-code.png)
</span>
<span class="subtitle">#shipit</span>

As always, [feedback is welcome](https://mitchjlee.com).
