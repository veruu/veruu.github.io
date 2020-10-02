---
title: "Finding bugs and improving team culture by using emojis as release names 👀"
slug: "release-emojis"
date: "2020-10-02"
---


Our team uses emojis everywhere. I don't remember how it started but we eventually became known for
pushing the boundaries and [including emojis in emails to kernel developers]. One of the activities
we really enjoy is naming our releases in JIRA with fitting emojis. Some people recently expressed their
opinions that we [shouldn't be doing it], and it got me thinking. But not thinking about why they are
right, the opposite. Thinking about the deeper reasons why *you* should do the same and start using
emojis in places that are not private chat messages.


## Finding bugs 🐞

There's plenty of programs that don't handle unicode well. Some of the more famous bugs are crashing
[smartphones] but problems with [databases] and [related tooling] are also very common. These issues
can cause security problems such as [information leaks] or [denials of service]. This may not sound
like a big deal if the program in question is your pet project but the moment you include users or a
public facing interface... [people can input anything] so you better handle it well.

By using unicode characters you can expose these bugs. Hopefully to report them and get them fixed.
If not, you can at least detect those [more than 10 years old MySQL deployments] and avoid them.


## Including others 🤗

The vast majority of world is not using pure ASCII. There are not only extensions to this set but
also completely different alphabets. By making sure the tool handles unicode well you're including
all those people by doing something that sounds trivial but is not -- being able to *show their names*.

None of the foreign financial/tax/bank websites I used so far could handle my name. And it only
contains one character that's in the extended ASCII set. It's not even unicode! I got it all. Sites
complaining about "illegal characters" in the input (excuse me? how rude!). Sites quietly exchanging
the affected letter for the famous empty square (□). Sites not allowing you to continue without telling
you what the issue is. The kicker? Because of the seriousness of the topic all of the sites had big
disclaimers about how you have to type your **legal name as it's shown on your ID card** or you'll
face legal repercussions, yet none of them allowed you to actually do so! Let's not even get into the
question of when some of those applications will finally find out Czechoslovakia hasn't existed for
decades... As a bonus, so you don't think it's only English-centric sites, one of my coworkers got
□ printed on his ID card by his own government!

Of course this is not only about names but any other input as well. Similarly to names, addresses are
a common problem. Or imagine a small company in a non-English speaking country with local customers,
why should they be forced to misspell their product or release names? If you are a product owner,
fixing language issues can also get you more customers from markets you'd have missed otherwise!

But let's back to the names for a bit longer. There's even [a list of falsehoods programmers believe about names]!
People are making [talks at well-known conferences about it]! This topic is not entertaining, it's
***dehumanizing.*** If pushing for emojis means people will eventually be able to use their names
properly, I'm taking the chance. I gave up years ago and use the ASCII version of my name by default
but I shouldn't have to do that and neither should others.

*Plenty of places preach inclusion. How many of them have deployments that don't even let all of
their employees use their names because it's "too much work"?* ***Force them to be better***.


## Sense of belonging and productivity 🥰

Picking emojis is a seemingly lightweight activity which gives people a little bit of mental break.
Emojis are also considered fun and childish (insert another "old man yells at cloud" meme here) which
enforces the statement even more.

The emojis are not chosen randomly but as a reflection on what happened since the last release.
This forces people to think about the achievements and struggles of the whole team and not only
themselves. It's almost like a small per-sprint retrospective but for free without an actual
retrospective! It makes you more aware about the experience of other team members, potentially also
giving you ideas about what you can help with or what needs to be solved in the near future (again
for free without the extra meeting!). For example, most of the team members were dealing with the
fallout of broken infrastructure? "🔥🚒" is a good release name candidate. We all did a lot of cleanup
tasks and participated in Linux Plumbers conference? Everyone wanted a bathroom-related emoji and
thus we ended up with a combination of "🔧🚽🛁🚿". Try to find a scheme that reflects on team events
and experiences!

Doing something together that's far from the actual workload makes teams happier, closer and more
productive. Why? Because it shows the humans and their personalities and by getting to know people
better you also respect them more and trust them more. That means people are more inclined to
voice their ideas and concerns - and other team members respect the feedback more - and *that* makes
the product better!


## Quick notes on accessibility 🦯

Unicode characters can break screen readers or make reading the characters very annoying. There's
a good example of how the special characters looking like formatted text sound [on Twitter]. If a
random text is mixed up with these characters - or emojis - reading the text can be a real pain;
especially if you're trying to convey useful information hidden after the characters or using the
visual shape of the characters instead of letters. Please be mindful of people using screen readers
and follow [the emoji etiquette for accessibility] in your everyday life as well. If done well, the
emoji usage in releases complies with the etiquette as the emojis are in predictable places and can
be skipped as they don't convey any useful information. Most importantly, if you have a team member
using screen readers, listen to them and their experience rather than a random person on the internet.




[including emojis in emails to kernel developers]: https://lore.kernel.org/linux-arm-kernel/20200117111344.GC6144@willie-the-truck/
[shouldn't be doing it]: https://i.kym-cdn.com/photos/images/newsfeed/001/044/247/297.png
[smartphones]: https://9to5mac.com/2018/02/15/messages-crashes-ios-11/
[databases]: https://jira.mongodb.org/browse/PYTHON-65
[related tooling]: https://github.com/vapor/mysql-kit/issues/25
[information leaks]: https://talosintelligence.com/vulnerability_reports/TALOS-2016-0036
[denials of service]: https://threats.kaspersky.com/en/vulnerability/KLA11246/
[they can input anything]: https://xkcd.com/327/
[more than 10 years old MySQL deployments]: https://medium.com/@adamhooper/in-mysql-never-use-utf8-use-utf8mb4-11761243e434
[a list of falsehoods programmers believe about names]: https://www.kalzumeus.com/2010/06/17/falsehoods-programmers-believe-about-names/
[talks at well-known conferences about it]: https://ep2020.europython.eu/talks/9ToYwpp-your-name-is-invalid/
[on Twitter]: https://twitter.com/kentcdodds/status/1083080784682995712
[the emoji etiquette for accessibility]: https://blog.easterseals.com/emojis-and-accessibility-the-dos-and-donts-of-including-emojis-in-texts-and-emails/
