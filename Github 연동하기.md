# Github 연동하기

1. 컴퓨터 내에 프로젝트 폴더 만들기

2. 프로젝트 폴더 내에 Github에 연동시킬 파일 올리기

3. cmd 창에 접속하여 프로젝트 폴더에 접속하기

   ```
   cd 프로젝트 폴더명
   ```

4. Github에 로그인한 후, repository에서 new버튼을 누르고 새 repository 설정

5. git 명령어로 Github에 연동하기

   ```
   git init
   git add .
   git status   #확인용이므로 굳이 안해도 됨
   git commit -m "____________"   #처음 올릴때는 first commit 이나 initial commit으로 할 수 있음
   git remote add origin [Github repository 주소]
   git push origin main
   ```



#### 이전 단계로 돌아가기

```
git reset --hard 커밋코드
```

* git log 후, 원하는 단계의 commit의 해시코드를 복사 붙여넣기

  

#### 서버(Github)에서 로컬(내컴퓨터)로 가져오기

```
git clone repository Github 주소 
```

* Github repository 주소는 Github repository 클릭 후 "code" 버튼을 누른 뒤 복사 버튼 누르면 된다.



```
git pull origin main
```

* Github에 새로운 파일을 올렸으나 로컬(내컴퓨터)에 없는 경우pull 명령어를 사용하여 당겨온다.



#### Reset 명령어 수행 후 다시 특정단계로 돌아가기

```
git reset --hard 깃허브 내 원하는 단계의 commit 코드 복사 
```



