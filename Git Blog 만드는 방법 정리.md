# Git Blog 만드는 방법 정리

```참고
Git blog는 Jekyll과 Github를 이용하여 만듦
선택하고 실제로 적용한 jekyll 테마 위주로 작성함 (jekyll 테마 적용 시 테마에 따라 Github 빌드에 문제가 생길 수 있음)
참고 사이트 1: https://supermemi.tistory.com/144
참고 사이트 2: https://velog.io/@neori/Jekyll-TeXt-Theme%EB%A1%9C-GitHub-%EB%B8%94%EB%A1%9C%EA%B7%B8-%EA%B0%9C%EB%B0%9C%ED%95%98%EA%B8%B0
```
</br>

## Repository 생성

### 1. Git Blog를 만들기 위해서는 먼저 새로운 Repository를 생성해야 함.
* `{username}.github.io`로 Repository 생성해야 함.

* 예시) Github username이 cloudnine-mj이면  cloudnine-mj.github.io로 Git Blog Repository를 생성해야 함.

  </br>

## Git Blog 생성

### 1. Git Bash를 이용하여 로컬에 새폴더 생성
* 새폴더 명은 git_blog로 함.

```bash
$ mkdir git_blog
```

### 2. 새로 만든 로컬의 git_blog 폴더로 이동한 후 `git clone` 명령어 실행

```bash
$ cd git_blog
$ git clone {Git Blog Repository HTTPS 주소}
```
* `{Git Blog Repository HTTPS 주소}` 는 아래 이미지 참고

![repository](https://user-images.githubusercontent.com/113915835/221565934-6ace75bf-f8ae-47fc-ba8a-da0c876de184.png)

### 3. `git clone` 한 폴더에서 간단한 파일 생성하기

```bash
$ cd {Git Blog Repository 명}
$ echo "Hello World" > index.html
```

### 4. 생성한 index.html 파일을 Github로 Push 하기
```bash
$ git add *
$ git commit -m "커밋메시지" # "커밋메시지"는 "start git blog"로 하여 생성함
$ git push -u origin main
```
* ` https://{Git Blog Repository 명}` 으로 접속하여 정상적으로 홈페이지가 생성되었는 지 확인

</br>



## jekyll 설치 후 jekyll 로컬 서버에 띄우기
```
Git Blog 꾸밀 때 jekyll을 사용함.
```

### 1. jekyll 다운 받기

* git clone 한 폴더에서 jekyll을 다운받아야 함.

```bash
$ gem install bundler
$ gem install jekyll
```
### 2. 이전에 만들었던 index.html 파일 삭제하기
```bash
$ rm -f index.html
```

### 3. 명령어 실행

* 다음과 같이 root 디렉터리에 저장해야 함.

```bash
$ jekyll new ./
```

### 4. bundle 설치
```bash
$ bundle install
```

### 5. jekyll을 로컬 서버에 띄우기

```bash
$ bundle exec jekyll serve
```
* `http://127.0.0.1:4000/` 을 새 브라우저에 입력한 후 제대로 적용되었는지 확인


### 6. Github로 Push 하기
```bash
$ git add *
$ git commit -m "커밋메시지" # "커밋메시지"는 "jekyll start"로 하여 생성함
$ git push -u origin main
```
*  `https://{Git Blog Repository 명}` 으로 접속하여 정상적으로 변경되었는지 확인

</br>


## Git Blog에 원하는 jekyll 테마 적용하기

* https://kitian616.github.io/jekyll-TeXt-theme/docs/en/quick-start 에서 jekyll 테마 다운로드 

### 1. 로컬에 새폴더 생성
```bash
$ cd ..
$ cd ..
$ mkdir blog
```
### 2. 생성한 새폴더로 이동
```bash
$ cd blog
```
### 3. 생성한 Git Blog Github Repository 연결
```bash
$ git init
$ git remote add origin {Git Blog Repository HTTPS 주소}
```

### 4. Repository에 있는 데이터를 blog 폴더에 내려받기
```bash
$ git pull origin main
```
* blog 폴더에 내려받은 후 .git 폴더를 제외한 나머지 파일들은 전부 삭제

### 5. 명령어 실행
* blog 폴더에서 아래의 명령어 실행
```bash
$ jekyll new ./
```

### 6. 다운받은 jekyll 테마 파일(압축파일)을 blog 폴더에 압축 풀기
* 겹치는 파일이 있는 경우 모두 새로운 파일로 replace(대체)함
* 다음 단계에서 발생할 수 있는 conflict(충돌)을 방지하기 위해 404.html, about.markdown, index.markdown 세 개의 파일을 삭제하는 게 좋음

### 7. bundle 설치 후 로컬 서버에 띄우기
```bash
$ bundle install
$ bundle exec jekyll serve
```
* `http://127.0.0.1:4000/` 을 새 브라우저에 입력한 후 jekyll 테마가 제대로 적용되었는지 확인

### 8. Github로 Push 하기
```bash
$ git add *
$ git commit -m "커밋메시지" # "커밋메시지"는 "change theme"로 하여 생성함
$ git push -u origin main
```
*  `https://{Git Blog Repository 명}` 으로 접속하여 정상적으로 변경되었는지 확인