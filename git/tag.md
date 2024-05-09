# Tag
---

## Tag 목록

```bash
$ git tag
v0.1
v1.3
```

## Tag 조회

검색 패턴을 통해 Tag를 검색할 수 있다. 

```bash
$ git tag -l "v1.8.5*"
v1.8.5
v1.8.5-rc0
v1.8.5-rc1
v1.8.5-rc2
v1.8.5-rc3
v1.8.5.1
v1.8.5.2
v1.8.5.3
v1.8.5.4
v1.8.5.5
```

> Note 
> 와일드카드를 사용하여 Tag 리스트를 확인하려면 -l, --list 옵션을 지정

## Tag 붙이기
Git의 태그는 Lightweight 태그와 Annotated 태그로 두 종류가 있다.

* Lightweight:
  - 특정 커밋을 가르키는 역할(포인터)
  - 단순히 태그이름만 저장

```bash
$ git tag v1.0.2
```
   
* Annotated:
  - 만든 사람 이름,만든 날짜, 이메일, 메시지를 저장
  - GPG(GNU Privacyt Guard) 서명 가능

```bash
$ git tag -a v1.0.3 -m "Release version 1.0.3"
```

GPG서명이 있다면 *-s* 옵션을 사용하여 Tag에 서명할 수 있다.
```bash
$ git tag -s -v1.0.3 -m "Release version 1.0.3"
```



## Tag 보기
Tag 메시지와 커밋정보를 확인할수 있습니다.

```bash
$ git show v1.0.3

tag v1.0.3
Tagger: pryaoh <yaoh+github@gmail.com>
Date:   Sat Feb 15 17:53:49 2014 +0900

Release version 1.0.3
```

## Tag 원격 저장소에 올리기

특정 Tag 올리기
```bash
$ git push origin v1.0.3
```

모든 태그 올리기
```bash
$ git push origin --tags
```

## Tag 삭제하기

```bash
$ git tag -d v1.0.0
```

원격 저장소에 Tag를 삭제하기 위해서는 *:*를 사용하여 삭제할 수 있다.
```bash
$ git push origin :v1.0.0
```


## 참고
- [git tag](https://git-scm.com/book/ko/v2/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-%ED%83%9C%EA%B7%B8)

