---
layout: post
title: "[Codility] BinaryGap"
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
tags: ["kotlin", "codility"]
keywords: kotlin, codility
ref:
lang: kr
---


### solution 1
2진법 계산을 하면서 마지막 1 위치에서 현재의 1 위치를 뺀 값이 이전 GAP 사이즈보다 크면 치환한다.
처음 생각해낸 방법. 가장 쉽게 떠오르는 방법이 아닐까 싶다.
```kotlin
fun solution(N: Int): Int {
    var gap = 0
    var lastPos = -1
    var ret = N

    var index = 0
    while (ret > 0) {
        (ret % 2).apply {
            if (this == 1) {
                println("${lastPos > -1}")

                if (lastPos != -1) {
                    (index - lastPos - 1).apply {
                        if (gap < this) {
                            gap = this
                        }
                    }
                }
                lastPos = index
            }
        }
        index++
        ret /= 2

    }
    return gap
}
```

### solution2
자바의 binaryString을 이용하여 계산
2진법 구하는 방식을 바꾼 것 뿐이지 solution1과 별 차이가 없다
```kotlin
fun solution2(N: Int): Int {
    var gap = 0
    var lastPos = 0
    Integer.toBinaryString(N).apply {
        println(this)
        forEachIndexed { index, char ->
            if (char == '1') {
                (index - lastPos - 1).apply {
                    if (gap < this) {
                        gap = this
                    }
                }
                lastPos = index
            }
        }
        return gap
    }
}
```

### solution3
binaryString을 통해서 구한 string을 trim을 이용하여 구한 방법이다.
문제를 푼 후 검색해보니 이런 방법이 있었다!!!
1. 먼저 양 옆의 0들을 제거 (1과 1사이의 갭을 찾는 것이기 때문)
2. 끝에 남은 양 옆의 1을 제거
3. 1로 split 하여 배열을 구하고 그 중에서 최고 값을 구한다
fun solution3(N: Int): Int {
    return Integer.toBinaryString(N).run {
        trim('0')
            .trim('1')
            .split('1').maxBy { it.length }?.length
    } ?: 0
}