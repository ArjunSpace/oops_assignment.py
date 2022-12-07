# oops_assignment.py
Q1. What is the purpose of Python's OOP?
      
      In Python, object-oriented Programming (OOPs) is a programming paradigm that 
    uses objects and classes in programming. It aims to implement real-world entities 
    like inheritance, polymorphisms, encapsulation, etc. in the programming. 
    
Q2. Where does an inheritance search look for an attribute?
      
      An inheritance search looks for an attribute first in the instance object,
    then in the class the instance was created from, then in all higher superclasses, 
    progressing from left to right (by default). 
    The search stops at the first place the attribute is found.
    
 Q3. How do you distinguish between a class object and an instance object?
      
    class                                                                object
    1.A class is a template for creating objects in program.              The object is an instance of a class.
    2.A class is a logical entity                                         Object is a physical entity
    3.A class does not allocate memory space when it is created.          Object allocates memory space whenever they are created.
    4.You can declare class only once.                                    You can create more than one object using a class.
    5.Classes can’t be manipulated as they are                            They can be manipulated.
      not available in memory.
  
  Q4. What makes the first argument in a class’s method function special?
  
        Self is the first argument to be passed in Constructor and Instance Method.
      Self is always pointing to Current Object.self represents the instance of the class.
      By using the “self”  we can access the attributes and methods of the class in python.
      It binds the attributes with the given arguments.
   
   Q5. What is the purpose of the init method?
   
        Python's __init__ method is called the initializer method. The __init__ method allows
       you to accept arguments to your class.More importantly, the __init__ method allows you
       to assign initial values to various attributes on your class instances.
       
   Q6. What is the process for creating a class instance?
    
            To create class instance or object of a class by calling the class name and should 
         include the arguments which were called in the init method of its class
         
         Ex:
         #creating class instance
         class xyz:
            def __init__(self, a, b):
               self.a = a
               self.b = b
            def add_two(self):
               print(self.a + self.b)
                  
          m = xyz(1,2)   #m is a objective of the class xyz
          m.add_two()
          print(m.a)
          print(m.b)
          
   Q7. What is the process for creating a class?
   
            class can be created by using the class keyword followed by class name 
        Syntax:
        class car:
 
         # init method or constructor
            def __init__(self, name, colour):
                  self.name = name
                  self.colour = colour
 
         # Sample Method
            def spects(self):
                  print("car model is :", self.name)
                  print("colour: ", self.colour)

         veh = car("tiago","blue")
         print(veh.name)
         print(veh.colour)
         veh.spects()
 
                
Q8. How would you define the superclasses of a class?
      
      A superclass is the class from which many subclasses can be created. 
    The subclasses inherit the characteristics of a superclass. The superclass is also               
    known as the parent class or base class.
        
     Ex:
     class xyz:     #xyz class is super class
         def __init__(self, a, b, c):
            self.a = a
            self.b = b
            self.c = c

         def test(self):
            print("it is from xyz class of test")

     class xyz1(xyz):
       def __init__(self, p, q, r):
            self.p = p
            self.q = q
            self.r = r 
       def test1(self):
            print("it is from xyz1 class of test")

     class xyz2(xyz1):

         def test2(self):
            print("it is from xyz2 class of test")


      q = xyz2(1,2,3)

      q.a
      q.test()
      q.test1()
      q.test2()

      o/p:
      it is from xyz class of test
      it is from xyz1 class of test
      it is from xyz2 class of test
  

Q9. What is the relationship between classes and modules?

        The module is a simple Python file that contains collections of classes, functions 
    and global variables and with having a .py extension file. where as class is structure
    for creating objects.
    
       modules may contain classes in it.
    
Q10. How do you make instances and classes?

     classes can be made by using key word class followed by class name.
     Ex:
        class Employee:   # it is a class having name Employee
     
     class instances can be created by following way:
        Emp_details = Employee(#arguments declared in the init constructor)
        By this way many instances can be created 
        
Q11. Where and how should be class attributes created?

     
     class sampleclass:
         count = 0	 # class attribute

	def increase(self):
          sampleclass.count += 1

     # Calling increase() on an object
     s1 = sampleclass()
     s1.increase()		
     print(s1.count)

    # Calling increase on one more
    # object
    s2 = sampleclass()
    s2.increase()
    print(s2.count)

    s3 = sampleclass()
    s3.increase()
    print(s3.count)
    print(sampleclass.count)
    
     
Q12. Where and how are instance attributes created?

     instance attributes are to be created inside a class by using 
     self 
     class emp:
          def __init__(self, name, salary):
              self.name = name
              self.salary = salary
  
          def show(self):
              print(self.name)
              print(self.salary)
  
     e1 = emp("xyz", 10000)
     e1.show()
     
 Q13. What does the term "self" in a Python class mean?
    
          self represents the instance of the class. By using the “self”  we can access the attributes 
      and methods of the class in python. It binds the attributes with the given arguments.
      The reason to use self. is because Python does not use the @ syntax to refer to instance attributes.
      Python decided to do methods in a way that makes the instance to which the method belongs be passed
      automatically, but not received automatically: the first parameter of methods is the instance of the
      method is called on.
      
          Self is always pointing to Current Object.Self is the first argument to be passed in Constructor and Instance Method.
      self is not a keyword we can use anything inplace of self but self is used because of best programming practice
      
 Q14. How does a Python class handle operator overloading?
 
          Consider that we have two objects which are a physical representation of a class (user-defined data type) 
      and we have to add two objects with binary ‘+’ operator it throws an error, because compiler don’t know 
      how to add two objects
      
      Ex:
         class Point:
             def __init__(self, x=0, y=0):
                 self.x = x
                 self.y = y

         p1 = Point(1, 2)
         p2 = Point(2, 3)
         print(p1+p2)
        
      o/p:
      TypeError                                 Traceback (most recent call last)
      <ipython-input-11-117bb3bdfa23> in <module>
      7 p1 = Point(1, 2)
      8 p2 = Point(2, 3)
      ----> 9 print(p1+p2)

      TypeError: unsupported operand type(s) for +: 'Point' and 'Point'
      
          We can overload all existing operators but we can’t create a new operator. To perform operator overloading, 
      Python provides some special function or magic function that is automatically invoked when it is associated
      with that particular operator. For example, when we use + operator, the magic method __add__ is automatically 
      invoked in which the operation for + operator is defined.
      
      
      class over_load:
          def __init__(self, a):
              self.a = a
 
      # adding two objects
          def __add__(self, o):
              return self.a + o.a
      ob1 = over_load(1)
      ob2 = over_load(2)
      ob3 = over_load("Big")
      ob4 = over_load("Data")
 
      #print(ob1 + ob2)
      #print(ob3 + ob4)

      # Actual working when Binary Operator is used.

       print(over_load.__add__(ob1 , ob2))
       print(over_load.__add__(ob3,ob4))

       #And can also be Understand as :

       print(ob1.__add__(ob2))
       print(ob3.__add__(ob4))
       
Q15. When do you consider allowing operator overloading of your classes?

Q16. What is the most popular form of operator overloading?

Q17. What are the two most important concepts to grasp in order to comprehend Python OOP code?
     
         Both inheritance and polymorphism are fundamental concepts of object oriented programming. 
     These concepts help us to create code that can be extended and easily maintainable.

Q18. Describe three applications for exception processing.

         Exceptions: Exceptions are raised when the program is syntactically correct, but the code 
     resulted in an error. This error does not stop the execution of the program, however, 
     it changes the normal flow of the program.
     
     Try with Else Clause
         In python, you can also use the else clause on the try-except block which must be present after
     all the except clauses. The code enters the else block only if the try clause does not raise an exception.

     Example: Try with else clause

 
     def AbyB(a , b):
         try:
             c = ((a+b) / (a-b))
         except ZeroDivisionError:
             print ("a/b result in 0")
         else:
             print (c)
 
         AbyB(2.0, 3.0)
         AbyB(3.0, 3.0)
         
	 Output:

         -5.0
          a/b result in 0 

      Finally Keyword in Python
      	Python provides a keyword finally, which is always executed after the try and except blocks. 
      The final block always executes after normal termination of try block or after try block terminates due to some exception.
     
 
Q19. What happens if you don't do something extra to treat an exception?
 
          Even if the syntax of a statement or expression is correct, it may still cause an error when executed. 
       Python exceptions are errors that are detected during execution and are not unconditionally fatal. 
       An exception object is created when a Python script raises an exception. If the script explicitly doesn't
       handle the exception, the program will be forced to terminate abruptly.
       
Q20. What are your options for recovering from an exception in your script?

         A single try statement can have multiple except statements. This is useful when the try block contains statements 
     that may throw different types of exceptions.can also provide a generic except clause, which handles any exception. 
     After the except clause(s), you can include an else-clause. The code in the else-block executes if the code in the
     try: block does not raise an exception.

Q21. Describe two methods for triggering exceptions in your script.

     triggering exceptions in python can be done by 
     1. try except statements
     2. raise statement :The raise statement allows the programmer to force a specified exception to occur
     
     Ex:
        raise NameError('HiThere')
        Traceback (most recent call last):
        File "<stdin>", line 1, in <module>
        NameError: HiThere
	
Q22. Identify two methods for specifying actions to be executed at termination time, regardless of whether or not an exception exists.
Q23. What is the purpose of the try statement?

         The try block lets you test a block of code for errors.
     When an error occurs, or exception as we call it, Python will normally stop and generate an error message.
     These exceptions can be handled using the try statement:

     Example
     The try block will generate an exception, because x is not defined:

      try:
      	print(x)
      except:
      	print("An exception occurred")
 
 Q24. What are the two most popular try statement variations?
 
      Syntax: 
      try:
      	# Some Code
      except:
     	 # Executed if error in the
      	 # try block
 
	First, the try clause is executed i.e. the code between try and except clause.
     If there is no exception, then only the try clause will run, except the clause is finished.
     If any exception occurs, the try clause will be skipped and except clause will run.
     If any exception occurs, but the except clause within the code doesn’t handle it,
       it is passed on to the outer try statements. 
     If the exception is left 	unhandled, then the execution stops.
     A try statement can have more than one except clause
	
     Code 1: No exception, so the try clause will run. 
 
     def divide(x, y):
     	try:
           # Floor Division : Gives only Fractional Part as Answer
           result = x // y
           print("Yeah ! Your answer is :", result)
           except ZeroDivisionError:
           print("Sorry ! You are dividing by zero ")
  
     divide(3, 2)
     Output : 
    ('Yeah ! Your answer is :', 1)
    
    Code 1: There is an exception so only except clause will run. 
 
    def divide(x, y):
    	try:
           # Floor Division : Gives only Fractional Part as Answer
           result = x // y
           print("Yeah ! Your answer is :", result)
       except ZeroDivisionError:
           print("Sorry ! You are dividing by zero ")
 
    divide(3, 0)
    Output : 
    Sorry ! You are dividing by zero
 
    Else Clause
    In python, you can also use the else clause on the try-except block which must be present
    after all the except clauses. The code enters the else block only if the try clause does 
    not raise an exception.
    Syntax:

    try:
    # Some Code
    except:
    # Executed if error in the
    # try block
    else:
    # execute if no exception
   
Q25. What is the purpose of the raise statement?
   
     The raise keyword is used to raise an exception.
     Ex:
     x = -1
     if x < 0:
     raise Exception("Sorry, no numbers below zero")
     
Q26. What does the assert statement do, and what other statement is it like?

     The assert keyword is used when debugging code.
     The assert keyword lets you test if a condition in your code returns True, if not, the program
     will raise an AssertionError.You can write a message to be written if the code returns False
     
     Ex:
       x = "hello"
       #if condition returns True, then nothing happens:
       assert x == "hello"
       #if condition returns False, AssertionError is raised:
       assert x == "goodbye"
       
Q27. What is the purpose of the with/as argument, and what other statement is it like?

	with statement is used in exception handling to make the code cleaner and much more readable.
	It simplifies the management of common resources like file streams. following code is example on 
	how the use of with statement makes code cleaner. 

	# file handling

	# 1) without using with statement
	file = open('file_path', 'w')
	file.write('hello world !')
	file.close()

	# 2) without using with statement
	file = open('file_path', 'w')
	try:
	    file.write('hello world')
	finally:
	    file.close()

	# using with statement
	with open('file_path', 'w') as file:
	    file.write('hello world !')
	    
Q28. What are *args, **kwargs?

     *args:
	The special syntax *args in function definitions in python is used to pass a variable number of arguments
     to a function. It is used to pass a non-key worded, variable-length argument list. 

	The syntax is to use the symbol * to take in a variable number of arguments; by convention, it is often used
      with the word args.What *args allows you to do is take in more arguments than the number of formal arguments 
      that you previously defined. With *args, any number of extra    arguments can be tacked on to your current formal
      parameters (including zero extra arguments).For example, we want to make a multiply function that takes any number 
      of arguments and is able to multiply them all together. It can be done using *args.Using the *, the variable that 
      we associate with the * becomes an iterable meaning you can do things like iterate over it, run some higher-order 
      functions such as map and filter, etc.
      
      Ex:
      def myFun(*argv):
         for arg in argv:
             print(arg)
      myFun('big' , 'data')
      
      **kwargs:
	    The special syntax **kwargs in function definitions in python is used to pass a keyworded, variable-length
	argument list. We use the name kwargs with the double star. The reason is that the double star allows us to pass
	through keyword arguments (and any number of them).

	    A keyword argument is where you provide a name to the variable as you pass it into the function.
	One can think of the kwargs as being a dictionary that maps each keyword to the value that we pass alongside it.
	That is why when we iterate over the kwargs there doesn’t seem to be any order in which they were printed out.
	
	Ex:
	
        def myFun(**kwargs):
            for key, value in kwargs.items():
            print(key, value)
	    
	myFun(first='Big',last='Data')
	
Q29. How can I pass optional or keyword parameters from one function to another?
	
         In Python, when we define functions with default values for certain parameters, 
     it is said to have its arguments set as an option for the user. Users can   either pass their values or can 
     pretend the function to use theirs default values which are specified.In this way, the user can call the function 
     by either passing those optional parameters or just passing the required parameters. 

     There are two main ways to pass optional parameters in python 

	Without using keyword arguments.
	By using keyword arguments.
	Passing without using keyword arguments
	
	Some main point to be taken care while passing without using keyword arguments is :

        The order of parameters should be maintained i.e. the order in which parameters are defined in function
	should be maintained while calling the function.
	
	The values for the non-optional parameters should be passed otherwise it will throw an error.
	
	The value of the default arguments can be either passed or ignored.
	
	Example 1:


	# Here b is predefined and hence is optional.
	def func(a, b=1098):
	    return a+b


	print(func(2, 2))

	# this 1 is represented as 'a' in the function and
	# function uses the default value of b
	print(func(1))
	Output:

	4
	1099

Q30. What are Lambda Functions?

         A lambda function is a small anonymous function.
      A lambda function can take any number of arguments, but can only have one expression.

	Syntax
	lambda arguments : expression
	The expression is executed and the result is returned:

	Example
	Add 10 to argument a, and return the result:

	x = lambda a : a + 10
	print(x(5))
 
	Lambda functions can take any number of arguments:

	Example
	Multiply argument a with argument b and return the result:

	x = lambda a, b : a * b
	print(x(5, 6))    
	
Q31. Explain Inheritance in Python with an example?

	One of the core concepts in object-oriented programming (OOP) languages is inheritance.
     It is a mechanism that allows you to create a hierarchy of classes that share a set of properties 
     and methods by deriving a class from another class. Inheritance is the capability of one class to
     derive or inherit the properties from another class. 

	class Person:

	    # Constructor
	    def __init__(self, name):
		self.name = name
	    # To get name
	    def getName(self):
		return self.name
	   # To check if this person is an employee
	    def isEmployee(self):
		return False
	# Inherited or Subclass (Note Person in bracket)	
	class Employee(Person):
	    def isEmployee(self):
		return True

	emp = Person("Arjun")  # An Object of Person
	print(emp.getName(), emp.isEmployee())

	emp = Employee("Vamshi")  # An Object of Employee
	print(emp.getName(), emp.isEmployee())
	
	Output: 
	Arjun False
	Vamshi True

 Q32. Suppose class C inherits from classes A and B as class C(A,B).Classes A and B both have their own versions of method func(). If we call func() from an object of class C, which version gets invoked?
 
	class A:
	  def test(self):
	    print("it is from A class ")
	class B:
	  def test(self):
	    print("it is from B class ")
	class C(A,B):
	  pass
	obj = C()
	obj.test() 

	o/p:
	it is from A class 
	
	#It can be inherited another way
	class A:
	  def test(self):
	    print("it is from A class ")
	class B:
	  def test(self):
	    print("it is from B class ")
	class C(B,A):
	  pass

	obj = C()
	obj.test() 

	o/p:
	it is from B class
	
Q33. Which methods/functions do we use to determine the type of instance and inheritance?

	Two built-in functions isinstance() and issubclass() are used to check inheritances.
     The function isinstance() returns True if the object is an instance of the class or other
     classes derived from it.Each and every class in Python inherits from the base class object.
     
     Similarly, issubclass() is used to check for class inheritance.
     
Q34.Explain the use of the 'nonlocal' keyword in Python.

	The nonlocal keyword is used to work with variables inside nested functions, where the variable 
    should not belong to the inner function.
    Use the keyword nonlocal to declare that the variable is not local.
    
    Ex:
	def myfunc1():
	  x = "Big"
	  def myfunc2():
	    nonlocal x
	    #x = "Data"
	  myfunc2() 
	  return x

	print(myfunc1())
	
	o/p:
	Big
	
Q35. What is the global keyword?

            The global keyword is used to create global variables from a no-global scope, e.g. inside a function.
	Declare a global variable inside a function, and use it outside the function:

	#create a function:
	def myfunction():
	  global x
	  x = "hello"
	myfunction()

	#x should now be global, and accessible in the global scope.
	print(x)

        o/p:
	hello
