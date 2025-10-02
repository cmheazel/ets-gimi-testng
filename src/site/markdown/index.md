# Test Suite Archetype - TestNG Framework

## Purpose
This Maven archetype serves as a template for creating a new executable test 
suite (ETS) based on the [TestNG framework](http://testng.org/). It enables 
a test developer to quickly generate a test suite and start adding tests to 
verify that some test subject &#x2013; such as a web service or a data 
representation &#x2013; conforms to one or more specifications.

## How to use it
The Maven coordinates of the archetype are shown below (using the 
[latest version](https://repo1.maven.org/maven2/org/opengis/cite/ets-archetype-testng/) 
is always recommended):

    groupId: org.opengis.cite
    artifactId: ets-archetype-testng
    version: 2.7

In order to use the archetype and build the resulting test suite a 
[Java Development Kit](http://www.oracle.com/technetwork/java/javase/downloads/) 
(JDK) and [Apache Maven](https://maven.apache.org/) must be installed:

* JDK 8
* Apache Maven 3.0 or higher

To create a new test suite open a command shell (terminal window) and invoke the interactive 
__archetype:generate__ goal. It is necessary to specify the `ets-code` property at this point, 
the value of which must be a legal Java package name. For OGC test suites the convention is 
to identify the principal specification by major and minor version: wfs20, cat30, and the 
like. See Listing 1 for a sample invocation where the ets-code value is "abc10"; note 
that a '\' (backslash) character indicates that a line is continued.

**Listing 1: Using the archetype interactively**

    mvn archetype:generate \
        -Dfilter=org.opengis.cite:ets-archetype-testng \
        -Dets-code=abc10

Several prompts will ask for various property values in order to generate the test suite 
project. The suggested default values may be modified if desired. It is also possible to 
create a test suite non-interactively in "batch" mode by using the -B flag as shown in 
Listing 2.

**Listing 2: Using the archetype in batch mode**

    mvn archetype:generate -B \
        -DarchetypeGroupId=org.opengis.cite \
        -DarchetypeArtifactId=ets-archetype-testng \
        -DarchetypeVersion=2.7 \
        -Dets-code=abc10 \
        -Dets-title='Web Test Service (WTS)' \
        -Dets-title-short='WTS 1.0' \
        -DartifactId=ets-abc10 \
        -Dpackage=org.opengis.cite.abc10

Once the initial test suite has been created it must be modified to cover the specific test 
requirements of interest. See [Conformance Testing with TestNG, Part 1](http://opengeospatial.github.io/teamengine/testng-essentials.html) 
for more information about how to get started.
