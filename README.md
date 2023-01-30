# Gene's Green
Gene's Green Golf Center is remodeling their golf course, and has hired you to help write a program that will be used to determine what materials will be needed to complete the project. There are 18 holes on the golf course, but Gene likes to keep things simple, so every hole looks very similar. A typical Hole at Gene's Green Golf Center looks like the image below - only the length and width change.
![Screenshot](https://raw.githubusercontent.com/phillamiller/Images/master/Gene's%20Green%20Diagram.png "Gene's Green golf course example")
```
import java.util.Scanner;

public class GenesGreen {
   public static void main(String[] args) {
      Scanner in = new Scanner(System.in);
      
      System.out.print("Enter Course Length : ");
      double length = in.nextDouble();
      
      System.out.print("Enter Course Width  : ");
      double width = in.nextDouble();
      
      System.out.println();
      
      double areaOfTee = areaOfCircle(width / 3.0);
      double areaOfPuttingGreen = areaOfCircle(width * 2.0 / 3.0);
      double areaOfSandTrap = areaOfCircle(width / 4.0);
      
      double totalYards = areaOfRectangle(length, width);
      int smoothSod = (int)Math.ceil(areaOfTee + areaOfPuttingGreen);
      int roughSod = (int)Math.ceil(totalYards - smoothSod - areaOfSandTrap);
      
      int totalSand = (int)Math.ceil(areaOfSandTrap * 9 * 2 * 80 / 2000);
      
      System.out.println("Total square yards of rough sod  : " + roughSod);
      System.out.println("Total square yards of smooth sod : " + smoothSod);
      System.out.println("Tons of sand                     : " + totalSand);
      System.out.println("Number of bushes                 : " + numberOfBushes(width, length));
      
      
   }
   
   public static double areaOfCircle (double diameter) {
      double Pi = 3.1415;
      double radius = diameter / 2;
      double area = Pi * radius * radius;
        
      return area;
   }
   
   public static double areaOfRectangle (double width, double height) {
      double area = width * height;
      
      return area;
   }
   
   public static double perimeterOfRectangle (double width, double height) {
       
    return 2 * width + 2 * height;
   }
   
   public static int numberOfBushes (double width, double length) {
      int totalBushes = (int)perimeterOfRectangle(width, length) - 2;
      
      return totalBushes;
   }   
}
```
