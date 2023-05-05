Download Link: https://assignmentchef.com/product/solved-ece-322-lab5-integrating-white-box-testing-techniques-tools
<br>
The objective of this lab is to become familiar with integration white box testing techniques tools. This lab makes of use of Java and JUnit testing for integration testing.

Introduction

The following sections will serve as a brief introduction to integration testing.

<strong>Integration Testing: </strong>

Integration testing serves as a logical extension of unit testing. There are two general approaches to integration testing:

<ul>

 <li><em>Non-incremental testing (Big Bang): </em>Test each module <strong>independently </strong>then test the system as a whole</li>

 <li><em>Incremental Testing (Top down/Bottom up): </em><strong>Combine </strong>the next module to be tested with the set of previously tested modules before running tests. Generally done in either a bottom up or top down method

  <ul>

   <li><em>Bottom up: </em>Test the lowest level modules in isolation, then incrementally add higher and higher level modules.</li>

   <li><em>Top down: </em>Test the highest level modules in isolation stubbing out lower level functionality, incrementally add lower modules.</li>

  </ul></li>

</ul>

Generally, integration testing requires the use of various stubs and drivers.

<ul>

 <li><em>Stubs: </em>In integration testing a stub is used as a stand in for lower level modules not currently under test. Generally, a stub returns a dummy value or simply makes an assertion so that the test case can ensure it was called.</li>

 <li><em>Drivers:</em> A driver is simply a piece of testing code which makes it possible to call a submodule of an application independently. Driver code may require <em>stub </em>setup, object initialization and so on.</li>

 <li>Mocking Frameworks</li>

</ul>

Mocking frameworks can be extremely helpful in abstracting away much of the grunt work involved in creating and maintaining stubs and drivers. These frameworks allow for the easy creation of Mock Objects, which are usable as stubs in integration tests.

Mockito is a popular Java mocking framework, you can install this package using gradle by including:

<table width="368">

 <tbody>

  <tr>

   <td width="143">repositories { jcenter() }</td>

   <td width="224"> </td>

  </tr>

  <tr>

   <td colspan="2" width="368">dependencies { testCompile “org.mockito:mockito-core:2.+” }</td>

  </tr>

 </tbody>

</table>




In your gradle build file, declare a maven dependency:

&lt;dependency&gt;

&lt;groupId&gt;org.mockito&lt;/groupId&gt;

&lt;artifactId&gt;mockito-all&lt;/artifactId&gt;

&lt;version&gt;latest&lt;/version&gt;

&lt;/dependency&gt;

Or download the latest jar file from:

http://jcenter.bintray.com/org/mockito/mockito-core/

By creating <em>mock objects </em>you will be able to define object interfaces to use as stubs in your test cases, and easily verify the correct behavior of the modules under test with minimal boilerplate code.

Some tutorials on how to use Mockito can be found at:

<ul>

 <li>http://www.vogella.com/tutorials/Mockito/article.html</li>

 <li>https://dzone.com/articles/getting-started-mocking-java</li>

</ul>

Or check the official documentation:

<ul>

 <li>http://static.javadoc.io/org.mockito/mockito-core/2.8.47/org/mockito/Mockito.html For the ease of marking, you can use Mockito 2.x in your tests. <strong> </strong></li>

</ul>

<strong>Preparation: </strong>

Prepare test cases for the tasks you will be working on in the lab session. Make sure you have Eclipse and JUnit installed on your account, or an equivalent Java IDE. The code for this lab is available on the class website and can be imported into eclipse as an existing project.

<h1>Task</h1>

Consider a simple database system which has been constructed in a modular fashion: Module A invokes Module B Module C, Module D, and Module E. Module D invokes Module F, and Module G. Module’s B and C also invoke Module F.

Entries in the database are composed of two elements, a String <em>name </em>and a String <em>Phone number. </em>Module A is a Command Line Interface which processes command strings and delegates functionality to sub modules:

<ol>

 <li>Open a data file (Module B)</li>

 <li>Sort records (Module C)</li>

 <li>Modify a record (Module D)</li>

 <li>Exit (Module E)</li>

</ol>

Files for this database should contain one entry per line, and elements of an entry should be comma separated. Sorting sorts records by first name.

The modify function (Module D) additionally uses the Display function (Module F) and the update function (Module G).

<strong>    Your task </strong>is to prepare and run test cases, stubs, and drivers for:

<ul>

 <li>Big Bang Integration</li>

 <li>Bottom Up testing</li>

 <li>Top Down testing</li>

</ul>

<strong>    Unit tests should cover the full functionality of each module;</strong> there should be at least one test for each piece of functionality and method. Your test cases should strive for, at a bare minimum, statement coverage. You <strong>do no</strong>t need to main function of the provided code as it implements a simple command loop.

Only the <strong>public </strong>methods of Module A need to be tested directly. Use the provided printstream accessor to test String message outputs from the module.

Your test cases <strong>must be broken into three distinct test suites, </strong>one for each type of integration testing (3 test suites total). The <strong>reuse </strong>of individual tests is <strong>encouraged;</strong> however, be aware that <em>test order and setup is key </em>to correct integration testing. Your test suites should be easily run against the provided application code for verification.

Run the test cases and record your observations and results in your report, as in previous labs <em>test cases must be presented in your report as a test case table </em>with meaningful descriptions, expected and actual results. Failed test cases must be highlighted.

Comment on the effectiveness of integration testing in isolating individual modules. Would this type of testing be helpful in a large scale system? Why? Are drivers and stubs an effective method of isolating modules? Which type of integration testing do you think is best? Which would be the most appropriate for a test driven development environment? Which would be the most appropriate for library development? Which is the easiest to maintain? Consider these and similar questions in your discussion of integration testing to show you have a strong understanding of the underlying concepts and motivations of this testing technique.

Your code should include:

<ul>

 <li>Unit tests for all <strong>public functionality </strong>of Modules A through F</li>

 <li>Unit tests testing module <strong>integration </strong>with proper use of <strong>stubs </strong></li>

 <li><strong>Three test suites </strong>, one for each type of integration testing, with test cases in the <strong>correct order </strong> You <strong>do not </strong>need to submit correct code for this assignment.</li>

</ul>

Your report should include

<ul>

 <li>Three <strong>test case tables,</strong> one for each type of integration testing. Test case reuse is okay where applicable; however results should be <strong>fully </strong>listed in each table for clarity.</li>

 <li>A discussion of <strong>your results </strong>regarding the application under test. This should include a discussion of any errors you found in the code, and <strong>fixes </strong>to make your tests pass  A discussion of the above questions regarding integration testing techniques.</li>

</ul>

<strong> </strong>