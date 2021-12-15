# Dependency , Devdependency 차이점 

## dependencies 
애플리케이션 동작과 연관된 라이브러리 설치.

## devDependencies 
애플리케이션 동작과 직접적인 연관은 없지만, 이름 그대로 로컬 개발 및 테스트에 필요한 라이브러리를 설치.(개발자가 필요 한 것)

즉, 어떤 라이브러리가 프로젝트의 컴파일(빌드) 타임에 필요하면 devDependencies에 넣고, 런타임에도 계속 쓰이는 것이면 dependencies에 넣어야 함.

## 왜 구분?
결국 배포할 때 어떤 라이브러리가 포함되냐의 문제! 
dependencies 에 설치된 라이브러리는 배포할 때 포함되지만
devDependencies 에 설치된 라이브러리는 개발할 때 필요한 라이브러리기 때문에 배포할 때 포함되지는 않음.
이렇게 잘 구분을 해서 설치해줘야 빌드시간도 줄이고, 배포할 때 불필요한 라이브러리를 포함시키지 않아도 됨.

[참고](https://imkh.dev/dependencies-package-json)  
[참고](https://www.codeit.kr/community/threads/29051)