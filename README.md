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

Multidimensional arrays: in java we use multidimensional arrays to store more complex sets of data, for example we can use a 2 dimensional array to store a matrix or a 3 dimensional array to store data for a cube. This is useful when it comes to scientific computtions. In order to change a one dimensional array into a 2 dimensional array, all you need to do is add an extra set of square brackets 

      int[][] numbers = new int[2][3];
      ->this matrix will have 2 rows and 3 columns.

What happens if you try to run arrays.toString on a multidimensional array?
you would just get the addresses of the rows in memory, in order to get print the values of multidimensional arrays, you must ust the method arrays.deepToString

Another way to print multidimensional arrays: 
    
      int[][] = numbers {{1,2,3},{4,5,6}};
      
 Constants: In java we can change the value of a variable at anytime during the programs life cycle. But what if we want the value of a variable to stay the same every time? 

     final float PI = 3.14;
     
Adding the final keyword to any variable will turn it into a constant, therefore making it unable to change its value.
Note: by convention we normally set final variables to all caps

Casting:
Lets say:

      short x = 1;
      int y = x+2;

When you print out the result, the result will be 3. However that happens under the hood is that java first converts the short into an integer and then adds. When moving up in data type, this is known as implicit or automatic casting. The order of data type for implicit casting is as shown:

       byte>short>int>long>long>float>doublbe
       ----------Implicit casting-------->
But what would happen if you needed to cast the other way? you would need to EXPLICITLY cast the variable in the method

      short x = 1;
      int y = (int)x+2;
      
Here the value of x is explicitly casted or converted into an integer and then added. Had there have been a decimal value for x, any value after the decimal point would be removed as the value of x gets casted into a integer
Note: this is only possible when youre casting 2 similar data types. You CANNOT for example, turn a string into an integer, that calls for a seperate method. In order for a string to be recognized as a number, you would have to use whats called a wrapper class

Integer.parseInt();

Why is parsing important?
Most frameworks for building user interfaces whether youre bulding a desktop, mobile or web application , we will always revieve the input from the user as a string to its important to know how to parse numbers.

Comparison operators
== : will check to see if 2 variables are equal
!= : will check to see if 2 variables are not equal
>= > < <= = other commonly used operators
