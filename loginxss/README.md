# 登入系統xss漏洞問題  
## 詳情:  
觀察登入系統網址: http://www.sggs.hc.edu.tw:8080/news2/admin.asp?post_group=&post_team=  
若將連結改為: [http://www.sggs.hc.edu.tw:8080/news2/admin.asp?post_group="><script>alert("xss")</script>&post_team=](http://www.sggs.hc.edu.tw:8080/news2/admin.asp?post_group="><script>alert("xss")</script>&post_team=)  
發現可以透過更改網址插入片段程式碼，雖然不危及整體系統安全問題，可是卻可能被插入導向惡意網站的指令並轉發而假借學校發送惡意連結，也不是件好事。  
## 解決方法:
在原始碼中建立白名單，抓出不該出現的字元並禁止它出現
