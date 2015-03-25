# cmvp-seed
CMVP architecture seed. Feel free to use in your projects :)

## Installation
`npm install`

## Running the tests
To check that the system is ok, simply run the test.
As long as we promote the use of a strong IDE, we suggest to run the test from PHPStorm.
To do this:

* Install PHPStorm
* Install Karma plugin 
* Configure Karma in "Run Configurations"
* Run the tests

## About CMVP Architecture

We created that architecture to decouple frontend from backend using the best technology we could find, that's why we choose AngularJS.
Besides this... we can't not predict the future. Maybe we want to replace the angularsj for other technology as reactjs or even backbone.
To avoid the dependency with the framework all the core of the architecture is pure Javascript, not AngularJS. 
That also have some good things like testeability, emergent design... That's Agile.

## Why C.M.V.P. ?

* C.ontroller: angularJS controller for $scope and other angular facilities injection
* M.odel: for managing data provided by server or that is about to be sent
* V.iew: for every single element that is displayed
* P.resenter: for model and view binding

### Diving in. Controller.

* The only responsibility is to instantiate the right view injecting all dependencies into it. 
* All angular logic is encapsulated in registerController method.
* Always one controller per view.


### Diving in. Model.

* Validates data. 
* Establishes server connection configuration.
* Constructs queries.
* Implements data interactions (inside its domain).


### Diving in. View.

* view’s responsibility is to instantiate a presenter. It also may pass presenter a model instance.
* view has 3 main blocks:
>* data: presentation model that is exposed in $scope and is accessible from the html view.
>* event: functions which execution means a model access. They are always overwritten in presenter.
>* fn: functions which execution do not require a model intervention. 

### Diving in. Presenter.

The only responsibility is to bind view events with model methods. It is accomplished passing view’s methods as callbacks.

# Components

## Aspects

Implemented with meld library. Aspects make possible to “cut across” different application domains. 
In JS they are used in order to implement Dynamic Proxy design pattern.

## EventBus

Communication between different views is accomplished by the implementation of Event Bus. 
With Event Bus views’ shared state can be avoided. Every view is independent and does not rely on other views implementation.

## Q Promises

Communication with server is done using q promises. They facilitate response treating implementing callbacks for success, error, timeout, etc.



