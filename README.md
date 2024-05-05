# 키친포스

## 퀵 스타트

```sh
cd docker
docker compose -p kitchenpos up -d
```

## 요구 사항

- ```kitchenpos``` 패키지의 코드를 보고 키친포스의 요구 사항을 정리한다.

#### 메뉴

- 메뉴 정보에는 이름, 가격, 그룹정보, 노출여부, 상품상세정보가 있다.
- 신규 등록
    - [ ] 메뉴 이름
        - [ ] 메뉴 이름은 필수로 입력해야한다.
        - [ ] 메뉴 이름에 욕설이 포함되어있는 경우 등록할 수 없다.
    - [ ] 메뉴 금액
        - [ ] 메뉴마다 금액정보는 필수로 입력해야한다.
        - [ ] 0원보다 적은 금액을 입력하는 경우 메뉴를 등록할 수 없다.
    - [ ] 메뉴그룹정보
        - [ ] 하나의 메뉴 그룹 정보가 필수로 입력해야한다.
        - [ ] 등록되어있지 않은 그룹정보를 입력하는 경우 메뉴를 등록할 수 없다.
    - [ ] 노출 여부
        - [ ] 메뉴 노출여부를 처음에 결정할 수 있다.
        - [ ] 노출여부는 필수로 입력해야한다.
    - [ ] 상품상세정보
        - [ ] 메뉴를 구성하는 상품정보를 필수로 입력해야한다.
        - [ ] 상품정보는 하나 이상 입력이 가능하다.
        - [ ] 등록되어있지 않은 상품정보를 입력하는 경우 메뉴를 등록할 수 없다.
        - [ ] 상품정보의 수량이 0보다 작은 경우 메뉴를 등록할 수 없다.
        - [ ] 상품정보의 총 합계 금액보다 메뉴의 가격이 비싼 경우 등록할 수 없다.
- 금액 변경
    - [ ] 메뉴는 금액을 변경할 수 있다.
    - [ ] 변경할 금액 정보가 없는 경우 변경이 불가하다.
    - [ ] 0보다 작은 금액을 입력하는 경우 변경이 불가하다.
    - [ ] 변경하려고 하는 메뉴 정보가 없는 경우 변경이 불가하다.
    - [ ] 변경금액이 상품 총 합계 금액보다 비싼 경우 변경할 수 없다.
- 노출여부 변경
    - [ ] 메뉴는 노출여부를 변경할 수 있다.
    - 노출로 변경
        - [ ] 등록된적 없는 메뉴는 변경이 불가하다.
        - [ ] 노출하려는 메뉴의 금액이 상품정보의 총 합계 금액보다 높은 경우 변경할 수 없다.
    - 미노출로 변경
        - [ ] 등록된적 없는 메뉴는 변경이 불가하다.
- 전체 조회
    - [ ] 등록되어 있는 모든 메뉴를 조회할 수 있다.

#### 메뉴그룹

- 등록
    - [ ] 메뉴 그룹의 이름은 필수로 입력해야한다.
    - [ ] 빈값만 입력하는 경우 등록할 수 없다.
- 전체 조회
    - [ ] 등록되어 있는 전체 메뉴 그룹을 조회할 수 있다.

#### 상품

- 등록
    - [ ] 싱픔의 가격은 필수로 입력해야한다.
    - [ ] 0보다 적게 입력하는 경우 등록할 수 없다.
    - [ ] 상품 이름을 입력하지 않는 경우 등록할 수 없다.
    - [ ] 상품 이름에 욕설이 포함되어있는 경우 등록할 수 없다.
- 가격 변경
    - [ ] 상품 가격은 변경할 수 있다.
    - [ ] 변경 가격을 입력하지 않는 경우 변경할 수 없다.
    - [ ] 0보다 적게 입력하는 경우 변경할 수 없다.
    - [ ] 등록되어 있지 않은 상품 정보인 경우 변경할 수 없다.
    - [ ] 금액 변경으로 인해 해당 상품이 포함된 메뉴의 가격이 메뉴 구성 전체 상품의 총 금액보다 비싸지는 경우 변경할 수 없다.
- 전체 조회
    - [ ] 등록되어 있는 전체 상품을 조회할 수 있다.

#### 주문

- 주문접수
    - 주문접수를 받을 때에는 주문타입, 주문테이블, 메뉴정보가 있다.
    - 주문타입
        - [ ] 주문타입 정보가 없는 경우 주문을 받을 수 없다.
        - 포장
          - [ ] 주문한 메뉴 중 0개보다 작은 메뉴가 있는 경우 주문할 수 없다.
        - 배달 주문
            - [ ] 배달 주소 정보는 필수로 입력해야한다.
            - [ ] 주문한 메뉴 중 0개보다 작은 메뉴가 있는 경우 주문할 수 없다. 
        - 매장식사
            - [ ] 주문 테이블 정보가 필요하다.
            - [ ] 손님이 없는 테이블로 접수가 들어온 경우 접수가 불가능하다.
    - 메뉴
        - [ ] 하나의 주문에 여러개 메뉴 주문이 가능하다.
        - [ ] 메뉴를 하나도 선택하지 않은 경우 주문할 수 없다.
        - [ ] 주문한 메뉴들 중에 하나라도 등록되어 있지 않은 메뉴가 포함되어 있으면 주문할 수 없다.
        - [ ] 미노출된 메뉴가 포함되어있는 경우 주문할 수 없다.
        - [ ] 주문한 메뉴의 금액과 등록된 메뉴 금액이 다른 경우 주문할 수 없다.
- 주문수락
  - [ ] 등록되지 않은 주문 접수인 경우 수락이 불가능하다.
  - [ ] 주문상태가 대기중이 아닌 경우 처리가 불가능하다.
  - [ ] 배달주문인 경우 배달라이더에게 배달 요청이 필요하다. 
  - [ ] 라이더에게 요청하는 경우 주문 정보, 총금액, 배달주소 정보를 제공해야한다.
  - [ ] 주문접수가 완료된 경우 주문상태가 WAITING에서 ACCEPTED로 변경된다.

#### 주문테이블

## 용어 사전

| 한글명 | 영문명 | 설명 |
|-----|-----|----|
|     |     |    |

## 모델링
