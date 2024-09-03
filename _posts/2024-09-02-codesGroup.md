---
layout: post
title:  "코드 예시들 모음 및 실습 제출"
date:   2024-09-02
excerpt: ""
tag:
- example
comments: true
---

PPT: https://www.miricanvas.com/v/13genyr

답안 제출: https://forms.gle/268buqsssVo9uheq8

# 함수 예시

public class Main {

  static void myMethod() {

    System.out.println("I just got executed!");

  }

  
  public static void main(String[] args) {

    myMethod();

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
  
    // Create a class constructor for the Main class
    public Main() {
      x = 5;
    }
  
    public static void main(String[] args) {
      Main myObj = new Main();
      System.out.println(myObj.x);
    }
  }
