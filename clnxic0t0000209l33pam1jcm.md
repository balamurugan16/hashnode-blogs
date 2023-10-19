---
title: "How to 🙈 Screw up as a Programmer?"
datePublished: Thu Oct 19 2023 18:20:17 GMT+0000 (Coordinated Universal Time)
cuid: clnxic0t0000209l33pam1jcm
slug: how-to-screw-up-as-a-programmer
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/sLrw_Cx6u_I/upload/d936c9d471a30a75c86732f6d10a1349.jpeg
tags: programmer, programming-ciovqvfcb008mb253jrczo9ye

---

We learn anything by trial and error, at least I learned anything that way. But making mistakes will have its own cost, If you make a syntax error that gives a runtime error, you can simply correct the syntax by seeing the error message, But what if you make a mistake that brings down production or something similar which could lead to escalation and other corporate dramas? Those are human errors that are bound to happen and programmers do make these mistakes. There are a lot of horror stories where a faulty algorithm turned out to be looping infinitely to generate a bill of $72,000 from GCP! This is a real story and to know about this [read this article](https://blog.tomilkieway.com/72k-1/).

So what I mean is programmers do make mistakes, of course, I am not encouraging you to go write bad code that will make catastrophic things, but the experiences of these mistakes will help you to be more cautious. I will share some of these experiences that I had that took the soul out of my body for a few hours. 😱

### **Huge bill from AWS! 💸**

Even I got a hefty bill of $40 from AWS. This was when I was in my final year of college where I hosted one Flask API in an AWS EC2 instance for my final year project. Everything was fine until I got the bill. Turns out I have to shut down and deallocate the instance once my job is done! Actually, that statement is so lame to say today but at that time, I had that realization the hard way. I didn’t have the money, what do you expect from a student, 40 dollars? are you kidding me? My parents let me stay in their home for free and I was grateful for that. So anyway I went and deactivated my AWS account so that I could avoid the fee. 😅

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697739413027/af8b09a2-7a70-4454-96df-6f569164367b.png align="center")

### **Kaboom! The code is gone 🙀**

So this happened very recently, I was in a new team as a frontend developer and had a task to work on. So I created a branch, worked on it created a PR myself and self-approved it. I self-approved it because 1. I can’t directly push to the branch because of the branch protection rules, and 2. I was not informed that the code review activity had started because the project was new and those setups were not in place yet. So my newly appointed team lead asked me to revert my PR and get it reviewed. So I did that, in that process, I accidentally reverted one particular merge commit which contained the code of 7 other developers! Yes, SEVEN! I casually reverted the PR and submitted it for review and within 30 minutes, I received escalation emails, and multiple calls from my scrum master, leads and members saying that my recent revert had created chaos. I can’t frame this as an honest mistake because in git, reverting changes is always a tricky task in a collaborative space where other people also push code. So I took the blame and reverted the commit that reverted my merge! Git was a blessing and a curse here, It put me through a nightmare and helped me to come out of it. 😬

So those are 2 among a lot of incidents where I screwed up. I don’t feel the shy in sharing my failures because It is part. I will share this post on LinkedIn where most people will only post their successes. For me, these failures shaped me as a programmer. And actually, I didn’t come up with any content so posted this article to fill the gap. Until next time! 😅👍