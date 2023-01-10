<h1>Qualys - VM - Scan 1</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
Qualys Vulnerability Management is a cloud-based service that helps organizations identify and prioritize vulnerabilities in their IT systems and applications. The service works by performing periodic scans of the organization's IT assets, such as servers, laptops, and network devices, to identify vulnerabilities.
During a scan, Qualys Vulnerability Management uses a variety of techniques to identify vulnerabilities, including network discovery, port scanning, and identifying known vulnerabilities in software and operating systems. The service also looks for misconfigurations and other potential security issues.
After the scan is complete, Qualys Vulnerability Management produces a report that lists all of the vulnerabilities that were found, along with their severity and recommendations for how to address them. This report can be used to prioritize the remediation of vulnerabilities based on their risk level, as well as to track progress over time.
Qualys Vulnerability Management also provides a range of tools and features to help organizations manage and mitigate vulnerabilities, including the ability to schedule scans, track remediation progress, and generate custom reports. In this porject I will be conducting a simple, straight forward scan. 

** NOTE ** We will be using a Virtual Machine for the purpose of a virtual scanner appliance, I am using Oracle VM, you can download it on their site for free and there are plenty of YouTube videos on how to download it and set it up.

 
<br />


<h2>Languages and Utilities Used</h2>

- <b>Quayls VMDR</b> 

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Oracle Virtual Machine</b>

<h2>Program walk-through:</h2>

<p align="center">
We will first start at the VMDR Dashboard: <br/>
<img src="https://imgur.com/cRj2qGM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
You would want to then click on Scans -> Appliances -> New -> Virtual Scanner Appliance:  <br/>
<img src="https://imgur.com/ksECV8W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After clicking on New Virtual Scanner Appliance, you then would want to click on "Start Wizard": <br/>
<img src="https://imgur.com/CNZK6ky.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
For Virtual Scanner Name we are using "Test-MD", you can put any name. On the "Choose a Virtualization Platform, select VMware Workstation, Workstation Player, Fusion:  <br/>
<img src="https://imgur.com/G31l9ve.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
You will then click Next until you get to the page that has a Personalization Code. Write down the code to be on the safe side, as you will need the code later on. Then click on Check Activation :  <br/>
<img src="https://imgur.com/mXqfkJ6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
This will take a few minutes to process:  <br/>
<img src="https://imgur.com/mak6jGP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We will then have our VM pull up where we will see confirmation of the appliance. Click on Finish:  <br/>
<img src="https://imgur.com/Dy4VsXY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
As you can see the VM Appliance is Importing:  <br/>
<img src="https://imgur.com/Kd3NP2Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once our Virtual Appliance/VM has loaded up **NOTE, the Virtual Scanner can take a bit of time to load**:  <br/>
<img src="https://imgur.com/zelOJHe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once the Virtual Scanner has loaded we will get to the Quayls Scanner Console Page:  <br/>
<img src="https://imgur.com/kUM3vmS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
If a pop up for our Virtual Machine mouse keeps pulling up, just click cancel. After a few minutes go by, you should then get to this page where you will see a section to enter your personalization code. Enter the Personalization code from earlier. :  <br/>
<img src="https://imgur.com/2fZApMx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once code is entered, we will then see a message saying "Preparing the scanner personalization. :  <br/>
<img src="https://imgur.com/mak6jGP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We need to add asset groups. We do this by going to Select Assets-Asset Group-New. We will then get to this page to enter information about our Group, such as the name and confirmation of the owner:  <br/>
<img src="https://imgur.com/pBPab4i.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We will then enter IPs that we will be conducting a scan on. Here are few generic IPs we can use but of course, its best to use the IP address associated with your devices on your network. We will then go to scanner appliances and drop down see our Virtual Appliance Scanner that we had named previously. Click Save. We will get an error but that is because we will need to add hosts assets.:  <br/>
<img src="https://imgur.com/QF6gZMU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click on Host Assets, then click on Add IP to CertView:  <br/>
<img src="https://imgur.com/0uf5Rbu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the same IP addresses in the Host IP section and then click add and then apply:  <br/>
<img src="https://imgur.com/7fZjsi1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We will then go back to asset groups, select asset groups, then select new. You will continue entering a name for your group and then under the IP section, "Select Asset Groups". Click on all the boxes of the IP addresses assigned and then click select. You then select the same virtual scanner as before and then click save to finalize:  <br/>
<img src="https://imgur.com/H7LTMOZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We will then Add Authentication, by clicking on authentication->New->Operating Systems->Windows->Add Domain and User Credentials. There you will enter title->credentials. Here you can enter admin, password1 as this is just an example. You will then again select the IP addresses entered previously:  <br/>
<img src="https://imgur.com/JPeQndk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next we will want to click on scans->scan->new->Give the Name->Select the Profile which you want->Select Our Virtual Scanner Appliance->Select Asset Group and click Launch. On the Launch Vulnerability Scan, we will enter info on the title and import the default settings for profile->Click "Dont Make Global" on the final profile section. Before clicking scan, enter the drop down info for scanner and groups. Click Launch to start scan:  <br/>
<img src="https://imgur.com/Od26mr6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Scans can take from a few minutes to a few hours. Once completed, Scan Status Overview will populate with info on scan. Once the scan is complete, you can then view a report by clicking on reports, new scan report. You can then enter a title of your report and then select the format and template on how you would like to view it:  <br/>
<img src="https://imgur.com/cC3YEmu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Here we can see details on the scan that will show the severity of our vulnerabilities at which we can then go to patch. I used MS Word to view my report. At a later lab, we will conduct patch management on vulnerabilites:  <br/>
<img src="https://imgur.com/jP3Gzzy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
