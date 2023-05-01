# Load Testing by JMeter
## Introduction
This project shows the results of a basic load test done by JMeter on frequently used API of a website(https://restful-booker.herokuapp.com/apidoc/index.html)

## Prerequisites
- Java (version 8 or higher)
- JMeter by Apache Software

## How to run this project?
- Download & install Java (Link: https://www.oracle.com/java/technologies/downloads/)
- Download & install JMeter (Link: https://dlcdn.apache.org//jmeter/binaries/apache-jmeter-5.5.zip)
- Download the *.jmx files of this project.
- Run JMeter by using JMeter.bat in the "bin" folder to run or edit the *.jmx files.

## Test Report Generating Procedure
- Go to jmeter.bat file location.
- Open CMD in the file location.
- Run the *.jmx files in CLI by typing the following command which will convert them to *.jtl files:
  ```sh
   jmeter -n -t [Filename].jmx -l report\[Filename].jtl
  ```
- Type the following in CLI to convert the *.jtl test reports to readable *.html format.
  ```sh
   jmeter -g report\[Filename].jtl -o report\[Filename].html
  ```
- Check the newly created "reports" folder in the "bin" folder & open *.html files to view reports.
- The following commands were used for generating the reports of this current project:
  For thread count 100:
  ```sh
   jmeter -n -t RestfulBooker_T100.jmx -l report\RestfulBooker_T100.jtl
   jmeter -g report\RestfulBooker_T100.jtl -o report\RestfulBooker_T100.html
  ```
  For thread count 150:
  ```sh
   jmeter -n -t RestfulBooker_T150.jmx -l report\RestfulBooker_T150.jtl
   jmeter -g report\RestfulBooker_T150.jtl -o report\RestfulBooker_T150.html
  ```
  For thread count 200:
  ```sh
   jmeter -n -t RestfulBooker_T200.jmx -l report\RestfulBooker_T200.jtl
   jmeter -g report\RestfulBooker_T200.jtl -o report\RestfulBooker_T200.html
  ```
## Test Reports
- Test Report for Thread Count 100 :
https://htmlpreview.github.io/?https://github.com/taufique95/Load-Testing-JMeter/blob/master/Test%20Report/RestfulBooker_T100.html/index.html
- Test Report for Thread Count 100 :
https://htmlpreview.github.io/?https://github.com/taufique95/Load-Testing-JMeter/blob/master/Test%20Report/RestfulBooker_T150.html/index.html
- Test Report for Thread Count 200 :
https://htmlpreview.github.io/?https://github.com/taufique95/Load-Testing-JMeter/blob/master/Test%20Report/RestfulBooker_T200.html/index.html


## Test Results Summary
The test was performed on frequently used APIs on https://restful-booker.herokuapp.com/apidoc/index.html.
From the reports gathers, the following results can be concluded:

| Concurret Request | Loop Count | AVG TPS for Total Sample | Total Concurrent API requested | Error(%) |
| ------ | ------ | ------ | ------ | ------ |
| 100 | 10| 12| 6000| 0%
| 150 | 10| 19| 9000| 0%
| 200 | 10| 16| 12000| 0.57%

While executed 200 concurrent requests, found 45 requestes got "403 Forbidden" error and the error rate was 0.57%.

Summary: Server can handle approximately concurrent 10500 API call with almost zero (0) error rate.

