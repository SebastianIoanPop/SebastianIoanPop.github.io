---
layout: post
title: "How to be lazy"
date: 2017-05-31
excerpt: "A post on automation and efficiency"
tags: [automation, bash]
comments: true
---

I've seen it a lot, I've done it a lot and man I hate it a lot. Yes, I am talking about doing repetitive manual work.

A good example started with the first position that I had in 
VeInteractive for my first week (yes I was not a Dev from the start).
The position was as an Email Specialist. Now the responsibilities made sense... most of the time anyway.

As I was the fresh newbie in the company tradition dictates that I would do the worst tasks like:
- accessing 9 Email accounts and checking where 100 emails sent to each account landed, each email different
- investigate any email landing in spam and try to find a solution for it
- run a daily senderscore check for our email servers

You can imagine that after the first 2 hours of doing these tasks I was already questioning my career choices, 
as being tuck in a basement and reading blocks of HTML text is not as fulfilling as it may sound.

My colleague that gave me those tasks however had already a small tool he developed in PHP to run the email 
account checks however it was too simple written and not of acceptable company standards.
So both of us were tasked with "doing it properly" and were put in a dev cradle with a mentor on our side.

That tool took around 1 year to finish and it ended up having 2 services and it's own API. Needless to say, the script 
did it faster and could have saved some effort if we just applied some clean code practices to it.

During the 1 year period of building this tool,  I've discovered various way of automating the 
various email specialist jobs, like senderscore checks, domain validations or other similar trivialities 
that we had to run for all our customers (a big number). 

This other features that we discovered are what actually delayed the tools release as we kept "improving" it but 
never quite managing to finish something.. but that story is for another post.

<figure>
	<a href="https://stephenhaunts.com/2015/10/02/friday-joke-automation/"><img src="https://stephenhaunts.files.wordpress.com/2015/09/4.gif"></a>
	<figcaption><a href="https://stephenhaunts.files.wordpress.com/2015/09/4.gif" title="Friday joke on automation from stephenhaunts blog">Friday joke on automation from stephenhaunts blog</a>.</figcaption>
</figure>

# Terminal, the box of magic and wizardy

Fast-forwarding my learning process of becoming a developer to the very recent days where 
I've already left these projects far behind in some other teams backlog and am now working 
with an Apache Storm project and I also changed my developing environment from a Windows machine to a Mac.
(now don't start criticizing me yet)

I have to say that I tried before having the mac to use the console for various automation 
tasks (like using PowerShell azure cli) but it was just not clicking with me.
However, as a consequence of a workshop held by Diego Luiz (his blog at http://diegoluiz.com) I learned to like the terminal.

After the workshop, I was faced with the first challenge:

The task was something trivial, we had X number of machines where X is a moderately large number that had to 
be stopped at the end of the day and started at the beginning of the day.
The machines were hosted on Azure so we had access to the CLI.

So I could now spend one hour a day clicking start-stop for those machines while sipping 
on some coffee or beer depending the time of the day and day of the week 
OR I could write 15 lines (and even that's because I was verbose) using the most simple terminal tricks like:
- grep
- cut
- azure cli (well documented and easy to use)
- a for each loop (yes sounds complex right??)

The stopping function

```bash
function stop {
    machines=`azure vm list $resourceGroup | grep running | cut -d" " -f14`

    for vm in $machines
    do
        azure vm deallocate $resourceGroup $vm & # It even runs in parallel! Just add a &!
    done

    wait
}
```

The starting function 

```bash
function start {
    machines=`azure vm list $resourceGroup | grep deallocated | cut -d" " -f14`

    for vm in $machines
    do
        azure vm start $resourceGroup $vm
    done

    wait
}
```

And these simple lines of code that I use every day yet are not source controlled nor running as a service are saving 
me 5 hours a week.

If you take it further to fully automate it and add a cron job in front of it then you will have a fully automated 
shutdown mechanism for your Azure VMs. 
I didn't as I prefer to have more control over them and sometimes leave them overnight but there's nothing stopping you!

And that's just one example!

I received more suggestions to automate various tasks, such as creating a scrum master bot to annoy 
people who don't update the backlog every day however I was told that I am annoying enough without a bot to help me.

If you're also working with VMs in the cloud as most developers do this day, consider using a few simple terminal commands
to manage the machines you're working with. You can save time and sometimes money (as in the previous scenario)

Let's not forget that you don't need to receive a letter by owl to start using the terminal, 
you do need to spend about 3 hours reading some boring documentation at least once.

###  But how and where?

A few usefull links can be found here:
- http://www.ee.surrey.ac.uk/Teaching/Unix/ basics
- http://www.thegeekstuff.com/2010/11/50-linux-commands/?utm_source=feedburner should know
- http://www.techradar.com/how-to/computing/apple/terminal-101-automate-the-terminal-with-bash-scripts-1305658 scripting
- https://support.google.com/websearch/answer/134479?hl=en ..yes

Note: it may differ depending on what operation system you're using but these links will give you the main idea on how automation works.
