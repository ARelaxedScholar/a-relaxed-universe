---
{"dg-publish":true,"permalink":"/1-cosmos/day-2-exploring-the-field/","created":"2025-01-22T11:17:14.164-05:00","updated":"2024-06-28T23:08:55.505-04:00"}
---

202406281718
Status: #idea
Tags: 
State: #nascient
# Day 2 ~ Exploring the field
Last day, I set up github, or at least that's what I tried to do.
Learned two lessons (re-learned):
- Don't do things of importance after midnight

*(haha, off by one error joke, give me a job)*

Jokes aside, lazygit didn't work. The whole night after it was still pushing.
We're going to assume I goofed something, so today I started by creating from scratch a git repo, and setting up the environment.

We take longer than I'd want to admit setting up the environment due to annoying merge conflicts, and are now raring to go.

## Overall Organization
From some research beforehand to figure out what I was getting into, I learned the following things that will be useful for our work.

A tauri project will have two sources, one for the UI and one for the backend. I had wrongly assumed that the one simply named "src" would be my main one and that I would use "src-tauri" later down readed when it came to that, but no.

- Src: contain the UI code, normally, this would be javascript/typescript galore, but since we will be using Leptos, we find there a familiar main.rs file accompanied by an app.rs file. It seems that the former contains the backend logic for the UI button, and the app.rs contains the visual components of our app.

Last day, we figured what would be the basics we would need to set to have a working app. Here we will specify them even further to have a more granular understanding.

It seems that before even getting started I will need to learn the PDF codec. ;-;
Considering the shit ton of stuff I already need to learn this is a frustrating setback, but I want to bring this project to fruition so we will give it a shot.

So tomorrow I will start reading and watching videos about the PDF format:
- My goals give a shot to the PDF series by Computerphile
- Acquire the PDF manual.
## References
