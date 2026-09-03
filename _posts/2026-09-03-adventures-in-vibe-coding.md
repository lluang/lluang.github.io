---
title: "Adventures in Vibe Coding a github.io website"
date: 2026-09-03
permalink: /posts/2026/09/adventures-in-vibe-coding/
tags:
  - "artificial intelligence"
  - "generative AI"
  - "programming"
---

I decided to create a github.io [(https://lluang.github.io)](https://www.blogger.com/blog/post/edit/13592469/3159048310915086294#) website using academicpages.github.io framework, because that is what all the cool ML/AI kids seem to do these days.  And it seemed that having a professional web presence there is better than just my blogger site (which is no longer cool. and has lots of non-professional musings).  But it seems like a lot of work.  A rendered site requires lots of data files.  And websites are not my thing.  But working with Generative AI is kinda my thing. So I was going to (1) use generative AI to customize my fork of the academicpages site, (2) create the data files for presentations, publications, and media appearances by pulling it out of the long form of my CV, and (3) vibe code the transfer of my blogger posts into markdown format so it would populate my github.io site.

Setting up the website and creating markdown with the Jekyll YAML front matter was easy. Gemini identified an issue that was solved by updating the version of python being used to render the site, and guided me through various layout decisions.  Presentations and talks and publications were pulled out of my CV, and Gemini helped guide creating categories and filling in the YAML for the dates and permalinks.  The fun part was going to be converting the blog posts.

For the blog posts, I used this chance to practice vibe coding. While in the past I did this inside of an IDE, this time I did this from the terminal using Google [Antigravity CLI](https://www.blogger.com/blog/post/edit/13592469/3159048310915086294#). I had it write a python script that:

1. Read posts from my blogger site.
2. Extract the date and title.
3. Extract text (and links)
4. Write markdown from text and filled in YAML frontmatter
5. Name the file using date and slug generated from the blog title
6. Save this to my [Obsidian](https://www.blogger.com/blog/post/edit/13592469/3159048310915086294#) folder.  This has a side effect of having additional writing samples with my thoughts and opinions in my own words for Generative AI to use when I'm using it to write.

My prompt was

> write a script that takes posts from https://lugerpitt.blogspot.com and creates a markdown file for use in an academicpages site. Yaml header should include title, date, permalink in the posts folder. File name should start with date of posting to the lugerpitt.blogspot site. put the markdown files in the posts directory

So Antigravity wrote a series of python scripts to explore the blogger site, inspect posts, identify links/media, format the posts, and bring everything together into a final script. 

> I have created and executed the Python script convert_blogger_to_academicpages.py to fetch all posts from https://lugerpitt.blogspot.com and convert them into AcademicPages (Jekyll) Markdown format inside the posts directory.
> 
>   ### Key Script Features & Formatting
> 
>   1. Blogger JSON Feed Integration & Pagination:
>       • Automatically handles Blogger feed pagination to fetch all 569 blog posts.
>
>   2. AcademicPages YAML Front Matter:
>       • Each file starts with front matter containing title, date, permalink (formatted as /posts/YYYY/MM/slug/), and tags (derived from Blogger categories).
>       • Titles and tags are safely quoted to handle colons, quotes, and special characters.
>
>   3. Date-Based File Naming:
>       • Output files are named YYYY-MM-DD-slug.md matching the post's published date on Blogger.
>       • Includes automatic collision handling if multiple posts share the same posting date and slug.
>
>   4. Clean Content Conversion:
>       • Converts Blogger HTML markup (images, links, iframe embeds, blockquotes, lists, tables) into clean Markdown.
>       • Cleans up non-breaking spaces and redundant HTML wrapper elements.
> 
>   ──────
> 
>   ### Example Generated Markdown File
> 
>   From 2026-07-25-why-learn-theory.md:
> 
>     ---
>     title: "Why learn theory"
>     date: 2026-07-25
>     permalink: /posts/2026/07/why-learn-theory/
>     tags:
>       - "artificial intelligence"
>       - "generative AI"
>       - "math"
>       - "operations research"
>     ---
> 
>     ![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR_lBVkpEMA8BRtLSXvaiePVL-f77oCvFlEEk6kDtX-Tw&s=10)
> 
>     Why learn theory? We were bringing our daughter back from an arts camp in northern Michigan... 

After looking at the output, I did a series of prompts to take care of removing some extraneous links and my standard writing of docstring for every function.  While the python script was pretty good right away, I did a few prompts to improve the code and output.  And finally I gave Antigravity my usual instructions of writing complete docstrings for each function. (the docstrings also serve as the description of the code.)

This was a fairly straightforward task, although as I am not a web developer I would not have been able to write this. And certainly not in such a short amount of time.  I could have also had Antigravity actually create the markdown versions of the posts. I chose to use AI to write python because I wanted the consistency of actual python code handling the conversions.

To put this in my earlier context on using AI, I find that using Generative AI is great in anything that is not my area of work, it is having a reasonably competent assistant in any domain available as a teammate. I'm sure a real web designer could do a better job, and give me more options, but this was good enough for something that now looks like it has history. And I'm happy with the result.