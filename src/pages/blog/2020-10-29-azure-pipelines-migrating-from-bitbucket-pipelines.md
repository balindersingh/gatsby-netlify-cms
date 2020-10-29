---
templateKey: blog-post
title: Azure pipelines- Migrating from bitbucket pipelines
date: 2020-10-29T01:10:27.024Z
description: In my last post, I shared some challenges I faced running selenium
  in bitbucket and how to fix those. In this post, I will be sharing few getting
  started tips about Azure Pipelines (product in Azure Devops) and what
  encouraged me to move from bitbucket pipeline to Azure pipeline. I won’t be
  sharing much of code or any 1–1 comparison between these two services but more
  of high level pain points or I would say implementation/project specific
  points which are better handled in Azure Devops space.
featuredpost: true
featuredimage: /img/pipe.png
tags:
  - bitbucket
  - azure devops
---
I am going to focus on Bitbucket pipeline and Azure Pipelines. Bitbucket repository, JIRA boards or Confluence and its alternatives in Azure Devops is topic for another day.

* First and foremost is Windows image support for builds. I primarily work with Microsoft stack and Salesforce. One of the limitations with Microsoft stack, more precisely, with .Net Full framework (legacy/original whatever) is, it needs Windows environment for its builds. Unfortunately bitbucket doesn’t have support for windows image yet. Although you can kick off some hooks from pipeline on your hosted machine somewhere and can get things done. Bonus point: in Azure pipelines you can have both windows and linux/unix based images in single pipeline. See sample code link in resources.
* There is a lot of out-of-the-box plugins/marketplace extensions available which you can easily plugin to your pipeline tasks. It comes very handy. Bitbucket also have concept of *pipes* which is quite similar but I personally found Azure Devops has bigger/better library of common tasks.
* Easy UI version of pipeline to get started easily for beginners. Although I mostly work with yaml but it is good to have this option I think.
* Manual gates for approval between stages is pretty awesome. I didn’t explore much about it in bitbucket if they have it any functionality like that but in Azure it is way easier to setup with Azure Devops Releases.
* Last but not least, the documentation makes life lot easier and Azure devops has plenty of it and very well organized.