
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
Tighten your sitbelts to enjoying some time-travel analogy to understand how Git works, how you can connect it to GitHub and how this will help you with your version control and potentially impact your publication.

We will introduce you to this free and open source distributed version-control system designed to maintain, track changes, recover old versions and collaborate with other while developing your code and documentation. 

## Proposed Schedule

Schedule day 1:

09h30 - Configurations & Introduction 
11h00 - Coffee break  
11h15 - Routine usage part 1 (status-stage-commit) 
13h00 - Lunch 
14h00 - History & Comparing Versions 
14h40 - Coffee break   
14h55 - Collaborating in GitHub  
17h00 - End of the day  

Schedule day 2:

09h30 - Solving Conflicts 
10h30 - Coffee break 
10h30 - Experimenting Risk Free: Working with Branchs
12h30 - Lunch 
13h00 - Tagging & Forking  
15h00 - Coffee break 
15h00 - Using the browser 
17h00 - End of the day 

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
- @[orcid(Tuur Muyldermans)](http://orcid.org/0000-0002-3926-7293)
- @[orcid(James Collier)](http://orcid.org/0000-0002-0020-421X)
- @[orcid(Alexander Botxki)](http://orcid.org/0000-0001-6691-4233)

## Citing this lesson

Please cite as:

  1. to be added soon ...

# Chapters List

| Chapter | Title                                                           |
| :---- | :------------------------------------------------                 |
| 0     | [Chapters summary render](https://liascript.github.io/course/?https://raw.githubusercontent.com/vibbits/introduction-github/master/tutorials/Git_modules.md#1)    |
| 1     | [Get Ready](./docs/tutorials/1_Get_ready_for_the_course/)         |
| 2     | [Inroduction](./docs/tutorials/2_introduction/)                   |
| 3     | [Getting started](./docs/tutorials/3_getting_started/)            |
| 4     | [Time travel](./docs/tutorials/4_time-travel_my_versions/)        |
| 5     | [From git to GitHub](./docs/tutorials/5_Connecting_2_GitHub/)     |
| 6     | [.gitingore & README files](./docs/tutorials/6_gitignore&README/) |
| 7     | [Collaborating](./docs/tutorials/7_collaborating_GitHub/)         |
| 8     | [Branchs](./docs/tutorials/8_branches/)                           |
| 9     | [Forks](./docs/tutorials/9_forks/)                                |
| 10    | [Git aliases](./docs/tutorials/10_Git_aliases/)                   |
| 11    | [GitHub & Rstudio](./docs/tutorials/11_github_rstudio/)           |
