
## My Notes by Quarkus 

#### Prepare env for MacOS

Add to ~/.bash_profile
```
export JAVA_HOME=$(/usr/libexec/java_home -v 1.8)
export PATH=$JAVA_HOME/bin:$PATH
```

Full list of Java, CL
```
/usr/libexec/java_home -V
```

#### How to Run

##### How to Run dev app 
```
./mvnw compile quarkus:dev
```

##### How to Run tests
```
./mvnw test
```

   
## How to run native executable package with GraalVM  

* Run through GraalVM launcher
```
   gu install native-image
```

* Create package  
```
   ./mvnw package -Pnative
   ./target/disk-scanner-quarkus-1.0-SNAPSHOT-runner
   ./mvnw verify -Pnative
```   
      
* Run in docker    
```
   docker build -f src/main/docker/Dockerfile.native -t quarkus-quickstart/getting-started .
   docker run -i --rm -p 8080:8080 quarkus-quickstart/getting-started
```