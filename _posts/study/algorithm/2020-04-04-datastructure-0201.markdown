---
layout: post
title:  "[자료구조] 포인터의 이해"
date:   2020-04-04
tags: [c++,c,datastructure]
category: [Algorithm]
---

<p class="intro"><span class="dropcap">포</span>인터를 사용하는 이유에 대해 알아보고 포인터의 기능과 사용법에 대해 알아보겠습니다.</p>

1. 주소를 사람이 사용해야 하나?
 - 모든 변수를 다 만들수 없고, 메모리를 얼마나 쓸지 알 수 없기 때문에
 - 메모리 '할당'이 필요함
 - c언어에서는 malloc 사용
 - 예시 : outlook

{% highlight ruby %}
int *p;
p = new int;
p = malloc(sizeof int);
{% endhighlight %}

 - p는 800번지 주소라고 가정
 - p에는 800이라는 숫자만 저장되어 있다
 - 현재로서는 800번지에 가면 type이 int인지  char인지 알수 없다.
 - 즉, p변수를 만들때 주소가 가르키는 것이 어떤 type 인지 알려주기 위해 int *p라고 쓴다.
 - int *p : p에 있는 값을 주소로 생각해서 그 주소가 가리키는 곳으로 간다.(그 목적지에는 int형 자료가 있다)

 [정리_포인터]
 - 이름은 없지만 주소만 있는 변수가 있다. 그 주소를 저장하는 변수가 포인터이다.
 - Type이 주소인 변수
 - 즉, 저장하는 값을 주소로 해석하기로 약속한 변수
 - 결과 : 그 주소를 확인해보면 어떤 Type의 변수가 있는지를 추가로 표시해 주어야 한다.

{% highlight ruby %}
int a;
int *p;
int **q;

p = &a;		//p에 a의 주소를 대입 (a의 주소가 800번지라고 가정)
*p = 30;		//p가 가리키는 800번지에 30을 저장 ( a = 30; 과 같다)

//q = & &a;	//오류 코드: a는 변수이기 때문에 주소가 있다. 하지만 주소의 주소는 있을 수 없다
q = &p;		//맞는 코드 : p의 주소를 저장할 수는 있다.
**q = 30;
{% endhighlight %}


 -int **q : q의 내용은 주소이고, 그 주소로 가면 또 주소가 있고 또 그 주소로 가보면 int 자료형이 있다.
 - 즉, (q가 100번지라고 가정) 100번지 가면 *q가 있고, *q를 확인 해보면 거기에도 주소가 있다. ( *q가 200번지라고 가정)
   다시  200번지에 가면 int 자료형이 있다.

{% highlight ruby %}
int a, x;
char b;

int *p, *r;
int **q;

p = &a; *p = 30; q = &p; **q = 30;

x = a + *p;	//맞는 코드 : int형 + int형
//p = p + r;	//오류 코드 : p, r은 주소. 주소 + 주소는 아무 의미가 없다. 즉, 주소간의 더하기는 허용하지 않는다.
p = p - r;	//맞는 코드 : p의 주소와 r의 주소가 얼마나 떨어져 있는지 알 수 있기 때문에 주소간의 빼기는 허용 된다.
p = p + 3;	//맞는 코드 : p의 주소에서 옆으로 3칸 떨어진 곳으로 간다.(int형 3칸 이동 : 3X4byte = 12byte만큼 이동)
{% endhighlight %}
