---
layout: post
title: R(MARKDOWN)+RSTUDIO+GITHUB 사용하기
---

이번에는, R Markdown 뿐만이 아닌 R Code를 손쉽게 Github에 올리고 공유하는 내용에 대해서 잠깐 정리해 볼까 한다.

GitHub은 소셜 기반의 버전 관리 시스템이다. 버전 관리 시스템의 개념과 역사(?)에 대해서만 설명해도 몇 개의 페이지가 나올 것 같으니 이에 대해 자세한 설명은 생략한다. GitHub에 대한 매뉴얼이나 문서는 구글링만 해도 쏟아져 나오고, 서점에는 잘 정리된 책들이 몇 권 나와있다. 혹은 급하신 분들은 일단 [여기를](https://github.com/progit/progit/blob/master/ko/01-introduction/01-chapter1.markdown) 활용해도 될 것이다.

Git 및 GitHub은 굉장히 유용하게 활용할 수 있으나 버전 관리 시스템을 사용했던 사람들이라도 개념 및 사용법이 익숙해지기까지 초반의 적응 기간이 좀 필요하다. 더우기 이를 사용한 경험이 없는 분들은 Git에 익숙해지는 데도 한참이 걸릴 것이다.(괜히 책까지 나와있는 것이 아니다.) 하지만 많은 R 라이브러리 및 문서들이 GitHub 을 통해 공유되고 있으므로, 이를 쉽게 사용할 수 있다면 매우 편리할 것이다.

R을 사용하는 사람들이 가장 많이 사용하는 IDE로 추측되는 RStudio에서 R로 코드 작성을 한 후, 이를 손쉽게 GitHub에 업로드 할 수 있다. (이 외에 SVN과 Git 등 기본적인 버전 관리 시스템과의 연동 역시 지원한다) GitHub으로 아주 복잡한 작업을 하지 않는 한 여기서 지원하는 정도로도 별 어려움 없이 GitHub을 쓸 수 있다. 이를 쓰면 'GitHub이 왜 어렵지?'라는 생각이 들 수도 있을 것이다.

다음과 같은 순서로 실행을 해 보자.

1.  [GitHub](https://github.com/)에 들어가서 계정을 생성한다.
2.  (혹시) R과 RStudio가 없다면 설치한다.
3.  [OS에 적합한 Git](https://support.rstudio.com/hc/en-us/articles/200532077-Version-Control-with-Git-and-SVN)을 설치한다.
4.  어디든 Git의 bash 버전이 깔린다. 이를 실행해서 다음과 같이 입력한다.

[![config](http://datum.io/wp-content/uploads/2014/07/config-300x60.jpg)](http://datum.io/wp-content/uploads/2014/07/config.jpg)

1.  RStudio의 메뉴에서 Tools-Global Options-Git/SVN으로 가서 Git을 설치한 폴더의 git 실행 파일을 찾아서 링크한다.

[![git](http://datum.io/wp-content/uploads/2014/07/git-300x283.jpg)](http://datum.io/wp-content/uploads/2014/07/git.jpg)

1.  RStudio를 재시작한다.
2.  GitHub의 개인 페이지로 가서 데이터를 업로드할 프로젝트를 만든다.

[![github](http://datum.io/wp-content/uploads/2014/07/github-300x183.jpg)](http://datum.io/wp-content/uploads/2014/07/github.jpg)

그럼 다음과 같은 프로젝트가 생긴다.

[![github2](http://datum.io/wp-content/uploads/2014/07/github2-300x196.jpg)](http://datum.io/wp-content/uploads/2014/07/github2.jpg)

1.  RStudio에서 File-New Project-Version Control-Git으로 가서 다음과 같이 만든다.

[![github3](http://datum.io/wp-content/uploads/2014/07/github3-300x214.jpg)](http://datum.io/wp-content/uploads/2014/07/github3.jpg)

이 때 URL은 이전 GitHub 프로젝트 페이지의 오른쪽 하단의 http 주소를 입력한다.

1.  그러면 해당 프로젝트에 대한 새 RStudio 창이 열린다. 거기에 필요한 코드들을 작성한다.

```
summary(cars)
```

```
##      speed           dist
##  Min.   : 4.0   Min.   :  2
##  1st Qu.:12.0   1st Qu.: 26
##  Median :15.0   Median : 36
##  Mean   :15.4   Mean   : 43
##  3rd Qu.:19.0   3rd Qu.: 56
##  Max.   :25.0   Max.   :120
```

혹은 문서를 만들거나, 그래프를 그리거나 할 수도 있다.

[![gr](http://datum.io/wp-content/uploads/2014/07/gr-300x214.png)](http://datum.io/wp-content/uploads/2014/07/gr.png)(문서를 작성하는 경우) R Markdown을 사용하여 문서를 만든다. (본 문서도 이렇게 만들어졌다.) html로 바로 변형해서 사용해도 되고, (GitHub에서는 기본 markdown을 지원하므로 md파일은 바로 볼 수 있다. ) md파일로 변형할 수도 있다.

> library(knitr)
>
> knit("RGitHub.Rmd")

 그 후 이렇게 생성된 파일을 GitHub 에 올립니다. RStudio 상단의 Git 버튼 - Commit/Push(변경된 파일을 Commit한 후 Push해서 GitHub으로 업로드) 를 사용합니다.

[![git1](http://datum.io/wp-content/uploads/2014/07/git1.jpg)](http://datum.io/wp-content/uploads/2014/07/git1.jpg)

그 다음 웹에서 GitHub의 자신의 프로젝트 페이지에 가면, 자신이 작성한 프로젝트 파일들이 잘 업로드된 것을 볼 수 있을 것이다.

파일을 수정한 후에도 동일하게 Commit하여 수정된 내용만 업데이트할 수 있고, 필요시 과거 이력을 확인해서 원상복구하거나 다른 사람들과 공동작업을 원활하게 할 수 있다.

이를 활용해 R 코드,R Markdown 파일, 개인 R 패키지 등을 생성해서 손쉽게 GitHub에 공유하여 활용할 수 있다.

(해당 내용은 동일한 과정으로 [GitHub Project](https://github.com/cojette/RGitHubTest)에 html 및 Rmd 파일이 동일하게 올라가 있다. 이 내용과 동일한 [md 파일 내용은 여기서](https://github.com/cojette/RGitHubTest/blob/master/RGitHub.md%C2%A0) 확인할 수 있고, html converting 내용은  <http://htmlpreview.github.io/> 를 활용해서 볼 수 있다. 이 글의 내용은 [다음](http://htmlpreview.github.io/?https://github.com/cojette/RGitHubTest/blob/master/RGitHub.html)과 같다.

*여기서는 아주 기본적인 GitHub으로 '공유'하는 내용만 올린 것이므로 상세한 버전 관리는 GitHub 관련 자세한 내용을 참고하면 좋다.* )

(참고 사이트:<http://www.molecularecologist.com/2013/11/using-github-with-r-and-rstudio/>, <https://support.rstudio.com/hc/en-us/articles/200532077-Version-Control-with-Git-and-SVN?version=0.98.945&mode=desktop>)
