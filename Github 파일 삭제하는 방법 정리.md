# Github 파일 삭제하기

1. 로컬 디렉터리와 Git 저장소에서 모두 삭제
2. 로컬 디렉터리에서는 파일 유지, Git 저장소에서만 삭제

```참고
파일 삭제 후 `commit`을 해야 함.
```
</br>

### 1. 로컬 디렉터리와 Git 저장소에서 모두 삭제

```bash
git rm {filename}
git commit -m "커밋메시지" # 커밋메시지는 삭제 시점의 커밋을 작성해주면 좋음
```

* 예시)

```bash
git rm 2023-02-28-hello.md
git commit -m "delete test post"  
```
</br>

### 2. 로컬 디렉터리에서는 파일 유지, Git 저장소에서만 삭제

* `git rm --cached` 명령어를 사용

```bash
git rm --cached {filename}
git commit -m "커밋메시지"  # 커밋메시지는 삭제 시점의 커밋을 작성해주면 좋음
```
* 예시)

```bash
git rm --cached 2023-02-28-hello.md
git commit -m "delete test post" 
```
