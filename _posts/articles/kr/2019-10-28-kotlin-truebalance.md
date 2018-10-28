---
layout: post
title: "트루밸런스 코틀린 도입기 첫번째"
tagline: ""
image: /assets/patterns/paisley.png
header:
  image: /assets/patterns/asanoha-400px.png
repository:
  is_project_page: true
  show_downloads: true
  repository_url: https://github.com/lorepirri/jekyll-social-metatags
  zip_url: https://github.com/lorepirri/jekyll-social-metatags/archive/master.zip
  tar_url: https://github.com/lorepirri/jekyll-social-metatags/tarball/master
tags: ["kotlin", "truebalance", "Android"]
keywords: kotlin, truebalance, Android 
ref: example-project-page
lang: kr
---

Kotlin은 안드로이드 공식 개발 언어로 최근에 많은 관심을 받고 있는 언어이다. 코드가 간결해지고 특히 NullPointException에서 자유로워지는 이점이 가장 크게 매력으로 느껴지는 언어이다. NPE에서 자유로워진다는 얘기는 안드로이드 어플리케이션이 Null로 인해 사망하는 경우가 많이 줄어든다는 얘기이기도 하다. 또 개발자가 null에 대한 스트레스를 덜 받을 수 있다는 뜻이기도 하다.

2017년 초부터 관심이 있었던 코틀린을 최근에 서비스 개발에 도입하기 시작하였다. Kotlin이 스칼라 같은 요즘 유행하는 언어를 많이 따라가 있었고, 무엇보다 러닝커브가 너무 컸기에 섣불리 도입하기가 어려웠다. 또 회사 안드로이드 개발팀의 코틀린 언어 숙련도도 문제였다. 볼 줄 아는 사람이 1명이었으니...

그런데도 도입한 이유는 누군가는 스타트를 끊어야 한다는 생각이었다. 환경도 나쁘지 않았다. 팀 규모가 크지도 않았고 무엇보다 코틀린에 대한 관심이 컸다. 문제는 할 시간, 할 의지가 나지 않았던 것 뿐. 그래서 스타트를 끊었다. 그동안 혼자 삽질을 많이 해봤으니 괜찮겠지 싶었다.

오만한 생각이었다. 오늘 부로 코틀린을 커밋한 지 3주째인데 잘못쓰는 부분이 많다. 언어에 대한 이해도 많이 부족했다. 익스텐션, 람다, 고차함수, 콜랙션, 표현식, 흉내는 낼 수 있지만 의미를 제대로 알고 쓰고 있는 지는 확답할 수 없었다. 팀원들에게 첫 리뷰 할 때, 그리고 개발하면서 물어볼 때, 어딘가 조금 부족한 설명을 하는 자신을 발견하고 말았다.

첫 포스팅부터 회고록에 가깝게 써버렸지만... 앞으로는 서비스에 어떻게 코틀린을 도입했는 지 차근차근 적어볼 생각이다. 