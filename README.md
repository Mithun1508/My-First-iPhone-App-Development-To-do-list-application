# iPhone App Development: To-do list app

 #Productivity #ios development #Mobile development    

![Screenshot_2023-01-28-11-25-52-82_f9ee0578fe1cc94de7482bd41accb329_2](https://user-images.githubusercontent.com/93249038/215304690-a4d3e4c5-680e-4a07-85b4-912fd81e1f5d.jpg)


# TOPICS COVERED:
1) IGListKit (YouTube & insta component kit)
  
2) Yoga Layout(Implements the flexbox layout engine) invented by facebook 

3) Material Design libraries(Build beautiful, usable products using Material Components for Android) they've buttons already got actions sheets ,dialogues and cocoa-pods )

4) Dependency Injection(DI)

5) promises

6) Networking images 

7) Scroll View

 
# STEPS:

1) First thing to do is Download and Open up Xcode (which is Apple's developer program) for making ios Applications

2) Create Xcode Project -> Single View Application ->todo-list in the product Name . chose to go Over with Objective C over swift(only declartive way )which provides support for Cross platform development and performance infrastructure code

3) click on Build and Run then headover to the View Controller change the Uik controller to the UI navigation controller for Navigation Support going to initilise the constructor and then create the new UI view controller for the todolist container and then creates a new sub class for this Was given self.navigationItem.title = "@Todos" and then run the Application then I can see the title star showing up and we also give a bg color to make it white

4) At this point we have to put the scroll View which would be pretty dynamic for items being added and removed they'd like to reuse the Views so the UI elements they're recycled in on and off screen these are called recycler views .Tend to build the abstractions and frameworks on top of these collection views . we gonna be using something that instagram using called IGlIST Kit and also to note its used in the Youtube App as well as well as say component kit little texture we have a set of Objects it's just a data and the framework will be able to render this into a list of Scrollable items and if the frameworks changes it will take care of all the updates to get into the list of items uses and rendered.

5)  Next thing is to install cocoapods to get installed simply go to the directory edit a path file and run pod install. Once you installed then it installs frameworks into the Project and exit the app and reload it and its now ready to use and then we dont forget to import the IGlIST kit and it will Overrride the load view .so created a collection view and then assign this to the IGlist to manage .we have to fill in this stub methods for IG Lists. we're to going to confirm this to IG list adapter lists datasource and then fill 3 methods for this for this we need to create a section controller for which manages each of the Sections, so create a new class section controller which comes from IG list controller and they require objects for the list Adapter which is the data section know as to ToDO'S within that there is an individuial items for each to

6) coming into the Section controller starts filling this out Number of items returns 4 as of now will put in like a  min line spacings cell for the index will return nail for now and for item in the index we returns CG Size make container size .Got an error with the ill cell and create a cell class for that and override layout subviews primary method for drawing and also we override the initializer

7) Now in implementation Section this is where the recycling begins and we need to deque the cell that can be reusable and start import the cell right after this self.collection contacts Dq reusabler self class and then we returns a cell

8)  Next thing is to fillin that cells by creating an UI label giving some text and add it to the view and lay this out . we may need a button for deleting the items .So I'll create a delete btn we'll give it a frame .They provides you a auto layout stack views .but they dont provide as much flexibility as using flexbox

9) Next thing is try to pull the yoga layout Onto the framework .Go to the pot file and then put in a one-liner to bring it in and run pod install and fire to exit this application. Configure the layout with the block and put flexgrow equals 1 and I'll do the same for the delete btn .So now you can see the layout also would like to add the margin 8 pts of margin and for data filled we just have to create a ADD btn. So go to the Navigation bar and add a btns for adding new items .So create a new UI navigation bar item add which is a new UI bar and you can wired to call method will call that as an Add will create a private method add just put in a log to show when this is tapped .So if I run this you can see a tapped item and something shows up in the debugger .We can also checkout the debugger tool pause the app checkout the views inspect right click on things print it in the description using "pio" we can print out the various items print out all the cmds and print all the sub views. we gonna be clicking on the add item . we need a text field for the user to put in a to-do list item some sort of dialogue .I'm going to bring in another framework.

10) Now isntallation of materila design with cocoa-pods by using the cmds       
    pod 'MaterialComponents/Dialogs' install it and be able to use that dialog     right away. also use pod 'MaterialComponents/Buttons' and make sure everything is added on the target make a delete btn looks very nice and import the materials btn changes into a MVC btn type .so for dialog we already have an alert controller setup we copy that code and paste it to create an alert allow the user to input some text. There is a property called as accessory view we use to input a text input field. so lemme create that get a setup .So I be able to type in the text filed in the 2D view controller I just create an array of strings to do this and the initailiser will initailse it to an empty array
    # NOTE: working of IG LIST:
     IG List is very immutable we can create a new copy of the data and send it to an IG lISt kit so it will update the items

  Coming back, we add some textfiled.text to the new array and call update on self for the upadte we can simply call an adapter which performs update and add it to the initializer . we're to create  a breakpoint here adds a new item .Here the identifier is todo's .everytime its asking for the objects its just returns new items that will trigger the framework to update the section then it would populate new items under the section controller for agile is good.I just have packed just need to assign that into the cell dot x equals add the current index and I need to expose the property for that cell and now input an item in todo list.Last thing is when you press delete it actually gets a callback all the way upto section controller expose this delete btn in the property make it non -atomic read only and its going to be on when the user presses on the button in terms of abstraction we're at the section controller level each cell need its own controller create a cell controller to delete .Create a controller on the Ns Object and creates an array of thse and also instantiate the cell controller for each of the to do items .
 
 What We did so far: we created like callback block for triggering the updates it;s going to be instantiated in the top level view controller and then pass that on to the section controller which will be passed into the cell controller 
