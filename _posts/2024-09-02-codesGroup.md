---
layout: post
title:  "코드 예시들 모음 및 실습 제출(함수와 클래스)"
date:   2024-09-02
excerpt: ""
tag:
- example
comments: true
---

PPT: https://www.miricanvas.com/v/13genyr
답안 제출: https://forms.gle/268buqsssVo9uheq8

실습 PPT: https://www.miricanvas.com/v/13otvxx
답안 제출: https://forms.gle/wXeENDnKu7YJpDTp7

# Scanner 예시

    import java.util.Scanner;

    public class test {
        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);
            System.out.println("Enter Number");
            int intValue = scanner.nextInt();
            System.out.println(intValue);
        }
    }

# 함수 예시

    public class Main {
      static void myMethod() {
        System.out.println("Executed!");
      }

      public static void main(String[] args) {
        myMethod()
      }
    }

# 매개변수 예시

    public class Main {
      static void myMethod(String fname) {
        System.out.println(fname + " Refsnes");
      }
  
      public static void main(String[] args) {
        myMethod("Liam");
        myMethod("Jenny");
        myMethod("Anja");
      }
    }

# 리턴 예시

    public class Main {
      static int myMethod(int x) {
        return 5 + x;
      }
  
      public static void main(String[] args) {
        System.out.println(myMethod(3));
      }
    }

# 클래스 예시

    public class Main {
      int x;
  
      public Main() {
        x = 5;
      }
  
      public static void main(String[] args) {
        Main myObj = new Main();
        System.out.println(myObj.x);
      }
    }
