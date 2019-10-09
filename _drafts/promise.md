---
title: [JavaScript] Promise
categories: JavaScript
tags: [JavaScript, promise]
excerpt:
---

```javascript 1.8
//프로미스 생성
function sendAjax(url) {
  return new Promise(function(resolve) {
    const xhr = new XMLHttpRequest();
    xhr.addEventListener("load", function() {
        resolve(xhr.responseText);
    });
    xhr.open("GET", url);
    xhr.send();
    });
}

//프로미스 실행
sendAjax(url).then(function(result) {
  console.log(result);
}, function(err) {
  console.log(err);
});
```
