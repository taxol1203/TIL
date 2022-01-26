# 목차

[Maven이란?](#Maven이란?)  
[Error in opening zip file](#Error-in-opening-zip-file)  

## Maven이란?

> 프로젝트를 **빌드**하고 라이브러리를 **관리**해주는 도구입니다.

### 왜 사용??

장점 1)

개발자들이 하나의 프로젝트를 편하게 서로 같이 협력하면서 일을 할 수 있도록 도와준다.

```
프로젝트를 진행하는데 라이브러리를 사용합니다. 
만약 사용하는 라이브러리 수가 몇개 안된다면 그냥 외부 jar를 추가해서 사용하면 되지만... 
프로젝트의 규모가 커질수록 라이브러리의 관리가 어려워집니다. 

모두 같은 환경에서 개발을 해야하는데 카톡이나 메일로 라이브러리를 보내주면서 
게속 import 시켜주는 비효율적인 행위보다는 
**pom.xml만 공유**하는게 훨씬 효율적
```

장점 2)

라이브러리의 하위 라이브러리까지 버전에 맞게 받아준다.

→ depedency에 작성한 라이브러리를 사용하기 위해 다른 라이브러리도 필요하다면
    알아서 같이 설치

## Maven Life-cycle

> 메이븐이 프로젝트를 빌드 할 때의 순서, 생명 주기

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9f8a3aa6-3229-4505-8cba-f34fa9596b42/Untitled.png)

각 단계(네모)는 phase를 뜻한다.

maven은 나중 단계의 phase를 실행 시켰다면 이전 단계가 모두 실행 되어진다.

"mvn install"이라는 명령을 내리면 compile 부터 install 단계까지 모두 실행이 된다.

### Compile

**명령 : mvn compile**

소스코드를 컴파일해주는 단계입니다. 성공적으로 컴파일이 된다면 target/classes폴더가 만들어지고 컴파일된 class파일이 생성된다.

### Test

**명령 : mvn test**

테스트 코드를 실행해주는 단계입니다. 실패하면 빌드가 멈춥니다. 이 단계에서 target/test-classes폴더와 안에 컴파일된 class파일이 생성되고 target/surefire-reports 폴더에 테스트 결과가 기록됩니다.

### Package

**명령 : mvn package**

**소스 코드를 컴파일하고 패키지한다**

해당 프로젝트를 지정한 확장자로 묶어주는 단계입니다. 확장자 타입은 pom.xml에 packaging 태그로 묶이게 되고 ( 예를들어 .jar)

"artifactId-version.packaging"형태의 파일을 target폴더안에 생성해줍니다. ( 000.jar)

만약 pom.xml에 jar파일로 패키지하라고 하면,

패키징할때 jar파일로 만들고 타겟 디렉토리에 만든다.

### install

**명령 : mvn install**

로컬 리포지토리 즉 Maven이 설치되어 있는 PC에 배포하게 됩니다.

### deploy

**명령 : mvn deploy**

원격 리포지토리가 등록되어 있다면 해당 원격 리포지토리에 배포하게 됩니다.

### Clean 라이프사이클

**명령 : mvn clean**

생성된 target 폴더를 삭제해버립니다.

### Site 라이프사이클

문서 사이트를 생성할 수 있도록 지원합니다.

## Trouble Issue

### error in opening zip file

jar가 깨진지 확인하는 방법

bash 에서 다음 문장을 통해 확인한다.

아래 /paht/to/lib 를 자신의 경로로 지정한다.

```jsx
for j in $(find /path/to/lib -name '*.jar'); do jar -tvf $j > /dev/null 2>&1; [ "$?" -ne 0 ] && echo "$j jar is broken"; done
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7f9226c6-9884-4958-ba9d-74fadc7472fe/Untitled.png)

나는 해당 jar 파일이 있는 디렉토리에서 bash 켜서 확인함

아무것도 안나온것을 보아, 깨진 jar는 없다.
