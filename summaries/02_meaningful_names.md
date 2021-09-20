# 2장 의미 있는 이름

## 의도를 분명히 밝혀라

```java
public List<int[]> getThem() {
    List<int[]> list1 = new ArrayList<int[]>();
    for (int[] x : theList)
      if (x[0] == 4)
        list1.add(x);
    return list1;
}
```

이 메소드는 당최 무슨 역할을 하는 것인지 감도 안온다. 또한 각 자료구조들과 변수명들은 용도를 절대로 알 수가 없다.

```java
public List<Cell> getFlaggedCells() {
    List<Cell> flaggedCells = new ArrayList<Cell>();
    for (Cell cell : gameBoard)
      if (cell.isFlagged())
        flaggedCells.add(cell);
    return flaggedCells;
}
```

단순히 이름을 고치는 것만으로 함수가 무슨 일을 하는지 이해하기 수월해진다.

## 의미 있게 구분하라

컴파일러나 인터프리터만 통과하려는 생각으로 코드를 구현하는 프로그래머는 스스로 문제를 일으킨다.

```java
public static void copyChars(char[] a1, char[] a2) {
    for (int i = 0; i < a1.length; i++) {
        a2[i] = a1[i];
    }
}
```

위와 같은 함수의 파라미터명을 `a1`, `a2`로 한다면 함수 인수에 대한 정보가 전혀 드러나지 않는다.

```java
getActiveAccount();
getActiveAccounts();
getActiveAccountInfo();
```

위 3개의 함수의 차이를 알 수 있는가? 절대로 모를 것이다.

읽는 사람이 차이를 알도록 이름을 지어야 한다.

## 발음하기 쉬운 이름을 사용하라

사람은 단어에 능숙하다. 두뇌에서 상당 부분은 단어라는 개념만 전적으로 처리한다. 또한 단어는 발음이 가능하다. 발음은 곧 말이고, 말은 두뇌에서 처리되기 위해 필요하다.

이름을 지을 경우 처음보는 사람이 절대로 추측하거나 발음할 수 없는 이름일 경우, 발음이 안되기 때문에 일단 대화가 통하지 않는다.

generate date, year, month, day, hour, minute, second 를 `genymdhms`처럼 한다면 누가 발음할 수 있겠는가?

적절히 `Timestamp`와 같은 단어를 합성하는 것이 좋아보인다.

## 클래스 이름

`Manager`, `Processor`, `Data`, `Info` 등과 같은 단어를 피하고, 동사는 사용하지 말자.

## 메서드 이름

동사나 동사구가 적합하다. 접근자, 변경자, 조건자는 자바빈 표준에 따라 get, set, is를 붙인다.

## 한 개념에 한 단어를 사용하라

메서드명이 어쩔 땐 `fetch`이다가, 어쩔 땐 `get`이라면 매우 헷갈린다. 어휘를 선택할 때는 일관성 있게 해야 한다.

## 불필요한 맥락을 없애라

일반적으로 짥은 이름이 긴 이름보다 좋다. 단, 의미가 분명한 경우에 한해서.

`accountAddress`와 `cutomerAddress`는 `Address`클래스의 인스턴스로는 좋은 이름이지만, 클래스의 이름으로는 적합하지 못하다.
