## .blind
### blind 란?
- 리더기엔 읽히게 하지만, 화면에서 보여주고 싶지 않을 때 blind(hidden) 클래스를 생성하여 사용하곤 한다.
- `text-indent`를 사용하는 방식은, tab으로 이동 시 화면이 이동되어버리는 오류가 생길 수 있어 수정해야 할 필요성이 있다.

#### AS-IS
```css
.hidden{display:block;overflow:hidden;position:absolute;left:-1000%;width:1px;height:1px;color:#fff;}
```

#### TO-BE
```css
.blind{overflow:hidden;position:absolute;width:1px;height:1px;margin:-1px;padding:0;clip:rect(0,0,0,0)}
```
