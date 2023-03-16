## wai-aria를 이용한 tab 구현하기
### tab?
tab 이란 주메뉴, 하위 메뉴보다는 작은 개념으로, 한 주제에 대해 여러 개의 세부 섹션을 표현하는 방법 중의 하나이다. 

### tab의 3가지의 요소 
  1. **tab list :** tab, tab panel을 하나의 그룹으로 묶어 `tab list`라고 표현. 만약 같은 페이지에 두 개의 tab 섹션이 있다면 두 개의 tab 리스트가 존재하는 것.
  2. **tab :** 리스트의 하위 영역으로 각각의 tab 요소. 만약 하나의 tab 리스트에 4개의 요소가 있다면, 4개의 tab이 존재하는 것. `role="tablist"`, `role="tab"`을 사용하여 tab을 구현하면 스크린리더기가 현재 선택된 tab이 몇 번째 tab 인지 등을 알려줌.
  3. **tab panel :** 각각 tab의 하위 콘텐츠.

### tab 구현
#### AS-IS
```html
<ul class="lst_tab">
  <li><button>1번</button></li>
  <li><button>2번</button></li>
  <li><button>3번</button></li>
  <li><button>4번</button></li>
</ul>

<div class="tab_cnt">
  <div>1번 콘텐츠</div>
  <div>2번 콘텐츠</div>
  <div>3번 콘텐츠</div>
  <div>4번 콘텐츠</div>
</div>
```

#### TO-BE
```html
<ul class="lst_tab" role="tablist">
  <li role="presentation">
    <button id="tab_1" type="button" role="tab" aria-selected="false" aria-controls="tabpanel_1">1번</button>
  </li>
  <li role="presentation">
    <button id="tab_2" type="button" role="tab" aria-selected="true" aria-controls="tabpanel_2">2번</button>
  </li>
  <li role="presentation">
    <button id="tab_3" type="button" role="tab" aria-selected="false" aria-controls="tabpanel_3">3번</button>
  </li>
  <li role="presentation">
    <button id="tab_4" type="button" role="tab" aria-selected="false" aria-controls="tabpanel_4">4번</button>
  </li>
</ul>

<div class="tab_cnt">
  <div id="tabpanel_1" role="tabpanel" aria-labelledby="tab_1">1번 콘텐츠</div>
  <div id="tabpanel_2" role="tabpanel" aria-labelledby="tab_2">2번 콘텐츠</div>
  <div id="tabpanel_3" role="tabpanel" aria-labelledby="tab_3">3번 콘텐츠</div>
  <div id="tabpanel_4" role="tabpanel" aria-labelledby="tab_4">4번 콘텐츠</div>
</div>
```
