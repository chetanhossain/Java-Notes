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
|| = or operator (either condition need to be fulfilled for the statement to be true)
&& = and operator (both conditions need to be fulfilled for the statement to be true)
! = not operator (the condition needs to be untrue for the statment to be true)

If statements: used in java for programs to make decisions based upon meeting certain conditions
         
         int temp = 32;
         if (temp >30);
         System.out.println("its a hot day");
         else if (temp >20);
         System.out.println("it is nice outside");
         else
         System.out.println(it is cold)

->The method after your if statement needs to be the action that must be performed if the statement is true
->You start your if statement with if and then followed by else if and else when you wish to end the if statement.

Switch statements: work similarly to if statements, they execute different parts of code based on the value of an expression

        switch(role){
        case: "admin"
        System.out.println("You are admin")
        break;
        
        case: "moderator";
        System.out.println("you are a moderator");
        break;
        
        Default:
        System.out.println("you are a user)"
        
->switch: switch operator
->fase is a substitute for clauses
->NOTE: we use break to break out of a switch statement. You do not need to break out of a default statement.

For Loops:
->In java there are many times where you need to have an action performed multiple times.

      Lets say you want to have this action printed 5 times:
      
      System.out.println("Hello World");

You can type this out 5 times, or you can use whats called a for loop.

       for(int i = 0; i<5; i++);
       System.out.println("Hello World)"

When running a for loop you need to hit 3 main conditions 
1. You need to declare the loop/counter variable and initialize it(in this case we take our variable "i" and set it to 0)
2. You need to create the boolean expression to determine the length of the loop (here we set the length to 5, so as long as the value of i stays under 5, then the loop will continue)
3. Determine what incraments the loop will be going (here "++" means that the loop will be going up in incrament of 1)

How does this loop work?
1. The first thing that java does is initialize the variable to zero.
2. It then evaluates the next condition (is i[0]>5?)
3. If the above condition is true, the loop will execute the body of the statement (In the above case, it will print out "Hello world")
4. The control will then move on to the next part of the loop which is incrementing the value of i up by 1
5. It will repeat this process until the 2 second condition is not true anymore, and in that case the control will then move out of the loop

NOTE: For reference you can change what value you want the variable to be instantialized to, you can change the size of the loop, and even change how the loop will be incremented.
   
           for(int i = 5; i>0; i--);
           
While Loops: While loops are very similar in functionlity, but different in terms of syntax

         int i = 0;
         while(i>0){
         System.out.println("Hello World")
         i--;

For loops are better when you know ahead of time how many times you want your loop to run. While loops are good for when you dont know how many times you need your loop to run. Lets tske an example where the loop will keep running until the user tells us to quit

        Scanner scanner - ew scanner(System.in);
        string input = "";
        while(!intput.equals(quit);
        System.out.println(Input: ");
        input = scanner.next().toLowerCase();
        System.out.println(input)

Note: For reference you want to keep you scanner class outside of the loop because had you put it in the loop, if you input 10 different objects the scanner would create 10 different objects instead of creating one object and giving it different values.

Do...While loops: In java there is something called a do while loop which is similar to a while loop but it will always execute at least once.

     do{
     System.out.println("Input": ");
     input = scanner.next().toLowerCase();
     System.out.println(input);
     }while (!input.equals("quit")
   
Do while loops will always run the body of the loop once because its designed to check the condition after executing the body. While people mainly use while loops, there are some situations where do while loops are useful.

Break and continue statements
 
      
      while(true){
      System.out.println("Input: ");
      Input = scanner.next.toLowerCase;
      if(input.equals("pass");
      continue;
      if(input.equals("quit"))
      break;
     
When you add the continue keyword after a condition, then if the condition is fulfilled, the control will move back to the beginning of the loop.
When you add the break keyword after a condition, then if the condition if fulfilled, the control will move out of the loop.
In the above mentuoned case, if the user types in pass, the loop will repeat meaning the console wont print anything but it will ask for another input. If the user types in quit, the console wont print anything out and the control will move out of the loop.

For each loop:

       String[] fruits = {"Apple" , "Mango" , "Orange"};
       for{String fruit: fruits)
       System.out.println(fruit);

In a for each loop you want to create a variable based on the types of items in the array.
Limitations of a for each loop:
->For each loops only iterate forward 
->You dont have access to each index of the loop. It will only tell you the value of that instance of the array.
