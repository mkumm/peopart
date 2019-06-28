# peopart
Sample iOS and watchOS application

![Resulting Application Demonstration](/assets/demo.gif?raw=true "Resulting Application")

## Step 1 - Setup UI Navigation Structure

### Concepts

* Understand Basic Swift Syntax
* Understand Basic Xcode IDE and Project Structure 
* Understand the structure of view controllers and how to display them
  * [UIAppDelegate](https://developer.apple.com/documentation/uikit/uiapplicationdelegate)
    * **Description**
      * Handles the various states and outside entry points into the application  
    * **Properties and Methods**
      * [application(_:willFinishLaunchingWithOptions:)](https://developer.apple.com/documentation/uikit/uiapplicationdelegate/1623032-application) 
        Setup the `UIWindow` for the `main` `UIScreen` with the root `UIViewController` 
  * [UIWindow](https://developer.apple.com/documentation/uikit/uiwindow)
    * **Description**
      * Backdrop of the UI 
    * **Properties and Methods**
      * [init(frame:)](https://developer.apple.com/documentation/uikit/uiwindow)
        Setup a new `UIWindow` based on the `UIScreen`
      * [rootViewController](https://developer.apple.com/documentation/uikit/uiwindow/1621581-rootviewcontroller)
        The root `UIViewController` 
      * [makeKeyAndVisible()](https://developer.apple.com/documentation/uikit/uiwindow/1621601-makekeyandvisible)
        Make the `UIWindow` key and visible
  * [UIScreen](https://developer.apple.com/documentation/uikit/uiscreen)
    * **Description**
      * Properties associated with a hardware-display
    * **Properties and Methods**
      * [main](https://developer.apple.com/documentation/uikit/uiscreen/1617815-main)
        the main screen of the device
  * [UIViewController](https://developer.apple.com/documentation/uikit/uiviewcontroller)
    * **Description**
      * Base View Controller 
  * [UITabBarController](https://developer.apple.com/documentation/uikit/uitabbarcontroller)
    * **Description**
      * `UIViewController` which contains a series of bottom tabs
    * **Properties and Methods**
      * [setViewControllers(, animated: Bool)](https://developer.apple.com/documentation/uikit/uitabbarcontroller/1621177-setviewcontrollers)
        Set the `UIViewController` for each tab
  * [UINavigationController](https://developer.apple.com/documentation/uikit/uinavigationcontroller)
    * **Description**
      * `UIViewController` for allowing tree-like navigation
    * **Properties and Methods**
      * [init(rootViewController:)](https://developer.apple.com/documentation/uikit/uinavigationcontroller/1621858-init)
        Creates and new `UINavigationController` with a the designated `rootViewController`
  * [UITableViewController](https://developer.apple.com/documentation/uikit/uitableviewcontroller)

### Tasks

* Display a single tab for listing users (no items needed yet)
* Create a class for listing users by subclassing UITableViewController

*Optional*

* Use [extensions](https://docs.swift.org/swift-book/LanguageGuide/Extensions.html) to refactor the way our view controllers are displayed

![What the end of step 1 should look like](/assets/step-1.jpg?raw=true "Step 1 Result")

## Step 2 - Parse and Display Data

### Concepts

* Reading a file from the Application [Bundle] using the [Data] type
* [Codable] protocol for easy JSON decoding
* [Delegation] pattern and how it is used with [UITableViewController]
* Basics of [Model-View-Controller] pattern
* Concept of [Optionals] and [Optional Chaining] and how to work with them
* How to throw and catch [Errors] in Swift

### Tasks

* Parse bundled json file using [Codable] into a set of [structs]
* Create a custom [UITableViewCell] and understand how to use [IBOutlet]
* Display the list of users from the JSON file into the `UsersTableViewController`
* Understand the basics of updating the user interface and the `main` thread

![What the end of step 2 should look like](/assets/step-2.jpg?raw=true "Step 2 Result")

## Step 3 - Display More Complex Data

### Concepts

* [JSONDecoder.dateDecodingStrategy]
* Protocol-Oriented Programming
* Functional Programming (map, reduce, sorting, max, etc...)
* Application Transport Security
  ```xml
  <key>NSAppTransportSecurity</key>
  <dict>
  <key>NSExceptionDomains</key>
  <dict>
  <key>lorempixel.com</key>
  <dict>
  <key>NSExceptionAllowsInsecureHTTPLoads</key>
  <true/>
  <key>NSIncludesSubdomains</key>
  <true/>
  </dict>
  </dict>
  </dict>
### Tasks

* Setup Posts and Comments
* Dealing with Dates and Codable
* Basic Functional Programming
* Setup Application Transport Security

## Step 4 - Apple Watch App Setup

### Tasks

* Setup a menu for displaying users and posts

[Delegation]: https://developer.apple.com/library/archive/documentation/General/Conceptual/DevPedia-CocoaCore/Delegation.html
[UITableViewController]: https://developer.apple.com/documentation/uikit/uitableviewcontroller
[Bundle]: https://developer.apple.com/documentation/foundation/bundle
[Data]: https://developer.apple.com/documentation/foundation/data
[Codable]: https://developer.apple.com/documentation/swift/codable
[Model-View-Controller]: https://developer.apple.com/library/archive/documentation/General/Conceptual/DevPedia-CocoaCore/MVC.html
[Optional Chaining]: https://docs.swift.org/swift-book/LanguageGuide/OptionalChaining.html
[Optionals]: https://developer.apple.com/documentation/swift/optional
[Errors]: https://docs.swift.org/swift-book/LanguageGuide/ErrorHandling.html
[sturcts]: https://docs.swift.org/swift-book/LanguageGuide/ClassesAndStructures.html
[UITableViewCell]: https://developer.apple.com/documentation/uikit/views_and_controls/table_views/configuring_the_cells_for_your_table
[IBOutlet]: https://developer.apple.com/library/archive/documentation/General/Conceptual/CocoaEncyclopedia/Outlets/Outlets.html
[JSONDecoder.dateDecodingStrategy]: https://developer.apple.com/documentation/foundation/jsondecoder/2895216-datedecodingstrategy
[Protocol-Oriented Programming]: https://developer.apple.com/videos/play/wwdc2015/408/
