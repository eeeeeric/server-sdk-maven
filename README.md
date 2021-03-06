[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.unboundid/server-sdk-maven-parent/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.unboundid/server-sdk-maven-parent) [![Build Status](https://travis-ci.org/UnboundID/server-sdk-maven.svg?branch=master)](https://travis-ci.org/UnboundID/server-sdk-maven) [![Javadocs](https://www.javadoc.io/badge/com.unboundid/server-sdk-maven-parent.svg)](https://www.javadoc.io/doc/com.unboundid/server-sdk-maven-parent)
# UnboundID Server SDK Maven Helpers

This repository provides two components that can be used to develop and package 
[UnboundID Server SDK](http://blog.arnaudlacour.com/2011/01/introducing-unboundid-server-sdk-future.html) 
extensions using Maven. Among other benefits, Maven-based projects:

* Provide easy dependency management and access to a vast ecosystem of Java components.
* Take advantage of integrations with IDEs like
[IntelliJ IDEA](https://www.jetbrains.com/help/idea/2016.2/getting-started-with-maven.html#create_maven_project)
and [Eclipse](https://books.sonatype.com/m2eclipse-book/reference/creating.html#creating-sect-m2e-create-archetype).
* Work seamlessly with continuous integration systems, such as
[Jenkins](https://wiki.jenkins-ci.org/display/JENKINS/Building+a+maven2+project),
[Travis](https://docs.travis-ci.com/user/languages/java/),
[CircleCI](https://circleci.com/docs/language-java/), and
[Bamboo](https://confluence.atlassian.com/bamboo/maven-289277038.html).

This project is provided as a convenient but unsupported
alternative to the Server SDK's official Ant-based build mechanisms.

The included components are:

| Component | Description |
| --- | --- |
| server-sdk-archetype | Generates a Maven project for building extension bundles. |
| server-sdk-docs-maven-plugin | Generates an extension bundle's HTML documentation. |

Typically, only the archetype needs to be used directly; the project that it
generates will use the docs plugin automatically.

## Usage

Use the archetype to generate a Maven project, providing your own values for 
`groupId` and `artifactId`:

```
mvn archetype:generate -DarchetypeGroupId=com.unboundid \
  -DarchetypeArtifactId=server-sdk-archetype \
  -DarchetypeVersion=1.0.10 \
  -DgroupId=com.example -DartifactId=my-extension \
  -DinteractiveMode=false
```

The new project will contain an example extension, which you should customize 
or replace. You will also need to customize the generated `pom.xml`.

When you are ready to build an extension bundle, run `mvn package`. 
The extension bundle will be created as a zip in the `target` directory.

## License

This is licensed under the Apache License 2.0.
