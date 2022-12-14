# 실패 가능성 타입 (fallible)

실패 가능성 타입은 `성공`이거나 `실패(예외 정보)`이다. 그 값은 다음 규칙에 따라 해석한다.

1. bool로 변환할 경우:
    - `성공`일 경우 `true`로, `실패`일 경우 `false`로 변환한다.
2. catch로 처리할 경우:
    1. catch `예외 유형`으로 처리한 경우:
        - `실패`이고, 지정한 `예외 유형`인 경우 catch 코드 블록을 실행한다.
        - `실패`지만 지정한 `예외 유형`이 아닌 경우, 즉시 throw한다.
        - `성공`일 경우 그냥 진행한다.
    2. catch로 처리한 경우:
        - `실패`일 경우 catch 코드 블록을 실행한다.
        - `성공`일 경우 그냥 진행한다.
3. 처리하지 않을 경우:
    - `실패`인 경우 즉시 throw된다.

(TODO: try ~ catch 구문이 필요한지 고민해보기)

throw되는 동작의 경우 바깥의 try ~ catch 구문이 있다면 예외를 낚아챌 수 있으며,
낚아채지 않은 경우 예외는 복구 불능 오류로 간주해 프로그램을 오류 코드 1로 종료시킨다.
디버그 모드일 경우 예외 메시지와 발생 지점을 추적할 수 있다.

## 예시

```
// 1의 경우
if some_fallible_operation() {
  // 성공
} else {
  // 실패
}

// 2의 경우
some_fallible_operation() catch { exit(0) }
some_fallible_operation() catch Failure { work_only_in_failure_type() }

// 3의 경우, 실패라면 throw, 아니면 그냥 실행
some_fallible_operation()
```
