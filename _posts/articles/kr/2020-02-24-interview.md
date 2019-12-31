---
layout: post
title: "2020 면접"
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
tags: ["interview"]
keywords: interview
ref:
lang: kr
---

# 안드로이드 4대 컴포넌트
4대 컴포넌트는 Intent를 통해 데이터를 주고 받는다.

1. Activity
  어플리케이션과 유저가 상호작용 하는 곳. 쉽게 말하자면 View.
  어플리케이션은 최소 1개의 Activity를 가지고 있다.
  Activity는 다른 Activity를 호출 할 수 있다.


2. BroadcastReceiver
	안드로이드의 다양한 이벤트를 수신하는 컴포넌트.
	디바이스에서 발생하는 여러 이벤트를 수신하는 데 사용한다. (베터리 상태, 화면 상태 등등 여러가지)


3. Service 
  사용자에게는 보여지지 않고 작업을 처리하는 컴포넌트. 포그라운드/백그라운드에서 수행됨.
  바인드를 통해 프로세스간 통신 (IPC)를 수행할 수 있음.
  Android OS 8 이후로는 백그라운드 사용이 매우 제한이 되면서 사용하는데 제약이 많이 생김.
  최근에는 WorkManager가 백그라운드 작업을 대체함


4. ContentProvider
  어플리케이션에 데이터를 제공 역할을 담당하는 컴포넌트
  어플리케이션의 로컬 DB를 관리하는 역할. 프로세스가 분리되어 있으면 content provider를 통해 하나의 로컬 DB 를 주고 받을 수 있다.
  ContentProvider를 통해 디바이스의 주소록 등 접근이 가능하고, 다른 앱에도 데이터를 제공할 수 있다.
  데이터 접근에 대한 권한 관리도 한다.


# Activity LifeCycle
<img src="https://developer.android.com/guide/components/images/activity_lifecycle.png?hl=ko" width="40%" height="40%" title="안드로이드 라이프사이클">
[androidLifeCycle]: https://developer.android.com/guide/components/activities/activity-lifecycle?hl=ko "Activity LifeCycle"