# Github 대용량 파일 push 실패 해결 방법



```
(error message : "RPC failed" & "fatal: The remote end hung up unexpectedly")
```



##### 1. POST 요청의 max buffer-size를 늘려준다.

* 참고링크

​      : https://j.mp/2PcS7uu

​      : https://j.mp/3bEzZkP

* git config --global http.postBuffer 157286400  (숫자는 직접 지정)

* 하나의 파일 용량이 지나치게 클 경우 1번을 적용해도 에러날 수도 있음



##### 2. Git LFS (Git Large File Storage)를 활용

* 참고링크

  : https://j.mp/37QJWdP (간단)



# Github 대용량 파일 push 실패 해결 방법



```
(error message : "RPC failed" & "fatal: The remote end hung up unexpectedly")
```



##### 1. POST 요청의 max buffer-size를 늘려준다.

* 참고링크

​      : https://j.mp/2PcS7uu

​      : https://j.mp/3bEzZkP

* git config --global http.postBuffer 157286400  (숫자는 직접 지정)

* 하나의 파일 용량이 지나치게 클 경우 1번을 적용해도 에러날 수도 있음



##### 2. Git LFS (Git Large File Storage)를 활용

* 참고링크

  : https://j.mp/37QJWdP (간단)
  
  : https://j.mp/3uw7PAV (상세)
  
  : https://velog.io/@luvlik207/github%EC%97%90-%EB%8C%80%EC%9A%A9%EB%9F%89-%ED%8C%8C%EC%9D%BC-%EC%97%85%EB%A1%9C%EB%93%9C%ED%95%98%EA%B8%B0 (실질적으로 도움을 받은 유용한 사이트)
  
  </br>
  
* 진행 순서
1. git LFS 설치 : https://git-lfs.com/
2. git bash 열고 추가된 대용량 파일이 있는 로컬 디렉터리로 이동
```
git lfs install
```
```
git lfs track "파일명"
```
```
git pull origin main
git add *   <- 변경 파일 추가
git commit -m "commit 메시지 작성"
git push -u origin main 
```
> 각 파일의 용량이 지나치게 커서 한번에 모든 파일들을 추가하지 못할 경우 , 각각의 파일을 하나씩 tracking 하여 추가하는 방법으로 진행함.

> 너무나 당연한 얘기지만
>
> 1. 깃허브에 repository를 미리 생성한 후, 생성한 repository에 파일 및 폴더 업로드
> 2. 추가될 대용량 파일(들)을 해당 repository에 add 해야 함.

