---
layout: post
title: "Internet browsers with Chinese characteristics"
date: 2013-03-20 09:46
comments: true
categories: china browsers ie6
---
## Being in China
The ex-patriots in China are very aware of the internet restrictions. Aka, internet with Chinese characteristics. It’s hard to explain to others what it’s like behind the Great Firewall. No facebook, no NY Times, and the sense of consistency. Beyond the occasional officially-unofficial media blackouts, most of the world doesn't think about what the internet is like in China, even though there are more internet users in China than there are citizens of the United States. [apira.org](http://j.mp/12wZ7mL) 

The censorship is secondary to considerations of the internet for web developers targeting Chinese users. In China, Internet Explorer 6 was king for far too long. The fallout from its history is obvious for web developers from the West. Like myself, China facing websites do not have the luxury of ignoring "obsolete" users. In a country where there are over 250 million Internet Explorer users, China facing websites consider an incredibly aggressive browser ecosystem. 

## Battle against the obsolete

There have, however, been enormous improvements in browser technologies recently. Two years ago IE6 had a 60% market share in China ([w3.org](http://j.mp/13HOpZG). Today, the wonderful website [IE6CountDown](http://www.ie6countdown.com/) states IE6 is a little more than 25% of the Chinese internet user population.

The problem with IE6 is not one of ignorance. IE6’s prior domination of the Chinese browser-share was the result of China’s piracy ecosystem. Remember the Windows XP system updates? If you remember correctly, only authorized editions of Windows XP are allowed to make those system updates. Because Chinese street markets sell a lot of "low-cost" software (aka, pirated software), a lot of Chinese computers can’t get official system updates. Old computers without system updates are unable to upgrade from their original IE6 browser. 

Adding insult to injury, Chinese web developers target the IE6 browsers. Jerry Jinks from [Maxthon](http://www.maxthon.com/about-us/) (a Chinese web browser provider) elegantly [explained](http://www.w3.org/QA/2012/06/interview_huawei_maxthon_qihoo.html) the IE6 problem: "There's a vicious cycle around IE6 in China: users keep using it because sites are designed for IE6, and people build sites for IE6 because users stay with it." By having a market that depends on IE6, web developers can continue buildings for obsolete systems. Table based layouts, Dreamweaver WYSIWYG markup, and browser hacks litter Chinese websites.

Although the problem is large, the problem has not gone unaddressed. Microsoft partnered with Chinese anti-virus and internet browser company Qihoo 360 to systematically eliminate IE6. The partnership allowed Qihoo to make upgrades to the default browser on Windows XP systems from IE6 to IE8. Because Qihoo markets itself as a “security solution,” users recognize the need to download and install the new software. While users feel they are more secure, Qihoo is really just another web browser.

Qihoo’s browser is based on a Microsoft browser framework called Trident. Trident, like Webkit, is a rendering engine which allows browser makers to have a solid starting point. Rather than rewriting a complete browser engine, browser developers can start from solid footing to customize the user experience, rather than the rendering engine. For reasons related to China’s interest in Microsoft products, Trident has been very popular.

Two of the largest China based browsers, Qihoo and Maxthon, use Trident ([sec.gov](http://j.mp/15A73RR)). Trident was developed by Microsoft to server as a web rendering engine for applications accessing web pages. Trident leverages parts of Internet Explorer, Webkit, and Chrome for various tasks. Interestingly enough, although Trident continues to develop today, the versions in Qihoo and Maxthon are dependent on IE8. Although the Chinese markets are moving off IE6, they are still using IE8. For web developers, that means no media-queries, no CSS3...

For browser developers, using an existing rendering engines makes sense. The W3C and WHATWG have both been emphasizing the need for browser consistency. After the intensional varriance of Netscape and Internet Explorer in the 90’s, browsers started keeping to a set of rules. For new browsers developing, like Qihoo and Maxthon, using existing rendering engines allows the companies to focus on other features. For example, Qihoo focuses on firewall and virus scanning tools. Compared to other alternative browsers, like Chrome and Firefox, marketing based on the value of security has worked in Qihoo’s favor.

## Different priorities
China's web infrastructure growth has impressed me with its high internet penetration rates, but the websites themselves are not so innovative. To be fair to Chinese web developers, though, there is a different focus on developing for the web in China. Users here don't want the newest technologies just because they are available. Again, as [Jerry Jinks stated](http://www.w3.org/QA/2012/06/interview_huawei_maxthon_qihoo.html), "They just want to see the Web". The issue is along the expectations behind the Chinese internet consumers. Just because there are a lot of users, does not by any means result in high quality websites.

US web users are spoiled. If a website isn’t pretty or doesn't load in a set period of time, they don’t want to visit the site. There is research that proves this ([seomoz](http://j.mp/Yf5WRn). Chinese users browsing habits are still developing. Standing on a train and looking over people's shoulders, you see people reading websites rendered without any CSS. 

Importance is not widely placed on web standards. Beautiful, shiny, CSS3-filled, progressively enhanced HTML5 websites are few in China. In fact, there are some web practices that are simply painful to watch ([queue Flash splash page leading to table layout website](http://zombo.com/)). The need for old browser coverage results in the sheer inability to embrace innovative technologies. It doesn't help that new libraries and frameworks are proudly dropping support for IE6 and IE7. 
Ironically, in a place where old browsers are such a problem, I have yet to see a Chinese progressively enhance or gracefully degrading website. When Modernizer and polyfills are being developed for the exact purpose of serving the worlds edge case browsers, I don't see a wide range of Chinese adopters. 

There’s a plethora of digital and printed content about web development available in English, but rarely to I see the same kind of material circulated in China. While I don't know if an internet growth market would be interested in the concepts of web standards, it could benefit from access to the discussions. 

## Conclusion
There is something to be said for the recent popularization of dropping support for old browsers. Undeniably, costs to develop for old browsers can be unreasonably high and unmanageable. Still, it should be considered that dropping support for old browsers entails dropping support for huge parts of the world. I am certain that in the coming years, China won't be as affected by this issue. Mobile browsers are exponentially claiming internet browser marketshare. For mobile devices alone, heads are turning toward standards and HTML5.

Until then, don't forget about the products Made in China and good luck finding stylish Chinese system fonts.

