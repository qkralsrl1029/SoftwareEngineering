# Problem Statement
## The problem
  세상엔 여러 음악이 존재하고 이에 따라서 온라인 음원 시장 또한 급격히 발전하고 있습니다.
  다양한 창작자와 창작물들이 등장하고, 인터넷 상에서 무단 복제되면서 저작권 문제가 대두되고 있습니다.
  저희의 목표는 저작자의 권리가 보호될 수 있도록, 창작물의 독창성을 보장해주는 것입니다.

## Scenarios
* 음원 등록 요청
  음원 등록자는 'Crypto Music'을 이용하여 자신의 창작물을 등록 요청할 수 있습니다.

* 검증
  'Crypto Music'은 ~~기술을 통해서 음원의 독창성을 내부적으로 검증한다. 

* 등록 승인
  검증 단계에서 표절이 아니라고 판단되었으면, 이 음악은 블록체인에 업로드 된다. 음원 등록자는 자신의 패킷을 포장해서 업로드 한다. 
  하지만 우리는 음원 등록자가 검증 결과를 무단으로 변경하지 않았음을 보장할 수 없다. 따라서 블록체인을 사용하는 다른 노드들, 즉 체인을 구성하는 다른 음원 등록자들 중 50프로 이상이 이 패킷에 대한 검증을 해서, 무결성(위변조 X)를 보장할 수 있다면 이 패킷은 블록체인 노드에 추가된다. 

* 서비스 유지
  블록체인을 유지하기 위해서, 음원 등록자는 월에 일정량 이상의 시간을 서버로 제공할 의무로 갖는다. 만약 음원 등록자가 서버로 자신의 자원을 제공하지 않는다면 우리의 검증 서비스는 더이상 음원 등록자의 저작물의 권리를 보호해주지 않는다. 즉 검증 서버의 DB에서 이 음원을 제거한다.


# Customer‘s Requirements

1. 저작권
  0. 자신의 고유한 창작물이 저작권이 지켜져 악의적인 표절로부터 보호받고 싶다.
  1. 자신이 등록한 음원의 저작권이 안전하게 보호되어야 한다. (저작자의 저작권이 악의적으로 변경되면 안된다.)

2. 유사도
  0. 자신의 음원을 시스템에 등록을 할 때, 자신의 창작물이 기존에 있는 음원들과 어느정도 유사한지 궁금하다.
  1. 검증을 할 때 전체적인 느낌도 판단해서 지표를 산출 했음 좋겠다. 
    (#참조1)
    1. 다만 이 지표는 음악 전문가와 일반 청취자들을 구별해서 판단하여 전문가에 우선순위를 두어야 한다.
    2. 장르와 클리셰를 염두에 두고 코드의 진행 방식과 같은 요소로 판단해야한다. 
      ex. swing장르 아이유 분홍신 vs nekta here’s us 일반인이 듣기엔 곡이 비슷하나 전문가가 들을때는 다를 수 있다.
  2. 패러디와 구별이 되어야 한다. (#참조2)
  3. 표절로 판단이 되었을 때 어떤 음원과 유사한지 결과가 나왔으면 좋겠다.
  4. 표절 검증이 빠르고 정확해야한다.

3. 조회
  0. 자신의 창작물을 포함하여 등록된 음원들을 조회할 수 있으면 좋겠다. (스트리밍과는 별개)
  1. 악의적인 표절을 한 음원도 시스템에 등록이 되어 저작권 침해를 한 창작자를 알 수 있어야 한다.


#참조1
<blockquote>
“표절”이란 일반적으로 두 저작물간의 실질적으로 표현이 유사한 경우는 물론 전체적인 느낌이 비슷한 경우까지를 의미하며, 그 안에는 타인의 저작물을 자신이 창작작한 것처럼 속였다는 도덕적 비난이 강하게 내포되어 있습니다. 따라서 타인의 저적물의 창작적 표현을 복제하였을 경우에는 표절의 문제가 발생할 수 있습니다(한국저작권위원회, 저작권자동상담시스템).

음악저작물의 저작권 침해여부를 판단하는 것은 쉬운 일은 아니지만, 일반적으로 가락, 리듬, 화음의 3가지 요소의 실질적 유사성 여부가 일반적인 기준이 됩니다. 특히 가락이 가장 중요한 요소를 차지하게 되는데, 개별적인 음표의 유사성보다는 그 음표가 어떻게 결합되어 연속되었는지가 중요합니다. 이와 같이 음악저작물의 저작권 침해여부를 판단하는 것은 쉬운 일은 아닙니다. 다만 판례에 따른 법률적 판단기준을 살펴보면 ① 기존 저작물을 이용하였을 것, 즉 창작적 표현을 복제 하였을 것, ② 기존의 저작물에 ‘의거’하여 이를 이용하였을 것, ③ 원저작물과의 사이에 실질적유사성이 있을 것 등입니다.
</blockquote>

# 참조2
<blockquote>
패러디(Parody)”란 표현의 형식을 불문하고 원작을 이용하여 원작 자체나 사회적 상황에 대하여 풍자적, 해학적 방식으로 비평하거나 웃음을 이끌어 내는 것으로써, 표절이 되지 않습니다. 패러디는 비평적 모방이라고 할 수 있는데, 유명한 원작을 대상으로 하고 누구든지 원작을 떠올릴 수 있는 방법으로 창조적 모방을 한다는 점에서 원작을 몰래 모방하는 표절과 구분하고 있습니다.
패러디가 표절로 인정되지 않는 이유는 기존 작품의 비평, 풍자를 위한 모방은 자유로운 표현행위로써 헌법상의 표현의 자유로 보호받아야 하며, 또한 새로운 문화의 향상발전이라는 「저작권법」의 목적과도 부합하기 때문입니다.
        「저작권법」 제28조에서 “공표된 저작물은 보도·비평·교육·연구 등을 위하여 정당한 범위 안에서 공정한 관행에 합치되게 이를 인용할 수 있다”고 규정하는 것을 패러디의 근거로 생각할 수 있습니다. 따라서 우리 「저작권법」상 적법한 패러디가 되기 위해서는 ① 비평 목적이 있어야 하며, ② 정당한 범위 안에서, ③ 공정한 관행에 따라 원작을 이용해야 합니다.
        우리 법원도 “컴백홈” 사건에서 당해 저작물에 대한 비평과 풍자는 패러디로 보호된다고 인정하면서도 원곡의 특징을 흉내 내어 단순히 웃음을 자아내는 정도는 패러디로 볼 수 없다고 판결하였습니다(서울고등법원 2010.10.13. 선고. 2010나35260 판결).  
</blockquote>
