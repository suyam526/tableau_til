# Fifth Study Week

- 39강: [LOD](#39강-lod)

- 40강: [EXCLUDE](#40-lod-exclude)

- 41강: [INCLUDE](#41-lod-include)

- 42강 : [매개변수](#42-매개변수)

* (43강이 없어 패스합니다)
- 44강: [매개변수 실습](#44-매개변수-실습)

- 45강: [마크카드](#45-워크시트-마크카드)

- 46강: [서식계층](#46-서식-계층)

- 47강: [워크시트](#47-워크시트-서식)

- [문제1](#문제-1)

- [문제2](#문제-2)

- [문제3](#문제-3)

## Study Schedule

| 강의 범위     | 강의 이수 여부 | 링크                                                                                                        |
|--------------|---------|-----------------------------------------------------------------------------------------------------------|
| 1~9강        |  ✅      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=84)       |
| 10~19강      | ✅      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=75)       |
| 20~29강      | ✅      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=65)       |
| 30~38강      | ✅      | [링크](https://www.youtube.com/watch?v=e6J0Ljd6h44&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=55)       |
| 39~47강      | ✅      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=45)       |
| 50~59강      | 🍽️      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=35)       |
| 60~69강      | 🍽️      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=25)       |
| 70~79강      | 🍽️      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=15)       |
| 80~89강      | 🍽️      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=5)        |


<!-- 여기까진 그대로 둬 주세요-->

> **🧞‍♀️ 오늘의 스터디는 지니와 함께합니다.**


## 39강. LOD

<!-- INCLUDE, EXCLUDE, FIXED 등 본 강의에서 알게 된 LOD 표현식에 대해 알게 된 점을 적어주세요. -->

```
- LOD = "Level of Detail"의 줄임말로,뷰에 세부 수준을 나타냄
- 현재 뷰에는 영향 받지 않고 계산할 수준을 세부적으로 제어 가능!

- LOD 표현식에서 차원을 입력하지 않으면 전체 데이터 기준에 따라 계산함
```

## 40. LOD EXCLUDE

<!-- INCLUDE, EXCLUDE, FIXED 등 본 강의에서 알게 된 LOD 표현식에 대해 알게 된 점을 적고, 아래 두 질문에 답해보세요 :) -->


> **🧞‍♀️ FIXED와 EXCLUDE을 사용하는 경우의 차이가 무엇인가요?**

```
- 세부 수준이 더 낮은 차원 선택 시
FIXED : 영향 X
EXCLUDE : 값이 변경됨. 계산식에 설정된대로 특정 차원을 제외하고 계산해서 표시하긴 하지만 현재 뷰에 있는 세부 수준이 더 낮은 차원을 기준으로 관련 계산을 표시함

- 필터
FIXED : 필터 영향 X
EXCLUDE : 필터 영향 O
```

> **🧞‍♀️ 왜 ATTR 함수를 사용하나요?**

```
특정 필드의 값이 단일값인지 확인하기 위해서 사용함. 
만약 해당 필드가 여러 개의 값을 가지면 *를 반환하고, 단일값인 경우 그 값을 반환해 데이터 안전하게 처리 가능.
```


## 41. LOD INCLUDE

<!-- INCLUDE, EXCLUDE, FIXED 등 본 강의에서 알게 된 LOD 표현식에 대해 알게 된 점을 적고, 아래 두 질문에 답해보세요 :) -->


> **🧞‍♀️ 그렇다면 어떤 경우에 각 표현식을 사용하나요? 예시와 함께 적어보아요**


```
INCLUDE : 현재 뷰에서 특정 차원을 추가하여 계산
    - 차원 필터를 통해 해당 값 변경 가능 


EXCLUDE : 현재 뷰에서 특정 차원을 제외하여 계산할 때 사용
    

FIXED : 현재 뷰의 차원과 상관없이 계산된 필드에서 원하는 차원에 따라 계산
    - 사용하는 경우
    1. FIXED에서 설정한 차원이 뷰에 포함되어 있을 때
    2. FIXED에서 설정한 차원이 뷰에 포함되어 있지 않을 때


표현식 3개 중 어떤 것을 사용해야 할까?
    * 뷰에 표시되는 값이 차원이면, FIXED만 사용 가능
      측정값만 반환되는 다른 2개와 달리 차원&측정값을 반환할 수 있기 때문 
    * 반환 값을 차원 필터의 영향을 받을 경우 INCLUDE  또는 EXCLUDE
```


## 42. 매개변수

<!-- 매개변수에 대해 알게 된 점을 적어주세요 -->
```
매개 변수 : 고정된 상수값 x, 동적인 값으로 변경하기 위해 활용하는 기능
반드시 *계산식 or 필터 or 참조선*과 함께 사용됨


- 만드는 방법
1. 필터창에서 '새 매개 변수 만들기' 선택
2. 원하는 필드 위에 마우스 우클릭 -> '만들기' -> '매개 변수' 선택 
3. 데이터 패널에 역삼각형 버튼 -> '매개 변수 만들기' 선택


* 매개변수 만든 후에 필터에서 카운트를 생성한 매개변수로 선택해두면 그 후로는 필터창에 들어가서 일일이 고치지 않아도 뷰에서 매개변수로 바로바로 원하는 값 표시하기 가능!
```


> **🧞‍♀️ 집합에도 매개변수를 적용할 수 있나요? 시도해봅시다**
```
집합 만들고 상위 탭에서 매개변수 선택 -> 집합 필드를 마크 카드 색상 위에 드래그 -> 집합에도 매개변수 적용 완료! 
```




## 44. 매개변수 실습
(43번 강의가 없어 패스합니다)

<!-- 매개변수에 대해 알게 된 점을 적어주세요 -->

```
분석 패널에 '참조선'을 뷰로 드래그하면 참조선 편집 화면이 나타남 


```


## 45. 워크시트 마크카드

<!-- 마크카드에 대해 알게 된 점을 적어주세요 -->
```
마크 : 워크 시트에서 차트를 만들면 해당 시트 안에 있는 데이터들

- 마크 서식을 변경하기 위해선 '마크 카드' 사용해야
- 행, 열 선반에 필드 드랍하면 자동으로 막대로 마크를 표시
- 마크창 드롭다운으로 마크 유형만 변경 가능 (차트 유형은 변경 X)

- 후광
    - [마크창] '마크' 선택 -> '후광'에서 색상 변경시 마크들에 특정 색으로 후광이 씌워짐

- 범례
    - [필드] 필드를 마크 색상에 드래그 시, 연속형 필드일 때는 색상 범위 범례, 불연속형 필드일 때는 항목별 범례

- 레이블
    - [마크창] '레이블'에서 수정 가능
        (근데 PUBLIC에서는 가능한 기능이 적은듯)

- [마크창] 세부 정보
    - 연속형 필드를 세부 정보에 드래그하면 차트 모양은 변화없지만 마우스 오버하면 도구 설명에 연속형 필드 정보 포함됨

- [마크창] 도구 정보
    - 도구 정보에 뜨는 텍스트들을 마음대로 변경 가능 (굵게, 텍스트 색 변경 등)

- [마크창] 경로 -> 차트 유형에 따라
    - 라인 차트일 경우 6번째 자리에 새롭게 나타나는 옵션
```


## 46. 서식 계층

<!-- 서식계층에 대해 알게 된 점을 적어주세요 -->
```
글꼴 변경 : '서식' 탭 -> '통합 문서' 선택
```

> **🧞‍♀️ 서식계층을 일반적인 것에서 구체적인 것 순서로 기입해보세요**


```
워크 시트 서식 
행/열 서식
특정 필드
필드 레이블
도구설명/제목/마크


*해당 서식 계층에서 상위 계층에 서식을 설정했을 때 상위 계층보다 아래 계층인 경우에 서식을 변경하게 되면 해당 아래 계층에 설정한 서식이 적용됨
```


## 47. 워크시트 서식

<!-- 워크시트 서식에 대해 알게 된 점을 적어주세요!-->
```
- 서식 탭의 '글꼴' 옵션
    : 워크 시트 내 텍스트들에 글꼴, 색상, 크기 변경 
    : '맞춤' 옵션으로 텍스트 정렬/방향 변경 


- '음영' 옵션
    : 워크 시트 내 표시된 데이터 셀에 음영을 적용 
    : '행/열 색상 교차' 옵션 이용해서 데이터 셀의 구간을 설정해 음영을 줄 수 있음
    : '행 색상 교차'의 '구간 크기'는 각 눈금이 하나의 데이터인 데이터 셀을 의미
```


## 문제 리스트



## 문제 1.

```
가장 많이 주문한 사람들은 물건 배송을 빨리 받았을까요?
조건을 준수하여 아래 이미지를 만들어봆시다.
1) 국가/지역별(이하 '나라'로 통칭), 범주별로 배송일자가 다를 수 있으니 먼저, 나라별/범주별로 평균 배송일자를 설정한 뒤,
2) 각 나라에서 가장 많이 주문한 사람의 이름을 첫 번째 열,
3) 그 사람이 주문한 제품 이름을 2번째 열,
4) 각 상품이 배송까지 걸린 날 수를 표현하고
5) 그리고 만약 배송이 각 나라/범주별 평균보다 빨랐다면 '빠름', 같다면 '평균', 느리다면 '느림' 으로 print 해주세요. 
```

![이미지주소](https://github.com/yousrchive/BUSINESS-INTELLIGENCE-TABLEAU/blob/main/study/img/2nd%20study/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202024-08-13%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.12.36.png?raw=true)

<!-- 여기까지 오는 과정 중 알게 된 점을 기입하고, 결과는 시트 명을 본인 이름으로 바꾸어 표시해주세요.-->

1. DATEDIFF 함수를 사용하여 '배송까지 걸린 일수' 계산된 필드 만들기 <br/>
![TAB1](./image/week5/Tableau1.png) <br/>

2. FIXED LOD 표현식을 사용하여 '나라별/범주별 평균 배송 일자' 계산된 필드 만들기 <br/>
![TAB2](./image/week5/Tableau2.png) <br/>

3. 앞서 만든 두 필드를 비교하여 '배송 속도 수준' 만들기 <br/>
![TAB3](./image/week5/Tableau3.png) <br/>

4. 행 선반에 '고객 이름', '제품 이름', '배송 속도 수준' 드래그 <br/>
마크창 색상에 '배송 속도 수준' <br/>
마크창 텍스트에 '배송까지 걸린 일수' <br/>
![TAB4](./image/week5/Tableau4.png) <br/>

## 문제 2.

```
채원이는 태블로를 쓰실 수 없는 상사분께 보고하기 위한 대시보드를 만들고 싶어요. 

제품 중분류별로 구분하되 매개변수로써 수익, 매출, 수량을 입력하면 저절로 각각 지표에 해당하는 그래프로 바뀌도록 설계하고자 해요.

 어떤 값이 각 지표의 평균보다 낮은 값을 갖고 있다면 색깔을 주황색으로, 그것보다 높다면 파란색으로 표시하고 싶어요. 그 평균값은 각 지표별로 달라야 해요.
```

1. 매개 변수 만들기 <br/>
![TAB5](./image/week5/Tableau5.png) <br/>

2. 제품 중분류별 값을 나타내는 계산된 필드 만들기 <br/>
![TAB6](./image/week5/Tableau6.png) <br/>

3. 평균값을 나타내는 계산된 필드 만들기 <br/>
![TAB7](./image/week5/Tableau7.png) <br/>

4. 앞서 만든 두 필드를 비교하는 계산된 필드 만들기 <br/>
![TAB8](./image/week5/Tableau8.png) <br/>

5. 열 선반에 '수익/매출/수량' 필드 드래그 <br/>
행 선반에 '하위 범주' <br/>
마크창 색상에 '비교'
![TAB9](./image/week5/Tableau9.png) <br/>