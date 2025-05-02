Globus nodes may need to be rebuilt for various reasons, updating the OS, the machine dies ect.  If you need to rebuild an existing globus node
1. Setup the environment variables with the machine you want to replace
   1. globus node name is the short name [that will be in inventory](https://github.com/pulibrary/princeton_ansible/blob/main/inventory/by_cloud/aws#L1-L10) I suggest the name you are replaceing with a `-new` or `-2`
   ```
     export GLOBUS_ENV=<globus environment (pdc_staging or pdc_production)>
     export GLOBUS_NODE_NAME=<globus node name>
   ```
1. Run the playbook to create a new EC2 instance with globus installed.
   ```
     ansible-playbook playbooks/globus.yml -e globus_environment=$GLOBUS_ENV -e globus_instance_name=$GLOBUS_NODE_NAME -u pulsys
   ```
1. Make sure the aws inventory file has the new host ip in the correct location (sometimes it gets put at the bottom of the file instead of the correct place)
   ```
   vi inventory/by_cloud/aws
   ``` 
1. Run the Node rebuild playbook to install the existing node configuration and setup the node
   ```
     ansible-playbook playbooks/globus_build_node --limit $GLOBUS_NODE_NAME -e globus_environment=$GLOBUS_ENV
   ```   
1. In the [AWS console](princeton.com/aws)
   1. turn off the the original machine
1. Verify globus is still working in the [globus webapp](https://app.globus.org/file-manager/collections) by loading the collection and verifying you can see the files 
1.  In the [AWS console](princeton.com/aws)
   1. Move the Elastic IP to the new machine
   1. deleted the original instance ( not neccisary, but allows you to rename the new instance in a day or two) 
1. Delete the new machine from the [inventory](https://github.com/pulibrary/princeton_ansible/blob/main/inventory/by_cloud/aws#L1-L10)

 
