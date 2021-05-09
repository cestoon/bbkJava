代码是这个样子
```
public class Hello {
    public static void main(String[] args) {
        int a = 1;
        byte b = 11;
        float f = 1.111f;
        short s = 2;
        long l = 333l;
        double d = 4.4d;
        char c = 'c';
        boolean boo = true;
        a += 1;
        if (a == 2){
            a -=1;
        }
        for (int i = 0; i <10 ; i++) {
            f += f;
        }
        System.out.println(a);
        System.out.println(f);
    }
}


```
字节码是这个样子
```
Classfile /Users/fbk/Documents/java/geek/geekField/src/jvm/Hello.class
  Last modified 2021年5月9日; size 624 bytes
  MD5 checksum 52118612cd7a8ecf9fb13fb80f014d84
  Compiled from "Hello.java"
public class jvm.Hello
  minor version: 0
  major version: 55
  flags: (0x0021) ACC_PUBLIC, ACC_SUPER
  this_class: #10                         // jvm/Hello
  super_class: #11                        // java/lang/Object
  interfaces: 0, fields: 0, methods: 2, attributes: 1
Constant pool:
   #1 = Methodref          #11.#22        // java/lang/Object."<init>":()V
   #2 = Float              1.111f
   #3 = Long               333l
   #5 = Double             4.4d
   #7 = Fieldref           #23.#24        // java/lang/System.out:Ljava/io/PrintStream;
   #8 = Methodref          #25.#26        // java/io/PrintStream.println:(I)V
   #9 = Methodref          #25.#27        // java/io/PrintStream.println:(F)V
  #10 = Class              #28            // jvm/Hello
  #11 = Class              #29            // java/lang/Object
  #12 = Utf8               <init>
  #13 = Utf8               ()V
  #14 = Utf8               Code
  #15 = Utf8               LineNumberTable
  #16 = Utf8               main
  #17 = Utf8               ([Ljava/lang/String;)V
  #18 = Utf8               StackMapTable
  #19 = Class              #30            // "[Ljava/lang/String;"
  #20 = Utf8               SourceFile
  #21 = Utf8               Hello.java
  #22 = NameAndType        #12:#13        // "<init>":()V
  #23 = Class              #31            // java/lang/System
  #24 = NameAndType        #32:#33        // out:Ljava/io/PrintStream;
  #25 = Class              #34            // java/io/PrintStream
  #26 = NameAndType        #35:#36        // println:(I)V
  #27 = NameAndType        #35:#37        // println:(F)V
  #28 = Utf8               jvm/Hello
  #29 = Utf8               java/lang/Object
  #30 = Utf8               [Ljava/lang/String;
  #31 = Utf8               java/lang/System
  #32 = Utf8               out
  #33 = Utf8               Ljava/io/PrintStream;
  #34 = Utf8               java/io/PrintStream
  #35 = Utf8               println
  #36 = Utf8               (I)V
  #37 = Utf8               (F)V
{
  public jvm.Hello();
    descriptor: ()V
    flags: (0x0001) ACC_PUBLIC
    Code:
      stack=1, locals=1, args_size=1
         0: aload_0
         1: invokespecial #1                  // Method java/lang/Object."<init>":()V
         4: return
      LineNumberTable:
        line 8: 0

  public static void main(java.lang.String[]);
    descriptor: ([Ljava/lang/String;)V
    flags: (0x0009) ACC_PUBLIC, ACC_STATIC
    Code:
      stack=2, locals=12, args_size=1
         0: iconst_1
         1: istore_1
         2: bipush        11
         4: istore_2
         5: ldc           #2                  // float 1.111f
         7: fstore_3
         8: iconst_2
         9: istore        4
        11: ldc2_w        #3                  // long 333l
        14: lstore        5
        16: ldc2_w        #5                  // double 4.4d
        19: dstore        7
        21: bipush        99
        23: istore        9
        25: iconst_1
        26: istore        10
        28: iinc          1, 1
        31: iload_1
        32: iconst_2
        33: if_icmpne     39
        36: iinc          1, -1
        39: iconst_0
        40: istore        11
        42: iload         11
        44: bipush        10
        46: if_icmpge     59
        49: fload_3
        50: fload_3
        51: fadd
        52: fstore_3
        53: iinc          11, 1
        56: goto          42
        59: getstatic     #7                  // Field java/lang/System.out:Ljava/io/PrintStream;
        62: iload_1
        63: invokevirtual #8                  // Method java/io/PrintStream.println:(I)V
        66: getstatic     #7                  // Field java/lang/System.out:Ljava/io/PrintStream;
        69: fload_3
        70: invokevirtual #9                  // Method java/io/PrintStream.println:(F)V
        73: return
      LineNumberTable:
        line 10: 0
        line 11: 2
        line 12: 5
        line 13: 8
        line 14: 11
        line 15: 16
        line 16: 21
        line 17: 25
        line 18: 28
        line 19: 31
        line 20: 36
        line 22: 39
        line 23: 49
        line 22: 53
        line 25: 59
        line 26: 66
        line 27: 73
      StackMapTable: number_of_entries = 3
        frame_type = 255 /* full_frame */
          offset_delta = 39
          locals = [ class "[Ljava/lang/String;", int, int, float, int, long, double, int, int ]
          stack = []
        frame_type = 252 /* append */
          offset_delta = 2
          locals = [ int ]
        frame_type = 250 /* chop */
          offset_delta = 16
}
SourceFile: "Hello.java"

```