# Burp Extension Maven Archetype

This project is a Maven archetype (template) for quickly creating extensions for Burpsuite. 

## Prerequisites

You need [Maven](https://maven.apache.org/install.html) installed to make use of this repository. Consult your package manager or IDE manual for specific installation instructions.

## Installation

To install this plugin, clone the repository and use `mvn` to install it:

1. `git clone https://github.com/ise-spolansky/burp-extension-maven-archetype.git`
2. `cd burp-extension-maven-archetype && mvn install`

## Creating a New Project

Once installed, create a new project using the following command line:

```
mvn archetype:generate -DgroupId=com.demo -DartifactId=DemoProject -DarchetypeArtifactId=burp-extension -DarchetypeGroupId=com.securityevaluators -DinteractiveMode=false
```

Replace `com.demo` with your organization's namespace, and `DemoProject` with your desired project name. Maven will then create the project structure for you, including a template extension source file. 

When you wish to test your changes, run `mvn clean compile assembly:single` to generate a self-contained JAR file that can be imported into Burp as an extension.

## IntelliJ Integration

IntelliJ can create projects based on Maven archetypes. To do so, first install the Maven plugin from the IntelliJ extension repository, then follow the installation instructions to install this archetype to your local Maven repository. To actually create a new project, go to the Create Project window select the `Maven` tab, and check the box for `Create from archetype`.

The first time you create a project, you will have to make IntelliJ aware of it. Click the `Add Archetype...` button. Enter `com.securityevaluators` for the GroupId, `burp-extension` for the ArtifactId, and `1.0` for the version. Leave `Repository` blank, and click `OK`. 

After that, you can simply select `com.securityevaluators:burp-extension` from the archetype list and follow the prompts to create your extension project.