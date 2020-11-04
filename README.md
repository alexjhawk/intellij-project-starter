# IntelliJ Project Starter for Ewon Development
This repository contains a starting project for Ewon development in the JetBrains IntelliJ IDEA IDE. 

**NOTE: Ewon development in IntelliJ is NOT supported or documented by Ewon!**

## Adding Ewon JTK as a JDK in IntelliJ

There are two ways to add the Ewon JTK to IntelliJ. The first way involves adding the `javaetk.jar` file from the ETK's lib folder as a library to a JDK that can source and compile Java 1.4 code. The second option is more reliable and carries across multiple projects in the same IDE, but involves more setup.

In the IntelliJ platform settings, click the `SDKs` tab and then click `+` to install a new JDK. Select the `Download JDK` option, then choose `BellSoft Liberica JDK` as the vendor, `1.8.0_xxx` as the version, leave the location as the default, and click `Download`.

After the download and installation of the BellSoft Liberica JDK 1.8.0_xxx version has been completed, change the name to something more identifiable, such as `JDK1.4`. Then, select all of the existing entries in the classpath of the JDK and remove them using the `-` button.

After the default/existing entries for the classpath have been removed, click the `+` button, and select the file `lib/javaetk.jar` in the Ewon Java ETK. Click `Apply` to save the changes and then click `OK` to close the window.

This newly added JDK can now be used for Ewon Java development as it only refers to the Ewon JTK on its classpath.

### Adding Created JDK to Project/Module

Open the module settings for the current module by right clicking the module name in the project explorer and selecting `Module Settings`.

Under `Project Settings`, select the `Project` page and under the `Project SDK` dropdown, select the JDK you previously created. Then, change `Project language level` to `1.4 - 'assert' keyword` and set `Project compiler output` to "bin".

Under `Project Settings`, select the `Modules` page and on the `Sources` tab, verify that the displayed lanaguage level is set to `Project default (1.4 - 'assert' keyword)` or `1.4 - 'assert' keyword`. On the `Paths` tab, select `Use module compile output path`, then set `Output path` to "bin" and `Test output path` to "bin\test".

Click `Apply` to save the changes, then click `OK` to close the projet structure dialog.

## Adding Source Folders to Project/Module

To add a source (src) folder to a project/module, simply right click on the folder and under `Mark directory as`, select `Sources root`. You will need to complete this for each source folder in the project. For example, you may need to mark `/src` and individual library source roots, `/lib/*/src`.

## Adding Ewon Ant Project to IntelliJ

To add the Ewon Ant project to IntelliJ, right click the `build.xml` file and click `Add as Ant Build File`. A tool window for Ant should appear on the right side of the IntelliJ window. If not, you can manually open the Ant tool window by selecting `View` > `Tool Windows` > `Ant`.

Within the Ant tool window, you can perform the `buildjar`, `deploy_ftp`, `startdeploy`, `startdeploy_debug` and `stop` Ant tasks. Prior to running each task, you must build the code in IntelliJ by selecting `Build` > `Build Project`. 

To automatically build source code prior to running each Ant task, you can right click the Ant task and select `Create Run Configuration`, which will create an IntelliJ run configuration. Ensure that the `Build` task is added under the `Before launch` tasks list before clicking `Apply` and `OK` to save the run configuration.

## Ewon Debugging in IntelliJ
Documentation on this topic is not yet available. Java debugging has been tested and works in IntelliJ, but requires a slight modification to the default build.xml file which is supplied by Ewon.



