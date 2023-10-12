# Unity Notes
[Unity docs for the version I'm working on](https://docs.unity3d.com/2022.3/Documentation/ScriptReference/Input.html)
## Unity Windows
**Hierarchy Window**: The window that shows all of the GameObjects within the game environment and their relationship/hierarchy between each other
**Inspector Window**: Let's you modify the properties of certain GameObjects and Scripts
* allows you to manage the various GameObject components
* If you define a variable within a script and then open that script within the inspector, it will only show you the public variables and [SerializeField] variables
	* variables defined within scripts are called fields and their values are called properties
**Project Window**: the window where you can see and manage all the assets, files, and components for the project and manage them 
* you should move files and assets around with this window instead of the file explorer because Unity keeps links in various config files (similar to Xcode functionality) and moving things within this window will properly update their links
## Unity Components
**Component**: a set of properties and attributes that are bundled together and can be applied to a Unity GameObject to change its functionality
* Your custom scripts that you attach to GameObjects are classified at components of those GameObjects
**Transform**: Unity component attached to every GameObject which allows you to change its position and rotation within the game environment
* Transform has Position, Rotation, and Scale
* When one GameObject extends another, its Transform component becomes relative to the parent's Transform component
	* (0,0,0) position of the child would make it be in the same spot as the parent
	* (2,2,2) scale for child would make it twice the size of its parent
**RigidBody2D**: Component that adds physics to GameObjects, allows them to have gravity, inertia, momentum, etc.
* Rigid bodies have different types:
	* **Dynamic**: Affected by forces and gravity, and can move around
	* **Kinematic**: Not affected by any forces or gravity, can only move through initial velocity
		* you can still modify things with scripts but no default behavior
**Collider**: Component that allows GameObjects to touch and collide with each other instead of moving through each other
**GetComponent**: method to get the Component object for a GameObject given its type, has a template syntax and would be used like this:
```c#
// PlayerController is the type of component that belongs to the gameObject
PlayerController playerScript = gameObject.GetComponent<PlayerController>();
```
## Other Terms
**GameObject**: An object that appears within a Unity game
* to instantiate a GameObject through a scripting, you call the Instantiate method and pass in a prefab for the object, prefab doesn't have to be specific can just be a blank reference to the type:
```c#
// prefab
public GameObject originalTile;
// new object
GameObject newObject = GameObject.Instantiate(originalTile);
```
**Fields**: Variable names defined within scripts
**Properties**: the values of variables defined within scripts/fields
**Script**: A C# file that lets you customize the behavior of a GameObject
**Prefab**: A blueprint in Unity for other GameObjects
**Scene**: Can be one of multiple "screens" user sees when playing the game, game can switch between these various scenes
* the scene editor is where you arrange different GameObjects and define the initial start of the game and edit them
* the game window is where you can see a preview of all the GameObjects in the Scene and play the game, but you cannot edit anything as the game is already running
**Sprite**: a graphic asset that shows up in the game, usually in a 2D context
* when you drag a sprite into a scene it becomes of the initial GameObjects within that scene, and becomes a physical object that can interact with things as opposed to just a blueprint
**Canvas**: A UI container for Unity, uses a separate camera
**Vectors**: Unity vectors used to transform the position, rotation, and scale of objects, implemented as structs so they are passed by reference as opposed to by value
**Physics2D**: Unity object that performs physics calculations within the game, use it to get values, all methods within it are static
**Start()**: Unity method that belongs to every GameObject and gets called **once** upon the creation of every GameObject
**Update()**: Unity method that belongs to every GameObject and gets called **every game frame** as long as that object is within the environment and is not deleted

# C# Notes
* C# is reference based like Java where everything except primitives and structs gets passed a pointer instead of copied
* https://chat.openai.com/share/e83a1acb-eda4-4c7f-9216-10b25819a96a
## Structs
* work the same way as structs in C++, and these are copied by value unless you specifically use the `ref`, `in`, or `out` keywords
* Structs cannot be null as they are values, objects can be null pointers
## C# Naming Convention
**Variables:**
```c#
// local variable
Object localVariable;
// Private Variables
Object _privateVariable;
// Public Variables, in Unity these are camelCase though
public Object PublicVariable;
// Constants
const Object ConstantVariable;
```
**Namespaces, Classes, Methods, Interfaces**
```c#
// these are all pascal case, remember to add I for interface
public void FunctionalMethod();
public class FunctionalClass;
public interface IFunctionalInterface;
namespace FunctionalNamespace;
```
