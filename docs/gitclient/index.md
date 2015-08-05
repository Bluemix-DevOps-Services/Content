#Setting up local clients to work with Git source control 

###### Last updated: 29 May 2015

If you use a Git repository for your IBM&reg; Bluemix&trade; DevOps Services project, you can manage your repository and work locally or in the DevOps Services Web IDE. You can either use the command line to access your repository or, if you work in Eclipse, install the EGit plug-in for version control.

If you use the Track & Plan feature and you want to manage your project plans and work items locally from Eclipse, install the IBM Rational Team Concert™ plug-in.

* [Accessing your Git repository from your DevOps Services project](#access_git)
* [Connecting the Track & Plan feature to Rational Team Concert](#eclipse_using_rtc)
* [Developing with Bluemix Live Sync and Node.js](#livesync)
* [Developing with IBM Eclipse Tools](#etools)

<a name='access_git'></a>
## Accessing your Git repository from your DevOps Services project

If you have a DevOps Services project that uses Git, you can connect the project to a Git repository in two ways:

* [Option 1: Accessing your repository by using command-line Git](#command_line_git)
* [Option 2: Accessing your repository by using Eclipse and the EGit plug-in](#eclipse_using_egit)

<a name='command_line_git'></a>
### Option 1: Accessing your repository by using command-line Git

If you know how to use the command line with Git, you can use this method to manage your repository. 

<a name='clone_your_git_project_from_the_command_line'></a>
#### Cloning your Git project from the command line

Create a local copy of the project files by cloning the Git repository so that you can access the contents of your repository outside the Web IDE. 

**Before you begin**

Check whether Git is installed. On a command line, type `git version`. If Git is installed, the version number is shown and you can begin. If Git is not installed, [go to the Git website](http://git-scm.com/downloads). Download and install the version for your operating system. You can accept the default installation values.

**Cloning your project**

1. Sign in to [DevOps Services](https://hub.jazz.net/).

2. Navigate to your project page.

2. From the right side of the page, copy the content of the **Git URL** field.  
 **Note**: DevOps Services supports the HTTPS protocol for Git URLs. The SSH and Git protocols are not supported.  
![The Git URL field on the Project page.][3]
3. Open a command line.

4. Change the directory to where you want the local copy of the Git repository to be.

5. Type `git clone`, paste the Git URL, and press Enter. When prompted, type your alias and IBM id password.

After the download is complete, you have a local repository of the files for your project. For more information about using Git, [see the Git documentation](http://git-scm.com/doc).

<a name='eclipse_using_egit'></a>
### Option 2: Accessing your repository by using Eclipse and the EGit plug-in


If you use Eclipse and have a project that uses Git for source control, you can use the EGit plug-in to manage your repository from Eclipse. 

<a name='install_the_egit_eclipse_plugin'></a>
#### Installing the EGit Eclipse plug-in

**Before you begin**: 

* If you use Eclipse 4.2.2 or later, complete these steps. If you use an earlier version of Eclipse, [see the EGit/FAQ page for instructions](http://wiki.eclipse.org/EGit/FAQ#Where_can_I_find_older_releases_of_EGit.3F).  
* If you do not have Eclipse installed and want tools for Java™ development, [download and install Eclipse IDE for Java EE Developers](http://www.eclipse.org/downloads/packages/eclipse-ide-java-ee-developers/keplersr2).  
* If you do not have Java 1.7 installed, [download and install the Java SE Development Kit](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html).
* Check whether the EGit plug-in is already installed. In Eclipse, click **Window > Show View > Other** and type `git` as the filter text. If you see a list of Git views, skip to [Connect to your DevOps Services project by using EGit](#connect_to_your_devops_services_project_with_egit).

**Installing the plug-in**
1. In Eclipse, click **Help > Install New Software...**.

2. In the Install window, complete these steps:
  1. In the **Work with** field, type `http://download.eclipse.org/egit/updates` and click **Add...** and type a name for this install repository.
  2. In the Eclipse Git Team Provider section, select only the **Eclipse Git Team Provider** check box.
![Installing the Eclipse Git Team Provider][21] 

  3. Click **Next** and click **Next** again.
  4. Review the license terms. If you agree to the terms, accept them.
  5. Click **Finish** to install the plug-in.
4. If you see a security warning message, click **OK**.

5. If you are prompted to restart Eclipse, click **Yes**.

<a name='connect_to_your_devops_services_project_with_egit'></a>

#### Connecting EGit to your DevOps Services project

1. In Eclipse, click either [newer] **Eclipse > Preferences > General > Workspaces** or [older] **Window > Preferences > General > Workspaces**. In the Text file encoding field, click **Other** and from the list, select **UTF-8**.

1. In [DevOps Services](https://hub.jazz.net/), browse to your project page. 

2. On the right side of the page, copy the **Git URL**.  
 **Note**: DevOps Services supports the HTTPS protocol for Git URLs. The SSH and Git protocols are not supported.  
![The Git URL field on the Project page.][3]

3. In Eclipse, click **File > Import**.

4. In the Import window, click **Git > Projects from Git**, and then click **Next**. 

5. Select **Clone URI** and click **Next**. 

6. In the **URI** field, paste the Git URL.

7. In the Authentication section, type your alias and IBM id password, and then click **Next**.

8. Select the branches to work on and click **Next**.

9. If necessary, update the local destination directory for the cloned repository and click **Next**. 

10. Click **Import as general project** and click **Finish**.

11. Type a project name and click **Finish**.

12. To work on this project, click **Window > Open Perspective**, select **Other** and select **Git**.  The Git Repositories view lists your connected Git repositories.  You could also use the **Project Explorer** view.

<a name='eclipse_using_rtc'></a>
## Connecting the Track & Plan feature to Rational Team Concert

If you use Eclipse, you can use the Rational Team Concert plug-in to access your work items.

<a name='install_eclipse_and_the_rational_team_concert_plugin'></a>
### Installing the Rational Team Concert plug-in

**Before you begin**

* Rational Team Concert 5.0.2 and later requires Eclipse 4.3.2. Eclipse requires Java 1.7.  
* If you do not have Eclipse installed and want tools for Java development, [download and install the  Java EE IDE for Eclipse](http://www.eclipse.org/downloads/packages/eclipse-ide-java-ee-developers/keplersr2).  
* If you do not have Java 1.7 installed, [download and install the Java SE Development Kit](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html).

**Installing the plug-in**

1. In Eclipse, click **Help > Install New Software**.

3. In the Install window, complete these steps:

  1. In the **Work with** field, type `https://jazz.net/downloads/rational-team-concert/5.0.2/5.0.2/p2` and click **Add...** and type a name for this repository.
  2. Press **OK** to load the contents of the update site.
  3. Select the **Rational Team Concert Client** check box.
  4. Select the **Group items by category** check box.
  5. Click **Next** and click **Next** again.
  6.  Review the license terms. If you agree to the terms, accept them.
  7.  Click **Finish** to install the plug-in.

6. If you see a security warning message, click **OK**.

7. If you are prompted to restart Eclipse, click **Yes**.

<a name='connect_to_your_devops_service_projects_from_eclipse'></a>
## Connecting to your DevOps Services project from Eclipse

1. In Eclipse, click **Window > Show View > Other... > Team > Team Artifacts**.
2. Click the **Manage IBM DevOps Services Projects** icon, which is visible under the Team category. 
 ![Manage IBM DevOps Services Projects button within the Team Artifacts view](./images/jazzhubfeature.png)    
3. In the Connect to IBM DevOps Services window, type your alias and IBM id password to sign in to Bluemix DevOps Services, and then click **Next**.
4. Select the Bluemix DevOps Services projects to connect to and click **Finish**.
5. Use the Work Items or My Work view to work with work items.

<a name='livesync'></a>
## Developing with Bluemix Live Sync and Node.js

If you are developing a Node.js app, you can make changes to static files, such as HTML or CSS, and immediately propagate the changes to the deployed app by using the Bluemix Live Sync. 

In the Web IDE, turn on Live Edit mode. You can see your updated static files by refreshing the app in your browser. If you update a node module, use the **Quick Restart** icon to restart the node run time in seconds, without redeploying the app.
![The Quick Restart icon.][23]


With the Debug feature of Bluemix Live Sync, you can create breakpoints and inspect variables in your node modules so that you can isolate problems as you work. For more information about Bluemix Live Sync, [see the Bluemix Live Sync documentation][1].

<a name='etools'></a>
## Developing with IBM Eclipse Tools

IBM&reg; Eclipse Tools for Bluemix&trade; provides plug-ins that you can install into an existing Eclipse environment to assist in integrating your IDE with Bluemix.

With the tools, you can deploy the following types of files and servers to the Bluemix server directly from your Eclipse IDE or from IBM&reg; WebSphere&reg; Application Server Developer Tools (WDT):
* JavaScript files
* WAR (web archive) files
* EAR (enterprise archive) files
* Liberty Profile packaged servers

You can also create services and link them to your app, and define environment variables as part of the deployment. For more information about IBM Eclipse Tools, [see Deploying apps with IBM Eclipse Tools for Bluemix][2].


[1]: https://www.ng.bluemix.net/docs/#manageapps/bluemixlive.html
[2]: https://www.ng.bluemix.net/docs/#manageapps/eclipsetools/eclipsetools.html#eclipsetools
[3]: images/gitURL.png
[18]: https://developer.ibm.com/answers/questions/?community=devops-services (Bluemix DevOps Services forum)
[19]: mailto:hub%40jazz.net
[20]: /docs
[21]: images/egit_team_provider.png
[22]: images/rtc_client_feature.png
[23]:images/quick_restart.png

