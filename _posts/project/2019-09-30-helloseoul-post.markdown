---
layout: post
title:  "Hello Seoul, 설로"
tags: [project, android, app, kotlin]
category: [Project]
date:   2019-09-30
image: "helloseoul.png"
description: "[Android][kotlin]프로젝트: 설로 포스팅입니다."
---

<p class="intro"><strong>새로운 서울을 만나다.<br>우리는 서울로 갑니다, 설로</strong><br>[Android][Kotlin][어플]</p>


  <!-- Swiper -->
  <div class="swiper-container">
    <div class="swiper-wrapper">
      <div class="swiper-slide"><img src="{{ '/assets/img/helloseoul.png' | prepend: site.baseurl }}" alt=""></div>
      <div class="swiper-slide"><img src="{{ '/assets/img/helloseoul2.png' | prepend: site.baseurl }}" alt=""></div>
      <div class="swiper-slide"><img src="{{ '/assets/img/helloseoul3.png' | prepend: site.baseurl }}" alt=""></div>
      <div class="swiper-slide"><img src="{{ '/assets/img/helloseoul4.png' | prepend: site.baseurl }}" alt=""></div>
      <div class="swiper-slide"><img src="{{ '/assets/img/helloseoul5.png' | prepend: site.baseurl }}" alt=""></div>
    </div>
    <!-- Add Pagination -->
    <div class="swiper-pagination"></div>
    <!-- Add Arrows -->
    <div class="swiper-button-next"></div>
    <div class="swiper-button-prev"></div>
  </div>

  <!-- Initialize Swiper -->
  <script>
    var swiper = new Swiper('.swiper-container', {
      pagination: {
        el: '.swiper-pagination',
        dynamicBullets: true,
      }, navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      },
    });
  </script>


<strong>[제작 기간]</strong> 2019년 8월 01일 ~ 9월 30일<br>
<strong>[제작 플랫폼]</strong> Android Studio, Kotlin<br>
<strong>[제작자]</strong> 김성윤, 오형석, 권순재<br>
<strong>[API]</strong> 서울 Tour API, Google Map, 기상청 날씨 API<br>
<strong>[제작 목적]</strong> 2019년 서울시 앱 공모전 출품<br>

<p><strong>동기</strong></p><br>
같은 학과 친구들 2명과 함께 여름방학을 불태울 앱 공모전을 알아보다가 “서울시 앱 공모전”을 알게 되었고 공모전 출품을 목표로 어플을 제작하기 시작했습니다. 

<strong>[주제]</strong><br>
주제의 경우 서울시를 대상으로 해야 했기에 마침 만들고 싶던 여행 어플로 선정했습니다. 제가대학 때문에 서울에 올라와서 정말 재밌었던 부분이 지하철 역 하나 하나가 여행지이고 역사라는 점이 참 좋았습니다. 1학년 때는 거의 매주 지하철역을 기점으로 친구들과 지하철, 버스, 따릉이를 타고 다니면서 좋은 추억도 많이 쌓았죠. 그 추억에서 출발하여 서울의 핫플, 맛집, 숙박을 한번에 검색하고 일정을 짜면서 여행하는 다른 사람들과 자신만의 여행 스토리를 공유할 수 있는, 그런 인스타 감성이 살짝 묻어 있는 어플을 만들어 보기로 했습니다.

<strong>[제작 과정]</strong><br>
우선은 제작기간을 한 달정도로 잡고 어플 제작을 실시하였습니다. 인력이 세명밖에 없어서 업무분담이나 프로젝트 구성을 잘하지는 못했습니다. 처음에는 서버 관리 한 명에 앱 개발자 두 명으로 생각했는데 코틀린 언어나 안드로이드 스튜디오 개발이 익숙지 않아서 중간 중간 프로젝트의 방향을 많이 바꿨습니다. 그러다 보니 업무 분담도 잘 안 지켜지고 제작기간도 두달이나 걸렸습니다. 밤샘 작업도 엄청 했습니다. 또 앱을 제작할 때는 큼직큼직한 기능을 먼저 갖추고 세부적인 내용을 제작했어야 하는데 디테일한 부분을 계속 건들이다 보니 더 늦어진 것 같습니다.

<strong>[핵심 기능]</strong><br>
1.	일정 생성 기능
-	날짜 선택 가능
-	친구 초대 및 공동 일정 생성 가능
2.	여행 스토리 공유
-	사전에 생성한 일정으로 여행이 끝나면 자동으로 리뷰를 작성할 수 있습니다.
-	작성된 리뷰는 인스타 그램처럼 메인 화면에 올라갑니다.
-	해쉬 태그를 작성 할 수 있습니다.
-	다른 사람의 여행 스토리를 보고 그 일정을 그대로 스크랩하여 일정을 재 생성할 수 있습니다.
3.	여행지 검색
-	다른 사용자가 작성한 해쉬 태그로도 여행지 검색이 가능합니다.
-	관광, 문화/쇼핑, 맛집, 숙박의 카테고리별로 검색 가능합니다.
-	지도상의 위치, 주소, 전화번호, 사진을 확인할 수 있습니다.

<strong>[부가 기능]</strong>
1.	좋아요 버튼
2.	날씨 확인

<strong>[결과]</strong><br>
9월 30일 오후 5시까지가 제출 기한이어서 29일은 팀원 모두 학교에서 밤새 만들었습니다. 저는 9월 30일날 퀴즈가 3개나 있었는데 퀴즈 가서 자고 실습실 가서 마무리하면서 거의 48시간을 꽉꽉 채워 만들었습니다. 사실 저희 팀은 결과물을 보고 결과물에 대해 상당히 만족했습니다. 제작기간이 오래 걸리고 힘들었지만 완성도 측면에서 실제 출시 가능할 정도로 디버깅하여 거의 모든 오류를 잡아 냈고, 디자인 적인 부분에서도 순수 제작한 이미지 또는 레이아웃을 쓰면서까지 섬세하게 만들었습니다. PHP를 이용해서 서버 통신에도 문제가 없었습니다.<br>
다만…..<br>
제출 후에 알게 된 사실은 구글 맵 API는 릴리즈 버전의 키와 디버그용 키가 따로 있다는 것이었습니다. ㅠㅠ 결국 제출한 APK파일에서는 구글 맵이 안 열리는 심각한 에러가 있었고, 그것 때문인지 어플의 성격이 공모전과 맞지 않았는지는 모르겠지만 탈락의 고배를 마셨습니다.

<strong>[소감]</strong><br>
혼자 책 보면서 안드로이드 스튜디오를 연습하다가 처음으로 완성도 있는 어플을 만들어 보면서 프로젝트 계획의 중요성, 역할 분담의 중요성을 뼈저리게 느꼈습니다. 학교 수업에서도 많이 들었던 이야기지만 그때는 몰랐는데, 두 달 정도 밤낮 바꿔 가며 고생해보니 알겠더군요…. 그래도 성취감도 충분히 있었고 재미도 있었습니다. 언젠가 다시 한번 수정해서 스토어에도 출시해보고 싶은 어플입니다. 혹시 구경 해보고 싶은 분들은 메일 주시면 apk파일 보내드리겠습니다.


오형석 : 입상하지 못한것이 좀 아쉽지만, 공모전을 준비하면서, 안드로이드에 대한 공부를 많이 하게 된것은 만족스럽다. 프론트부터 백앤드까지 들어간 프로젝트가 이번이 처음이라 서투른 부분이 많았다. github을 이용해서 프로젝트를 진행했는데, 처음에는 사용법이 익숙하지 않아서 실수도 많이 했었지만, 프로젝트가 진행됨에 따라 branch도 나누고 complict도 해결하면서 점점 익숙해지게 되었다. 다음 공모전에는 꼭 입상을 하도록 실력을 키워야겠다는 다짐을 하게 된 계기가 되었다.

{% include youtube.html id="Lfs7DTwRhSM" %}