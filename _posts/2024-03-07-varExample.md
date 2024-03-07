---
layout: post
title:  "주석, 변수, 상수"
date:   2024-03-07
excerpt: ""
tag:
- example
comments: true
---

# 주석 : 실행에 영향을 주지 않는 영역
## 한줄: // 뒤에 오는 영역
## 여러줄: /* ~ */ 안의 모든 영역
## 주석의 용도: 코드가 길어지면 뭐가 뭔지 알기 힘들기 때문에 메모처럼 그 코드가 어떠 기능을 하는지 적는데에 사용된다.

  public class Annotation {
	  public static void main(String[] args) { 
		  System.out.println("%s", "Hello, World!");		//	string
		  // System.out.println("%s", "Hello, World!");
		  /*
		  System.out.println("%s", "Hello,");
		  System.out.println("%s", "World!");
		  */
	  }
  }

# 변수 : 계속적으로 변할 수 있는 값(예: 인구)
# 상수 : 변할 수 없는 값(예: 원주율은 3.141592...)
