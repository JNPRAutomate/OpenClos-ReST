An example of a provisioning tool using ReST API for OpenClos. 

What is OpenClos ?
------------------
OpenClos is an open-source (available on GitHub) set of Python scripts and libraries that facilitate setting up IP Fabric networks built on BGP. 
It addresses the problem of automating the creation of IP fabrics at a large scale. 
More information can be found @ https://github.com/Juniper/OpenClos

How do you use OpenClos ?
-------------------------
The user interface for OpenClos can be provided either using the command line or ReST APIs

What does this tool do ?
------------------------
OpenClos generates IP fabric configuration for a POD - which constitutes a set of 'n' devices that make up the IP fabric. 
For each POD, the user needs to manually initiate ReST [POST/PUT] calls, create the JSON input to generate the configuration files
These configuration files can then be loaded to existing devices manually or can be used for ZTP. 
With this tool, users can initialize the YAML variable files and run the appropriate playbooks. This will generate the configuration files for multiple PODs/devices at once and push it to the target nodes without any manual intervention. 

Usage : 
------
To initialize the ReST API for multiple PODs: 
ansible-playbook -i hosts rest.yml 

To load the generated files to target devices: 
ansible-playbook -i hosts put-get-config.yml

POD information for ReST parameters : 
/roles/create-pod/vars/main.yaml

Global variable definition including target nodes:
/group_vars/all/global.yaml


