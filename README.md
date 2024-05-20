# 키친포스

## 퀵 스타트

```sh
cd docker
docker compose -p kitchenpos up -d
```

## 요구 사항

- ```kitchenpos(키친포스)``` 요구 사항을 정리한다.

#### 메뉴그룹

- 등록
    - [X] 메뉴 그룹을 정상적으로 등록할 수 있다.
    - [X] 메뉴 그룹의 이름은 필수로 입력해야한다.
    - [X] 빈값만 입력하는 경우 등록할 수 없다.
- 전체 조회
    - [ ] 등록되어 있는 전체 메뉴 그룹을 조회할 수 있다.

#### 상품

- 등록
    - [X] 상품을 정상적으로 등록할 수 있다.
    - [X] 싱픔의 가격은 필수로 입력해야한다.
    - [X] 0원보다 적게 입력하는 경우 등록할 수 없다.
    - [X] 상품 이름을 입력하지 않는 경우 등록할 수 없다.
    - [X] 상품 이름에 욕설이 포함되어있는 경우 등록할 수 없다.
- 가격 변경
    - [X] 상품 가격은 변경할 수 있다.
    - [X] 변경 가격을 입력하지 않는 경우 변경할 수 없다.
    - [X] 0원보다 적게 입력하는 경우 변경할 수 없다.
    - [X] 등록되어 있지 않은 상품 정보인 경우 변경할 수 없다.
    - [X] 금액 변경으로 인해 해당 상품이 포함된 메뉴의 가격이 메뉴 구성 전체 상품의 총 금액보다 비싸지는 경우 메뉴가 숨겨진다.
- 전체 조회
    - [ ] 등록되어 있는 전체 상품을 조회할 수 있다.

#### 주문테이블

- 테이블정보에는 테이블이름, 손님 수, 착석여부가 있다.
- 테이블정보 등록
    - [X] 테이블정보를 정상으로 등록할 수 있다.
    - [X] 테이블 이름은 필수로 입력해야한다.
    - [X] 최초 등록시 테이블의 손님 수와 착석여부 상태는 모두 빈 좌석으로 저장된다. (손님수 0명, 미착석 상태)
- 테이블 착석여부 변경
    - [X] 테이블의 착석여부를 변경할 수 있다. -> (TODO) 착성중/미착석 분리
    - [X] 등록된 테이블정보가 아닌 경우 처리가 불가능하다.
    - 착석중
    - [X] 착석여부 상태가 착석으로 변경된다.
    - 미착석
    - [X] 테이블에 주문된적이 있고 주문상태가 COMPLETED 가 아닌 경우 처리가 불가능하다.
    - [X] 손님 수 정보와 착석여부 상태가 미착석으로 변경된다.
- 손님수 변경
    - [X] 손님수를 변경할 수 있다.
    - [X] 변경하려는 손님 수가 0명보다 적은 경우 변경할 수 없다.
    - [X] 등록된 테이블 정보가 아닌 경우 손님 수를 변경할 수 없다.
    - [X] 테이블이 손님 착성중 상태가 아닌 경우 손님 수를 변경할 수 없다.
- 전체 조회
    - [ ] 등록된 모든 테이블 정보를 조회할 수 있다.

#### 메뉴

- 메뉴 정보에는 이름, 가격, 그룹정보, 노출여부, 메뉴상품이 있다.
- 신규 등록
    - [ ] 메뉴를 등록할 수 있다.
    - [X] 메뉴 이름
        - [X] 메뉴 이름은 필수로 입력해야한다.
        - [X] 메뉴 이름에 욕설이 포함되어있는 경우 등록할 수 없다.
    - [X] 메뉴 금액
        - [X] 메뉴마다 금액정보는 필수로 입력해야한다.
        - [X] 0원보다 적은 금액을 입력하는 경우 메뉴를 등록할 수 없다.
    - [X] 메뉴그룹정보
        - [X] 등록되어있는 메뉴 그룹 정보가 필수로 입력해야한다.
    - [X] 메뉴상품
        - [X] 메뉴를 구성하는 상품정보를 필수로 입력해야한다.
        - [X] 상품정보는 하나 이상 입력이 가능하다.
        - [X] 등록되어있지 않은 상품정보를 입력하는 경우 메뉴를 등록할 수 없다.
        - [X] 상품정보의 수량이 0개보다 작은 경우 메뉴를 등록할 수 없다.
        - [X] 상품정보의 총 합계 금액보다 메뉴의 가격이 비싼 경우 등록할 수 없다.
- 금액 변경
    - [X] 메뉴는 금액을 변경할 수 있다.
    - [X] 변경할 금액 정보가 없는 경우 변경이 불가하다.
    - [X] 0원보다 작은 금액을 입력하는 경우 변경이 불가하다.
    - [X] 변경하려고 하는 메뉴 정보가 없는 경우 변경이 불가하다.
    - [X] 변경금액이 메뉴 상품의 총 합계 금액보다 비싼 경우 변경할 수 없다.
- 노출여부 변경
    - [X] 메뉴는 노출되도록 변경할 수 있다.
    - [X] 메뉴는 숨길 수 있다.
    - 노출로 변경
        - [X] 등록된적 없는 메뉴는 노출되도록 변경할 수 없다.
        - [X] 노출하려는 메뉴의 금액이 상품정보의 총 합계 금액보다 높은 경우 변경할 수 없다.
    - 미노출로 변경
        - [X] 등록된적 없는 메뉴는 노출되지 않도록 변경할 수 없다.
- 전체 조회
    - [ ] 등록되어 있는 모든 메뉴를 조회할 수 있다.

#### 주문

- 주문접수 (WAITING)
    - 주문접수를 받을 때에는 주문타입, 주문테이블, 메뉴정보가 있다.
    - 주문타입
        - [X] 주문타입 정보가 없는 경우 주문을 받을 수 없다.
    - 메뉴
        - [X] 하나의 주문에 여러개 메뉴 주문이 가능하다.
        - [X] 메뉴를 하나도 선택하지 않은 경우 주문할 수 없다.
        - [X] 주문한 메뉴들 중에 하나라도 등록되어 있지 않은 메뉴가 포함되어 있으면 주문할 수 없다.
        - [X] 미노출된 메뉴가 포함되어있는 경우 주문할 수 없다.
        - [X] 주문한 메뉴의 금액과 등록된 메뉴 금액이 다른 경우 주문할 수 없다.
        - [X] 주문이 접수완료된 경우 주문상태가 대기중(WAITING)이 된다.

    - 배달 주문
        - [X] 배달 주문을 접수받을 수 있다.
        - [X] 배달 주소 정보는 필수로 입력해야한다.
        - [X] 주문한 메뉴 중 0개보다 작은 메뉴가 있는 경우 주문할 수 없다.

    - 매장 주문
        - [X] 매장 주문을 접수받을 수 있다.
        - [X] 등록된 테이블정보가 아닌 경우 접수가 불가하다.
        - [X] 손님이 착석중이 아닌 테이블로 접수가 들어온 경우 접수가 불가능하다.
        - [X] 0개보다 적게 취소주문이 가능하다. (취소는 1개씩 가능)

    - 포장 주문
        - [X] 포장 주문을 접수받을 수 있다.
        - [X] 주문한 메뉴 중 0개보다 작은 메뉴가 있는 경우 주문할 수 없다.

- 주문수락 (ACCEPTED)
    - [X] 접수된적 없는 주문인 경우 수락이 불가능하다.
    - [X] 주문상태가 대기중이 아닌 경우 처리가 불가능하다.
    - 배달 주문
        - [X] 배달주문인 경우 배달라이더에게 배달 요청이 완료되어야 수락된다.
    - [X] 주문수락이 완료된 경우 주문상태가 대기중 에서 수락(ACCEPTED) 상태로 변경된다.
- 음식 제공 완료 (SERVED)
    - [X] 접수된적 없는 주문인 경우 처리할 수 없다.
    - [X] 주문상태가 수락상태가 아닌 경우 처리할 수 없다.
    - [X] 처리가 되는경우 주문상태가 수락에서 에서 음식제공 완료(SERVED) 로 변경된다.
- 배달 중 (DELIVERING)
    - [X] 배달주문(DELIVERY)이 아닌 경우 배달을 시작할 수 없다.
    - [X] 음식이 아직 제공되지 않은 경우(SERVED) 배달을 시작할 수 없다.
    - [X] 접수된적 없는 주문인 경우 배달을 시작할 수 없다.
    - [X] 배달이 시작되면 주문 상태는 음식 제공에서 배달중(DELIVERING) 으로 변경된다.
- 배달 완료 (DELIVERED)
    - [ ] 접수된적 없는 주문인 경우 처리할 수 없다.
    - [ ] 주문상태가 배달 중이 아니면 배달완료로 처리할 수 없다.
    - [ ] 배달완료상태가 되는 경우 배달 중 에서 배달 완료(DELIVERED) 로 변경된다.
- 주문 처리 완료 (COMPLETED)
    - [ ] 완료 상태가 되면 주문 처리 완료(COMPLETED) 가 된다.
    - [ ] 접수된적 없는 주문인 경우 처리할 수 없다.
    - 배달주문
        - [ ] 배달주문인데 배달 완료 상태가 아니면 처리할 수 없다.
    - 포장/매장주문
        - [ ] 포장주문이거나 매장식사인 경우 음식 제공 완료 상태가 아니면 처리할 수 없다.
    - 매장주문
        - [ ] 메징식사인 경우 주문상태가 완료가 되면 주문테이블의 손님 수와 착석여부 상태를 빈 좌석으로 정리한다. (손님 수 0명, 미착석 상태로 변경)
- 전체 조회
    - [ ] 접수되었던 모든 주문 정보를 조회할 수 있다.

## TODO

- [ ] repository fake 객체로 리팩토링

## 용어 사전

| 한글명 | 영문명 | 설명 |
|-----|-----|----|

## 모델링

