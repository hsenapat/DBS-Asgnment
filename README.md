# DBS-Asgnment
Step-1.
------

-- Kindly make sure you have JDK 1.8 is installed and latest maven is installed 
   Also make sure your JAVA_HOME and JDK_HOME is installed and your PATH env. variable points
   to JVM(both javac and java executable) and maven binary (mvn) for example.
   In My MaC OS X it looks like below.

   export PATH=$PATH:/Users/harry/Downloads/apache-maven-3.6.3/bin:/Library/Java/JavaVirtualMachines/jdk1.8.0_192.jdk/Contents/Home/bin:.

   Open Terminal and run 

   $java --version

   export M2_HOME=/usr/local/apache-maven/apache-maven-3.3.1 
   export M2=$M2_HOME/bin

   export MAVEN_OPTS=-Xms256m -Xmx512m

   Step-2.
   ------

   Unzip the enclosed ZIP file to a directory. You will get a dir. name called  "asgnment".Go inside that you will see a file called "TestDirUtility" 

  To Run the java application standalone
  ---------------------------------------

   You have to modify the program below two lines
  
   String pathName = "/Users/harry/practice/Java/asgnment/";
   File fileName   = new File("/Users/harry/practice/Java/asgnment/TestNewOne.java");

   and then execute the program the below two commands 

   javac -classpath .:/Users/harry/practice/Java/asgnment/json-simple-1.1.jar TestDirUtility.java
   java -classpath .:/Users/harry/practice/Java/asgnment/json-simple-1.1.jar TestDirUtility

   
  To Run the maven application for REST APIS
  ------------------------------------------

   Go inside the directory i.e asgnment/DirectoryUtility. You will see the "pom.xml"
   In my case /Users/harry/practice/Java/asgnment/DirectoryUtility.

   To Build and download the package fire the command 
   --------------------------------------------------

   $ mvn package  

   -- The above command will download and build the SPRING-BOOT project directory

   To run the SPRING-BOOT REST Server
   -----------------------------------

   $ mvn spring-boot:run  

   To run the SPRING-BOOT REST Client 
   -----------------------------------
   For Method-1:
   ------------
   Note: Use the curl command for the 1st Api Problem-1-a

   $ curl -X GET "http://localhost:8080/dir/listing/?pathName="/Users/harry/practice/Java/asgnment""
   
   The Output will be big here so i am not pasting... Refer to below method.

   For Method-2:
   ------------

   $curl -X GET "http://localhost:8080/dir/fileinfo/?fileName="/Users/harry/practice/Java/asgnment/TestDirUtility.java""

   Output will be
   --------------
   {"canExecute":true,"AFilePath":"\/Users\/harry\/practice\/Java\/asgnment\/TestDirUtility.java","canRead":true,"canWrite":true,"lastModified":"1594477618000 millis","isHideen":false}

   When you cut and paste it in a JSON beautifier by going to link https://codebeautify.org/jsonviewer the corresponding output will be 

  {
  "canExecute": true,
  "AFilePath": "/Users/harry/practice/Java/asgnment/TestDirUtility.java",
  "canRead": true,
  "canWrite": true,
  "lastModified": "1594477618000 millis",
  "isHideen": false
  }
   Note : For above two please change the fileName or pathName to an existent file in your file system.


   To Execute the Unit Test 
   -----------------------------------
   Create a directory called Documents and create a file called testFile.txt like below

   For example mkdir ~/Documents and touch ~/Documents/testFile.txt

   $ cd asgnment/TestDirUtility , where pom.xml resides and execute the below command
  
   $ mvn test. It will execute the test cases

   To open the javadoc index.html 
   ------------------------------
   $ cd /Users/harry/practice/Java/asgnment/DirectoryUtility/src/main/java/com/haraprasad/io/DirectoryUtility

   open the docs/index.html. You will see the javadoc for the below 3 files

   -DirectoryFileUtilityService	 
   -DirectoryUtilityApplication	 
   -DirectoryUtilityController

   ------------------O-X-O----------------------
