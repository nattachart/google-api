### Authentication and Authorization

#### Terminology
* **Authentication** means the process of proving of one's identity that it is authentic. For example, a user proves him/herself to a web application by performing the login, providing the username and password.

* **Authorization** is an act that specifies access rights to resources for an identity. For example, a user can be granted for only reading a file, but not writing. For the case of YouTube API, an application that use the API may be granted the rights for only read data from YouTube, or user's account information, but not modifying the private information. This granting in YouTube or Google is done by the user who is the account owner.

* A **token** is something that represents something else, generally having higher value, such as a coin representing an amount of money. In the case of security, a token may be used to represent a pass of authentication, a result from an authorization. In the case of Google API, after a user grants permissions for an application (authorization), Google generates tokens that represent that authoziation (for the pair of the user and the application), and sends them back to the application. The application can store these tokens somewhere. When the application needs to perform specific actions that need authorization from the user again, it can just present the tokens to Google for verification. If the tokens are valid, Google allows the application to do what it requests according to the permissions having been granted by the user previously. Google now does not ask the user for authorization again. However, if the tokens are not valid, or absent, the user is going to be asked by Google whether he/she wants to grants the permission(s) to the application again.

* A **credential** is an item to be used in security, to represent something on behalf of an individual. For example, the username and password are credentials to represent a user. A Google's OAuth token is a credential to represent a set of authorized permissions.

#### Getting Credentials for the Application
This step is going to get credentials that represent your application. There are many types of applications that can use Google APIs as mentioned [here](https://developers.google.com/accounts/docs/OAuth2). It assumes that you have already created a project in [here](https://console.developers.google.com/project) already.

Your application can be classified as an installed application, which is neither a web application, client-side application, nor device application. Therefore, when you go to get the credentials (client ID and client secret) by going into your project in Google -&gt; APIs &amp; auth -&gt; Credentials, then click CREATE NEW CLIENT ID and choose "Installed application". You can also consult [here](https://developers.google.com/console/help/).

Then you will see Client ID and Client secret under "Client ID for native application". You can copy these two to replace "Enter ..." in __client_secrets.json__ in the directory __resources__ in [here](https://github.com/nattachart/google-api/tree/master/code/youtube).

#### Login and Logout
You can use the following __Auth__ class to let your application's users log in and out using their Google accounts. The code with examples is [here](https://github.com/nattachart/google-api/tree/master/code/youtube). You may also find its Java document [here](../code/youtube/doc/Auth.html).

#### Libraries Required
* [google-api-java-client-1.17.0-rc.zip](https://code.google.com/p/google-api-java-client/wiki/Setup#Download_Library_with_Dependencies)
* Servlet libraries
	* You can download and install Glassfish [here](http://www.oracle.com/technetwork/java/javaee/downloads/index.html?ssSourceSiteId=otncn)
	* Find all javax.servlet{any thing}.jar in {glassfish folder}/glassfish/modules
	* Include all of them into your project

### Libraries Links
* https://code.google.com/p/google-api-java-client/wiki/Setup#Download_Library_with_Dependencies
* http://www.oracle.com/technetwork/java/javaee/downloads/index.html?ssSourceSiteId=otncn
* http://javadoc.google-http-java-client.googlecode.com/hg/1.17.0-rc/index.html?overview-summary.html
* http://javadoc.google-api-java-client.googlecode.com/hg/1.17.0-rc/index.html
* http://javadoc.google-oauth-java-client.googlecode.com/hg/1.17.0-rc/index.html?overview-summary.html
