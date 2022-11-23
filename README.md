# LBA_generate_objectQA


## Overview

This repository contain object related question and answering generation code in DramaQA code based on hand-designed QA-templated




## Question Templates

input: reference episode, scene, shot

output: target episode, scene, shot that matched with refrenced's annotations

1. obj 2개이상, 위치정보
    - What is the name of that object next to (obj)?
    - What is the positional relationship between (obj1) and (obj2)?
    - What (obj1) is next to the (obj2)?
    - behind, next to, positional relationship(on, in, next to, under, irrelevant) -> 좌표정보로 알기 어려움
   
2. obj 1개이상
    - Which {object} is seen the most?
    - How many (obj) are there?
    
3. obj 3개이상, 위치정보
    - What is the (obj1) between (obj2) and (obj3)?
    
    between

4. obj 1개이상, person 2명이상, 위치정보(between)
    - How many (obj) are between {person1} and {person2}
    
    between
    
5. obj1개이상, obj_person 또는 person 1명이상 
    - What is the visual relationship between the {person, obj_person} and the (obj)?
    
    visual relationship(on, in, next to, under, irrelevant)
   
6. obj 1개 이상, person 1명 이상,위치정보
    - What is the (obj) in front of {person}?
    - What is the (obj) next to {person}?
    - How many (obj) are there behind {person}?

7. obj 1개 이상, person 1명 이상, person_realated_object 1개이상
    - What is the (obj) {person} {predicate}?
    


## answer


1. c0_t0 obj1의 next to 관계의 ojbect
2. c0_t1 obj1, obj2의 positional relationship
3. c0_t2 obj1의 next to 관겨의 object
4. c1_t0 obj1의 개수
5. c1_t1 object info에서 가장 많은 수의 object
6. c2_t0 obj2, obj3 중앙좌표 사이에 있는 object
7. c3_t0 obj2, obj3 중앙좌표 사이에 있는 obj1의 개수
8. c4_t0 obj1, person1사이의 positional relationship
9. c5_t0 person_pos1 중앙좌표 앞에 있는 object
10. c5_t1 person_pos1 중앙좌표 옆에 있는 object 
11. c5_t2 person_pos1 중앙좌표 뒤에 있는 obj_pos1의 개수
12. c6_t0 person_pos1의 related object 0



- positional relationship
- 중앙좌표(x,y), 타겟좌표(x_hat, y_hat)
- upper left
    - 레퍼런스기준(중앙좌표 (0,0)) 2사분면
- upper right
    - 레퍼런스기준 4분면, 1 사분면
- lower left
    - 레퍼런스기준 4분면, 3 사분면
- lower right
    - 레퍼런스기준 4분면, 4사분면

- next to
    - 레퍼런스 기준 가장 가까운 물체

- behind
    - 레퍼런스 기준, y_hat < y
- in front of
    - 레퍼린스 기준, y_hat > x



