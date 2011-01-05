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
    * [What Puppet is](guides/introduction.html) **Needs revision, needs new diagrams.**
    * [Installing and setting up Puppet](guides/installation.html)
        * [Supported platforms](guides/platforms.html) **Need to qualify statement of Windows support, since it's still way shaky.**
        * [Setting up](guides/configuring.html) **needs to be shrunk and revised; some of these instructions are irrelevant until the user has a better grasp of client/server puppet.**
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
    * [Code style](guides/style.html) *Although this doc needs to be prominent in the refs section, too. Duplicate this one instead of replacing it.* 
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
    * [Modules](guides/modules.html) **Needs a rewrite.**
        * Thou shalt use modules for damn well everything.
        * Classes (more complete version)
        * [Module structure](guides/modules.html) **Needs a rewrite.**
        * [Module autoloading](guides/plugins_in_modules.html)  *sort of.*
            * foo           -> modules/foo/manifests/init.pp
            * foo::bar      -> modules/foo/manifests/bar.pp
            * foo::bar::fog -> modules/foo/manifests/bar/fog.pp
        * moduletool
        * forge
        * Tying it together: composing nodes using classes from modules
    * [File serving](guides/file_serving.html) (via modules) *Could use a rewrite; this was where I first started grappling with module autoloading, and it's not as important as some of the other parts of the system.*
    * [Templates](guides/templating.html) (via modules) *Looking pretty good; will want revision once we have the surrounding text written.*
* Interlude: intermediate exercises
    * Make a hello world module
    * Make multiple modules and apply them to different nodes.
    * Download, use, and extend a public module
    * (More later)
* Completing the basic skill set
    * tags
    * Parameterized classes 
    * Defined resource types **The current best info on these is in guides/language tutorial.**
    * [Custom facts](guides/custom_facts.html) *status: ???*
    * [Custom functions](guides/custom_functions.html) *status: ???*
    * [Virtual resources](guides/virtual_resources.html) *Doing okay, could use better integration with the surroundings. Should this material be mentioned earlier?*
        * Mention the existence of exported resources
* Controlling the big picture
    * [Reports](guides/reporting.html) *status unknown. To me, at least.*
    * [Environments](guides/environment.html) *May have outdated info at the bottom.*
    * Storeconfigs **Missing completely.**
    * [exported resources](guides/exported_resources.html) *unrevised*
    * [External node classifiers](guides/external_nodes.html) *unrevised*
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



Orphaned Docs
========

Existing docs files that don't have a new home yet. 

* `best_practices.markdown`
* `complete_resource_example.markdown`
* `custom_types.markdown`
* `development_lifecycle.markdown`
* `faq.markdown`
* `from_source.markdown`
* `installing_dashboard.markdown`
* `language_tutorial.markdown`
* `mongrel.markdown`
* `passenger.markdown`
* `provider_development.markdown`
* `rest_api.markdown`
* `scaling.markdown`
* `security.markdown`
* `techniques.markdown`
* `tools.markdown`
* `troubleshooting.markdown`
* `types`
* `using_dashboard.markdown`
