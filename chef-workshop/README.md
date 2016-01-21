# Chef Training

## Details
**Date:** 2015-01-21<br />
**Time:** 10:00am - 5:00pm<br />
**Location:** Pasadena Convention Center (Room 103)<br />

Chef Website<br />
[https://www.chef.com](https://www.chef.com)

Chef Documentation<br />
[https://docs.chef.io](https://docs.chef.io)

## Definitions

### Resource

In a Chef recipe, a resource is something that exists on a system alone with its state.

A service to be started, a package to be installed, or a user to be created are all examples of resources.

[https://docs.chef.io/resources.html](https://docs.chef.io/resources.html)

### Cookbook

A Chef cookbook is the fundamental unit of configuration and policy distribution

## Commands

### chef
An executable programs that allows to execute cookbooks

#### Examples

help menu

`chef --help`

Help on generate function

`chef generate --help`

Help on generate cookbook

`chef generate cookbook --help`

Generate a cookbook

`chef generate cookbook COOKBOOK_NAME`

```
# Creates the below structure

workstation/
├── Berksfile
├── chefignore
├── metadata.rb
├── README.md
├── recipes
│   └── default.rb
├── spec
│   ├── spec_helper.rb
│   └── unit
│       └── recipes
│           └── default_spec.rb
└── test
    └── integration
        ├── default
        │   └── serverspec
        │       └── default_spec.rb
        └── helpers
            └── serverspec
                └── spec_helper.rb
```


### chef-apply
chef-apply is an executable program that runs a single recipe from the command line:

- Is part of the Chef development kit
- A great way to explore resources
- Is NOT how Chef is run in production

#### Examples

Help menu for chef-apply

`sudo chef-apply --help`

Install a package

`sudo chef-apply -e "package 'nano'"`

Apply a recipe file

`sudo chef-apply hello.rb`



### chef-client
Appying Recipes from Cookbooks

chef-client is an agent that runs locally on every node that is under management by Chef.

When a chef-client is run, it will perform all of the steps that are required to bring the node into the expected state.

### Examples

Apply local recipe

`sudo chef-client --local-mode -r "recipe[workstation::setup]"`

Apply multiple local recipes

```
sudo chef-client --local-mode -r \
    "recipe[workstation::setup], recipe[apache::server]"
```

## Testing
What are we running in production? Maybe I could test the cookbook against a virtual machine.

- Create Virtual Environment
- Install Chef Tools
- Copy Cookbooks
- Run/Apply Cookbooks
- Verify Assumptions
- Destroy Virtual Machine


### Test Kitchen
Test Kitchen is an integration tool for developing and testing infrastructure code and software on isolated target platforms.

When a chef generates a cookbook, a default .kitchen.yml file is created.

[http://kitchen.ci/](http://kitchen.ci/)

[https://github.com/test-kitchen/test-kitchen](https://github.com/test-kitchen/test-kitchen)




#### Commands
Change instance state to create. Start one or more instances

`kitchen create`

Create the instance (if necessary) and then apply the run list to one or more instances

`kitchen converge`

Change instance state to verify. Run automated tests on one or more instances

`kitchen verify`

Change instance state to destroy. Delete all information for one or more instances

`kitchen destroy`

Adds some configuration to your cookbook so Kitchen can rock

`kitchen init`

Test (destroy, create, converge, setup, verify and destroy) one or more instances

`kitchen test`

### ServerSpec
With Serverspec, you can write RSpec tests for checking your servers are configured correctly.

Serverspec tests your servers' actual state by executing command locally, via SSH, via WinRM, via Docker API and so on. So you don't need to install any agent softwares on your servers and can use any configuration management tools, Puppet, Ansible, CFEngine, etc.

```ruby
describe 'workstation::default' do

    describe package('tree') do
        it { should be_installed }
    end

end
```








