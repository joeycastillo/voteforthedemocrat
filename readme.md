---
layout: page
title: Information for Site Contributors
---
# The Vote For The Democrat Readme File

First off, some background. Vote For The Democrat is a website dedicated to increasing the ambient positivity surrounding every Democrat who might be on the ballot next November. It lives at [www.voteforthedemocrat.org](https://www.voteforthedemocrat.org) and it's a personal side project from one person, Joey Castillo, who really wants to make sure we don't screw it up again in 2020. Contributions are welcome! 

First off, some basic notes on the site:

* The site is generated by a tool called Jekyll that takes Markdown documents and turns them into plain old HTML pages. 
* The site is broadly structured so that all races have a folder at the top level, i.e. presidential candidates live in a folder called /president/, Senate candidates are all somewhere in /senate/, etc.
* The folder structure generally creates the URL structure of the site, which is to say that `permalink:` fields in the front matter are to be avoided.
* Each candidate should have one markdown file and one photograph in their respective folder.
* **Candidates' markdown files are never to be deleted.** When a candidate is no longer viable (i.e. no path for them to become the nominee in their race), the candidate is marked `viable: false`, and their permalink set to redirect to the main page of the race. This way the link won't 404, but rather take people to a list of Democrats that can still win.

## Editing an existing candidate's page

Just find the candidate's page (it looks like `/president/firstname-lastname.md`) and edit it, right in GitHub. When you're done, open a pull request, and I can merge the changes in. Here's a file from one of the candidates in January 2019: 

    ---
    title: Andrew Yang
    viable: true
    name: Andrew
    surname: Yang
    photo: /president/andrew-yang.jpg
    photo_terms: CC-BY-SA 4.0 photo by Asa Mathat for Techonomy
    website: https://www.yang2020.com
    donate_link: https://secure.actblue.com/donate/friends-of-andrew-yang
    volunteer_link: https://my.yang2020.com
    facebook: andrewyang2020
    twitter: andrewyangVFA
    instagram: andrewyangvfa
    youtube: UCriIuQZpMi6gEt_2P7xKCww
    copyright_line: Bio text adapted from [CC-BY-SA 3.0 Unported](https://creativecommons.org/licenses/by-sa/3.0/) content from Wikipedia
    ---
    Andrew Yang (born January 13, 1975) is an American entrepreneur, the founder of Venture for America, and a 2020 Democratic presidential candidate. He has worked in startups and early stage growth companies as a founder or executive for nearly two decades and was appointed to public office in 2015 by the Obama administration as an Ambassador of Global Entrepreneurship.

Between the `---` lines is the *front matter*. They're like fields in a database, metadata that the Jekyll template will use to populate the page. 

The first few fields shouldn't need to be edited. The `title` field is the name that appears on each page; `viable` notes whether the candidate should be shown in the listings. The `name` and `surname` fields are used for sorting. If this is a house or senate candidate, there may also be a  `state` and `district` field in here.

The `photo` field is a relative URL to the candidate's photo; more on that in a moment. For now note that if you name it the same as the Markdown file and put it in the same folder, it's as simple as `/race/firstname-lastname.jpg` or `/race/state/firstname-lastname.jpg`. 

If the photo is in the *public domain*, such as an official Senate portrait, you may omit or leave blank the `photo_terms` field. If you are uploading a *Creative Commons* photo, make sure to include the required attributions. You may use markdown in this field, but keep it short.

The `website`, `donate_link` and `volunteer_link` fields should be full URL's to each of these pages for the candidate. Please only include official campaign websites; I'll vet these before merging.

The `facebook`, `twitter`, `instagram` and `youtube` fields should contain just the candidate's identifiers for these networks — no full links, and leave the @ symbols out. The Jekyll template for candidate info will format these properly. 

The `copyright_line`, like the `photo_terms` field, should be filled in with the appropriate attributions for the candidate's bio.

Finally, below the front matter is the bio itself. **For the moment, I'm aiming for 400-500 words per candidate**, written in the third person (i.e. not "I believe that," but "Candidate Smith believes..."). In some cases, campaign websites have bios that can fit this format; in other cases, I've raided Ballotpedia or brazenly rewritten official campaign bios. If you're passionate about your candidate and want to write something better than what's there now, please have at! The goal of this site is to tout all of the Democratic candidates, and a great bio is crucial to this effort.

## Adding a New Candidate

Same guidelines apply as above. Make sure to name your candidate's Markdown file `firstname-lastname.md`. If the candidate has any accents in their name, include them in the front matter, but limit the filename to **lowercase ASCII** (i.e. `julian-castro.md`, not `Julián-Castro.md`).

You'll also need to provide a photo. Generally speaking, an official portrait is preferred, both because they are quality photos sanctioned by the candidates themselves, and because they are generally less encumbered by copyright. In the case of portraits shot by federal employees in the course of official business, they are explicitly in the public domain.

Candidate photos are to be cropped to a 4:5 ratio. The final size of all photographs should be **880 × 1100** pixels, in **8-bit RGB** with an **sRGB color profile**. They should be saved as **optimized JPEG files** with a **lowercase .jpg extension**. To ensure that the design of the site stays consistent and gives each candidate equal visual weight, you'll want to follow some guidelines when cropping:


### If your image editing program supports diagonals while cropping

![image](/assets/images/candidate-photo-diagonals.png)

* The top of the subject's head should be just inside the top line of the frame.
* The diagonals from the top left and top right should cross just outside the iris of the subject's eyes, and intersect at the tip of the subject's nose. 
* The diagonals from the bottom left and bottom right should intersect at the bottom of the subject's chin. 

### If your image editing program supports thirds while cropping

![image](/assets/images/candidate-photo-thirds.png)

* The subject should be completely centered within the frame.
* The top of the subject's head should be just inside the top third line.
* The subject's eyes should be just above the top third line and just within the left and right third lines.
* The bottom third line should be just at the subject's neckline.

If an official photo cannot be cropped to these guidelines ([Cory Booker](https://commons.wikimedia.org/wiki/File:Cory_Booker,_official_portrait,_114th_Congress.jpg)), is extremely outdated ([Bernie Sanders](https://commons.wikimedia.org/wiki/File:Bernie_Sanders.jpg)) or has incompatible licensing terms ([Marianne Williamson](https://marianne.com/about/)), you should try to find a Creative Commons or CC0 compatible image that can be cropped to fit the guidelines, preferably one where the candidate is [facing the camera](https://commons.wikimedia.org/wiki/File:Senator_Booker_Meets_with_Judge_Garland_(26396442725).jpg), with [eye contact](https://commons.wikimedia.org/wiki/File:Bernie_Sanders_in_January_2016_by_Gage_Skidmore.jpg) or [an engaged expression](https://commons.wikimedia.org/wiki/File:Andrew_Yang_talking_about_urban_entrepreneurship_at_Techonomy_Conference_2015_in_Detroit,_MI.jpg). Look for an image with [minimal background distractions](https://www.flickr.com/photos/jus10h/14041888020/) so that the focus is on the candidate and not the surrounding scene, but **do not clone-stamp or artificially blur the background**, even if the CC license allows modification. This is an ethics thing for me, not a copyright thing.

Open a pull request touching only the files that need to be changed to add or update your candidate. There is no need to reach out via email; I'll get notified whenever a pull request is opened.