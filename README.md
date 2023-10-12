# 키친포스

## 요구 사항

### 메뉴 그룹
- 메뉴 그룹은 이름을 갖는다.
- [x] 메뉴 그룹을 생성한다.
- [x] 메뉴 그룹을 전체 조회한다.

### 메뉴
- 메뉴는 이름, 가격, 메뉴 그룹 정보, 메뉴 상품(해당 메뉴와 개수)들을 갖는다.
- [x] 메뉴를 생성한다.
  - [x] 메뉴에서 가격은 음수가 될 수 없다.
  - [x] 메뉴는 메뉴 그룹에 속해야한다.
  - [x] 입력받은 메뉴의 가격은 메뉴 상품들의 가격보다 비싸면 안된다. (할인하거나 같아야함)
- [x] 메뉴를 전체 조회한다

### 상품
- 상품은 이름과 가격을 갖는다.
- [x] 상품을 생성한다.
  - [x] 상품의 가격은 음수가 될 수 없다.
- [x] 상품을 전체 조회한다.

---

### 주문
- 주문은 주문한 테이블 정보(테이블 그룹 정보(생성 날짜, 주문 테이블 정보), 손님 수, 테이블이 등록되어 있는지), 주문 상태(조리, 식사, 계산 완료), 주문 시간, 메뉴 정보(메뉴, 수량)을 갖는다.
- [x] 주문을 생성한다.
  - [x] 메뉴 정보가 아무것도 없으면 예외처리한다.
  - [x] 메뉴 정보들에 존재하는 메뉴가 DB에 존재하지 않으면 예외 처리한다.
  - [x] 테이블 정보가 DB에 존재하지 않으면 예외처리한다.
  - [x] 주문을 처음 생성하면 조리 상태가 된다.
- [x] 주문을 전체 조회한다.
- [x] 주문 상태를 변경한다.
  - [x] 이미 계산 완료되었으면 상태를 변경할 수 없다.

### 단체 지정
- 단체 지정은 생성 시간과 주문한 테이블 정보들을 갖는다.
- [ ] 단체 지정을 생성한다.
  - [ ] 테이블이 2개 이상일 때 합칠 수 있다.
  - [ ] 주문한 테이블 정보들이 DB에 존재하지 않으면 예외처리한다.
  - [ ] 테이블이 빈 테이블이 아니거나 다른 단체 지정이 되어있으면 예외 처리한다.
- [ ] 단체 지정을 해제한다.
  - [ ] 주문한 테이블들이 계산 완료 상태가 아니라면 예외 처리한다.

### 테이블
- 테이블은 단체지정 정보와 손님 수 빈 테이블인지 정보를 갖는다.
- [ ] 테이블을 등록한다.
- [ ] 테이블을 전체 조회한다.
- [ ] 빈 테이블인지 아닌지 상태를 변경한다.
  - [ ] 단체 지정이 되어있으면 예외처리한다.
  - [ ] 빈 테이블이 아니고 계산 완료 상태가 아니라면 예외처리한다.
- [ ] 테이블의 손님수를 변경한다.
  - [ ] 손님의 수가 0보다 작으면 예외 처리한다.
  - [ ] 빈 테이블이면 예외 처리한다.

---
## 용어 사전

| 한글명 | 영문명 | 설명 |
| --- | --- | --- |
| 상품 | product | 메뉴를 관리하는 기준이 되는 데이터 |
| 메뉴 그룹 | menu group | 메뉴 묶음, 분류 |
| 메뉴 | menu | 메뉴 그룹에 속하는 실제 주문 가능 단위 |
| 메뉴 상품 | menu product | 메뉴에 속하는 수량이 있는 상품 |
| 금액 | amount | 가격 * 수량 |
| 주문 테이블 | order table | 매장에서 주문이 발생하는 영역 |
| 빈 테이블 | empty table | 주문을 등록할 수 없는 주문 테이블 |
| 주문 | order | 매장에서 발생하는 주문 |
| 주문 상태 | order status | 주문은 조리 ➜ 식사 ➜ 계산 완료 순서로 진행된다. |
| 방문한 손님 수 | number of guests | 필수 사항은 아니며 주문은 0명으로 등록할 수 있다. |
| 단체 지정 | table group | 통합 계산을 위해 개별 주문 테이블을 그룹화하는 기능 |
| 주문 항목 | order line item | 주문에 속하는 수량이 있는 메뉴 |
| 매장 식사 | eat in | 포장하지 않고 매장에서 식사하는 것 |
