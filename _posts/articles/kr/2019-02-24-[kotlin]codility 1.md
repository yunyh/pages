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


~~ solution 1
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
~~

~~ solution2
```Kotlin
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
~~