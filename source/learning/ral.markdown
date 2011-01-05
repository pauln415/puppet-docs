---
layout: default
title: Learning: Resources and the Resource Abstraction Layer
---

Learning: Resources and the Resource Abstraction Layer
=====

Resources are the building blocks of Puppet, and the division of resources into types and providers is what gives the Puppet language its power. 

* * * 

Atoms and Abstraction
-----

Think of a system's configuration as being composed of a number of individual atoms; call them "**resources.**" These discrete pieces can vary in size, complexity, and lifetime: a user account can be a resource, as can a specific file, a software package, a running service, or a scheduled cron job. Even a single invocation of a shell command can be a resource.

Each of these individual things is very similar to a class of related things: any given file will have a path and an owner, and any given user will have a name, an ID, and a group. Which is to say: _similar resources can be grouped into types._ Furthermore, the most important attributes of a resource type are usually conceptually identical across operating systems, regardless of how the implementations differ. Which is to say: _the description of a resource can be abstracted away from its implementation._ 

These two insights form Puppet's resource abstraction layer (RAL). The RAL splits resources into **types** (high-level models) and **providers** (platform-specific implementations), and lets you declare resources -- instances of a resource type -- in a way that can be applied to any system. 






