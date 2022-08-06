# 응답 헤더

## `Response` 매개변수 사용하기

*경로 연산 함수*에서 `Response` 타입의 매개 변수를 지정할 수 있습니다. (응답 쿠키에서 처럼).

그런 다음 *임시* 응답 객체에 헤더를 설정할 수 있습니다.

```Python hl_lines="1  7-8"
{!../../../docs_src/response_headers/tutorial002.py!}
```

그런 다음 평소처럼 필요한 객체를 반환할 수 있습니다 (`dict`, 데이터베이스 모델, 기타 등등).

`response_model`를 선언했다면, 반환될 객체를 필터링, 변환하는데 여전히 사용될겁니다.

**FastAPI**는 *임시* 응답 객체를 이용해 헤더(그리고 쿠키, 응답 코드)를 추출하고, `response_model`로 필터링 된 최종 값들이 최종 응답에 포함될 것입니다.

또는 `Response` 매개변수를 종속성에서 선언하고, 거기에 헤더(그리고 쿠키)를 설정할 수도 있습니다.

## `Response` 직접적으로 반환하기

`Response`를 직접적으로 반환할 때 헤더를 추가할 수도 있습니다.

[응답 직접 반환하기](response-directly.md){.internal-link target=_blank}에 설명된 것 처럼 응답을 만들어 추가적인 매개 변수와 함께 헤더를 넘기면 됩니다.

Create a response as described in [Return a Response Directly](response-directly.md){.internal-link target=_blank} and pass the headers as an additional parameter:

```Python hl_lines="10-12"
{!../../../docs_src/response_headers/tutorial001.py!}
```

!!! note "기술적 세부사항"
    `from starlette.responses import Response` 혹은 `from starlette.responses import JSONResponse`를 사용하도 됩니다.

    **FastAPI**는 `starlette.responses`를 개발자의 편리함을 위해 `fastapi.responses`로 이름을 바꿔 제공하고 있습니다. 대부분의 가능한 응답은 Starlette에서 직접 제공하고 있습니다.

    그리고 `Response`는 헤더와 쿠키를 설정하는 데 자주 사용할 수 있으므로, **FastAPI**또한 이걸 `fastapi.Response`로 제공하고 있습니다.

## 커스텀 헤더

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers" class="external-link" target="_blank">'X-' 접두사를 이용해</a> 사용자 정의 독점 헤더를 추가할 수도 있음을 염두에 두십시오.

하지만 브라우저에서 클라이언트가 볼 수 있는 커스텀 헤더를 갖게 할려면 CORS 설정에서 이를 추가해야 됩니다. ([CORS (Cross-Origin Resource Sharing)](../tutorial/cors.md){.internal-link target=_blank}에서 자세히 읽어보세요.) <a href="https://www.starlette.io/middleware/#corsmiddleware" class="external-link" target="_blank">Starlette's CORS docs</a>에서 설명된 `expose_headers`를 사용하세요.
