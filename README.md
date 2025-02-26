# test-git-flow

## Git-Flow 전략 개요
Git-flow에는 다섯가지 종류의 브랜치가 존재합니다. 항상 유지되는 메인 브랜치들(master, develop)과 일정 기간 동안만 유지되는 보조 브랜치들(feature, release, hotfix)이 있습니다.

- master : 제품으로 출시될 수 있는 브랜치
- develop : 다음 출시 버전을 개발하는 브랜치
- feature : 기능을 개발하는 브랜치
- release : 이번 출시 버전을 준비하는 브랜치
- hotfix : 출시 버전에서 발생한 버그를 수정하는 브랜치

Git-flow를 설명하는 그림  

![alt text](image.png)

1. master와 develop 브랜치가 존재.
2. `develop` 브랜치에는 상시로 버그를 수정한 커밋들을 추가
3. 새로운 기능 추가 작업이 있는 경우 `develop` 브랜치에서 feature 브랜치를 생성(feature 브랜치는 언제나 `develop` 브랜치에서부터 시작해서 기능 추가 작업이 완료되었다면 `develop` 브랜치로 merge)
4. `develop`에 이번 버전에 포함되는 모든 기능이 merge 되었다면 QA를 하기 위해 `develop` 브랜치에서 부터 release 브랜치를 생성
5. QA를 무사히 통과했다면 release 브랜치를 master와 `develop` 브랜치로 merge
6. 마지막으로 출시된 master 브랜치에서 버전 태그를 추가