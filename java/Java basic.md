### Accessibility of classes and members

For members (fields, methods, nested classes, and nested interfaces), there are four possible access levels, listed here in order of increasing accessibility:

* <b>private</b>: The member is accessible only from the top-level class where it is declared.

* <b>package-private</b>: The member is accessible from any class in the package where it is declared. Technically known as default access, this is the access level you get if no access modifier is specified.

* <b>protected</b>: The member is accessible from subclasses of the class where it is declared (subject to a few restrictions [JLS, 6.6.2]) and from any class in the package where it is declared.

* <b>public</b>: The member is accessible from anywhere.
