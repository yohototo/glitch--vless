# glitch--vless

1.[注册并创建一个项目，删除所有的默认配置文件](https://glitch.com/)  

2.[上传app.js和package.json 就行](https://github.com/yohototo/glitch-nodejs-proxy)  
修改代码的中uuid并保存，预览网页，获得glitch域名地址
3.cloudflare worker 反代代码,替换“flexible-kaylee-kj123.koyeb.app”为自己的glitch域名地址
```
export default {
  async fetch(request, env) {
    let url = new URL(request.url);
    if (url.pathname.startsWith('/')) {
      url.hostname = 'flexible-kaylee-kj123.koyeb.app'
      let new_request = new Request(url, request);
      return fetch(new_request);
    }
    return env.ASSETS.fetch(request);
  },
};
```
v2rayN 节点写法
![image](https://github.com/yohototo/glitch--vless/assets/35169273/bfab30e7-99d3-4fd5-b35d-0e5ca925b46e)
