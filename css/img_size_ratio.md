## 이미지 사이즈 비율 맞추는 방법
### 1. object-fit
  ```css
  img {
    width: 값;
    height: 값;
    object-fit: 속성;
  }
  
  -> 너비와 높이 값을 입력하고, object-fit 속성만 지정해주면 됨
  ```
  | 속성 | 특징 |
  | --- | --- |
  | fill | 기본값 / 주어진 너비와 높이에 맞도록 사이즈 조절 / 이미지 가로세로 비율 유지 X |
  | contain | 이미지 가로세로 비율 유지O / 비율이 맞지 않는 경우 자리 남음 |
  | cover | 이미지 가로세로 비율 유지O / 비율이 맞지 않더라도 확대하여 잘라서 채워넣음 |
  | none | 본래 이미지 사이즈 유지 / container보다 큰 이미지의 경우 이미지 가운데로 보여짐 |
  | scale-down | none 또는 contain 중에 더 적절한 방향으로 이미지 사이즈 조절 |
  
![Untitled](https://user-images.githubusercontent.com/126733056/233889597-5414da3a-4b78-4dca-b1fe-ac7a49bebcaf.png)

### 2. position: absolute
  ```css
  .container {
    position: relative;
    width: 값;
    height: 값;
    overflow: hidden;
  }
    
  .container > img {
    position: absolute;
  /* width: 100%; height: auto; -> 가로폭 기준
      height: 100% width: auto; -> 세로폭 기준 */
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  
  -> 이미지를 position:absolute로 띄운 다음, 컨테이너에게 overflow:hidden 을 주어 넘치는 부분 자름
  -> 이미지를 정렬하기 위해 top, left, transform 속성 사용
  ```

![Untitled (1)](https://user-images.githubusercontent.com/126733056/233889623-bef81e98-6002-4cf5-b841-d24d3430221c.png)

### 3. background-size
  ```css
  .container {
    background-image: url("이미지url") no-repeat 50%;
    background-size: 속성;
  }
  ```
  | 속성 | 특징 |
  | --- | --- |
  | contain | 이미지 가로세로 비율 유지O / 비율이 맞지 않는 경우 자리 남음 |
  | cover | 이미지 가로세로 비율 유지O / 비율이 맞지 않더라도 확대하여 잘라서 채워넣음 |
  
![Untitled (2)](https://user-images.githubusercontent.com/126733056/233889641-7f5116dd-a178-4b82-8882-1a3fcd9f161b.png)

