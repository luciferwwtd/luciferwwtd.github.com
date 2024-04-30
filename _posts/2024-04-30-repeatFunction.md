---
layout: post
title:  "제귀함수"
date:   2024-04-30
excerpt: ""
tag:
- example
comments: true
---

# 제귀함수
## 함수가 자기자신을 호출하는 식
## 종료조건이 필수

# 제귀함수 예제(유클리드 알고리즘을 제귀함수 사용하지 않고 구현)

    public class EuclidWhile {
    	public static void main(String[] args) {
    		int value1 = 30;
    		int value2 = 36;
    		int originalValue1 = value1;
    		int originalValue2 = value2;
    		while(value1%value2 != 0) {
    			int temp = value1;
    			value1 = value2;
    			value2 = temp % value2;
    		}
    		System.out.println("최대공약수:" + value2);
    		System.out.println("최소공배수:" + originalValue1*originalValue2/value2);
    	}
    }

# 제귀함수 예제 2(유클리드 알고리즘을 재귀함수 사용하여 구현)

    public class EuclidRecursive {
    	static int recursive(int value1, int value2){
    		if(value2 == 0) return value1;
    		return recursive(value2, value1%value2);
    	}
    	public static void main(String[] args) {
    		int value1 = 50;
    		int value2 = 20;
    		System.out.println(recursive(value1, value2));
    	}
    }

## 반복문 및 조건문이 한줄일 경우 3번 줄과 같이 붙여서 표기할 수 있다.