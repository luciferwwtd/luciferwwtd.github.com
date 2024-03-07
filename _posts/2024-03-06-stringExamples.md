---
layout: post
title:  "Scanner, print"
date:   2024-03-06
excerpt: ""
tag:
- example
comments: true
---
# System.out.println

  public class PrintFormat {
	  public static void main(String[] args) { 
		  System.out.println(1);
		  System.out.println('A');
		  System.out.println("Hello, World!");
		  System.out.println(3.14);
	  }
  }

### 출력 방법 : print, printf, println
### System.out.println에서 println을 위 3가지 중 하나로 바꿔서 테스트 해봐도 됨
### 솔직히 어차피 결국엔 println만 쓰게 됨

# Scanner

import java.util.Scanner;

  public class InputFormat {
	  public static void main(String[] args) {
		  Scanner scanner = new Scanner(System.in);
		  System.out.println("Enter Number:"); 
 		  int intValue = scanner.nextInt();
 		  System.out.println(intValue);
		
 		  System.out.println("Enter Float:"); 
 		  float floatValue = scanner.nextFloat();
 		  System.out.println(floatValue);
		
		  System.out.println("Enter String with Space:");
		  String stringValue = scanner.next();
 		  System.out.println(stringValue);
		
		  stringValue = scanner.nextLine();
		  System.out.println(stringValue);
		
		  scanner.close();
	  }
  }

### 18번째 줄에선 이전 Scanner로 읽어들인 문자를 사용한다
### next() : 토큰(어절) 마다 하나 씩 읽어온다.
### nextLine() : 한 문장 전체를 읽어온다.

**입력은 Scanner, 출력은 System.out.println**
{: .notice}
