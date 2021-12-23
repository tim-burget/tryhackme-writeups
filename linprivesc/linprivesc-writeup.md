# TryHackMe Linux Privesc Room
If you want to try this room yourself, you can find it at [tryhackme.com/room/linprivesc](https://tryhackme.com/room/linprivesc).

Unless otherwise specified, each task's machine has been accessed by clicking the "Start Machine" button to the right of that task's title, then clicking "Show Split View" near the top of the page to display the machine if it isn't already visible.

For the attacking machine (when necessary), I will be assuming you're using a (reasonably up-to-date) Kali Linux Distribution connected to TryHackMe's network through OpenVPN.

In screenshots, parts redacted with **red** boxes are answers for the current , parts redacted with **blue** boxes are personal information that is a necessary part of a command (generally my IP address on TryHackMe's VPN), and parts redacted with **white** boxes are other personal information or answers to other questions.

(**Note:** When using the target magine through the "Show Split View" button, underscores are invisible! Be wary of this!)
## Tasks 1 and 2
No answers are necessary here. Just read the tasks and make sure you understand their contents.

## Task 3: Enumeration 
### Question 1: What is the hostname of the target?
Run the command `hostname` on the target machine to get the hostname:

![hostname](https://user-images.githubusercontent.com/22843584/147180393-77710856-106d-4dab-95bc-2f3cfefbd534.png)

Other ways to find this:
* Run the command `cat /etc/hostname`:

   ![cat /etc/hostname](https://user-images.githubusercontent.com/22843584/147181944-8dff09f1-3b79-42d6-84f0-0e5ffc4cc58f.png)
* Run `uname -n`:

   ![uname -n](https://user-images.githubusercontent.com/22843584/147182484-ddcb892b-92d5-4845-8994-642f7ead2333.png)
* Run `uname -a`. The hostname will come right after the word `Linux`:

   ![uname -a](https://user-images.githubusercontent.com/22843584/147183392-da80699a-eedd-4d04-bc58-48baae35f019.png)

* Run `cat /etc/hosts`. You will find the hostname on the line with `127.0.1.1`:

   ![cat /etc/hosts](https://user-images.githubusercontent.com/22843584/147184462-08ee5048-78d3-4bc6-99c1-906de96a6d7d.png)
   
   (**Note:** This only works on Debian and Linux distros derived from Debian, like Ubuntu and Kali.)

* Run `bash`. By default, this will display the username, an at sign, and then the hostname at the beginning of the prompt:

   ![bash](https://user-images.githubusercontent.com/22843584/147185293-972c09a0-07f5-4a3e-bceb-3563c9cb018a.png)
