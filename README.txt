Running Instruction:
Unzip ballnsocket.zip.
To generate PlantUML diagrams, install Graphviz software on your machine following the instructions here(http://plantuml.com/graphvizdot.html).
If you run it on Mac/Linux:
Open terminal, get into the umlparser¡¯s directory(should be in ballnsocket folder), run
$./umlparser ./testcase <output file name>

If you run it on Windows:
Open terminal, get into the /ballnsocket/target/ folder, run
$java -jar ballnsocket-1.0-SNAPSHOT-jar-with-dependencies.jar ./testcase <output file name>

The UML diagram will be generated in the testcase folder.


Compile Instruction:
Unzip ballnsocket.zip.
To generate PlantUML diagrams, install Graphviz software on your machine following the instructions here(http://plantuml.com/graphvizdot.html).
Install maven on your machine following the instructions here(https://maven.apache.org/install.html).
Open terminal, get into the ballnsocket folder, run:
$mvn clean compile assembly:single
A jar file named ballnsocket-1.0-SNAPSHOT-jar-with-dependencies.jar will be generated under /ballnsocket/target/ directory. (It will replace the one which has already been generated under the same directory)


This project is written by using javaparser and plantUML.
javaparser https://github.com/javaparser/javaparser
plantUML http://plantuml.com/

This project is constructed in IntelliJ IDEA 14. In pom.xml file, libraries and tools(javaparser, plantUML and maven) are imported by adding the following lines:
	<dependencies>
  	  <dependency>
  	      <groupId>com.github.javaparser</groupId>
    	    <artifactId>javaparser-core</artifactId>
    	    <version>2.1.0</version>
  	 </dependency>
    	<dependency>
        	<groupId>net.sourceforge.plantuml</groupId>
        	<artifactId>plantuml</artifactId>
        	<version>8031</version>
    	</dependency>
      </dependencies>

     <build>
        <plugins>
            <plugin>
                <artifactId>maven-assembly-plugin</artifactId>
                <configuration>
                    <archive>
                        <manifest>
                            <mainClass>Printer</mainClass>
                        </manifest>
                    </archive>
                    <descriptorRefs>
                        <descriptorRef>jar-with-dependencies</descriptorRef>
                    </descriptorRefs>
                </configuration>
            </plugin>
        </plugins>
     </build>