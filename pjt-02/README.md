# pjt-02
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@100..900&display=swap" rel="stylesheet">
    <style>
        * {
            font-family: "Noto Sans KR", serif;
            font-optical-sizing: auto;
            font-weight: bold;
            font-style: normal;
        }
```
폰트 설정을 하고 싶을 때는 link등으로 폰트를 불러와서
위와 같은 방법으로 폰트를 설정할 수 있다
위의 경우는 전체 폰트를 Noto Sans KR로 설정하고 있지만
클래스 별로 다른 폰트를 적용하여 일부에도 폰트를 설정할 수 있다.
```css
input[type="radio"]:hover+.selected,
        input[type="checkbox"]:hover+.selected {
            color: #0d6efd;
            border: solid 1px #0d6efd;

        }

        input[type="radio"]:checked+.selected,
        input[type="checkbox"]:checked+.selected {
            background-color: #0d6efd;
            color: white;

            border-right: solid 1px white;
            border-left: solid 1px white;

            border-top: solid 1px #0d6efd;
            border-bottom: solid 1px #0d6efd;
        }
```
라디오 버튼(input type="radio")/체크 박스(input type="checkbox")의 경우 기본 형태를 변형하기 어렵기 때문에
다른 형태로 해당 기능을 구현할 때는 기본의 버튼을 숨기고 다른 태그를 통해
해당 버튼 들의 기능을 구현한다. 
그럴 경우 버튼에 커서를 올렸을 때나 버튼을 눌렀을 때 css를 변경하고 싶다면 
커서를 올렸을 때 : hover
선택했을 때 : checked를 위와 같은 형태로 사용하여 css를 변경할 수 있다. 
(그 외 :
    focus : tab키 등으로 버튼이 선택된 경우
    active : 버튼을 클릭하고 클릭을 해제할 때까지)
```html
<a class="nav-link text-dark bg-primary-subtle" href="portfolio.html#portfolio-edit">포트폴리오</a>
```
a 태그를 통해서 링크를 통해서 이동한다는 것은 다른 경로로 이동하는 것이다.
인터넷 웹 페이지도 서버에 저장된 파일을 유저가 볼 수 있게 접근하는 것이므로
파일이 로컬에 있는 경우, a 태그의 href 속성을 이용해 상대 경로 또는 절대 경로로 이동할 수 있다.
또한 파일의 특정 지점을 불러올 수도 있는데 href의 경로#id 형식으로 작성하면 
해당 경로에 존재하는 해당 id 위치로 스크롤된다.
이 이동 방법을 사용할 경우 페이지가 즉시 이동하는데
```css
html {
  scroll-behavior: smooth;
}

```
위의 코드를 사용해서 부드러운 스크롤 효과를 추가할 수 있다.(부트스트랩 기본인듯)

---
그 외 알게 된 사항

    border-daius는 top bottom 같은 구분이 아닌 선언 순서에 따라 값 부여
    - 상단은 직각, 하단은 둥글게 하는 예시 border-radius: 0 0 10px 10px;


어려웠던 점

    - 어떤 태그에 클래스를 적용해야 CSS가 바르게 적용되는지
      - 해당 사항의 경우 개발자 도구로 판단하는 것이 빠르다고 느꼈다
    - 시멘틱 태그의 구성
      - 참고한 내용
       1. header 내부에 포함될 수 있는 요소  
            nav (주로 내비게이션 메뉴)  
            h1 ~ h6 (제목 요소)  
            p (소개 텍스트)  
            logo (로고를 위한 img 또는 span)  

        2. nav 내부에 포함될 수 있는 요소  
            ul, ol (메뉴 목록)  
            li (각 메뉴 항목)  
            a (링크 요소)  
            button (메뉴 토글 버튼 등)  

        3. main 내부에 포함될 수 있는 요소  
            article (독립적인 콘텐츠)  
            section (논리적 그룹핑)  
            aside (부가 정보)  

        4. article 내부에 포함될 수 있는 요소  
            h1 ~ h6 (제목)  
            p, img, figure, figcaption (본문 내용)  
            section (세부 내용 구분)  
            footer (관련 링크, 작성자 정보)  

        5. section 내부에 포함될 수 있는 요소  
            h1 ~ h6 (섹션 제목)  
            p, img, figure (콘텐츠)  
            article (연관 콘텐츠)  

        6. aside 내부에 포함될 수 있는 요소  
            nav (사이드바 내 내비게이션)  
            p, img, ul (광고, 링크 등)  

        7. footer 내부에 포함될 수 있는 요소  
            p (저작권 정보)  
            nav (푸터 내 메뉴)  
            address (연락처 정보)  
            small (부가 정보)
  

아쉬운 점 


    시간 부족으로 만들지 못한 것
    - grid를 사용한 커뮤니티 란(이미지 활용)
    - 로그인 페이지
    - 로그아웃한 상태의 홈페이지