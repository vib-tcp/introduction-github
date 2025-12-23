<!--
author:   Bruna Piereck, Alexander Botzki, James Collier, Tuur Muyldermans
email:    trainingandconferences@vib.be
version:  1.0.0
language: en
narrator: UK English Female

icon:     https://vib.be/sites/vib.sites.vib.be/files/logo_VIB_noTagline.svg

comment:  This document shall provide an entire compendium and course on the
          development of Open-courSes with [LiaScript](https://LiaScript.github.io).
          As the language and the systems grows, also this document will be updated.
          Feel free to fork or copy it, translations are very welcome...

script:   https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.js
          https://felixhao28.github.io/JSCPP/dist/JSCPP.es5.min.js

link:     https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.css
link:     https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css
link:     https://raw.githubusercontent.com/vib-tcp/material-liascript/master/img/org.css
link:     https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.11.2/css/all.min.css
link:     https://fonts.googleapis.com/css2?family=Saira+Condensed:wght@300&display=swap
link:     https://fonts.googleapis.com/css2?family=Open+Sans&display=swap

link:  https://raw.githubusercontent.com/vib-tcp/material-liascript/master/vib-styles.css

@orcid: [@0](@1)<!--class="orcid-logo-for-author-list" -->

@edition: 10th 
@CourseTitle: Versioning code and documentation with Git & GitHub

@JSONLD
<script run-once>
  let json = @0 

  const script = document.createElement('script');
  script.type = 'application/ld+json';
  script.text = JSON.stringify(json);

  document.head.appendChild(script);

  // this is only needed to prevent and output,
  // as long as the result of a script is undefined,
  // it is not shown or rendered within LiaScript
  console.debug("added json to head")
</script>
@end

-->

# Versioning code and documentation with Git & GitHub

<section>

Hello and welcome to our workshop! We are very happy to have you here.

This is the @edition edition of this workshop, jointly organised by VIB and ELIXIR.

> We are using the interactive Open Educational Resource online/offline course infrastructure called LiaScript.
> It is a distributed way of creating and sharing educational content hosted on github.
> To see this document as an interactive LiaScript rendered version, click on the
> following link/badge: [LiaScript](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/README.md)

## General context

This workshop will take you through the basics and a little more on how to use Git and GitHub.
Tighten your sitbelts to enjoying some time-travel analogy to understand how Git works, how you can connect it to GitHub and how this will help you with your version control and potentially impact your publication.

We will introduce you to this free and open source distributed version-control system designed to maintain, track changes, recover old versions and collaborate with other while developing your code and documentation. 

## Proposed Schedule

Schedule day 1:

* 09h30 - Configurations & Introduction

* 11h00 - Coffee break  

* 11h15 - Routine usage part 1 (status-stage-commit) 

* 13h00 - Lunch 

* 14h00 - History & Comparing Versions 

* 14h40 - Coffee break   

* 14h55 - Collaborating in GitHub  

* 17h00 - End of the day  

Schedule day 2:

* 09h30 - Solving Conflicts 

* 10h30 - Coffee break 

* 10h30 - Experimenting Risk Free: Working with Branchs

* 12h30 - Lunch 

* 13h00 - Tagging & Forking  

* 15h00 - Coffee break 

* 15h00 - Using the browser 

* 17h00 - End of the day 

</section>

# Lesson overview

> <i class="fa fa-lock"></i> **License:** [Creative Commons Attribution 4.0 International  License](https://creativecommons.org/licenses/by/4.0/deed.en)
>
> [<img src="https://raw.githubusercontent.com/vibbits/introduction-github/master/images/logos/CC-by.png" title="" alt="" width="80">](https://creativecommons.org/licenses/by/4.0/)
>
> <i class="fa fa-user"></i> **Target Audience:** Researchers, trainers, training providers
>
> <svg xmlns="http://www.w3.org/2000/svg" height="14" width="16" viewBox="0 0 576 512"><!--!Font Awesome Free 6.5.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2023 Fonticons, Inc.--><path d="M384 64c0-17.7 14.3-32 32-32H544c17.7 0 32 14.3 32 32s-14.3 32-32 32H448v96c0 17.7-14.3 32-32 32H320v96c0 17.7-14.3 32-32 32H192v96c0 17.7-14.3 32-32 32H32c-17.7 0-32-14.3-32-32s14.3-32 32-32h96V320c0-17.7 14.3-32 32-32h96V192c0-17.7 14.3-32 32-32h96V64z"/></svg> **Level:** Beginner  
>
> <i class="fa fa-arrow-left"></i> **Prerequisites**  
> Some experience with command line linux/unix/bash. For that you can follow the [***Introduction to Linux command line***](https://elearning.vib.be/courses/linux/) on [VIB e-learnign](https://elearning.vib.be/) system.
>
> <i class="fa fa-bookmark"></i> **Description**  
> Get you started with Git from zero (note that if you already use Git, this workshop will be too introductory for you). This course is intended for anyone who is learning or using a programming language (R, Python, ...) or writing documentation that needs a record of changes. If you intend to make your code collaborative, bonus points for you! This course consist of a lot of practice combined with some theory.
> 
> <i class="fa fa-arrow-right"></i> **Learning Outcomes:**  
> By the end of the course, learners will be able to:
>
> 1. Configure Git on a local machine to prepare for version control in research projects.
> 2. Create and manage repositories using Git commands to track changes and maintain project history.
> 3. Apply basic Git operations (e.g., staging, committing, pushing) to work effectively with local and remote repositories.
> 4. Implement branching and pull request workflows to collaborate with others on shared codebases.
> 5. Interpret Git logs and history to understand project evolution and troubleshoot issues.
> 6. Collaborate with other people in your project.
>
> <i class="fa fa-hourglass"></i> **Time estimation**: 16 hours (2 days)
>
> <i class="fa fa-asterisk"></i> **Requirements:** The (technical) installation requirements are described in the chapter ["Get ready"](./docs/tutorials/1_Get_ready_for_the_course/tutorial.md).
>
> <i class="fa fa-envelope-open-text"></i> **Supporting Materials**:
> 
> 1. [Exercises](./docs/exercises/)
> 2. [Slides](./docs/presentation/)  
> 
> <i class="fa fa-life-ring"></i> **Acknowledgement**:
>
> * [ELIXIR Belgium](https://www.elixir-belgium.org/)
> * [VIB Technologies](https://www.vib.be/)
>
> <i class="fa fa-money-bill"></i> **Funding:** 
>
> <i class="fa fa-anchor"></i> **PURL**:  


## Authors and Contributors

Authors

- @[orcid(Bruna Piereck)](http://orcid.org/00000-0001-5958-0669)
- @[orcid(James Collier)](http://orcid.org/0000-0002-0020-421X)
- @[orcid(Tuur Muyldermans)](http://orcid.org/0000-0002-3926-7293)
- @[orcid(Alexander Botxki)](http://orcid.org/0000-0001-6691-4233)

## Citing this lesson

Please cite as:

  1. to be added soon ...

# Chapters List

## [1. Get Ready for the course](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/01_Get_ready_for_the_course.md#1) 

In this chapter you will find the step-by-step of what you need to get ready for this course. You will be guided in installing all tools that will be used and find a link to practice a bit of UNIX/LINUX command line before you join the course. 

There are preparation steps for all, Windows, Linux and Mac computers. 

Most things you need to get installed before hands, one or the other are optional tools to help with visualization and for somethings you can ask the trainer by mail or arriving 30 min before the class starts.

[click here 🔗](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/01_Get_ready_for_the_course.md#1)

__

[<img src="https://raw.githubusercontent.com/vibbits/introduction-github/192d9178ab16af65b9f743d096ce3e9c0ed60133/images/help!.svg" width="200"/>](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/01_Get_ready_for_the_course.md#1)


## [2. Introduction ](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/02_introduction.md#1)

Find out the differences between Git and GitHub why reflecting into versioning your documents and codes. Why is Git in several cases the best approach for versioniung?

[click here 🔗](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/02_introduction.md#1)

__

[<img src="https://raw.githubusercontent.com/vibbits/introduction-github/8fc0d7c978044944c18f6e85e25aa2961af13a32/images/git_diff_github.svg" width="200"/>](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/02_introduction.md#1)

## [3. Get started with Git](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/03_getting_started.md#1) 

Understand how Git is structured to use in your favor when debugging. Onve you have that you can make your first commit, learn the basic routine to get one version saved and managed with Git. With all that in place you have learned the basic routine of Git and can use to basic projects.

__

[click here 🔗](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/03_getting_started.md#1)

[<img src="https://raw.githubusercontent.com/vibbits/introduction-github/ab984e5abf41d29cd68a2ef732cfb5e8bd41d87d/images/Git-logo-black.svg" width="150"/>](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/03_getting_started.md#1)


## [4. A travel in Time: Check your versions](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/04_time-travel_my_versions.md#1)

Go a bit beyond to be able to see old versions and compare with the current one. You can list all versions to remember what has been changed, check among all the files in your dev. area if they need some version update or simply compare. You are moving towards becoming more confident and using some of the power of Git.

[click here🔗](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/04_time-travel_my_versions.md#1)

__

[<img src="https://raw.githubusercontent.com/vibbits/introduction-github/c67c73b703dd8df3b51e9ef79d220abd70215032/images/images_tutorial/DeLorean_back.svg" width="150"/>](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/04_time-travel_my_versions.md#1)


## [5. Connect to GitHub](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/05_Connecting_2_GitHub.md#1)

Connect your local repository to GitHub, make a remote backup of all your versions. Your commands routine will have a few steps added to keep it all in sync. This step will move you foward to also be able to collaborate with your colleages. 

 [click here🔗](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/05_Connecting_2_GitHub.md#1)

__

[<img src="https://raw.githubusercontent.com/vibbits/introduction-github/master/images/class-act.png" width="150"/>](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/05_Connecting_2_GitHub.md#1)


## [6. READM & .gitignore - Importante files](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/06_gitignore%26README.md#1)

GitHub is not about intuition, is about concient choices and clear messages. Learn about README files and .gitignore files. They will make all the difference in the organization of your repositories. These are essential for a good project development.

[click here🔗](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/06_gitignore%26README.md#1)

__

[<img src="https://raw.githubusercontent.com/vibbits/introduction-github/8fc7c9dfd9497984d3031e267658c7bf052db913/images/git_files.svg" width="150"/>](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/06_gitignore%26README.md#1)


## 7. [Collaborting](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/07_collaborating_GitHub.md#1)

Start a collaboration and develop together with your colleagues. As in real life, git projects and collaborations can lead to some conflicts. If both have to work in the same file, or different ideas need to be tested. Do not worry!!! In this chapter we teach you how to start the collaboration, best practices when working in a team and last but not least ... HOW TO SOLVE CONFLICTS! Only in Git, ofcourse.

[click here🔗](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/07_collaborating_GitHub.md#1)

__

[<img src="https://raw.githubusercontent.com/vibbits/introduction-github/master/images/benevocats.png" width="200"/>](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/07_collaborating_GitHub.md#1)


## [8. Branchs](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/08_branches.md#1)

To work in collaboration or experiment new code or documentation desing you can creat parallel developing areas. Learn more about the application of Branchs, how to create, delete and merge them. This is a great resource to avoid breaking the working version of your project or even to just test a new idea. This step wil take you to the next level when working with and GitHub. It will add more flexibility, more organization and garantee that you can always have a functional version of your code.

[click here🔗](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/08_branches.md#1)

__

[<img src="https://raw.githubusercontent.com/vibbits/introduction-github/548d204f4613b52f5fb95e80168c34baa69f0286/images/branch_basic.svg" width="130"/>](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/08_branches.md#1)


## [9. Forks](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/09_forks.md#1)

You find a nice repo that you want to work on a new idea, or you want your collaborators to work separatelly before their changed is reviewd and approved for merging. Here it is an strategy for you. Forking adds a layer for a reviewer, and also allows you to start a personal project from someone elses project. Take a look to learn more about this interesting resource.

[click here🔗](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/09_forks.md#1)

__

[<img src="https://raw.githubusercontent.com/vibbits/introduction-github/master/images/forktocat.jpg" width="230"/>](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/09_forks.md#1)


## [10. Aliases](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/10_Git_aliases.md#1)

Create commans shortcut for your favorite commands, simply your commands routine by creating your own commands.

[click here🔗](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/10_Git_aliases.md#1)

__

[<img src="https://raw.githubusercontent.com/vibbits/introduction-github/39cd4a64d2e4ad573cba1fc8283ad2b25b755ab7/images/git_aliases.svg" width="200"/>](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/BP_addtemplatFormating/docs/tutorials/10_Git_aliases.md#1)


## [11. GitHub & Rstudio](https://github.com/vib-tcp/introduction-github/blob/BP_addtemplatFormating/docs/tutorials/11_github_rstudio.md)

A big developer of R ? 
Integrate Git, GitHub and RStudio. Develope all your project in one platform and take advantage of the ready to use  buttons avoiding extra command line. 

[click here 🔗](https://github.com/vib-tcp/introduction-github/blob/BP_addtemplatFormating/docs/tutorials/11_github_rstudio.md)

__

[<img src="https://raw.githubusercontent.com/vibbits/introduction-github/master/images/images_tutorial/rstudio-1.PNG" width="200"/>](https://github.com/vib-tcp/introduction-github/blob/BP_addtemplatFormating/docs/tutorials/11_github_rstudio.md)


# About us

*About ELIXIR Training Platform*

The ELIXIR Training Platform was established to develop a training community that spans all ELIXIR member states (see the list of Training Coordinators). It aims to strengthen national training programmes, grow bioinformatics training capacity and competence across Europe, and empower researchers to use ELIXIR's services and tools.

One service offered by the Training Platform is TeSS, the training registry for the ELIXIR community. Together with ELIXIR France and ELIXIR Slovenia, VIB as lead node for ELIXIR Belgium is engaged in consolidating quality and impact of the TeSS training resources (2022-23) (https://elixir-europe.org/internal-projects/commissioned-services/2022-trp3).

The Training eSupport System was developed to help trainees, trainers and their institutions to have a one-stop shop where they can share and find information about training and events, including training material. This way we can create a catalogue that can be shared within the community. How it works is what we are going to find out in this course.

*About VIB and VIB Technologies*

VIB is an entrepreneurial non-profit research institute, with a clear focus on groundbreaking strategic basic research in life sciences and operates in close partnership with the five universities in Flanders – Ghent University, KU Leuven, University of Antwerp, Vrije Universiteit Brussel and Hasselt University.

As part of the VIB Technologies, the 12 VIB Core Facilities, provide support in a wide array of research fields and housing specialized scientific equipment for each discipline. Science and technology go hand in hand. New technologies advance science and often accelerate breakthroughs in scientific research. VIB has a visionary approach to science and technology, founded on its ability to identify and foster new innovations in life sciences.

The goal of VIB Technology Training is to up-skill life scientists to excel in the domains of VIB Technologies, Bioinformatics & AI, Software Development, and Research Data Management.

--------------------------------------------

*Editorial team for this course*

Authors: @[orcid(Alexander Botzki)](https://orcid.org/0000-0001-6691-4233), @[orcid(Bruna Piereck)](https://orcid.org/0000-0001-5958-0669)

Technical Editors: Alexander Botzki

License: [![CC BY SA](img/picture003.jpg)](https://creativecommons.org/licenses/by-sa/4.0/deed.en)

```json   @JSONLD
{
  "@context": "https://schema.org/",
  "@type": "LearningResource",
  "@id": "https://elixir-europe-training.github.io/ELIXIR-TrP-TeSS/",
  "http://purl.org/dc/terms/conformsTo": {
    "@type": "CreativeWork",
    "@id": "https://bioschemas.org/profiles/TrainingMaterial/1.0-RELEASE"
  },
  "description": "track the versions of your code and your documentation, make your research more reproducible and more impactifull",
  "keywords": "FAIR, Reproducibility, RDM, code, data analysis",
  "name": "Versioning code and documentation with Git & GitHub",
  "license": "https://creativecommons.org/licenses/by/4.0/",
  "educationalLevel": "beginner",
  "competencyRequired": "Unix command line basic knowledge",
  "teaches": [
    "1. Configure Git on a local machine to prepare for version control in research projects.",
    "2. Create and manage repositories using Git commands to track changes and maintain project history.",
    "3. Apply basic Git operations (e.g., staging, committing, pushing) to work effectively with local and remote repositories.",
    "4. Implement branching and pull request workflows to collaborate with others on shared codebases.",
    "5. Interpret Git logs and history to understand project evolution and troubleshoot issues.",
    "6. Collaborate with other people in your project."
  ],
  "audience": "training providers",
  "inLanguage": "en-US",
  "learningResourceType": [
    "tutorial"
  ],
  "author": [
    {
      "@type": "Person",
      "name": "Bruna Piereck"
    },
    {
      "@type": "Person",
      "name": "James Collier"
    },
    {
      "@type": "Person",
      "name": "Alexander Botzki"
    }
    {
      "@type": "Person",
      "name": "Tuur Muyldermans"
    }
  ],
}
```
=======

<!--
author:   Bruna Piereck, James Collier, Tuur Muyldermans, Alexander Botzki
email:    trainingandconferences@vib.be
version:  3.0.0
language: en
narrator: UK English Female

icon:     https://vib.be/sites/vib.sites.vib.be/files/logo_VIB_noTagline.svg

comment:  This document shall provide an entire compendium and course on the
          development of Open-courSes with [LiaScript](https://LiaScript.github.io).
          As the language and the systems grows, also this document will be updated.
          Feel free to fork or copy it, translations are very welcome...

script:   https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.js
          https://felixhao28.github.io/JSCPP/dist/JSCPP.es5.min.js

link:     https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.css
link:     https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css
link:     https://raw.githubusercontent.com/vib-tcp/material-liascript/master/img/org.css
link:     https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.11.2/css/all.min.css
link:     https://fonts.googleapis.com/css2?family=Saira+Condensed:wght@300&display=swap
link:     https://fonts.googleapis.com/css2?family=Open+Sans&display=swap

link:  https://raw.githubusercontent.com/vib-tcp/material-liascript/master/vib-styles.css

@orcid: [@0](@1)<!--class="orcid-logo-for-author-list"-->

@edition:  1sh 
@CourseTitle: Versioning code and documentation with Git & GitHub

@JSONLD
<script run-once>
  let json = @0 

  const script = document.createElement('script');
  script.type = 'application/ld+json';
  script.text = JSON.stringify(json);

  document.head.appendChild(script);

  // this is only needed to prevent and output,
  // as long as the result of a script is undefined,
  // it is not shown or rendered within LiaScript
  console.debug("added json to head")
</script>
@end

-->

# @CourseTitle

<section>

Hello and welcome to our workshop! We are very happy to have you here.

This is the @edition edition of this workshop, jointly organised by VIB and ELIXIR.

> We are using the interactive Open Educational Resource online/offline course infrastructure called LiaScript.
> It is a distributed way of creating and sharing educational content hosted on github.
> To see this document as an interactive LiaScript rendered version, click on the
> following link/badge: [LiaScript](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/training_material_template/main/README.md)

## General context

This workshop will take you through the basics and a little more on how to use Git and GitHub.
Tighten your sitbelts to enjoying some time-travel analogy to understand how Git works, how you can connect it to GitHub and how this will help you with your version control.
Git is a free and open source distributed version-control system designed to maintain code, track changes, recover old versions and collaborate with other developers. 

## Proposed Schedule

Schedule day 1:

- 9:30 - 11:00 - session
- 11:00 - 11:15 - break
- 11:15 - 12:45 - session
- 12:45 - 13:45 - lunch
- 13:45 - 15:15 - session
- 15:15 - 15:30 - break
- 15:30 - 17:00 - session

Day 1

| Time  | Session                                                                   |
| ----- | ------------------------------------------------------------------------- |
| 9h30  | Configurations & Introduction                                             |
| 11h00 | Coffee break                                                              |
| 11h15 | Routine usage part 1 (status-stage-commit)                                |
| 13h00 | Lunch                                                                     |
| 14h00 | History & Comparing Versions                                              |
| 14h40 | Coffee break                                                              |
| 14h55 | From Git to GitHub                                                        |
| 17h00 | End of the day                                                            |

Day 2

| Time  | Session                                                                   |
| ----- | ------------------------------------------------------------------------- |
| 9h30  | Collaborating in GitHub                                                   |
| 11h00 | Coffee break                                                              |
| 11h15 | Experimenting Risk Free: Working with Branchs                             |
| 13h00 | Lunch                                                                     |
| 14h00 | Solving Conflicts and changing old versions                               |
| 14h40 | Coffee break                                                              |
| 14h55 | Tagging & Forking                                                         |
| 17h00 | End of the day                                                            |

</section>

# Lesson overview

> <i class="fa fa-lock"></i> **License:**  [Creative Commons Attribution 4.0 International  License](https://creativecommons.org/licenses/by/4.0/deed.en)
>
> [<img src="https://raw.githubusercontent.com/vibbits/introduction-github/master/images/logos/CC-by.png" title="" alt="" width="80">](https://creativecommons.org/licenses/by/4.0/)
>
> <i class="fa fa-user"></i> **Target Audience:** Researchers, trainers, training providers, anyone that wants to learn about git
>
> <svg xmlns="http://www.w3.org/2000/svg" height="14" width="16" viewBox="0 0 576 512"><!--!Font Awesome Free 6.5.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2023 Fonticons, Inc.--><path d="M384 64c0-17.7 14.3-32 32-32H544c17.7 0 32 14.3 32 32s-14.3 32-32 32H448v96c0 17.7-14.3 32-32 32H320v96c0 17.7-14.3 32-32 32H192v96c0 17.7-14.3 32-32 32H32c-17.7 0-32-14.3-32-32s14.3-32 32-32h96V320c0-17.7 14.3-32 32-32h96V192c0-17.7 14.3-32 32-32h96V64z"/></svg> **Level:** Beginner  
>
> <i class="fa fa-arrow-left"></i> **Prerequisites**  
> To be able to follow this course, learners should have knowledge in:
> 
> 1. Basic knowlegde of UNIX/Linux command line  
>
> <i class="fa fa-bookmark"></i> **Description**  This course consist of two days training that leads you from A to Z into the basics of how to use Git and connect with GitHub. After this course you will feel confortable to use it and work with others.
> 
> <i class="fa fa-arrow-right"></i> **Learning Outcomes:**  
> By the end of the course, learners will be able to:
>
> 1. Define what ..... [Remembering] 
>
> 2. Discuss and explain ..... [Understanding] 
>
> 3. Apply and modify ..... [Applying] 
>
> 4. Compare ..... [Analysing] 
>
> 5. Evaluate and select ..... [Evaluating] 
>
> 6. Create and integrate ..... [Creating]
>
>> Check more about [Bloom's taxonomy](https://cft.vanderbilt.edu/guides-sub-pages/blooms-taxonomy/) to categorize the levels in educational goals
>
> <i class="fa fa-hourglass"></i> **Time estimation**: 120 minutes
>
> <i class="fa fa-asterisk"></i> **Requirements:** The (technical) installation requirements are described in the [installations](https://vibbits-nextflow-workshop.readthedocs.io/en/latest/installations.html) section.
>
> <i class="fa fa-envelope-open-text"></i> **Supporting Materials**:
> 
> 1. [Exercises and solutions](link)
> 2. [Slides](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/training_material_template/refs/heads/main/supplementary/chapter_01_presentation.md)  
> 
> <i class="fa fa-life-ring"></i> **Acknowledgement**:
>
> * [ELIXIR Belgium](https://www.elixir-belgium.org/)
> * [VIB Technologies](https://www.vib.be/)
>
> <i class="fa fa-money-bill"></i> **Funding:** This project has received funding from the ELIXIR Programme 2022-2023.
>
> <i class="fa fa-anchor"></i> **PURL**:  


# Authors and Contributors

Authors

- @[orcid(Alexander Botxki)](https://orcid.org/0000-0001-6691-4233) 
- @[orcid(Bruna Piereck)](https://orcid.org/0000-0001-5958-0669) 
- @[orcid(James Collier)](https://orcid.org/0000-0002-0020-421X) 
- @[orcid(Tuur Muyldermans)](https://orcid.org/0000-0002-3926-7293) 

## Citing this lesson

Please cite as:

  1. ... (to be updated soon)

# Chapters List

| Chapter | Title                                                   |
| :---- | :------------------------------------------------         |
| 0     | [Get ready for the course, instalation and pre-reading](link) |
| 1     | [Chapter title](link)                                             |
| 2     | [Chapter title](link)                                             |
| 3     | [Chapter title](link)                                             |


# References

Here are some great tips for learning and to get inspired for writing your own pipelines:

- Nextflow's official documentation ([link](https://www.nextflow.io/docs/latest/index.html))
- Reach out to the community on Slack ([link](https://www.nextflow.io/slack-invite.html))
- Curated collection of patterns ([link](https://github.com/nextflow-io/patterns))
- Workshop focused on DSL2 developed by CRG Bioinformatics Core ([link](https://github.com/biocorecrg/ELIXIR_containers_nextflow))
- Tutorial exercises (DSL1) developed by Seqera ([link](https://github.com/seqeralabs/nextflow-tutorial))
- Curated ready-to-use analysis pipelines by NF-core ([link](https://nf-co.re/))
- Model example pipeline on Variant Calling Analysis with NGS RNA-Seq data developed by CRG ([link](https://github.com/CRG-CNAG/CalliNGS-NF))
- Tutorial by Andrew Severin ([link](https://bioinformaticsworkbook.org/dataAnalysis/nextflow/02_creatingAworkflow.html#gsc.tab=0))
- Nextflow community basic training ([link](https://training.nextflow.io/basic_training/))

# About us

*About ELIXIR Training Platform*

The ELIXIR Training Platform was established to develop a training community that spans all ELIXIR member states (see the list of Training Coordinators). It aims to strengthen national training programmes, grow bioinformatics training capacity and competence across Europe, and empower researchers to use ELIXIR's services and tools.

One service offered by the Training Platform is TeSS, the training registry for the ELIXIR community. Together with ELIXIR France and ELIXIR Slovenia, VIB as lead node for ELIXIR Belgium is engaged in consolidating quality and impact of the TeSS training resources (2022-23) (https://elixir-europe.org/internal-projects/commissioned-services/2022-trp3).

The Training eSupport System was developed to help trainees, trainers and their institutions to have a one-stop shop where they can share and find information about training and events, including training material. This way we can create a catalogue that can be shared within the community. How it works is what we are going to find out in this course.

*About VIB and VIB Technologies*

VIB is an entrepreneurial non-profit research institute, with a clear focus on groundbreaking strategic basic research in life sciences and operates in close partnership with the five universities in Flanders – Ghent University, KU Leuven, University of Antwerp, Vrije Universiteit Brussel and Hasselt University.

As part of the VIB Technologies, the 12 VIB Core Facilities, provide support in a wide array of research fields and housing specialized scientific equipment for each discipline. Science and technology go hand in hand. New technologies advance science and often accelerate breakthroughs in scientific research. VIB has a visionary approach to science and technology, founded on its ability to identify and foster new innovations in life sciences.

The goal of VIB Technology Training is to up-skill life scientists to excel in the domains of VIB Technologies, Bioinformatics & AI, Software Development, and Research Data Management.

--------------------------------------------

*Editorial team for this course*

Authors: @[orcid(Alexander Botzki)](https://orcid.org/0000-0001-6691-4233), @[orcid(Bruna Piereck)](https://orcid.org/0000-0001-5958-0669)

Technical Editors: Alexander Botzki

License: [![CC BY SA](img/picture003.jpg)](https://creativecommons.org/licenses/by-sa/4.0/deed.en)

```json   @JSONLD
{
  "@context": "https://schema.org/",
  "@type": "LearningResource",
  "@id": "https://elixir-europe-training.github.io/ELIXIR-TrP-TeSS/",
  "http://purl.org/dc/terms/conformsTo": {
    "@type": "CreativeWork",
    "@id": "https://bioschemas.org/profiles/TrainingMaterial/1.0-RELEASE"
  },
  "description": "TeSS, how can I help you? This is our interactive hands-on course about efficient use of the ELIXIR TeSS platform.",
  "keywords": "FAIR, OPEN, Bioinformatics, Teaching, TeSS",
  "name": "TeSS, how can I help you?",
  "license": "https://creativecommons.org/licenses/by/4.0/",
  "educationalLevel": "beginner",
  "competencyRequired": "none",
  "teaches": [
    "search events and material in TeSS via direct and faceted search",
    "add manually and automatically events and material to TeSS",
    "extract events and material from TeSS by using TeSS widgets"
  ],
  "audience": "training providers",
  "inLanguage": "en-US",
  "learningResourceType": [
    "tutorial"
  ],
  "author": [
    {
      "@type": "Person",
      "name": "Bruna Piereck"
    },
    {
      "@type": "Person",
      "name": "Olivier Sand"
    },
    {
      "@type": "Person",
      "name": "Alexander Botzki"
    }
  ],
  "contributor": [
    {
      "@type": "Person",
      "name": "Yasmine Maes"
    },
    {
      "@type": "Person",
      "name": "Finn Bacall"
    },
    {
      "@type": "Person",
      "name": "Munazah Andrabi"
    }
  ]
}
```












# Introduction to Git & GitHub
## About this course
## Material license
## Contributors
## Get ready for the course

#### 1. BEFORE THE COURSE 

If you don’t have experience with command line it is ***essential*** that you follow a quick course since this skills are very important to be able to use git and GitHub.

To not get lost during the course start the crash course [***Introduction to Linux command line***](https://elearning.vib.be/courses/linux/) on [VIB e-learnign](https://elearning.vib.be/) system.

#### 2. GET YOUR COMPUTER READY

For this course we are going to use some tools, some are mandatory some are sugestions that we believe can possibly make your experience better and the didatics more simple. You can find the detailes instructions for **any operating system*** in our [Get Ready chapter](https://liascript.github.io/course/?https://raw.githubusercontent.com/vibbits/introduction-github/master/tutorials/1_Get_ready_for_the_course/tutorial.md#1). 

Summary of what you might need:
- WSL with GitBash (for windowns users)
- Git installed in your terminal (MAC & Linux)
- MarkText (Editor Sugestion - MarkDown)
- Ungit (Visualization tool - NOT mandatory)

## Program




## Learning Outcomes

1. Enumerate the primary purpose and advantages of Git in version control. [Knowledge] 

2. Identify and name the difference between Git and GitHub. [Knowledge] 

3. Explain the differences between branches and forks and their use cases. [Knowledge] 

4. Describe and Distinguish between the development area, staging area, local and remote repositories. [Knowledge and Comprehension] 

5. Explain the importance of commit messages and their role in tracking changes. [Comprehension] 

6. Discuss the significance of staging changes before committing it. [Comprehension] 

7. Apply the key steps in Git routine, including staging, committing changes to update the working tree. [Application] 

8. Illustrate the purpose and use of branches in Git for testing new features and collaborations. [Comprehension and Application] 

9. Use the Git commands to share changes from local to remote repository and vice versa. [Application] 

10. Create a new repository on GitHub, clone it locally, make edits, and push changes back to GitHub. [Application] 

11. Be able to clone a GitHub repository locally and perform edits. [Application] 

12. Evaluate the impact of well-crafted `commit` messages on project documentation and collaboration. [Analysis] 

13. Analyse the benefits and challenges of using branches in Git for project development. [Analysis] 

14. To use commands to check the status and unique ID's of content modificaitons. [Application]

## Complementary reading (Tutorials)

Check some [**chapters**](https://liascript.github.io/course/?https://raw.githubusercontent.com/vibbits/introduction-github/master/tutorials/Git_modules.md#1) with complementary reading.

You will *review* what you saw in the course and get *some extra* tips and information, such as using Rstudio on GitHub.
