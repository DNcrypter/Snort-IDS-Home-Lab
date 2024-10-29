# Snort-IDS-Home-Lab
[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
        [![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-blue)](https://www.linkedin.com/in/nikhil--chaudhari/)
        [![Medium](https://img.shields.io/badge/Medium-Writeups-black)](https://medium.com/@nikhil-c)

## 🍁Introduction
Snort is an Intrusion Detection System(IDS) and an Intrusion Prevention System (IPS). it is used to notify and alert the security personnel in an organization of breached security rules. It uses a set of rules that define malicious network activity and uses these rules to find packets that match against them and generates alerts for users.

## 📝 Requirements:
- Ubuntu server/Desktop installed on Virtual machine
- Internet Connection

## 👩🏻‍🔬🧪 Lab Setup : 
**🍁 snort installation:**
**Step 1** : make sure that your Ubuntu Operating System is up and running on your VM and that you can ping it from your secondary Operating System (Kali). This means that they should be on the same network or subnet.
**Step 2** : go to terminal of ubuntu machine type commmand below.
```
 sudo apt-get update.
```
**Step 3** : install the Snort program and its dependencies.
```
sudo apt-get install snort
```
**Step 4** : type whereis snort command. It will list every directory containing the phrase snort. The directories created by Snort includes:
```
whereis snort
```
**/etc/snort**: It contains the configuration and rules files.
**/usr/sbin/snort**:- This is the executable binary of the Snort IDS/IPS.
**/usr/lib/snort**:- This contains the shared libraries and files that are used by the Snort executable /usr/sbin/snort and other Snort-related components.
**/usr/include/snort**:- This contains header files and related resources used for compiling and building custom plugins, preprocessors, or other Snort-related extensions.

**🍁 Configuring Snort**:
Now we have installed the snort and we are now going to configure snort by adding rules and other things.
**Step 1**: Navigate to etc/snort directory. locate the snort.conf file. This file contains various settings that are necessary for the effective working of Snort IDS.
```
cd etc/snort
ls
```
before moving forward we go through the snort.conf file. note that you have sudo permission. Open file in edit and write mode.
```
sudo su
```
This is the part where we shall set our home network to which we want Snort to monitor. Here, we shall indicate the full mask/subnet of our home network.  
```
nano snort.conf
```
Under the ipvar **HOME_NET** part, it’s where we set our home address. (Please include the /24 mask). This can be got from your Ubuntu terminal using the command ip a s as below. It is the second inet under the adapter enp0s3( it is different for you).
**Step 2**: save our changes and exit. use Ctrl + x, press Y and then Enter key.

Now, we have successfully installed and configured snort IDS.

## ❄️ Test snort configuration file for errors:
Let’s test our snort.conf file to make sure that there are no errors while running it.
```
sudo snort -T -i enps03 -c /etc/snort/snort.conf , run inside /etc/snort
```
- **-T** : it is used to open snort in test mode.
- **-i** : use to specify network interface.
- **-c** : specifies location of snort config file.
  
Observe, we have seen message below on terminal that “ **snort successfully validate the configuration** ”.

## 🍁🍁 Conclusion
We have successfull configured snort IDS. i have also written some medium articles where i shown how to create custom rules to handle Network based attacks and Web based attacks you must visit them.
