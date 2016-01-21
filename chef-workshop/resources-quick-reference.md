# Chef Resources Quick Reference
In a Chef recipe, a resource is something that exists on a system alone with its state.
A service to be started, a package to be installed, or a user to be created are all examples of resources.

##package
used to install, remove, and upgrade packages.
```
package 'httpd' do
    version '2.2.1'
    action :install
end
```

## template
Used to manage files fro mthe '/templates' directory in a cookbook.
Erubis templating processes the file contents after transferring it to a node.
```
template '/var/www/index.html' do
    owner 'root'
    group 'root'
    mode '0644'
    source 'index.html.erb'
    variables({ :key => value, :key => value })
    action :create
end
```

## service
used to manage services
```
service 'ntpd' do
    action :start
end
```

## file
used to manage files directly on a node.
```
file '/etc/motd' do
    owner 'root'
    group 'root'
    mode '0644'
    content 'A string to write.'
    action :create
end
```

## directory
used to manage a directory
```
directory '/data/alice' do
    owner 'alice'
    group 'root'
    mode '0750'
    recursive true
    action :create
end
```

## execute
used to execute a single, arbitrary command
```
execute 'apt-get -y update'

execute 'apt-get -y update' do
    not if { File.exist?('/var/tmp/apt-updated') }
end
```

## user
used to manage users and passwords
```
user 'alice' do
    comment 'Alice is a user.'
    home '/home/alice'
    system false
    shell '/bin/sh'
    uid '501'
    action :create
end
```

## group
used to manage a local group
```
group 'staff' do
    gid '501'
    members ['alice', 'bob']
end
```

## ruby_block
used to execute arbirary Ruby code during the chef-client run.
```
log 'A message to add to the log file.' do
    level :info
    action :write # default is STDOUT
end
```

## remote_directory
Used to transfer a directory from a cookbook
```
remote_directory '/path/to/directory' do
    owner 'root'
    group 'root'
    mode '0755'
    recursive true
    source 'directory_to_transfer'
    action :create
end
```

## remote_file
used to transfer files from a mote location
```
remote_file '/data/alice/stuff.zip' do
    owner 'alice'
    group 'staff'
    mode '0644'
    checksum 'b57cbc304cbfe1cfce08..la7e'
    source 'http://chef.io/stuff.zip'
    action :create
end
```

## cookbook_file
used to transfer files from the '/files' directory in a cookbook
```
cookbook_file '/var/www/css/bootstrap.css' do
    owner 'root'
    group 'root'
    mode '0644'
    source 'bootstrap.css'
    action :create
end
```

## script (bash, csh, perl, python, ruby)
used to execute scripts with a specific interpreter
```
script 'extract_module' do
    interpreter 'bash'
    code <<--EOH
        mkdir -p #{extract_path}
        tar xzf #{src_filename} -C #{extract_path}
        mx #{extract_path}/*/* #extract_path}/
    EOH
    not_if { File.exist?(extract_path) }
end
```

```
# each interpreter has a specific resource. For example, bash:
bash 'extract_module' do
    code <<-EOH
        mkdir -p #{extract_path}
        tar xzf #{src_filename} -C #{extract_path}
        mv #{extract_path}/*/* #{extract_patch}/
    EOH
    not_if { File.exist?(extract_path) }
end
```

## git
used to manage files that are sourced from a git repository
```
git "#{Chef::Config[:file_cache_path]}/app_name" do
    repository node['app_name']['git_repository']
    revision node['app_name']['git_revision']
    action :sync
end
```

## link
used to create symbolic and hard links
```
link '/path/to/target/file' do
    mode '0755'
    link_type :symbolic # or :hard
    to '/path/to/linked/file'
    action :create
end
```


## Common properties/actions (used with/any resource)

### defer property evaluation until runtime:

`property_name lazy { Ruby code }`

### specify an interpreter

`guard_interpreter :bash # :python, :ruby, etc.`

### continue chef-client run even if resource fails:

`ignore_failure true`

### prevent execution when true:

`not_if { 'grep bob /etc/motd', :user => 'alice' }`

### allow execution when true:

`only_if { File.exist?('stuff.zip') }`

### notify another resource when this one changes:

`notifies :action, 'resource[name]'`

### listen to another resource for changes

`subscribes :action, 'resource[name]'`

### retry the resource:

```
retries 0 # number of times to retry
retry_delay 2 # retry delay, in seconds
```

### wait to be notified by another resource

`action :nothing # wait for notification`

### Example: package, template, service
order matters! The package resource runs first, then the template resource, and then the service resource.

```
package 'haproxy' do
    action :install
end

template '/etc/haproxy/haproxy.cfg' do
    owner 'root'
    group 'root'
    mode '0644'
    source 'haproxy.cfg.erb'
    notifies :reload, 'service[haproxy]'
end

service 'haproxy' do
    supports :reload => true
    action [:start, :enable]
end
```
