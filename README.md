using System;
public class ReadOnlyTest
{
    class MyClass
    {   public int x;
        public readonly int y = 25; // Initialize a readonly field
        public readonly int z;
        public MyClass()
        {          
		 z = 24;   // Initialize a readonly instance field
        }
         public MyClass(int p1, int p2, int p3)
        {   x = p1;
            y = p2;
            z = p3;
          }
         public void add() {
          Console.WriteLine(y); }
    }
    public static void Main()
    {   MyClass p1 = new MyClass(11, 21, 32);   // OK
        Console.WriteLine("p1: x={0}, y={1}, z={2}", p1.x, p1.y, p1.z);
        MyClass p2 = new MyClass();
        p2.x = 55;   // OK
       // p2.z = 88;
        Console.WriteLine("p2: x={0}, y={1}, z={2}", p2.x, p2.y, p2.z);
    }
}
