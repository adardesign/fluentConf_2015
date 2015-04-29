# Transform into Your Team’s Web Security Guru
#### Monday April 20th 3:45pm – 5:15pm
###### Stephen Teilhet (IBM)


[github link - FluentTalkSecurityInfo](https://github.com/steilhet/FluentTalkSecurityInfo)



## The AppSec Triangle
- AppSec Knowledge
- Security Code Review SAST
- Pen-Testing DAST

### AppSec Knowledge
- Focus
- Pick your language(s) carefully
- Don’t try to learn it all at once
- To certify or not…
- Stand on the shoulders of giants
  - OWASP  	(owasp.org)
  - SANS  	(sans.org)
  - CWE 		(cwe.mitre.org)
  - CVE 		(cve.mitre.org)

### AppSec Knowledge - Tools
- [ZAP Proxy](goo.gl/smh3Vm)
- [Kali](https://www.kali.org) (General Security Testing)
- [OWASP Web Testing Environment](https://www.owasp.org/index.php/OWASP_Web_Testing_Environment_Project) (OWASP specific, mainly contains OWASP tools)
- [Samurai-WTF](www.samurai-wtf.org)
- [checkout toolswatch.org](http://www.toolswatch.org/)

## Source or Sink?
Always ask the question, is it a Source or a Sink?

### Sources:
- External user input (QueryStrings, HTTP Headers, POST Body, URL Hashes)
- Stored user input (LocalStorage, Cookies, SessionStorage, Files)
- Data from services  (Internal/External) AJAX Calls, Web Services, WebSockets)
- Sensitive data (GPS Location, SSN, CCN?, Passwords, Other PII, Crypto Keys)

### Sinks
- Send data to a service (QueryStrings, HTTP Headers, POST Body, AJAX Calls)
- Store data locally (LocalStorage, Cookies, SessionStorage, Files)
- Write data to DOM ((Internal/External) AJAX Calls, Web Services, WebSockets)
- Execution (Eval, XPath, RexEx)
- Use file paths (OpenFile, ReadFile, WriteFile, DeleteFile)
- Manipulate HTTP Headers (AddHeader, ModifyHeader)

http://google-gruyere.appspot.com/start


