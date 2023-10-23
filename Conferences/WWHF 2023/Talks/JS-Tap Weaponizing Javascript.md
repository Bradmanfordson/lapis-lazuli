---
Speaker: Drew Kirkpatrick
Company: TrustedSec
---
Write javascript and demonstrate how dangerous it is under the guise of "IF someone runs this..."

iframe's are basically browsers inside of browsers. Think credit card processing blocks, ads prolly, etc.


You can spoof the address bar with iframes and it's not even a vulnerability, it's part of the browsers functionality and javascript.


So you can have a xss vulnerability call to an external server hosting JS, and when it loads it'll use an iframe to spoof a wordpress login, spoof the address, and collect and forward the password to the ACTUAL wordpress so we can collect all the information we can get.

JS-Tap does this but also "persists" and watches through iframes the rest of the users session so we can spy on what they do. This will capture what the users type, it'll send screenshots of the pages they hit, it tracks cookies and when they change. This tool gives us a full view of exactly what the target goes.

This is an excellent tool to use to show the TRUE impact of XSS and phishing. (which is generally shit)

This will also download the html code for a page, including any passwords that were rendered on the page.


