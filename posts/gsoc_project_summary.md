# Google Summer Of Code 2024 - Project summary
```{post} 2024-07-23
:author: Ioannis Sifnaios
:tags: pvlib, github, open science, gsoc
```

Going through the last week of the Google Summer Of Code 2024, this post is a summary of my experience. An overview of my work can be found in [this pvlib issue](https://github.com/pvlib/pvlib-python/issues/2068), which presents all the merged and ongoing pull requests related to my project.

## Personal reflection

Following the pattern of the GSoC's final evaluation, the first thing to do is to check if the original project goals were fulfilled:

```{admonition} Original project outline
This project aims to extend pvlib's capabilities, enabling accurate modeling of floating PV panels. The following will be added:
* [Estimation of albedo for water bodies](https://github.com/pvlib/pvlib-python/pull/2079)
* [Wind speed calculation at module height](https://github.com/pvlib/pvlib-python/issues/2118)
* [Gallery example of the expansion of the Faiman expression for floating PV](https://github.com/pvlib/pvlib-python/pull/2110)
* [Lindholm model for calculating floating PV module temperature](https://github.com/pvlib/pvlib-python/pull/2075)
```

The GitHub link connected to each of these goals shows that the original project goals have been fulfilled! One interesting thing I learned was the selection procedure for adding something to pvlib. As someone who works in academia and is involved in publishing, I found it very interesting to see how important it is to have fully documented every part of your work so other users can replicate and evaluate it. Though it can be a bit frustrating to some authors, a model or function will never be included in pvlib if every step of it is not fully documented and openly described. This led to some minor changes to my original plan, but luckily, they were quickly adjusted in agreement with my mentors.

However, I did not just strictly follow the original project outline. I was very happily involved in some more maintenance-related tasks, like [fixing broken links in some gallery examples](https://github.com/pvlib/pvlib-python/pull/2111), [correcting the accuracy of some test functions](https://github.com/pvlib/pvlib-python/pull/2080), and [reviewing the documentation after the upgrade to a newer version of sphinx](https://github.com/pvlib/pvlib-python/pull/2112). Last, I added a function that estimates the [water temperature](https://github.com/pvlib/pvlib-python/pull/2104) using the ambient temperature as an input.

Overall, during the GSoC period, I made 30 contributions to pvlib (i.e., commits, pull requests, code review, and issues), contributing to 1387 lines of new code  - you can see a complete list of my commits to pvlib [here](https://github.com/pvlib/pvlib-python/commits?author=IoannisSifnaios).

Looking back, I think I can confidently say that this project was a great success! It has been a very inspiring process, where I've written a lot of code and learned more than I ever could have imagined. Now, all I have to do is put my newly acquired knowledge to good use and keep contributing to pvlib and other open-source libraries!

## Acknowledgments

A huge thanks goes to my mentors [Adam Jensen](https://github.com/AdamRJensen) and [Kevin Anderson](https://github.com/kandersolar), who encouraged me to apply to GSoC and spent countless hours on my project. Their eagerness to help when I got stuck and their devotion to the project has truly been inspiring and really made GSoC a very fun experience for me!

Also, I was very lucky to have two more GSoC students working with pvlib during the same period, [Echedey Luis](https://github.com/echedey-ls) and [Rajiv (Dax) Daxini](https://github.com/RDaxini). This enabled reviewing each other's work, giving feedback to each other, and sharing our questions and frustrations; making GSoC an even more enjoyable experience!

Last, I would like to thank all the pvlib maintainers that, although they were not part of my project, they still gave valuable comments and feedback and increased my learning!
