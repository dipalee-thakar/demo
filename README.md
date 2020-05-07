package com.example.Testing;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.Scanner;

public class BubbleSortAlgorithm {

public static void main(String[] args) throws IOException {
//BufferedReader
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        String name = br.readLine();                // Reading input from STDIN
        System.out.println("No.of person, " + name + ".");    // Writing output to STDOUT

        //Scanner
        Scanner s = new Scanner(System.in);
        ArrayList<String> inputs = new ArrayList<String>();
        inputs.add((s.nextLine()));
        System.out.println("inputs: " + inputs);
       
        String newString = "";
        for (String st : inputs) {
        newString = newString + st;
        }
        System.out.println("new String: " + newString);
        String[] sg = newString.split(" ");
       
        int arr[] = Stream.of(sg).mapToInt(Integer::parseInt).toArray();

        int arr[] = { 22,56,98};
        int n = arr.length;
        bubbleSort(arr, n);
        System.out.println("Sorted array: ");
        printArray(arr, n);

       n = deleteElement(arr, n, x); 
   
        System.out.println("Modified array is"); 
        for (int i = 0; i < n; i++) 
            System.out.print(arr[i]+" "); 


}
static int deleteElement(int arr[], int n, int x) 
    { 
        // Search x in array 
        int i; 
        for (i=0; i<n; i++) 
            if (arr[i] == x) 
                break; 
   
        // If x found in array 
        if (i < n) 
        { 
            // reduce size of array and move all 
            // elements on space ahead 
            n = n - 1; 
            for (int j=i; j<n; j++) 
                arr[j] = arr[j+1]; 
        } 
   
        return n; 
    }

private static void printArray(int[] arr, int size) {
int i;
        for (i = 0; i < size; i++)
            System.out.print(arr[i] + " ");
        System.out.println();

}

private static void bubbleSort(int[] arr, int n) {
int i, j, temp;
       boolean swapped;
       for (i = 0; i < n - 1; i++)  
       {
           swapped = false;
           for (j = 0; j < n - i - 1; j++)  
           {
               if (arr[j] > arr[j + 1])  
               {
                   // swap arr[j] and arr[j+1]
                   temp = arr[j];
                   arr[j] = arr[j + 1];
                   arr[j + 1] = temp;
                   swapped = true;
               }
           }
 
           // IF no two elements were  
           // swapped by inner loop, then break
           if (swapped == false)
               break;
       }

}
}
