---
{"dg-publish":true,"permalink":"/1-cosmos/day-1-backend-file-management/"}
---

202406272340
Status: #idea
Tags: 
State: #nascient
# Day 1 ~ Backend File Management
Today, I didn't code too much. I focused on understanding how the Leptos-Tauri, Rust setup played together to create one coherent whole.

I also took the time to break down what exactly I mean by "Building a Rust-powered pdf/epub/web collection reader and annotator".

More specifically, what were the features that I would need to implement specifically:
- read files (pdf/ebook/html)
- store webpages as html in some designated folder
- list all the files in the collection

That's for the file part.
Annotation is another thing:
- implement a format that supports annotations (Idk anything about that, so I will need to look into it)
- Write the annotations somewhere somehow, and retrieve them. Potentially on the files themselves.
- Annotate in a buffer and save annotated copy keeping a clean version.

For this part, I choose to focus on the first part.
## Collection Manager ~
Notice how for now everything I have listed is backend stuff. This is because for now this seems like the quickest thing to knock down the list. So I will define the functions.

I started by creating a module for file management, I then break the module up into commands (for tauri) and implementations for how I actually write the stuff. I then have a module for it.

## Setting up the file and git
Besides that I mainly 



## References
