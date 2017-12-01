title: 留言板
date: 2017-09-07 21:43:11
comments: ture
---
欢迎交流: zhuangfifi@gmail.com
<div id="container"></div>
<link rel="stylesheet" href="https://imsun.github.io/gitment/style/default.css">
<script src="https://imsun.github.io/gitment/dist/gitment.browser.js"></script>
<script>
var gitment = new Gitment({
  id: '', //https://fifi1996.github.io/board/
  owner: 'Fifi',  
  repo: 'Comments', 
  oauth: {
    client_id: 'c2c63042a04065f34fd4', 
    client_secret: 'baeeb7babf6a5c64fa9cf1f6b8753409715079de', 
  },
})
gitment.render('container')
</script> 