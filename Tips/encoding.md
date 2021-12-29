# Encoding

## 인코딩 관련
각종 IDE나 프로그램 도구들을 사용할 때 인코딩 문제로 한글이 깨지는 경우가 있습니다.  
한글의 경우 대표적으로 UTF-8, euc-kr, CP949 방식으로 인코딩 되는데 각 방식간의 호환이 제대로 이루어지지 않아 글자 깨짐이 발생합니다. 

## 문제 발생
GUI를 사용하여 직관적이고 편리하게 버전 관리를 할 수 있어 소스트리를 사용중입니다.  
지금까지 과제나 기타 코드들을 소스트리를 이용하여 버전 관리를 해왔는데 TIL을 진행중 소스트리로 커밋되는 결과를 보니 한글이 깨져나오는 오류가 있었습니다.  

## 조건 분석
- CP949를 기본 인코딩 방식으로 사용하는 VisualStudio
- 웹상(깃허브 내 수정)에서 md파일은 UTF-8 방식으로 인코딩됨
- VSCode와 소스트리는는 인코딩 방식을 지정할 수 있음 (UTF-8과 euc-kr(CP949))

## 해결 방안
- VisualStudio의 모든 파일을 UTF-8로 지정해준다. (그렇다해도 기존의 커밋 기록내 한글은 깨짐)
	- 이를 위해 기존의 CP949 인코딩 방식으로 저장되던 파일들을 UTF-8로 바꿔줘야함
- 결론적으론 UTF-8로 통일하는게 가장 베스트!

## 1차 적용 방식
- 소스트리 "도구-옵션-기본 텍스트 인코딩"을 UTF-8로 지정
- 소스트리의 c++ 관련 리포지토리의 config 파일에 아래 코드를 추가
```
[i18n]
	logOutputEncoding = UTF-8
	commitEncoding = UTF-8
```
- VisualStudio에 "Force UTF (No BOM)"을 설치

## 결과
- 기존의 커밋 내역들은 깨지지만 앞으로 커밋할 파일들을 모두 정상으로 나옵니다.

## 다시 오류
TIL의 md파일 리포지토리에서 다시 깨짐 현상이 일어났습니다.  
- 다시 euc-kr로 바꾼 후 VSCode에선 setting에서 Auto Guess Encoding을 활성화하여 VSCode내에서 깨짐 현상을 없앴습니다.
- 하지만 깃허브 내 편집기로 수정 시 아래와 같은 경고 문구가 뜹니다.
- "We’ve detected the file encoding as EUC-KR. When you commit changes we will transcode it to UTF-8."
- 역시 소스트리에서 pull을 해보니 깃허브 내에서 수정한 부분은 한글이 깨집니다.
- 결론은 어떻게든 utf-8로 통일을 시켜야합니다.

## 최종 결과 및 세팅
+ 최종 결과
	+ 기존의 cpp 및 헤더파일 들의 SourceTree 내의 History는 한글이 깨짐 
	+ 새로 커밋하는 것들 부터는 잘 나타남
	+ md 파일들도 잘 나옴
	+ 깃허브 내 편집기에서도 앞전의 경고 문구 안뜸
+ 세팅
	+ SourceTree
		+ 언어 : 한국어
		+ 기본 텍스트 인코딩 : UTF-8
		+ cpp 파일 위주 리포지토리 config 파일에 추가한 항목
		```
		[i18n]
			logOutputEncoding = UTF-8
			commitEncoding = UTF-8
		```
		+ md 파일 위주 리포지토리 config 파일에 추가한 항목
		```
		[i18n]
			logOutputEncoding = UTF-8
			commitEncoding = UTF-8
		```
	+ VSCode
		+ Encodig : UTF-8
	+ VisualStudio 
		+ 기본 세팅
		+ 확장 프로그램 [**Force UTF-8(No BOM)**](https://marketplace.visualstudio.com/items?itemName=1ndrew100.forceUTF8NoBOM) 설치 

## 참고자료
- [[Sourcetree] History 한글 깨짐 현상 수정](https://smoh.tistory.com/346)
- [한글 인코딩의 이해 1편: 한글 인코딩의 역사와 유니코드](https://d2.naver.com/helloworld/19187)
