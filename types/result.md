# 결과 타입 (T!)

결과 타입은 `성공(T 값)`이거나 `실패(예외 정보)`인 타입이다. 결과 값은 다음 규칙에 따라 해석한다.

1. bool로 변환할 경우:
    결과 값이 성공일 경우 true로, 실패일 경우 false로 변환한다.
2. catch로 처리할 경우:
    1. catch `예외 유형`으로 처리한 경우:
        결과 값이 실패이고, 지정한 예외 유형인 경우 catch 코드 블록을 실행한다.
        결과 값이 실패지만 지정한 예외 유형이 아닌 경우, 즉시 throw한다.
        결과 값이 성공일 경우 그냥 진행한다.
    2. catch로 처리한 경우:
        결과 값이 실패일 경우 catch 코드 블록을 실행한다.
        결과 값이 성공일 경우 그냥 진행한다.
3. 처리하지 않을 경우:
    결과 값이 실패인 경우 즉시 throw된다.

(TODO: try ~ catch 구문이 필요한지)
throw되는 동작의 경우 바깥의 try ~ catch 구문이 있다면 예외를 낚아챌 수 있으며,
낚아채지 않은 경우 예외는 복구 불능 오류로 간주해 프로그램을 오류 코드 1로 종료시킨다.

## 예시

```
// 생각해볼 점: T!가 bool이 되는 동작(1)과 T!가 T가 되는 동작(3)이 헷갈리지는 않는지?
// 1의 경우
i32! i = some_fallible_operation()
if i { /* 실패하지 않았으니 i 사용 */ } else { /* 실패 */ }

// 2의 경우
i32 i = some_fallible_operation() catch { exit(0) }
i32 i = some_fallible_operation() catch Failure { value_only_in_failure } // TODO: 넣을지, 지금 문법으로 넣을지

// 3의 경우, 실패한 경우 throw, 성공한 경우 그냥 i32
i32 i = some_fallible_operation()
```
