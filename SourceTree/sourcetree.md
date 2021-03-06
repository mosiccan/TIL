# SourceTree
> TBU
> *상황별 이미지 설명을 추가할 예정입니다.  

## 목차
- 개요
- reset
- revert
  
## 개요
리눅스를 배우기 전, CLI에 익숙하지 않았을 때 깃허브를 접하게 되었습니다.  
그러면서 커밋을 하는 방법이나 기록을 하기 위한 도구로 더 직관적인 건 없을까 하고 접했던 것이 바로 소스트리 입니다.  
(2021/12/29) 지금까지는 소스트리를 사용하며 다시 이전 문서로 되돌리고 싶을 때 그냥 문서 내에서 해당 부분을 지우고 다시 커밋을 반복하였습니다.  
효율성 등을 생각해보니 너무나 불필요한 커밋들의 낭비가 아닌가 싶었습니다.  
<u>생활코딩님의 GIT SourceTree 시리즈</u>를 정주행 하며 필요한 부분 개념을 다시 정리하고자 하였습니다!

- [GIT2 - SourceTree 버전관리편](https://www.youtube.com/watch?v=VeQDmXjbHtQ&list=PLuHgQVnccGMCejd1l8C8oyZSYQDtkMRAg)
- [GIT3 - SourceTree 브랜치 & 충돌](https://www.youtube.com/watch?v=FB1se6hEYx8&list=PLuHgQVnccGMCWlMygyYg9XjCIjESUbW4b)
- [GIT4 - SourceTree 협업](https://www.youtube.com/watch?v=v8niKCVmUXs&list=PLuHgQVnccGMCeAdpRidv18VRVS8mqzFdS)

## reset
- 이 커밋까지 현재 브랜치를 초기화
- (Reset current branch to this commit)  
리셋을 하면 이전 커밋 내역으로 완전히 다시 돌아갈 수 있습니다.  
옵션에서 Hard를 선택하여 수정하던 기록들도 다 지우고 원하는 버전으로 돌아갈 수 있습니다.

## revert
- 협업 시 특히 회계 분야에서는 이러한 뒤로가기가 문제가 될 수 있으므로 reset하지 않고 실수는 그대로 남겨둔 채 바꿀 수 있게끔 합니다.  

> ex) '회식' 을 잘못 입력했을 때  
>| A        | B      | C   |
>| -------- | ------ | ---- |
>| <u>회식     | <u>50000  |     |
>| 사무용품 | 100000 |  
  
> 수정
>| A        | B      | C   |
>| -------- | ------ | --- |
>| 회식     | 50000  |     |
>| 사무용품 | 100000 |
>| <u>**회식** | <u>**-50000** | 1번 항목 실수 |
- revert는 "사용자가 지정한 그 파일"에서 변경된 사항을 되돌리겠다는 의미 입니다.
- 소스트리에서는 실수한 파일을 **Reverse commit** 하면(Git에선 revert)  
  현재 실수한 파일의 커밋기록은 남고 실제 파일은 실수 직전의 파일로 되돌아 갑니다.
- revert를 한 후 더 이전의 기록으로 돌아가려면 한단계씩 원하는 커밋 기록까지 Reverse commit을 해줘야 합니다.  
revert를 한 후 여러 단계를 바로 건너뛰게 되면 충돌이 발생합니다.   
앞선 의미에 따라 여러 단계를 바로 건너뛰게 된다면 현재 파일과 돌아가고자 하는 파일의 변경지점이 달라지기 때문입니다.

## 시간여행
- 원하는 버전으로 잠시 돌아가려면 원하는 커밋 내역을 더블 클릭 하여 돌아갑니다.
- 그리고 다시 최신 버전으로 돌아오려면 리스트 상단에 있는 커밋 기록을 누르지 않고 왼쪽 BRANCHES에 있는 `main`을 더블 클릭 하여 돌아갑니다.