
# Design Pattern
 Software enginnering have many common occuring problems which can be solved by reusable code known as design patterns.
The design pattern used in JavaScript are as follows:-

 **1.  Creational Design Patterns**
    For handling objects creations mechanisms
    
 **2.  Structural Design Patterns**
     For identifying ways to realize relationship between objects
     
 **3.  Behavioral Design Patterns**
     For handling communication between different objects
 
I will discuss 5 design pattern here I will cover mostly Creational Design pattern with examples:

**1. Constructor design Pattern**
This is the part of *creational design patterns*.


    class Person {
    name: string
    age: number
    habits: string[]
    constructor(name: string, age: number, habits: string[]) {
    	this.name=name
    	this.name=number
    	this.habits=[...habits]
    }

    addHabit(habit: string) {
    	/*Method to add new habit*/
	    }
    }

The Person class consists of the person properties name, age and habit and a method as addHabit. The constructor method gets called when we create an instance of the class using the new operator. The constructor method helps in assigning values to the instance variables of the class by creating a new object.

let person1 = new person("satyam", 25, ["watch cricket"])

If the above line is executed, the properties name, age, habit and addHabit method are defined on the person1 object. 

**2. Prototype Design Pattern**

We can create clones of existing objects by using this design pattern. The prototypal inheritance in JavaScript is similar. 
All of the attributes and methods of an object can be made available on any other object by leveraging the power of the __proto__ property. We can do that by using the ES6 Object.create method:

let person1= Object.create(Person.prototype)

We achieve the prototypal inheritance using the classic functional objects as in JavaScript:

    let fitnessLevelDetails = {
    weiht: 60,
    height: 10, fitnessLevel: function (level) {
	}
    }
    function Person () {}
    /* The prototype of Person is fitnessLevelDetails, which means Person should be cloned as fitnessLevelDetails */
    Person.prototype = fitnessLevelDetails
    let personObj = new Person()

/* fitnessLevel method is present on the personObj as fitnessLevelDetails is attached to it __proto__ property */

	personObj.fitnessLevel('expert')

The prototype design pattern is used to implement inheritance in JavaScript generally. This pattern add the properties of the parent to the child objects.

**3. Singleton Design Pattern**

This pattern only allows single instantiation, but many instances of the same object. This restricts clients from creation of multiple objects, after the first object created, it will return instances of itself.

This design pattern is very rarely used. For example in office printer it is used. If there are 15 people in an office and they are  using 1 printer, 15 computers share 1 printer. They share the same resources by sharing same printer.

    var printer = (function () {
    var printerInstance;

    function create () {

    function print() {
        // underlying printer working
    }

    function turnOn() {
        // warm up
        // check for paper
    }

    return {
        // public + private states and behaviors
        print: print,
        turnOn: turnOn
    };
    }

    return {
    getInstance: function() {
        if(!printerInstance) {
        printerInstance = create();
        }
        return printerInstance;
    }
    };

    function Singleton () {
    if(!printerInstance) {
        printerInstance = intialize();
    }
    };
    })();


The create method is private because we do not want the client to access this, however, notice that the getInstance method is public. Each employee can create a printer instance by interacting with the getInstance method as follows:

var officePrinter = printer.getInstance();

**4. Observer Design Pattern**

This comes under Behavioral Design Patterns. This design pattern used in a place where objects communicate with other sets of objects simultaneously. There is no unnecessary pull and push of events across the states, rather the sections involved only update the current state of data in this observer design pattern.

function Observer() {
this.observerContainer = [];
}

Observer.prototype.subscribe = function (item) {
this.observerContainer.push(item);
}

// the following removes an item from the container

Observer.prototype.unsubscribe = function (item) {

const itemIndex = this.observerContainer.indexOf(item);
if (itemIndex &gt; -1) {
this.observerContainer.splice(itemIndex, 1);
}
}

/**
* we notify items added to the container by calling
* each subscribed components added to our container
*/

Observer.prototype.notifyAll = function (item) {
this.observerContainer.forEach(function (observerItem) {
observerItem(item);
});
}

**5. Command Design Pattern**

The command design pattern contains method invocation, operations, or requests into a single object. This design pattern provides us a chance to write commands from anything executing commands and assign responsibility to different objects. These commands are represented by run() and execute() format.
For example:-

(function(){

var carManager = {

//requested information
requestInfo: function( model, id ){
return "The information for " + model + " with ID " + id + " is foo bar";
},

// For purchasing the car
buyVehicle: function( model, id ){
return "You have successfully purchased Item " + id + ", a " + model;
},

// For booking a viewing
arrangeViewing: function( model, id ){
return "You have successfully booked a advanced viewing of " + model + " ( " + id + " ) ";
}

};

})();

**Reference Links:**
 - https://www.toptal.com/javascript/comprehensive-guide-javascript-design-patterns
 - https://www.digitalocean.com/community/tutorial_series/javascript-design-patterns
 - https://codesource.io/javascript-design-patterns/
 - https://www.digitalocean.com/community/tutorial_series/javascript-design-patterns
