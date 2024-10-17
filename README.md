# 1주차 문자열 덧셈 계산기

## 📌 구현할 기능 목록

- 예외 처리

    [ ] 잘못된 입력은 예외를 발생시키는 로직 구현
  
    [ ] 숫자 관련 예외 처리 메서드 구현

    [ ] 구분자 관련 예외 처리 메서드 구현

<br>

- 핵심 기능 구현

    [ ] 라이브러리를 사용하여 문자열 입력 받기

    [ ] 문자열에서 숫자를 추출해 더한 값 저장하기

    [ ] 예외 처리 적용하기

    [ ] 출력 형식에 맞게 숫자의 합 출력하기

<br>

---

## 기능 요구사항

- 입력한 문자열에서 숫자를 추출해 더한 값을 반환하는 계산기

    - 기본 구분자 `,`와 `:` 또는 커스텀 구분자를 기준으로 분리한 숫자의 합을 반환
    - 커스텀 구분자 지정은 문자열 맨 앞 부분 `//` `\n` 사이 문자로 지정

      **Q. 기본 구분자와 커스텀 구분자를 혼용하여 입력할 수 있는가?**

        - 기본 구분자와 커스텀 구분자는 구분되는 케이스로 구현할 것이다. 구분자의 종류가 늘어나는 것은 기능적으로 깔끔하지 못하다고 생각하기 때문이다.
        - 기본 구분자는 이미 2가지로 지정되어 있기에, 커스텀 구분자를 사용하면 구분자를 하나로 줄일 수 있어 계산기를 보다 명확히 사용할 수 있다. 경우에 따라 사용자가 이런 장점을 획득할 수 있도록 케이스를 분리한다.
        - `//;\n1;2;3`이란 예시를 보았을 때  커스텀 구분자만 사용하는 것이 요구사항에 더 가까워보인다.
    
    - 잘못된 입력은 `IllegalArgumentException` 반환

<br>

---

## 입출력 및 예외 처리 요구사항

### 입력

- 구분자와 양수로 구성된 문자열

    e.g.`1:2,3` 기본 구분자

    e.g. `//&\n1&3&5` 커스텀 구분자

### 출력

- 덧셈 결과
- 출력 형식

```
덧셈할 문자열을 입력해 주세요.
1:2,3
결과 : 6
```

### 예외

- 잘못된 입력인 경우 발생
    - 숫자가 포함되어있지 않은 문자열
    - 음수가 포함된 문자열
    - 숫자나 구분자가 두 개 이상 연속해서 나오는 경우
    - 커스텀 구분자를 지정하지 않은 경우
        - 기본 구분자 이외의 문자 입력
    - 커스텀 구분자를 지정한 경우
        - 지정된 구분자 이외의 문자 입력

- 처리
  - `IllegalArgumentException` 반환 후 애플리케이션 종료

<br>

---

## 라이브러리

- `camp.nextstep.edu.missionutils`에서 제공하는`Console`API를 사용하여 구현해야 한다.
    - 사용자가 입력하는 값은 `camp.nextstep.edu.missionutils.Console`의 `readLine()`을 활용한다.