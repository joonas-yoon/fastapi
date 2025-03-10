# 쿠키 매개변수

`Query` 및 `Path` 매개변수를 정의한 방법과 동일하게 쿠키 매개변수를 정의할 수 있습니다.

## `Cookie` 임포트

먼저 `Cookie`를 임포트합니다:

```Python hl_lines="3"
{!../../../docs_src/cookie_params/tutorial001.py!}
```

## `Cookie` 매개변수 선언

이제 `Path` 및 `Query`를 사용한 동일한 구조를 이용하여 쿠키 매개변수를 선언합니다.

첫 번째 값은 기본값이며, 추가 검증이나 어노테이션 매개변수 모두 전달할 수 있습니다:

```Python hl_lines="9"
{!../../../docs_src/cookie_params/tutorial001.py!}
```

!!! note "기술적 세부사항"
    `Cookie`는 `Path` 및 `Query`의 "자매" 클래스입니다. 이 역시 동일한 공통 `Param` 클래스를 상속합니다.

    `Query`, `Path`, `Cookie` 그리고 다른 것들을 `fastapi`에서 임포트 할 때, 이들은 실제로 특별한 클래스를 반환하는 함수임을 기억하세요.

!!! info "정보"
    쿠키를 선언하기 위해서 `Cookie`를 사용해야 합니다. 그렇지 않으면 해당 매개변수를 쿼리 매개변수로 해석하기 때문입니다.

## 요약

`Cookie`를 `Query` 및 `Path`와 동일한 공통 패턴을 사용하여 선언합니다.
