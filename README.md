<html>
<head>

</head>
<body>
    <h1>Insertion Sort</h1>

<h3>Introduction</h3>

Given an array of primitive data, insertion sort will sort each element from least to greatest or greatest to least. The algorithm iterates through the array, and places each element in the correct spot starting from the first element. Therefore, with each iteration, the sorted section of the array grows by one, until the end of the array is reached, at which point the entire array is sorted. The best case scenario for this algorithm’s efficiency is if the array is already sorted. The worst case is that the array is sorted in the opposite order intended. This tutorial uses Java to implement the algorithm. The implementation may look different in other languages. 

<h3>List of Materials</h3>

--Java v7.0 or newer
--Java environment of your choice (Eclipse, IntelliJ IDEA, etc.)

<h3>FAQs</h3>

Q>Can insertion sort be implemented in other languages?
A>Yes it can.
Q>Is insertion sort the only sorting algorithm that exists?
A>No, insertion sort is just one well known example of many sorting algorithms.

<h3>Troubleshooting/Where to Get Support</h3>

Most programming environments have a built in debugger, which is an extremely helpful tool in deducing errors within implemented algorithms like insertion sort.

<h3>How to Contribute</h3>

Please email porterwa@appstate.edu should you have anything to contribute.

<h3>Licensing</h3>

Permissions include commercial and personal use, distribution, and modification.

<h3>Instructions</h3>

    1. Define the method header:
       
           public static void sort(int[] ar){}
           
           The method is static so that an object does not have to be created to call it. The method does not return anything, rather it takes an array as input (int[] ar) and    adjusts the placement of the elements within the array. This tutorial uses an array of integers, but any other primitive data type will suffice (including char).
                       
    2. public static void sort(int[] ar){
           for (int i=0;i<ar.length;i++){}
                           }
                   We must immediately enter a for loop. This is the for loop that iterates through the entire array once. The variable i keeps tracks of where the unsorted section of the array begins.
                   
    3. for (int i=0;i<ar.length;i++){
           int holder = ar[i];
       }
       Soon the algorithm may be moving around elements, so we have to keep track of the element that we want to sort. We declare a variable, holder, and set it equal to the current element.
       
    4. for (int i=0;i<ar.length;i++){
           int holder = ar[i];
           int x=i-1;
       }
       We declare another variable and set it equal to one less than i. We will need this to iterate through the already sorted section of the array.
       
    5. for (int i=0;i<ar.length;i++){
           int holder = ar[i];
           int x=i-1;
           while(x >= 0 && holder < ar[x]) {}
       }
       We declare a while loop. This will iterate through the front of the array (the unsorted part). One of the conditions is “holder < ar[x]”. When the loop sees an element that is less than the current element, it will stop iterating. 
       
    6. for (int i=0;i<ar.length;i++){
           int holder = ar[i];
           int x=i-1;
           while(x >= 0 && holder < ar[x]) {
              ar[x+1] = ar[x--];
           }
       }
       Inside the while loop, we set each element of the sorted section equal to the element just before it. This creates space for the current element(holder). The while loop will continue doing this until it finds an element less than holder (or until it reaches the very beginning of the array). After this line executes, x will decrease by one. This is accomplished by the two minus signs after x and ensures that the loop is making progress.
       
    7. public static void sort(int[] ar) {
    for (int i=0;i<ar.length;i++){
        int holder=ar[i];
        int x = i - 1;
        while(x >= 0 && holder < ar[x]) {
            ar[x+1] = ar[x--];
        }
        ar[x+1] =holder;
    }
    }
       Above is the completed method. The newly added line, “ar[x+1] =holder”, executes after the while loop has found the spot where the current element belongs.
</body>
</html>
