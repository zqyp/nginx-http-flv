# nginx-http-flv

## 问题记录
1. 浏览器多次刷新直播视频会加载不出来

   nginx.conf 中 worker_processes设置,作者推荐1的方式，因为推流到多个
   worker上，拉流时HTTP 请求是被随机分配给 worker 进程的，有可能http
   拉的worker没有publish流，就会造成视频无法播放。