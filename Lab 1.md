Lab 1a-1 

Creating Linux environment, which started with VirtualBox download using virtualization software. The goal is to familiarize ownself to network settings in virtualized environment.

In this lab exercise, a VirtualBox or an equivalent virtualization tool is required together with Ubuntu (as desktop ISO), Git, and Github.

Started this exercise with downloading VirtualBox, which downloaded smoothly, continued with the download of Ubuntu. Which all links are acquired through the official links.
However, the process of downloading Ubuntu inside the VM, didn't go smoothly, causing the page to be stuck on the loading process for more than 10 minutes which was deemed abnormal.

<img width="2048" height="1140" alt="ubuntu fail" src="https://github.com/user-attachments/assets/e00fd67e-2d84-41f9-9f87-fc1466cb2c13" />

Hence, VMware was installed instead of VirtualBox. Which worked miraculously and installation complete message was delivered through NAT configuration.

<img width="738" height="1010" alt="ubuntu success" src="https://github.com/user-attachments/assets/94ce609e-e41a-479f-a989-6945907f559a" />

"Restart Now" was clicked and Ubuntu automatically restarted and prompt to enter password for the username created.

<img width="1974" height="1155" alt="password prompt ubuntu" src="https://github.com/user-attachments/assets/96ee162b-7c16-4db9-bd81-94b185aa8e15" />

After it is fully loaded, I installed git to the Ubuntu by prompting the following:

*sudo apt update* 

*sudo apt install git*

However, I ran into a problem because it kept prompting error. Thus, I realized that my NAT was not fully connected to the VM. After repairing the VM, I attempted to install git again and it worked. I continued by connecting my Git to my Github. 

<img width="2048" height="1042" alt="github connected" src="https://github.com/user-attachments/assets/16838f8c-58f2-4f3d-a9d3-05ca6a5eeaa9" />

1. What challenges did you encounter during the virtual machine setup? VirtualBox VM is not loading causing a long waiting delay time.
2. What did you learn about virtualisation tools and their differences? The importance of NAT and a reliable VM
3. How confident do you feel using Ubuntu after completing this lab? Yes
4. In what ways can a virtualised Linux environment help in industry scenarios? 
5. What would you do differently if setting up another VM? Using VMware from the start and stabilizing NAT



What are the advantages of using virtual machines for testing and development? 

What challenges did you face during installation or network setup? 

What are the differences between NAT and Bridged networking in VirtualBox? 

What did you learn about Linux distributions (distros) from your reading? 



