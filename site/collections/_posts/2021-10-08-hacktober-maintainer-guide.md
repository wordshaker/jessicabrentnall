---
layout: post
title: Maintaining Repositories During Hacktober
description: "A guide to maintaining repositories during Hacktoberfest 2021"
date: 2021-10-08
image: "/images/posts/2021/10-08.jpg"
tags: ["2021"]
---

---

<center>
<h3> A quick guide to maintaining repositories during Hacktober. </h3>
</center>

---

<br/>

<h2>Quick Links:</h2>

- [Repository Setup](#repository-setup)
  - [What To Do To Opt-In To Hacktober](#what-to-do-to-opt-in-to-hacktober)
  - [How To Mark Un-helpful Contributions](#how-to-mark-un-helpful-contributions)
  - [In Built Guidance](#in-built-guidance)
  - [GitHub Templates](#github-templates)
  - [Branch Protection](#branch-protection)
  - [Setting up CI and CD](#setting-up-ci-and-cd)
- [What I've learnt as a maintainer](#what-ive-learnt-as-a-maintainer)
  - [Use the right licence](#use-the-right-licence)
  - [Have a Code Of Conduct in place](#have-a-code-of-conduct-in-place)
  - [Have a cracking README](#have-a-cracking-README)
  - [Contribution Guidelines](#contribution-guidelines)
  - [Avoiding PR clashes](#avoiding-pr-clashes)
  - [Advantages to the above documentation](#advantages-to-the-above-documentation)
    - [Maintaining consistency](#maintaining-consistency)
    - [Transparency](#transparency)
- [Issues and Correspondence](#issues-and-correspondence)
  - [The many types of contribution](#the-many-types-of-contribution)
  - [Tone of voice](#tone-of-voice)
- [In Conclusion](#in-conclusion)

<br/>

It's that most wonderful time of the year again! <a href="https://Hacktoberfest.digitalocean.com/" target="_blank">Hacktoberfest</a> takes place for the whole of October with the aim of encouraging people to contribute to Open Source. If you have some open source repositories you'd like to encourage contributions to, there are a few things you can do to make the experience better for you, and the people interacting with your repository.

This post is a guide to some of the things I've learnt while looking after open repositories.

<br/>

## Repository Setup

In previous years, Hacktoberfest has been a time of horror for repository maintainers. It's been a month of weeding out the valuable contributions from those where people have deleted one random bit of white space in the aim of getting a t-shirt.

To protect against this, the rules of Hacktober have tightened to make it possible for you to opt into the experience as a maintainer.

### What To Do To Opt-In To Hacktober

To opt your repository into Hacktoberfest do **EITHER** of the following.

**1. Add `Hacktoberfest` to the repositories topic**

On the main page of your repository add _Hacktoberfest_ as a topic tag. See the image below to see where this is editable.

<br/>
<div style="text-align:center; width:80%; margin-left: 10%;" markdown="1">
<img src="{{site.baseurl}}/images/posts/2021/10-08/topic.png" alt="Screen shot of the GitHub Topic section.">
</div>
<br/>

**2. Add a `Hacktoberfest-accepted` label**

Add a _Hacktoberfest-accepted_ label which can be applied to approved issues or pull requests in your repository.

<br/>
<div style="text-align:center; width:80%; margin-left: 10%;" markdown="1">
<img src="{{site.baseurl}}/images/posts/2021/10-08/label.png" alt="Screen shot of the Hacktoberfest-accepted label in GitHub.">
</div>
<br/>

### How To Mark Un-helpful Contributions

To ensure spam pull requests aren't counted as a Hacktoberfest contribution just as much as you, so please give them an `invalid` or `spam` label and close them. Pull requests that these labels won’t be counted toward Hacktoberfest.

<br/>
<div style="text-align:center; width:80%; margin-left: 10%;" markdown="1">
<img src="{{site.baseurl}}/images/posts/2021/10-08/spam.png" alt="Screen shot of the spam label in GitHub.">
</div>
<br/>

### In Built Guidance

A lot of the items mentioned in this section are listed in the Community Profile listed in GitHub. To see this, head to your repository and click on `Insights` > `Community`.

<br/>
<div style="text-align:center; width:80%; margin-left: 10%;" markdown="1">
<img src="{{site.baseurl}}/images/posts/2021/10-08/community.png" alt="Screen shot of the GitHub Community Profile page.">
</div>
<br/>

<br/>

### GitHub Templates

Adding <a href="https://docs.github.com/en/free-pro-team@latest/github/building-a-strong-community/about-issue-and-pull-request-templates" target="_blank">issue and pull request templates</a> to your repository helps ensure that all Pull Requests and Issues are consistent and contain the information needed.

You can outline headings and put down some description of what you would like those contributing to put under each heading. For example, in the Pull Request template for the repositories I co-manage, we ask for a list of changes, test evidence of them working and links to relevant issues.

There is also the opportunity to create different templates for different scenarios. For example, on one of the repositories I co-manage we have separate templates for Bug Report Issues versus Feature Requests. These two types of issues require different information, so separating them was useful to us and our community.

Instructions for how to set up these templates can be found <a href="https://docs.github.com/en/free-pro-team@latest/github/building-a-strong-community/about-issue-and-pull-request-templates" target="_blank">here.</a>

### Branch Protection

In the Settings of the GitHub repository as a maintainer you can protect your branches under a number of criteria. You can set it up so that pull requests can't be merged without build checks passing, reviews from certain people or a set number of reviews or certain Code Owners.

You can set up any CI workflows/scripts as a required check. As part of the repositories I maintain I include checks for passing tests, security scans and linter checks.

These rules ensure that unwanted changes can't be merged into your main branch and that changes match the quality and needs you expect in your project.

<br/>

### Setting up CI and CD

Closely related to the above, for pull requests and deployments, you can set up builds and test runs to check that the builds and tests haven't failed on any changes made.

There are a variety of tools available. In the repositories I co-manage we are using GitHub actions with steps for the various different checks mentioned in the previous section.

Repositories can also be set up to deploy when changes are merged into the main branch. This stops any unnecessary manual effort.

<br/>

## What I've learnt as a maintainer

The next sections explore at a high level, what I have learnt about as a maintainer. Maintaining a repository during Hacktober exercised a number of skills. I needed to be able to reviews peoples contributions, and make the comments and suggestions suitable for a range of experiences and abilities. Communication was a big part throughout all of this, from managing issues to communicating with contributors. With Hacktober only taking place over October, there was also the lesson in time management and timeliness; ensuring that the repositories were being checking on a near daily basis.

<br/>

### Use the right licence

Licencing is a tricky topic, but as a maintainer you need to ensure a licence is in place for the code you are caring for. There are many resources on this topic including the documentation <a href="https://opensource.org/licenses" target="_blank">on the OpenSource.Org Website.</a>

I'd highly recommend watching <a href="https://www.youtube.com/watch?v=OV94p_kB-Lg" target="_blank">this talk by Jeff Strauss titled - What You Need to Know About Open Source—Trust Me, I’m a Lawyer</a>. I've watched this talk 3 times in person, back when we could watch talks in person. Jeff clearly talks through the different types of licence, what they mean and how they impact you as a code owner. It's an interesting topic and not one I had considered before seeing Jeff speak.

Not only does this enforce how your software can be used, but also many contributors will avoid contributing to repositories that don't have a licence.

<br/>

### Have a Code Of Conduct in place

The Code of Conduct is for maintainers as well as contributors. Having a code of conduct makes it clear what behaviour and language is expected of all those taking part in the repository. It also states what will happen if anyone behaves in a way that is not allowable by the maintainers.

This means all those contributing are pre-warned to the consequences of actions that make others feel targeted, uncomfortable or abused. If anyone is made to feel unsafe, there are instructions for how to report the behaviour that has made them feel that way.

All in all this document helps provide the information necessary to try to preserve a good culture in the repositories you are maintaining and make sure that everyone taking part has a good experience.

The trickiest bit in my point of view is having a plan in place for if any code of conduct issues do arise. What will you do as a maintainer if someone is abusive or inappropriate in the space of the repository you manage? What will the repercussions to be to the person who is breaking the code of conduct? Can a person report behaviour in a safe and, potentially, confidential way? An occurrence like this is rare, but it is best to be prepared, just in case you do have to deal with it.

<br/>

### Have a cracking README

The README is the first thing I look at when going to a repository. As such it is a fantastic place, in my view, to link to any resources and give guidance on how to work with the repository. Some of the things I found useful to have in the README include:

- #### Build badge

  In the README we have a build badge for our main branch. This easily shows if the main branch is in a good state.

- #### Links to other markdown files

  As the README is the first place a lot of people look for information, we found it useful to have links to the other files including the Contribution Guidelines and Code of Conduct.

- #### Instructions on how to build the project locally

  When a developer is working on your repository they will often want to build your project locally while they are working on it. Especially for those unfamiliar with your project, instructions on how to do this are useful. This also means manual tests and evidence of change can be attached to the Pull Request.

- #### Instructions on how to test the project locally

  Again, contributors will often want to test their changes and ensure they haven't had unexpected impacts on your project. Instructions for how to run tests locally, not only means they won't rely on the build to see if these tests work, but also means they can take screen shots for evidence on their PR.

- #### Branding information
  If there are any branding guidelines, such as fonts or colour schemes it's often useful. As the majority of the repositories I maintain are websites, I've found this information is useful for contributing developers and designers alike.

<br/>

### Contribution Guidelines

These guidelines inform contributors what they need to do to make changes to the repository. Some of the sections we found useful include:

- #### Instructions for picking up work

  As there may be multiple people wanting to work on the same issues, it's useful to have instructions for what to do when someone wants to pick up work, and how the contributor will be selected when multiple people want to work on the same issue. How does one indicate their interest? At what point can they submit their work on their issue? How will it be communicated that they can pick up a piece of work?

- #### PR Guidelines
  This is assisted with some of the automation available which is outlined later, such as PR templates and Code Owner files. You may want to add information in your guidelines though if there is a particular PR workflow you want people to adhere to. This can also include what labels used for PRs in different statuses and what is required to have a PR approved and merged.
- #### Branching guidelines

  How do you want people to branch from your project? Branch directly? Fork the repository? It can also be useful to link to resources for beginners. Also, is there a naming style for branches you would like contributors to conform to?

- #### Issue raising guidelines
  Again, so that your contributors have visibility of what to do, it can be useful to have a section on what to do when creating an issue. For the repositories I work on, we use this section to outline the different types of issues and their purpose, the level of information required and how to link to pre-existing issues.
- #### Link to the code of conduct
  Might seem like I've put this everywhere, but the Code of Conduct is inherently linked to contributing. This is a light reminder that if you are considering working on a repository, all contributors need to behave in a way that aligns to the Code of Conduct.

Instructions for <a href="https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/setting-guidelines-for-repository-contributors" target="_blank">how to set up a contribution.md can be found here.</a>

<br/>

### Avoiding PR clashes

Tracking suggested changes can be done using Issues. For the repositories I look after I ask that a person is assigned to an existing issue or an that a new issue is raised. Once a maintainer has assigned the change to them, then they can raise a pull request. This worked on a "first-come-first-served" basis. In the contribution guidelines, state how long an issue can be assigned to a person before it can be reassigned to someone new. This is indicated by un-assigning the issue and adding in labels again such as `help wanted` and removing `in progress` labels.

The reason for this is you may have a number of pull requests being raised for the same issue from numerous people. This provides a fair way to decide who's changes went through, and to be transparent about what this process was.

<br/>

### Advantages to the above documentation

#### Maintaining consistency

By documenting how you want individuals to contribute to your repository, it increases the changes that there will be consistency between the different contributions the repository received. This can include things like branch name structure, whether you want contributors to fork the repository opposed to branching straight from the main repository or if you want any evidence of changes. Overall, this will help with the maintainability of the repository and for multiple people working on the code to understand it.

#### Transparency

Being transparent about the work available in the repository, expected behaviours of those contributing and how to work on the repository will make it a better experience for contributors and fellow maintainers. It reduces the risk of misunderstandings and keeps all involved in the project informed.

<br/>

## Issues and Correspondence

Communication is a key part in managing a repository. How you communicate with your contributors and community is important not only for ensuring people have everything they need for successfully contributing, but also building the culture of your space.

<br/>

### The many types of contribution

There are lots of different types of contribution that can be made to a repository including:

- Bug fixes
- Feature contributions
- Designs
- Adding tests
- Accessibility testing and checks
- UI and UX assessments

In the contribution guidelines it is good to be clear how these changes can be made.

It's also worth keeping in mind, contributors can come in many forms. Not only will contributors vary in experience and know-how, but they will also differ in profession. Open Source is not just for developers, let alone being restricted to certain types of developer. Make the most out of the opportunity to get contributions from designers, user-researchers, technical documentation experts and more.

<br/>

### Tone of voice

When taking care of a repository you need to determine your tone of voice when talking to contributors. Make sure its constructive, and not unkind.

Your tone of voice determines the culture of the repository as a whole. The maintainers are the example for what communications and behaviours should look like.

If you have multiple maintainers on a project, have a discussion about what you want as your tone of voice for the project, so that you are consistent with all your messaging.

<br/>

## In Conclusion

This is not a fully comprehensive list of all that is involved in being a maintainer. It's a lot of work and a time commitment (so I would recommend getting some co-maintainers to help if you can). Hopefully this starter for ten might help someone starting with maintaining and repository.

_Stay Safe,_

_Jess_

---

<div style="text-align:center" markdown="1">
<img src="{{site.baseurl}}/images/logo.png" alt="Logo">
</div>
