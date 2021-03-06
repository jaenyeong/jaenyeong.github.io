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
~~~
> gem install bundler
> bundle update
> bundle install
> bundle exec jekyll serve
~~~

### ruby(rbenv) 설치 실행시 에러 발생한 경우
~~~
> brew update && brew upgrade
> brew install rbenv ruby-build
> brew uninstall binutils
> rbenv install 2.6.6 && rbenv local 2.6.6 ;
> vim ~/.zshrc
    [[ -d ~/.rbenv  ]] && \
    export PATH=${HOME}/.rbenv/bin:${PATH} && \
    eval "$(rbenv init -)"
> source ~/.zshrc
~~~

## 설정

### 게시물 변경 일자 설정
* include page__meta.html 주석 처리
* _includes/archive-single.html 파일에 post.date 추가
* _layouts/single.html 파일에 page.date 추가

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
