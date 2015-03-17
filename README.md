
# Jackdaw [![Build Status](https://travis-ci.org/vbauer/jackdaw.svg)](https://travis-ci.org/vbauer/jackdaw) [![Maven](https://img.shields.io/github/tag/vbauer/jackdaw.svg?label=maven)](https://jitpack.io/#vbauer/jackdaw)

<img align="right" style="margin-left: 15px" width="300" height="243" src="jackdaw-misc/jackdaw.png" />

Java [Annotation Processor](http://docs.oracle.com/javase/7/docs/api/javax/annotation/processing/Processor.html) which
allows to simplify development without using reflections and prevents writing of tedious code.


## Features

**Jackdaw** support the following compile time annotations:

<ul>
    <li><a href="#jadapter">@JAdapter</a></li>
    <li><a href="#jbean">@JBean</a></li>
    <li><a href="#jbuilder">@JBuilder</a></li>
    <li><a href="#jclassdescriptor">@JClassDescriptor</a></li>
    <li><a href="#jcomparator">@JComparator</a></li>
    <li><a href="#jfactorymethod">@JFactoryMethod</a></li>
    <li><a href="#jfunction">@JFunction</a></li>
    <li><a href="#jmessage">@JMessage</a></li>
    <li><a href="#jpredicate">@JPredicate</a></li>
</ul>


## Setup

### Maven

```xml
<repository>
    <id>jitpack.io</id>
    <url>https://jitpack.io</url>
</repository>

<dependencies>
    <dependency>
        <groupId>com.github.vbauer</groupId>
        <artifactId>jackdaw-core</artifactId>
        <version>${jackdaw.version}</version>
    </dependency>
</dependencies>

<build>
    <plugins>

        <!-- Disable annotation processors during normal compilation -->
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-compiler-plugin</artifactId>
            <version>${maven.compiler.plugin.version}</version>
            <configuration>
                <compilerArgument>-proc:none</compilerArgument>
            </configuration>
        </plugin>

        <plugin>
            <groupId>org.bsc.maven</groupId>
            <artifactId>maven-processor-plugin</artifactId>
            <version>${maven.processor.plugin.version}</version>
            <executions>
                <execution>
                    <id>process</id>
                    <goals>
                        <goal>process</goal>
                    </goals>
                    <phase>generate-sources</phase>
                    <configuration>
                        <encoding>${file.encoding}</encoding>
                        <processors>
                            <processor>com.github.vbauer.jackdaw.JackdawProcessor</processor>
                        </processors>
                        <optionMap>
                            <!--<addGeneratedAnnotation>false</addGeneratedAnnotation>-->
                            <addGeneratedDate>true</addGeneratedDate>
                        </optionMap>
                    </configuration>
                </execution>
            </executions>
            <dependencies>
                <dependency>
                    <groupId>com.github.vbauer</groupId>
                    <artifactId>jackdaw-apt</artifactId>
                    <version>${jackdaw.version}</version>
                </dependency>
            </dependencies>
        </plugin>

        <plugin>
            <groupId>org.codehaus.mojo</groupId>
            <artifactId>build-helper-maven-plugin</artifactId>
            <version>${maven.build.helper.plugin.version}</version>
            <executions>
                <execution>
                    <id>add-source</id>
                    <phase>generate-sources</phase>
                </execution>
            </executions>
        </plugin>

    </plugins>
</build>
```

### Gradle

```groovy
repositories {
    maven {
        url "https://jitpack.io"
    }
}

dependencies {
    compile 'com.github.vbauer:jackdaw-core:1.0.0'
}
```

**TODO:** Finish section.


## Annotations

### @JAdapter
**TODO:** Finish section.

### @JBean
**TODO:** Finish section.

### @JBuilder
**TODO:** Finish section.

### @JClassDescriptor
**TODO:** Finish section.

### @JComparator
**TODO:** Finish section.

### @JFactoryMethod
**TODO:** Finish section.

### @JFunction
**TODO:** Finish section.

### @JMessage
**TODO:** Finish section.

### @JPredicate
**TODO:** Finish section.


## Building from source

MapStruct uses Maven for its build. To build the complete project run

```bash
mvn clean install
```

from the root of the project directory.


## Might also like

* [caesar](https://github.com/vbauer/caesar) - Library that allows to create async beans from sync beans.
* [houdini](https://github.com/vbauer/houdini) - Type conversion system for Spring framework.
* [herald](https://github.com/vbauer/herald) - Logging annotation for Spring framework.
* [commons-vfs2-cifs](https://github.com/vbauer/commons-vfs2-cifs) - SMB/CIFS provider for Commons VFS.
* [avconv4java](https://github.com/vbauer/avconv4java) - Java interface to avconv tool.


## License

Copyright 2015 Vladislav Bauer

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

See [LICENSE](LICENSE) file for details.