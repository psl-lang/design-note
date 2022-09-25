# 표준 입출력

PS에서 표준 입출력을 자주 활용하는 만큼, 특수 문법으로 지정하여 사용합니다.

## 입력 받기

형식 입력 문법을 기본으로 하고, 나머지 문법은 논의해볼 만한 문법적 설탕입니다.

```
<형식 입력> = "read" <형식 지정자>
<공백 구분 입력> = "read" <식별자>,* // TODO: 의견 수렴
<선언과 동시에 입력> = "read " <타입> <식별자>,* // TODO: 의견 수렴
```

## 출력하기

형식 출력 문법을 기본으로 하고, 나머지 문법은 논의해볼 만한 문법적 설탕입니다.

```
<형식 출력> = "write" <형식 지정자>
<공백 구분 출력> = "write" <식별자>,* // TODO: 의견 수렴
```