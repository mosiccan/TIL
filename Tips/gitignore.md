# gitignore

## gitignore 파일이란?
- 프로젝트를 만들고 원격 저장소에서 관리되지 않아야 하는 파일들이나 원격 저장소에 올리지 말아야하는 파일들을 지정하여 원격 저장소에 올라가지 않도록 해주는 파일

## .gitignore 생성
- 위치 : .git 폴더가 위치한, 최상위 폴더에 생성 해주면 됩니다.
- 문서 편집기 등으로 작성하여 파일 형식을 `.gitignore` 로 지정 해줍니다.

## .gitignore 문법
- Glob 패턴을 사용합니다.
> 자주 사용되는 패턴들
>| 표시(와일드카드) | 설명      |
>| -------- | ------ | 
>| * | / 를 제외한 모든 문자열과 매칭 (문자열 길이 0이상)  |
>| ** | / 를 포함한 모든 문자열과 매칭 (문자열 길이 0이상) |    
>| ? | / 를 제외한 하나의 문자와 매칭 (빈 문자 X) |
>| [abc] | [ ] 안에 있는 모든 각각의 문자들과 매칭 |
>| {a,b,c} | { } 안에 있는 ,로 구분된 각각의 문자열들과 매칭 |
>| [^abc] | [ ] 안에 있는 모든 각각의 문자들을 제외한 문자들과 매칭 |
>| [a-z] | [ ] 안에서 - 사이에 있는 첫 문자와 마지막 문자의 범위에 있는 모든 문자들에 대해 매칭 |

## 작성 예시
```
# Compiled Dynamic libraries
*.so
*.dylib
*.dll
```

## 간단하게 자동으로 .gitignore 파일을 만들어주는 사이트
- https://www.toptal.com/developers/gitignore 
    - 여러 환경, 언어를 중첩하여 생성 가능합니다. 
    - C++에 해당하는 gitignore 파일 생성 결과
    ```
    
    # Created by https://www.toptal.com/developers/gitignore/api/c++
    # Edit at https://www.toptal.com/developers/gitignore?templates=c++

    ### C++ ###
    # Prerequisites
    *.d

    # Compiled Object files
    *.slo
    *.lo
    *.o
    *.obj

    # Precompiled Headers
    *.gch
    *.pch

    # Compiled Dynamic libraries
    *.so
    *.dylib
    *.dll

    # Fortran module files
    *.mod
    *.smod

    # Compiled Static libraries
    *.lai
    *.la
    *.a
    *.lib

    # Executables
    *.exe
    *.out
    *.app

    # End of https://www.toptal.com/developers/gitignore/api/c++
    ```
    
    + 2022/01/10 비주얼스튜디오 사용시 메인 언어 선택과 동시에 VisualStudio도 추가해주자.
    > C++만 추가했더니 VisualStudio 파일들도 같이 커밋되면서 용량이 커져 오류 발생!
