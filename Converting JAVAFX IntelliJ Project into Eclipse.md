Do these following steps:  

1.  Open Eclipse -> Help -> Eclipse Marketplace
2.  Search for "javafx"
3.  You'll see e(fx)eclipse, install it.
4.  After installation, restart eclipse
5.  Then create new project File > New > Project(don't select Java project).
6.  Then Select JavaFX > JavaFX Project
7.  Then click Next, give project name and click Finish
8.  You'll get "The import javafx cannot be resolved"
9.  Download JavaFX in here [JavaFX](https://gluonhq.com/products/javafx/)
10.  Extract the folder and place it downloads folder (or anyplace)
11.  Then in eclipse right click the project and select properties
12.  Choose Java Build Path
13.  Then select Libraries tab (you'll see tabs on the top)
14.  You'll see Classpath > JavaFX SDK
15.  Click on Classpath, then click Add external JARs from the right.
16.  Then from the download JavaFX (placed in downloads folder or somewhere you've placed).
17.  Choose all the .jars file in Downloads/javafx-sdk-11.0.2/lib/(all .jar(s) file) and click open.
18.  Then click Apply and Apply and close.
19.  Then you won't get red underlines or (error).
20.  Then right click on project > Run as > Run configuration
21.  Choose the arguments tab and type this in VM arguments.

```
    --module-path /path/to/JavaFX/lib  --add-modules=javafx.controls,javafx.fxml
```

22.  (Important) Then uncheck the box that says "Use the -XstartOnFirstThread..."
23.  Click Apply and Run.