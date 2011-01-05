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

To begin with, a resource is simply a thing. 

This will sound rather abstract, which is ultimately the point. A user account can be a resource, and so can a specific file, a software package, a running service, or a scheduled cron job. Even a single invocation of a shell command can be a resource.

Each of these individual things is very similar to a class of related things: any given file will have a path and an owner; any given user will have a name and an ID and a group. Which is to say: _similar resources can be grouped into types._

regardless of your OS or filesystem,

What ties these disparate things together is that each of them belongs to an abstracted class of similar things: A user account on Mac OS X is implemented differently than a user account on Solaris or Ubuntu or Fedora Core, but they all have common properties, such as a user name, a user ID, one or more groups, a password, etcetera. Regardless of the filesystem a given OS uses, files on it will still have paths, owners, and permission modes. Puppet 





Every resource belongs to a type, 