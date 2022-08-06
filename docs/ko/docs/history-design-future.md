# 역사, 디자인 그리고 미래

과거에, <a href="https://github.com/tiangolo/fastapi/issues/3#issuecomment-454956920" class="external-link" target="_blank">한 **FastAPI** 유저가 물었습니다.</a>

> 이 프로젝트의 역사가 어떻게 되나요? 단 몇 주 만에 어디선가 나타난 것 같아서요 [...]

여기에 그 역사를 몇 자 적어보도록 하겠습니다.

## 대안들

저는 복잡한 요구 사항에 맞는 API를 몇 년간 만들어 왔습니다. 머신 러닝, 분산 시스템, 비동기 작업, NoSQL 데이터베이스 등이었고, 여러 개발 팀을 이끌기도 했습니다.

그러다보니, 저는 많은 대안들을 알아보고 테스트하고 사용해야 했습니다.

**FastAPI**의 역사의 대부분은 그 선구자들의 역사에 있습니다.

[Alternatives](alternatives.md){.internal-link target=_blank} 문서에 적은 바와 같이,

<blockquote markdown="1">

**FastAPI**는 wouldn't exist if not for the previous work of others.
**FastAPI** wouldn't exist if not for the previous work of others.

이것을 만드는 것에 영감을 주었던, 이전에 만들어진 많은 툴들이 있었습니다.

저는 몇년 동안 새로운 프레임워크를 만드는 것을 피하고 있었습니다. 먼저 **FastAPI**에서 다루는 모든 기능을 많은 다른 프레임워크, 플러그인, 도구를 사용하여 해결하려고 했습니다.

하지만 어느 순간, 만드는 것 말고는 다른 선택지가 없었습니다. 이 모든 기능을 제공하고, 이전의 도구들에서 최고인 아이디어들은 가져오고, 그걸 가능한 최선의 방법으로 합치면서, 이전에는 없었던 언어의 특징들(Python 3.6+ 타입 힌트)을 사용해서요.

</blockquote>

## Investigation

By using all the previous alternatives I had the chance to learn from all of them, take ideas, and combine them in the best way I could find for myself and the teams of developers I have worked with.

For example, it was clear that ideally it should be based on standard Python type hints.

Also, the best approach was to use already existing standards.

So, before even starting to code **FastAPI**, I spent several months studying the specs for OpenAPI, JSON Schema, OAuth2, etc. Understanding their relationship, overlap, and differences.

## 디자인

Then I spent some time designing the developer "API" I wanted to have as a user (as a developer using FastAPI).

I tested several ideas in the most popular Python editors: PyCharm, VS Code, Jedi based editors.

By the last <a href="https://www.jetbrains.com/research/python-developers-survey-2018/#development-tools" class="external-link" target="_blank">Python Developer Survey</a>, that covers about 80% of the users.

It means that **FastAPI** was specifically tested with the editors used by 80% of the Python developers. And as most of the other editors tend to work similarly, all its benefits should work for virtually all editors.

That way I could find the best ways to reduce code duplication as much as possible, to have completion everywhere, type and error checks, etc.

All in a way that provided the best development experience for all the developers.

## Requirements

After testing several alternatives, I decided that I was going to use <a href="https://pydantic-docs.helpmanual.io/" class="external-link" target="_blank">**Pydantic**</a> for its advantages.

Then I contributed to it, to make it fully compliant with JSON Schema, to support different ways to define constraint declarations, and to improve editor support (type checks, autocompletion) based on the tests in several editors.

During the development, I also contributed to <a href="https://www.starlette.io/" class="external-link" target="_blank">**Starlette**</a>, the other key requirement.

## Development

By the time I started creating **FastAPI** itself, most of the pieces were already in place, the design was defined, the requirements and tools were ready, and the knowledge about the standards and specifications was clear and fresh.

## 미래

이 시점에서, **FastAPI**와 그 아이디어들이 많은 사람들에게 유용하다는 것은 이미 명백합니다.

이전의 대안들을 넘어서 더 많은 사례들에 알맞게 선택받고 있습니다.

이미 많은 개발자들과 개발팀들이 프로젝트에 **FastAPI**를 쓰고 있습니다. (저와 제 팀을 포함해서)

하지만 여전히, 앞으로 다가올 개선점들과 기능들이 많이 있습니다.

**FastAPI**는 아주 유망합니다.

그리고 [도와주셔서](help-fastapi.md){.internal-link target=_blank} 대단히 감사합니다.
