---
layout: post
title:  "[자료구조]수학적 귀납법"
date:   2020-04-04
tags: [algorithm, c++, baekjoon, greedy]
category: [Algorithm]
---

<p class="intro"><span class="dropcap">수</span>학적 귀납법에 대해서 알아보고 재귀 함수를 수학적 귀납법으로 정확성 증명하는 부분에 대해 알아보겠습니다. 또한 binary search를 예시로 시간 복잡도까지 계산해보겠습니다.</p>

1. 수학적 귀납법
 - 수학적 귀납법의 기본형 : 
	P(1)이 참이고, P(n-1) -> P(n)이 참이면 P(n)은 모든 자연수 n에 대해서 참이다.
 - 수학적 귀납법의 강한 형태 : 
	P(1)이 참이고, P(1) ^ P(2) ^ .... ^ P(n-1) -> P(n)이 참이면 P(n)은 모든 자연수 n에 대해서 참이다.

2. 재귀 함수의 정확성 증명_수학적 귀납법을 이용해서 

{% highlight ruby %}
int sum(int x) {
 if(x<=0) return 0;
 return x + sum(x-1);
}
{% endhighlight %}


[정확성 증명]
 - 재귀 함수 코드를 따라 들어가면서 확인하는 방법은 재귀함수 코드가 복잡해지면 불가능에 가깝다.
 - 따라서, 수학적 귀납법을 이용해 정확성 증명을 해야한다.

 - 수학적 귀납법 : sum(x)는 1부터 x까지 숫자의 합을 리턴한다.

(Base) P(1)이 참이다 : "sum(1)이 리턴하는 값은 1이다"를 증명하면 됨.
	실제 코드에 1을 대입하면 1을 리턴함을 알 수 있음
(Step) P(x-1) -> P(x)이 참이다 : "sum(x-1)이 1+2+...+(x-1)을 리턴하면 sum(x)는 1+2+3+...+x 를 리턴한다"를 증명하면 됨.
	코드에서 sum(x)는 x+sum(x-1)의 값을 리턴함. sum(x-1)의 리턴 값은 1+2+...+(x-1)과 같다고 가정했으므로
	sum(x)는 1+2+...+(x-1)+x = 1+2+...+x를 리턴함을 확인할 수 있음


3. Array (배열)
 - 정의 : 연속된 주소, 동일한 Type
 - 장점 : n개 중 k번째 element access가 상수 시간에 가능. Search가 빠름
 - 단점 : 크기 변화 비용이 크다. Insert, Delete가 느릴 수 있다.
 - 사용 : 변화가 없거나 드문 자료


4. Binary Search
[코드]_배열 a는 정렬되어 있다고 가정
{% highlight ruby %}
int search(int a[ ], int n, int x) {
 int l, r, m;
 l = 0; r = n-1;		// l: 검색 범위의 왼쪽 끝, r: 검색 범위의 오른쪽 끝

 while(l <= r ){
	m = (l+r)/2;
	if(a[m] == x) return m;	//x를 찾으면 배열의 index 리턴
	else if(a[m] > x) r = m-1;	
	else l = m+1;
 }
 return -1;
}
}
{% endhighlight %}

 - x가 배열 a[ ]에 있다면, a[l] ~ a[r](검색 범위) 사이에 있다.

Proof by Invariant
 - Invariant : 만약 어떤 i에 대해서 a[i] = x라면 l <= i <= r이 항상 성립한다.
	(invariant는 최초에 성립하고, invariant가 깨질 수 있는 코드가 전혀 없다.)
 - a[i] = x인 i가 없다면 루프는 반드시 끝나고 -1이 리턴 됨
 - a[i] = x인 i가 있다면 루프 안에서 반드시 리턴 됨


5. Recursive Binary Search
[코드]_배열 a는 정렬되어 있다고 가정
{% highlight ruby %}
int search(int a[ ], int n, int x) {
 int m;
 if(n == 0) return -1;
 m = n/2;
 if (a[m] == x) return m;
 else if(a[m] > x) return search(a, m-1, x);
 else {
	r = search(a+m+1, n-m-1, x);
	if (r == -1) return -1;
	else return r + m + 1;
 }
}
{% endhighlight %}

Proof by Induction
 - 주장 : 만약 어떤 i에 대해서 a[i] = x라면 위 함수는 i를 리턴한다.
 - (Base) n = 0인 경우 "어떤 i에 대해서 a[i] = x"가 성립할 방법이 없고, 함수는 항상 -1을 리턴한다.
 - (Step)
	(case 1) a[m] = x인 경우 m을 리턴하므로 주정이 성립
	(case 2) a[m] > x인 경우 a[m], a[m+1], ... ,a[m-1] 중에서는 x와 같은 값이 없다.
	따라서 a[i] = x 인 경우가 있다면 i는 0,1,...,m-1 중 하나이다.
	귀납적으로 search(a, m-1, x)가 정확하다고 가정하면, 
	즉, 제일 위 주장이 search(a, m-1, x)에서 성립한다고 가정하면 제일 위 주장이 성립함.
	(case 3) case2와 유사함
 - 시간 복잡도 : T(n) = 1 + T(n/2) = 1 + 1 + T(n/4) = ... = log n
		T(n) = O(log n)


6. log n 은 무엇있가?
 - k = log n <==> 2^k = n
 - 따라서, log n은
   - 2를 몇 번 곱하면 n이 되느냐의 질문 대한 답
   - n을 2로 몇 번 나누면 1이 되느냐의 질문에 대한 답
 - log n은 n보다 월등히 작다.
   - log n =10, n = 1,024
   - log n = 30, n = 1,073,741,824
 