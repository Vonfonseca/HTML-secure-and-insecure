This project demonstrates common security issues in web authentication systems and compares an insecure implementation with an improved version.

The goal is educational: to show how poor client-side security practices can expose applications to attacks and how some basic protections can reduce risk.

This project was created as a learning exercise in web development and introductory cybersecurity concepts.

 Project Structure

/project
├── index.html → Project explanation 
├── insecure.html → Vulnerable login implementation
├── secure.html → Improved login implementation
├── form.html → Page accessed after login
├── back.css → Styling

Insecure Version

The insecure version demonstrates common mistakes found in beginner web applications.

Main problems:

* Authentication logic is entirely on the client side.
* Credentials are visible in the JavaScript code.
* No limit on login attempts.
* No protection against automated login attempts.
* Minimal input validation.

Example of insecure logic:


if (u === "admin" && p === "1234") {
    window.location.href = "form.html";
}


Because the verification happens in the browser, an attacker could inspect or manipulate the code and bypass the login system.

Improved Version

The secure version introduces basic defensive practices while still remaining a front-end simulation.

Security improvements:

* Input validation (`required`, `maxlength`, `minlength`)
* Limiting login attempts
* Generic error messages
* Clearing input fields after failed login
* Basic protection against repeated attempts

Example protection logic:

let chances = 0;

if (chances >= 3) {
    alert("Too many attempts. Try again later.");
}


Important note:

In real-world applications, authentication must be handled on the server side with encrypted password storage and proper backend validation.


Automation and Security Testing

Automation can be used to test whether a login system is secure.

Attackers often use automated scripts to perform **brute-force attacks**, where thousands of passwords are tested quickly.

Example concept of automated attempts:

["1234", "password", "admin", "qwerty"].forEach(p => {
    attemptLogin("admin", p);
});


If a system does not limit login attempts or implement delays, automated attacks can guess passwords much faster than a human.

Security systems often defend against this by:

* Limiting login attempts
* Adding delays between attempts
* Using CAPTCHA
* Logging suspicious activity
* Blocking suspicious IP addresses



Educational Purpose

This litle project is intended to demonstrate:

* Basic web development with HTML and JavaScript
* Common web security mistakes
* Introductory concepts in ethical hacking and defensive security

The focus is on understanding vulnerabilities and improving system design, not exploiting real systems.



## Author

Victor Fonseca
A Cybersecurity student
