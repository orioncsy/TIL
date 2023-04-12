# Anomaly

## 개념

### Anomaly

- 정규화를 해야 하는 이유는 anomaly라는 이상 현상을 방지하기 위해서 이다.

## 종류

### 삽입 이상(Insertion Anomaly)

- 기본키가 {MemberId, ClassId}라고 할 경우 클래스를 수강하지 않은 멤버는 ClassId를 null로 해야 하는데 기본키는 null이 될 수 없어 table에 추가가 불가능하다.
- 삽입하기 위해서는 수강하지 않는다는 값을 만들어 넣어야한다.

### 갱신 이상(Update Anomaly)

- 어떤 멤버가 듣는 수업을 체육에서 미술로 변경한다고 하면, 모든 ClassId를 변경해주어야 하지만 일부에서는 변경이 일어나지 않아 데이터가 불일치하는 경우 발생

### 삭제 이상(Deletion Anomaly)

- 어떤 멤버가 수업을 철회하였을 경우 해당 튜플을 삭제하면서 멤버의 정보들도 함께 삭제되는 현상 발생
- 필요한 정보까지 함께 삭제되는 문제를 예방하기 위해 정규화를 통해 table을 나눈다.

## Reference

[https://gyoogle.dev/blog/computer-science/data-base/Anomaly.html](https://gyoogle.dev/blog/computer-science/data-base/Anomaly.html)