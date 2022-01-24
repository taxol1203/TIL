# 목차

[Error in opening zip file](#Error-in-opening-zip-file)

## Error in opening zip file

jar가 깨진지 확인하는 방법

bash 에서 다음 문장을 통해 확인한다.

아래 /paht/to/lib 를 자신의 경로로 지정한다.

```jsx
for j in $(find /path/to/lib -name '*.jar'); do jar -tvf $j > /dev/null 2>&1; [ "$?" -ne 0 ] && echo "$j jar is broken"; done
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7f9226c6-9884-4958-ba9d-74fadc7472fe/Untitled.png)

나는 해당 jar 파일이 있는 디렉토리에서 bash 켜서 확인함

아무것도 안나온것을 보아, 깨진 jar는 없다.
