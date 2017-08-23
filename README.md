# Google Form
- 為什麼要用Google Form
  - 能任意設計外觀的Contact form
  - 幫使用者整理好回饋資訊
<br>

# 流程
### Google雲端
  - 新增 > Google表單 > 右下角有一個？ > 點選 **"返回舊表單"**
  - 編輯完後 上面有一個查看回應點 **選建立表單**，略過這步驟會收不到回應喔
  - 點選 **查看即時表單**
    - 開啟開發者模式，從```<div class="ss-form">```開始複製到```</tr></tbody></table></div></ol></form></div>```
<br>


### 程式碼
- 自訂6~8英文權杖, 例如hahaha
```
<iframe name="iframe_權杖" id="iframe_權杖" style="display:none;" onload="if(typeof sent_權杖!='undefined'){window.location='googleForm.html';}"></iframe>
  ```

- 把上面這一串插在```<div class="ss-form">```後面

- 在iframe後面的form Tag裡，改寫成這樣
```
target="iframe_權杖"  //target其實跟前面的id一樣喔
onsubmit="sent_權杖=true"
```

- 當表單填寫完後寄出重回自己的頁面的功能：
```
{window.location='原頁面的名稱.html';} // eg:googleForm
```

- 當要跳到特定位置手機版會有bug
  - 可以使用location.reload();
  ```
  window.location='index.html#contact'; location.reload();
  ```
