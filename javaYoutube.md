# 자바 강좌 헷갈리는 부분 & 핵심 정리 - 동 빈

## 2강 - 변수, 상수

변수 : 프로그래이 실행되는 동안에 언제든지 저장된 값이 변경될 수 잇는 공간을 의미
상수 : 한 번 정해지면 값을 변경할 필요가 없는 데이터를 의미

``` Java

final static double PI = 3.145292; //상수는 main 함수 밖에 선언! 
//final : 한 번 선언되면 절대 바뀔 수 없다는 뜻
//static : 하나의 클래스에서 공유하는 자원

 
```

 변수 관련 상식 : 자바에서는 변수 초기화를 하지 않으면 사용할 수 없다.
 정수 변수 안에 실수만 넣으면 정수 부분만 변수에 저장된다.
 실수 값을 반올림할 때는 변수에 0.5를 더한 뒤에 정수형으로 정수형으로 형 변환을 하면 된다.
 
 반올림 한 값 = (int)(실수+0.5);
 
 ## 3장 - 자료형
 
 ``` java
 
 int a = 200;
 System.out.println("10진수 : " + a); //10진수 출력
 System.out.format("8진수 " + %o\n", a); // 10진술를 8진수로 출력 , %o : 형식지정자(문자열 포메팅???), %x : 16진수로 출력
 // System.out.println은 출력 후 자동으로 한 줄 띄움, format과 print는 안 띄움
 ```
 
 String은 substring 함수를 가지고 있다.
 
 자료형 관련 상식 : 기본적으로 정수를 나태내는 자료형이 많은 이유는 각 자료형이 차지하는 메모리 공간의 크기가 다르기 때문
 double 형이라고 하더라도 과도하게 큰 수를 저장하고자 하면 잘못된 계산 결과가 나올 수 있다.
 소수점 표기 형식을 지수 형식으로 출력하고 싶다면 %e를 이용하면 된다.
 자바의 String은 클래스 기반의 비원시적인 자료형이다.
 
 ## 4장 - 연산자
 
 조건 ? 참 : 거짓 연산의 개념을 바르게 이해하고 프로그램을 작성해보자
 
 Boolean experssion ? True part : False part
 
 연산자 관련 상식 : i++와 ++i는 단순히 갑슬 증가시키려는 목적이라면 그 기능이 동일하지만 출력하는 문자 안에서는 달라짐
 100<x<200은 잘못된 표현이다. (100<x) && (x<200)로 and 연산자로 표현하는 것이 올바른 연산 식 표현이다.
 i++는 i+= 1과 동일한 표현이다. 또한 i = i+1과도 동일한 표현이다. 모두 1만큼 증가시킨다는 의미를 갖고있다.
 
 
 ## 5장 - 조건문 & 반복문 (1)
 
 조건문 반복문은 논리적 흐름을 의미
 
 -  If문을 이용하여 문자열이 특정 문자열을 포함하는지 확인하는 프로그램을 작성

``` java
 public class Main {

 	public static void main(String[] args) {
	
		String a =  "I Love you";
	 	if(a.contains("Love")) {
			System.out.println("Me too");	
		} 
		else 
		{
			System.out.println("No");
		}
	}

}

```
 
## 6장 - 조건문 & 반복문 (2) 

 -  점수에 따라서 다른 메세지를 출력하는 프로그램 작성


 ``` java

public class Main {

	public static void main(String[] args) {
		
		 int score = 92;
		 
		 if(score>=90) {
			 System.out.println("A+입니다");
		 }
		 else if(score>=80) {
			 System.out.println("B+입니다");
		 }
		 else if(score>=70) {
			 System.out.println("C+입니다");
		 }
		 else 
		 {
			 System.out.println("F입니다");
		 }

	}

}
```
 - 문자열과 정수형을 각각 조건문을 이용해 활용해보고 그 차이점을 공부

``` java

 
public class Main {

	public static void main(String[] args) {
		
		String a = "MAN";
		int b = 0;
		
		// 자바는 String을 비교할 때 equal()을 이용한다.
		// 그 이유는 String은 다른 자료형과 다른 문자열 자료형이기 때문
		if(a.equals("MAN"))
		{
			System.out.println("남자 입니다");
		}
		else
		{
			System.out.println("여자 입니다");
 		}
		if(b == 3) 
		{
			System.out.println("b는 3입니다");
		}
		else
		{
			System.out.println("b는 3이 아닙니다");
		}
		if(a.equalsIgnoreCase("man")&& (b == 0))
		{
			System.out.println("참입니다");
		}
		

	}

}
```

 - While문을 이용하여 1부터 1000까지의 합을 출력하는 프로그램

``` java

public class Main {

	public static void main(String[] args) {
				
		int i = 1, sum = 0;
		while(i<=1000)
		{
			sum += i++; // sum = sum + i++;
		}
		System.out.println(sum);
	}
}
```

 - for문을 이용하여 삼각형을 출력하는 프로그램을 작성해봅시다
  
```java
public class Main {
	final static int N = 15;
	public static void main(String[] args) {
		for(int i = N; i>0; i--)
		{
			for(int j = i; j>0; j--)
			{
				System.out.print("*");
			}
			System.out.println("");
		}
	}
}
```
조건문 & 반복문 기본 상식 : 하나의 비교 연산자는 true 혹은 false를 반환하게 된다
모든 조건문, 반복문에서는 왠만해서 무조건 괄호를 적용
for문 혹은 while문은 얼마든지 중첩 가능
for(;;)는 while(true)와 똑같이 무한 루프라는 의미로 동작
brake;를 이용하여 반복문을 즉시 빠져나올 수 있다.



 ## 7장 - 기본 입출력
 
 자바에서는 대표적으로 Scanner() 함수를 이용하여 사용자와 상호작용 할 수 있다. 일반적으로 Scanner sc = new Scanner(System.in);으로 클래스 객체를 생성한 뒤에 sc.nextInt();와 
 같은 방법으로 int형을 입력 받을 수 있다
 
 ``` java
 import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		
		Scanner sc = new scanner(System.in); //Scanner  클래스 인스턴스인 sc를 만들고 new scanner을 사용해 초기화 시킴 
 		// Scanner은 자바에서 제공하는 기본 라이브러리 중 하나 어떤 입출력을 가능하게 해주는 라이브러리, 기본 라이브러리를 가져오려면 import 사용해야 함
		// Scanner도 하나의 클래스 처럼 작성이 되어있고 당연히 내부적으로 어떤 함수를 가질 수 있다.
		// sc라는 변수를 만들었고 만들어줄 때 이렇게 초기화를 해주었는데, System.in 이라는 것은 일반적으로 사용하는 콘솔창에서 입력하는 어떠한 데이터 
		System.out.println("정수를 입력하세요: ");
		int i = sc.nextInt(); //즉 sc라는 입출력함수가 바로 콘솔창에 입력되는 다음 정수를 입력받아서 아예 넣어준다. 사용자가 입력한 값을 I에다넣음
		System.out.println("입력된 정수는 " + i + " : ");
	}

}
```

``` java


import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		
		File file = new File("input.txt");
		try {
			Scanner sc = new Scanner(file); //Try는 이부분을 실행하겠다
			while(sc.hasNextInt()) //sc가 현재 읽어오는 파일 에서 다음으로 읽을 정수가 있는지 물어보는 거 
			{
				System.out.println(sc.nextInt()* 100);
			}
			sc.close();
		} catch (FileNotFoundException e) { //FileNotFoundExceptiond이라는 오류가 발생했을 경우 아래 로 넘어갈 수 있는 예외처리 구문

			System.out.println("파일을 읽어오는 도중에 오류가 발생하였습니다.");//e.printStackTrace(); 원래는 얘가 기본
		}
	}

}
```
 - 8장 과제(1)

```java


public class Main {

	public static void main(String[] args) {
		System.out.println("최하람");

	}

}
```

 - 8장 과제(3)

```java
public class Main {

	public static void main(String[] args) {
		for(int i = 0; i<20; i++) {
			for(int j = 0; j<10; j++) {
				System.out.print("*");
			}
			System.out.println("");
		}
	}

}
```
 ## 9장 - 사용자 정의 함수(1)
 - 3개의 수 최대공약수를 찾는 프로그램
```java

public class Main {
	//반환형, 함수명, 매개변
	public static int function(int a, int b, int c) {
		int min;
		if(a>b)
		{
			if(b>c)
			{
				min = c;
			}
			else
			{
				min = b;
			}
		}
		else
		{
			if(a>c)
			{
				min = c;
			}
			else
			{
				min = a;
			}
		}
		for(int i = min; i>0; i--)
		{
			if(a % i ==0  && b % i == 0 && c % i == 0)
			{
				return i;
			}
		}
		return -1;
	}
	
	public static void main(String[] args) {
		System.out.println("400, 300, 200의 최대 공약수는 : "+ function(400,300,200));

	}

}
```
 
 ## 10장 - 사용자 정의 함수(2)
  - 약수 중 k번째로 작은 수를 찾는 프로그램
 ```java
 
public class Main {
	public static int function(int number, int k) {
		for(int i = 1; i <= number; i++)
		{
			if(number % i == 0)
			{
				k--;
				if(k==0)
				{
					return i;
				}
			}
		}
		return -1;
	}
	//main method가 종료되면 프로그램이 종료된 것과 마찬가지 이기 때문에 반환형이 없다는 뜻에 void사용.
	public static void main(String[] args) {
			int result = function(3050,10);
			if(result == -1)
			{
				System.out.println("3050의 10번째 약수는 없습니다.");
			}
			else
			{
				System.out.println("3050의 10번째 약수는 " + result + "입니다");
			}
	}

}
```
 
 - 문자열 마지막 단어 반환하는 함수

```java

public class Main {
	public static char function(String input) {//어떠한 문자열을 입력 받아 그 문자를 처리해서 딘어를 하나 반환할 수 있도록 해주는 것
		return input.charAt(input.length() - 1); //charAt은 0부터 시작, length는 글자 수 세는 것
		
	}
	
	public static void main(String[] args) {
		System.out.println("Hello workld의 마지막 단어는 " + function("Hello world"));
	}
			
```

- max() 함수를 이용하여 최대값을 저장하는 프로그램

```java

public class Main {
	
	public static int max(int a, int b) {
		return (a>b) ? a : b;
	}
	
	public static int function(int a, int b, int c) {
		int result = max(a, b);
		result = max(result, c);
		return result;
	}
	
	public static void main(String[] args) {
		
		System.out.println("(345,567,789)중에서 가장 큰 값은 " +function(345, 567, 789));
	}
}
```
## 11장

 - 반복함수를 이용해 팩토리얼 구하기
```java

public class Main {
	
	public static int factorial(int number) {
		int sum = 1;
		for(int i = 2; i <= number; i++)
		{
			sum  = sum * i;
		}
		return sum;
	}
	
	public static void main(String[] args) {
		System.out.print(factorial(10));

	}

}
```

 - 재귀함수를 이용해 팩토리얼 구하기

```java
public class Main {
	
	public static int factorial(int number) {
		if(number ==1)
		{ 
			return 1;
		}
		else
		{
		return number * factorial( number - 1);
		}
	}
	
	public static void main(String[] args) {
		System.out.println(factorial(10));

	}

}
```
## 12장

 - 반복함수를 이용해 피보나치 수열 구하기
```java
public class Main {
	
	public static int fibonacci(int number) {
		int one = 1;
		int two = 1;
		int result = -1;
		if(number == 1) {
			return one;
		}
		else if(number == 2)
		{
			return two;
		}
		else
		{
			for(int i = 2; i<number; i++)
			{
				result = one + two;
				one = two;
				two = result;
				
			}
		}
		return result;
	}
	
	public static void main(String[] args) {	 
		System.out.println("피보나치 수열의 5번째 원소는" + fibonacci(10));
	}
	
}
```

 - 재귀함수를 이용해 피보나치 수열 구하기
 
```java
public class Main {
	
	public static int fibonacci(int number) {
		if(number == 1)
		{
			return 1;
		}
		else if(number == 2)
		{
			return 1;
		}
		else
		{
			return fibonacci(number - 1) +  fibonacci(number - 2);
		}
	}
	
	public static void main(String[] args) {	 
		System.out.println("피보나치 수열의 5번째 원소는" + fibonacci(5));
	}
	
}
```

재귀함수 사용하는 것이 반복함수를 사용하는 것보다 코드가 간단할 수는 있지만 시간이 오래 걸리는 경우도 있으니 잘 사용하기


## 13장

- 배열 : 데이터가 많을 때 그 많은 데이터를 효과적으로 처리하고 저장할 수 있도록 하는 자료 형태
 
- 'array'라는 이름의 배열 만드는 법
int[] arryay = new int[100];
new는 어떠한 변수 또는 인스턴스 만들 때 사용하는 약속된 하나의 언어, 위애 코드가 배열을 만들기 위한 하나의 문법이라고 생각하면 된다.


 - 원하는 개수만큼의 배열 생성 및 최대값을 구하는 프로그램을 작성합니다.


```java
import java.util.Scanner;

public class Main {
	
	public static int max(int a, int b) {
		return (a > b) ? a : b;
	}
	public static void main(String[] args) {
		
		Scanner scanner = new Scanner(System.in);
		System.out.print("생성할 배열의 크기를입력하세요 : ");
		int number = scanner.nextInt();
		int[] array = new int[number];
		for(int i = 0; i < number; i++)
		{
			System.out.print("배열의 입력할 정수를 하나씩 입력하세요(양수) : ");
			array[i] = scanner.nextInt();
		}
		int result = -1;
		for(int i = 0; i < number; i++)
		{
			result = max(result, array[i]);
		}
		System.out.println("입력한 모든 정수 중에서 가장 큰 값은 " + result +" 입니다");
	}

}
```
 - 100개의 랜덤 정수의 평균을 구하는 프로그램

```java
import java.util.Scanner;

public class Main {
	
	public static void main(String[] args) {
	
	int[] array = new int[100];
	for(int i = 0; i < 100; i++) {
		array[i] = (int) (Math.random() * 100 + 1);
	}
	int sum = 0;
	for(int i = 0; i < 100; i++) {
		sum += array[i];
	}
	System.out.println("100개의 랜덤 정수의 평균 값은" + sum/100 + " 입니다");	
	}
}
```
## 14장

 - 2차원 배열 안에 랜덤으로 값 넣기
```java

public class Main {

	public static void main(String[] args) {
		 
		int N = 50;
		int [][] array = new int [N][N];
		for(int i = 0; i < N; i++) 
		{
			for(int j = 0; j < N; j++) 
			{
				array [i][j] = (int)(Math.random() * 10);
			}
		}
		for(int i = 0; i < N; i++)
		{
			for(int j = 0; j < N; j++)
			{
				System.out.print(array[i][j]+" ");
			}
			System.out.println(" ");
		}
	}

}
```
## 15장
		
## 16장

## 17장

## 18장

## 19장

## 20
