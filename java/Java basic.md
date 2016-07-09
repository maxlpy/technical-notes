### Accessibility of classes and members

For members (fields, methods, nested classes, and nested interfaces), there are four possible access levels, listed here in order of increasing accessibility:

* <b>private</b>: The member is accessible only from the top-level class where it is declared.

* <b>package-private</b>: The member is accessible from any class in the package where it is declared. Technically known as default access, this is the access level you get if no access modifier is specified.

* <b>protected</b>: The member is accessible from subclasses of the class where it is declared (subject to a few restrictions [JLS, 6.6.2]) and from any class in the package where it is declared.

* <b>public</b>: The member is accessible from anywhere.

### Examples
* Delegation
```
public class A {
  private B b = new B();

  public void methodA() {
    b.methodB();
  }
}
```
When clients of A call methodA, class A delegates the call to B's methodB.

Rationale. Class A exposes behaviours that belong elsewhere. This can happen in single-inheritance languages where class A inherits from one class, but its clients need behaviours that are implemented in a different class. [Further study](http://beust.com/java-delegation.html).

* Composition
```
public class A {
  private B b = new B();

  public A() {
  }
}
```
Once no more references to a particular instance of class A exist, its instance of class B is destroyed.

Rationale. Allows classes to define behaviours and attributes in a modular fashion. [Further study](http://www.artima.com/designtechniques/compoinh.html).

* Aggregation
```
public class A {
  private B b;

  public A( B b ) {
    this.b = b;
  }
}

public class C {
  private B b = new B();

  public C() {
    A a = new A( this.b );
  }
}
```
Once there are no more references to a particular instance of class A, its instance of class B will not be destroyed. In this example, both A and C must be garbage collected before B will be destroyed.

Rationale. Allows instances to reuse objects. [Further study](http://www.coderanch.com/t/659747/Wiki/Association-Aggregation-Composition).
