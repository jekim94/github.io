---
title: "Github Blog 시작하기!!"
categories:
  - GithubBlog
tags:
  - minimal mistakes
  - jekyll
  - blog
toc: true
toc_sticky: true
toc_label: "POSTING"
toc_icon: "blog"
---

❗️ **개발 환경** <br>
**OS** : M1<br>
**Tool** : Visual Studio Code<br>
{: .notice--info}

Github Blog 세팅 방법을 적어보려합니다 👏 <br>
<br>

# Github 레파지토리 생성하기
[Github](https://github.com/) (계정이 없다면 회원가입)

1. Repository 생성하기 <br>
- 우측 상단에 내 프로필 클릭 > *Your repositories* 클릭 > *New* 버튼 클릭 <br>
![image](https://user-images.githubusercontent.com/84657150/225246550-60c5e491-5c0b-4d23-a535-ab4d5de92671.png){: width="100%" height="80%"}
- 아래 이미지와 같이 입력한 후 *Create repository* 클릭!! <br>
![image](https://user-images.githubusercontent.com/84657150/225506287-9eabbd19-eb1d-4c6f-8c27-a232fbed842e.png){: width="100%" height="80%"}

2. 내 로컬 폴더에 생성한 레파지토리 연결하기 <br>
- HTTPS 주소 복사 <br>
![image](https://user-images.githubusercontent.com/84657150/225270929-82e81646-bcc7-4aae-8edf-d105a2f6fd18.png){: width="100%" height="80%"}
- 내 컴퓨터에 신규 폴더 생성 및 git 레파지토리 clone 하기 <br>
( 터미널을 켠 후 ```cd 로컬 폴더 주소``` > ```git clone 복사한 주소``` ) <br>
git config 관련해서는 무시하기 (특정 계정으로 연동 하고싶을 때 사용하는 것으로 자세한 부분은 여기로!!) <br>
![image](https://user-images.githubusercontent.com/84657150/225491967-fc20fe14-5620-4471-a840-da7a1efec8e0.png){: width="100%" height="80%"}
- 신규 파일 생성하기 <br>
( 터미널을 켠 후 ```cd 로컬 폴더 주소``` > ```echo "Hello GithubBlog" > index.html``` ) <br>
![image](https://user-images.githubusercontent.com/84657150/225496732-079b72d4-2582-4550-b0b4-be6516d012b6.png){: width="100%" height="80%"}
- 레파지토리에 최초 푸시하기 <br>
( 터미널을 켠 후 ```git add .``` > ```git commit -m "init"``` > ```git push -u origin main``` ) <br>
![image](https://user-images.githubusercontent.com/84657150/225502895-81710874-676e-4b59-a042-5db0ec269d6b.png){: width="100%" height="80%"}
<br>
<br>

# jekyll 테마 적용하기
[jekyll](http://jekyllthemes.org/) 사이트에서 마음에 드는 테마 선택하기!! <br>
내가 선택한 테마는 [minimal-mistakes](http://jekyllthemes.org/themes/minimal-mistakes/), Download 버튼을 눌러 소스 zip 파일을 내려받기 <br>

1. 압축 푼 후 해당 파일 삭제 <br>
![image](https://user-images.githubusercontent.com/84657150/225529132-225d0e10-d042-458a-a069-79256ac8d090.png){: width="100%" height="80%"}

2. docs 폴더 안에 해당 파일 상위로 이동 <br>
![image](https://user-images.githubusercontent.com/84657150/225529298-94cd10bd-76de-48e5-9651-2674ed696646.png){: width="100%" height="80%"}

3. docs 폴더 삭제 및 최종 파일 구조 <br>
( image 폴더 안에 내용은 모두 삭제해도 됨 )
![image](https://user-images.githubusercontent.com/84657150/225529957-9036bdc4-ffd6-4ddb-869e-ee06d8ae76d8.png){: width="100%" height="80%"}

4. Homebrew 로 rudy (rbenv) 설치 <br>
( 만약 설치가 안되어 있다면 [Homebrew](https://brew.sh/index_ko) 설치 ) <br>
- brew 통하여 rbenv 설치하기 및 **rbenv path를 추가** ( 중요 ) <br>
      ```bash
      # 설치
      brew update
      brew install rbenv  

      # 설치 확인
      rbenv versions

      # 설치된 ruby들이 나오고, 선택된 루비가 표시됨
      *system (set by /Users/yozi/.rbenv/version)
        3.1.2

      # 여기서 global ruby로 선택을 변경
      rbenv global 3.1.2

      # ~/.zshrc 편집
      vi ~/.zshrc

      # i 입력모드로 붙여넣은 후 :wq 저장하기
      [[ -d ~/.rbenv  ]] && \
        export PATH=${HOME}/.rbenv/bin:${PATH} && \
        eval "$(rbenv init -)"
        
      # 저장 이후 터미널에 명령어 입력
      source ~/.zshrc
      ```

5. bundle 명령어 실행 <br>
( 터미널을 켠 후 ```cd userName.github.io``` 경로로 이동 후 실행 ) <br>
    ```bash
    bundle install
    # 로컬 실행 
    bundle exec jekyll serve
    ```
아래와 같이 로컬 서버가 정상적으로 뜨면 성공 🙌 <br>
![image](https://user-images.githubusercontent.com/84657150/225548079-11a5bd3c-4b04-4995-b057-d666a1e7093f.png){: width="100%" height="80%"}

6. 소스 푸시하기!! <br>
( 터미널을 켠 후 ```cd userName.github.io``` 경로로 이동 후 실행 ) <br>
    ```bash
    git add . 
    git commit -m "테마적용"
    git push
    ```
<br>

# 참고 사이트
[왕초보를 위한 Github 블로그 만들기](https://zeddios.tistory.com/1222) <br>
[mac에서 ruby 설치하기](https://blog.yozi.kr/entry/mac%EC%97%90%EC%84%9C-ruby-%EC%9E%AC%EC%84%A4%EC%A0%95%EC%84%A4%EC%B9%98-%ED%95%98%EA%B8%B0-rbenv)<br>

테마 상세 수정은 다음편에서~