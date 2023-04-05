---
layout: single
title: "[프로그래머스] 스택/큐 주식가격, Go/Java"
date: "2023-04-05 00:01:00 +0900"
last_modified_at: "2023-04-05 00:01:00 +0900"
categories:
  - algorithm-programmers
tags:
  - 알고리즘
# toc_label: "목차"
# toc: true
# toc_sticky: true
---

<br/>

## 0. 들어가면서

> 스택/큐의 주식가격 문제이다.

## 1. 문제풀이

### 1.1 Java

```java
class Solution {
    public int[] solution(int[] prices) {
        int[] answer = new int[prices.length];

        for(int i =0; i<prices.length; i++){
            int temp = prices[i];
            int count = 0;
            for(int j = i+1; j<prices.length; j++){
                count+=1;
                if(prices[i]>prices[j]){
                    break;
                }

            }
            answer[i]=count;
        }
        System.out.println(answer[0]);
        return answer;
    }
}

```

### 1.2 Go

## CLOSING

> 나쁘지 않았다.
