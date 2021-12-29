# SourceTree

## 소스트리
(2021/12/29) 지금까지는 소스트리 사용시 다시 이전 문서로 되돌리고 싶을 때 그냥 문서 내에서 해당 부분을 지우고 다시 커밋을 반복하였습니다.  
최근들어 효율성 등을 생각해보니 너무나 불필요한 커밋들의 낭비가 아닌가 싶었습니다.  
생활코딩님의 git 시리즈를 정주행 하며 개념을 다시 정리하고자 하였습니다.

## reset
- 이 커밋까지 현재 브랜치를 초기화
- (Reset current branch to this commit)  
리셋을 하면 이전 커밋 내역으로 완전히 다시 돌아갈 수 있습니다.  
옵션에서 Hard를 선택하여 수정하던 기록들도 다 지우고 원하는 버전으로 돌아갈 수 있습니다.
- 협업 시 특히 회계 분야에서는 이러한 뒤로가기가 문제가 될 수 있으므로 reset하지 않고 실수는 그대로 남겨둔 채 바꿀 수 있게끔 합니다.  
ex)
| A | B | C |  
|---|---|---|  
|회식|50000| |  
|사무용품|100000| |   