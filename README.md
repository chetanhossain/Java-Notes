 Java-Notes
 
 Variables: Variables are used to temporarily store data

Imagine in this program you want to store someones age in memory. You would instantiate a variable like this:

          int age = 40;
         
     ->int: type of variable
     ->age: name/label/identifier
     ->40: value

Instantializing a variable: giving the variable a value
You can also change the value of a variable

int age = 30;
age = 35;

the output of this would be 35 

Note: we use primitive type variables to store variables like numbers, characters, or boolean values. We use reference types to store date, string, or other complex objects. 
There are 8 types of primitive type variables: byte , short , int , long , float , double , boolean and char. Everything else is a reference type.
NOTE: When declaring a primitive type variable, you dont need to allocate memory. However when declaring  a reference variable, you want to declare the variable, give it a name, and then set it to a new variable.

        Date now = new Date();
        ->Date: imports the date class from the java util package
        ->now: identifier. Now has become an object of the date class. From now on when refer to "now" variable, know it gets taken from the date class.
       
       
When you create a reference type, first it will create the object in a memory location and then create the variable that refers to that address in memory

        Point point1 = new point(x:1, y:1);
        -> what happens here is that first at a random location in memory (lets say the address is 100), create the object of point(1,1). So now when you try to refer to point 1, youre not going to get the value of (1,1) returned, instead you will get the address of where thst object is (100).

      Point point1 = new point(x:1,y:1);
      Point point2 = point1;
 
What happens here is both point 1 and 2 are going to refer to the same point in memory for the object (1,1). This means that when printed, both will give the output of 100. This also means that when one of the points get changed, so does the other.
Note: In java when creating a string variable, instead of typing:
           
           String message = new string ("hello");
       
You can actually instantialize it into a string literal and it does the same thing
        
            String message = "hello";
            
You can also "concatinate" or join a strnig with another string operator

            String message = "hello" + " world";

Because string is a class that we are creating an instance out of, it has members we can access using the dot operators

                  message.endsWith
                  message.length
                  
Arrays

We use arrays in java to store a list of objects, like a list of numbers, or a list of people

            int numbers[] = new int[5];
            ->int: declaring the type
            ->numbers: name of the array
            ->new: arrays are reference type variables, you set new to allocate memory for the object
            
            
            int[] numbers = new int[5];
            numbers[0] = 1;
            
What we are doing here is were taking the numbers array and adding a value to the first index of that array

Note: what happens when you try to set a number outside of the arrays parameters?

             numbers[10] = 3;
->because the array was instantialized to only have 5 indexes, there is no 10th number in the array. Therefore java does something called raising an exception
Exceptions: java's way of reporting an error. In the case above, an exception was raised and the program crashed.

Remeber: when you try to print the array, you will just get a random collection of numbers and letters, this is because arrays are a reference type variable and it will print out the array's address in memory

So how would you be able to print out the numbers in an array?
Java has a util class for arrays that has different methods 

    Arrays.toString(float a);       ->the array.tostring method contsins mutliple different implementations. It can take a float, int, btye, etc.
                   (int a);          This is known as method overloading
                   (byte a);    
          
 In order to print your array, you would need to run this method:

            System.out.println(Arrays.toString(numbers);
            
            
Note: There is an easier way to initialize the array if you already know what items are going to be put into the array (using curly braces);

      int[] numbers = {2,3,5,1,4};
      
This will automatically set the size of the array
Note: In java, arrays are a fixed length, meaning you cannot add or remove any additional items once the array has been set
