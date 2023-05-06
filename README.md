# foxe-get-proof
批量调用获取proof

## 以下代码，直接复制到浏览器控制台中，修改你的钱包地址，然后运行即可

```js
let success = false;
let yourAddress = ""//请复制你的地址在这里
while (!success) {
  try {
    const response = await fetch("https://api.foxe.vip/api/merkle/" + yourAddress, {
      "headers": {
    "accept": "*/*",
    "accept-language": "zh-CN,zh;q=0.9,en-US;q=0.8,en;q=0.7",
    "sec-ch-ua": "\"Chromium\";v=\"112\", \"Google Chrome\";v=\"112\", \"Not:A-Brand\";v=\"99\"",
    "sec-ch-ua-mobile": "?0",
    "sec-ch-ua-platform": "\"macOS\"",
    "sec-fetch-dest": "empty",
    "sec-fetch-mode": "cors",
    "sec-fetch-site": "same-site"
  },
  "referrer": "https://www.foxe.vip/",
  "referrerPolicy": "strict-origin-when-cross-origin",
  "body": null,
  "method": "GET",
  "mode": "cors",
  "credentials": "omit"
    });
    const data = await response.json();
    console.log(data);
    success = true;
  } catch (error) {
    console.error(error);
  }
  await new Promise(resolve => setTimeout(resolve, 15000));
}
```
