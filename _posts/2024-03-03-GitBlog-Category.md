---
layout: single
title: "Git Blog"
categories:
  - GitBlog
---


# GitBlog-Category
**목차**

---


```markdown
1. navigation.yml - Category 정의
2. Post - Category 추가
3. Page - Category에 맞는 Post가 포함되도록 정의
4. Category - Page 연결
5. _config.yml을 수정하여 SideBar 위치에 Category 표시
```

---
1. navigation.yml - Category 정의
    - Category 속성을 찾아 갈 수 있도록 navigation 정의
  
---
<br>**main:**  
&nbsp;title: "여기에 뭘 넣으면 좋을까"  
&nbsp;url: https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/  

**sidebar-category:<br>**
&nbsp;&nbsp;title: "Plan"<br>
&nbsp;&nbsp;url: "Plan"<br>
&nbsp;&nbsp;title: "Study"<br>
&nbsp;&nbsp;children:<br>
&nbsp;&nbsp;title: "Test"<br>
&nbsp;&nbsp;url: "/Test"<br>
&nbsp;&nbsp;title: "정보처리기사"<br>
&nbsp;&nbsp;url: "/exam"  
&nbsp;&nbsp;title: "Azure"<br>
&nbsp;&nbsp;url: "/Azure"<br>
<br>

---

**2.&nbsp;Post - Category 추가**

---
-&nbsp;-&nbsp;-<br>
layout: single  
title: "Git Blog, Category 생성 과정"  
categories:  
&nbsp; -&nbsp;Plan
<br>-&nbsp;-&nbsp;-

---

**3. Page - Category에 맞는 Post가 포함되도록 정의**

---

- root/_pages 하위에 작성 ex) "category-plan.md"  
- layout은 archive로 작성  
- liquid for문은 category 클릭시 plan category를 가진 Post만 표시하는 기능  
---

-&nbsp;-&nbsp;-<br>
title: "Plan"  
layout: archive  
permalink: /Plan
<br>-&nbsp;-&nbsp;-  

{% assign posts = site.categories.Plan %}  
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {%endfor %}

---
**4. _config.yml을 수정하여 SideBar 위치에 Category 표시**

---
defaults:  
  &nbsp;&nbsp;&nbsp;&nbsp;#_posts  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;scope:  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    path: ""  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    type: posts  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  values:  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    layout: single  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    author_profile: true  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    read_time: true  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    comments: # true  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;     share: true  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    related: true  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   sidebar:  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    nav: "sidebar-category"  

---
[공부 Site](https://x2info.github.io/minimal-mistakes/%EC%B9%B4%ED%85%8C%EA%B3%A0%EB%A6%AC_%EB%A7%8C%EB%93%A4%EA%B8%B0/)

---
**문제점**

---

1. post 안에서 sidebar(category)가 안보임.
---
<br>
할 일

---

1. post 안에서 sidebar(category)가 보이게 하기.
2. 자기소개에 사진 넣기.
3. 블로그 최상단 배너에 사진넣기

---