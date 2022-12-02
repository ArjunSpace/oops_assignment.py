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
