# FENCE Project 데이터 분석🚧


### 데이터 전처리부터 분석까지👩‍💻


### 👤contributor

* [최리안](https://github.com/leeeeean)
* [배수혜](https://github.com/Uranel)
* [황희주](https://github.com/heejuHwang)
* [서유림](https://github.com/yurim22)

--------------------------------------------------

## Fence Project?🚧

* 2020-1학기 명지대학교 캡스톤 디자인 수업에서 진행하는 프로젝트입니다.

* 범죄예방 이론 및 정책 중에서도 CPTED의 뛰어난 범죄 예방 효과에 주목하여, 이를 기반으로 한 통계적 분석과 그 결과를 통한 안전지도의 구현을 최종 목표로 합니다.

> CPTED란?
> 'Crime Prevention Through Environmental Design'의 약자로, '환경설계를 통한 범죄예방'을 의미합니다.


### 분석문항

📎 **분석1.** 서울특별시 각 자치구 범죄율 순위

📎 **분석2.** CPTED의 5가지 물리적 요인과 치안 등급의 관계

📎 **분석2-1.** cctv 수는 치안 등급에 영향을 미치는가?

📎 **분석2-2.** 보안등 수는 치안 등급에 영향을 미치는가?

📎 **분석2-3.** 경비원 수는 치안 등급에 영향을 미치는가?

📎 **분석2-4.** 파출소 수는 치안 등급에 영향을 미치는가?

📎 **분석2-5.** 근린시설 수는 치안 등급에 영향을 미치는가?


-------------------------------------------------------------------------

## 분석1. 서울특별시 각 자치구 범죄율 순위

👤contributor : [서유림](https://github.com/yurim22)

* 서울시내 모든 자치구에 대해 범죄등급을 조사하고 분석하는 데에는 무리가 있다고 판단하여 범죄율이 높은 자치구를 선별하여 분석을 진행하고자 한다.
    - 이후 추가적으로 범죄율이 낮은 6개의 자치구에 대해서도 분석 진행
    - 범죄율 상위 8개구 / 범죄율 하위 6개구 선별
    
* 이에 모든 분석과정에 앞서 서울시 내 자치구 범죄율 순위를 분석하는 과정을 거친다.

### 📋활용한 데이터

* 서울시 관서별 5대범죄(2018년)
   - 출처 : 공공데이터 포털 
   - [홈페이지](https://www.data.go.kr/data/15054737/fileData.do)

* 서울시 인구분포(2018년)
   - 출처 : 국가통계포털 
   - [홈페이지](http://kosis.kr/index/index.do)
   
   
### ✏️분석 방법
> 범죄율=(형법범죄 / 총인구) ×  100,000

* 서울시 자치구별 발생한 5대범죄 건수를 파악하고 총 범죄 발생 건수를 구한다.
* 범죄율 구하는 공식에 따라 범죄 발생건수를 자치구 인구 수로 나누어 주고 100000을 곱한다.
* 인구 십만명 당 발생하는 범죄 건수를 구하여 sorting한다.

1. 범죄율 순위 결과(table)

![범죄율 순위표](https://user-images.githubusercontent.com/33304898/82736405-8a409480-9d64-11ea-94ef-3ebe06b204ec.JPG)

2. 범죄율 시각화(plot)

<img src="https://user-images.githubusercontent.com/33304898/82801273-05ff2600-9eb8-11ea-8faa-e6aec62b0786.png"  width="600" height="370">


### ✏️분석 결과
* 중구 / 종로구 / 마포구 / 영등포구 / 용산구 / 금천구 / 강남구 / 구로구 순으로 범죄율이 높게 나타났다.

* 은평구 / 도봉구 / 성북구 / 노원구 / 양천구 / 강서구 순으로 범죄율이 낮게 나타났다.

### 이후 활동

* 각 구별로 데이터를 수집하고 전처리를 진행한다.

----------------------------------------------------------------------------

## 분석2. CPTED의 5가지 물리적 요인과 치안 등급의 관계


👤contributor

* [최리안](https://github.com/leeeeean)
* [배수혜](https://github.com/Uranel)
* [황희주](https://github.com/heejuHwang)
* [서유림](https://github.com/yurim22)


* 본격적인 분석에 들어가기 앞서 각 구역 별 치안안전등급 조사를 실시한다.

* `구역`의 범위는 각 지구대 및 파출소의 관할구역으로 지정한다.
   - 경찰청에서 요청하여 제공받은 '서울특별시 지방경찰청과 경찰서의 조직 및 사무분장규칙(법령전문)' 자료 참고

### 참고 자료 및 사이트

* 생활안전지도 

   - [홈페이지](https://www.safemap.go.kr/main/smap.do)
   
* 서울특별시 지방경찰청과 경찰서의 조직 및 사무분장규칙(법령전문)


### 📋데이터 수집

1. 생활안전지도의 치안안전 정보를 바탕으로 각 지역 별 5대범죄 및 전체 등급 수집

   > 5대범죄 : 살인, 강도, 절도, 폭력, 성폭력
   
   > 전체 등급 : 전체 범죄등급에 대한 평균
   
   * 범죄 정보 관련하여 여러 부정적인 영향이 있기 때문에 경찰청에서 자세하고 직접적인 범죄 데이터를 제공해주지 않는다.
   
   * 지도에서 하나하나 찾아가면서 엑셀에 정리
   
   * 생활안전지도에서 제공하는 치안안전등급 정보는 다음과 같다.
   
<img src="https://user-images.githubusercontent.com/33304898/82802455-e537d000-9eb9-11ea-8c7e-faa855157aee.png" width = 600, height = 300>
       
       
      - 생활안전지도에서 api형태가 아닌 png로 데이터를 제공해주기 때문에 직접 수집해야하는 어려움이 있었다.
       

2. 지구대 및 파출소 별 관할 구역 데이터 정리

   * 경찰청으로부터 제공받은 한글파일을 바탕으로 파출소 및 지구대 별 관할구역을 엑셀로 정리

3. 지구대 및 파출소 위도, 경도 데이터 추가

### 📋데이터 전처리

파출소 및 지구대 이름을 기준으로 직접 정리한 치안 안전 등급과 파출소 및 지구대 관할구역을 합쳐 하나의 파일로 생성 

1. 서울시 각 자치구의 범죄율 순위를 바탕으로 상위 8개의 구 조사 

    - [데이터보기](https://github.com/MJU-Capstone-Design/FENCE_data_analysis/blob/master/yurim/02secure_data/secure_7.csv)
    - 중구
    - 종로구
    - 마포구
    - 영등포구
    - 용산구
    - 금천구
    - 강남구
    - 구로구
    
 2. 서울시 각 자치구의 범죄율 순위를 바탕으로 하위 6개의 구 조사
 
    - [데이터보기](https://github.com/MJU-Capstone-Design/FENCE_data_analysis/blob/master/yurim/02secure_data/low_secure.csv)
    - 강서구
    - 양천구
    - 노원구
    - 성북구
    - 도봉구
    - 은평구


### 활용계획

* 지구대 및 파출소의 관할구역을 기준으로 구역을 나누어 범죄예방에 관련이 있다고 생각하는 요인들과 치안등급 간의 상관관계 분석
