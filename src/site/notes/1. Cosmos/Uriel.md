---
{"dg-publish":true,"permalink":"/1-cosmos/uriel/"}
---


202406251520
Status: #idea
Tags: 
State: #nascient
# Uriel
## The Open-Source Incremental Reader for Anki
I've been wanting an incremental reading tool to make my life easier. Never tried SuperMemo (likely should lol), but I have been using Anki to great effects to help with my japanese and recently with my math and computer science ectures in University to commit to memory the appropriate stuff.

But I've been craving for something more than just flashcards, I've been craving for an environment where I could do all my processing and reading in a convenient one in all package and transfer the cards to Anki when they're ready. I do not like having multiple SRS environments, main reason I abandoned the great JPDB software as my japanese vocab software, a sensational app that I recommend to at least try, but something that at least for me can't be my main.
## My Goals
Issues I am aiming to solve:
- I have a ridiculously big list of textbooks, articles and other things to read, things I'll probably never end up reading, because sitting through to read one thing would take well over a year. And while there's an argument to be made for depth, I cannot reasonably read cover to cover, one at a time, all the ressources I want to read and finish what I want to do in a reasonable time.
- i want a set and forget space for my textbooks and notes, equipped with priorities with scheduling. I want the software to on its own take care of the book I am supposed to read, so that when I open the app all I have to think about is how to read what I want.
- I need snippet extraction and card creation. I will expressly not be building the app for SRS, Anki will fill that role. But I want the app to allow me to extract snippets, make flashcards and then send them to Anki.

## Minimal Viable Product ~ MVP
This is already a pretty big project on its own, so to start with let's tone it down to a minimum viable product. 
- Text snippet extraction and ability to make cards (that's the main reason I want to build this)
- One place, universe of stuff I want to read. Think Calibre/Zotero, but simpler, for a start the ability to store files, read them, and remove them from the collection would be the most important.
- Automatic scheduling of the texts, based on priorities.

Logically, the order of implementation would be something like collection manager, text snippet extraction and card maker (plus export), then the scheduling of texts. 

I imagine that even that will probably stretch over a few months, assuming that I focus on this and put other things to the side, which I can hardly do. Still, since I want to hopefully use this, I will focus on it to some extent.

## Tech Stack
- I am planning to code in Rust, love it or hate it, but I drank the Rust kool-aid and I think it has a good future, I like the fact it can be used both for high level, and low level stuff; the fact that it seems to be in vogue in contexts that are critical, and I just find it fun; it forces you to think about what you're writing.

- I will build this desktop using Tauri+[Leptos](https://book.leptos.dev/). As shameful as it is to say in this day and age, I do not have much javascript experience. Played with HTML, CSS, bootstrap, and tailwind, I lost steam about right where they introduced javascript, at the time where it was seen as an irracible language that one just had to tame to do web (I was maybe 14?) Because I am not keen on learning a new language, I will use Tauri for the cross platform aspect, but I'll build the UI in Leptos. Syntax is probably similar enough that I could get by, but no point doing it if I can do without.

- I am planning to use [SQLx](https://docs.rs/sqlx/latest/sqlx/) as my Rust-crate of choice for database management. I know SQL (data science degree, lol) and I like the idea of writing pure SQL for the database stuff, it's also well supported. So yeah.

- I will do my version control using Git, and upload to Github. I don't think I need to explain why.

## The Journey
### Step 1: Building a Rust-powered pdf/epub/web collection reader and annotator:
I want support for the aforementioned format, pdf/epub/html. With the ability to store, read, annotate and extract snippets. I should be able to store all my files in one place.

[[1. Cosmos/Day 1 ~ Backend File Management\|Day 1 ~ Backend File Management]]
[[1. Cosmos/Day 2 ~ Exploring the field\|Day 2 ~ Exploring the field]]
[[1. Cosmos/Day 3 ~ Probably Leave PDF aside for now\|Day 3 ~ Probably Leave PDF aside for now]]
## References
