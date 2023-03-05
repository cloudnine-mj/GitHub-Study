# Github 이미지 크기 조절 방법

> 실제로 가장 많이 사용하는 방법으로 이미지 크기 조절 방법 작성함. 
>
> (추후 이미지 크기 조절 방법 추가 예정)

<br/>

### 1. Github issue에 이미지를 끌어다 놓기

* Github issue에 이미지를 끌어다 놓으면 다음과 같은 URL이 자동 생성됨

  ```
  ![파일이름](cloud.githubusercontent.com에 업로드 된 URL)
  
  # <img src="https://user-images.githubusercontent.com/113915835/222959803-8e896c29-75f5-48c2-9f05-295d85db7588.png">
  ```



### 2. 이미지 크기 조절하기

```
<img src="cloud.githubcontents.com에 업로드 된 URL" width="">

# <img src="https://user-images.githubusercontent.com/113915835/222959803-8e896c29-75f5-48c2-9f05-295d85db7588.png" width="60%">
```

* width의 default 값은 100%  (원본 이미지 사이즈)
* 크기 조절 시 width에 원하는 `숫자%`를 넣으면 됨        ex) 60%