# Notes from Hello, World! on iOS
Our first iPhone App - created from the "Single-View Application" template
### What are all of these files?
The iOS project structure can be confusing at first. I hope to remedy that a bit by explaining the different file types you may find.
#### Files that start with .h or .m
All files with these extensions (called header and class files respectively) contain Objective-C code that controls different parts of the app. They typically come in pairs, each class file having a corresponding header. Header files contain declarations of most functions and variables that the class file will use. 

This construct comes from Objective-C's roots in C. In traditional C code, any you wish to create a function, you must declare its structure before implementing it. For example:
```
//Declare functions at the top, or header, of our C file
//If we remove this line, our code won't compile!
int add(int x, int y);

int main(){
	int b = add(5,2);
}

//Here is where we actually implement our function...
int add(int x, int y){
	return x+y;
}
```
In Objective-C, these declarations are moved to a separate file (header) for a combination of readability and a few compiler (preprocessor) tricks. The important takeaway here is that the main code that controls how our app runs lives inside of these files.

#### Storyboard File
Storyboards allow us to declare interfaces. If you click on the .storyboard file in your project, the interface builder will open and you'll see what looks like an iPhone screen. Interface Builder actually used to be a separate and bulky application, but now it's completely integrated into Xcode. From here, you can control the UI objects you wish each screen to have, as well as the different ways in which your Objective-C code interacts with the interface.

One note - Storyboard files are actually collections of different screens. They call each screen a "scene". The advantage of having these collection objects is that they allow you to map out your entire app and easily setup transitions between different scenes. Pretty cool stuff!

#### Images.xcassets
This is where you should store any images you want pre-loaded into your app. You can create image sets where you can specify different sized images to use when the same image appears on different devices.

#### info.plist
This file specifies some of the core project settings. Plist files are just XML. Most of the time, you won't need to manipulate this file directly. More project settings can be found by clicking on the project file in Xcode.

#### Launch.xib
xib stands for XML-Interface-Builder file, which means exactly what it sounds like. This file is different than a storyboard in that it only contains one screen. The Launch.xib is the screen that appears at launch. This screen used to just be a static image, but it recently has become a customizable XML screen so as to suit different screen sizes.

### How do we make things work?
The Hello, World! app we made mainly makes use of two different Objective-C constructs - IBOutlets and IBActions.

IBOutlets allow us to map interface builder items to Objective-C variables. IBActions allow us to map interface actions (for example, when the user presses a button) to Obj-C methods or functions. Both of these need to be declared in the header file in order for them to be recognized by Interface Builder. Take note of the placement of each of these:
```
/*
 * ViewController.h
 */
#import <UIKit/UIKit.h>
@interface ViewController : UIViewController
{
    //Variables should be declared here
    IBOutlet UILabel *myLabel;
}
//Methods should be declared here
-(IBAction)buttonPressed;
@end
```
We can then go into the interface builder inspector and connect both the outlet and the action to a real object. Check out the Hello, World! project on GitHub to see how we can use these objects to create a small interactive app.

### Useful Links
[]()
