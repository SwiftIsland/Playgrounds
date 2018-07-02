# Creating an interactive readme in playgrounds
Most of this tutorial is based on the WWDC talk [Getting the Most out of Playgrounds in Xcode](https://developer.apple.com/videos/play/wwdc2018/402/) So if you want to know more i recommend looking at it.

## Basic playground introduction

### Where is what and what is where again?
![run.png](run.png)

First open a new Playground in XCode 10. Now there are two ways in which you can run the playground code. 
1.  Down at the left to run the enitre playground
2. Or you can use the play button on the lines

![inline-result.png](inline-result.png)

By selecting the box you can show the result inline, so you can see the changes you make. When using the new play button, you can add a line that changes your view and only run that line to be able to see the quickest results!

### The live view
If you want to see the result of ViewControllers you can set the current liveView to your viewController:
`PlaygroundPage.current.liveView = ViewController`
Dont' forget to `Import PlaygroundSupport` when you do this.

![live-view.png](live-view.png)

Show the assistant editor to make your live view visible

![lost-live-view.png](lost-live-view.png)

Pro-tip: When you lose your live view you can reselect it in this drop down menu by choosing Live View instead of Manual.

### Files
![add-files.png](add-files.png)

When you show the navigator you can add files to your playground

![images.png](images.png)

Add images to the `Resources` folder

![files.png](files.png)
Add Code files to the `Sources` folder. Don't forget to make the classes or entenstions public!

![code.png](code.png)
And you can use the extension in your playground code.

Pro-tip. When debugging these code files breakpoints don’t get hit, so debug them by either using print statements, or just add the code to your playground page to make full use of inspection and when you are happy with it move them to a separate code file.

## Creating the README

### Adding playground to a framework

When you want to add a playground to a framework, open the `.xcodeproj` file of the framework and add a new playground by going File > New > Playground.

Remember to always open the  `.xcodeproj`  file and not just the playground, otherwise it won’t be able to access the framework.

Don't forget to build the framework before you play your playground!

Still having trouble? Here are some other tips:

![platform.png](platform.png)

- make sure you have the build target for you framework set to the same platform as your playground
-
-

### Playground description

Implement `playgroundDescirption` from the `CustomPlaygroundDisplayConvertible` protocol as an extension to the entiity you want to add the description to:

```
import UIKit

extension NSObject: CustomPlaygroundDisplayConvertible {
    public var playgroundDescription: Any {
        return "Whatever you want"
    }
}
```
You can do this in your Playground Page or add it as a separate file in your Sources folder.

Pro-tip: If you add a separate file, don't forget to build again!

### Markdown

For the possibilities of markdown in Playgrounds check [this](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_markup_formatting_ref/index.html) out

![markdown.png](markdown.png)

Simply tick the render documentation box in the inspector and the markdown is displayed.

### Playground Pages

![new-page.png](new-page.png)

To be able to add more info for your users without cluttering the playground, you can add multiple playground pages.

![new-page2.png](new-page2.png)
When you add a new Playground Page the page you had before will automatically get it’s own sub page as well. And the links to the previous page are also automatically added.






