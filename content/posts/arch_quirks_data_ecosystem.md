---
title: "Architectural Quirks of the Data Ecosystem"
date: 2022-07-16T11:42:43+10:00
draft: true
toc: true
tags:
    - data engineering
    - data science
    - tooling
---

# Architectural Quirks of the Data Ecosystem


## Introduction + Background

Within the data-{engineering, science, analysis} space, there's a fairly well known set of mainstream tools and languages and I am interested in pulling apart the component pieces and taking a hard look at _why_ they exist, and whether we should be using them in the future.<!--more__>
I am of the opinion that a huge chunk of this space is vastly overcomplicated - an issue driven by 2 main factors:
* companies with a vested interest in making the entire space seem as complicated and involved as possible, thus justifying their existence and usage.

and

* hype / resume driven developement. An affliction that affects the whole development community, and manifests in the data space as what I would characterise as "scale driven development". Unsurprisingly, everyone _wants_ to work on data that's just "so big" that you need huge, multi-node spark clusters, 100's of TB of database + S3 storage, clusters of query engines, scalable streaming processors, etc etc.

These factors combine to feed into more serious issues, which I'll discuss below, but first, let's look at what the common components are, why we'd use them and where the issues come into play.

## Languages
First up, let's have a look at the primary languages in use:
* Python
* SQL
* Spark-Scala
* Lesser used languages - R

Python basically has a strangehold on the data space. What this means will be covered later.  
SQL sees a huge amount of use as well - unsurprising given its widespread use within databases, it's theoretical basis in relational-algebra and it's syntactical simplicty.  
Scala saw an explosion of popularity within the space - it's functional programming background and strong type system brought a bit of a sea-change to the JVM landscape, and quite a few data-engineering and data science tools/frameworks were/are written in it (notably Spark). 