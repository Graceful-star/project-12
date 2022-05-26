# Documentation of project 12

## STEP 1
1. I created a directory, named it "ansible-config-artifact" and changed the permission.
   `sudo mkdir /home/ubuntu/ansible-config-artifact`
   `chmod -R 0777 /home/ubuntu/ansible-config-artifact`

   ![Project12](images/image1.PNG)

2. I installed "copy artifacts from my jenkins web console"
  
   ![Project12](images/image2.PNG)

3. I created a freestyle project and named it "save_artifacts"

    ![Project12](images/image3.PNG)

4. I configured my freestlye project for it to trigger builds from ansible builds

    ![Project12](images/image4.PNG)
    ![Project12](images/image5.PNG)

5. I confirmed if my files are in the ansible-config-artifact directory

    ![Project12](images/image6.PNG)
     ![Project12](images/image11.PNG)

6. I created a role path for ansible in "etc/ansible/ansible.cnf"

   `sudo vi /etc/ansible/ansible.cnf`

   ![Project12](images/image12.PNG)

7. I created a file; "common-del.yml" in my static-assignments directory
    
    ![Project12](images/image13.PNG)

8. I confirmed if my ansible command was runing

   `ansible all -m ping`
       
       ![Project12](images/image15.PNG)

9.  I ran my playbook to delete wireshark and it worked

    `ansible-playbook -i /home/ubuntu/ansible-config-artifact/inventory/dev.yml /home/ubuntu/ansible-config-artifact/playbooks/site.yml`

    ![Project12](images/image16.PNG)

10. I confirmed if wireshark has been deleted on all instances connected

    ![Project12](images/image17.PNG)
    ![Project12](images/image18.PNG)
    ![Project12](images/image19.PNG)
    ![Project12](images/image20.PNG)
    ![Project12](images/image21.PNG)


11. I launched two new instances and named it "web1-uat" and "web2-uat"
   
     ![Project12](images/image22.PNG)

12. I created a webserver role

     ![Project12](images/image23.PNG)

13. I edited my ansible.conf file

    ![Project12](images/image24.PNG)

14.  I commited and pushed all changes to my github repository

     ![Project12](images/image25.PNG)

15. I manually checked if my webservers are okay
      
      `uat-webserver -m ping`
    ![Project12](images/image26.PNG)

16. I run my ansible-playbook command and it worked

    ![Project12](images/image27.PNG)

17. These are the commands in my files
    
    ![Project12](images/uat.PNG)
    ![Project12](images/uat-inventory.PNG)
    ![Project12](images/.PNG)
    ![Project12](images/common-del.PNG)
