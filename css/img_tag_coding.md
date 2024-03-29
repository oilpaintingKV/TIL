## 이미지 처리 시 고려해야 할 4가지
### 이미지 처리 시 고려해야 할 4가지

#### 1. 부모 요소 `div.image` 에 `width`, `height` 값 지정
  - 이미지가 로딩되지 않는 경우에 `img`태그에만 값을 설정해두었다면, 그 공간이 사라져 레이아웃이 깨지게 된다.
  - 다음과 같이 이미지를 감싸고 있는 부모 요소에 `width`, `height` 값을 지정해주어야 한다.

#### 2. resizing 처리
  -  잡아둔 width, height 값보다 작은 이미지가 들어왔을 시, resizing을 어떻게 처리해야 할 지에 대해 생각해야한다.
      - 이미지 고유의 크기를 살린다 vs 그냥 늘려서 맞추어 준다

#### 3. 투명 이미지 처리
  - 쇼핑몰과 같은 사이트는 특성 상 제품 배경 색상이 화면의 배경 색상과 같은 경우(배경이 투명인 이미지 등)가 있을 수 있어, `border`를 주거나, `background`에 이미지, 색상을 주는 등의 작업이 필요하다.
    
#### 4. 이미지 에러 처리 (이미지를 못 불러왔을 때)
```html
<img src="" alt="" onerror="this.src='./image/img_no.png'">
```
  - `onerror` 속성을 추가해주어 이미지를 불러오지 못했을 때의 이미지 처리를 진행해 주어야 한다.
