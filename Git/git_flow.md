# git rep 옮길 때 Mirror 방식
Mirror를 사용하면 git 이력이 모두 포함되어 Merge가 된다.

## 1.기존 git 주소를 복사하여 다운 받는다.
    git clone --mirror {기존 git}
    cd {기존 git 프로젝트}
    git remote set-url --push origin {신규 git}
    git push --mirror
> 여기서 잠깐! private일 때는 권한을 신경써줘야 하는 것으로 판단된다.

## 2.위에 방법으로 안될 때
    git clone --bare {기존 git}
    cd {기존 git}
    git push --mirror

## 3.위의 방법이 안될 때
    gitlab project에 들어가서 unprotect를 수행한다.

## 4.다른 방법
    git clone --mirror 
    cd {기존 리파지토리 명}.git
    git remote set-url --push origin {신규 리파지토리 주소}
    git push --mirror

------------

# Github Private 저장소에 접근이 안될때

## 1.우선 Git Config 확인
    git --list 
    git --list --global

## 2.확인 결과
실제 Github Private에 접근하기위해서는 Token 값이 있어야함.
    git config --global --add url."https://oauth2:{token}@{github project}/".insteadOf "{github project url}"

------------
------------
# GitLab Branch 전략 및 Pipeline 구성하기

## 1.GitLab 설치

## 2.GitLab 프로젝트 생성

## 3.GitLab Web Hook로 Slack 연동

Slack에다가 Add APPS를 한다.

Incomming Webhooks를 추가한다.

slack App directory 페이지에서 연동할 Channel을 선택한다.

channel 선택 후 Add를 하면 아래와 같이 Slack hooks 주소를 준다.

https://hooks.slack.com/services/{T017GDLRQUR/B02NUEM8RPB/oqI7tIGf7bHhbtGvFTuJFT8y}

GitLab 해당 프로젝트로 접속하여 Slack hooks 주소를 입력해준다.

GitLab 해당 프로젝트  Settings > Intergrations를 클릭한다.

그곳에서 Webhooks 주소에 입력 후 Test를 하면 slack으로 정상적으로 값이 넘어 오는 것을 확인 할 수 있다.