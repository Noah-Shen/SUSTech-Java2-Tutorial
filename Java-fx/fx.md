# JavaFX Sample Tutotial
This tutorial is based on the jdk8, if your java version is higher than 8, using internet to solve it.



------

 # If you are using Eclipse as your IDE:

## How to install e(fx)eclipse and Scene Builder 
   This part will introduce how to develop and run JavaFX programe on Eclipse IDE.
   To start the journal, it is neccessriy to set up the environment and tools for helping us programe on Eclipse. 

### e(fx)eclipse
The Eclipse e(fx)clipse project provides tooling and runtime components that help developers create JavaFX applications. e(fx)eclipse is a set of tools and necessary library. It is going to help you execute JavaFX program, so you need to make sure that you have already download it and installed successfully on your eclipse. If you haven't installed e(fx)eclipse yet, I hope the tutorial below will do you a favor:

   Chinese:http://www.yiibai.com/javafx/install-efxclipse-into-eclipse.html
   
   English:http://wiki.eclipse.org/Efxclipse/Tutorials/AddingE(fx)clipse_to_eclipse#Installing_e.28fx.29clipse_IDE.

### JavaFX Scene Builder
   JavaFX Scene Builder is a visual layout tool that lets users quickly design JavaFX application user interfaces, without coding. Users can drag and drop UI components to a work area, modify their properties, apply style sheets, and the FXML code for the layout that they are creating is automatically generated in the background. The result is an FXML file that can then be combined with a Java project by binding the UI to the application’s logic. 
   
Chinese:http://www.yiibai.com/javafx/install-javafx-scene-builder-into-eclipse.html

English:https://o7planning.org/en/10621/install-javafx-scene-builder-into-eclipse

--------

# If you are using Intellij IEDA as your IDE:

You only need to download JavaFx Scene Builder and javafx plugin.

English:https://www.jetbrains.com/help/idea/preparing-for-javafx-application-development.html

Chinese:https://blog.csdn.net/hst_gogogo/article/details/82530929

-------

# 1. Create Project

Open Eclipse, Select:
- File -> New -> Project

- Select JavaFX Project
![](Picture1.png)
- Named your project
![](Picture2.png)
After all, your project structure will look like:
![](Picture3.png)
Then, let us make sure that JAVA2LAB3Demo excute successfully, right click on the main class (Main) and select:
- Run As -> Java Application
 ![](Picture4.png)
- JAVA2Lab3Demo application is running, and the result is blank  as follows:
- ![](Picture5.png)
------
For Intellij IEDA
- File -> New -> Project
![](picture34.png)
- Select JAVAFX on the left
![](picture35.png)
- Next -> type name -> Finish


# 2. JAVA2Lab3Demo example description
In the above steps, JAVA2Lab3Demo application have successfully been created and run .

In general, a JavaFX application will have three major components namely Stage, Scene and Container, Layouts and Controls as shown in the following diagram.
![](Picture6.png)
For details:https://www.tutorialspoint.com/javafx/javafx_application.htm

# 3. Using JavaFX Scene Builder Demo
This is a small example of using Scene Builder to design an application interface. The model of MVC applied to this example is as follows:
![](Picture8.png)
- Display on VIEW
- User use CONTROLLER
- operate data(Create, update, delete,..) on Model
- Display data from MODEL on VIEW

Next step, we are going to create a new mainUI.xml file.
- File -> New -> Other…
![](Picture9.png)
![](Picture10.png)
- Type the name of file: "mainUI" or other name.(Root element should be VBox)
![](Picture11.png)
- the result should be below:
![](Picture12.png)

we can use JAVAFX Scene Builder to open fxml format file.
![](Picture13.png)
if you use IDEA:
![](picture33.png)
- mainUI.fxml design should look like:
![](Picture14.png)

- Set the properties of the VBox
![](Picture15.png)
![](Picture16.png)
![](Picture17.png)
- Drag and drop a label into the VBox 
![](Picture18.png)


- Set its Text to the text to display (For example: "Click the button to learn the meaning of life")
- Continue to set the font and text color 
![](Picture19.png)
- Drag and drop a ImageView into the VBox
![](Picture20.png)
- click "..." select a photo
![](Picture21.png)
![](Picture22.png)

- Drag and drop a Button into the VBox
![](Picture23.png)

- Set it's Text to the the to display(For example:"Click to Learn")

- Continue to set the font and text color
![](Picture24.png)
- set method "moveWindow", call when mouse entered
![](Picture25.png)

- Select "File" -> "Save" 
- Select "Preview" -> "Show Preview in Window" to preview your design
![](Picture26.png)

- After all, your design should be:
![](Picture27.png)

- Close JAVAFX Scene Builder and refresh project on eclipse, you can view your code in mainUI.fxml
![](Picture28.png)

- Add the property fx:controller to <VBox>, which will have a reference to a control inside the VBox (such as myButton).
![](Picture29.png)

- At this point, we create a new class in the application package, named MainUIxml, remember that the name of this class should be the same as the one set in fxml.
![](Picture30.png)
- MainUIxml.java:
![](Picture31.png)
- Main.java
![](Picture32.png)







# Advanced
For people whose jdk version are higher than 8.
## JavaFX in Java 9
JavaFX did not get a lot of new features in Java 9, but it did get 750+ bug fixes, so if you are planning to build a new JavaFX app from scratch, you might want to consider starting with Java 9 !

## JavaFX From Java 11
From Java 11, JavaFX has been removed from the Java SDK again. JavaFX has been detached into its own open source project. This means that to download JavaFX from Java 11 / JavaFX 11, you have to go to:

http://openjfx.io


# Reference:

http://www.yiibai.com/javafx/install-efxclipse-into-eclipse.html

http://wiki.eclipse.org/Efxclipse/Tutorials/AddingE(fx)clipse_to_eclipse#Installing_e.28fx.29clipse_IDE.

https://www.jetbrains.com/help/idea/preparing-for-javafx-application-development.html

https://blog.csdn.net/hst_gogogo/article/details/82530929

http://openjfx.io
