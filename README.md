# GIMI 1.0 Test-Suite

## Scope
The GIMI 1.0 Test-Suite is an Executable Test Suite (ETS) that verifies implementations against the GIMI 1.0 specification.

See specification documentation [here](https://github.com/opengeospatial/gimi).

Two conformance classes are defined:
  * [ISOBMF](http://www.opengis.net/spec/TDB)
  * [GIMI](http://www.opengis.net/spec/TBD)

## Bugs
Issue tracker is available at github.

## How to run the tests
The test suite is built using [Apache Maven v3](https://maven.apache.org/). The options
for running the suite are summarized below.

## Dependency requirement

On Linux, the test suite [requires](https://github.com/opengeospatial/ets-geotiff11/blob/master/src/main/java/org/opengis/cite/geotiff11/util/URIUtils.java#L203) libtiff-tools.


#### 1. Integrated development environment (IDE)

Use a Java IDE such as Eclipse, NetBeans, or IntelliJ. Clone the repository and build the project.

Set the main class to run: `org.opengis.cite.gimi.TestNGController`

Arguments: The first argument must refer to an XML properties file containing the
required test run arguments. If not specified, the default location at `$
{user.home}/test-run-props.xml` will be used.

You can modify the sample file in `src/main/config/test-run-props.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE properties SYSTEM "http://java.sun.com/dtd/properties.dtd">
<properties version="1.0">
  <comment>Test run arguments</comment>
  <entry key="iut">[GIMI File Name HERE].gimi</entry>
</properties>
```

The TestNG results file (`testng-results.xml`) will be written to a subdirectory
in `${user.home}/testng/` having a UUID value as its name.

#### 2. Command shell (console)

One of the build artifacts is an "all-in-one" JAR file that includes the test
suite and all of its dependencies; this makes it very easy to execute the test
suite in a command shell:

`java -jar target/ets-gimi-SNAPSHOT-ctl.jar  [-o|--outputDir $TMPDIR] [xml-file]`

Where `xml-file` is the path to the properties XML file, e.g., `src/main/config/test-run-props.xml`.

#### 3. OGC test harness

Use [TEAM Engine](https://github.com/opengeospatial/teamengine), the official OGC test harness.
The latest test suite release are usually available at the [beta testing facility](http://cite.opengeospatial.org/te2/).
You can also [build and deploy](https://github.com/opengeospatial/teamengine) the test
harness yourself and use a local installation.
