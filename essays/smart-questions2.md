---
layout: essay
type: essay
title: "Smart Questions"
# All dates must be YYYY-MM-DD format!
date: 2024-01-25
published: true
labels:
  - Smart Questions
---

<img width="800px" class="rounded float-left pe-4" src="img/3520511.png">

## Finding the Passion

As someone who grew up assembling PCs and modding video games on my PC, I know exactly what it's like see smart and "not smart" questions. I've personally spent a few hundread hours on Reddit just for troubleshooting advice, simply because I know I'm talking to real people who knows exactly what I'm talking about. There's a reason why searching a technical question is typicallay followed by "Reddit" or "StackOverflow," because you're more likely to get real, tired and true solutions rather than coming across the tenth article telling you to "turn it off/on" again. 

## Is this For Me?

Speaking of StackOverflow, it is a deep well of information for software engineers at all skill levels. Whether you're a senior developer or a student who just printed "Hello World" for the first time, everyone will eventually find themselves scrolling through StackOverflow for a solution to their problem. However, if you want to find valuable information, you need to ask valuable questions, or at least find them. It is very easy to ask "I did x to achieve y, but I'm getting z instead. Please fix!!!" and assume other developers will know exactly what you're talking about and fix your problem for you. While I'm sure there are a few developers exactly like that, most people will not even bother with said question if it sounds like the original poster just wants to be spoonfed the answers. Take this question for example:

```
Q: How to create a unit test for a method searching keywords within a list of objects?

I am trying to get the date of the previous month with python. Here is what i've tried:

str( time.strftime('%Y') ) + str( int(time.strftime('%m'))-1 )

However, this way is bad for 2 reasons: First it returns 20122 for the February of 2012 (instead of 201202) 
and secondly it will return 0 instead of 12 on January.

I have solved this trouble in bash with:

echo $(date -d"3 month ago" "+%G%m%d")

I think that if bash has a built-in way for this purpose, then python, much more equipped, should provide something 
better than forcing writing one's own script to achieve this goal. Of course i could do something like:

if int(time.strftime('%m')) == 1:
    return '12'
else:
    if int(time.strftime('%m')) < 10:
        return '0'+str(time.strftime('%m')-1)
    else:
        return str(time.strftime('%m') -1)
        
I have not tested this code and i don't want to use it anyway (unless I can't find any other way:/)

Thanks for your help!
```

## Perhaps...

I'm hoping to delve more into these topics as the semester goes on. Navigating Github was a little overwhelming at first, but it's actually not too bad. Javascript syntax is already similar to most languages I've dabbled in, though ES6 might take some getting used to. I'm mainly excited at the prospect of finally building something that closely resembles a "real-world" project. Since we're doing modules on freecodecamp, I've also signed up for The Odin Project to get a little more experience alongside freecodecamp. I'd have to see how my workload's going to be like for the rest of the semester though!

## Final Remarks
I've found something I want to do. The future looks just a little more certain now. Hopefully going to delve much deeper into the actual process of software engineering this semester. More to come.

Note: ChatGPT was used to fix any spelling/grammatical errors.
