Golang uber 코드 스타일
===

[우버 Test cse](https://pkg.go.dev/cmd/vet#hdr-Printf_family)

모든 코드는 golint 와 go vet를 실행할 때 에러가 없어야 한다. 또한 우리는 여러분들의 에디터를 아래와 같이 설정하기를 권고한다

Run goimports on save
Run golint and go vet to check for errors

* 여기서 린트(lint)란 무엇인가 소스 코드를 분석하여 
프로그램 오류, 벅, 스타일 오류, 의심 스러운 구조체에 표시를 달아 놓기 위한 도구를 가리킨다.


# 가이드라인(Guidelines)
인터페이스에 대한 포인터(Pointes to Interfaces)
