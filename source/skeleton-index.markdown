Puppet Labs Documentation
=========================

Welcome to the Puppet Labs documentation site. 

* * * 

NOTE: You can find the Marionette Collective documentation [here](./mcollective/index.html).

Outline with comments from tech [here](https://docs.google.com/a/puppetlabs.com/document/d/1_OAhZImvuK_1bbhVrbl9gTY3dy6AEP3fAK6hHqbnXEI/edit?hl=en#).

Learning Puppet
-----

New users start here.

* Introduction 
    * What Puppet is
    * Installing and setting up Puppet
* Resources and the RAL
    * RAL concepts
    * ralsh exercises
    * Introduction to a few resource types
        * namevars
        * Link to the resource type references and brief digression on how to read the references
* Manifests and the Puppet DSL
    * puppet apply
    * Resource declarations
    * Resource relationships
    * Variables/arrays/conditionals
    * Scope
    * Classes (basic version)
        * Not at all like an OO programming class; more like a role. 
        * Nodes are composed of classes.
        * `include some_class` == `class { some_class: }`; this gets important later, so get used to telling the difference between outside-the-curlies and inside-the-curlies now. 
    * Code style
* Interlude: beginning exercises
    * Implement a package/file/service pattern and apply it. 
    * (More later)
* Client/server Puppet
    * master and agent
    * What happens where?
        * facter
        * catalog compilation
        * applying compiled catalogs
        * ???
    * HTTP and SSL overview
        * (This will be brief, but I want to be able to say "this is what makes it work; there, now it's not magic and you know how to find out more once you actually need to.")
    * Puppet ca 
        * Links to troubleshooting info for the inevitable cert issues, including info on what needs to be done with certs when you're scaling to a non-WEBrick web server. 
    * Up-and-running walkthrough
        * Start the master. Point the agent at the master and run with --test. Puppet cert --sign. Start the agent with --test again. Start the agent for real. 
        * Apply a test manifest.
    * Here is your stethoscope, set of hexdrivers, and squirrel tenderizer
        * --configprint
        * --test and --verbose and --debug and --no-daemonize and --noop and --onetime
        * log files and messages
        * links to troubleshooting docs
* The shape of a real puppet site
    * site.pp (`puppet master --configprint manifest`)
        * mention external node classifiers, without going into too much detail.
    * Modules
        * Thou shalt use modules for damn well everything.
        * Classes (more complete version)
        * Module structure 
        * Module autoloading 
            * foo           -> modules/foo/manifests/init.pp
            * foo::bar      -> modules/foo/manifests/bar.pp
            * foo::bar::fog -> modules/foo/manifests/bar/fog.pp
        * moduletool
        * forge
        * Tying it together: composing nodes using classes from modules
    * File serving (via modules)
    * Templates (via modules)
* Interlude: intermediate exercises
    * Make a hello world module
    * Make multiple modules and apply them to different nodes.
    * Download, use, and extend a public module
    * (More later)
* Completing the basic skill set
    * Parameterized classes
    * Defined resource types
    * tags
    * Custom facts
    * Custom functions
    * Virtual resources
        * Mention the existence of exported resources
* Controlling the big picture
    * Reports
    * Environments
    * Storeconfigs
    * exported resources
    * External node classifiers
    * puppet dashboard
        * installing
        * as a report tool
        * as a node classifier
* Testing out: advanced exercises
    * (Don't know yet.)
* Branching paths
    * All the other guides can be approached in any order. Provide some quick suggestions for starting points and we're done. 





Tasks and Techniques
-----

Once you've learned how to use Puppet, explore here to learn about common tasks and use cases. 

* Readying Your puppet master For Production -- Your absolute first step once you're ready to deploy Puppet for real. 
    * Passenger
    * Unicorn and Nginx
    * Mongrel cluster with load-balancer



Reference Library
-----

The dog-eared notebook of the experienced user.

