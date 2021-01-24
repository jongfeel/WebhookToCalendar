# WebhookToCalendar

Github webhook event push to google calendar management web service

## Motivation

매주 온라인 모각코 issue를 생성한 후에 각 참여자가 self-assigned를 하는데 그 때마다 assignees를 보고 google calendar event에 assignees에 맞는 사용자를 추가하는 작업을 진행.

문제는 assignees가 할당 되었다는 알림을 볼 때 마다 그 assignee를 수동으로 google calendar에 추가해 주는데 자동으로 이걸 해주는 service가 있으면 좋겠다는 생각에 시작함.

## Requirements

## Analysis

### Studied pre-requirements

- github에 issue의 상태를 알 수 있는 REST API가 있음. 이걸 pulling해야 하나 할 때 쯤에 검색해 보니 github webhook도 있다는 걸 알게 됨
- .NET Core로 할 생각은 없었지만 github actions를 사용하고 싶은 생각이 많이 들었고 거기에 최적화 되어 있는 deploy가 azure를 쓸 때 적합하다는 걸 찾아냄
- 무엇보다도 cloud service 중에 한정된 기간 혹은 크레딧 소진 없이 서비스를 유지할 수 있는 cloud는 azure 뿐임 => azure web apps에는 F1 이라는 진짜 free tier가 있는데 일 60분의 CPU를 공유해서 쓸 수 있다.
- Google Calendar API 역시 .NET client를 지원하므로 어렵지 않게 구현 가능함.

## Design

## Skill keyword

- Github webhook
- .NET Core
- Github Actions
- Azure web apps with github actions
- Google Calendar API
- OAuth 2.0
