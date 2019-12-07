## service worker生命周期
- 注册
- 下载，解析和执行
- 安装
- 激活

## 注册
调用register函数, service worker开始下载

## 下载，解析和执行
在注册过程中, 浏览器会开始下载, 解析并执行service worker，如果在此步骤出现任何的错误，resigter返回的promise都会执行reject操作，并且service worker会被废弃.

## 安装
一旦service worker成功执行，安装事件就会激活， service worker是基于事件的，意味着我们可以利用这些事件来实现超快速缓存技术。

## 激活
一旦安装完成，worker就被激活，并控制其范围内的一切，如果生命周期中的所有事件都成功了，worker便准备就绪，随时可以使用。

## 备注
当第一次加载页面时，service worker还没有激活，所以它不会处理任何的请求，只有当它安装和激活后，才能控制其范围内的一切，这意味着，只有刷新页面或导航到另一个页面。service worker内的逻辑才会启动。
