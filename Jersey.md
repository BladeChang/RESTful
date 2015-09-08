# Jersey Tutorial #

## Create First Jersey Project with Maven ##
1. **Setup the Maven with window**
	1. 參考 [https://maven.apache.org/install.html](https://maven.apache.org/install.html "安裝Maven")
	2. 有關proxy設定:
		1. 在C:\Users\你的是用者\.m2找到**settin.xml**
		2. 在<proxies\>下新增<proxy\>
		>
		  	<proxy>
			<id>optional</id>
	      	<active>true</active>
	      	<protocol>http</protocol>
	      	<username></username>
	      	<password></password>
	        <host>172.16.20.16</host>
	      	<port>8080</port>
	      	<nonProxyHosts>local.net|some.host.com</nonProxyHosts>
	      	</proxy>
		>	
2. **Create a Jersey Project with Maven command:**
	>  
		mvn archetype:generate -DarchetypeArtifactId=jersey-quickstart-grizzly2 -DarchetypeGroupId=org.glassfish.jersey.archetypes -DinteractiveMode=false -DgroupId=com.example -DartifactId=simple-service -Dpackage=com.example -DarchetypeVersion=2.21
	>

	 	

	- 執行完畢後可以在執行的目錄下找到**simple-service**(project root)資料夾	  
	-	project root下會產生一個pom.xml
	-	project source會在src/main/java下
		1. Main.java
		2. MyResource.java
	-	project test source會在src/test/java下
		1. MyResourceTest.java
	
		
3. **Running the Project**
	>
		mvn clean test
	>
	執行完畢可看到以下結果:
	>
		Results :
		Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
		[INFO] ------------------------------------------------------------------------
		[INFO] BUILD SUCCESS
		[INFO] ------------------------------------------------------------------------
		[INFO] Total time: 39.916 s
		[INFO] Finished at: 2015-09-08T14:50:56+08:00
		[INFO] Final Memory: 13M/31M
		[INFO] ------------------------------------------------------------------------
	>
	在接著執行
	>
		mvn exec:java
	>
	>顯示下圖表示你已經成功建立你的第一個RESTful Project
	
	>![](http://i.imgur.com/8mP6sVD.jpg)

4. **其它類型專案 Maven Commands**
	1. Creating a JavaEE Web Application
		>
			mvn archetype:generate -DarchetypeArtifactId=jersey-quickstart-webapp -DarchetypeGroupId=org.glassfish.jersey.archetypes -DinteractiveMode=false -DgroupId=com.example -DartifactId=simple-service-webapp -Dpackage=com.example -DarchetypeVersion=2.21
		>
		執行
		>
			mvn clean package
		>
		>執行完畢 war當產生路徑 *"./target/simple-service-webapp.war"*
		- 注意:你的servlet container 必須要支援Servlet2.5或更新的版本.
		>
	2. Creating a Web Application that can be deployed on Heroku
		>
			mvn archetype:generate -DarchetypeArtifactId=jersey-heroku-webapp -DarchetypeGroupId=org.glassfish.jersey.archetypes -DinteractiveMode=false -DgroupId=com.example -DartifactId=simple-heroku-webapp -Dpackage=com.example -DarchetypeVersion=2.21
		>

