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

코딜리티 BinaryGap 문제
# Listen 1 - Iterations
``
A binary gap within a positive integer N is any maximal sequence of consecutive zeros that is surrounded by ones at both ends in the binary representation of N.

For example, number 9 has binary representation 1001 and contains a binary gap of length 2. The number 529 has binary representation 1000010001 and contains two binary gaps: one of length 4 and one of length 3. The number 20 has binary representation 10100 and contains one binary gap of length 1. The number 15 has binary representation 1111 and has no binary gaps. The number 32 has binary representation 100000 and has no binary gaps.

Write a function:

fun solution(N: Int): Int

that, given a positive integer N, returns the length of its longest binary gap. The function should return 0 if N doesn't contain a binary gap.

For example, given N = 1041 the function should return 5, because N has binary representation 10000010001 and so its longest binary gap is of length 5. Given N = 32 the function should return 0, because N has binary representation '100000' and thus no binary gaps.

Write an efficient algorithm for the following assumptions:

N is an integer within the range [1..2,147,483,647].
Copyright 2009–2019 by Codility Limited. All Rights Reserved. Unauthorized copying, publication or disclosure prohibited.
``

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
```kotlin
fun solution3(N: Int): Int {
    return Integer.toBinaryString(N).run {
        trim('0')
            .trim('1')
            .split('1').maxBy { it.length }?.length
    } ?: 0
}
```