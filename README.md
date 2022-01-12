# community.digitalocean.digital_ocean_droplet
Create and delete a DigitalOcean droplet

Create and delete a DigitalOcean droplet

Note

This plugin is part of the community.digitalocean collection (version 1.14.0).

You might already have this collection installed if you are using the ansible package. It is not included in ansible-core. To check whether it is installed, run ansible-galaxy collection list.

To install it, use: ansible-galaxy collection install community.digitalocean.

To use it in a playbook, specify: community.digitalocean.digital_ocean_droplet.

    Synopsis

    Parameters

    Examples

    Return Values

Synopsis

    Create and delete a droplet in DigitalOcean and optionally wait for it to be active.

Parameters
Parameter 	Choices/Defaults 	Comments
backups
boolean
	

    Choices:
    no ←
    yes

	
Indicates whether automated backups should be enabled.
firewall
list / elements=string
		
Array of firewall names to apply to the Droplet.
Omitting a firewall name that is currently applied to a droplet will remove it.
id
integer
		
The Droplet ID you want to operate on.

aliases: droplet_id
image
string
		
This is the slug of the image you would like the Droplet created with.

aliases: image_id
ipv6
boolean
	

    Choices:
    no ←
    yes

	
Enable IPv6 for the Droplet.
monitoring
boolean
	

    Choices:
    no ←
    yes

	
Indicates whether to install the DigitalOcean agent for monitoring.
name
string
		
This is the name of the Droplet.
Must be formatted by hostname rules.
oauth_token
string
		
DigitalOcean OAuth token.
There are several other environment variables which can be used to provide this value.
i.e., - 'DO_API_TOKEN', 'DO_API_KEY', 'DO_OAUTH_TOKEN' and 'OAUTH_TOKEN'

aliases: api_token
private_networking
boolean
	

    Choices:
    no ←
    yes

	
Add an additional, private network interface to the Droplet (for inter-Droplet communication).
project_name
string
	Default:
""
	
Project to assign the resource to (project name, not UUID).
Defaults to the default project of the account (empty string).
Currently only supported when creating.

aliases: project
region
string
		
This is the slug of the region you would like your Droplet to be created in.

aliases: region_id
resize_disk
boolean
	

    Choices:
    no ←
    yes

	
Whether to increase disk size on resize.
Only consulted if the unique_name is true.
Droplet size must dictate an increase.
size
string
		
This is the slug of the size you would like the Droplet created with.
Please see https://slugs.do-api.dev/ for current slugs.

aliases: size_id
sleep_interval
integer
	Default:
10
	
How long to sleep in between action and status checks.
Default is 10 seconds; this should be less than wait_timeout and nonzero.
ssh_keys
list / elements=string
		
Array of SSH key fingerprints that you would like to be added to the Droplet.
state
string
	

    Choices:
    present ←
    absent
    active
    inactive

	
Indicate desired state of the target.
present will create the named droplet; be mindful of the unique_name parameter.
absent will delete the named droplet, if it exists.
active will create the named droplet (unless it exists) and ensure that it is powered on.
inactive will create the named droplet (unless it exists) and ensure that it is powered off.
tags
list / elements=string
		
A list of tag names as strings to apply to the Droplet after it is created.
Tag names can either be existing or new tags.
timeout
integer
	Default:
30
	
The timeout in seconds used for polling DigitalOcean's API.
unique_name
boolean
	

    Choices:
    no ←
    yes

	
Require unique hostnames.
By default, DigitalOcean allows multiple hosts with the same name.
Setting this to true allows only one host per name.
Useful for idempotence.
user_data
string
		
Opaque blob of data which is made available to the Droplet.
validate_certs
boolean
	

    Choices:
    no
    yes ←

	
If set to no, the SSL certificates will not be validated.
This should only set to no used on personally controlled sites using self-signed certificates.
volumes
list / elements=string
		
A list including the unique string identifier for each Block Storage volume to be attached to the Droplet.
vpc_uuid
string
added in 0.1.0 of community.digitalocean
		
A string specifying the UUID of the VPC to which the Droplet will be assigned.
If excluded, the Droplet will be assigned to the account's default VPC for the region.
wait
boolean
	

    Choices:
    no
    yes ←

	
Wait for the Droplet to be active before returning.
If wait is false an IP address may not be returned.
wait_timeout
integer
	Default:
120
	
How long before wait gives up, in seconds, when creating a Droplet.
