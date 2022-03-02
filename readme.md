# Headless Junit-based Selenium-Test with selenium-ide-Support

This is a very quick and rough proof-of-concept.
- First I installed the selenium extension for Chrome from https://www.selenium.dev/selenium-ide/.
- Then I started up some random hello-world web service with login functionality. 
- Next I used selenium-ide to record the login flow.
- I exported the 'SampleloginTest' to Java (in selenium-ide: right click on test > Export > Java Junit)
Finally, I scratched together the necessary maven boilerplate to run the exported Java file.

Junit 5 with junit-vintage-engine and hamcrest-library was all that was needed.
To make the Test headless (I assume this is a precondition in order to run this as a jenkins job) I added
```
options.addArguments("--headless");
```
in the exported Java file.

Minor drawback: As long as we need to modify the exported Java file, we cannot just 'drop' a freshly exported test.


_Disclaimer_:  
I did not invest more than 20 minutes into this project. It might serve as a starting point for a specific 
 project of a customer of mine. The selected frameworks (Java, Maven, selenium) were a given.
This I did not spend any time into doing research about possible alternatives. 

