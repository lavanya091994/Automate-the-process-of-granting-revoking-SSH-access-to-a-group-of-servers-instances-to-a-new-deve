### Project Name: Automate-the-process-of-granting-revoking-SSH-access-to-a-group-of-servers-instances-to-a-new-developer.
## Steps involved:-
<br> Master: </br>
<p> generate a user which is common in both master & slave .. Example: ansible_admin</p>
<p> Give user"ansible_admin"root previleges<p> 
  <p> 6.1 goto visudo ->add user with root previleges </p>
  <p> 6.2 Example:ansible_admin ALL(ALL) NOPASSWD: ALL & save it. </p>
<p> Access the slave we need to ssh from master to slave <p> 
 <p> 9.1. goto  cd /etc/sshd.config & change the password_authentication:yes & #Password_authentication:No </p>
 <p> 9.2. Follow the same process in this location : cd /etc/ssh.config </p>
<p>  Next we have to restart the ssh service to make that chnages apply </p> 
  <p>11.1. command for restart:  service restart sshd or systemctl  restart </p>
  <p>11.2. Follow the same step in the node machine. </p>
  
#### NOTE: Follow the same step (2-11.2) in the node machine as well.
<p>  Next generate a key for  SSH-keygen </p> 
  <p> 15.1.Copy that aah key to particular node: </p>
  <p> 15.2.ssh-copy-id user@x.x.x </p>
  <p> 15.3.It will ask first time for the user_name & password </p>
  <p> 15.4.It will ask for the password & for the first time we have to give the password & second time login using ssh x.x.x.x.x </p>
<p>  Install Ansible based upon your O.S.</p> 
   <p> 21.1. edit that ansible.cfg file </p>
       <p> 21.1.1. command: vi etc/ansible/ansible.cfg </p>
       <p> 21.1.2.Uncomment "Inventory &  host file" & whatever needed for your requirement </p>
       <p> 21.1.3.Edit the hostfile & place all the host IP address in this file ahich you want to control </p>
<br> Install Python & its dependencies for ansible <br> 
<br>  Run your playbook by using:"ansible-playbook yourfile.yml"<br>  
