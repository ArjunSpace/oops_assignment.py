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
         include the attributes which were called in the init method of its class
         
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
          
