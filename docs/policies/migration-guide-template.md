# 이전 패키지에서 새 패키지로 이동하기 위한 안내서

이 안내서는 이전 패키지에서 새 패키지로 이동하는 데 도움을 주기 위한 것입니다. 두 패키지 간의 유사한 작업에 대한 병렬 비교에 초점을 맞출
것이다.

우리는 당신이 오래된 패키지를 잘 알고 있을 것이라고 생각합니다. 그렇지 않은 경우 본 가이드가 아닌 README에 패키지 이름을 링크 텍스트로
사용하여 여기에 있는 새 패키지 링크를 참조하십시오.

## 목차

## Migration 이점

Azure가 성숙해지고 더 다양한 개발자 그룹에 수용됨에 따라, 우리는 개발자 생산성을 최상으로 지원하고
(NET/JavaScript/Python/Java) 언어의 차이를 이해하기 위한 패턴과 관행을 배우는 데 초점을 맞추고 있다.

Azure 클라이언트 라이브러리 생태계 전반에 걸쳐 일관된 피드백을 제공하는 몇 가지 영역이 있었습니다. 가장 중요한 것 중 하나는 서로 다른
Azure 서비스를 위한 클라이언트 라이브러리가 조직, 명명 및 API 구조에 일관된 접근 방식을 가지고 있지 않다는 것입니다. 또한 많은
개발자들은 학습 곡선이 어렵다고 느꼈으며, API는 Azure를 학습하거나 특정 Azure 서비스를 탐색하는 사람들에게 좋고, 접근 가능하며,
일관된 온보딩 스토리를 제공하지 않았다.

Azure 서비스 전반에 걸쳐 개발 경험을 개선하기 위해 모든 언어에 대해 모든 서비스에 대해 설정된 API 패턴으로 일관된 경험을 제공할 수
있는 일련의 통일된 [디자인 가이드라인](https://azure.github.io/azure-sdk/general_introduction.html))이
만들어졌습니다. Java 지침과 같은 링크 텍스트를 사용하여 언어 별 지침에 링크를 추가하는 것 또한 특정 언어 클라이언트가 특정 언어 생태계와
관련하여 자연스럽고 관용적인 느낌을 갖도록 하기 위해 도입되었습니다. 새 패키지 이름은 다음 지침을 따릅니다.

### 서비스 간 SDK 개선

최신 서비스의 클라이언트 라이브러리는 다음과 같은 Azure 개발 경험에 대한 교차 서비스 개선 사항을 공유할 수 있는 기능도 제공합니다

- 새 사용자 언어로 ID 패키지 이름 추가 라이브러리를 사용하여 클라이언트 간에 단일 인증 접근 방식 공유
- 각 클라이언트 라이브러리의 활동에 대한 공통 보기를 제공하는 통합 로깅 및 진단 파이프라인
- JS에 대해서만 줄을 추가하여 단순화된 프로그래밍 경험을 위한 콜백보다 약속 사용
- JS에 대해서만 줄 추가하여 호출 API에서 비동기 사용
- Java에 대해서만 행 추가하여 Project Reactor(https://projectreactor.io/)를 사용하는 통합 비동기
프로그래밍 모델입니다.
- Java 전용으로 줄 추가한 빌더를 통해 클라이언트를 만드는 통합된 방법입니다.

### Performance improvements

Use this section to advertise the performance improvements in new package when
compared to the old one. Skip this section if no perf improvements are found
yet.

### New features

Use this section to advertise any new features in the new package when compared
to the old one. Skip this section if no new features were added

## Important changes

### Package names and namespaces

Note: This section is always applicable for .NET and Java, while being
occasionally applicable to JavaScript and Python where we tend to re-use the old
package name where possible. The concept of namespace does not apply to
JavaScript, we use the "@azure" scope instead. Remove this section if not
needed. Below example text is for .NET Event Hubs, tweak as needed.

Package names and the namespace root for the modern Azure client libraries for
.NET have changed. Each will follow the pattern Azure.[Area].[Service] where the
legacy clients followed the pattern Microsoft.Azure.[Service]. This provides a
quick and accessible means to help understand, at a glance, whether you are
using the modern or legacy clients.

In the case of Event Hubs, the modern client libraries have packages and
namespaces that begin with Azure.Messaging.EventHubs and were released beginning
with version 5. The legacy client libraries have packages and namespaces that
begin with Microsoft.Azure.EventHubs and a version of 4.x.x or below.

### Client hierarchy and constructors

If there has been no change other than naming) in client hierarchy or entry
level classes, skip "hierarchy" from the header, otherwise talkabout why the
client hierarchy was changed. Compare code snippets for the client constructors
between the old and new packages, while pointing out differences and the reason
behind them.

### Champion scenario 1

Repeat this section for the common high level usage scenarios for this library.
Show how you would accomplish these both in the old and new packages, pointing
out the key differences, reasons and advantages.

## Additional samples

More examples can be found at (Add link to samples here with link text Samples
for new package name)
