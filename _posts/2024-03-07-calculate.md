---
layout: post
title:  "연산자"
date:   2024-03-07
excerpt: ""
tag:
- announcement
comments: true
---

# 산술 연산자
- 정수, 실수, 문자에 적용
- +(더하기), -(빼기), *(곱하기), /(나누기)
- % : 나머지 연산자

# 예제 1
    public class OperatorArithmetic {
	    public static void main(String args[]) {
		    int int1 = 5, int2 = 29;
		    System.out.println("29 * 5 = " + int2 * int1);
		    System.out.println("29 / 5 = " + int2 / int1);
		    System.out.println("25 / 5 = " + 25 / int1);
		    System.out.println("29 % 30 = " + 29 % 30);
		
		    System.out.println("'a' % 'b' = " + 'a' % 'b');
		    System.out.println("29.1f % 30.7 = " + 29.1f % 30.7);
	    }
    }
## 10번째 줄에서 30.8은 double형이므로 29.1f가 double로 형변환된다.

# 관계 연산자
- 결과는 boolean(참/거짓) 형태
- 노건이 필요한 경우
- 크기 비교 : <. <=, >, =>
- 동등 비교 : ==(같다), !=(같지 않다)

# 논리 연산자
- 결과는 boolean(참/거짓) 형태
- 그리고 : &&
- 또는 : ||

# 예제 2
    public class OperatorLogical {
	    public static void main(String args[]) {
		    int int1 = 5, int2 = 6, int3 = -1;
		    if(int1 < int2 && int3 < 0)
			    System.out.println("int1 < int2 && int3 < 0");
		    if(int1 < int2 && int3 > 0)
			    System.out.println("int1 < int2 && int3 > 0");
		    if(int1 > int2 || int3 < 0)
			    System.out.println("int1 > int2 || int3 < 0");
		    if(int1 > int2 || int3 > 0)
			    System.out.println("int1 > int2 || int3 > 0");
	    }
    }

# 증가, 감소 연산자
- ++ : 값을 1 증가
- -- : 값을 1 감소

    public class OperatorIncrement {
        public static void main(String args[]) {
		    int i = 0, b;
		    b = i++;
		    //	b = i;
		    //	i = i + 1;
		    System.out.println("(i++) b = " + b);
		    System.out.println("(i++) i = " + i);
		
		    i = 0;
		    b = ++i;
		    //	i = i + 1;
		    //	b = i;
		    System.out.println("(++i) b = " + b);
		    System.out.println("(++i) i = " + i);
  
            char c = 'A';
		    System.out.println("c++ = " + c++);
            System.out.println("++c = " + ++c);
        }
    }

# 기타 연산자

| 유형 | 표현 |
|:--------|--------:|
| int max = (a>b) ? a : b | (a > b) 식이 참이면 a, 거짓이면 b를 max 값으로 저장 |
| int b = a | a를 b에 저장 |
| int b += a | b = b + a |
| -=, *=, 등 | +=의 빼기, 곱하기 버전 |
{: rules="groups"}
