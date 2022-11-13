# STEPS:
1. Create a new project
2. Open terminal and type
```
mvn clean compile
```


Stage 
Scene
  
# Basic Structure:
```java
package com.example.exitfx;  
  
import javafx.application.Application;  
import javafx.fxml.FXMLLoader;  
import javafx.scene.Scene;  
import javafx.stage.Stage;  
  
import java.io.IOException;  
  
public class HelloApplication extends Application {  
  
  
  
    public static void main(String[] args) {  
        launch(args);  
    }  
  
    @Override  
    public void start(Stage stage) throws Exception {  
  
  
        stage.show();  
    }  
}
```


```java
//new stage
Stage stage = new stage();
//create a root node
Group root = new Group;
//new scene {Scene requires a root node as argument}
Scene scene = new Scene(root);
//set scene {we pass the scene to the stage}
stage.setScene(scene);
//set title of main window
stage.setTitle("Title here");
//to view the stage window
stage.show();
//to set icon in the stage window put a an image in the source folder and make new image and pass it as an argument as below:
Image icon = new Image("Image name here");
stage.getIcons().add(icon);
//To set the width and height of the stage
stage.setWidth(1280);
stage.setHeight(1024);
//Make Borderless Window
stage.initStyle(StageStyle.UNDECORATED);
//Adding hex color
Color.valueOf("0F1A20")
//cannot resize stage window
stage.setResizable(false);
//position of application on the screen at launch
stage.setX(x);  
stage.setY(y);
//Full screen method
stage.setFullScreen(true);
//Change full screen exit hint
stage.setFullScreenExitHint("Any text here will appear as hint");
//Change full screen exit key
stage.setFullScreenExitKeyCombination(KeyCombination.valueOf("any key 
"here"));

//SCENES

/*We can also pass width and height directly in scene constructor
It adjust the size of stage according to the width and height of scene*/
Scene scene = new Scene(root,800,600); 
/*We can also pass color in scene constructor along with width and height*/
Scene scene = new Scene(root,800,600,Color.Black); 
//Create a new text object
Text text = new Text();
/*To set text in text object either pass String directly into the text object constructor or use following:*/
text.setText("THE GYM GURU");
/*After setting text in text object we need to specify where our text should display on scene so we set co-ordinates as:*/
text.setX(50);  
text.setY(150);
/*After setting co-ordinate we need to add the text box to the root node object as, we can also pass any other node to the group object*/
root.getChildren().add(text);
//Changing Font, Pass font name and font size as argument
text.setFont(Font.font("Verdana",32));
//Change Text Color
text.setFill(Paint.valueOf("White"));
text.setFill(Color.WHITESMOKE);
//Create and edit line
Line line = new Line();  
line.setStartX(200);  
line.setStartY(200);  
line.setEndX(500);  
line.setEndY(200);  
line.setStrokeWidth(5);  
line.setFill(Color.WHITESMOKE);

//CREATE AND EDIT RECTANGLE
Rectangle rectangle = new Rectangle();
rectangle.setX();
rectnagle.setY();
rectnagle.setWidth();
rectangle.setHeight();
rectangle.setFill(Color."color");
rectangle.setStrokeWidth();
rectangle.setStrokColor();

//CREATE TRIANGLE
Polygon triangle = new Polygon();
triangle.getPoints().setAll()(
	200.0, 200.0,
	300.0, 300.0,
	200.0, 300.0
);
triangle.setFill(Color."color");

//CREATE CIRCLE
Circle circle = new Circle();
circle.setCenterX();
circle.setCenterY();
circle.setRadius();

//Adding Image
//Copy file paste in your source folder of project folder
Image image = new Image("name");
ImageView imageview = new ImageView(image);
imageview.setX(150);
imageview.setY(150);










```