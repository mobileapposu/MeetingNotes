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
Storyboards allow us to declare interfaces. If you click on the .storyboard file in your project, the interface builder will open and you'll see what looks like an iPhone screen. 

#### Images.xcassets

#### info.plist

#### Launch.xib
