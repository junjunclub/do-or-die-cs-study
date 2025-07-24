# do-or-die-cs-study
제대로 안 하면 없어지는 CS 스터디입니다.

## 1. 스터디 도서
<img src="이것이 취업을 위한 컴퓨터 과학이다.jpg" width="300" height="400"/>  
<br>  

- [이것이 취업을 위한 컴퓨터 과학이다.](https://www.hanbit.co.kr/store/books/look.php?p_code=B3079890360)
- 진행 목차
  1. CHAPTER 01 기술 면접과 실무를 위한 컴퓨터 과학
  2. CHAPTER 02 컴퓨터 구조
  3. CHAPTER 03 운영체제
  4. CHAPTER 04 자료구조
  5. CHAPTER 05 네트워크
  6. CHAPTER 06 데이터베이스

## 5. Collaborator
| <a href="https://github.com/won-ee"><img src="https://github.com/won-ee.png" width="100"></a> | <a href="https://github.com/MINJOO-KIM"><img src="https://github.com/MINJOO-KIM.png" width="100"></a> | <a href="https://github.com/junjunclub"><img src="https://github.com/junjunclub.png" width="100"></a> | <a href="https://github.com/JAEKWANG97"><img src="https://github.com/JAEKWANG97.png" width="100"></a> | <a href="https://github.com/suhrin-huh"><img src="https://github.com/suhrin-huh.png" width="100"></a> |
| --- | --- | --- | --- | --- |
| 고충원<br>([@won-ee](https://github.com/won-ee)) | 김민주<br>([@MINJOO-KIM](https://github.com/MINJOO-KIM)) | 김여준<br>([@junjunclub](https://github.com/junjunclub)) | 유재광<br>([@JAEGWANG97](https://github.com/JAEKWANG97)) | 황민채<br>([@suhrin-huh](https://github.com/suhrin-huh)) |

아래는 현재 스터디의 폴더 구조와 흐름에 맞게 **README에 바로 붙일 수 있도록 예쁘고 명확하게 꾸민 컨벤션 섹션**입니다.
기존 마크다운 스타일과 자연스럽게 어우러지도록 디자인했습니다.

---

## 6. ✅ 스터디 컨벤션

**이 스터디는 "무조건 한다"는 각오로 진행합니다. 아래 규칙을 꼭 지켜주세요.**

---

### 📁 디렉토리 & 파일 구조

```
📁 이것이 취업을 위한 컴퓨터 과학이다/
 └── 📁 {챕터번호}. {챕터이름}/
      └── 📁 {이니셜 or GitHub ID 소문자}/
           └── CH{번호}_{주제명}.md
```

#### ✅ 예시

```
📁 이것이 취업을 위한 컴퓨터 과학이다/
 └── 📁 2. Computer Architecture/
      └── 📁 yj/
           └── CH02_컴퓨터구조.md
 └── 📁 3. Operating System/
      └── 📁 mj/
           └── CH03_운영체제.md
```

> **주의**
>
> * 폴더 이름, 파일 이름, 이니셜은 통일된 양식으로 작성합니다.
> * 챕터 번호는 항상 두 자리로(`CH01`, `CH02`, …)

---

### 🌿 브랜치 규칙

* 브랜치는 **자신의 GitHub ID**로 생성합니다.
* 챕터 번호는 브랜치명에 **포함하지 않습니다**.

#### ✅ 예시

```
JAEKWANG97
mj
won-ee
```

---

### ✍️ 파일 작성 규칙

* 마크다운(.md) 파일로 작성
* 자유롭게 정리하되 아래와 같은 구성 권장:

```md
# CH02. 컴퓨터 구조

## 📌 핵심 개념 요약
- 하버드 구조 vs 폰 노이만 구조
- 파이프라이닝의 장단점

## 💡 면접 예상 질문
- 캐시 메모리는 왜 필요한가요?
- RISC와 CISC의 차이점은?

## ❓스터디에서 논의하고 싶은 질문
- 컨트롤 유닛이 명령어 디코딩 시 수행하는 실제 동작은?

## 🔗 참고 자료
- [CS 정리 블로그](https://example.com)
```

---

### 🔀 Pull Request 규칙

* 자신의 브랜치 → `main`으로 PR을 보냅니다.
* PR 제목 형식:

  ```
  {이름 or ID} / CH{번호} / {주제명} 정리 완료
  ```
* 예시:

  ```
  유재광 / CH02 / 컴퓨터구조 정리 완료
  won-ee / CH03 / 운영체제 요약
  ```

#### ✅ PR 본문 템플릿 (복붙해서 사용하세요)

```md
## 📚 정리 요약
- 명령어 사이클 정리
- 제어 유닛, ALU, 레지스터 관계 정리

## ❓논의하고 싶은 질문
- 캐시 적중률이 CPU 성능에 미치는 영향은?

## ✅ 체크리스트
- [ ] 
```
