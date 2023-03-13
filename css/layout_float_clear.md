## float 해제하는 방법

### float를 해제하는 9가지 방법
1. **float가 적용된 요소의 부모태그에 높이 값 적용**
    - 반응형시 자동 높이 값 설정 불가
2. **float가 적용된 요소의 부모태그에 `overflow:hidden` 적용**
    - 해당 요소를 벗어나는 컨텐츠가 가려질 수 있음 (tab 포커스 또한 가려짐)
3. **float가 적용된 요소의 부모태그에 `overflow:auto` 적용**
    - 스크롤 바 표시될 수 있음
4. **float가 적용된 요소의 부모태그에 `float` 설정**
    - `inline-block` 되며, 다른 요소에도 영향이 갈 수 있음
5. **float가 적용된 요소의 부모 태그에 `display:inline-block` 적용**
    - `inline-block` 으로 무조건 만들어지기 때문에 원하는 레이아웃에 제약이 갈 수 있음
7. **float가 적용된 요소의 다음에 나오는 태그에 `clear:both` 지정**
    - `clear:both`가 적용된 요소에는 `margin-top` 적용 불가 및 불필요한 태그 사용
8. **float가 적용된 요소의 부모태그에 가상요소를 만들고 그 가상요소에 `clear:both` 지정**
    - 가장 보편적인 방법
    ```CSS 
      float된 요소의 부모태그::after{content:'';display:block;clear:both;}
    ```
9. **float가 적용된 요소의 부모태그에 `display:flow-root` 지정**
    - 가장 적은 스타일링으로 clear 가능, 그러나 IE 이슈 존재
    ```CSS 
      부모태그{display:flow-root}
    ```

- 일반적으로 주로 8번을 사용한다.
