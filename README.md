# ajax
ajax设计方案封装库

####整理原声ajax设计方案原因如下：
  1. 从资源合理利用的角度以及网站优化角度去想，每次为了那几个功能，去引用一个框架，不划算
  2. 拜读了w3c的ajax的设计方案，包括level1和level2的规范，有种豁然开朗的感觉
  3. 有朋友遇到ajax的跨域方案，各种纠结在心里，导致内心不能舒畅
  4. 自己的框架底层也要需要用到ajax的基础功能，（get post请求，对于level2的上传暂时没用到）
  5. 最关键的也是之前对这块概念十分模糊，所以开始整理ajax这块的设计方案

####一些概念：
    *浏览器的同源策略：浏览器最基本的安全功能，同源是指，域名，协议，端口相同（所以我写的接口部署端口分别为1122和2211即不是同源，属于跨域）    
    *ajax：是一种技术方案，依赖的是CSS/HTML/Javascript，最核心依赖是浏览器提供的XMLHttpRequest对象，这个对象使得浏览器可以发出HTTP请求与接收HTTP响应。    
    *nginx：是一个高性能的HTTP和反向代理服务器    
    *IIS:微软开发的的服务器，window系统自带   
    *XMLHttpRequest Level 1主要存在以下缺点：    
      1. 受同源策略的限制，不能发送跨域请求；   
      2. 不能发送二进制文件（如图片、视频、音频等），只能发送纯文本数据；   
      3. 发送和获取数据的过程中，无法实时获取进度信息，只能判断是否完成；   
    *XMLHttpRequest Level 2中新增了以下功能:    
     1. 可以发送跨域请求，在服务端允许的情况下；    
　　  2. 支持发送和接收二进制数据；   
　　  3. 新增formData对象，支持发送表单数据；    
　　  4. 发送和获取数据时，可以获取进度信息；    
　　  5. 可以设置请求的超时时间；    
    *XMLHttpRequest 兼容性如下：       
  ![](http://images2015.cnblogs.com/blog/801930/201611/801930-20161129224459115-1023971996.png)
