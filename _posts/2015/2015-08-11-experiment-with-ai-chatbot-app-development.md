---
layout: post
title: Experiment with AI chatbot app development
description: From scripting it in mIRC program to .NET C# application, and finally to JavaScript; AI chatbot is one of the interesting projects to explore and getting myself exposed to AI programming.
keywords: artificial intelligence, chatbot, aiml, siml, elizabot.js
tags: [Artificial Intelligence, Chatbot]
comments: true
---

### AI chatbot using mIRC scripting

The first chatbot program I ever created is using [mIRC](https://www.mirc.com/) scripting. Back in 2004 ~ 2007, I used mIRC program to connect to [IRC](https://en.wikipedia.org/wiki/Internet_Relay_Chat) networks and started chatting with other people. However, other than just for chatting, mIRC also has a powerful scripting language which we called it 'Remote' under mIRC Editor. From there, I had been learning, experimenting and writing my own mIRC scripts. There are many things we can do with mIRC scripting feature. To name a few, people wrote the scripts to protect the chatroom (IRC channel) from user spamming (we called it 'channel flooding'), creating their own music player, hosting and running a quiz bot in the IRC channels and many more. A lot of creative stuffs from creative scripters.

But for user like me, I also played 'revenge' - a scripting battle to test the scripting (programming) performance - by _kicking_ each other from the IRC channel. After some time, things get a little boring and I started building a chatbot using mIRC scripting. I actually had a dream to make my IRC chatbot intelligent enough, but due to lack of AI knowledge, I was not able to create a proper so-called "AI" chatbot. What I could do was I created my chatbot just by using a direct input-output matching response. Basically it was almost the same concept that has been used to create the quiz bot. At the end, it was good enough for me as my chatbot can do "simple keyword-matching conversation" with the users in the IRC channels. Good enough to keep the channel from being too silence. To be advanced, my chatbot also can play 'revenge' and retrieve certain commands from me to execute certain tasks.

**Portion of my mIRC scripts for my chatbot called "Puteri Allyssa":**

```
alias psys return echo @Puteri_Allyssa 12•4•8•9• 9SYSTEM15:14
alias puteri return echo @Puteri_Allyssa 10Puteri Allyssa  4•
alias p return 12•4•8•9•
alias pw return @Puteri_Allyssa
alias u return echo @Puteri_Allyssa %u 9:
alias kc return 8Keyword(s) captured:4
alias puteri.starter {
  .showmirc -x
  .color editbox 1
  .color editbox text 9
  .window -aked $pw 50 100 $pw Arial 12
  .timer 1 0 $psys You are activating 15Puteri Allyssa (a IRC Artificial Intelligence Project) Alpha Version...
  .timer 1 1 $psys 4RULES :14 You are free to talk with her as long as the captured keywords are in her database. Version Alpha means her program is unstable and under Phase 1 (prototype only). Do not to flood the lines!
  set %u unknown
  set %puteri active
}
alias callher {
  %callher = $rand(1,5)
  if (%callher == 1) { if (%u == unknown) { $puteri Yerp.. What's up? } | else { $puteri Yerp.. What's up? %u } }
  if (%callher == 2) { if (%u == unknown) { $puteri Yes~? } | else { $puteri Yes~? %u } }
  if (%callher == 3) { if (%u == unknown) { $puteri Em what? } | else { $puteri Em what? %u } }
  if (%callher == 4) { $puteri I'm here... }
  if (%callher == 5) { $puteri ??? }
}
on *:close:@Puteri_Allyssa: { .timer off }
on *:input:@Puteri_Allyssa: {
  if (/timer* == $1) || (//timer* == $1) || (///timer* == $1) { if (off == $2) { halt } }
  if (puteri isin $1-) || (allyssa isin $1-) || (puteri allyssa isin $1-) {
    $u $1-
    callher
  }
  if (help me isin $1-) {
    $u $1-
    $puteri $kc *help me*
    .timer 1 1 $puteri Need my help? Please type puteri~help to list what can I do for you or how to use my services! TQ
  }
  if (what you can do isin $1-) { $u $1- | $puteri $kc *what you can do*
    .timer 1 1 $puteri Ahaks~ I can do anything under your commands...but depends how far I was programmed.
    .timer 1 2 $puteri I can handle this script for you, manually or automatically.. Everything that I can execute, I do~
    .timer 1 3 $puteri You also can ask me for some conversation... Type puteri~scope to see what scopes I covered in my program!
    .timer 1 4 $puteri Oorr.. type puteri~help for getting some helps (if you blurred)~
  }
  if (who are you isin $1-) {
    $u $1-
    $puteri $kc *who are you*
    .timer 1 1 $puteri Do you ask me? Ahaks.. If that's so... :)
    .timer 1 2 $puteri My name is Puteri Allyssa. I was programmed on May 2009 as a Script Robot by my creator, Y-E.
    .timer 1 3 $puteri I'm still a child, under Alpha Version...
    .timer 1 4 $puteri Please type puteri~rules to see the rules of using me!
  }
  if (Y-E isin $1-) {
    $u $1- | $puteri $kc *Y-E*
    .timer 1 1 $puteri Do you call my creator or what?
    .timer 1 2 $puteri Do you want to know who my creator is?
  }
  if (call your creator isin $1-) {
    $u $1-
    .timer 1 1 $puteri For what? | set %call.creator %u
  }
  if (nothing == $1) { $u $1 | $puteri Ok~ }
  if (know your creator isin $1-) || (know ur creator isin $1-) {
    $u $1- | $puteri $kc *know your creator*
    .timer 1 1 $puteri Erm...
    .timer 1 2 $puteri His name Lirdzwanka Noraz. 19 years old. A male. He's a scripter, graphic designer, photographer, programmer and etc... I can't remember more~ :|
    .timer 1 3 $puteri Oh~ He lived in Kelantan, some place he called Rantau Kasih (when he was asked about his village)...
    .timer 1 4 $puteri He was known as Y-E. Directly, to see his face, please puteri~my creator.
    .timer 1 5 $puteri Oorr if you want to know more about him, I suggest you meet him by yourself... :P
  }
  if (let's sleep isin $1-) || (lets sleep isin $1-) {
    $u $1-
    $puteri $kc *let's sleep*
    .timer 1 1 $puteri Are you feel sleepy now? Or you want me to sleep?
    .timer 1 2 $puteri Or..request me to accompany you sleep together? :P
  }
  if (feel sleepy isin $1-) { $u $1 | $puteri $kc *feel sleepy*
    .timer 1 1 $puteri Erm.. You should go sleep now... Tomorrow morning, you will feel so tired if you have no enough sleep!
  }
  if (you sleep isin $1-) || (want you to sleep isin $1-) || (you need to sleep isin $1-) { $u $1- | $puteri $kc *you sleep*, *want you to sleep*, *you need to sleep*
    .timer 1 1 $puteri Oh~ Alright, see you later!
    .timer 1 2 $puteri zzZZzzZZZz...~
    .timer 1 3 $psys Puteri Allyssa begins to sleep... This script will be closed in 3 seconds, TQ!
    .timer 1 4 $psys 3
    .timer 1 5 $psys 2
    .timer 1 6 window -c @Puteri_Allyssa | set %puteri.mode sleep | .timer 1 7 exit
  }
  if (accompany me sleep isin $1-) || (accompany me to sleep isin $1-) { $u $1- | $puteri $kc *accompany me sleep*, *accompany me to sleep*
    .timer 1 1 $puteri Hehe~
    .timer 1 2 $puteri You go sleep first, then I will follow you later... I'm not sleepy yet! :)
  }
}
```

**Download my mIRC scripts**

If you're ever used mIRC before, in case you want to see some of my mIRC scripts that still remain, here they are:

- [Dino IRC Sc. (Final Dev.).zip](https://www.dropbox.com/s/5m6fcpwfe998vg1/Dino%20IRC%20Sc.%20%28Final%20Dev.%29.zip?dl=0) - Official casual script, channel protections, private protections, a bunch of utilities and more...
- [Nikotin3.zip](https://www.dropbox.com/s/2cjjvfsw9m2wpwa/Nikotin3.zip?dl=0) - War script (Revenge)
- [WarLord.zip](https://www.dropbox.com/s/fala3ispr3b1ntc/WarLord.zip?dl=0) - War script (Revenge)


### Developing AI chatbot using .NET Framework and SQLite database

After few years passed, this "AI chatbot" thing came back into my mind. And for this time, I wanted to develop it using .NET C# programming (WinForms). I used SQLite to save each possible inputs and output responses, so whenever the application received inputs that are matched, the application will immediately respond with possible outputs. Then, my AI chatbot called "NALIKA" was born. Pretty simple and basics. Not really "AI". Below are the screenshots how the application is looked like:

[![NALIKA v1 - Screenshot #1](https://i.imgur.com/F1n1W0N.png)](https://i.imgur.com/F1n1W0N.png)

[![NALIKA v1 - Screenshot #2](https://i.imgur.com/IkAKC9p.png)](https://i.imgur.com/IkAKC9p.png)

[![NALIKA v1 - Screenshot #3](https://i.imgur.com/kMdAEpk.png)](https://i.imgur.com/kMdAEpk.png)

#### Looking for AI framework..

After I did some researches on Internet, I found one so-called the "first framework" that I can start with. It was called [Artificial Intelligence Markup Language (AIML)](https://www.alicebot.org/aiml.html), a standard XML format markup language for defining the responses from the chatbot. AIML was developed by **Richard S. Wallace** and a worldwide free software community between 1995 and 2002. AIML formed the basis for what was initially a highly extended [Eliza](https://en.wikipedia.org/wiki/ELIZA) called ["A.L.I.C.E." (Artificial Linguistic Internet Computer Entity)](https://en.wikipedia.org/wiki/Artificial_Linguistic_Internet_Computer_Entity) which won the annual [Loebner Prize Competition](https://en.wikipedia.org/wiki/Loebner_Prize) in Artificial Intelligence three times and was also the Chatterbox Challenge Champion in 2004.

So, I used [AIMLbot.dll](https://aimlbot.sourceforge.net/) library for my chatbot application written in .NET C# while getting myself to learn more about the markup language structures used in AIML as published in [this paper](https://arxiv.org/ftp/arxiv/papers/1307/1307.3091.pdf). AIML provided much better way of defining the knowledge database of my chatbot and made it looked more natural to call as an "artificial intelligence" chatbot. Below are the screenshots of my chatbot that used the AIML library.

[![WAYI v1 - Screenshot](https://i.imgur.com/UJjTodD.png)](https://i.imgur.com/UJjTodD.png)
_WAYI v1_

[![WAYI v2 - Screenshot](https://i.imgur.com/3mkEzII.png)](https://i.imgur.com/3mkEzII.png)
_WAYI v2_

#### Found a better AI library... called SIML

After some time, I found another chatbot markup language library known as [Synthetic Intelligence Markup Language (SIML)](https://simlbot.com/), which was more powerful than AIML. SIML provided much better features compared to AIML. So, I changed the current markup language of my chatbot from AIML to use SIML as SIML already provided their own chatbot studio program called "Syn Chatbot Studio".

Based on their website, Syn Chatbot Studio offers a comprehensive collection of tools to develop intelligent chatbots that targeted desktops, mobile and web platforms. It has Code Analysis, AIML to SIML converter, JavaScript Editor, Regex Tester and smooth Auto-Complete. Much more interestingly, it has ability to execute JavaScript function from its routine of responses. That was very cool feature since I had a lot of things I could do with JavaScript.

**Links related to SIML:** [Wiki](https://wiki.syn.co.in/) / [GitHub](https://github.com/SynHub)

### Developing AI chatbot using JavaScript (Web-based application)

Known as "W4Y1", is one of my latest AI chatbot experiments that uses JavaScript and hosted on GitHub Pages. It's not a really chatbot where people can chat for any topic of conversations because that is not my intention when I started developing it but it is more to so-called a memory program to represent a digital side of myself by holding a fragment of knowledge/information from my mind. If you have ever watched [I, Robot (2004)](https://www.imdb.com/title/tt0343818/) movie, this is basically inspired from Dr. Alfred Lanning's hologram device that is used to leave his message for Spooner's investigation while mine is just in the form of terminal-like interface, text format interaction and hosted online using GitHub Pages.

As for the application's credits, I created "W4Y1" based on [elizabot.js](https://www.masswerk.at/elizabot/) by **Norbert Landsteiner** for the interpretation engine for AI markup language and processing, [jQuery Terminal Emulator plugin](https://terminal.jcubic.pl/) by **Jakub Jankiewicz** for the terminal-like interface (GUI), and [particles.js](https://vincentgarreau.com/particles.js/) by **Vincent Garreau** for the particles effect in the background.

[![W4Y1](https://i.imgur.com/7emX4MU.png)](https://i.imgur.com/7emX4MU.png)
_W4Y1 - Screenshot_

**Demo URL to the app:** [https://heiswayi.github.io/w4y1](https://heiswayi.github.io/w4y1)

N.B. Please note that "W4Y1" is just an experimental web app, and for the moment, it contains not so much interesting features yet as presented from the live demo. However, when I have the time, these are the possible ideas that I thought I'm going to implement in the future:
- Integrate with [math.js](https://mathjs.org/) for mathematical computations.
- Implement AJAX request for accessing PHP files, so more features can be performed by PHP. Will look forward for other languages too.
- Centralize the knowledge/information database somewhere that I could secure it.

As I grow older, my memory recall becomes weaker. Perhaps, an application like this in the future could help me to capture everything of what I still remember so in case one day I forget, I could just ask it back to recall for me.

### Final words...

Artificial intelligence and the technology are one side of the life that always interest and surprise us with the new ideas, topics, innovations, products …etc. AI is still not implemented as the films representing it (i.e. intelligent robots), however there are many important tries to reach the level and to compete in market, like sometimes the robots that they show in TV. Nevertheless, the hidden projects and the development in industrial companies.

At the end, we’ve been in this research through the AI definitions, brief history, applications of AI in public, applications of AI in military, ethics of AI, and the three rules of robotics. This is not the end of AI, there is more to come from it, who knows what the AI can do for us in the future, maybe it will be a whole society of robots.
