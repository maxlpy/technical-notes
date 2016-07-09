### Understanding Spring Web Application Architecture: The Classic Way

#### The Two Pillars of a Good Architecture
* The Separation of Concerns (SoC) Principle
The Separation of Concerns (SoC) principle is specified as follows: Separation of concerns (SoC) is a design principle for separating a computer program into distinct sections, such that each section addresses a separate concern.
This means that we should

  * Identify the “concerns” that we need to take care of. 
  * Decide where we want to handle them.
In other words, this principle will help us the identify the required layers and the responsibilities of each layer.

* The Keep It Simple Stupid (KISS) principle
The Keep It Simple Stupid (KISS) principle states that: Most systems work best if they are kept simple rather than made complicated; therefore simplicity should be a key goal in design and unnecessary complexity should be avoided.
This principle is the voice of reason. It reminds us that every layer has a price, and if we create a complex architecture that has too many layers, that price will be too high.

#### Three Layers Should Be Enough for Everybody

If think about the responsibilities of a web application, we notice that a web application has the following “concerns”:

* It needs to process the user’s input and return the correct response back to the user.
* It needs an exception handling mechanism that provides reasonable error messages to the user.
* It needs a transaction management strategy.
* It needs to handle both authentication and authorization.
* It needs to implement the business logic of the application.
* It needs to communicate with the used data storage and other external resources.

We can fulfil all these concerns by using “only” three layers. These layers are:

* <b>The web layer</b> is the uppermost layer of a web application. It is responsible of processing user’s input and returning the correct response back to the user. The web layer must also handle the exceptions thrown by the other layers. Because the web layer is the entry point of our application, it must take care of authentication and act as a first line of defense against unauthorized users.
* <b>The service layer</b> resides below the web layer. It acts as a transaction boundary and contains both application and infrastructure services. The application services provides the public API of the service layer. They also act as a transaction boundary and are responsible of authorization. The infrastructure services contain the “plumbing code” that communicates with external resources such as file systems, databases, or email servers. Often these methods are used by more than a one application service.
* <b>The repository layer</b> is the lowest layer of a web application. It is responsible of communicating with the used data storage.

Reference from http://www.petrikainulainen.net/software-development/design/understanding-spring-web-application-architecture-the-classic-way/

Note: There are still more valuable articles about software design in this link. See [here](http://www.petrikainulainen.net/category/software-development/design/)
