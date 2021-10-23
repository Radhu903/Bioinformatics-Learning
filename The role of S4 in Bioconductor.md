```
1. The Role of S4 in Bioconductor
R is a functional programming language. Because S4 is extensively used in Bioconductor packages we will cover the basics here. But bear in mind, this is a big enough topic for a book. The two most used systems in R are S3 and S4, in order to understand better S4 we will start by shortly explaining S3-characteristics, and then making a comparison with S4.

2. S3
Most of CRAN packages use the S3 system, which is simple but powerful. It gives flexibility to the user and it has an interactive nature. This means it reacts differently, depending on the input, by using a generic function to decide which method to call. In R a good example is the plot() function. It actually has about 29 different kinds of plots which will be interpreted depending on your input. This is fantastic and makes R very flexible for the user. However, S3 is not good at evaluating and validating types, hence when the user gives an unexpected argument, the generic function will try all its options before it returns an error. Other annoyances are the poor use of naming conventions and how inheritance differs by the input.

3. S4
The S4 system motivation is to implement an object-oriented style of programming. The base concept is to define the data first and then work on it. Once an object is defined, it is generalized to a class by defining the kind of data it contains and any actions or functions to manipulate it. As you will see in more detail in the coming chapters, biological representations are complex and very often interconnected. Bioconductor then, recommends re-using methods and classes before implementing new representations. S4 classes have a formal definition, hence are a lot better to check input types, because of their definition and inheritance. You can create a new object from a class like in the example. We created a new genome description. This object will contain slots to describe it. S4 requires a bit more work to implement, but it serves to extend the code so that others can reuse the framework.

4. Is it S4 or not?
How do we know whether a definition of an object is S4 or not? Use the function isS4() It returns a logical. Another way to check if an object is S4 is by using the `str` function. If it is S4 it will start with 'Formal class'. On the other hand, S3 objects are those that respond FALSE to isS4() and don't have a formal class definition.

5. S4 class definition
An S4 class describes a representation of an object with a name and slots (also called methods or fields), helpful for validation. A class optionally describes its inheritance (usually with the parameter contains). A class allows us to define all the characteristics concerning an object and it gives us code reusability. For example, we create a class using setClass() Its name is MyEpicProject with three slots: ini, end and milestone. This class inherits from the class MyProject. This means we can reuse slots from it.

6. S4 accessors
Basic information of an S4 object is accessed through accessor-functions, also called methods. As we have seen, a class definition includes slots for describing an object. The function dot-S4methods() used with main classes gives you a summary of its accessors. For other subclasses use the showMethods() function, but this gives you a breakdown, which might be a bit too long to look at. If you want an object summary, use the accessor function show(). You will use some of these accessors in the coming exercises.

7. Let's practice!
Now it's your turn to use Bioconductor S4 objects and classes! Enjoy!

```
