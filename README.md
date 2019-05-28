# Bootstrap-select

:star: **[bootstrap-select](https://github.com/snapappointments/bootstrap-select)**

<br/>

### 1. 기존 Bootstrap-select 문제 
- **Electron**에서 `bootstrap-select` 최신 버전을 사용시 **ipc통신**에서 오류.<br/>
- bootstrap-select의 이전 버전 사용하면 한글 검색(live-search) 시 커서 위치가 단어 맨 앞으로 이동되는 오류.<br/>

-> 위 두 가지 오류 해결한 파일

<br/>

### 2. 사용 방법(예)

-> Html
```html
<select class="selectpicker" data-live-search="true">
</select>
```
-> Javascript
```javascript
const selectbox = document.querySelector(".selectpicker");
const selectpicker = $(selectbox).selectpicker();

ipcRenderer.send('getData', {});
ipcRenderer.on('setData', function (event, items) {
  for (let p in items) {
    $(selectbox).append(`<option val='${p}'>${p}</option>`);
  }
  $(selectbox).selectpicker('refresh');
});

```

<br/>


### 3. CSS
bootstrap-select 의 css 파일은 최신 버전의 bootstrap-select를 사용하면 된다.
- github : [bootstrap-select](https://github.com/snapappointments/bootstrap-select)
- npm : `$ npm install bootstrap-select`






