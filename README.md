# design-note

PS를 위한 프로그래밍 언어를 다같이 설계해봅시다

## 충분히 논의된 사항들 (추가 논의 사항이 없지는 않지만 결정된 사항이 있음)

- 변수 선언 -> [변수 선언](./syntax/variable-declaration.md)
- 입출력 형식 편하게 하기 -> [형식 지정자](./syntax/format-specifier.md), [표준 입출력](./syntax/stdio.md)

## 언급된 사항들

- C++ 혹은 C를 타겟으로 하는 source-to-source compiler
- Python만큼 쉬워야 함
- 정적 타입 사용
- C++보다는 느리지만 Python보단 나은 성능을 목표
- 전역 상태를 기본으로? 아예 스크립트처럼 main 없이 굴리는 건?
- 참조와 복사의 구분 (like Rust)
- 표준 라이브러리에 빵빵한 자구 라이브러리
- 코드 보고 시간 복잡도 쉽게 알 수 있으면 좋겠음
- 특정 문제를 해결해가며 문법 디자인해보기
- 베열 선언 numpy reshape?
- 정수 자료형은 i32 i64 ibig만?
- 자료 구조 시각적 디버거
- github 조직 팠음 :white_check_mark:
  - 이름 뭐로 하죠? psl? psudo? ips? 추가 아이디어 받아요
- 개발은 kiwiyou가 주로? 문서화는 누가 할까요
- 타입 추론 구현 어려울까요? -> 일단은 안 하는 방향?
- 연산자 우선순위
