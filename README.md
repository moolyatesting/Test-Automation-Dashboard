/***************************************************************

<strong>* Tool Creators : <a href="http://in.linkedin.com/pub/yagnesh-shah/40/507/180/">Yagnesh Shah</a>, <a href="http://in.linkedin.com/in/ladneerajkumar">Neeraj Lad</a>, <a href="https://in.linkedin.com/in/adilimroz">Adil Imroz</a></strong>

<strong>* Organization  : Moolya Software Testing Pvt Ltd</strong>

<strong>* website            : http://moolya.com/</strong>

<strong>* Licence             : <a href="https://github.com/moolyatesting/Test-Automation-Dashboard/blob/master/LICENSE">MIT</a></strong>

<strong>* contact             : yagnesh@moolya.com</strong>

***************************************************************/

<h1>About the software :</h1>

<h3>Background:</h3>
  <p>Automating a large product comprising of many small features &amp; sub products is a journey of diverse challenges. Reporting has always been one such challenge for everyone.</p>
  <ul>
	  <li>Here are some sample reports:</li>
	  <ul>
	    <li><a href="http://content.screencast.com/users/yash18774/folders/Default/media/7782f657-f96e-4e02-9cc1-aa1a6819478f/Testng%20report%20sample.png">TestNg Report</a></li>
	    <li><a href="http://screencast.com/t/lnXxuDuRV">XSLT Report Overview</a></li>
	    <li><a href="http://screencast.com/t/lGj9s6MghKv8">XSLT Report Detailed</a></li>
	    <li><a href="http://www.screencast.com/t/Th4GzjcO">Maven Report</a></li>
	  </ul>
	  <li>We knew that TestNG, Ant, Maven reports would not serve our needs entirely, as they are limited to the scripts or individual suite we execute currently.</li>
	  <li>What happens if our business heads need information on the entire product containing hundreds of scripts and multiple(N) suites? For them, the current suite result information is of no use to make decisions. They need info on entire automation results rather than individual suite reports.</li>
	  <li>They need a quick way of making decisions like looking at pie-chart for the results of hundreds of scripts.</li>
  </ul>

<h3>Challenge:</h3>
<p>We needed a reporting solution which could report everything automatically &amp; displays the information on dashboard.</p>

<h3>Solution:</h3>
<p>We made our own 'Test Automation Dashboard' tool which basically solves following two problems for our customers:</p>
<ol>
	<li>Retains 'Test execution History' for all suites.</li>
	<ol>
	  <li>View results by date</li>
	  <li>View results by period</li>
	</ol>
	<li>Reflects 'Test Execution Results' on a real-time basis for each suites.</li>
  <p>Hence, allowing our business heads to view information on real-time basis instead of waiting for 3-4 hours until all suites are executed.<p>
</ol>

<h3>Screenshots:</h3>
<p>Feature 1a:  <a href="http://screencast.com/t/wBvuDajW">View results by date</a><br>
Feature 1b: <a href="http://screencast.com/t/sTzxYsaM0d">View results by period</a><br>
Feature 2: Reflects <a href="http://screencast.com/t/fag1lLgsbODY">'Test Execution Results' on a real-time basis for each suites</a></p>

<h1>Pre-requisites:</h1>
<ol>
	<li>Input folder for Tool:</li>
	<p>The tool works by reading all reports from a specific directory on local system<br>
	Example:  E:\SampleReport\QA\ testngReports</p>
	
	<li>Report Type within Input folder :: TestNg Report format only</li>
  <p>Tool extracts necessary content from "TestNg" report type only.<br>
  Follow this reference guide to create "TestNg" reports as per "Date &amp; Time Stamp + Suite Name" directory format for for each suite we execute: <a href="http://yagnesh23.wordpress.com/2014/09/01/build-xml-for-selenium-webdriver-ant-testng-xslt-automation-reporting-chapter-1/">Build.xml for Selenium Webdriver + Ant + TestNg + XSLT</a></p>
  
  <li>Allow opening file:// links on pages loaded by http(s):// scheme:: <a href="https://chrome.google.com/webstore/detail/locallinks/jllpkdkcdjndhggodimiphkghogcpida">Local Links (Chrome Addon)</a></li>
</ol>

<h1>Configurations + How to run:</h1>
<ol>
  <li>Install <a href="http://tomcat.apache.org/">Apache-tomcat-7.0.55</a> server</li>
	<li>Copy-paste our 'TestAutomationDashboard_v1.0.war' into 'Webapps' directory within tomcat.</li>
	<p>Example: C:\apache-tomcat-7.0.55\webapps</p>
	<li>Start tomcat server by executing ' bat' file from 'C:\apache-tomcat-7.0.55\bin'. This action wil deploy the war file &amp; create a directory for 'TestAutomationDashboard_v1.0'</li>
	<li>Edit 'config.xml' from 'C:\apache-tomcat-7.0.55\webapps\TestAutomationDashboard_v1.0' directory to configure "input directory" for the tool:</li>
  <ol>
    <li><b>Configure total domains for 'Test Automation Dashboard" website:</b></li>
    <p>Within 'Sidebar' tag, by default there are 3 tags 'Links'. Each of them specifies a domain name for which we use to execute our test suites. The same domain name would be reflected in the Tool website.<br>
    We can add/remove a 'Links' tag in this file. On refreshing the tool website, the same would be reflected.<br>
    <b>Example: Add a QA domain within website:</b><br>
    &lt;Links&gt;<br>
    &lt;Name&gt;QA&lt;/Name&gt;<br>
    &lt;URL&gt;E:\projectName\QA\testngReports&lt;/URL&gt;<br>
    &lt;/Links&gt;<br>
    </p>
    
    <li><b>Configure the TestNg report folder for 'Test Automation Dashboard' tool input:</b></li>
    <p>Configure the local system address where your TestNg reports are being generated for each test suite:<br>
    Example: Configuring QA domain, TestNg report directory for tool input:<br>
    &lt;Links&gt;<br>
    &lt;Name&gt;QA&lt;/Name&gt;<br>
    &lt;URL&gt;E:\projectName\QA\testngReports&lt;/URL&gt;<br>
    &lt;/Links&gt;<br>
    </p>
  </ol>
	
	<li>Open Chrome browser and open following URL:</li>
	<p>http://localhost:8080/TestAutomationDashboard_v1.0/login.jsp</p>
	
	<li>Username: moolya / Password: moolya123</li>
	<p>Done :) You should be good to play around with the tool &amp; it's features now.</p>
</ol>

<h1>Limitations of the software:</h1>
<p>Version1.0 of 'Test Automation Dashboard' tool has following limitations:<br>
"Test Automation Dashboard_v1.0" is aimed to provide dashboard information with regards to only:<br></p>
<ol>
	<li>View results by date</li>
	<li>View results by period</li>
	<li>Test Execution Status: Real-time test suite execution status</li>
	<p><b>Note:</b> On refreshing the 'Test Execution Status' tab, it would automatically display all test suite execution status which has been executed so far. It does not tell you how many more test suites are pending to execute yet.</p>
</ol>

