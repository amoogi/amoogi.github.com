## tar

여러개의 파일을 묶거나 푸는 명령어이다.
z 옵션을 사용하면 압축하거나 풀수도 있다.

### 옵션
- -c : tar를 생성할 때 사용한다. (여러 파일을 하나로 묶는다.)
- -r : tar에 다른 파일을 추가할 때 사용한다.
- -t : tar의 내용을 확인할때 사용한다.
- -++f : tar를 사용할때 반드시 사용한다.++
- -p : tar를 생성하거나 풀 때 퍼미션을 유지한다.
- -v : 묶거나 풀 때 로그를 보여준다.
- -x : tar를 풀 때 사용한다.
- -Z : compress로 압축이나 해제를 할 때 사용한다.
- -z : gzip으로 압축이나 해제를 할 때 사용한다.

### 사용예
```
# dirA 디렉토리의 모든 파일을 묶는 경우
tar cvf dirA.tar dirA

# dirA.tar의 내용을 확인할 경우
tar tvf dirA.tar

# dirA의 내용을 푸는 경우
tar xvf dirA.tar

# 묶음과 압축을 동시에 하는 경우
tar cvfz dirB.tar.gz dirB

# 묶고 압축된 파일 풀기
tar xvfz dirB.tar.gz

# dirC 디렉토리를 10M 단위로 나누어 압축하고 묶는 경우
tar cvfpz - dirC | split -b 10m - dirC.tar.gz

# 같은 용량 단위로 압축되어 묶인 파일을 해제하는 경우
cat dirC.tar.gz* | tar xvfpz -


```


