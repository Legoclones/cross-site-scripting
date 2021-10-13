# Cross-Site Scripting

## Introduction
Cross-site scripting (XSS) is a common attack that malicious actors use impersonate other users, including you. Each time you visit a website that requires you to log in, the website sends you what's called a cookie. This is simply a long, randomly-generated string of characters that proves who you are. When you log in, the website sends you the cookie, and each time you visit another page, you send that cookie back. If an attacker can steal that cookie from you, they can send it in their own web requests and act as you - the server won't know the difference. Cross-site scripting is when an attacker exploits a vulnerability in the website that allows them to steal your cookies (or other important data, like passwords) and act as you. If this is on a banking website, they can clear your account. If this is on your email, they can reset all your passwords. If you really think about, the consequences can be disastrous! 

In this tutorial, I'm going to teach you how to avoid this kind of attack and ensure cookies are safe.

## Steps of XSS
Before thinking about how to mitigate, or remove, the vulnerability, I believe it's important to understand how it works. I will go through the 4 main steps of cross-site scripting, and afterwards show two different examples.

### Find a Reflection Point
A reflection point is a place on a website where user input is reflected. Some common examples are comments, bios, social media and blog posts, notes, messages, or even what you type into the search bar. There are two main types of XSS:

* Stored/persistent XSS
* Reflected XSS

Reflected XSS is when the user input is temporary, and only present when specifically directed to by the attacker. For example, parameters in a malicious URL might be shown on the webpage, such as a search bar. Going to the URL `https://sos.tn.gov/site-search/malicious-input-here` will display `malicious-input-here` on the page (try it!). However, the victim must go to the URL, and they probably aren't going to type in malicious code to execute on themselves. This is why reflected XSS is more difficult, and usually relies on tricking the victim into clicking on a URL from a phishing email or social media post.

pic1

Stored XSS has a much higher success rate because if someone goes to a site with stored, malicious input of their own volition, they will receive the payload. For example, if you make a comment on a Facebook post, anyone that sees the Facebook post will see your input. While tricking a victim into going to that webpage will speed things up, it's not necessary. Stored XSS means your user input is stored in some sort of database or file and, whenever a person access that page, your input is retrieved and then displayed. For example, this is a simplistic pastebin site. If you create a public paste, anyone that visits it will then see your malicious input.

pic2

I think it's also important to note that reflection points don't just have to be visual - you can also have hidden reflection points, especially when inserting user input into HTML elements as classes, names, titles, values, etc.

### Insert JavaScript


### Deliver a Payload


## How to Mitigate XSS Attacks
Javascript (textcontent, innerhtml, etc.)

PHP htmlspecialchars

Others

DOMPurify when html is necessary

All sensitive cookies as HTTP only

Escaping all <> and '"

## Additional Resources
1. a
    - a
2. a
    - a
3. a
    - a
4. a
    - a
