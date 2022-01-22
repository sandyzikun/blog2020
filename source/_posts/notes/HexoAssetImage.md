---
title: Hexo图片问题
date: 2019-04-11 12:40:00
tags:
- Notes(代码笔记)
mathjax: true
---

## I. 安装插件

如果要在Hexo博客上插入图片, 首先要安装一个叫做`hexo-asset-image`的插件, 在博客生成文件的根目录下执行:

```sh
> npm install hexo-asset-image --save
```

## II. BUG补丁

但是这个插件后来更新来更新去的出现了一个BUG, 这时我们需要进入`node_modules`把插件中的`index.js`更改为如下代码:

```js
'use strict';
var cheerio = require('cheerio');

// http://stackoverflow.com/questions/14480345/how-to-get-the-nth-occurrence-in-a-string
function getPosition(str, m, i) {
  return str.split(m, i).join(m).length;
}

hexo.extend.filter.register('after_post_render', function(data){
  var config = hexo.config;
  if(config.post_asset_folder){
    var link = data.permalink;
	var beginPos = getPosition(link, '/', 3) + 1;
	// In hexo 3.1.1, the permalink of "about" page is like ".../about/index.html".
	var endPos = link.lastIndexOf('/') + 1;
    link = link.substring(beginPos, endPos);

    var toprocess = ['excerpt', 'more', 'content'];
    for(var i = 0; i < toprocess.length; i++){
      var key = toprocess[i];
 
      var $ = cheerio.load(data[key], {
        ignoreWhitespace: false,
        xmlMode: false,
        lowerCaseTags: false,
        decodeEntities: false
      });

      $('img').each(function(){
		// For windows style path, we replace '\' to '/'.
        var src = $(this).attr('src').replace('\\', '/');
        if(!/http[s]*.*|\/\/.*/.test(src)){
		  // For "about" page, the first part of "src" can't be removed.
		  // In addition, to support multi-level local directory.
		  var linkArray = link.split('/').filter(function(elem){
		    return elem != '';
		  });
		  var srcArray = src.split('/').filter(function(elem){
		    return elem != '';
		  });
		  if(linkArray[linkArray.length - 1] == srcArray[0])
		    srcArray.shift();
          src = srcArray.join('/');
          $(this).attr('src', '/' + link + src);
        }
      });
      data[key] = $.html();
    }
  }
});
```

然后就可以正常使用了
