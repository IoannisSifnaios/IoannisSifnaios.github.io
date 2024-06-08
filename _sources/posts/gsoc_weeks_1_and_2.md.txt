# Google Summer Of Code 2024
```{post} 2024-06-08
:author: Ioannis Sifnaios
:tags: pvlib, github, open science, gsoc
```

So, the coding period officially started on May 27th, and the first two weeks of GSoC have already passed! As with everything new, the whole introduction to GiHub and open-source coding has been a bit challenging, but luckily, the mentors were here to help every time I got stuck! I feel like I learned so many things these past two weeks that I have a bit of a hard time organizing my thoughts in a post that makes sense... But I will give it a shot!

One of the biggest struggles one has to go through to start contributing to open-source libraries (like **pvlib**) is working with [GitHub](https://github.com/). GitHub is a web-based platform primarily used for version control and collaborative software development. It provides tools for managing code repositories, tracking changes, and facilitating team collaboration. GitHub contains repositories, which are essentially storage spaces where your project’s files and the revision history of each file are stored.

I can't really say that I am a proficient user of GitHub after only two weeks, but using [GitHub Desktop](https://desktop.github.com/) definitely gave some structure to my work and enabled me to start working with GitHub (even if I am not always 100% sure why or how things work)!

One of the things that amazed me the most in GitHub was version control. GitHub uses Git (a version control system created by Linus Torvalds), allowing multiple developers to work on the same project simultaneously, track changes, and manage different versions of code. To give you an idea of how powerful this tool is, try to imagine the following:

We found a bug in the code, and we were able to tack it back to 2016, where the maintainers changed some functions and there were some leftover parameters that were no longer correct. And it was actually possible to find this incident, and actually see the code being modified and how these parameters remained accidentally unchanged... MIND BLOWING! 

Having an academic background (and being quite bad at documentation - like most academics), I feel that there is a lot to learn from a tool like GitHub. I think that all my future projects should have a streamlined workflow and version control so that my future self doesn't have to struggle if he ever needs to revisit them!

Ok, so maybe my post so far could be titled "An Ode to GitHub"... But this is not the only thing I learned in the past two weeks. I actually submitted my first pull request (PR) to **pvlib**! A PR is essentially a proposal to merge code changes (or add functions) to a project. Of course, the downside of GitHub being so organized is that there is a very specific way to contribute to a repository. Luckily, the **pvlib** maintainers have created a guide called [Contributing](https://pvlib-python--2072.org.readthedocs.build/en/2072/contributing.html), which gives some guidelines on code contributions. 

So, my first PR was adding a function that calculates the [albedo for water bodies](https://github.com/pvlib/pvlib-python/pull/2079). Such a function can be used for estimating the amount of irradiance reflected from the water surface when photovoltaics are placed on water (aka floating PV). Now, I am waiting for the review from the pvlib maintainers. Fingers crossed!

Stay tuned for updates!
