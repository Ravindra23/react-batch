Well, what is Library?:-
A library provides a set of helper functions/objects/modules which your application code calls for specific functionality. Libraries typically focus on a narrow scope (e.g., strings, IO, sockets), so their API’s also tend to be smaller and require fewer dependencies. It is just a collection of class definitions.
It performs a set of  specific and well-defined operations. Examples : Network protocols, compression, image manipulation, string utilities, regular expression evaluation, math etc

 Why we need them?:-    
 The reason being very simple i.e. code reuse, use the code which has already been written by other developers. 
 
 Example, some library has a method named findLastIndex(char) to find the last index of a particular character in a string. We can straightaway call findLastIndex(charToFind) function of the library ans pass teh characters whose position we need to find as a parameter in the function call.

str = "React.org"
var pos = str.lastIndexOf("."); // simply calling function of string library

what is Framework?:-

Framework, on the other hand has defined open or unimplemented functions or objects which the user writes to create a custom application. Because a framework is itself an application, it ha a wider scope and includes almost everything necessary to make a user application as per his own needs.

Key Difference:-

Thus, the key difference is in the “Inversion of Control”, commonly called as IoC. When we call a method from a library, we are in control. But in framework, the control is inverted i.e. the framework calls us. It defines a skeleton where the application defines its own features to fill out the skeleton.

