UI-Tests for the adidas homepage
Framework Architecture
  Project
	|
	|_src/main/
	|	|_java
	|	|	|_CucuberFramework
	|	|		|_pageObjects
	|	|			|_BrowserSetup.java
	|	|			|_HomepagePageObject.java
	|	|			|_SearchPage.java
	|	|			|_UtilAdidas.java
	|	|_resources
	|		|_global.properties
	|		
	|_src/test/java/CucuberFramework/
		|_features
		| 	|_homepage.feature
		|_resources
		| 	|_chromedriver.exe
		|	|_geckodriver.exe
		|_runner
	 	|	|_MainRunner.java    This is the file we have to run
		|_stepFiles
			|_Homepage.java
Instruction to run the testing on MacOS
Pre-requirement
JDK 9 (preferred version )
Maven
Homebrew
Latest version of chrome and firefox browser
Required installation
Install chromedriver for running the test on chrome browser
brew install chromedriver
Install geckodriver for running the test on firefox browser
brew install geckodriver
Run the test
To run the test on chrome browser
Go to Terminal, run the following command to run chromedriver
chromedriver
Then go to this location src/main/resources and make changes below changes to this global.properties
browser=chrome
Then open another terminal and go to project directory. Then run the following command
./mvnw test
To run the test on firefox browser
Go to Terminal, run the following command to run geckodriver
chromedriver
Then go to this location src/main/resources and make changes below changes to this global.properties
browser=firefox
Then open another terminal and go to project directory. Then run the following command
./mvnw test
Where can I see report
Once you run the test successfully, go to project directory and open directory named "target". You will find report.html

Note: In case, the above instruction is not working, please follow the instruction to run the test manually which is explained at the of this document.

Running test on Windows
Running test on windows machine is different than running on mac because there are some changes required in code. Please follow the steps below.

Pre-requirement
JDK 8
Maven
Latest version of chrome and firefox browser
Eclipse
Things to change in the code
go to src/main/resources/ and make the following changes in the code. Just remove the # in front of those two line
#firefox_driver_path=src\\test\\java\\CucuberFramework\\resources\\geckodriver.exe
#chrome_driver_path=src\\test\\java\\CucuberFramework\\resources\\chromedriver.exe
if you want to run the test on firefox, then change the browse
browser=firefox
Then go to src/main/java/CucuberFramework/pageObjects/ and open BrowserSetup.java. Then comment out following two line in the code and remove // in front of the code
//System.setProperty("webdriver.gecko.driver",global_data.getProperty("firefox_driver_path"));
//System.setProperty("webdriver.chrome.driver",global_data.getProperty("chrome_driver_path"));
Now you are ready to run the test.
Run the test on Maven
I tried to run the test using maven. But for some reason its not working using the maven. So I would recommend to run the test manually which is explained below.

To run the test manually
Clone the repository
Open the project in Eclipse as maven project
Then install following dependency
Go to Help > Eclipse marketplace from eclipse. Then search for cucumber and install Natural 0.7.6
Then again got to Help > Eclipse marketplace from eclipse. Then search for testng and install TestNg for eclipse
Install cucumber eclipse plugin. Follow instruction here
Then set project build path to JDK
Fin# UI-Tests for the adidas homepage

### Framework Architecture
		
	  Project
		|
		|_src/main/
		|	|_java
		|	|	|_CucuberFramework
		|	|		|_pageObjects
    	|	|			|_BrowserSetup.java
    	|	|			|_HomepagePageObject.java
    	|	|			|_SearchPage.java
    	|	|			|_UtilAdidas.java
		|	|_resources
		|		|_global.properties
		|		
		|_src/test/java/CucuberFramework/
			|_features
    		| 	|_homepage.feature
			|_resources
    		| 	|_chromedriver.exe
    		|	|_geckodriver.exe
			|_runner
   		 	|	|_MainRunner.java    This is the file we have to run
			|_stepFiles
    			|_Homepage.java



## Instruction to run the testing on MacOS

### Pre-requirement

* JDK 9 (preferred version )
* Maven
* Homebrew
* Latest version of chrome and firefox browser

### Required installation

* Install chromedriver for running the test on chrome browser
```sh
brew install chromedriver
```
* Install geckodriver for running the test on firefox browser
```sh
brew install geckodriver
```

### Run the test

#### To run the test on chrome browser

* Go to Terminal, run the following command to run chromedriver
```sh
chromedriver
```
* Then go to this location src/main/resources and make changes below changes to this **global.properties**
```sh
browser=chrome
```
* Then open another terminal and go to project directory. Then run the following command
```sh
./mvnw test
```

#### To run the test on firefox browser

* Go to Terminal, run the following command to run geckodriver
```sh
chromedriver
```
* Then go to this location src/main/resources and make changes below changes to this **global.properties**
```sh
browser=firefox
```
* Then open another terminal and go to project directory. Then run the following command
```sh
./mvnw test
```

### Where can I see report

Once you run the test successfully, go to project directory and open directory named "target". You will find report.html

**Note:** In case, the above instruction is not working, please follow the instruction to run the test manually which is explained at the of this document.



## Running test on Windows
Running test on windows machine is different than running on mac because there are some changes required in code. Please follow the steps below.

### Pre-requirement

* JDK 8
* Maven
* Latest version of chrome and firefox browser
* Eclipse

#### Things to change in the code
* go to src/main/resources/ and make the following changes in the code. Just remove the **#** in front of those two line
```
#firefox_driver_path=src\\test\\java\\CucuberFramework\\resources\\geckodriver.exe
#chrome_driver_path=src\\test\\java\\CucuberFramework\\resources\\chromedriver.exe
```
* if you want to run the test on firefox, then change the browse
```
browser=firefox
```
* Then go to src/main/java/CucuberFramework/pageObjects/ and open BrowserSetup.java. Then comment out following two line in the code and remove **//** in front of the code
```
//System.setProperty("webdriver.gecko.driver",global_data.getProperty("firefox_driver_path"));
//System.setProperty("webdriver.chrome.driver",global_data.getProperty("chrome_driver_path"));
```
* Now you are ready to run the test.

#### Run the test on Maven
I tried to run the test using maven. But for some reason its not working using the maven. So I would recommend to run the test manually which is explained below.

#### To run the test manually
* Clone the repository
* Open the project in Eclipse as maven project
* Then install following dependency
	- Go to **Help > Eclipse marketplace from eclipse**. Then search for cucumber and install **Natural 0.7.6**
	- Then again got to **Help > Eclipse marketplace from eclipse**. Then search for testng and install **TestNg for eclipse**
	- Install **cucumber eclipse plugin**. [Follow instruction here](http://toolsqa.com/cucumber/install-cucumber-eclipse-plugin/)
	- Then set project build path to JDK
	- Finally run MainRunner.java as Junit test **Before you run the test please follow instruction in "Things to change in the code if you are an windows user")**ally run MainRunner.java as Junit test Before you run the test please follow instruction in "Things to change in the code if you are an windows user")
