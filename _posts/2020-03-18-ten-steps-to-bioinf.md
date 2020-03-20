---
layout: post
title: From Biologist to Bioinformatician in Ten Worthwhile Steps
---

It’s finally happened. You have an experimental biology question, but don’t know where to start your research. Traditional techniques have lost their luster, or you’re hungry to learn something new. The papers you read make claims you feel powerless to interpret. Maybe your advisor is making you do it. Maybe it’s your reviewer’s fault. Maybe Excel just crashed one too many times. <i>(Special March 2020 edit: Maybe you’re just plain quarantined and need something to do until your keycard works again!)</i>

One way or another, you’ve decided to learn bioinformatics.

Congratulations! I am truly, genuinely thrilled for you. You are about to embark on an exciting journey that will unlock brand new problem-solving skills and fresh insights into science. You are going to delight and amaze your coworkers with your head-turning graphs, nuanced insights, and creative hypothesis formation. Your future self will feel forever indebted to you and your wise choice to familiarize yourself with this particular toolbox.

That said, it’s absolutely normal to feel afraid. This journey will have many twists and turns. This path is not just a learning curve, but a perpetual upward climb. 

<img src = 'https://fictionfanblog.files.wordpress.com/2019/06/homer-mountain.gif' class = 'center'>

You will spend many hours Googling answers to fix basic mistakes (this, you will find, is a critical and ever-present part of the process). You will feel perpetually surrounded by people who wrote their thesis on the tools you are struggling to grasp (this, too, is unavoidable in a field that is both wide and deep). You will spend a gear-grinding year getting good at single cell RNA-Seq, wander into a talk on the limitations of transcriptomics, and leave questioning every professional choice you have ever made. 

But here’s the thing: you can learn basic bioinformatics. This is true regardless of your programming background or your middle school math grades. However far you choose to hike up Mount Bioinformatics, you will gain clear-eyed, fresh perspectives that will distinguish you as a scientist and as a colleague. With effort and time - the same ingredients that made you the biologist you are today - you can become bilingual in both computational and benchside biology.

The first challenge you will face is an abundance of resources and advice. Where do you begin? Should you find an online class, or try to join a seminar series? What will actually be important to know down the line? In short - what is the best use of your time?

I have spent years teaching bioinformatics both to myself and to a diverse set of other biologists. What follows is the approach that seems to work the best for a wide variety of people. Though the strategy below might feel like a long and difficult process, following these steps will help you learn the most important features as quickly as possible.

Given my own background, it is geared towards those learning transcriptomics (e.g., RNA-Seq) but these principles are broadly applicable. I promise they will continue to be useful for any type of computational biology skill you acquire down the line.

Without further ado - those steps are:

1. [Find a project that you care about.](https://kmuench.github.io/2020/03/18/step-1/)
2. **STEP ONE: Find a project that you care about.**
* **STEP TWO: Commit to one approach (at first).**
* **STEP THREE: Decide if you want to code.**
* **STEP FOUR: Start prototyping.**
* **STEP FIVE: Use Github for version control.**
* **STEP SIX: Pay attention to error messages.**
* **STEP SEVEN: Do the vignettes.**
* **STEP EIGHT: Ask for help.**
* **STEP NINE: Manage frustration.**
* **STEP TEN: Refine your prototype.**




## STEP TWO: Commit to one approach (at first)
A lot of biologists - myself included - waste a lot of time trying to plan out the “correct” pipeline rather than just coding something up. In fact, there is usually no “correct” pipeline - and there are often multiple different, valid approaches one can use for any given problem.

When I started my transcriptomics career, I would drop one software pipeline as soon as I got a whiff that something else might be better. Cuffdiff is the past*? Abandon the project halfway through and switch to edgeR! Of course, I quickly discovered that there was no single right way to do things - only dozens of people with strong opinions on the particular way to tailor your analysis for your specific purpose. As a consequence, I wasted a lot of time half-learning techniques, growing steadily more discouraged as I had nothing to show for my hours of work. It wasn’t until I committed to writing a complete version of one of the many potential pipelines that I felt I was making progress. Moreover, once I knew those software packages inside and out, it was much easier to understand why others might be better or worse for my data.

Of course, if you are replicating the results from an existing paper, this step is a little easier - just follow the pipeline described in that paper’s methods.



## STEP THREE: Decide if you want to code.
It is not always necessary to code to analyze large biological datasets. In many cases, graphical user interfaces (GUIs) will allow you to explore and get an intuition for your large datasets quickly. Bulk RNA-Seq users can use Galaxy. Single cell RNA-Seq experiments performed on a 10X Chromium may be able to use Loupe. ATAC-Seq people can use Guava. ChIP-Seq people can use ChIPseeker.

Learning to code, however, will give you three massive advantages: control, reproducibility, and hireability. The more you can tinker with a piece of software, the more flexibility you have to customize the assumptions in the analysis, the exploration of the data, the resulting visualizations. Learning how to write well-organized code will also make it easier for you to say exactly why and how you got a result instead of trying to remember the specific order in which you clicked buttons. Being able to interface with code is also a sought-after job skill that will make you more appealing as a job candidate in both academia and industry.

What languages should you learn? This will depend on your particular bioinformatic specialty. Pretty much every data scientist that uses a computational cluster or Unix (MacOS or Linux) would benefit from learning some basic bash commands for navigating through folders on your computer, peeking at large files, and running scripts. For transcriptomics, I recommend either using R or Python and sticking with that until you feel very fluent in it.

How do you choose which to use? If you are around other coders, use what they use, because it will help your progress tremendously if there are people you can ask for help (more on that later). If you are your lab’s only coder, and doing transcriptomics or Prism-type statistics, I think it’s a toss-up. Python is more flexible and a highly desired skill in a wide array of positions outside academia (although many positions want R). Python is also the preferred method for extremely large datasets (millions of single cell RNA-Seq datapoints!) or for machine learning. R has more widely-vetted ready-made libraries for transcriptomics analysis (although Python is catching up). Both languages will help you do good work and get a job someday. 

If you choose Python, I suggest that you start writing your pipelines in JuPyTer. If you choose R, start writing your pipelines in RStudio using R Notebooks. Both of these formats will allow you to work with code interactively and create neat, formatted, highly annotated versions of your code ready for export into a lab notebook.

Coding isn’t for everyone, and you may hate it. It can be really difficult to tell the difference between frustration and true coding hatred for quite some time. I recommend trying to get through the visualization-producing step of your pipeline before you decide to give up coding forever. It feels great to transform a matrix of numbers into a nice-looking visual! 

Remember - even if you don’t fall in love with coding - having tried it will make it easier to communicate effectively with the people who did.

I am such a big advocate for learning to code, in fact, that I’ll proceed with this outline with the assumption you want to code. 


## STEP FOUR: Start prototyping.
Here is a sad but ironclad truth: experience beats out classes every time. 

There is no book, online tutorial, or workplace training that imbue you with code skills better or faster than just working on your project. Classes might help you get a sense for the basics, but 99% of people forget everything they learn unless they immediately apply it to a project. 

Troubleshooting is your best teacher. True learning comes from repeatedly Googling “How to sum subset of rows of a matrix in R”. Believe it.

(Note that this is why it helps to pick a project that you care about in Step One!)


## STEP FIVE: Use Github for version control.
There may be someone reading over your shoulder right now who tells you that you can skip this step. Please - ignore them! That person likely never codes collaboratively with others, never makes mistakes, or has zero ambitions to work in a job that uses coding. (Yeah, I said it, shoulder-reader! Fight me!)

Version control means keeping track of the many documents you produce as you revise and re-revise your pipeline. Without even knowing it, you probably already use your own sort of version control system for your written documents (e.g., ‘myGrant_1.docx’, ‘myGrant_2.docx’, ‘myGrant_FINAL.docx’, ‘myGrant_FINAL_advisorEdits.docx’...look familiar?). 

Git is a software tool that is really helpful for doing complex, streamlined version control. It works for any kind of text file - cookie recipes, dissertation drafts, or code. It cuts down the number of confusing files on your computer, and helps you keep track of tangents when you try things a different way. Github is a website that hosts what you create with Git. You can find many wonderful tutorials online (I love <a href = 'https://happygitwithr.com/'>happygitwithR.com</a>. You could also check out <a href = 'https://ourcodingclub.github.io/2017/02/27/git.html'>Our Coding Club</a> or <a href='https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4945047/'>this other fun list</a>).

Github is really helpful when you want to send other people code, work on the same piece of code as your student, or back up code because you accidentally deleted it (what, me? never).

Your Github also becomes your professional portfolio. I’ve heard it said that most industry jobs will not even consider you if you do not include your Github on your CV. The code you write, as well as the clarity of its documentation and the amount of activity on your page, are all helpful indicators of your skill level.

One drawback is that all your code is publicly accessible unless you pay for a Pro account. This is non-viable for many biologists working in today’s competitive research environment. However, <b>Git student trainees with an academic email can upgrade to a Pro account for <a href='https://education.github.com/pack'>free</a>.</b> 

STEP SIX: Pay attention to error messages.
In the course of writing your pipeline, you will Google many mysterious error messages. In fact, it will be tempting to just copy/paste the text into Google without actually reading it. In most cases, you will have no other recourse, because the error messages will be gobbledegook.

However, I invite you meditate for a moment about what the error message is saying. Can you glean any clues from the gobbledegook? Is it pointing to specific lines in your code that broke? What does it mean when it says “incompatible type”? Or “object not found“? Asking those questions can help you learn what first troubleshooting steps you can take.

Learning what error messages are associated with what kinds of mistakes will be critical to making your troubleshooting faster.


## STEP SEVEN: Do the vignettes
Software packages often come with vignettes. You may be so eager to work on your project that you will skip the vignette and slap the new tool onto your own data.

This is a mistake. It is a mistake I still make today. Listen: I regret it EVERY. TIME. The vignettes are designed to teach you how to play with the tool and understand all of the ways it can help you. More importantly, doing the vignette will show you if your code’s problems are due to a software issue. It’s better to figure out sooner rather than later that a technique is buggy and under-supported.


## STEP EIGHT: Ask for help.
Getting help when you are well and truly stuck will speed up your learning by an order of magnitude. If you have Googled your problem to death, spent hours trying new approaches, but still cannot figure out the solution, it may be time to ask for help.

(In fact, it probably was the time to ask for help a while ago – you will rarely encounter problems that a more experienced coder can’t solve faster.)

All practicing bioinformaticians got help from someone while they were first learning (and likely still do). Many feel that it is their duty to pay it forward. It is the circle of bioinformatics life.

Outside of the workplace, my two favorite sources of help are friends and internet forums. There are good and bad ways to ask for help. The worst way to ask for help is to make someone else your computer monkey - that is, to ask for someone else to solve your problems for you. Whether you are gchatting a friend or writing a post on Stack Exchange, try to follow these guidelines:
* Introduce a quick description of your problem 
*	Include a brief toy example (e.g., a tiny matrix, a trimmed-down version of your function) so that someone else can replicate your problem 
*	Include any error messages you have received
*	Show that you’ve already tried to solve the problem - describe any actions you have taken to solve the problem on your own, and why they didn’t work (This part is critical)

Often, just following that outline gives me a new idea that helps me troubleshoot my code on my own. 

<p class="message">
PRO TIP: Be courageous in asking for help, but be kind to the people who take the time to do so. A genuine thank-you, and a token of appreciation - an upvote, a bar of chocolate - go a long way.
</p>

## STEP NINE: Manage frustration.
There will almost certainly be a point at which you come perilously close to chucking your computer out the nearest window.

This is normal! Feeling extremely frustrated does not mean you will hate coding forever, or that you are a bad coder. In fact, frustration means that you are truly giving your new bioinformatics muscles a thorough workout, and you are well on your way to becoming stronger. 

But just as a good workout requires a recovery period, effective computational biology require rest as well. It is imperative that you learn how to identify and work around frustration if you are going to acquire bioinformatics as a skill.

If you feel frustrated, try these steps.
1.	Take a quick break. Grab a coffee, have a snack, clear your mind.
2.	If you still feel frustrated, break the problem down into manageable chunks. If the chunks still feel overwhelming, break it down some more. Repeat. The manageable chunk you eventually identify may be very, very small, like Googling the definition of “multiplexing”. Every brick counts when you’re building a palace!
3.	If you need to, ask for help.
4.	If you’re still stuck and feeling lost, take a scientific break. Make a list of side projects you can work on that will make you feel productive. Do you have a list of gene hits you’ve been meaning to read about online? Is there something completely unrelated to bioinformatics you can knock out to feel productive, like a PCR? Can you take a few days off to do a different bench experiment? A week?
5.	Practice self compassion. Remind yourself how much progress you’ve already made. What can you do today that you weren’t able to do when you started? Even small tasks like importing a file can represent big achievements when you are first starting out.

Sometimes it helps to pick a step, set a timer, and devote yourself completely to one of these steps. Give yourself permission to forget about bioinformatics entirely. If you still feel miserable and hopeless every time you sit down to think about code, then you should consider changing your strategy.


## STEP TEN: Refine your prototype.
Once you’ve written your first pipeline through, take time to reflect on it. You may finally have a visualization or a list of hits, but the real work is just beginning.

List the assumptions made by your pipeline. Does any of the software you use assume, for example, that you have an equal number of samples in each condition? Does one algorithm perform best with hundreds of samples, and poorly with only three?

Read papers that ask questions similar to yours. What tools are they using? Are there pieces of your pipeline with superior alternatives, or that better meet the specific requirements of your data?

Seek feedback on your methods and results from practicing computational biologists. Do they have suggestions, or recommendations for best practices?

Now that you have a prototype, refining your pipeline to find the best possible version will be much easier.


## SECRET STEP ELEVEN: Appreciate the view.
If you’ve made it this far, congratulations! You can now mark the part of your life in which you began to learn computational biology. Use your powers wisely and well. 

You know what? Buy yourself that pint of ice cream. Eat it while gloating. You deserve it.



<i>A big thanks to Connie Pasternak for her editorial guidance and excellent feedback on this post.</i>
