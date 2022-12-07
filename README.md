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
     			   
