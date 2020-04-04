jettytestwebapp

-> maven created using maven-archetype-webapp 1.4
-> converted to support Servlet 3.1 using below answer

https://stackoverflow.com/questions/17910574/how-to-create-servlet-3-0-web-application-in-maven
{ There is still no good way of doing this. }

web.xml for servlet 3.1
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee 
		 http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd"
         version="3.1">
  <display-name>jettytestwebapp</display-name>
  <welcome-file-list>
    <welcome-file>index.html</welcome-file>
    <welcome-file>index.htm</welcome-file>
    <welcome-file>index.jsp</welcome-file>
    <welcome-file>default.html</welcome-file>
    <welcome-file>default.htm</welcome-file>
    <welcome-file>default.jsp</welcome-file>
  </welcome-file-list>
</web-app>


-> used jetty instead of tomact as servlet container
<plugin>
    <groupId>org.eclipse.jetty</groupId>
    <artifactId>jetty-maven-plugin</artifactId>
    <version>9.3.11.v20160721</version>
    <configuration>
        <webApp>
            <contextPath>/jetty</contextPath>
        </webApp>
    </configuration>
</plugin>

-> Also, refer below link to solve maven error or missing JRE.
https://mkyong.com/eclipse/eclipse-ide-no-compiler-is-provided-in-this-environment-perhaps-you-are-running-on-a-jre-rather-than-a-jdk/