# [jaenyeong.github.io](https://jaenyeong.github.io)

## 실행 순서

### 불필요한 파일 삭제
* .editorconfig
* .gitattributes
* .travis.yml
* .github
* /docs
* /test
* CHANGELOG.md
* minimal-mistakes-jekyll.gemspec
* README.md
* screenshot-layouts.png
* screenshot.png

### 디렉토리 생성
* _drafts
  * 테스트 게시물 작성 위치 (배포되지 않음)
* _posts
  * 게시물 작성 위치

### 실행 설정
~~~console
# bundler 설치, 업데이트
gem install bundler

# 번들 설치 및 업데이트
bundle install
bundle update
~~~

### 실행

```console
bundle exec jekyll serve

# 실행 시 webric 에러 발생
bundler: failed to load command: jekyll (/Users/jaenyeong/.rbenv/versions/3.1.2/bin/jekyll)
/Users/jaenyeong/.rbenv/versions/3.1.2/lib/ruby/gems/3.1.0/gems/jekyll-3.9.0/lib/jekyll/commands/serve/servlet.rb:3:in `require': cannot load such file -- webrick (LoadError)

# webric은 간단한 HTTP 서버를 제공하는 루비 라이브러리
# 아래 명령을 실행하여 webrick 추가
bundle add webrick
```

### 접속
* [메인 페이지](http://127.0.0.1:4000)
  * 브라우저에서 [이력서](http://127.0.0.1:4000/about/)

### ruby(rbenv) 설치 실행시 에러 발생한 경우
~~~
> # brew 패키지 최신화
> brew update && brew upgrade
> 
> # 루비 관리 패키지 rbenv 설치
> brew install rbenv ruby-build
>
> # rbenv 설치 가능한 목록(버전) 확인
> rbenv install -l
>
> # GNU 바이너리 유틸리티 제거
> brew uninstall binutils
>
> # rbenv 패키지를 통해 최신(지정) 루비 버전 설치
> # 실패 (BUILD FAILED (macOS 12.6 using ruby-build 20220910.1))
> rbenv install 3.1.2 && rbenv local 3.1.2
>
> # zshrc에 rbenv 설정 추가
> vim ~/.zshrc
> 
> [[ -d ~/.rbenv  ]] && \
> export PATH=${HOME}/.rbenv/bin:${PATH} && \
> eval "$(rbenv init -)"
> 
> source ~/.zshrc
~~~

## 설정

### 게시물 변경 일자 설정
* include page__meta.html 주석 처리
* _includes/archive-single.html 파일에 post.date 추가
* _layouts/single.html 파일에 page.date 추가
  
### 테마 변경
[테마 변경](_config.yml)

### 띄어쓰기
공백이 필요한 경우 중간에 `<br/>` 삽입

## 참조
* jekyll 문서
  * https://jekyllrb.com/
* Minimal-Mistakes 테마 문서
  * https://mmistakes.github.io/minimal-mistakes/
* 깃허브 블로그 만들기
  * https://khw11044.github.io/githubpages/
* jekyll Minimal-Mistakes 테마 블로그 만들기
  * https://devinlife.com/howto/
  * https://honbabzone.com/jekyll/start-gitHubBlog/
* jekyll Minimal-Mistakes 테마 구조
  * https://ansohxxn.github.io/blog/jekyll-directory-structure/
* ruby(rbenv) 설치 실행시 에러 발생한 경우
  * https://stackoverflow.com/questions/59483699/ruby-2-6-0-installation-fails-on-macos-with-rbenv
