#How to use properties in maven

##Using external properties
You can put properties to an external properties file. 
__It is not allowed to pass version properties in external files. Maven will try to load the version for all dependencies and plugins at the same time. So maven won't know which version of the properties-plugin to use for loading properties. It is a classical chicken-or-egg-problem__

##Property defined in properties block
Define your property in the properties block of the pom.xml  
E.g:  
	<properties>  
		<build.props.path>${basedir}/src/main/resources/build.properties</build.props.path>  
		<maven.compiler.source>1.8</maven.compiler.source>  
		<maven.compiler.target>1.8</maven.compiler.target>  
		<properties-maven-plugin.version>1.0.0</properties-maven-plugin.version>  
		<!-- Manage dependency version by properties -->  
		__<commons.version>2.6</commons.version>__  
	</properties>  

##Pass property on command line
To override the properties defined in pom.xml, pass them on the command line  
__mvn install -Dcommons.version=2.6__