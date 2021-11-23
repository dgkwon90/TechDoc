# git rep 옮길 때 Mirror 방식
Mirror를 사용하면 git 이력이 모두 포함되어 Merge가 된다.

## 1. 기존 git 주소를 복사하여 다운 받는다.
    git clone --mirror {기존 git}
    cd {기존 git 프로젝트}
    git remote set-url --push origin {신규 git}
    git push --mirror
> 여기서 잠깐! private일 때는 권한을 신경써줘야 하는 것으로 판단된다.

## 2. 위에 방법으로 안될 때
    git clone --bare {기존 git}
    cd {기존 git}
    git push --mirror

## 3. 위의 방법이 안될 때
    gitlab project에 들어가서 unprotect를 수행한다.

## 4. 다른 방법
    git clone --mirror 
    cd {기존 리파지토리 명}.git
    git remote set-url --push origin {신규 리파지토리 주소}
    git push --mirror

------------

# Github Private 저장소에 접근이 안될때

## 1. 우선 Git Config 확인
    git --list 
    git --list --global

## 2. 확인 결과
실제 Github Private에 접근하기위해서는 Token 값이 있어야함.
    git config --global --add url."https://oauth2:{token}@{github project}/".insteadOf "{github project url}"