# Steam 플렛폼 구매율 예측<br>
<br>
<img src = 'http://images.vg247.com/current//2011/04/steam1.jpg'><br>
<br>
# 프로젝트 개요<br>
<br>
## **목표**<br>
스팀 플렛폼(게임)에 관련된 데이터로 <span style="color:red">구매율(어플리케이션 소유자 수)</span>를 예측하는 모델을 생성<br>
<br>

## **변수정의**<br>
<br>
  * appid - 게임 고유 ID
  * name - 게임 이름
  * developer - 개발자(여러 개발자 일 경우 쉼표로 구분)
  * publisher - 발행자(유통사)
  * score_rank - 사용자 리뷰를 기반으로 만들어진 게임의 점수 등급
  * positive - 긍정적인 사용자의 리뷰 수
  * negative - 부정적인 사용자의 리뷰 수
  * userscore - 게임 사용자들이 평가한 점수
  * <span style="color:red">owners - steam에서 해당 어플리케이션 소유자 수</span>
  * owners_variance - 소유자 분산(변동,차이). (실제소유자 +/- 변동범위) 형태로 표기
  * players_forever - 2009년 3월 이후로 플레어 수
  * players_forever_variance - 전체 플레이어의 분산.
  * players_2weeks - 지난 2 주 동안 플레이어들의 수
  * players_2weeks_variance - 지난 2 주 동안 플레이어의 수에 대한 분산
  * average_forever - 2009년 3월 이후 플레이 시간(평균). 분 단위.
  * average_2weeks - 지난 2 주간 플레이 시간(평균). 분 단위.
  * median_forever - 2009년 3월 이후 플레이 시간(중앙값). 분 단위.
  * median_2weeks - 지난 2 주간 플레이 시간(중앙값). 분 단위. 
  * price - US가격. 센트 단위.
  * ccu - 어제 최고 CCU(개별 앱이 요청된 경우에만 카운트) **
  * tags - 해당 게임의 태그(Yes=1, No=0)
  * genre - 해당 게임의 장르(Yes=1, No=0)
